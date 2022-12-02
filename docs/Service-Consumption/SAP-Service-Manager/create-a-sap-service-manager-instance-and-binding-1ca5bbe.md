<!-- loio1ca5bbeac19340ce959e82b51b2fde1e -->

# Create a SAP Service Manager Instance and Binding

The SAP Service Manager APIs are protected with OAuth 2.0 client credentials. This document describes the general steps you need to perform to create an OAuth client and obtain an access token to call the SAP Service Manager APIs, and shows a detailed example of the procedure in the Cloud Foundry environment.



<a name="loio1ca5bbeac19340ce959e82b51b2fde1e__section_ugp_ywd_4nb"/>

## General Procedure

1.  Create a SAP Service Manager service instance with one of the [SAP Service Manager Broker Plans](sap-service-manager-broker-plans-917a8a7.md).

2.  Create a binding object \(service key in the Cloud Foundry environment\) for the SAP Service Manager instance.

    There are two types of binding objects, depending on the type of authorization you choose:

    -   Default credentials type binding

    -   X.509 credentials type binding


    To create a binding object with the default credentials type, run the following command:

    ```
    smctl bind <sm_instance_name> <sm_binding_name>
    ```

    -   *<sm\_instance\_name\>* - the name of the service instance for which you're creating the binding.
    -   *<sm\_binding\_name\>* - the name of the service binding you're creating.

    The example of a binding object created with the default credentials type:

    ```
    {
    "clientid": "<client_id>",
    "clientsecret": "<client_secret>",
    "sm_url": "<service_manager_URL>",
    "url": "<https://<subdomain>.authentication.<region domain>",
    "xsappname": "<xsapp name>"
    }
    
    ```

    To create a binding object with the X.509 credentials type, run the following command:

    ```
    smctl bind <sm_instance_name> <sm_binding_name> -c {"credential-type":"x509"}
    ```

    > ### Note:  
    > The command example shows minimum requirements for JSON object parameters specification. Besides the `credentials-type`, you can also provide the following parameters in the same object:
    > 
    > -   `key-length` - specifies the byte length of the generated private key. Default value is 2048 bytes.
    > 
    > -   `validity-type` - specifies the validity time unit. Valid values are: `DAYS`, `MONTHS`, and `YEARS`. Default value is `DAYS`.
    > 
    > -   `validity` - specifies the number of time units in `validity-type`. Default value is 7, thus the complete validity defaults to `7 DAYS`.
    > 
    > 
    > The example of the JSON object with all of the parameters specified:
    > 
    > ```
    > {
    >   "credential-type": "x509",
    >   "x509": {
    >     "key-length": 2048,
    >     "validity": 7,
    >     "validity-type": "DAYS"
    >   }
    > }
    > ```

    The example of a binding object created with the X.509 credentials type:

    ```
     {
             "clientid": "xxxxxxx",
             "certificate": "-----BEGIN CERTIFICATE-----...-----END CERTIFICATE",
             "key": "-----BEGIN RSA PRIVATE KEY-----...-----END RSA PRIVATE KEY-----",
             "certurl": "<certificate_URL>",
             "xsappname": "<name>",
             "sm_url": "<service_manager_URL>"
         }
    ```


For more information about the required steps for different environment types, see [Consuming SAP BTP Services from Various Environments](../Consuming-SAP-BTP-Services-from-Various-Environments/consuming-sap-btp-services-from-various-aa2ba14.md).



<a name="loio1ca5bbeac19340ce959e82b51b2fde1e__section_im4_f4d_k3b"/>

## Obtaining Access Credentials in Cloud Foundry



### Prerequisites

-   You have downloaded and installed the latest version of the Cloud Foundry command line interface \(cf CLI\). See [Download and Install the Cloud Foundry Command Line Interface](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/4ef907afb1254e8286882a2bdef0edf4.html).
-   You have a Cloud Foundry org which has service access to at least one **service-manager** service plan.

    > ### Note:  
    > To check if you have an access to Service Manager \(technical name: `service-manager`\) in the Cloud Foundry marketplace, execute the following command:
    > 
    > ```
    > cf marketplace -s service-manager
    > ```
    > 
    > You should see the `service-manager` service plans to which your orgs have access.

-   Your have created a space in your Cloud Foundry org.



### Procedure

1.  Login to your space using cf CLI. See [Log On to the Cloud Foundry Environment Using the Cloud Foundry Command Line Interface](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/7a37d66c2e7d401db4980db0cd74aa6b.html).

    **Example:**

    ```
    
    cf api https://api.<landscape domain>
    cf login
    cf target -o ORG -s SPACE
    
    ```

2.  Using the cf CLI run the following command to create a service instance. See [Create Service Instances Using the Cloud Foundry Command Line Interface](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/a872531845d6416b8fa07a8b84875d7e.html)

    ```
    cf create-service service-manager PLAN SERVICE_INSTANCE
    ```

    Specify the following parameters:

    -   `PLAN:` The name of the service plan you want to use. See [SAP Service Manager Broker Plans](sap-service-manager-broker-plans-917a8a7.md).
    -   `SERVICE_INSTANCE:` Name of the service instance.

3.  Get the OAuth 2.0 client information and SAP Service Manager endpoints using either one of the following methods:
    1.  Bind the service instance to your application. See [Bind Service Instances to Applications Using the Cloud Foundry Command Line Interface](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/296cd5945fd84d7d91061b2b2bcacb93.html).
        -   Display the environment of your application.

            ```
            cf env APP-NAME
            ```

        -   Locate the details of your SAP Service Manager instance in the application environment, for example:

            ```
            System-Provided:
            {
             "VCAP_SERVICES": {
              ...
              "service-manager": [
               {
                "credentials": {
            		 		"clientid": "<client_id>",
             				"clientsecret": "<client_secret>",
             				"sm_url": "<service management URL>",
            				 "url": "<token URL>",
            				 "xsappname": "<xsapp name>"
            				},    
                "instance_name": "<SERVICE_INSTANCE>",
                "plan": "<PLAN>"
               }
              ]
            ...
            }
            
            ```


    2.  Create a service key. See [Create Service Keys Using the Cloud Foundry Command Line Interface](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/7de6b314b62748b9b59df5fc09dbe8fb.html).

        ```
        cf create-service-key SERVICE_INSTANCE SERVICE_KEY
        ```

        Specify the following parameters:

        -   `SERVICE_INSTANCE:`Name of the service instance.
        -   `SERVICE_KEY:`Name for the service key.

        Display the service key information:

        ```
        cf service-key SERVICE_INSTANCE SERVICE_KEY
        {
         "clientid": "<client_id>",
         "clientsecret": "<client_secret>",
         "sm_url": "<service management URL>",
         "url": "<https://<subdomain>.authentication.<region domain>",
         "xsappname": "<xsapp name>"
        },    
        
        ```





<a name="loio1ca5bbeac19340ce959e82b51b2fde1e__section_xph_mcr_w3b"/>

## Working With Swagger APIs

Use the values of the parameters: `clientid`, `clientsecret`, and the *<subdomain\>* part of the `url` parameter's value you obtained in the previous step to authenticate with the SAP Service Manager.

For example, in the following output:

```

{
"clientid": "sb-fd7c7fac-61d5-4871-bce6-f82584abea4e!b4065|service-manager!b4065",
"clientsecret": "******Qa7tJPIu***********",
"sm_url": "https://service-manager.cfapps.sap.hana.ondemand.com",
"url": "https://svcmgr.authentication.sap.hana.ondemand.com",
"xsappname": "fd7c7fac-61d5-4871-bce6-f82584abea4e!b4065|service-manager!b4065"
}

```

the needed values are:

-   `sb-fd7c7fac-61d5-4871-bce6-f82584abea4e!b4065|service-manager!b4065` for `clientid`

-   `******Qa7tJPIu***********` for `clientsecret` \(only part of the value is exposed in the example\)

-   `svcmgr` in the `url`

Go to <code>https://service-manager.<i class="varname">&lt;app domain&gt;</i>.<i class="varname">&lt;landscape domain&gt;</i>/swaggerui/swagger-ui.html</code>

> ### Example:  
> If your account is running on the Europe \(Frankfurt\) region, use this URL:
> 
> `https://service-manager.cfapps.eu10.hana.ondemand.com/swaggerui/swagger-ui.html`

-   **[SAP Service Manager Broker Plans](sap-service-manager-broker-plans-917a8a7.md "")**  


