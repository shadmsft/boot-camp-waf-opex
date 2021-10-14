# CSA Boot Camp WAF - Operational Excellence Hands On Activity

## The goal of this activity to give you some hands on experience with one of the pillars of Operational Excellence. Operational Excellence is a large topic and there is more than we can cover in a 25 minute hands on lab. The focus of this lab is to introduce you to 

## Objectives
* Deploy Azure Monitor Log Analytics Workspace & App Insights
* Deploy Azure App Service & Web App
* Configure Diagnostics
* Configure Azure Alerts
* Configure Autoscaling
* Query Logs

https://portal.azure.com/?feature.customportal=false

## Prerequisites
1. An Azure Subscription.

## Deploy Azure Monitor Log Analytics Workspace & App Insights
1. Navigate to the Azure Portal https://portal.azure.com
1. Click on the Cloud Shell. You may be prompted to create a storage account if this is your first time to use the cloud shell.
   ![image](./media/1.png)
1. Ensure that you use Bash for the Cloud Shell
    ![image](./media/2.png)
1. Set the context to the subscription you want to use.
    ```cli
    az account set --subscription "<your subscription name or Id>"
1. Type the following command in the cloud shell, make sure to use your <resource group name> and <cluster name>

    ```cli
    az group create --name rg-opex --location southcentralus
    ```

    ```cli
    az monitor log-analytics workspace create -g rg-opex -n la-ws-opex
    ```

1. Navigate to the portal to verify the Log Analytics Workspace has been deployed.

    ![image](./media/3.png)
1. Run the following commands to get the WorkspaceId and the Workspace Key, alternatively you can get them from the Portal as well.
    ```cli
    az monitor log-analytics workspace show -g rg-opex --workspace-name la-ws-opex --query customerId
    ```
    ```cli
    az monitor log-analytics workspace get-shared-keys -g rg-opex --workspace-name la-ws-opex
    ```
##  Deploy Azure App Service & Web App
1. Deploy an App Service Plan
    ```cli
    az appservice plan create -g rg-opex -n asp-opex-1 --location southcentralus
    ```
    ```cli
    let randomNum=$RANDOM*$RANDOM
    ```
    ```cli
    webAppName=waopex$randomNum
    ```
    ```cli
    az webapp create -g rg-opex -p asp-opex-1 -n $webAppName
    webAppId=$(az webapp show -g rg-opex -n $webAppName --query id --output tsv)
    ```
1. Create a deployment to the Web App, using a sample application
    ```cli
    gitRepo=https://github.com/Azure-Samples/php-docs-hello-world

    az webapp deployment source config --name $webAppName --resource-group rg-opex --repo-url $gitRepo --branch master --manual-integration

    echo http://$webAppName.azurewebsites.net
    ```

    ```cli
    az extension add -n application-insights

    az monitor app-insights component create --app ai-opex --location southcentralus --kind web -g rg-opex --application-type web --retention-time 120

    az monitor app-insights component connect-webapp -a ai-opex -g rg-opex --app $webAppName

    shad@Azure:~$ az monitor app-insights component connect-webapp -a ai-opex -g rg-opex --app ai-opex --web-app $webappId

    ```

    ```cli
    az monitor app-insights component create --app ai-opex --location southcentralus --kind web -g rg-opex --application-type web --retention-time 120

    ```

## Configure Diagnostics
1. Create Diagnostic Settings for the Web app
    ```cli
     wsID=$(az monitor log-analytics workspace show --workspace-name la-ws-opex -g rg-opex --query id --output tsv)

    ```
    ```cli
    az monitor diagnostic-settings create --resource $webAppId --name diagWebApp --workspace $wsID --logs '[{"category":"AppServiceHTTPLogs","enabled":true,"retentionPolicy":{"enabled":false,"days":0}},{"category":"AppServiceConsoleLogs","enabled": true,"retentionPolicy":{"enabled":false,"days":0}}]' --metrics '[{"category":"AllMetrics","enabled":true,"retentionPolicy":{"enabled":false,"days":0}}]'
    ```
1. Create some load from the Cloud Shell
    ```cli
    while true
    do
        curl http://$webAppName.azurewebsites.net
    done
    ```
    Type Ctrl+C when finished with load test

##  Configure Azure Alerts & Configure Autoscaling

### Autoscaling
1. Navigate to https://portal.azure.com
2. Ensure you are in your subscription
3. Navigate or search for Monitor anc click on it.

    ![image](./media/6.png)

4. In the Settings Section click on Autoscale

    ![image](./media/7.png)

1. Click on the rg-opex App Service Plan deployed previously.

    ![image](./media/8.png)
1. Click on Custom autoscale.

    ![image](./media/9.png)

1. Set the following Values
   1. Scale mode: Scale based on a metric
   2. Rules: + Add Rule

      ![image](./media/9a.png)

      * Metric Source: Current Resource (asp-opex-1)
      * Time aggregation: Average
      * Metric namespace: App Service plans standard metrics
      * Metric name: CPU Percentage
      * Dimension Name: Insance
      * Operator: =
      * Dimension Values: All Values
      * Operator: Greater than
      *  Metric threshold to trigger scale action: 4  (Set this value below the CpuPercentage in the screen, just to trigger an autoscale. This is just for demonstration purposes, you should carefully evaluate what the actual threshold should be)
      * Duration (minutes): 5
      * Time grain (minutes): 1
      * Time grain statistic: Average
      * Operation: Increase count by
      * Instance count: 1
      * Cool down (minutes): 5

            ![image](./media/10.png)
   1. Instance Limits  Minimum: 1
   1. Instance Limits  Maximum: 1
   1. Instance Limits  Default: 1

        ![image](./media/11.png)

    1. Click Save

        ![image](./media/12.png)

## Query Logs
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

8. To Do:

    TODO:
    * Wire up Get GitHub (clone|deployment) - Maybe
    * Add App Insights
    * Add a problem - maybe
    * Add as many diagnostics to each service
    * Gen load with command shell do while(true)
    * Add Alerts
    * Add Queries
    ```

## Reference
https://docs.microsoft.com/en-us/cli/azure/monitor/log-analytics/cluster?view=azure-cli-latest#az_monitor_log_analytics_cluster_create

https://docs.microsoft.com/en-us/azure/virtual-machines/extensions/oms-linux#azure-cli-deployment

https://docs.microsoft.com/en-us/cli/azure/monitor/log-analytics/workspace?view=azure-cli-latest#az_monitor_log_analytics_workspace_get_shared_keys

https://docs.microsoft.com/en-us/azure/azure-monitor/vm/monitor-vm-azure#collect-platform-metrics-and-activity-log

https://docs.microsoft.com/en-us/azure/virtual-machines/extensions/diagnostics-linux?toc=%2Fazure%2Fazure-monitor%2Ftoc.json&tabs=azcli

## Web Apps & App Service Plans
https://docs.microsoft.com/en-us/cli/azure/webapp?view=azure-cli-latest#az_webapp_create

https://docs.microsoft.com/en-us/cli/azure/appservice/plan?view=azure-cli-latest#az_appservice_plan_create

https://docs.microsoft.com/en-us/azure/app-service/quickstart-dotnetcore?tabs=netcore31&pivots=development-environment-cli#publish-your-web-app

https://docs.microsoft.com/en-us/azure/azure-monitor/app/create-workspace-resource

https://docs.microsoft.com/en-us/azure/app-service/scripts/cli-deploy-github?toc=/cli/azure/toc.json

https://docs.microsoft.com/en-us/azure/app-service/tutorial-troubleshoot-monitor#create-azure-resources

https://docs.microsoft.com/en-us/cli/azure/monitor/app-insights/component?view=azure-cli-latest#az_monitor_app_insights_component_connect_webapp

https://docs.microsoft.com/en-us/cli/azure/monitor/app-insights/component?view=azure-cli-latest#az_monitor_app_insights_component_create