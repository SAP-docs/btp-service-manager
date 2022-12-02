<!-- loio90f0856f6c0748138422082841aae553 -->

# Platforms

 



Platforms are Open Service Broker API-enabled software systems on which applications and services are hosted.

With SAP Service Manager, you can register your platform and enable it to consume the SAP Business Technology Platform services from your native environment.

This registration results in a returned set of credentials that are needed to deploy the SAP Service Manager agent.

SAP Service Manager currently supports the Kubernetes platform.

See [Consuming SAP BTP Services in Kubernetes with SAP Service Manager Broker Proxy \(Service Catalog\)](../Consuming-SAP-BTP-Services-from-Various-Environments/consuming-sap-btp-services-in-kubernetes-20195bf.md).

**Base URI:** <code>https://service-manager.cfapps.<i class="varname">&lt;landscape domain&gt;</i>/v1/platforms</code>



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

`/v1/platforms`



</td>
<td valign="top">

`Get all platforms`

> ### Recommendation:  
> See [Filtering Parameters and Operators](filtering-parameters-and-operators-3331c6e.md) to learn about all the filtering options available when calling this API.



</td>
</tr>
<tr>
<td valign="top">

*POST*



</td>
<td valign="top">

`​/v1​/platforms`



</td>
<td valign="top">

`Register a platform`



</td>
</tr>
<tr>
<td valign="top">

*GET*



</td>
<td valign="top">

<code>/v1/platforms/<code>{platformID}</code></code>



</td>
<td valign="top">

`Get platform details`



</td>
</tr>
<tr>
<td valign="top">

*DELETE*



</td>
<td valign="top">

<code>/v1/platforms/<code>{platformID}</code></code>



</td>
<td valign="top">

`Unregister a platform`



</td>
</tr>
<tr>
<td valign="top">

*PATCH*



</td>
<td valign="top">

<code>/v1/platforms/<code>{platformID}</code></code>



</td>
<td valign="top">

`Update a platform`



</td>
</tr>
</table>

