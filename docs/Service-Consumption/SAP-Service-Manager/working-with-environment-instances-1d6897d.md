<!-- loio1d6897d22f90443c8a3f9f6c8bb41bb8 -->

<link rel="stylesheet" type="text/css" href="../../css/sap-icons.css"/>

# Working with Environment Instances

Create an instance of an environment to consume in your subaccount.



On a subaccount level, environments constitute the actual platform-as-a-service \(PaaS\) offering of SAP BTP that allows for the development and administration of business applications.

Each environment comes equipped with specific tools, technologies, and runtimes that you need to build applications. The availability of different environments allows for greater flexibility in your development process. For more information, see [Environments](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/15547f7e7ecd47ee9fa052b0e18c7b0a.html).

If you've created a multi-environment subaccount, you can use it as a single address to host various applications and offer diverse development options. For more information about creating multi-environment subaccounts, see [Create a Subaccount](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/05280a123d3044ae97457a25b3013918.html).

There are two ways to enable an environment for consumption in a subaccount, from the *Service Marketplace*and from the *Overview* pages of the SAP BTP cockpit. If you need more information about an environment and its available plans, we recommend that you use the *Service Marketplace*. But if you are already familiar with the environment, use the *Overview* page.



<a name="loio1d6897d22f90443c8a3f9f6c8bb41bb8__section_tpl_zk4_bpb"/>

## Enabling Environments from the *Service Marketplace* Page

Environments are offered in the *Service Marketplace* of the SAP BTP cockpit together with other services.

To find them in your subaccount, from the navigation bar select *Services* \> *Service Marketplace*, and then from the dropdown menu of the *All Types* filter, select *Environments*.

Choose the tile of the environment that you want to enable for consumption in your subaccount, and then in the top-right corner of the tile, select <span class="SAP-icons"></span> \(Create\) to open the wizard to manually configure your environment instance.

Currently, you can enable the Cloud Foundry or Kyma environment.



<a name="loio1d6897d22f90443c8a3f9f6c8bb41bb8__section_tbc_vzv_mpb"/>

## Enabling Environments from the *Subaccount Overview* Page

From the navigation bar, select *Overview*.

Choose an environment you want to enable for consumption by selecting either *Enable Cloud Foundry* or *Enable Kyma*.

This action opens a wizard to configure an environment instance.

> ### Note:  
> Wizard that opens on this page is environment-specific, therefore its layout is slightly different from the wizard that opens when creating an environment instance on the *Service Marketplace* page.



For more information, see [Create a Kyma Environment instance from Service Marketplace](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/284ac5e55b2243d7b9f33c1c1325c58e.html).



<a name="loio1d6897d22f90443c8a3f9f6c8bb41bb8__section_usz_bfz_qrb"/>

## Assigning Labels to Environment Instances

You can assign labels to environment instances to make them searchable and organized according to various criteria.

For more information, see [Labels](https://help.sap.com/products/BTP/65de2977205c403bbc107264b8eccf4b/8ed4a705efa0431b910056c0acdbf377.html#loioe8663c08ead648faa673b0d63c5b478e).

> ### Note:  
> For environment instances, these custom labels are user-defined and apply only to SAP BTP. They are not the same labels that might be defined by your environment broker.



### Procedure

1.  In the navigation area, choose *Services* \> *Instances and Subscriptions*.

2.  Find the instance to which you want to assign labels under the *Environment* section of the page.

3.  Select the actions \(<span class="SAP-icons"></span>\) menu and from the dropdown list, choose *Add Labels*.

    > ### Note:  
    > If there are already labels assigned to the service instance, the action becomes *Change Labels*.
    > 
    > You can see the existing labels under the *Labels* column.
    > 
    > If you do not see the column, unhide it by clicking on :gear:.


