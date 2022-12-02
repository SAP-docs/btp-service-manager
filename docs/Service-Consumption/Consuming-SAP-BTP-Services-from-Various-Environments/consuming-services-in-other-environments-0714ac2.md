<!-- loio0714ac254e83492281d95e25548b388c -->

# Consuming Services in Other Environments Using the SAP Service Manager Instances

Consume SAP BTP services from any runtime environment by creating service instances and service bindings directly in your subaccount with the Service Manager Control \(SMCTL\) CLI or APIs.



<a name="loio0714ac254e83492281d95e25548b388c__section_i3l_zmj_gmb"/>

## Context

The services are consumed in the context of your SAP BTP subaccount, which is necessary for verifying the required entitlements to commercial services and all the related administrative operations such as billing of the services that incur costs.



<a name="loio0714ac254e83492281d95e25548b388c__section_uhd_qnj_gmb"/>

## Consumption Flow

> ### Note:  
> The following example demonstrates how to consume an SAP BTP service by using either the Service Manager Control \(SMCTL\) CLI or APIs via curl.
> 
> To learn how to consume services from other environments by using the SAP BTP cockpit, see the following topics:
> 
> -   [Creating Instances in Other Environments](../SAP-Service-Manager/creating-instances-in-other-environments-bf71f6a.md)
> 
> -   [Creating Service Bindings in Other Environments](../SAP-Service-Manager/creating-service-bindings-in-other-environments-55b31ea.md)

By using CLI or API, you achieve the integration with any deployment script that supports the execution of shell scripts or commands.

For more information about how to use the SAP Service Manager service CLI and API, see the following links: [Using the Service Manager Control \(SMCTL\) Command-Line Tool](../SAP-Service-Manager/using-the-service-manager-control-smctl-command-line-tool-0107f3f.md) and [Working with SAP Service Manager APIs](../SAP-Service-Manager/working-with-sap-service-manager-apis-4e19b11.md).



### Example

In the example, you use the `application` plan of the `xsuaa` service. The specific plan and service are convenient for demonstration since they don’t require any entitlements and don’t incur costs.

> ### Note:  
> You can apply the same steps to any other service that supports cross consumption and that your subaccount is entitled to use.



### General Prerequisites

You have an SAP Business Technology Platform subaccount.



### Consuming Services with the Service Manager Control \(SMCTL\) CLI

 **Prerequisites** 

-   You’re logged on to your subaccount.

    For more information, see [Using the Service Manager Control \(SMCTL\) Command-Line Tool](../SAP-Service-Manager/using-the-service-manager-control-smctl-command-line-tool-0107f3f.md).

-   You have a command-line JSON processor at your disposal, for example jq.


1.  Locate the plan for the service you want to use by running the following command that lists all the available services in your subaccount:

    ```
    smctl marketplace
    ```

    The output includes the name of the service, the plan used for the service, the description of the service, and the ID of the service broker associated with it.

    In the example, we choose the `xsuaa` service with the `application` plan.

2.  Create a service instance of the selected `xsuaa` service by running the following command:

    ```
    smctl provision example-xsuaa-instance xsuaa application --param async=false
    ```

    Where the name of the new instance is `example-xsuaa-instance`, and the `--param async=false` setting indicates that the command output becomes available only once the instance is ready to be used.

3.  Create a binding to access the service instance you created in the previous step by running the following command:

    ```
    smctl bind example-xsuaa-instance example-xsuaa-binding --param async=false
    ```

    The name of the new binding is `example-xsuaa-binding`. and the output includes the `credentials` section that contains the access URLs and authorization details required to use the `xsuaa` service.

4.  Inject service access details to your application.

    > ### Note:  
    > While the method to extract the relevant access and authorization details from the binding credentials is universal for all environments, the way to inject those details to an application is specific to the environment in which the application is deployed.

    For example, if you're deploying a Spring Boot Java application, you can use the `application.properties` file or the Java environment to inject the required values.

    In this example, we extract the `clientid` field from the binding credentials, and store it in the `client_id` variable using jq:

    ```
    binding_json=$(smctl get-binding example-xsuaa-binding -o json)              
    binding_credentials=$(echo $binding_json | jq ".items[0].credentials")
    client_id=$(echo $binding_credentials | jq -r ".clientid")
    ```




### Consuming Services with the SAP Service Manager APIs

 **Prerequisites** 

-   You have obtained an API access token. For more information, see [Accessing the APIs](../SAP-Service-Manager/accessing-the-apis-93711c1.md).

-   You have downloaded the command-line tool and library for transferring data with URLs \(curl\).

-   You have a command-line JSON processor at your disposal, for example jq.


1.  Use the `Get All Service Offerings` API to get the list of all service offerings and retrieve the ID of the `xsuaa` service:

    ```
    xsuaa_service_id=$(curl "https://service-manager.cfapps.<region domain>/v1/service_offerings" \
                            -H "Authorization: Bearer <access token>" \
                            -G --data-urlencode "fieldQuery=name eq 'xsuaa'" \
                            | jq -r ".items[0].id")
    ```

    For more information about the API, see [Service Offerings](../SAP-Service-Manager/service-offerings-e43b399.md)

2.  Use the `Get All Service Plans` API to retrieve the ID of the `application` service plan:

    ```
    application_plan_id=$(curl "https://service-manager.cfapps.<region domain>/v1/service_plans" \
                            -H "Authorization: Bearer <access token>" \
                            -G --data-urlencode "fieldQuery=name eq 'application' and service_offering_id eq '$xsuaa_service_id'" \
                            | jq -r ".items[0].id")
    ```

    For more information about the API, see [Service Plans](../SAP-Service-Manager/service-plans-2c37d0c.md).

3.  Create the service instance of the `xsuaa` service using the `Create a Service Instance` API:

    ```
    xsuaa_instance_id=$(curl -X POST "https://service-manager.cfapps.<region domain>/v1/service_instances?async=false" \
                        -H "Authorization: Bearer <access token>" \
                        -d '{"name": "example-xsuaa-instance","service_plan_id": "'"$application_plan_id"'"}' \
                        | jq -r ".id")
    ```

    The name of the new instance is `example-xsuaa-instance`, and the `async=false` setting indicates that the command output becomes available only once the instance is ready to be used.

    For more information about the API, see [Service Instances](../SAP-Service-Manager/service-instances-9981887.md).

4.  Create a binding to access the service instance you created in the previous step by calling the `Create a Service Binding` API:

    ```
    curl -X POST "https://service-manager.cfapps.<region domain>/v1/service_bindings?async=false" \
                    -H "Authorization: Bearer <access token>" \
                    -d '{"name": "example-xsuaa-binding","service_instance_id": "'"$xsuaa_instance_id"'"}'
    ```

    The name of the new binding is `example-xsuaa-binding`. and the output includes the `credentials` section that contains the access URLs and authorization details required to use the `xsuaa` service.

    For more information about the API, see [Service Bindings](../SAP-Service-Manager/service-bindings-392eb36.md).

5.  Inject service access details to your application:

    > ### Note:  
    > While the method to extract the relevant access and authorization details from the binding credentials is universal for all environments, the way to inject those details to an application is specific to the environment in which the application is deployed.

    In this example, we extract the `clientid` field from the binding credentials, and store it in the `client_id` variable using jq:

    ```
    binding_json=$(curl "https://service-manager.cfapps.<region domain>/v1/service_bindings" \
                    -G --data-urlencode "fieldQuery=name eq 'example-xsuaa-binding'" \
                    -H "Authorization: Bearer <access token>")
    binding_credentials=$(echo $binding_json | jq ".items[0].credentials")
    client_id=$(echo $binding_credentials | jq -r ".clientid")
    ```


You can now consume the `xsuaa` service in the environment of your choice.

**Parent topic:** [Consuming SAP BTP Services from Various Environments](consuming-sap-btp-services-from-various-aa2ba14.md "Learn more about how to consume SAP BTP services from various runtime environments.")

**Related Information**  


[Consuming SAP BTP Services from the Cloud Foundry Environment](consuming-sap-btp-services-from-the-clou-9a3d669.md "SAP BTP, Cloud Foundry environment is an open Platform-as-a-Service (PaaS) targeted at microservice development and orchestration.")

[Consuming SAP BTP Services from the Neo Environment](consuming-sap-btp-services-from-the-neo-7cbbbee.md "SAP BTP, Neo environment is an enterprise platform-as-a-service (enterprise PaaS) that provides comprehensive application development services and capabilities, which lets you build, extend, and integrate business applications in the cloud.")

[Consuming SAP BTP Services from the Kyma Environment](consuming-sap-btp-services-from-the-kyma-20a8360.md "SAP BTP Kyma environment is a fully managed Kubernetes-based environment that allows you to consume external services and use their functionality to build and deploy your own applications.")

[Consuming SAP BTP Services from Kubernetes](consuming-sap-btp-services-from-kubernet-ba4fd1f.md "Kubernetes, also known as K8s, is an open-source environment for automating deployment, scaling, and management of containerized applications. In the following sections, you'll learn how to consume SAP BTP services from Kubernetes.")

