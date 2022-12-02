<!-- loioec7f5c7703db466e8f234f1cd362cbfc -->

# Migrating from svcat to SAP BTP Service Operator

Learn how to migrate a registered Kubernetes platform, based on the Kubernetes Service Catalog \(svcat\) and SAP Service Manager agent, together with its content, to an SAP BTP service operator-based platform.



<a name="loioec7f5c7703db466e8f234f1cd362cbfc__section_psz_f5h_wqb"/>

## Context

SAP BTP service operator enables you to provision and consume SAP BTP offerings from Kubernetes cluster in a Kubernetes-native way, based on the Kubernetes Operator pattern.



<a name="loioec7f5c7703db466e8f234f1cd362cbfc__section_adc_l5h_wqb"/>

## Prerequisites

-   You have Service Manager Control \(SMCTL\) Command-Line tool. See [Using the Service Manager Control \(SMCTL\) Command-Line Tool](../SAP-Service-Manager/using-the-service-manager-control-smctl-command-line-tool-0107f3f.md).

-   You must be an SAPBTP subaccount admin.




<a name="loioec7f5c7703db466e8f234f1cd362cbfc__section_lr4_nvh_wqb"/>

## Procedure

The procedure consists of two main groups of steps; first, you set up the service operator and the migration command line interface in the same cluster in which your Kubernetes service-catalog content is located, then you perform the migration.



### Setup

1.  Perform steps 1 and 2 described in the [Setup](setup-e977f23.md) topic.

2.  Deploy the SAP BTP service operator by executing the following command:

    ```
     helm upgrade --install sap-btp-operator https://github.com/SAP/sap-btp-service-operator/releases/download/<release>/sap-btp-operator-<release>.tgz \
         --create-namespace 
         --namespace=sap-btp-operator 
         --set manager.secret.clientid=<clientid> 
         --set manager.secret.clientsecret=<clientsecret> 
         --set manager.secret.url=<sm_url> 
         --set manager.secret.tokenurl=<url>
         --set cluster.id=<clusterID>
    
    ```

    > ### Note:  
    > For *<clusterID\>*, specify the ID of the cluster. To find it, run the following command:
    > 
    > ```
    > kubectl get configmap -n catalog cluster-info -o yaml
    > ```
    > 
    > and extract `id` from the output.
    > 
    > Output example:
    > 
    > ```
    > apiVersion: v1
    > data:
    > id: ab7fa5e9-5cc3-468f-ab4d-143458785d07
    > kind: ConfigMap
    > metadata:
    > .
    > .
    > ```

3.  Download and install SAP BTP service operator CLI in one of the following ways:

    -   Manual Installation:

        1.  Get the CLI needed to perform the service operator migration by running the following command:

            ```
            go get github.com/SAP/sap-btp-service-operator-migration
            ```

        2.  Install the CLI:

            ```
            go install github.com/SAP/sap-btp-service-operator-migration
            ```

        3.  Rename the CLI binary:

            ```
            mv $GOPATH/bin/sap-btp-service-operator-migration $GOPATH/bin/migrate
            ```


    -   Automatic Installation:

        Download the latest release of the CLI. For more information, see [SAP BTP Service Operator CLI Releases](https://github.com/SAP/sap-btp-service-operator-migration/releases).


    You need the CLI to perform the migration.


CLI Overview

```
Tool used to migrate content from SVCAT to SAP BTP Service Operator-based platform.

Usage:
  migrate [flags]
  migrate [command]

Available Commands:
  dry-run     Run migration in dry-run mode
  help        Help about any command
  run         Run migration process
  version     Prints migrate version

Flags:
  -c, --config string       Config file (default is $HOME/.migrate/config.json)
  -h, --help                Help command for the migrate
  -k, --kubeconfig string   Absolute path to the kubeconfig file (default $HOME/.kube/config)
  -n, --namespace string    Specify the namespace to find operator secret (default sap-btp-operator)
```



### Migration

1.  Prepare your platform for migration by executing the following command:

    ```
    smctl curl -X PUT -d '{"sourcePlatformID": ":platformID"}' /v1/migrate/service_operator/:instanceID
    ```

    Where the parameter values are as following:

    -   `platformID` is the ID that was generated when you registered a subaccount-scoped cluster in the step 1 of the Cluster Configuration topic. See [Cluster Configuration](cluster-configuration-a55506d.md).

    -   `instanceID` is the ID of the `service-operator-access` instance created in the step 1 of the Setup subsection.


2.  Execute the migration by running the following command:

    ```
    migrate run
    ```

    .

    > ### Tip:  
    > You can perform a dry run before you execute the migration by running the command:
    > 
    > ```
    > migrate dry-run
    > ```
    > 
    > Dry run is useful if you wish to execute the scan and validation steps described in the Migration Script Example section below without performing the actual migration.
    > 
    > At the end of the run, summary including all encountered errors is shown.
    > 
    > This way, you can decide whether to continue with the migration or first fix the issues.


> ### Note:  
> Once the actual migration process has been initiated, the platform is suspended, and you can’t create, update, or delete its service instances and service bindings.
> 
> The process is reversible for as long as the actual migration of the resources doesn’t start \(described below in the part 3 of the migration script example\).
> 
> To cancel the migration, execute the following command:
> 
> ```
> smctl curl -X DELETE -d '{"sourcePlatformID": ":platformID"}' /v1/migrate/service_operator/:instanceID
> ```



<a name="loioec7f5c7703db466e8f234f1cd362cbfc__section_ucx_q2k_wqb"/>

## Migration Script Example

1.  The script first scans all service instances and service bindings that are managed in your cluster by Kubernetes Service Catalog \(svcat\), and verifies whether they’re also maintained in SAP BTP.

    Migration isn't performed on those instances and bindings that aren't found in SAP BTP.

    ```
    migrate run
      
      *** Fetched 2 instances from SM
      *** Fetched 1 bindings from SM
      *** Fetched 5 svcat instances from cluster
      *** Fetched 2 svcat bindings from cluster
      *** Preparing resources
      
      svcat instance name 'some_instance_name_1' id 'XXX-6134-4c89-bff5-YYY' (some_instance_name_1) not found in SM, skipping it...
      svcat instance name 'some_instance_name_2' id 'XXX-cae6-4e23-9e8a-YYY' (some_instance_name_2) not found in SM, skipping it...
      svcat instance name 'some_instance_name_3' id 'XXX-dc1d-49d1-86c0-YYY' (some_instance_name_3) not found in SM, skipping it...
      svcat binding name 'some_binding_name_1' id 'XXX-5226-42cc-81e5-YYY' (some_binding_name_1) not found in SM, skipping it...
      
      *** found 2 instances and 1 bindings to migrate 
    ```

2.  Before the actual migration starts, the script also validates whether all resources are migratable.

    > ### Note:  
    > If there’s an issue with one or more resources, the process stops.

    ```
    svcat instance 'some_instance_name_4' in namespace 'namespace_name' was validated successfully
            svcat instance 'some_instance_name_5' in namespace 'namespace_name' was validated successfully
            svcat binding 'some_binding_name_2' in namespace 'namespace_name' was validated successfully
      
            *** Validation completed successfully
    
    ```

3.  After all resources were validated successfully, the actual migration starts.

    Each service instance and binding is removed from the Service Catalog and added to the SAP BTP service operator:

    ```
    migrating service instance 'some_instance_name_4' in namespace 'namespace_name' (smID: 'XXX-3d1f-40db-8cac-YYY')
            deleting svcat resource type 'serviceinstances' named 'some_instance_name_4' in namespace 'namespace_name'
            migrating service instance 'some_instance_name_5' in namespace 'namespace_name' (smID: 'XXX-0f94-4fde-b524-YYY')
            deleting svcat resource type 'serviceinstances' named 'some_instance_name_5' in namespace 'namespace_name'
            migrating service binding 'some_binding_name_2' in namespace 'namespace_name' (smID: 'XXX-fc36-4d50-a925-YYY')
            deleting svcat resource type 'servicebindings' named 'some_binding_name_2' in namespace 'namespace_name'
      
      *** Migration completed successfully
    
    ```


> ### Note:  
> Once the migration process has been completed, the Kubernetes platform, based on the Kubernetes Service Catalog \(svcat\) and SAP Service Manager agent is no longer usable.

