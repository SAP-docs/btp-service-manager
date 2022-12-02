<!-- loio0e6850de6e7146c3a17b86736e80ee2e -->

# Binding Service Instances to Cloud Foundry Applications

Bind a service instance to your Cloud Foundry app to enable the automatic delivering of credentials needed to access the service instance to the application.





### Prerequisites

-   Deploy an application in the same space in which you plan to create the service instance. For more information, see [Deploy Business Applications in the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/4946ea5421374924963ce8575a5f3d05.html).

-   Create a service instance. For more information, see [Creating Service Instances in Cloud Foundry](creating-service-instances-in-cloud-foundry-6d6846d.md).




### Procedure

1.  In the navigation area, choose *Services* \> *Service Instances*.

    All existing service instances grouped by environments appear.

2.  In the Cloud Foundry instances section, select the instance to which you wish to bind the application.

3.  In the service instance details section that opens to the right, select the Actions menu \(![](images/Actions_icon_e7540c0.png)\) and then select *Bind Application*.

    > ### Note:  
    > If all the applications in your Cloud Foundry space have already been bound, or there are no applications, an error is returned.

4.  In the **New Binding** wizard, choose the application to bind.

5.  Provide the parameters for your binding by choosing one of the following options:

    -   Upload a JSON file.

    -   Configure in-line in a JSON format.



