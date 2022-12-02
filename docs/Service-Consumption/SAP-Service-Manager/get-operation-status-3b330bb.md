<!-- loio3b330bbb98d649078f96a05121c7d241 -->

# Get Operation Status

Check the status of the asynchronous operation.



Check the status of the asynchronous operation you created after the POST, DELETE, or PATCH calls of the Service Instances and Service Bindings API groups.

In the *Location* response headers of those APIs, you get the path parameters that are required for this API.



<a name="loio3b330bbb98d649078f96a05121c7d241__section_x43_xck_2lb"/>

## Prerequisites

You have obtained an access token with the scope required for the operation for which you wish to get status.

For more information, see [Accessing the APIs](accessing-the-apis-93711c1.md).



<a name="loio3b330bbb98d649078f96a05121c7d241__section_nt4_ryj_mjb"/>

## Request

**URI:** <code>https://service-manager.cfapps.<i class="varname">&lt;landscape domain&gt;</i>/v1/<code>{resourceType}</code>/<code>{resourceID}</code>/operations/<code>{operationID}</code></code>

**HTTP Method:** *GET*



### Path Parameters


<table>
<tr>
<th valign="top">

Parameter Name



</th>
<th valign="top">

Required



</th>
<th valign="top">

Parameter Type



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

`resourceType`



</td>
<td valign="top">

Yes



</td>
<td valign="top">

String



</td>
<td valign="top">

The type of the SAP Service Manager resource associated with the asynchronous operation.

Values:

`platforms`

`service_brokers`

`service_bindings`

`service_instances`



</td>
</tr>
<tr>
<td valign="top">

`resourceID`



</td>
<td valign="top">

Yes



</td>
<td valign="top">

String



</td>
<td valign="top">

The ID of the resource entity for which to get asynchronous operation status.



</td>
</tr>
<tr>
<td valign="top">

`operationID`



</td>
<td valign="top">

Yes



</td>
<td valign="top">

String



</td>
<td valign="top">

The ID of the asynchronous operation for which to get status.



</td>
</tr>
</table>



<a name="loio3b330bbb98d649078f96a05121c7d241__section_bgz_3fk_mjb"/>

## Response

Returns details about the requested asynchronous operation, and its associated objects.

**Content Type:***JSON*



### Response Headers


<table>
<tr>
<th valign="top">

Header



</th>
<th valign="top">

Values



</th>
</tr>
<tr>
<td valign="top">

`content-type`



</td>
<td valign="top">

`application/json; charset=UTF-8`



</td>
</tr>
</table>



### Response Status and Error Codes


<table>
<tr>
<th valign="top">

Code



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

200



</td>
<td valign="top">

Found asynchronous operation \(OK\)



</td>
</tr>
<tr>
<td valign="top">

400



</td>
<td valign="top">

Bad Request



</td>
</tr>
<tr>
<td valign="top">

403



</td>
<td valign="top">

Forbidden



</td>
</tr>
<tr>
<td valign="top">

404



</td>
<td valign="top">

Asynchronous operation not found



</td>
</tr>
</table>



### Response Objects and Their Parameters



### `OperationResponseObject`

Contains details about the last operation, and transitive resources.


<table>
<tr>
<th valign="top">

Parameter Name



</th>
<th valign="top">

Parameter Type



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

`id`



</td>
<td valign="top">

String



</td>
<td valign="top">

The ID of the last operation.



</td>
</tr>
<tr>
<td valign="top">

`ready`



</td>
<td valign="top">

Boolean



</td>
<td valign="top">

Whether the resource is ready.



</td>
</tr>
<tr>
<td valign="top">

`type`



</td>
<td valign="top">

String



</td>
<td valign="top">

The type of the operation.

Possible values:

`CREATE`

`UPDATE`

`DELETE`



</td>
</tr>
<tr>
<td valign="top">

`state`



</td>
<td valign="top">

String



</td>
<td valign="top">

Possible values:

`in progress`

`succeeded`

`failed`

While `"state": "in progress"`, the platform continues polling.

When: `"state": "succeeded"` or `"state": "failed"` the platform stops polling.



</td>
</tr>
<tr>
<td valign="top">

`description`



</td>
<td valign="top">

String



</td>
<td valign="top">

Details about the operation for customer-facing UI.



</td>
</tr>
<tr>
<td valign="top">

`resource_id`



</td>
<td valign="top">

String



</td>
<td valign="top">

The ID of the resource.

Present when `"state": "succeeded"`, and after PATCH or DELETE requests.



</td>
</tr>
<tr>
<td valign="top">

`errors`



</td>
<td valign="top">

Array of JSON objects:

Error



</td>
<td valign="top">

The list of errors if the operation has failed.

Each `Error` object in the list contains two parameters:

`error`, which indicates the name of the error, and its `description`.



</td>
</tr>
<tr>
<td valign="top">

`labels`



</td>
<td valign="top">

JSON object:

`LabelsResponseObject`



</td>
<td valign="top">

Additional data associated with the last operation.

Can be an empty object.



</td>
</tr>
<tr>
<td valign="top">

`transitive_resources`



</td>
<td valign="top">

JSON object:

`TransitiveResourceObject`



</td>
<td valign="top">

Additional information about the transitive resource.

See the next table `TransitiveResourceObject` for its properties.



</td>
</tr>
</table>



### `TransitiveResourceObject`


<table>
<tr>
<th valign="top">

Parameter Name



</th>
<th valign="top">

Parameter Type



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

`id`



</td>
<td valign="top">

String



</td>
<td valign="top">

The ID of the resource.



</td>
</tr>
<tr>
<td valign="top">

`type`



</td>
<td valign="top">

String



</td>
<td valign="top">

The type of the resource.



</td>
</tr>
<tr>
<td valign="top">

`operation_type`



</td>
<td valign="top">

String



</td>
<td valign="top">

The type of the operation associated with the resource.



</td>
</tr>
<tr>
<td valign="top">

`criteria`



</td>
<td valign="top">

String



</td>
<td valign="top">

The minimum criteria required to use the resource in the context of the platform.



</td>
</tr>
<tr>
<td valign="top">

`resource_type`



</td>
<td valign="top">

String



</td>
<td valign="top">

The type of the resource associated with the last operation.



</td>
</tr>
<tr>
<td valign="top">

`platform_id`



</td>
<td valign="top">

String



</td>
<td valign="top">

The ID of the platform associated with the operation.



</td>
</tr>
<tr>
<td valign="top">

`correlation_id`



</td>
<td valign="top">

String



</td>
<td valign="top">

The correlation ID received from the request related to this operation.



</td>
</tr>
<tr>
<td valign="top">

`reschedule`



</td>
<td valign="top">

Boolean



</td>
<td valign="top">

Whether the operation has reached a checkpoint and can be tried again.



</td>
</tr>
<tr>
<td valign="top">

`deletion_scheduled`



</td>
<td valign="top">

String



</td>
<td valign="top">

The time the resource is scheduled for deletion.

In ISO 8601 format:

`YYYY-MM-DDThh:mm:ssTZD`



</td>
</tr>
<tr>
<td valign="top">

`created_at`



</td>
<td valign="top">

String



</td>
<td valign="top">

The time the operation started.

In ISO 8601 format:

`YYYY-MM-DDThh:mm:ssTZD`



</td>
</tr>
<tr>
<td valign="top">

`updated_at`



</td>
<td valign="top">

String



</td>
<td valign="top">

The last time the resource was updated.

In ISO 8601 format:

`YYYY-MM-DDThh:mm:ssTZD`

This field is mandatory if `"state": "succeeded"` or `"state": "failed"`.



</td>
</tr>
</table>



### Response Example

```
{
  "id": "dsdssd498da96-e5f3-4402-8",
  "ready": true,
  "type": "CREATE",
  "state": "in progress",
  "description": "string",
  "resource_id": "string",
  "transitive_resources": [
    {
      "id": "0aba8e41-5e69-44b1-974f-83100",
      "type": "string",
      "operation_type": "string",
      "criteria": "string"
    }
  ],
  "resource_type": "string",
  "platform_id": "string",
  "correlation_id": "string",
  "reschedule": true,
  "deletion_scheduled": "2020-04-10T22:28:05.215Z",
  "created_at": "2020-04-10T22:28:05.215Z",
  "updated_at": "2020-04-10T22:28:05.215Z",
  "errors": [
    {
      "error": "string",
      "description": "string"
    }
  ],
  "labels": {
    "label1": [
      "value1",
      "value2",
      "value3"
    ],
    "label2": [
      "value1",
      "value2",
      "value3"
    ]
  }
}
```

**Related Information**  


[Operations](operations-abff334.md)

