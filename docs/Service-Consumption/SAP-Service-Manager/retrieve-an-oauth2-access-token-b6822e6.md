<!-- loiob6822e603cee4d1ca71ef899a85c5509 -->

# Retrieve an OAuth2 Access Token



1.  Get an access token:

    Use the `uaa_url`, `clientid`, and `clientsecret` you obtained when you created a service instance \([Create a SAP Service Manager Instance and Binding](create-a-sap-service-manager-instance-and-binding-1ca5bbe.md)\) with one of the broker plans \([SAP Service Manager Broker Plans](sap-service-manager-broker-plans-917a8a7.md)\) to request an access token using the following command:

    ```
    curl '<uaa_url>/oauth/token' -X POST \
        -H 'Accept: application/json' \
        -d 'grant_type=client_credentials&client_id=<clientid>&client_secret=<clientsecret>
    ```

    > ### Note:  
    > The access token received also contains the scopes that are granted for this access token. Therefore, only APIs which require one of these scopes can be used with this access token.
    > 
    > ```
    > {
    >   "access_token": "<access_token>",
    >   "token_type": "bearer",
    >   "expires_in": 43199,
    >   "scope": "<xsappname>.job.read <xsappname>.event.read"
    > }
    > 
    > ```

    See [Enable API Access to an XSUAA Configuration](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/ebc9113a520e495ea5fb759b9a7929f2.html).

2.  Add the Authorization header to your request: “Authorization: Bearer <access token\>”


