<!-- loio3331c6e075fa40039af2714965191b6e -->

# Filtering Parameters and Operators

Use various combinations of filtering parameters to optimize the results of the Get all API calls of the SAP Service Manager service resources APIs.



The resources to which these parameters apply are: platforms, service brokers, service instances, service bindings, service plans, and service offerings.

Check the SAP Service Manager API section of [SAP Business Accelerator Hub](https://api.sap.com/api/APIServiceManager/overview) for more details about the Get all APIs for each of the resources.



<a name="loio3331c6e075fa40039af2714965191b6e__section_ymc_jbh_plb"/>

## Context

There are two types of filtering based on resource fields and labels.

You can control filtering with the following query parameters:


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

`fieldQuery`

</td>
<td valign="top">

string

</td>
<td valign="top">

Returns the items that have field values that match the provided field query.

Must be a nonempty string.

> ### Example:  
> `type eq 'kubernetes'`



</td>
</tr>
<tr>
<td valign="top">

`labelQuery`

</td>
<td valign="top">

string

</td>
<td valign="top">

Returns the items that have label values that match the provided label query.

Must be a nonempty string.

> ### Example:  

`environment eq 'dev'`

</td>
</tr>
</table>

Field and label values that are used to filter the SAP Service Manager resources in API calls are called literals.

The SAP Service Manager APIs support the following types of literals:

-   string

-   boolean

-   integer

-   date-time




<a name="loio3331c6e075fa40039af2714965191b6e__section_pqh_nwv_plb"/>

## Filter Syntax and Rules

-   String literals must be enclosed in single quotes \(`'`\). SAP Service Manager reads a single quote as the start or the end of the string. If the text itself contains a single quote, replace it with two single quotes \(`''`\). Two single quotes in a row tell SAP Service Manager that the quote is part of the text.

    For example:

    `type ne 'cloud foundry'`

    To search for a text that contains a single quote, build the string like this:


    <table>
    <tr>
    <th valign="top">

    Step
    
    </th>
    <th valign="top">

    Result
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Text to search for
    
    </td>
    <td valign="top">
    
    `Finance department's cluster`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Replace the single quote inside the text with two single quotes
    
    </td>
    <td valign="top">
    
    `Finance department''s cluster`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Enclose the text in single quotes
    
    </td>
    <td valign="top">
    
    `'Finance department''s cluster'`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Complete query
    
    </td>
    <td valign="top">
    
    `description eq 'Finance department''s cluster'`
    
    </td>
    </tr>
    </table>
    
-   Boolean literals can't be enclosed in quotes.

-   Literals can't be enclosed in brackets.

-   Integer literals can only consist of digits with one optional leading `+` or `-` sign.

-   Date-time literals must follow ISO 8601 format, and can't be enclosed in quotes.

    The supported ISO 8601 format is `yyyy-mm-ddThh:mm:ss.s[Z|(+|-)hh:mm]`




<a name="loio3331c6e075fa40039af2714965191b6e__section_kq2_pzv_plb"/>

## Supported Query Operators

The table shows all the supported operators that you can use to filter the results of your API calls.


<table>
<tr>
<th valign="top">

Operator

</th>
<th valign="top">

Field Query

</th>
<th valign="top">

Label Query

</th>
</tr>
<tr>
<td valign="top">

`eq`

\(equal\)

</td>
<td valign="top">

Evaluates to true if the field value matches the literal. False otherwise.

</td>
<td valign="top">

Evaluates to true if the label exists and one label value matches the literal. False otherwise.

</td>
</tr>
<tr>
<td valign="top">

`en`

\(equal or null\)

</td>
<td valign="top">

Evaluates to true if the field value matches the literal or if the field value is `null`. False otherwise.

</td>
<td valign="top">

Evaluates to true if the label exists and one label value matches the literal, or if the label doesn't exist. False otherwise.

</td>
</tr>
<tr>
<td valign="top">

`ne`

\(not equal\)

</td>
<td valign="top">

Evaluates to true if the field value doesn’t match the literal. False otherwise.

</td>
<td valign="top">

Evaluates to true if the label exists and no label value matches the literal. False otherwise.

</td>
</tr>
<tr>
<td valign="top">

`in`

</td>
<td valign="top">

Evaluates to true if the field value matches at least one value in the list of literals. False otherwise.

</td>
<td valign="top">

Evaluates to true if the label exists and the label value matches at least one value in the list of literals. False otherwise.

</td>
</tr>
<tr>
<td valign="top">

`notin`

</td>
<td valign="top">

Evaluates to true if the field value doesn’t match any value in the list of literals. False otherwise.

</td>
<td valign="top">

Evaluates to true if the label exists and no label value matches any value in the list of literals. False otherwise.

</td>
</tr>
<tr>
<td valign="top">

`and`

</td>
<td valign="top">

Evaluates to true if both the left and right operands evaluate to true. False otherwise.

</td>
<td valign="top">

Evaluates to true if both the left and right operands evaluate to true. False otherwise.

</td>
</tr>
<tr>
<td valign="top">

`contains`

</td>
<td valign="top">

Evaluates to true if the literal is part of the field value. False otherwise.

</td>
<td valign="top">

Evaluates to true if the literal is part of the label value. False otherwise.

</td>
</tr>
</table>

The following operators apply only to the field query:


<table>
<tr>
<th valign="top">

Operator

</th>
<th valign="top">

Field Query

</th>
</tr>
<tr>
<td valign="top">

`gt`

</td>
<td valign="top">

Evaluates to true if the field value is greater than the literal. False otherwise.

</td>
</tr>
<tr>
<td valign="top">

`ge`

</td>
<td valign="top">

Evaluates to true if the field value is greater than, or equal to the literal. False otherwise.

</td>
</tr>
<tr>
<td valign="top">

`lt`

</td>
<td valign="top">

Evaluates to true if the field value is less than the literal. False otherwise.

</td>
</tr>
<tr>
<td valign="top">

`le`

</td>
<td valign="top">

Evaluates to true if the field value is less than, or equal to the literal. False otherwise.

</td>
</tr>
</table>

> ### Note:  
> Label and field queries can be combined. The returned lists only contain entries that match both queries.



<a name="loio3331c6e075fa40039af2714965191b6e__section_xxl_lbw_plb"/>

## Query Task Examples



### Field Query

In a field query, you can filter a resource only by its own fields. To filter by a related resource, get its ID first, in this order: service broker, service offering, service plan, service instance, service binding.

-   List all service instances with a service plan ID that equals `bvsded31-c303-123a-aab9-8crar19e1218`.

    ```
    service_plan_id eq 'bvsded31-c303-123a-aab9-8crar19e1218'
    ```

-   List all bindings that use the `small` or `medium` plan of the `mysql` service provided by the broker with the ID `f85bcbd3-6c8b-43f0-a019-7f0a1ec5dba4`.

    A binding has no broker, service, or plan fields, so run four queries in sequence. In each step, use all IDs returned by the previous step.

    > ### Note:  
    > If a response contains a token, the list continues on another page. Repeat the same request with the `token` parameter until the response contains no token, and collect the IDs from all pages. If a step returns no items, stop. There are no matching bindings.

    1.  Get the `mysql` service offerings of the broker \(`GET /v1/service_offerings`\).

        ```
        broker_id eq 'f85bcbd3-6c8b-43f0-a019-7f0a1ec5dba4' and name eq 'mysql'
        ```

    2.  Get the `small` and `medium` plans of these offerings \(`GET /v1/service_plans`\).

        ```
        service_offering_id in ('<offering ID 1>', '<offering ID 2>') and name in ('small', 'medium')
        ```

    3.  Get the service instances of these plans \(`GET /v1/service_instances`\).

        ```
        service_plan_id in ('<plan ID 1>', '<plan ID 2>')
        ```

    4.  Get the bindings of these service instances \(`GET /v1/service_bindings`\).

        ```
        service_instance_id in ('<instance ID 1>', '<instance ID 2>')
        ```


-   List all usable service instances that are managed by SAP Service Manager.

    ```
    platform_id eq 'service-manager' and usable eq true
    ```




### Label Query

-   List all service instances with a `context_id` label that has a value `ad8cddb0-4679-43bf-89bc-357e9a638f30`.

    ```
    context_id eq 'ad8cddb0-4679-43bf-89bc-357e9a638f30'
    ```




### Combined Field and Label Queries

-   List all `kubernetes` platforms whose `purpose` is `dev`.

    > ### Note:  
    > The following code samples are field and label queries respectively.

    ```
    type eq 'kubernetes'
    ```

    ```
    purpose eq 'dev'
    ```


