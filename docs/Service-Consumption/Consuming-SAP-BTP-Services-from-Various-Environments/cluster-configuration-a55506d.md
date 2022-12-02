<!-- loioa55506d6ceea4e3bb4534739bf0699d9 -->

# Cluster Configuration



## Procedure

1.  Register a subaccount-scoped cluster.

    ```
    smctl register-platform <platform name> kubernetes
    ```

    You can choose any arbitrary name for the technical name of the cluster as long as it is unique per region.

    The call above will return a similar output:

    ```
    ID             Name                     Type        Description  Created                      Updated                      Labels                         Username    Password
    -------------  -----------------------  ----------  -----------  ---------------------------  ---------------------------  -----------------------------  -----------  ----------
    <platform id>  <platform name>  kubernetes               2019-11-26T12:54:28.040401Z  2019-11-26T12:54:28.040401Z  subaccount_id=<subaccount id>  admin         admin    
    ```

    -   The value of *name* must be unique in the region.

    -   *Username* and *Password* are the credentials that the SAP Service Manager broker proxy uses to communicate with SAP Service Manager. The credentials need to be provided in the helm chart for installing the SAP Service Manager broker proxy.


2.  Install the service catalog in your Kubernetes cluster.

    1.  Add the service-catalog Helm repository to your machine:

        ```
        helm repo add svc-cat https://svc-catalog-charts.storage.googleapis.com
        ```

    2.  Create the catalog namespace:

        ```
        kubectl create namespace catalog
        ```

    3.  Install the Service Catalog in the catalog namespace:

        ```
        helm install catalog svc-cat/catalog  --namespace catalog --version 0.3.0
        ```


    See [Install Service Catalog using Helm](https://kubernetes.io/docs/tasks/service-catalog/install-service-catalog-using-helm/)

    > ### Note:  
    > Svcat v0.3.0 is required for compatibility with Kubernetes clusters v1.17.4.

3.  Install the SAP Service Manager broker proxy in your Kubernetes cluster. See [service-broker-proxy-k8s](service-broker-proxy-k8shttps://github.com/Peripli/service-broker-proxy-k8s/blob/master/charts/service-broker-proxy-k8s/README.md).

    1.  Add the Peripli Helm repository to your machine:

        ```
        helm repo add peripli 'https://peripli.github.io'
        ```

    2.  Create the service-broker-proxy namespace:

        ```
        kubectl create namespace service-broker-proxy
        ```

    3.  Install the SAP Service Manager Broker Proxy in the service-broker-proxy namespace:

        ```
        helm install service-broker-proxy peripli/service-broker-proxy-k8s \
          --namespace service-broker-proxy \
          --version <VERSION> \
          --set config.sm.url=<SM_URL> \
          --set sm.user=<USER> \
          --set sm.password=<PASSWORD>
        ```

        -   Replace the SM\_URL with the URL of the SAP Service Manager.

            Syntax: `https://service-manager.cfapps.<landscape domain>` \(to find the landscape domain of the SAP Service Manager, see [Regions and API Endpoints Available for the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html#loiof344a57233d34199b2123b9620d0bb41).

        -   Replace the USER and PASSWORD with the credentials obtained in Step 2.

        -   Replace the VERSION with the required version as listed on [Releases](https://github.com/Peripli/service-broker-proxy-k8s/releases). It is recommended to use v0.7.0.




