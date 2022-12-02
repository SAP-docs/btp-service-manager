<!-- loio97be6794829a441f99c9da04532a3c2b -->

# Rate Limiting

Describes how all API requests to the SAP Service Manager service adhere to rate limiting rules.



<a name="loio97be6794829a441f99c9da04532a3c2b__section_hjm_nqf_jvb"/>

## Context

All APIs define their own custom rate limit rules for the number of requests per time window and per identified caller.

API callers are identified through the authenticated requests associated with the username on the authenticated platform or with the OAuth client ID.

When the rate limit is exceeded, the client receives the *HTTP 429 Too Many Requests* response status code.



<a name="loio97be6794829a441f99c9da04532a3c2b__section_osd_rqf_jvb"/>

## Service Manager and Rate Limiting

With the SAP Service Manager APIs, the rate-limiting rules are applied on the following three levels:

-   Total number of requests for all SAP Service Manager APIs.

    You can call 10 000 Service Manager APIs per hour and 1000 per minute.

-   Total number of requests for a specific SAP Service Manager resource API group:


    <table>
    <tr>
    <th valign="top">

    API Endpoint


    
    </th>
    <th valign="top">

    Maximum Number of Calls


    
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
    </table>
    
-   Total number of requests per SAP Service Manager API resource group and method:


    <table>
    <tr>
    <th valign="top">

    API Method and Endpoint


    
    </th>
    <th valign="top">

    Maximum Number of Calls


    
    </th>
    </tr>
    <tr>
    <td valign="top">

    `CREATE /v1/service_instances`


    
    </td>
    <td valign="top">

    -   Minute: 50


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    `UPDATE /v1/service_instances`


    
    </td>
    <td valign="top">

    -   Hour: 6000
    -   Minute: 600


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    `DELETE /v1/service_instances`


    
    </td>
    <td valign="top">

    -   Hour: 6000
    -   Minute: 600


    
    </td>
    </tr>
    </table>
    

> ### Note:  
> Rate-limiting mechanism works concurrently on all three levels.
> 
> For example, if you try to perform more than 50 Create Service Instance API requests in a minute, you will reach the rate limit for that specific endpoint, but you can still perform up to 950 requests to other Service Manager APIs.



<a name="loio97be6794829a441f99c9da04532a3c2b__section_zbv_2cm_53b"/>

## Response Example

If you called `GET /v1/service_bindings` 900 times in a minute, you will receive the following error:

```
HTTP/1.1 429 Too Many Requests
{
  "description": "The allowed request limit of 600 responses has been reached. Please try again later.Check the 'Retry-After' header value to see how long you need to wait."
}

```

The example shows that there is also the `Retry-After` header value at your disposal. It indicates how long you need to wait before you can try again.

Its value is in HTTP-date format:

`Date:<day-name>, <day> <month> <year> <hour>:<minute>:<second> GMT`

```
Retry-After
Sun, 06 Nov 1994 08:49:37 GMT

```

