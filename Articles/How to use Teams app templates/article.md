# How to use Microsoft Teams app templates

Microsoft Teams can be extended in several different ways using no-code, low-code and custom code solutions. Microsoft Teams app templates are a great way to start discovering ideas, extensibility options and examples of application architectures and coding patters or just start using an app right away in your organization. App templates are community driven, open source and production-ready apps. Installation instructions, detailed prerequisites and source code are available for each app on Github ([Office Developer](https://github.com/OfficeDev/)). You can install each app as it is or clone the repository of an app and start extending it for your own purposes. You can find a detailed list of app templates here [App Templates for Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/platform/samples/app-templates). In time of writing this article there are already 45 templates available. 

There are several different technologies used in apps and an app can be built utilizing one or more of these technologies.
- Microsoft Teams Bots ([What are conversational bots?](https://docs.microsoft.com/en-us/microsoftteams/platform/bots/what-are-bots))
- Tabs ([What are Microsoft Teams custom tabs?](https://docs.microsoft.com/en-us/microsoftteams/platform/tabs/what-are-tabs))
- Personal apps (tabs available on Teams left-rail)
- Message extensions ([What are messaging extensions?](https://docs.microsoft.com/en-us/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions))
- Power Apps and Power Automate workflows
- SharePoint sites, lists, pages and templates

## Prerequisites

- Microsoft 365 tenant is required for installing apps. If you are a developer, you can get a free Microsoft 365 Developer tenant by [joining a Microsoft 365 Developer program](https://developer.microsoft.com/en-us/microsoft-365/dev-program).
- Depending on an app template, you may also require a Microsoft Azure subscription. You can get a free trial subscription with $200 credits for first 30 days and 12 months of popular free services here: [Azure trial subscription](https://azure.microsoft.com/en-us/free/)
- Some templates may require a Power BI license, which is now included in new Microsoft 365 Developer subscription tenants. You can also use Power BI Pro trial license on your tenant.
- Power Apps and Power Automate flows can be tested in default Power Platform enviroment created for Office 365 subscription. For production usage I suggest creating a separate production environment, if your organization doesn't have one already.

## Deploying a template to your environment
Once you have picked a template, first thing is to read the documentation. Documentation contains an overview of the solution, detailed deployment instructions and solution overview, which describes solution architecture data, how data is stored and a cost estimation.

## Deploying an Azure based app to Teams

For Azure based resources you need to have an Azure subscription, permissions to deploy resources to the subscription and have Global Admin role access to Azure Active Directory in your Microsoft 365 tenant.

All Azure related services are created with Azure Resource Manager template (ARM). Each app has a Deploy to Azure button, which opens up the Azure Portal based on your credentials. 

![Deploy to Azure button](https://camo.githubusercontent.com/7b9633223ccfac1fa26b9d503ef7741b3357360f23a10100a39924c9fb64ad87/68747470733a2f2f617a7572656465706c6f792e6e65742f6465706c6f79627574746f6e2e706e67)

Easiest way is to use that browser session, where you have logged in with an account linked to your Azure subscription where you like to deploy the services. Based on required resources for the app, ARM template is providing different configuration options.

![ARM template configuration](https://github.com/mpaukkon/Microsoft365Dev/blob/master/Articles/How%20to%20use%20Teams%20app%20templates/teams-app-azure-deployment.png)


First pick-up a subscription and Resource group to deploy new resources. I suggest creating a new resource group for the app, at least when you are testing, so you can easily manage app's resources and access to them. Choose something unique for Base Resource Name, it's quite commonly used as part of deployed service URL endpoints. Refer the app deployment documentation for configuration options. Once complete click Create and Azure resource deployment begins. Depending on a type and number of services, it can take up to 15 minutes to complete.


## Deploying SharePoint resources

Some app templates require you to create new resources, like sites and lists, to SharePoint Online. SharePoint resources can be created with PowerShell script provided in deployment guide or manually.

## Deploying a Power App to Teams



## Installing an app to Teams
Depending on your Teams configuration, there are two options for installing an app.
- With sideloading, you can upload the app to you or your team. App is not available for anyone else in your tenant.
- Uploading the app to organization app catalog, adds the app available for everyone in your organization by default. App availability for users can be controlled with Teams app setup policies.

### Uploading an app to Teams App Catalog

## Considerations

### Estimating costs on Azure resources

Each app template with Azure resources also contains a documentation about estimated costs. Cost estimation is based on assumption about number of users and usage of the app. Cost estimation is a basis for scaling Azure resources. Actual costs depend on how resources are scaled and how much usage there is. 

You can also do your own estimation with Azure calculator by adding services.

### Scaling Azure services for testing app templates
Most costly Azure service for most of these app templates is Azure App Service. If you want to cut some costs on your try-out subscription or trying these out on your production subscription, you can scale down App Services.


## Further Learning
