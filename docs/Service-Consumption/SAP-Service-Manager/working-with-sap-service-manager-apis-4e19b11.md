<!-- loio4e19b11211fe4ca2a266d3fdd4a72188 -->

# Working with SAP Service Manager APIs

The SAP Service Manager service API defines a centralized REST interface that allows the management of environments, service brokers, service offerings, service plans, service instances, and service bindings.

The SAP Service Manager APIs are divided into three groups:

-   SAP Service Manager admin APIs that manage service brokers and attached platforms.

-   Service Controller APIs that allow the SAP Service Manager to act as an Open Service Broker \(OSB\) platform for service brokers that are registered in SAP Service Manager \(SAP Service Manager as a platform\).

-   OSB APIs, which allow the SAP Service Manager to act as a service broker for platforms that are registered in SAP Service Manager \(SAP Service Manager as a Broker\).




<a name="loio4e19b11211fe4ca2a266d3fdd4a72188__section_u4s_gjy_jnb"/>

## API Specifications in SAP API Business Hub and Swagger

Visit [SAP API Business Hub](https://api.sap.com/api/APIServiceManagment/resource) for the list of all SAP Service Manager APIs, their specifications, and links to accompanying documentation.

If you also want to try out the APIs, go to SAP-customized Swagger at <code>https://service-manager.<i class="varname">&lt;app domain&gt;</i>.<i class="varname">&lt;landscape domain&gt;</i>/swaggerui/swagger-ui.html</code>

The Swagger URL changes depending on your app and landscape domains.

> ### Example:  
> If your account is running on the Europe \(Frankfurt\) region, use this URL:
> 
> `https://service-manager.cfapps.eu10.hana.ondemand.com/swaggerui/swagger-ui.html`

-   **[Accessing the APIs](accessing-the-apis-93711c1.md)**  

-   **[Rate Limiting](rate-limiting-97be679.md "Describes how all API requests to the SAP Service
                                Manager service adhere to
		rate limiting rules.")**  
Describes how all API requests to the SAP Service Manager service adhere to rate limiting rules.
-   **[SAP Service Manager API Groups](sap-service-manager-api-groups-9b97aee.md "You can use the following sets of APIs to manage platforms,, service instances, service
		bindings, service plans, and service offerings.")**  
You can use the following sets of APIs to manage platforms,, service instances, service bindings, service plans, and service offerings.

