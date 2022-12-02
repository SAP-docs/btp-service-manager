<!-- loio3331c6e075fa40039af2714965191b6e -->

# Filtering Parameters and Operators

Use various combinations of filtering parameters to optimize the results of the Get all API calls of the SAP Service Manager service resources APIs.



The resources to which these parameters apply are: platforms, service brokers, service instances, service bindings, service plans, and service offerings.

Check the SAP Service Manager API section of [SAP API Business Hub](https://api.sap.com/api/APIServiceManagment/resource) for more details about the Get all APIs for each of the resources.



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

-   String literals must be enclosed in single quotes \(`''`\). Single quotes in strings must be encoded with another single quote \('`''`'\).

    For example:

    `type ne 'cloud foundry'`

    `description eq ''customized' kubernetes'`

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

-   List all service instances with a service plan ID that equals `bvsded31-c303-123a-aab9-8crar19e1218`.

    ```
    service_plan_id eq 'bvsded31-c303-123a-aab9-8crar19e1218'
    ```

-   List all bindings that use the `small` or `medium` plan of the `mysql` service provided by the broker with the ID `f85bcbd3-6c8b-43f0-a019-7f0a1ec5dba4`.

    ```
    broker_id eq 'f85bcbd3-6c8b-43f0-a019-7f0a1ec5dba4' and service_name eq 'mysql' and plan_name in ('small', 'medium')
    ```

-   List all service instances that aren’t of the `postgresql` service, that are managed by the SAP Service Manager, and that aren’t orphans.

    ```
    platform_id eq 'service-manager' and service_name ne 'postgresql' and orphan ne true
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


