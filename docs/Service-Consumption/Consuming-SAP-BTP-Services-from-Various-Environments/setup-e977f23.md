<!-- loioe977f23be2ed4cd9aa0b32704b37d77e -->

# Setup



<a name="loioe977f23be2ed4cd9aa0b32704b37d77e__section_by4_z5p_r4b"/>

## Procedure

1.  Install cert-manager.

    Cert-manager is used to set up the certificates needed for internal communication between the Kubernetes API server and the deployment of the SAP BTP service operator in your cluster.

    For more information, see [Kubernetes cert-manager](https://cert-manager.io/docs/installation/kubernetes/).

2.  Obtain the access credentials for the SAP BTP service operator:

    1.  Using the SAP BTP cockpit or Service Manager Control \(SMCTL\) command-line interface, create an instance of the SAP Service Manager \(technical name: `service-manager`\) with the plan: `service-operator-access`.

        > ### Note:  
        > If you can't see the needed plan, you need to entitle your subaccount to use SAP Service Manager.
        > 
        > For more information about how to entitle a service to a subaccount, see [Configure Entitlements and Quotas for Subaccounts](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/5ba357b4fa1e4de4b9fcc4ae771609da.html).

        For more information about creating service instances, see:

        -   [Creating Instances in Other Environments](../SAP-Service-Manager/creating-instances-in-other-environments-bf71f6a.md)

        -   [provision](../SAP-Service-Manager/provision-b327b66.md) \(SMCTL command name\)


    2.  Create a binding to the created service instance.

        For more information about creating service bindings, see:

        -   [Creating Service Bindings in Other Environments](../SAP-Service-Manager/creating-service-bindings-in-other-environments-55b31ea.md)

        -   [bind](../SAP-Service-Manager/bind-f53ff26.md)


    3.  Retrieve the generated access credentials from the created binding object.

        The example of the binding object created with the default credentials type:

        ```
        
         {
             "clientid": "xxxxxxx",
             "clientsecret": "xxxxxxx",
             "url": "https://mysubaccount.authentication.eu10.hana.ondemand.com",
             "xsappname": "<name>",
             "sm_url": "<service_manager_URL>"
         }
        ```

        The example of the binding object created with the X.509 credentials type:

        ```
         {
                 "clientid": "xxxxxxx",
                 "certificate": "-----BEGIN CERTIFICATE-----XXX-----END CERTIFICATE",
                 "key": "-----BEGIN RSA PRIVATE KEY-----XXX-----END RSA PRIVATE KEY-----",
                 "certurl": "<certificate_URL>",
                 "xsappname": "<name>",
                 "sm_url": "<service_manager_URL>"
             }
        ```


3.  Deploy the SAP BTP service operator in the cluster using the obtained access credentials.

    The example of the deployment that uses the default access credentials type:

    ```
    helm upgrade --install sapbtp-operator https://github.com/SAP/sap-btp-service-operator/releases/download/<release>/sapbtp-operator-<release>.tgz \
        --create-namespace \
        --namespace=sapbtp-operator \
        --set manager.secret.clientid=<clientid> \
        --set manager.secret.clientsecret=<clientsecret> \
        --set manager.secret.sm_url=<sm_url> \
        --set manager.secret.tokenurl=<url>
    ```

    The example of the deployment that uses the X.509 access credentials type:

    ```
    helm upgrade --install sap-btp-operator https://github.com/SAP/sap-btp-service-operator/releases/download/<release>/sap-btp-operator-<release>.tgz \
        --create-namespace \
        --namespace=sap-btp-operator \
        --set manager.secret.clientid=<clientid> \
        --set manager.secret.tls.crt="$(cat /path/to/cert)" \
        --set manager.secret.tls.key="$(cat /path/to/key)" \
        --set manager.secret.sm_url=<sm_url> \
        --set manager.secret.tokenurl=<certurl>
    
    ```




For the list of the available SAP BTP service operator releases, see [Available Releases](https://github.com/SAP/sap-btp-service-operator/releases).

> ### Note:  
> To learn more about how to consume SAP BTP services from any hyperscaler, see [Consume SAP BTP Services from Any Hyperscaler](https://developers.sap.com/tutorials/btp-hyperscaler-extension.html).

