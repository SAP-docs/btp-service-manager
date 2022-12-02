<!-- loio6fcac08409db4b0f9ad55a6acd4d31c5 -->

<link rel="stylesheet" type="text/css" href="../../css/sap-icons.css"/>

# Creating Service Keys in Cloud Foundry

Create service keys so that local or external clients can manually access your service instances.





### Prerequisites

Create a service instance. For more information, see [Creating Service Instances in Cloud Foundry](creating-service-instances-in-cloud-foundry-6d6846d.md).



### Procedure

> ### Note:  
> You can create a service key for a Cloud Foundry instance either directly from your subaccount or from your Cloud Foundry space in your subaccount.
> 
> -   In the first case, in navigation area, select *Services* \> *Instances and Subscriptions* after you have chosen your subaccount.
> 
> -   In the second case, navigate first to *Cloud Foundry* \> *Spaces*, and then to *Services* \> *Instances and Subscriptions*
> 
>     .

1.  Select a Cloud Foundry instance for which you want to create a service key.

2.  In the service instance details area that opens to the right, select the Actions menu \(<span class="SAP-icons"></span>\).

3.  Choose *Create Service Key*.

4.  In the **New Service Key** wizard, choose a name for your service key and provide configuration parameters either by uploading a JSON file or by configuring them in-line.

    For the full list of the available configuration parameters, see the documentation of the particular service offering.


