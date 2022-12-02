<!-- loio002ae850a32244af85c8405fbcd7d9ab -->

<link rel="stylesheet" type="text/css" href="../../css/sap-icons.css"/>

# Updating Service Instances

Update the name, plan, and configuration parameters of your service instance directly from your subaccount by using the SAP BTP cockpit.



## Procedure

> ### Note:  
> The procedure applies to service instances created in Cloud Foundry or Other Environments.
> 
> Service instances created in Kyma or Kubernetes can't be updated in the SAP BTP.
> 
> For more details, see [Using Services in the Kyma environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/ea4dd81e49254dd482d32e3c20f4477a.html) and [Kubernetes Consumption](https://help.sap.com/viewer/09cc82baadc542a688176dce601398de/Cloud/en-US/20195bf3b6e64189966e08f669c275e1.html).

1.  In the navigation area of the SAP BTP cockpit, choose *Services* \> *Instances and Subscriptions*.

    All existing service instances in your subaccount appear under a single table.

2.  In the *Runtime Environments* column of the *Service Instances* table, find Cloud Foundry or Other Environments, and select the instance you want to update.

    > ### Note:  
    > You update an instance by selecting the Actions \(<span class="SAP-icons"></span> \) menu, and then *Update Instance*.
    > 
    > You can find the Actions menu either at the end of each instance row of the *Service Instances* tables, or in the top-right section of the service instance details area that opens to the right if you click on an instance row.

3.  In the **Update Instance** wizard that opens, follow the steps to update your instance.

    You can update the name of the instance and a plan.

    > ### Note:  
    > You can update a subscription plan only if additional plans for the service whose instance you are creating are entitled to the subaccount in which you're updating the instance and if your service is eligible for plan updates.


