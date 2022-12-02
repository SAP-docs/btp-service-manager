<!-- loio308dd03732d541efbd8bc592b4356c17 -->

# list services/binding



<a name="loio308dd03732d541efbd8bc592b4356c17__section_xcr_2nt_pkb"/>

## Overview



***btp list services/binding*** 

List all service bindings in a subaccount.



<a name="loio308dd03732d541efbd8bc592b4356c17__section_fp5_f4t_pkb"/>

## Usage

`btp list services/binding [parameters]`



<a name="loio308dd03732d541efbd8bc592b4356c17__section_hdy_lpt_pkb"/>

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

The ID of the subaccount in which to view bindings. You can omit this parameter if you have already set the context to the subaccount using `btp target --subaccount ID`.



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

Filters the service binding based on the label query. For example, to list all service bindings that are used for 'backing services', use `purpose eq 'backing services'`.

For the full list of the available query options, see [Filtering Parameters and Operators](filtering-parameters-and-operators-3331c6e.md).



</td>
</tr>
<tr>
<td valign="top">

`--fields-filter`



</td>
<td valign="top">

Filters the service bindings based on the field query. You can filter for all fields that are displayed in the 'list services/binding' command.

For example, to list all the service bindings that are ready to be used, use `ready eq 'true'`.

For the full list of the available query options, see [Filtering Parameters and Operators](filtering-parameters-and-operators-3331c6e.md).



</td>
</tr>
</table>

