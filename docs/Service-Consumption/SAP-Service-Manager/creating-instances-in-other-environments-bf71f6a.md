<!-- loiobf71f6a7b7754dbd9dfc2569791ccc96 -->

<link rel="stylesheet" type="text/css" href="../../css/sap-icons.css"/>

# Creating Instances in Other Environments

Use the SAP BTP cockpit to create instances for environments in which the deployed applications don’t bind natively to instances.



> ### Note:  
> Service instances created for environments other than Cloud Foundry, Kyma, or Kubernetes environments have different ways of connecting to applications. For more information, see [Consuming Services in Other Environments Using the SAP Service Manager Instances](../Consuming-SAP-BTP-Services-from-Various-Environments/consuming-services-in-other-environments-0714ac2.md).



### Procedure

1.  Navigate to the subaccount in which you want to create a service instance.

2.  In the navigation area, choose *Services* \> *Instances and Subscriptions*.

    All existing service instances grouped by the environments appear.

3.  Select *Create* in the top-right corner.

    A **New Instance** wizard opens, offering you to configure your new instance:

    1.  **Enter basic info for your instance**

        Choose a service for which you wish to create an instance from the dropdown list.

    2.  Select one of the available service plans.

    3.  Choose *Other* as a runtime environment.

    4.  Choose a name for your service instance, then choose *Next*.

        > ### Recommendation:  
        > Use a CLI-friendly name to enable the managing of your instances also with the CLI for SAP Business Technology Platform.
        > 
        > CLI-friendly name is a short string \(up to 32 characters\) that only contains alphanumeric characters \(A-Z, a-z\), numbers from 0 to 9, periods, underscores, and hyphens.
        > 
        > It can’t contain white spaces.

    5.  **\(Optional\) Configure instance parameters**

        Specify a JSON file to upload or configure parameters manually in the JSON format, then choose *Next*.

        > ### Note:  
        > Some services support providing of additional configuration parameters during instance creation.
        > 
        > Pass these parameters in a valid JSON object that contains service-specific configuration parameters, provided either in-line or in a file.
        > 
        > For a list of supported configuration parameters, see the documentation of a particular service offering.

    6.  **Review and verify the instance details**

        Use the preview to verify the instance details, then choose *Create*.

        The new instance is created.

        > ### Note:  
        > Creation of the instance can take a while.
        > 
        > To check the current creation status, see the **Status** column of the new instance under the *Service Instance* table





<a name="loiobf71f6a7b7754dbd9dfc2569791ccc96__section_usz_bfz_qrb"/>

## Labels

You can assign labels to service instances to make them searchable and organized within the subaccount according to various criteria.



### Procedure

1.  In the navigation area, choose *Services* \> *Instances and Subscriptions*.

2.  Find the instance to which you want to assign labels under the *Instances* section of the page.

3.  Select the actions \(<span class="SAP-icons"></span>\) menu and from the dropdown list, choose *Add Labels*.

    > ### Note:  
    > If there are already labels assigned to the service instance, the action becomes *Change Labels*.
    > 
    > You can see the existing labels under the *Labels* column.
    > 
    > If you do not see the column, unhide it by clicking on :gear:.


For more information, see [Labels](https://help.sap.com/products/BTP/65de2977205c403bbc107264b8eccf4b/8ed4a705efa0431b910056c0acdbf377.html#loioe8663c08ead648faa673b0d63c5b478e).

