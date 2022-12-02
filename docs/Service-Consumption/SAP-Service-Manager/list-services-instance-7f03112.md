<!-- loio7f03112dff9a4e7d91f57225763f35f7 -->

# list services/instance



<a name="loio7f03112dff9a4e7d91f57225763f35f7__section_xcr_2nt_pkb"/>

## Overview



***btp list services/instance*** 

List all service instances in a subaccount.



<a name="loio7f03112dff9a4e7d91f57225763f35f7__section_fp5_f4t_pkb"/>

## Usage

`btp list services/instance [parameters]`



<a name="loio7f03112dff9a4e7d91f57225763f35f7__section_hdy_lpt_pkb"/>

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

The ID of the subaccount for which to list service instances. You can omit this parameter if you have already set the context to the subaccount using `btp target --subaccount ID`.



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

`--labels-filter`



</td>
<td valign="top">

Filters the instances based on the label query. For example, to list all instances that are available in a production landscape, use `landscape eq 'production'`.

For the full list of the available query options, see [Filtering Parameters and Operators](filtering-parameters-and-operators-3331c6e.md).



</td>
</tr>
<tr>
<td valign="top">

`--fields-filter`



</td>
<td valign="top">

Filters the instances based on their fields. You can filter for all fields that are displayed with the 'list services/instance' command. For example, to list all instances that are usable, use `usable eq 'true'`.

For the full list of the available query options, see [Filtering Parameters and Operators](filtering-parameters-and-operators-3331c6e.md).



</td>
</tr>
</table>

