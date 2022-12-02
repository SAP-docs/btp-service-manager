<!-- loio0ccebd7cec24411dacd5ad17799534e0 -->

# Working with SAP BTP Service Operator

Use the SAP BTP service operator to consume SAP BTP services from your Kubernetes cluster.



<a name="loio0ccebd7cec24411dacd5ad17799534e0__section_mtm_kc1_t4b"/>

## Context

To consume an SAP SAP BTP service, you create an instance of that service, and then you create a binding so that your Kubernetes-native applications can get access credentials to the instance you created.



<a name="loio0ccebd7cec24411dacd5ad17799534e0__section_txy_tc1_t4b"/>

## Procedure



### Creating a Service Instance

1.  Create a `ServiceInstance` custom resource file with the following structure:

    ```
    apiVersion: services.cloud.sap.com/v1alpha1
        kind: ServiceInstance
        metadata:
            name: my-service-instance
        spec:
            serviceOfferingName: <offering>
            servicePlanName: <plan>
            externalName: my-service-instance-external
            parameters:
              key1: val1
              key2: val2
    ```

    where:

    -   *<offering\>* is the name of the SAP BTP service whose instance you're creating. To learn more about viewing and managing the available services for your subaccount in the SAP BTP cockpit, see [View and Manage Services from the Service Marketplace](../SAP-Service-Manager/view-and-manage-services-from-the-service-marketplace-affcc24.md).
    -   *<plan\>* is the plan of the selected service offering for which you're creating an instance.

2.  Apply the custom resource file from step 1 in your cluster by running the following command:

    ```
    kubectl apply -f path/to/my-service-instance.yaml
    ```

3.  Check that the status of the service instance in your cluster is `Created` by running the following command:

    ```
    kubectl get serviceinstances
    NAME                  STATUS   AGE
    my-service-instance   Created  19s
    ```




### Creating a Service Binding

1.  Create a `ServiceBinding` custom resource file and set the `serviceInstanceName` field value to the name of the `ServiceInstance` custom resource file you created in the first section:

    ```
    apiVersion: services.cloud.sap.com/v1alpha1
    kind: ServiceBinding
    metadata:
        name: my-binding
    spec:
        serviceInstanceName: my-service-instance
    ```

2.  Apply the custom resource file from step 1 in your cluster by running the following cubectl command:

    ```
    kubectl apply -f path/to/my-binding.yaml
    ```

3.  Check that the status of the service binding in your cluster is `Created` by running the following command:

    ```
    kubectl get servicebindings
    NAME         INSTANCE              STATUS    AGE
    my-binding   my-service-instance   Created   16
    ```

4.  Check that a secret with the same name as the name of your binding is created.

    The secret contains credentials applications in your cluster can use to access the service instance:

    ```
    kubectl get secrets
    NAME         TYPE     DATA   AGE
    my-binding   Opaque   5      32s
    ```


For more information about how to use the generated credentials from your applications in Kubernetes cluster, see [Using Secrets](https://kubernetes.io/docs/concepts/configuration/secret/#using-secrets).

