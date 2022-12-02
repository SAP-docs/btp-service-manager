<!-- loio392eb36119874831b5b2f577ed71c2e7 -->

# Service Bindings

Service bindings provide access details for an existing service instance.



The access details can be found in the service binding `credentials` property, and typically include access URLs and credentials.

**Base URI:** <code>https://service-manager.cfapps.<i class="varname">&lt;landscape domain&gt;</i>/v1/service_bindings</code>



## Methods


<table>
<tr>
<th valign="top">

HTTP Method



</th>
<th valign="top">

URI



</th>
<th valign="top">

Name



</th>
</tr>
<tr>
<td valign="top">

*GET*



</td>
<td valign="top">

`/v1​/service_bindings​`



</td>
<td valign="top">

`Get all service bindings`

> ### Recommendation:  
> See [Filtering Parameters and Operators](filtering-parameters-and-operators-3331c6e.md) to learn about all the filtering options available when calling this API.



</td>
</tr>
<tr>
<td valign="top">

*POST*



</td>
<td valign="top">

`/v1​/service_bindings​`



</td>
<td valign="top">

`Create a service binding`



</td>
</tr>
<tr>
<td valign="top">

*GET*



</td>
<td valign="top">

<code>/v1​/service_bindings​/<code>{serviceBindingID}</code></code>



</td>
<td valign="top">

`Get a service binding`



</td>
</tr>
<tr>
<td valign="top">

*DELETE*



</td>
<td valign="top">

<code>/v1​/service_bindings​/<code>{serviceBindingID}</code></code>



</td>
<td valign="top">

`Delete a service binding`



</td>
</tr>
</table>

