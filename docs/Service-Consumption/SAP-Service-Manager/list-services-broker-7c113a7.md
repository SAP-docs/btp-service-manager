<!-- loio7c113a784f6542dbb7dd06975b69eef9 -->

# list services/broker



<a name="loio7c113a784f6542dbb7dd06975b69eef9__section_xcr_2nt_pkb"/>

## Overview



***btp list services/broker*** 

Lists all service brokers registered in the subaccount.



<a name="loio7c113a784f6542dbb7dd06975b69eef9__section_fp5_f4t_pkb"/>

## Usage

`btp list services/broker [parameters]`



<a name="loio7c113a784f6542dbb7dd06975b69eef9__section_hdy_lpt_pkb"/>

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

Subaccount ID. To find your subaccount ID, use `btp list accounts/subaccount` or you can omit this parameter if you have already set the context to a subaccount using `btp target --subaccount ID`.



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

Help for `list services/broker` command.



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



<a name="loio7c113a784f6542dbb7dd06975b69eef9__section_wv2_4pt_pkb"/>

## Example

```
> btp list services/broker
id            name              description broker_url   created_at                     updated_at                    labels    
my-broker-id  my-broker-name    my-broker-url            2020-02-27T16:04:47.810739Z    2020-02-27T16:04:47.810739Z   subaccount_id = my-subaacount-id

OK

```

