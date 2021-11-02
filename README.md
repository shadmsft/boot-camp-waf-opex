<h1>CSA Boot Camp WAF - Operational Excellence Hands On Activity</h1>
The operational excellence pillar covers the operations processes that keep an application running in production. Deployments must be reliable and predictable. Automated deployments reduce the chance of human error. Fast and routine deployment processes won't slow down the release of new features or bug fixes. Equally important, how does your application to respond to spikes in demand, as well as how do you monitor and alert on your applications?

## Resources
* [Overview of the operational excellence pillar](https://docs.microsoft.com/en-us/azure/architecture/framework/devops/overview)
* [Azure Well-Architected Review](https://docs.microsoft.com/en-us/assessments)

## Why are we doing this?

The goal of this activity to give you some hands on experience with several principles Operational Excellence:

  * [Automation of infrastructure](https://docs.microsoft.com/en-us/azure/architecture/framework/devops/automation-overview)
  *  [Application deployment via GitHub](https://docs.microsoft.com/en-us/azure/architecture/framework/devops/release-engineering-cd)
  *  [Monitoring](https://docs.microsoft.com/en-us/azure/architecture/framework/devops/monitoring)
  *  [Alerting](https://docs.microsoft.com/en-us/azure/architecture/framework/devops/alerts)
  *  [Autoscaling](https://docs.microsoft.com/en-us/azure/architecture/best-practices/auto-scaling)

# Objectives

- [Objectives](#objectives)
- [Architecture](#architecture)
- [Prerequisites](#prerequisites)
- [Deploy Azure Monitor Log Analytics Workspace and App Insights](#deploy-azure-monitor-log-analytics-workspace-and-app-insights)
- [Deploy Azure App Service and Web App](#deploy-azure-app-service-and-web-app)
- [Configure App Insights and Diagnostics](#configure-app-insights-and-diagnostics)
- [Configure Azure Alerts and Autoscaling](#configure-azure-alerts-and-autoscaling)
  - [Alerts](#alerts)
  - [Autoscaling](#autoscaling)
- [Query Logs](#query-logs)
- [Clean Up](#clean-up)
- [What did we accomplish?](#what-did-we-accomplish)
- [References](#references)

# Architecture

Once this lab is completed you should have an Architecture that looks something like the diagram below.

 ![image](./media/WAFOpexBootCamp.drawio.png)

# Prerequisites
* An Azure Subscription.

# Deploy Azure Monitor Log Analytics Workspace and App Insights
[Back to Objectives](#objectives)

1. Navigate to the Azure Portal https://portal.azure.com
1. Click on the Cloud Shell. You may be prompted to create a storage account if this is your first time to use the cloud shell.

   ![image](./media/1.png)


1. Ensure that you use Bash for the Cloud Shell

    ![image](./media/2.png)

1. Set the context to the subscription you want to use.
    ```cli
    az account set --subscription "<your subscription name or Id>"
    ```
1. Create a Resource Group and Log Analytics Workspace by typing these commands in the Cloud Shell.

    ```cli
    az group create --name rg-opex --location southcentralus
    ```
    ```cli
    az monitor log-analytics workspace create -g rg-opex -n la-ws-opex
    ```
1. Run the following commands to get the WorkspaceId and the Workspace Key, alternatively you can get them from the Portal as well.
    ```cli
    az monitor log-analytics workspace show -g rg-opex --workspace-name la-ws-opex --query customerId
    ```
    ```cli
    az monitor log-analytics workspace get-shared-keys -g rg-opex --workspace-name la-ws-opex
    ```
#  Deploy Azure App Service and Web App
[Back to Objectives](#objectives)

1. Deploy an App Service Plan and create a Web App
    ```cli
    az appservice plan create -g rg-opex -n asp-opex-1 --location southcentralus --sku S1
    ```
    ```cli
    let randomNum=$RANDOM*$RANDOM
    webAppName=waopex$randomNum
    az webapp create -g rg-opex -p asp-opex-1 -n $webAppName
    ```
    ```cli
    webAppId=$(az webapp show -g rg-opex -n $webAppName --query id --output tsv)
    ```
1. Create a deployment to the Web App, using a sample application
    ```cli
    gitRepo=https://github.com/Azure-Samples/php-docs-hello-world
    ```
    ```cli
    az webapp deployment source config --name $webAppName \
    --resource-group rg-opex \
    --repo-url $gitRepo --branch master \
    --manual-integration
    ```
1. Verify the web app by getting the Url and opening the web site. You should see <b>Hello World!</b>
    ```cli
    echo http://$webAppName.azurewebsites.net
    ```
1. Verify deployment settings in the Portal.
   1. In the portal, navigate to the rg-opex resource group and click on the app service you created.

        ![image](./media/a.png)

    1. Click on the Deployment Center

        ![image](./media/b.png)

    1. Verify that the Repository and Branch are set.

        ![image](./media/c.png)

# Configure App Insights and Diagnostics
[Back to Objectives](#objectives)

1. Configure App Insights for the Web app
    ```cli
    az extension add -n application-insights
    ```
    ```cli
    wsID=$(az monitor log-analytics workspace show --workspace-name la-ws-opex -g rg-opex --query id --output tsv)
    ```
    ```cli
    az monitor app-insights component create --app ai-opex \
    --location southcentralus \
    --kind web \
    --resource-group rg-opex \
    --application-type web \
    --workspace $wsID
    ```
    ```cli
    az monitor app-insights component connect-webapp -a ai-opex \
    -g rg-opex \
    --app ai-opex \
    --web-app $webAppId
    ```
1. Let's verify that the Web App has been configured with your Application Insights you just created.
   1. In the portal, navigate to the rg-opex resource group and click on the app service.

    ![image](./media/d.png)

    1. Click on 'View Application Insights data -->' this will take you to the Application Instights instance.

    ![image](./media/e.png)

1. Create Diagnostic Settings for the Web app
    ```cli
     wsID=$(az monitor log-analytics workspace show --workspace-name la-ws-opex -g rg-opex --query id --output tsv)
    ```
    ```cli
    az monitor diagnostic-settings create --resource $webAppId --name diagWebApp --workspace $wsID --logs '[{"category":"AppServiceHTTPLogs","enabled":true,"retentionPolicy":{"enabled":false,"days":0}},{"category":"AppServiceConsoleLogs","enabled": true,"retentionPolicy":{"enabled":false,"days":0}}]' --metrics '[{"category":"AllMetrics","enabled":true,"retentionPolicy":{"enabled":false,"days":0}}]'
    ```
1. Let's verify the Diagnostic settings were created in the portal.
    1. In the portal, navigate to the rg-opex resource group and click on the app service.

    ![image](./media/a.png)

    1. Click on Diagnostic Settings in the Monitoring Section

    ![image](./media/f.png)

    1. Click on the Edit Settings of the diagWebApp setting

    ![image](./media/g.png)

    1. You should see the settings as we created them in the CLI.

    ![image](./media/h.png)

2. Create some load from the Cloud Shell.  You may leave this running while you complete the lab.
    ```cli
    while true
    do
        curl http://$webAppName.azurewebsites.net
    done
    ```
    Type Ctrl+C when finished with load test after the lab.

#  Configure Azure Alerts and Autoscaling
[Back to Objectives](#objectives)

## Alerts
Now we will configure alerts to let us know when our Web App begins to consume a certain % of CPU Utilization.

1. Navigate to https://portal.azure.com .
1. Ensure you are in your subscription.
1. Navigate or search for Alerts and click on it.

    ![image](./media/13.png)

1. Click on + New alert rule

    ![image](./media/14.png)

1. Click on + Select Scope

    ![image](./media/15.png)

1. Filter by App Service plans and select the asp-opex-1 item then click Done.

   ![image](./media/16.png)

1. Click on Next: Condition >  Then select the CPU Percentage signal

   ![image](./media/17.png)

1. Configure the signal logic, for the lab utilize the graph to make a decision as to when this might trigger. In this scenario, my utilization is pretty low, so I will set it to 2

   ![image](./media/18.png)

1. Click on Next: Action > + Create action group

   ![image](./media/19.png)

1. Create the action group. Save it in rg-opex resource group and name it agEmail

    ![image](./media/20.png)

1. Click on Next: Notifications >
    * Choose: Email/SMS message/Push/Voice
    * Name: EmailMe
    * Email: [ Use your email address ]

    ![image](./media/21.png)

1. Click on Next: Actions >. We won't add any specific actions right now.
1. Click Review + Create.
1. Click Create to finish the action group creation.
1. Click on Next: Details > Setting the following
    * Subscription: Choose your subscription
    * Resource group: rg-opex
    * Severity: Informational
    * Alert rule name: Alert CPU
    * Alert description: CPU Alert
    * Enable upon creation: On
    * Automatically resolve alerts: On

        ![image](./media/22.png)

1. Click on Review + create. Then Create.

## Autoscaling
Now we will configure autoscale for our Web App to scale out and scale in when our Web App begins to consume a certain % of CPU Utilization.

1. Navigate to https://portal.azure.com .
1. Ensure you are in your subscription.
1. Navigate or search for Monitor anc click on it.

    ![image](./media/6.png)

1. In the Settings Section click on Autoscale

    ![image](./media/7.png)

1. Click on the rg-opex App Service Plan deployed previously.

    ![image](./media/8.png)

1. Click on Custom autoscale.

    ![image](./media/9.png)

1. Set the following Values
   1. Scale mode: Scale based on a metric
   2. Rules: + Add Rule - This will be the scale out rule

      ![image](./media/9a.png)

      * Metric Source: Current Resource (asp-opex-1)
      * Time aggregation: Average
      * Metric namespace: App Service plans standard metrics
      * Metric name: CPU Percentage
      * Dimension Name: Instance
      * Operator: =
      * Dimension Values: All Values
      * Operator: Greater than
      *  Metric threshold to trigger scale action: 20  (Set this value below the CpuPercentage in the screen, just to trigger an autoscale. This is just for demonstration purposes, you should carefully evaluate what the actual threshold should be)
      * Duration (minutes): 5
      * Time grain (minutes): 1
      * Time grain statistic: Average
      * Operation: Increase count by
      * Instance count: 1
      * Cool down (minutes): 5

        ![image](./media/10.png)

    1. Repeat the previous step with one minor change to make the Scale in rule.
       1. Set the Metric threshold to trigger scale action: 15
       1. Set the Operation: Decrease count by

            ![image](./media/10a.png)

   3. Now you should have a Scale out and Scale in rule

   4. Instance Limits  Minimum: 1
   5. Instance Limits  Maximum: 1
   6. Instance Limits  Default: 1

        ![image](./media/11.png)


    2. Click Save

        ![image](./media/12.png)

    3. After some time, you can click on the 'Run History' in the tool bar of the auto scale setting to see the observed instance count over time to observe when your app service plan scales out and in.

        ![image](./media/12a.png)

# Query Logs
[Back to Objectives](#objectives)

Now lets learn how to write and execute a KQL Query against Log Analytics.

1. Navigate to https://portal.azure.com
2. Ensure you are in your subscription
3. Navigate to the rg-opex resource group
4. Click on your App Service Web Item Item
5. In the Monitoring Section click on Logs

    ![image](./media/4.png)

6. Close the 'Queries' dialog window.

    ![image](./media/3a.png)

7. Enter the following KQL in the query text box and click Run. Then above the results click on Chart.
    ```kql
        // Response times of requests
        // Avg & 90, 95 and 99 percentile response times (in milliseconds) per App CsHost
        AppServiceHTTPLogs
        | summarize avg(TimeTaken), percentiles(TimeTaken, 90, 95, 99) by CsHost
    ```

    ![image](./media/5.png)

# Clean Up
[Back to Objectives](#objectives)

To clean up the lab, run the following command in the cloud shell.

```cli
az group delete --name rg-opex
```

# What did we accomplish?
[Back to Objectives](#objectives)
* Automated infrastructure deployment using CLI script.
* Configured Monitoring for Logs and Metrics with Diagnostic Settings.
* Automated Web App Deployment from GitHub.
* Configured Alerts and Autoscaling
* Queried Log Analytics

# References
* [az monitor app-insights component | Microsoft Docs](https://docs.microsoft.com/en-us/cli/azure/monitor/log-analytics/workspace?view=azure-cli-latest#az_monitor_log_analytics_workspace_get_shared_keys)
* [az monitor app-insights component create | Microsoft Docs](https://docs.microsoft.com/en-us/cli/azure/monitor/app-insights/component?view=azure-cli-latest#az_monitor_app_insights_component_create)
* [az appservice plan | Microsoft Docs](https://docs.microsoft.com/en-us/cli/azure/appservice/plan?view=azure-cli-latest#az_appservice_plan_create)
* [az webapp | Microsoft Docs](https://docs.microsoft.com/en-us/cli/azure/webapp?view=azure-cli-latest#az_webapp_create)
* [Tutorial: Troubleshoot with Azure Monitor - Azure App Service | Microsoft Docs](https://docs.microsoft.com/en-us/azure/app-service/tutorial-troubleshoot-monitor#create-azure-resources)
* [CLI: Deploy an app from GitHub - Azure App Service | Microsoft Docs](https://docs.microsoft.com/en-us/azure/app-service/scripts/cli-deploy-github?toc=/cli/azure/toc.json)
* [Create a new Azure Monitor Application Insights workspace-based resource - Azure Monitor | Microsoft Docs](https://docs.microsoft.com/en-us/azure/azure-monitor/app/create-workspace-resource)
* [Quickstart: Deploy an ASP.NET web app - Azure App Service | Microsoft Docs](https://docs.microsoft.com/en-us/azure/app-service/quickstart-dotnetcore?tabs=netcore31&pivots=development-environment-cli#publish-your-web-app)
