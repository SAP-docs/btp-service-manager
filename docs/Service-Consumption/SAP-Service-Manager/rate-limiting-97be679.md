<!-- loio97be6794829a441f99c9da04532a3c2b -->

# Rate Limiting

This topic describes how all API requests to SAP Service Manager adhere to rate-limiting rules.



<a name="loio97be6794829a441f99c9da04532a3c2b__section_hjm_nqf_jvb"/>

## About API Rate Limiting

API rate limiting restricts how often clients, whether users, services, or automated tools, can call the API. Rate limiting is both a security measure and a stability mechanism. It protects shared backend resources from excessive use and helps ensure consistent performance for all consumers.

Each API group in SAP Service Manager defines specific limits for the number of allowed requests per minute and per hour. The limit applies per authenticated identity \(username or OAuth client ID\). When a client exceeds the limit, SAP Service Manager returns an HTTP 429 Too Many Requests error.



<a name="loio97be6794829a441f99c9da04532a3c2b__section_osd_rqf_jvb"/>

## Service Manager APIs

SAP Service Manager hosts several API resource groups, such as:

-   Service Offerings
-   Service Plans
-   Service Instances
-   Service Bindings
-   Service Brokers
-   Platforms

The following limits apply:

**Global Limits**

These apply across all SAP Service Manager APIs combined:

-   1000 requests per minute
-   10,000 requests per hour

**Resource Group Limits**

Each resource group also has its own limits:


<table>
<tr>
<th valign="top">

API Endpoint

</th>
<th valign="top">

Maximum Calls per Hour

</th>
<th valign="top">

Maximum Calls per Minute

</th>
</tr>
<tr>
<td valign="top">

`/v1/service_bindings`

</td>
<td valign="top">

6000

</td>
<td valign="top">

600

</td>
</tr>
<tr>
<td valign="top">

`/v1/service_offerings`

</td>
<td valign="top">

1000

</td>
<td valign="top">

100

</td>
</tr>
<tr>
<td valign="top">

`/v1/service_plans`

</td>
<td valign="top">

1000

</td>
<td valign="top">

100

</td>
</tr>
<tr>
<td valign="top">

`/v1/service_instances`

</td>
<td valign="top">

6000

</td>
<td valign="top">

600

</td>
</tr>
</table>

**Special Limit for Creating Service Instances**

The following endpoint has an additional, more restrictive limit:

-   `POST /v1/service_instances` → 5 requests per minute


This limit applies even if the general limit for the resource group or the global limit has not been reached.

> ### Remember:  
> All API calls made within the same time frame \(per minute and per hour\) count toward the global limit, regardless of resource group.



<a name="loio97be6794829a441f99c9da04532a3c2b__section_kbx_qcv_3hc"/>

## Examples

-   **Exceeding a Resource-Group Limit**

    You call `/v1/service_offerings` exactly 100 times in one minute.

    This exhausts the 100-per-minute limit for that group.

    -   Any further call to `/v1/service_offerings` within that minute returns `HTTP 429`.

    -   However, you can still call `/v1/service_bindings` up to 600 times, as that group’s limit is independent.


-   **Exceeding the Special `CREATE` Limit**

    You issue 5 `POST /v1/service_instances` requests in the same minute.

    -   The 6th POST request in that minute returns `HTTP 429,`

        **even though**:

        -   The service-instances group limit \(600/min\) is not reached

        -   The global limit \(1000/min\) is not reached



    This is because the `CREATE` operation has its own dedicated 5-per-minute limit.

-   **Interaction with Global Limits**

    Suppose, within one minute, you have made:

    -   100 calls to`/v1/service_offerings`

    -   600 calls to `/v1/service_bindings`

    -   5 calls to `POST /v1/service_instances`


    Together these calls add up to 705 calls for that minute.

    -   Global remaining quota: 1000 − 705 = 295 calls.

    -   You may still call other APIs in other groups until the total reaches 1000 for that minute.

    -   When the 1000th call is made, further requests of *any* type return HTTP 429.





<a name="loio97be6794829a441f99c9da04532a3c2b__section_zbv_2cm_53b"/>

## Response

A client that exceeds a per-minute limit receives a response similar to:

```
HTTP/1.1 429 Too Many Requests
{
  "description": "The allowed request limit has been reached. Please try again later. Check the 'Retry-After' header to see how long you need to wait."
}

```

The response includes a `Retry-After`header indicating when you may resend your request:

```
Retry-After: Sun, 06 Nov 1994 08:49:37 GMT


```

