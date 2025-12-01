<!-- loio97be6794829a441f99c9da04532a3c2b -->

# Rate Limiting

Describes how all API requests to the SAP Service Manager adhere to rate-limiting rules.



<a name="loio97be6794829a441f99c9da04532a3c2b__section_hjm_nqf_jvb"/>

## About API Rate Limiting

API rate limiting is, in a nutshell, limiting people \(and bots\) from accessing the API based on the rules set by the API’s operator or owner.

API rate limiting can be used as a defensive security measure for the API, and also a quality control method. As a shared service, the API must protect itself from excessive use to encourage an optimal experience for anyone using the API. Quality-wise, as all APIs operate on finite resources, rate limiting is essential to improve the availability of API service for many users as possible by avoiding excessive resource usages.

All APIs define their own custom rate-limit rules for the number of requests per time window and per identified caller.

API callers are identified through the authenticated requests associated with the username on the authenticated platform or with the OAuth client ID.

When the rate limit is exceeded, the client receives the *HTTP 429 Too Many Requests* response status code.



<a name="loio97be6794829a441f99c9da04532a3c2b__section_osd_rqf_jvb"/>

## Service Manager APIs

The Service Manager works with the following resources: platforms, service brokers, service bindings, service offerings, service plans, and service instances.

There's a dedicated group of APIs for each of the SAP Service Manager resources.

The total number of requests that you can perform for all SAP Service Manager APIs together is 10,000 calls per hour and 1000 per minute.

While the same rate-limiting rule per hour and minute applies to all platform and service broker APIs, as well as all available GET APIs for the service instances group, different, and more restrictive rules apply to other Service Manager resource API groups. Refer to the details in the table below.

> ### Remember:  
> All API calls executed in the same time frame \(minute and hour\) **count together** towards rate limits. See the examples below the table for more details.


<table>
<tr>
<th valign="top">

API Endpoint



</th>
<th valign="top">

Maximum Number of Calls per Timeframe



</th>
</tr>
<tr>
<td valign="top">

`/v1/service_bindings`



</td>
<td valign="top">

-   Hour: 6000
-   Minute: 600



</td>
</tr>
<tr>
<td valign="top">

`/v1/service_offerings`



</td>
<td valign="top">

-   Hour: 1000
-   Minute: 100



</td>
</tr>
<tr>
<td valign="top">

`/v1/service_plans`



</td>
<td valign="top">

-   Hour: 1000
-   Minute: 100



</td>
</tr>
<tr>
<td valign="top">

`/v1/service_instances`



</td>
<td valign="top">

-   Hour: 6000
-   Minute: 600

> ### Note:  
> `CREATE /v1/service_instances` is limited to 50 calls per minute.



</td>
</tr>
</table>

> ### Example:  
> -   You've called one of the `/v1/service_offerings` APIs 100 times within a minute. If you try to call any of the APIs in that same resource group again, you get the HTTP 429 response code. However, you can still call any of the `/v1/service_bindings` APIs up to 500 times within that same minute because their per-minute limit is 600 and you've already used 100 of them on another API resource group in that minute.
> 
> -   Let's say you've now used up all of the remaining 500 API calls for `/v1/service_bindings` APIs for that minute. If you try to call any of the APIs in that same resource group again within the same minute, you get the HTTP 429 response code. However, you still have up to 400 available API calls for any of the resource groups to which the 1000-per-minute rule applies because 1000-600 \(used calls\) = 400.
> 
> -   If you used all available 1000 API calls in that minute, for the same hour you still have up to: 10,000 available API calls for the hour - 1000 used API calls = 9000 API calls.



<a name="loio97be6794829a441f99c9da04532a3c2b__section_zbv_2cm_53b"/>

## Response

The error you receive after calling one of the `/v1/service_offerings` APIs 100 times within a minute and then one of the `/v1/service_bindings` 501 times within that same minute:

```
HTTP/1.1 429 Too Many Requests
{
  "description": "The allowed request limit of 600 responses has been reached. Please try again later.Check the 'Retry-After' header value to see how long you need to wait."
}

```

The example shows that there's also the `Retry-After` header value at your disposal. It indicates how long you need to wait before you can try again.

The `Retry-After` header value is in HTTP-date format:

`Date:<day-name>, <day> <month> <year> <hour>:<minute>:<second> GMT`

```
Retry-After
Sun, 06 Nov 1994 08:49:37 GMT

```

