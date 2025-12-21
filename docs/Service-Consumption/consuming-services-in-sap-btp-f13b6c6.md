<!-- loiof13b6c63eef341bc8b7d25b352401c92 -->

# Consuming Services in SAP BTP

SAP BTP provides a wide range of managed services, such as databases, messaging systems, authentication services, and application runtime components, that applications can easily consume as part of their architecture.



## Overview

To consume a service in SAP BTP, you first create a service instance and then obtain credentials that allow your application to access that instance securely. Service instances can be created through the SAP BTP cockpit or using the command-line tools of your chosen environment \(for example, the SAP BTP Command Line Interface\).

Services in SAP BTP are published in the Marketplace, where you can browse available services, compare plans, and provision the one that fits your needs.



## Service Instances and Plans

A service instance is a dedicated, provisioned instance of a service running in your subaccount. Each instance is created using a service plan, which defines a configuration variant of the service, such as storage size for a database, performance tiers, or feature sets. Different plans of the same service may support different cost models, capabilities, or service-level agreements.

> ### Example:  
> A database service may offer *standard*, *high-availability*, and *developer* plans. Each of these is a separate plan, and provisioning an instance using any of them yields a service instance configured according to that plan.



## Obtaining Credentials and Binding Applications

After you create a service instance, your application must receive credentials that allow it to authenticate and communicate with the service. This is typically achieved through service bindings, which generate the required authentication material \(for example, client IDs, secrets, URLs, certificates, or token endpoints\).

How bindings are delivered varies by environment, however, in most environments, the binding establishes the trust relationship between your application and the service instance.



## Consuming the Service at Runtime

Once the application has the credentials, it uses them to:

-   establish secure connections to the service,
-   perform allowed operations based on the service’s API,
-   refresh credentials or tokens when needed, and
-   follow any service-specific security or lifecycle requirements \(for example, rate limits, plans with usage quotas, or rotating credentials\).

For applications managed through the Service Manager API or brokered services, the instance lifecycle \(provision, update, deprovision\) follows the Open Service Broker API semantics.



## Further Learning

In the following chapters, you will learn in detail how to work with service instances, service plans, bindings, and credentials in each SAP BTP environment. You will also see how these concepts integrate with the Service Manager, how lifecycle operations are performed, and how applications consume services at runtime using the credentials delivered through bindings or service keys.

-   **[About SAP Service Manager](SAP-Service-Manager/about-sap-service-manager-3a27b85.md "SAP Service
                                Manager service is the central registry for service brokers and
    environments in SAP BTP.")**  
SAP Service Manager service is the central registry for service brokers and environments in SAP BTP.
-   **[Consuming SAP BTP Services from Various Environments](Consuming-SAP-BTP-Services-from-Various-Environments/consuming-sap-btp-services-from-various-aa2ba14.md "Learn more about how to consume SAP BTP services from various
		runtime environments.")**  
Learn more about how to consume SAP BTP services from various runtime environments.

**Related Information**  


[About Services](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/d1d0fc8e78474494a59caad02259ec7e.html)

[Discovery Center Service Catalog](https://discovery-center.cloud.sap/serviceCatalog)

