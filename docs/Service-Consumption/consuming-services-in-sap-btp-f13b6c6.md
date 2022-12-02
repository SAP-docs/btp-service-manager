<!-- loiof13b6c63eef341bc8b7d25b352401c92 -->

# Consuming Services in SAP BTP

To use services in SAP BTP, you creatе a service instance, using either the SAP BTP cockpit, or the command-line tools of your runtime platform, for example, the Cloud Foundry environment Command Line Interface \(cf CLI\), and create bindings to retrieve access credentials.

In a Platform-as-a-Service \(PaaS\) environment, all external dependencies, such as databases, messaging and filing systems, are services.

PaaS environments are also services.

In SAP BTP, services are offered in a marketplace, from which users can create service instances on-demand. A service instance is a single instantiation of a service running on SAP BTP.

Service instances are created using a specific service plan. A service plan is a configuration variant of a service. For example, a database can be configured with various plan sizes; each is a different service plan.

To achieve the integration between a service and an application, you must deliver credentials to application. You can use bindings to generate credentials to communicate directly with a service instance.

Some runtime platforms, such as Cloud Foundry, allow binding service instances to your application to automatically deliver the credentials to the application.

-   **[SAP Service Manager](SAP-Service-Manager/sap-service-manager-3a27b85.md "SAP Service
                                Manager
		service is the central registry for service brokers and platforms in SAP BTP.")**  
SAP Service Manager service is the central registry for service brokers and platforms in SAP BTP.
-   **[Consuming SAP BTP Services from Various Environments](Consuming-SAP-BTP-Services-from-Various-Environments/consuming-sap-btp-services-from-various-aa2ba14.md "Learn more about how to consume SAP BTP services from various
		runtime environments.")**  
Learn more about how to consume SAP BTP services from various runtime environments.

**Related Information**  


[About Services](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/d1d0fc8e78474494a59caad02259ec7e.html)

[Discovery Center Service Catalog](https://discovery-center.cloud.sap/serviceCatalog)

