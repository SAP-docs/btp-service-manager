<!-- loio6d6846def3c443aa9f83d127353147ce -->

<link rel="stylesheet" type="text/css" href="../../css/sap-icons.css"/>

# Creating Service Instances in Cloud Foundry

The service instances that you create in your Cloud Foundry org enable your Cloud Foundry apps to consume services natively from Cloud Foundry.



<a name="loio6d6846def3c443aa9f83d127353147ce__section_ajy_bdz_qrb"/>

## Prerequisites

If you’re working in an enterprise account, you need to add quotas to the services you purchased in your subaccount before they appear in the service marketplace. Otherwise, only default free-of-charge services are listed. Quotas are automatically assigned to the resources available in trial accounts.

For more information, see [Configure Entitlements and Quotas for Subaccounts](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/5ba357b4fa1e4de4b9fcc4ae771609da.html?q=Configure%20entitlements%20and%20quotas%20for%20subaccounts).



<a name="loio6d6846def3c443aa9f83d127353147ce__section_bjy_bdz_qrb"/>

## Procedure

You can create instances from your subaccount or from a Cloud Foundry space.



### Creating Service Instances from your Subaccount

1.  In the SAP BTP cockpit, navigate to the subaccount in which you want to create a service instance.

    For more information, see [Navigate to Orgs and Spaces](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/5bf87353bf994819b8803e5910d8450f.html?q=Navigate%20to%20orgs%20and%20spaces).

2.  In the navigation area, choose *Services* \> *Instances and Subscriptions*.

    All existing service instances in your subaccount appear under a single table.

3.  Select *Create* in the top-right corner.

    A wizard opens, offering you to configure your new instance:

    1.  **Enter basic info for your instance**

        Choose a service for which you wish to create an instance from the dropdown list.

    2.  Select one of the available service plans.

    3.  Choose *Cloud Foundry* as a runtime environment.

    4.  Select a space in your Cloud Foundry org to create the instance.

    5.  Choose a name for your service instance, then choose *Next*.

        > ### Recommendation:  
        > Use a CLI-friendly name to enable the managing of your instances also with the CLI for SAP BTP.
        > 
        > CLI-friendly name is a short string \(up to 32 characters\) that only contains alphanumeric characters \(A-Z, a-z\), numbers from 0 to 9, periods, underscores, and hyphens.
        > 
        > It can’t contain white spaces.

    6.  **\(Optional\) Configure instance parameters**

        Specify a JSON file to upload or configure parameters manually in the JSON format, then choose *Next*.

        > ### Note:  
        > Some services support providing of additional configuration parameters during instance creation.
        > 
        > These parameters are provided in a JSON object with a schema that defines the properties for which to provide values, either in-line or as a file to upload.
        > 
        > For your convenience, we have prepopulated JSON schema with properties for those services that support this feature, so you only need to provide values.
        > 
        > For additional information about the supported configuration parameters, see the documentation of a particular service offering.

    7.  **Review and verify the instance details**

        Use the preview to verify the instance details, then choose *Create*.

        The new instance of the selected service is created in your Cloud Foundry space.

        > ### Note:  
        > Creation of the instance can take a while.
        > 
        > To check the current creation status, see the **Status** column for the new instance in the *Service Instances* table.





### Creating Service Instances from your Cloud Foundry Space

1.  In SAP BTP cockpit, navigate to the subaccount in which you want to create a service instance.

2.  In the navigation area, choose *Cloud Foundry* \> *Spaces*.

    All spaces in your subaccount appear.

3.  Select the space in which you want to create a service instance.

4.  In the navigation area, choose *Services* \> *Service Instances*.

5.  Select *Create* in the top-right corner and follow the instructions in the **New Instance or Subscription** wizard.

    The new instance of the selected service is created in your Cloud Foundry space.




<a name="loio6d6846def3c443aa9f83d127353147ce__section_usz_bfz_qrb"/>

## Labels

You can assign labels to service instances to make them searchable and organized within the subaccount according to various criteria.

For more information, see [Labels](https://help.sap.com/products/BTP/65de2977205c403bbc107264b8eccf4b/8ed4a705efa0431b910056c0acdbf377.html#loioe8663c08ead648faa673b0d63c5b478e).



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


