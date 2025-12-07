<!-- loio3a27b85a47fc4dff99184dd5bf181e14 -->

# About SAP Service Manager

SAP Service Manager service is the central registry for service brokers and environments in SAP BTP.

Use it to consume services across multiple connected runtime environments, track the creation and management of service instances, and share service instances across environments when appropriate.

SAP Service Manager can be accessed using the following tools:

-   SAP BTP cockpit
-   SAP BTP command-line interface \(btp CLI\)

-   API

-   SAP BTP service operator


SAP Service Manager works with the following resources:

-   Environments \(Platforms\)

    Open Service Broker API–enabled software systems on which applications and services are hosted. With SAP Service Manager, you can register your environment and enable it to consume SAP Business Technology Platform services. This registration returns a set of credentials needed to deploy the SAP Service Manager agent.

-   Service Brokers

    Mediators between SAP Service Manager and the SAP BTP marketplace that advertise catalogs of service offerings and service plans. They also receive and process requests to provision, bind, unbind, and deprovision these offerings and plans.

-   Service Instances

    Independent, running copies of a service. Think of a service as a blueprint and a service instance as the working realization of that blueprint, with its own resources and configuration. Each instance lets users or applications access the service in a dedicated environment.

-   Service Bindings

    Provide access details for an existing service instance. The access details are in the service binding `credentials` property and typically include access URLs and credentials.

    These access details enable consumption of a service.

-   Service Plans

    Sets of capabilities provided by a service offering. For example, database offerings provide different plans for various versions or sizes, while SAP Service Manager plans offer different data-access levels.

-   Service Offerings

    Advertisements of services supported by a service broker. Service offerings are related to one or more service plans.


You can use SAP BTP tools to perform operations on Service Manager resources.

> ### Note:  
> Service Manager provides full CRUD functionality for service instances that are environment-agnostic. These instances are created at the subaccount level and, by default, are not tied to any specific environment. They are referred to as **Other Environment** instances.
> 
> Although instances from environments like Cloud Foundry, Kubernetes, or Kyma can be viewed in Service Manager, their creation, modification, and deletion must be performed using each environment’s native tools \(for example, `cf` for Cloud Foundry or `kubectl` for Kubernetes\).

In the next chapters, you'll learn how to work with each of these tools.

-   **[What's New for SAP Service Manager](what-s-new-for-sap-service-manager-c9d5c05.md)**  

-   **[Working with SAP Service Manager](working-with-sap-service-manager-c459d61.md "You can use the SAP Service
                                Manager service
		capabilities from the SAP BTP cockpit to manage
		service instances and service bindings. Also, technical access is available via a
		command-line interface and REST APIs.")**  
You can use the SAP Service Manager service capabilities from the SAP BTP cockpit to manage service instances and service bindings. Also, technical access is available via a command-line interface and REST APIs.

**Parent topic:**[Consuming Services in SAP BTP](../consuming-services-in-sap-btp-f13b6c6.md "SAP BTP provides a wide range of managed services, such as databases, messaging systems, authentication services, and application runtime components, that applications can easily consume as part of their architecture.")

**Related Information**  


[Consuming SAP BTP Services from Various Environments](../Consuming-SAP-BTP-Services-from-Various-Environments/consuming-sap-btp-services-from-various-aa2ba14.md "Learn more about how to consume SAP BTP services from various runtime environments.")

