<!-- loio3a27b85a47fc4dff99184dd5bf181e14 -->

# SAP Service Manager

SAP Service Manager service is the central registry for service brokers and platforms in SAP BTP.

It allows you to consume platform services in any connected runtime environment, track the creation and management of service instances, and share services and service instances between different environments.

SAP Service Manager supports services that implement the [Open Service Broker API](https://www.openservicebrokerapi.org/) \(OSBAPI\), and can be consumed natively in OSBAPI-enabled environments such as Cloud Foundry and Kubernetes.

SAP Service Manager can be accessed via the SAP BTP cockpit, command line tool or API, and allows management of platforms, service brokers, service instances, and service bindings. It's tightly integrated with SAP BTP services, and enforces service access rules and quotas.

SAP Service Manager works with the following resources:

-   Platforms

    Platforms are Open Service Broker API-enabled software systems on which applications and services are hosted. With SAP Service Manager, you can register your platform and enable it to consume the SAP Business Technology Platform services from your native environment. This registration results in a returned set of credentials that are needed to deploy the SAP Service Manager agent.

-   Service Brokers

    A service broker acts as a broker between the SAP Service Manager and a platform’s marketplace to advertise catalogs of service offerings and service plans. It also receives and processes the requests from the marketplace to provision, bind, unbind, and deprovision these offerings and plans.

-   Service Instances

    Service Instance is an instantiation of a service that makes the functionality of that service available for consumption.

-   Service Bindings

    Service bindings provide access details for an existing service instance. The access details can be found in the service binding credentials property, and typically include access URLs and credentials.

-   Service Plans

    Service plans represent sets of capabilities provided by a service offering. For example, database service offerings provide different plans for different database versions or sizes, while the SAP Service Manager plans offer different data access levels.

-   Service Offerings

    Service offerings represent an advertisement of the service that is supported by a service broker. Service offerings are related to one or more service plans.


-   **[What's New for SAP Service Manager](what-s-new-for-sap-service-manager-c9d5c05.md)**  

-   **[Working with SAP Service Manager](working-with-sap-service-manager-c459d61.md "You can use the SAP Service
                                Manager service
		capabilities from the SAP BTP cockpit to manage
		service instances and service bindings. Also, technical access is available via a
		command-line interface and REST APIs.")**  
You can use the SAP Service Manager service capabilities from the SAP BTP cockpit to manage service instances and service bindings. Also, technical access is available via a command-line interface and REST APIs.

**Parent topic:** [Consuming Services in SAP BTP](../consuming-services-in-sap-btp-f13b6c6.md "To use services in SAP BTP, you creatе a service instance, using either the SAP BTP cockpit, or the command-line tools of your runtime platform, for example, the Cloud Foundry environment Command Line Interface (cf CLI), and create bindings to retrieve access credentials.")

**Related Information**  


[Consuming SAP BTP Services from Various Environments](../Consuming-SAP-BTP-Services-from-Various-Environments/consuming-sap-btp-services-from-various-aa2ba14.md "Learn more about how to consume SAP BTP services from various runtime environments.")

