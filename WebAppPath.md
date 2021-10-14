# CSA Boot Camp WAF - Operational Excellence Hands On Activity

## The goal of this activity to give you some hands on experience with one of the pillars of Operational Excellence. Operational Excellence is a large topic and there is more than we can cover in a 25 minute hands on lab. So, we'll setup this lab with progressive objectives that can be completed at a later time.

## Objectives
* Deploy Azure Monitor Log Analytics Workspace
* Deploy Azure App Service & Web App
* Configure Diagnostics
* Configure Azure Alert based on VM Metric
* Configure Autoscaling

https://portal.azure.com/?feature.customportal=false

## Prerequisites
1. .NET Core SDK - https://dotnet.microsoft.com/download/dotnet-core/3.1
2. 

## Deploy Azure Monitor Log Analytics Workspace
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

    ```cli
az extension add -n application-insights
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
    az appservice plan create -g rg-opex -n asp-opex-1 --location southcentralus --sku FREE
    ```
    ```cli
    let randomNum=$RANDOM*$RANDOM
    ```
    ```cli
    webAppName=waopex$randomNum
    ```
    ```cli
    az webapp create -g rg-opex -p asp-opex-1 -n $webAppName
    ```
1. Create deployment to the Web App, using a sample application
    ```cli
    gitRepo=https://github.com/Azure-Samples/php-docs-hello-world

    az webapp deployment source config --name $webAppName --resource-group rg-opex --repo-url $gitRepo --branch master --manual-integration

    echo http://$webAppName.azurewebsites.net
    ```
1. Create Diagnostic Settings for the Web app
    ```cli
     wsID=$(az monitor log-analytics workspace show --workspace-name la-ws-opex -g rg-opex --query id --output tsv)
     webAppId=$(az webapp show -g rg-opex -n $webAppName --query id --output tsv)
    ```
    ```cli
    az monitor diagnostic-settings create --resource $webAppId --name diagWebApp --workspace $wsID --logs '[{"category":"AppServiceHTTPLogs","enabled":true,"retentionPolicy":{"enabled":false,"days":0}},{"category":"AppServiceConsoleLogs","enabled": true,"retentionPolicy":{"enabled":false,"days":0}}]' --metrics '[{"category":"AllMetrics","enabled":true,"retentionPolicy":{"enabled":false,"days":0}}]'
    ```
2. Create some load from the Cloud Shell
    ```cli
    while true
    do
        curl http://$webAppName.azurewebsites.net
        sleep 3
    done
    ```
    Type Ctrl+C when finished with load test
3. To Do:

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