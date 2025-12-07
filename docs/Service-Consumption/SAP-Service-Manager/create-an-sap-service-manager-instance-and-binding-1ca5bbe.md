<!-- loio1ca5bbeac19340ce959e82b51b2fde1e -->

# Create an SAP Service Manager Instance and Binding

Learn how to create an OAuth client and obtain access credentials to call the SAP Service Manager APIs. The APIs are protected with OAuth 2.0 client credentials.



<a name="loio1ca5bbeac19340ce959e82b51b2fde1e__section_ugp_ywd_4nb"/>

## Overview

To access the SAP Service Manager, you need to:

1.  Create an SAP Service Manager service instance
2.  Create a service binding to obtain OAuth credentials
3.  Use the credentials to authenticate API calls

This guide provides detailed procedures for both general environments \(using btp CLI\) and Cloud Foundry-specific scenarios.



## Create Service Instance and Binding Using btp CLI

Use the SAP BTP command-line interface \(btp CLI\) to create service instances and bindings for any environment.

The btp CLI calls the BTP control plane, which then calls Service Manager's OSB API.

1.  **Create an****SAP Service Manager ****service instance:**

    ```
    btp create services/instance --offering-name service-manager --plan-name <PLAN> --name <INSTANCE_NAME> --subaccount <SUBACCOUNT_ID>
    ```

    Variables:

    -   *<PLAN\>* - The service plan \(for example, `container`, `subaccount-admin`\). See [SAP Service Manager Broker Plans](sap-service-manager-broker-plans-917a8a7.md)
    -   *<INSTANCE\_NAME\>* - A unique name for your service instance

    -   *<SUBACCOUNT\_ID\>* - Your subaccount ID


    For more information, see [Creating Service Instances](creating-service-instances-fad874a.md).

2.  **Create a service binding:**

    Create a binding to retrieve the OAuth credentials. Choose between two credential types:

    **Option A: Default Credentials \(Client ID and Secret\)**

    This is the standard authentication method using a client ID and secret.

    The OAuth token issued with these credentials contains scopes that are derived from the selected Service Manager service plan. Different service plans grant different sets of scopes, which in turn determine which API operations are allowed. All API requests are authorized at runtime based on the scopes contained in the access token. For an overview of which plans grant which scopes, see [SAP Service Manager Broker Plans](sap-service-manager-broker-plans-917a8a7.md),

    ```
    btp create services/binding --name <BINDING_NAME> --instance-name <INSTANCE_NAME> --subaccount <SUBACCOUNT_ID>
    ```

    Variables:

    -   *<BINDING\_NAME\>* - A unique name for your service binding
    -   *<INSTANCE\_NAME\>* - The name of your service instance \(from Step 1\)
    -   *<SUBACCOUNT\_ID\>* - Your subaccount ID

    The binding will contain credentials in this format:

    ```
    {
      "clientid": "<client_id>",
      "clientsecret": "<client_secret>",
      "sm_url": "<service_manager_URL>",
      "url": "https://<subdomain>.authentication.<region_domain>",
      "xsappname": "<xsapp_name>"
    }
    ```

    > ### Note:  
    > OAuth tokens are tenant-scoped and a token issued for one subaccount cannot be used in another. The `sm_url` value is region-specific. SAP Service Manager is deployed separately per region, and access tokens and API requests are valid only for the region in which the service instance was created.

    **Option B: X.509 Certificate-Based Credentials**

    Use certificate-based authentication for enhanced security:

    **Basic command:**

    ```
    btp create services/binding --name <BINDING_NAME> --instance-name <INSTANCE_NAME> --subaccount <SUBACCOUNT_ID> --parameters '{"credential-type":"x509"}'
    ```

    **Advanced configuration with custom parameters:**

    You can customize the certificate properties:

    ```
    btp create services/binding --name <BINDING_NAME> --instance-name <INSTANCE_NAME> --subaccount <SUBACCOUNT_ID> --parameters '{"credential-type":"x509","x509":{"key-length":2048,"validity":7,"validity-type":"DAYS"}}'
    ```

    **X.509 Parameters**


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Description
    
    </th>
    <th valign="top">

    Default
    
    </th>
    <th valign="top">

    Valid Values
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    `key-length`
    
    </td>
    <td valign="top">
    
    Byte length of the generated private key
    
    </td>
    <td valign="top">
    
    2048
    
    </td>
    <td valign="top">
    
    Any valid key length
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `validity`
    
    </td>
    <td valign="top">
    
    Number of time units for certificate validity
    
    </td>
    <td valign="top">
    
    7
    
    </td>
    <td valign="top">
    
    Any positive integer
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `validity-type`
    
    </td>
    <td valign="top">
    
    Time unit for validity
    
    </td>
    <td valign="top">
    
    DAYS
    
    </td>
    <td valign="top">
    
    DAYS, MONTHS, YEARS
    
    </td>
    </tr>
    </table>
    
    **Example JSON parameters object:**

    ```
    {
      "credential-type": "x509",
      "x509": {
        "key-length": 2048,
        "validity": 7,
        "validity-type": "DAYS"
      }
    }
    ```

    The X.509 binding will contain:

    ```
    {
      "clientid": "<client_id>",
      "certificate": "-----BEGIN CERTIFICATE-----...-----END CERTIFICATE-----",
      "key": "-----BEGIN RSA PRIVATE KEY-----...-----END RSA PRIVATE KEY-----",
      "certurl": "<certificate_URL>",
      "xsappname": "<xsapp_name>",
      "sm_url": "<service_manager_URL>"
    }
    ```

3.  **Retrieve Binding Credentials**

    To view your binding credentials:

    ```
    btp get services/binding <BINDING_NAME> --instance-name <INSTANCE_NAME> --subaccount <SUBACCOUNT_ID> --show-parameters
    ```


> ### Caution:  
> Protect your OAuth credentials at all times. Do not store client IDs, client secrets, certificates, or service keys in source code repositories, documentation files, or shared communication tools. Rotate client secrets and certificates regularly according to your organization’s security policy. If credentials are exposed or suspected to be compromised, revoke them immediately and issue new ones.



### Credential Revocation and Rotation

If an OAuth client secret, certificate, or service key is exposed or suspected to be compromised, revoke it immediately and generate new credentials. For bindings created with the btp CLI, delete and recreate the service binding to rotate the credentials. For Cloud Foundry service keys, delete the affected service key and create a new one. Update all dependent applications and tools with the new credentials before resuming API access.

For more information about consuming services from different environment types, see [Consuming SAP BTP Services from Various Environments](../Consuming-SAP-BTP-Services-from-Various-Environments/consuming-sap-btp-services-from-various-aa2ba14.md).



<a name="loio1ca5bbeac19340ce959e82b51b2fde1e__section_im4_f4d_k3b"/>

## Obtain Credentials in Cloud Foundry Environment

If you're working specifically in a Cloud Foundry environment, use the cf CLI to create instances and retrieve credentials.



### Prerequisites

Before you begin, ensure you have:

-   cf CLI installed - See [Download and Install the Cloud Foundry Command Line Interface](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/4ef907afb1254e8286882a2bdef0edf4.html).
-   Service access - A Cloud Foundry org with access to at least one **`service-manager`** service plan.
-   Cloud Foundry space - A space created in your Cloud Foundry org

Verify service access:

Check if you have access to Service Manager in the Cloud Foundry marketplace:

```
cf marketplace -s service-manager
```

This command displays all `service-manager` service plans available to your org.

> ### Note:  
> To create service instances, service bindings, and service keys, you must have the required SAP BTP authorizations in the target subaccount or Cloud Foundry organization and space. If you do not have sufficient permissions, the commands will fail with authorization errors. Contact your subaccount or organization administrator if access is missing.



### Procedure

1.  **Log in to Cloud Foundry**

    Connect to your Cloud Foundry environment and target your org and space:

    Log in to your space using cf CLI.

    **Example:**

    ```
    
    cf api https://api.<landscape-domain>
    cf login
    cf target -o ORG -s SPACE
    
    ```

    Replace *<landscape-domain\>*, *<ORG\>*, and *<SPACE\>* with your values.

    See [Log On to the Cloud Foundry Environment Using the Cloud Foundry Command Line Interface](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/7a37d66c2e7d401db4980db0cd74aa6b.html).

2.  **Create Service Instance**

    Create a service instance in your Cloud Foundry space:

    ```
    cf create-service service-manager <PLAN> <SERVICE_INSTANCE>
    ```

    Variables:

    -   *<PLAN\>* - The service plan name \(see [SAP Service Manager Broker Plans](sap-service-manager-broker-plans-917a8a7.md)\).
    -   *<SERVICE\_INSTANCE\>* - A unique name for your service instance.

    See [Create Service Instances Using the Cloud Foundry Command Line Interface](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/a872531845d6416b8fa07a8b84875d7e.html).

3.  **Retrieve OAuth Credentials**

    Choose one of the following methods to obtain your OAuth credentials:

    **Method 1: Bind to an Application**

    Use this method if you want to automatically inject credentials into an application.

    1.  Bind the service instance to your application:

        ```
        cf bind-service <APP_NAME> <SERVICE_INSTANCE>
        ```

        Variables:

        -   *<APP\_NAME\>* - Your app name.
        -   *<SERVICE\_INSTANCE\>* - Service instance name.

        See [Bind Service Instances to Applications Using the Cloud Foundry Command Line Interface](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/296cd5945fd84d7d91061b2b2bcacb93.html).

    2.  Restage your application:

        ```
        cf restage <APP_NAME>
        ```

    3.  View the credentials in the application environment:

        ```
        cf env <APP_NAME>
        ```

    4.  Locate the credentials in VCAP\_SERVICES:

        ```
        {
          "VCAP_SERVICES": {
            "service-manager": [
              {
                "credentials": {
                  "clientid": "<client_id>",
                  "clientsecret": "<client_secret>",
                  "sm_url": "<service_manager_URL>",
                  "url": "<token_URL>",
                  "xsappname": "<xsapp_name>"
                },
                "instance_name": "<SERVICE_INSTANCE>",
                "plan": "<PLAN>"
              }
            ]
          }
        }
        ```


    **Method 2: Create a Service Key \(Recommended for API Testing\)**

    Use this method to obtain credentials for manual use, API testing, or external tools.

    1.  Create a service key:

        ```
        cf create-service-key <SERVICE_INSTANCE> <SERVICE_KEY>
        ```

        Variables:

        *<SERVICE\_INSTANCE\>* - Your service instance name

        *<SERVICE\_KEY\>* - A name for the service key.

        See [Create Service Keys Using the Cloud Foundry Command Line Interface](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/7de6b314b62748b9b59df5fc09dbe8fb.html).

    2.  Display the service key:

        ```
        cf service-key <SERVICE_INSTANCE> <SERVICE_KEY>
        ```

        Output:

        ```
        {
          "clientid": "<client_id>",
          "clientsecret": "<client_secret>",
          "sm_url": "<service_manager_URL>",
          "url": "https://<subdomain>.authentication.<region_domain>",
          "xsappname": "<xsapp_name>"
        }    
        
        ```


    > ### Remember:  
    > Save these credentials securely. You'll need them to authenticate API calls.

    > ### Note:  
    > Successful authentication does not override API consumption limits. Even properly authenticated and authorized requests remain subject to rate-limiting rules.




### Manually Retrieve an OAuth 2.0 Access Token \(Optional\)

If you need to call the SAP Service Manager APIs outside of SAP BTP tooling, applications, or the SAP Business Accelerator Hub, for example, from scripts, external systems, or API testing tools, you can manually request an OAuth 2.0 access token using the client credentials you retrieved from the service binding or service key.

Use the `url`, `clientid`, and `clientsecret` values to request an access token:

```
curl '<url>/oauth/token' -X POST \
  -H 'Accept: application/json' \
  -d 'grant_type=client_credentials&client_id=<clientid>&client_secret=<clientsecret>'

```

Response example:

```
{
  "access_token": "<access_token>",
  "token_type": "bearer",
  "expires_in": 43199,
  "scope": "<xsappname>.job.read <xsappname>.event.read"
}

```

> ### Note:  
> The access token is valid only for the duration specified in the `expires_in` field. When the token expires, applications must request a new access token using the same client credentials. The OAuth 2.0 client-credentials flow does not provide a refresh token. Long-running applications and automation scripts must therefore implement automatic token renewal.

Add the access token to all API requests using the following HTTP header:

```
Authorization: Bearer <access_token>

```

> ### Note:  
> The access token contains the scopes granted for this client. Only APIs that require one of these scopes can be called with this token.
> 
> For more information, see [Enable API Access to an XSUAA Configuration](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/ebc9113a520e495ea5fb759b9a7929f2.html).

> ### Note:  
> Even with a valid and authorized access token, API requests can be rejected due to enforced rate limits. If the allowed request quota is exceeded, the Service Manager API returns `HTTP 429` \(Too Many Requests\). For details, see [Rate Limiting](https://help.sap.com/docs/service-manager/sap-service-manager/rate-limiting?version=Cloud).



<a name="loio1ca5bbeac19340ce959e82b51b2fde1e__section_xph_mcr_w3b"/>

## Try Out the Service Manager APIs in the SAP Business Accelerator Hub

The SAP Business Accelerator Hub provides an interactive environment for exploring and testing the SAP Service Manager APIs. It allows you to understand API behavior, inspect request and response structures, and run real API calls, all without installing tools or writing code.



### Why Use SAP Business Accelerator Hub?

The Hub lets you test API calls directly in your browser, work with an interactive console that displays real responses, access complete endpoint documentation, browse structured API references and data schemas, view sample responses, and generate ready-to-use code snippets.



### Access the API Package

You can access the SAP Service Manager API package here: [SAP Service Manager APIs](https://api.sap.com/api/APIServiceManager/resource/platforms).

The package includes several navigation tabs:

-   Overview – Introduction to SAP Service Manager
-   API Reference – Complete list of endpoints
-   Schema View – Data models used by the API
-   Try Out – Browser-based interactive testing console
-   Documents – Additional supporting material



### Configure Your Environment for API Testing

To test APIs using your own Service Manager landscape, you must configure an environment in the Hub using your OAuth 2.0 client credentials:

1.  **Gather Your Credentials**

    Obtain the following fields from your service binding or service key:


    <table>
    <tr>
    <th valign="top">

    Field
    
    </th>
    <th valign="top">

    Source
    
    </th>
    <th valign="top">

    Example Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Client ID
    
    </td>
    <td valign="top">
    
    `clientid`
    
    </td>
    <td valign="top">
    
    sb-fd7c7fac-…
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client Secret
    
    </td>
    <td valign="top">
    
    `clientsecret`
    
    </td>
    <td valign="top">
    
    AbCd1234…
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Service Manager URL
    
    </td>
    <td valign="top">
    
    `sm_url`
    
    </td>
    <td valign="top">
    
    https://service-manager.cfapps.eu10.hana.ondemand.com
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Token URL
    
    </td>
    <td valign="top">
    
    `url`
    
    </td>
    <td valign="top">
    
    https://svcmgr.authentication.eu10.hana.ondemand.com
    
    </td>
    </tr>
    </table>
    
    Example service key:

    ```
    {
      "clientid": "sb-fd7c7fac-61d5-4871-bce6-f82584abea4e!b4065|service-manager!b4065",
      "clientsecret": "AbCd1234EfGh5678IjKl",
      "sm_url": "https://service-manager.cfapps.eu10.hana.ondemand.com",
      "url": "https://svcmgr.authentication.eu10.hana.ondemand.com",
      "xsappname": "fd7c7fac-61d5-4871-bce6-f82584abea4e!b4065|service-manager!b4065"
    }
    
    ```

2.  **Configure the Environment**

    1.  Open the *Try Out* tab in the API reference page.

    2.  Select *Environment → + Add New Environment.*

    3.  Fill in the configuration fields:


        <table>
        <tr>
        <th valign="top">

        Field
        
        </th>
        <th valign="top">

        Value
        
        </th>
        <th valign="top">

        Notes
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        Display Name
        
        </td>
        <td valign="top">
        
        Any descriptive name
        
        </td>
        <td valign="top">
        
        Example: “My Service Manager”
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Starting URL
        
        </td>
        <td valign="top">
        
        Default value
        
        </td>
        <td valign="top">
        
        Matches your landscape
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Landscape
        
        </td>
        <td valign="top">
        
        Your region
        
        </td>
        <td valign="top">
        
        Extracted from `sm_url` \(for example, eu10\)
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Authentication Type
        
        </td>
        <td valign="top">
        
        OAuth 2.0 Application Flow
        
        </td>
        <td valign="top">
        
        Preselected
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Client ID
        
        </td>
        <td valign="top">
        
        Paste your `clientid`
        
        </td>
        <td valign="top">
        
        From the service key
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Client Secret
        
        </td>
        <td valign="top">
        
        Paste your `clientsecret`
        
        </td>
        <td valign="top">
        
        From the service key
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Token URL
        
        </td>
        <td valign="top">
        
        Auto-filled
        
        </td>
        <td valign="top">
        
        Must match your authentication domain
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Subdomain
        
        </td>
        <td valign="top">
        
        Extracted from `url`
        
        </td>
        <td valign="top">
        
        For example, `svcmgr`
        
        </td>
        </tr>
        </table>
        
    4.  Choose an environment scope:
        -   Use for this session only \(default\), or

        -   Save for future sessions to reuse the configuration later.


    5.  Click *Configure*. The system retrieves an OAuth access token automatically.




### Test API Calls

With your environment configured, you can test any endpoint:

1.  Select an endpoint from the navigation panel, for example:
    -   `GET /v1/service_instances`
    -   `GET /v1/service_bindings`

2.  Review optional request parameters:

    -   `fieldQuery` – Filter by fields

    -   `labelQuery` – Filter by labels

    -   `max_items` – Result limit

    -   `token` – Pagination token


3.  Run the API and review the response.



### Example: List All Platforms

Response:

> ### Sample Code:  
> ```
> {
>   "num_items": 2,
>   "items": [
>     {
>       "id": "platform-123",
>       "name": "my-k8s-cluster",
>       "type": "kubernetes",
>       "description": "Production Kubernetes cluster"
>     },
>     {
>       "id": "platform-456",
>       "name": "cf-org-space",
>       "type": "cloudfoundry",
>       "description": "Cloud Foundry development space"
>     }
>   ]
> }
> 
> ```



### Generate Code Snippets

Each endpoint includes a *Code Snippet* tab that generates ready-to-use code for the configured request. You can copy the generated snippet and use it directly in your application.

Example cURL snippet:

> ### Sample Code:  
> ```
> curl -X GET \
>   'https://service-manager.cfapps.eu10.hana.ondemand.com/v1/platforms' \
>   -H 'Authorization: Bearer <access_token>'
> 
> ```



### Troubleshooting Authentication Failures

If API calls return authentication errors such as `401 Unauthorized` or `403 Forbidden`, perform the following checks:

1.  Verify that the client ID and client secret belong to the correct service instance.

2.  Confirm that the token URL matches the authentication domain of your landscape.

3.  Ensure that the service instance is not deleted or in a failed state.

4.  Check that your OAuth token has not expired and is being refreshed correctly.

5.  Confirm that your user has sufficient authorizations in the target subaccount or Cloud Foundry space.


If the issue persists, revoke the credentials and recreate the binding or service key.



### Understanding API Key vs. OAuth Authentication

The *Show API Key* button provides an API key for certain Hub features but is not used for Service Manager API authentication.

Service Manager APIs always require OAuth 2.0 client credentials authentication, which is handled through the Try Out / Configure Environment workflow. The Hub automatically manages token generation and renewal.



### Common Security Misconfigurations to Avoid

Check the following if authentication does not behave as expected or if credentials appear to work inconsistently:

-   Using expired client secrets or expired X.509 certificates

-   Using a service key that was deleted and recreated without updating applications

-   Mixing credentials from different subaccounts or landscapes

-   Using a token URL that does not match the authentication domain of the Service Manager instance

-   Storing credentials in application source code instead of environment variables

-   Reusing the same service key across multiple unrelated applications




### Learn More

For more information, see:

-   [SAP Service Manager API Reference](https://api.sap.com/api/APIServiceManager/resource/platforms)
-   [SAP Business Accelerator Hub Onboarding Guide](https://help.sap.com/docs/business-accelerator-hub/sap-business-accelerator-hub-onboarding-guide/setting-up-sap-business-accelerator-hub?version=Cloud)

-   **[SAP Service Manager Broker Plans](sap-service-manager-broker-plans-917a8a7.md "")**  


