<!-- loio55b31ea23c474f6ba2f64ee4848ab1b3 -->

<link rel="stylesheet" type="text/css" href="../../css/sap-icons.css"/>

# Creating Service Bindings in Other Environments

Create a service binding to obtain the access credentials to the service instance of a service you want to consume.



## Procedure

1.  In the SAP BTP cockpit, navigate to the subaccount in which you want to create a service instance.

2.  Choose *Services* \> *Instances and Subscriptions*.

    All existing service instances in your subaccount appear under a single table.

3.  Find the service instance for which you want to create a service binding.

    > ### Recommendation:  
    > To narrow down your search, look for **Other Environments** under the *Runtime Environment* column of the Service Instances table.

4.  In the service instance details section that opens to the right, select the Actions \(<span class="SAP-icons"></span> \) menu, and then *Create Binding*.

5.  In the **New Binding** wizard, choose a name for your binding and provide configuration parameters either by uploading a JSON file or by configuring them in-line.


You have created a new binding for the service instance.

> ### Note:  
> To learn more about service instances and service bindings in other environments, see [Consuming Services in Other Environments Using the SAP Service Manager Instances](../Consuming-SAP-BTP-Services-from-Various-Environments/consuming-services-in-other-environments-0714ac2.md)

