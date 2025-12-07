<!-- loioe3403a43d5d640e4a2cf91654e3580c3 -->

<link rel="stylesheet" type="text/css" href="../../css/sap-icons.css"/>

# Sharing Instances Using Various SAP BTP Tools

Learn how to share service instances with different SAP BTP tools.

<a name="task_pcn_g5w_1cc"/>

<!-- task\_pcn\_g5w\_1cc -->

## SAP BTP Command Line Interface \(btp CLI\)



<a name="task_pcn_g5w_1cc__prereq_z4c_w5w_1cc"/>

## Prerequisites

Check if the plan for the service instance you want to share supports the instance-sharing feature. To do so, run the following command:

```
btp list services/plan
```

See [List Service Plans](https://help.sap.com/docs/BTP/btp-cli/btp-list-services-plan.html?locale=en-US&state=PRODUCTION&version=Cloud).

In the response, look for the `shareable` Boolean value. If it is set to `true`, the plan supports instance sharing:

```
ID                 Name                 Shareable          Description
------------------     -------------------   ----------------   --------------------------
<service plan ID>      <service plan name>   true               <service plan description>
<service plan ID>      <service plan name>   false              <service plan description>

```

> ### Note:  
> Not all services offer plans that support this feature.



<a name="task_pcn_g5w_1cc__steps_mxv_y5w_1cc"/>

## Procedure

1.  Create a service instance:

    ```
    btp create services/instance --subaccount <ID> --name <NAME>
    ```

    See [Create a Service Instance](https://help.sap.com/docs/BTP/btp-cli/btp-create-services-instance.html?locale=en-US&state=PRODUCTION&version=Cloud).

    Response:

    ```
    id: <service instance id>
    ready: true
    name: <service instance name>
    service_plan_id: <service plan ID>
    platform_id: <identifier of the platform where the service instance was created>
    dashboard_url: <url to the service dashboard>
    usable: true
    created_at: <timestamp>
    updated_at: <timestamp>
     
    OK
    ```

2.  Share the service instance:

    ```
    btp share services/instance <ID> --subaccount <ID> --name <NAME>
    ```

    See [Share a Service Instance](https://help.sap.com/docs/BTP/btp-cli/btp-share-services-instance.html?locale=en-US&state=PRODUCTION&version=Cloud).

    Response:

    ```
    id: < service instance ID>
    ready: true
    shared: true
    name: <service instance name>
    service_plan_id: <service plan ID>
    platform_id: <identifier of the platform where the service instance was created>
    dashboard_url: <url to the service dashboard>
    usable: true
    created_at: <timestamp>
    updated_at: <timestamp>
     
    OK
    ```

    Sharing an instance adds a new `reference-instance` plan to the service. You will use this plan in the next step to create a new instance that references the shared instance.

3.  Create a new instance with the `reference-instance` plan:

    ```
    btp create service/instance --subaccount <ID> --name <NAME> --plan-name reference-instance --offering-name <offering name> --parameters '{\"referenced_instance_id\":\"ID\"}'
    ```

    > ### Note:  
    > To establish a reference to the shared instance, use either the ID of the shared instance or one or more of the available selectors. Provide this information using the `--parameters` option. In the example above, we used the shared instance ID. Refer to the following table for more details about the available reference pointers.


    <table>
    <tr>
    <th valign="top">

    Name
    
    </th>
    <th valign="top">

    Info
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    `referenced_instance_id`
    
    </td>
    <td valign="top">
    
    The ID of the shared instance. To find it, run:

    ```
    btp get services/instance --name NAME --subaccount <ID>
    ```

    > ### Note:  
    > When a shared instance is provisioned across multiple data centers, its ID alone is insufficient for unique identification. In such cases, references using only the ID will fail and result in an error message.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `instance_name_selector`
    
    </td>
    <td valign="top">
    
    Name of the shared instance. To find it, run:

    ```
    btp get services/instance <ID> --subaccount <ID>
    ```


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `plan_name_selector`
    
    </td>
    <td valign="top">
    
    Use the same command to find the name of the plan associated with the shared instance.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `instance_label_selector`
    
    </td>
    <td valign="top">
    
    Labels are added to the instance during its creation. They offer additional ways to describe and categorize it. To see the existing shared instance labels, add `--show-parameters` to the following command:

    ```
    btp get services/instance --name NAME --subaccount <ID> --show-parameters
    ```

    For more information about the command, see [Get a Service Instance](https://help.sap.com/docs/btp/btp-cli-command-reference/btp-get-services-instance).

    Use the `instance_label_selector` to identify the shared instance through a label query. For example:

    ```
    btp create service/instance --subaccount <ID> --name <NAME> --plan-name reference-instance --offering-name <offering name> --parameters '{\"referenced_instance_label\":\"environment eq dev\"}'
    ```

    For more information about labels and operators you can use with labels, see [Filtering Parameters and Operators](filtering-parameters-and-operators-3331c6e.md).

    > ### Note:  
    > Some services do not support showing instance labels. Check the service's documentation or contact support for more details.


    
    </td>
    </tr>
    </table>
    
4.  Create a service binding to obtain the credentials to access the instance created in step 1:

    ```
    btp create services/binding
    ```

    See [Create a Service Binding](https://help.sap.com/docs/btp/btp-cli-command-reference/btp-create-services-binding?locale=en-US&q=btp%20CLI%20command%20line%20reference).


<a name="task_qjc_hyw_1cc"/>

<!-- task\_qjc\_hyw\_1cc -->

## SAP BTP Cockpit



<a name="task_qjc_hyw_1cc__prereq_eq2_lyw_1cc"/>

## Prerequisites

Check if the plan for the service instance you want to share supports the instance-sharing feature. To do so, perform the following steps:

1.  Go to *Services → Service Marketplace*.

2.  Click on the tile of the service whose instance you want to share.

3.  Find the *Service Plans* section.

4.  Under *Description*, see whether the plan supports instance sharing.




<a name="task_qjc_hyw_1cc__steps_o5x_nyw_1cc"/>

## Procedure

1.  Select *Create* and follow the *New Instance or Subscription* wizard's steps to create an instance.

2.  Verify that the new instance was successfully created. You can do this by:

    1.  Navigating to the *Instances and Subscriptions* page.

    2.  Locating the instance under the *Service Instances* section.


3.  Share an instance by clicking on the *actions* icon \(<span class="SAP-icons-V5"></span>\) at the end of the instance row and selecting *Share* from the drop-down menu.

    Sharing an instance adds a new *reference-instance* plan to the service. You will use this plan in the next step to create a new instance that references the shared instance.

    > ### Note:  
    > If an instance was created with a plan that does not support sharing, the *Share* option will not appear in the drop-down menu.

4.  Create a new instance with the *reference-instance* plan. To do this, select *Create* and follow the *New Instance or Subscription* wizard's steps.

    > ### Note:  
    > In step 2 of the wizard, specify the shared instance to which your new instance should refer.
    > 
    > You can use either the ID of the shared instance, or one or more of the available selectors. Refer to the table below for more details:


    <table>
    <tr>
    <th valign="top">

    Name
    
    </th>
    <th valign="top">

    Info
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    `referenced_instance_id`
    
    </td>
    <td valign="top">
    
    The ID of the shared instance. Use the following procedure to see it:

    1.  Navigate to the *Instances and Subscriptions* page.

    2.  Locate the instance in the *Service Instances* section.
    3.  Select the instance row.
    4.  Locate the ID in the details section that opens.

    > ### Note:  
    > When a shared instance is provisioned across multiple data centers, its ID alone is insufficient for unique identification. In such cases, references using only the ID will fail and result in an error message.
    > 
    > Add one or more of the selectors to narrow-down your search to the specific shared instance.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `instance_name_selector`
    
    </td>
    <td valign="top">
    
    Use the same method as described in the table row above to find the shared instance name.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `plan_name_selector`
    
    </td>
    <td valign="top">
    
    Use the same method as described in the table row above to find the plan associated with the shared instance.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `instance_label_selector`
    
    </td>
    <td valign="top">
    
    Labels are added to the instance during its creation. They offer additional ways to describe and categorize it.

    You can find the existing shared instance labels under the dedicated *Labels* section in the service instance details. See *Info*for `referenced_instance_id` selector.

    Use the `instance_label_selector` to identify the shared instance through a label query.

    Apply it during the creation of the reference instance in step 2 of the *New Instance or Subscription* wizard.

    For more information about labels and operators you can use on labels, see [Filtering Parameters and Operators](filtering-parameters-and-operators-3331c6e.md).

    > ### Note:  
    > Some services do not support showing instance labels. Check the service's documentation or contact support for more details.


    
    </td>
    </tr>
    </table>
    
5.  Create a binding to obtain the access credentials for the shared instance.

    See [Service Bindings](service-bindings-bb8009d.md).


<a name="task_yry_422_bcc"/>

<!-- task\_yry\_422\_bcc -->

## Service Manager API



<a name="task_yry_422_bcc__prereq_b24_r22_bcc"/>

## Prerequisites

Check if the plan for the service instance you want to share supports the instance-sharing feature. To do so, call the `Get service plan details` API:

```
GET /v1/service_plans/{servicePlanID)
```

In the response, look for the `shareable` Boolean value. If it is set to `true`, the plan supports instance sharing:

```
{
  "id": "<service plan ID>",
  "ready": true,
  "name": "<service name>",
  "description": "<service plan description>",
  "catalog_id": "<service catalog ID>",
  "catalog_name": "<service catalog name>",
  "free": true,
  "bindable": true,
  "shareable": true
  "metadata": {
    "supportedPlatforms": [
      "<supported platforms for the service plan>"
    ],
    "supportedMinOSBVersion": "<version>",
    "supportedMaxOSBVersion": "<version>"
  },
  "service_offering_id": "<offering ID>",
  "created_at": "<timestamp>",
  "updated_at": "<timestamp>"
}
```

See [Get service plan details](https://api.sap.com/api/APIServiceManager/path/getServicePlansByServiceId)



<a name="task_yry_422_bcc__steps_u45_s22_bcc"/>

## Procedure

1.  Call the `Create a service instance` API:

    ```
    POST /v1/service_instances
    ```

    See [Create a service instance](https://api.sap.com/api/APIServiceManager/path/createServiceInstance).

2.  Share a service instance by updating the instance you created \(or an existing instance that you want to share, if its plan supports the sharing feature\). Call the `Update a service instance` API:

    ```
    PATCH /v1/service_instances/(serviceinstanceID}
    
    Request body structure:
    {
      "shared": true
    }
    ```

    > ### Note:  
    > When using the `shared` Boolean, you can't include any other parameters in the same API call to update an instance. This is because updating a shared instance is a unique scenario.

    See [Update a service instance](https://api.sap.com/api/APIServiceManager/path/updateServiceInstance).

    Sharing an instance adds a new `reference-instance` plan to the service. You will use this plan in the next step to create a new instance that references the shared instance.

3.  Create a new instance with the `reference-instance` plan.

    > ### Note:  
    > To establish a reference to the shared instance, use either the ID of the shared instance or one or more of the available selectors. Provide this information in the `labels` field of the `Create a service instance` API's request body. Refer to the following table for more details about the available reference pointers.


    <table>
    <tr>
    <th valign="top">

    Name
    
    </th>
    <th valign="top">

    Info
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    `referenced_instance_id`
    
    </td>
    <td valign="top">
    
    The ID of the shared instance. Find it by calling the `Get service instances` API. See [Get service instances](https://api.sap.com/api/APIServiceManager/path/getAllServiceInstances).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `instance_name_selector`
    
    </td>
    <td valign="top">
    
    Name of the shared instance. Find it by calling the `Get a service instance` API. See [Get a service instance](https://api.sap.com/api/APIServiceManager/path/getServiceInstanceById).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `plan_name_selector`
    
    </td>
    <td valign="top">
    
    Plan associated with the shared instance. Find it by calling the `Get a service instance` API. See [Get a service instance](https://api.sap.com/api/APIServiceManager/path/getServiceInstanceById).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `instance_label_selector`
    
    </td>
    <td valign="top">
    
    Labels are added to the instance during its creation. They offer additional ways to describe and categorize it.

    To see the existing shared instance labels, call the `Get a service instance` API and see the `Labels` section of the `ServiceInstanceResponseObject`.

    Use the `instance_label_selector` to identify the shared instance through a label query.

    For more information about labels and operators you can use on labels, see [Filtering Parameters and Operators](filtering-parameters-and-operators-3331c6e.md).

    > ### Note:  
    > Some services don't support showing instance labels. Check the service's documentation or contact support for more details


    
    </td>
    </tr>
    </table>
    
    The following example shows how the region label identifies a shared instance:

    ```
    POST /v1/service_instances
    
    Request body example:
    {
      "name": "my-reference-instance",
      "service_offering_name": "<name of the service offering>",
      "service_plan_name": "reference-instance",
      "parameters": {
        "referenced_instance_id": "<ID>",
      },
      "selectors": {
        "instance_label_selector": "region eq EU10"
      },
    }
    ```

4.  Create a service binding to obtain the credentials for accessing the shared instance. To do this, call the `Create a service binding` API:

    ```
    POST /v1/service_bindings
    ```

    In the binding, include the details of the shared instance.

    See [Create a service binding](https://api.sap.com/api/APIServiceManager/path/createServiceBinding).


<a name="task_jxk_5j2_bcc"/>

<!-- task\_jxk\_5j2\_bcc -->

## SAP BTP Service Operator



<a name="task_jxk_5j2_bcc__prereq_fr1_wj2_bcc"/>

## Prerequisites

To verify that the plan for the service instance you want to share supports the instance-sharing feature, use one of the following Service Manager tools: btp CLI, SAP BTP cockpit, or Service Manager API.



<a name="task_jxk_5j2_bcc__steps_pvc_zj2_bcc"/>

## Procedure

1.  Create a service instance by specifying a `ServiceInstance` custom resource file:

    ```
    apiVersion: services.cloud.sap.com/v1
        kind: ServiceInstance
        metadata:
            name: my-service-instance
        spec:
            serviceOfferingName: sample-service
            servicePlanName: sample-plan
            externalName: my-service-btp-name
            
    ```

2.  Share a service instance by updating the instance you created \(or an existing instance that you want to share, if its plan supports the sharing feature\) with the `shared` Boolean set to `true`:

    ```
    apiVersion: services.cloud.sap.com/v1
        kind: ServiceInstance
        metadata:
            name: my-service-instance
        spec:
            serviceOfferingName: sample-service
            servicePlanName: sample-plan
            shared: true
     
    ```

    Sharing an instance adds a new `reference-instance` plan to the service. You use this plan in the next step to create a new instance that references the shared instance.

3.  Create a new service instance by specifying a `ServiceInstance` custom resource file. In the file, use the `reference-instance` plan:

    ```
    apiVersion: services.cloud.sap.com/v1
        kind: ServiceInstance
        metadata:
            name: my-reference-service-instance
        spec:
            serviceOfferingName: sample-service
            servicePlanName: reference-instance
            externalName: my-service-btp-name
            parameters:
              referenced_instance_id: 'the ID of the shared instance'
            
    ```

    > ### Note:  
    > To establish a reference to the shared instance, use either the ID of the shared instance or one or more of the available selectors. Provide this information under the `parameters` field.. In the example above, we used the shared instance ID. Refer to the following table for more details about the available reference pointers.


    <table>
    <tr>
    <th valign="top">

    Name
    
    </th>
    <th valign="top">

    Info
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    `referenced_instance_id`
    
    </td>
    <td valign="top">
    
    The ID of the shared instance. To find it out, run:

    ```
    kubectl get serviceinstances <shared insance name> -o yaml
    ```

    > ### Note:  
    > When a shared instance is provisioned across multiple data centers, its ID alone is insufficient for unique identification. In such cases, references using only the ID will fail and result in an error message.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `instance_name_selector`
    
    </td>
    <td valign="top">
    
    The name of the shared instance. Find it by running:

    ```
    kubectl get serviceinstances <shared instance ID> -o yaml
    ```

    Use the name selector when creating a reference instance to point to the shared instance in the following way:

    ```
    apiVersion: services.cloud.sap.com/v1
    kind: ServiceInstance
    metadata:
      name: my-reference-instance2
    spec:
      serviceOfferingName: sample-service
      servicePlanName: reference-instance
      parameters:
        selectors:
          "instance_name_selector": 'my-service-instance'
    ```


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `plan_name_selector`
    
    </td>
    <td valign="top">
    
    The name of the plan with which the shared instance was created. Find it by running any of the commands mentioned in the table rows above.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `instance_label_selector`
    
    </td>
    <td valign="top">
    
    Labels added to the shared instance during its creation. Use the label selector to identify the shared instance through a label query. For example:

    ```
    apiVersion: services.cloud.sap.com/v1
    kind: ServiceInstance
    metadata:
      name: my-reference-instance2
    spec:
      serviceOfferingName: sample-service
      servicePlanName: reference-instance
      parameters:
        selectors:
          "instance_label_selector": 'environment eq dev'
    ```

    For more information about labels and operators you can use on labels, see [Filtering Parameters and Operators](filtering-parameters-and-operators-3331c6e.md).

    > ### Note:  
    > Each service defines its own instance labels. For details on the labels applicable to your service, refer to its documentation.


    
    </td>
    </tr>
    </table>
    
4.  Create a `ServiceBinding` custom resource to obtain credentials and make the service usable within the cluster. Set the `serviceInstanceName` field to the name of the `ServiceInstance` resource \(`my-service-instance` in our example\) that you've created.

    ```
    apiVersion: services.cloud.sap.com/v1
        kind: ServiceBinding
        metadata:
            name: my-binding
        spec:
           serviceInstanceName: my-service-instance
           externalName: my-binding-external
           secretName: my-secret
           parameters:
               key1: val1
               key2: val2   
    ```

    See [SAP BTP Service Operator](https://github.com/SAP/sap-btp-service-operator/blob/main/README.md) for more details about the steps.


