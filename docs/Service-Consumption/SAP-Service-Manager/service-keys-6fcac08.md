<!-- loio6fcac08409db4b0f9ad55a6acd4d31c5 -->

<link rel="stylesheet" type="text/css" href="../../css/sap-icons.css"/>

# Service Keys

Unlike service bindings that are used to automatically generate credentials, service keys are used to manually configure credentials for users to consume marketplace services. Once you configure them for your service, local clients, apps in other spaces, or entities outside your deployment can access your service with these keys. We discuss service keys in the context of a Cloud Foundry environment.





### Prerequisites

-   You have an assigned *space developer* role. For more information, see [About Roles in the Cloud Foundry Environment](https://help.sap.com/docs/btp/sap-business-technology-platform/about-roles-in-cloud-foundry-environment?version=Cloud).

-   You've created a service instance. For more information, see [Creating Service Instances in Cloud Foundry](creating-service-instances-in-cloud-foundry-6d6846d.md).




### Procedure

> ### Note:  
> You can create a service key for a Cloud Foundry instance either directly from your subaccount or from your Cloud Foundry org in your subaccount.
> 
> -   In the first case, in navigation area, select *Services* \> *Instances and Subscriptions* after you've chosen your subaccount.
> 
> -   In the second case, navigate first to *Cloud Foundry* \> *Spaces*, and then to *Services* \> *Instances and Subscriptions*.

1.  Select a Cloud Foundry instance for which you want to create a service key.

2.  In the service instance details area that opens to the right, select the Actions menu \(<span class="SAP-icons"></span>\).

3.  Choose *Create Service Key*.

4.  In the **New Service Key** wizard, choose a name for your service key and provide configuration parameters either by uploading a JSON file or by configuring them in-line.

    For the full list of the available configuration parameters, see the documentation of the particular service offering.


