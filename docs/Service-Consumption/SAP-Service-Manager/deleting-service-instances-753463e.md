<!-- loio753463e1542f445895b420cd7957811c -->

<link rel="stylesheet" type="text/css" href="../../css/sap-icons.css"/>

# Deleting Service Instances

Delete service instances that you created in your subaccount by using the SAP BTP cockpit.



<a name="loio753463e1542f445895b420cd7957811c__section_vgt_zpz_xmb"/>

## Procedure

> ### Note:  
> You can delete service instances created in Cloud Foundry or Other Environments.
> 
> Service instances created in Kyma or Kubernetes can't be deleted from the SAP BTP cockpit.
> 
> For more details, see [Using Services in the Kyma environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/ea4dd81e49254dd482d32e3c20f4477a.html) and [Kubernetes Consumption](https://help.sap.com/viewer/09cc82baadc542a688176dce601398de/Cloud/en-US/20195bf3b6e64189966e08f669c275e1.html).

1.  In the navigation area, choose *Services* \> *Instances and Subscriptions*

    All existing service instances in your subaccount appear under a single table.

2.  You delete an instance by selecting the Actions \(<span class="SAP-icons"></span> \) menu, and then *Delete Instance*.

    You can find the Actions menu either at the end of each instance's row, or in the top-right section of the service instance details area that opens to the right if you click on an instance row.


> ### Note:  
> You can only delete instances that are not bound to applications.
> 
> If your instance has service bindings or service keys, you are prompted to delete those first.

