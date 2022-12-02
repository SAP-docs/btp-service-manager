<!-- loioae1e34b33f3242c0a81f88d39cd6b38e -->

# list services/platform



<a name="loioae1e34b33f3242c0a81f88d39cd6b38e__section_xcr_2nt_pkb"/>

## Overview



***btp list services/platform*** 

List all platforms in a subaccount that are registered for service consumption.



<a name="loioae1e34b33f3242c0a81f88d39cd6b38e__section_fp5_f4t_pkb"/>

## Usage

`btp list services/platform [parameters]`



<a name="loioae1e34b33f3242c0a81f88d39cd6b38e__section_hdy_lpt_pkb"/>

## Parameters


<table>
<tr>
<th valign="top" colspan="2">

Required



</th>
</tr>
<tr>
<td valign="top">

`-sa`, `--subaccount`



</td>
<td valign="top">

Subaccount ID. To find your subaccount ID, use `btp list accounts/subaccount` or you can omit this parameter if you have already set the context to a subaccount using `btp list target --subaccount ID`.



</td>
</tr>
</table>


<table>
<tr>
<th valign="top" colspan="2">

Optional



</th>
</tr>
<tr>
<td valign="top">

`-h`, `--help`



</td>
<td valign="top">

Help for `btp list services/platform` command.



</td>
</tr>
<tr>
<td valign="top">

`--labels-filter`



</td>
<td valign="top">

Filters the service brokers based on the label query. Only items that have label values matching the provided label query will be returned.



</td>
</tr>
<tr>
<td valign="top">

`--fields-filter`



</td>
<td valign="top">

Filters the service brokers based on the field query. Only items that have field values matching the provided field query will be returned.



</td>
</tr>
</table>



<a name="loioae1e34b33f3242c0a81f88d39cd6b38e__section_wv2_4pt_pkb"/>

## Example

```
> btp list services/platform

id            name                        description broker_url   created_at                     updated_at                    labels    
my-broker-id  my-platformplatform-name    my-platformplatform-url  2020-02-27T16:04:47.810739Z    2020-02-27T16:04:47.810739Z   subaccount_id = my-subaacount-id

OK

```

