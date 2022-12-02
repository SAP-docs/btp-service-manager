<!-- loio2c37d0cd9b394422a7e8b97b96bf4f44 -->

# Service Plans

Service plans represent sets of capabilities provided by a service offering.



For example, database service offerings provide different plans for different database versions or sizes, while the SAP Service Manager plans offer different data access levels.

**Base URI:** <code>https://service-manager.cfapps.<i class="varname">&lt;landscape domain&gt;</i>/v1/service_plans</code>



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

`/v1/service_plans`



</td>
<td valign="top">

`Get all service plans`

> ### Recommendation:  
> See [Filtering Parameters and Operators](filtering-parameters-and-operators-3331c6e.md) to learn about all the filtering options available when calling this API.



</td>
</tr>
<tr>
<td valign="top">

*GET*



</td>
<td valign="top">

<code>/v1/service_plans/<code>{servicePlanID}</code></code>



</td>
<td valign="top">

`Get a service plan`



</td>
</tr>
</table>

