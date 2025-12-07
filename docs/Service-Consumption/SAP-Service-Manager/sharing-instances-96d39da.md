<!-- loio96d39daca76540e194688fd0b3f11396 -->

# Sharing Instances

Share service instances across applications within the same subaccount using SAP Service Manager to streamline data exchange, reduce costs, and simplify resource management.



<a name="loio96d39daca76540e194688fd0b3f11396__section_nfn_31n_qxb"/>

## About

Sharing instances is a concept that allows multiple applications within different scopes of a subaccount to utilize a single service instance. This optimizes resource allocation, reduces the costs associated with creating and managing multiple instances, and simplifies communication between subaccount entities. By sharing instances, the need for complex authorization methods \(such as service keys, bindings, or user-provided instances\) is eliminated, improving cross-scope interaction.

SAP Service Manager enables this concept in SAP BTP between different Cloud Foundry spaces or between different environments \(such as Cloud Foundry and Kubernetes\).

> ### Note:  
> You can only share instances that are in the same subaccount.



<a name="loio96d39daca76540e194688fd0b3f11396__section_qjm_rrq_dyb"/>

## How It Works

This section provides a general overview of how instance sharing works. You can share service instances using various SAP BTP tools, and the exact procedure varies depending on the tool you're using. For detailed instructions on specific tools, see the Related Information section below.



### Prerequisites

Ensure the plan of the instance you intend to share supports the sharing feature. Note that not all service plans offer this capability.



### Procedure

1.  Create a new instance to share, or choose an existing instance if its associated plan supports sharing.

2.  Initiate the sharing process. This adds a new reference-instance plan to the service whose instance you created and shared.

3.  Utilize the newly-added reference-instance plan to create another service instance. This reference instance acts as a reference \(or a pointer\) to the shared instance, enabling you to access the service from a different subaccount scope.

4.  Establish a binding for the reference instance. This binding will contain the credentials required to access the shared instance.

    For detailed information about creating a service binding, see [Service Bindings](service-bindings-bb8009d.md).




<a name="loio96d39daca76540e194688fd0b3f11396__section_wrz_hkc_ccc"/>

## Related Information

-   [SAP BTP Command Line Interface \(btp CLI\)](https://help.sap.com/docs/service-manager/sap-service-manager/instance-sharing-by-service-manager-clients?locale=en-US&state=DRAFT#sap-btp-command-line-interface-(btp-cli))

-   [SAP BTP Cockpit](https://help.sap.com/docs/service-manager/sap-service-manager/instance-sharing-by-service-manager-clients?locale=en-US&state=DRAFT#sap-btp-cockpit)

-   [Service Manager API](https://help.sap.com/docs/service-manager/sap-service-manager/instance-sharing-by-service-manager-clients?locale=en-US&state=DRAFT#service-manager-api)

-   [SAP BTP Service Operator](https://help.sap.com/docs/service-manager/sap-service-manager/instance-sharing-by-service-manager-clients?locale=en-US&state=DRAFT#sap-btp-service-operator)


-   **[Sharing Instances Using Various SAP BTP Tools](sharing-instances-using-various-sap-btp-tools-e3403a4.md "Learn how to share service instances with different SAP BTP tools.")**  
Learn how to share service instances with different SAP BTP tools.

