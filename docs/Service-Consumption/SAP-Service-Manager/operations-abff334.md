<!-- loioabff3346c64e471cad7f5f0a11b65818 -->

# Operations



Check the status of the asynchronous operation you created after the POST, DELETE, or PATCH calls of the Service Instances and Service Bindings API groups.

The APIs of those groups provide a Boolean `async`request parameter whose default value is TRUE.

Use that parameter to generate an asynchronous operation, if needed.

In the *Location* response headers of the APIs, you get the path parameters that are required for this API.



<a name="loioabff3346c64e471cad7f5f0a11b65818__section_qyk_gmf_nlb"/>

## Methods


<table>
<tr>
<th valign="top">

HTTP Method



</th>
<th valign="top">

Action



</th>
<th valign="top">

URI



</th>
</tr>
<tr>
<td valign="top">

*GET*



</td>
<td valign="top">

[Get Operation Status](get-operation-status-3b330bb.md)



</td>
<td valign="top">

<code>/v1/<code>{resourceType}</code>/<code>{resourceID}</code>/operations/<code>{operationID}</code></code>



</td>
</tr>
</table>

-   **[Get Operation Status](get-operation-status-3b330bb.md "Check the status of the asynchronous operation.")**  
Check the status of the asynchronous operation.

