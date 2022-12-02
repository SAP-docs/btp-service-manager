<!-- loio989769ed476748a4b21b467e8f964183 -->

# get services/binding

View details of a specific service binding, such as its access details. They are included in its ‘credentials’ property, and typically include access URLs and credentials.



<a name="loio989769ed476748a4b21b467e8f964183__section_xcr_2nt_pkb"/>

## Overview



***btp get services/binding*** 



<a name="loio989769ed476748a4b21b467e8f964183__section_fp5_f4t_pkb"/>

## Usage

`btp get services/binding [parameters]`



<a name="loio989769ed476748a4b21b467e8f964183__section_hdy_lpt_pkb"/>

## Parameters


<table>
<tr>
<th valign="top" colspan="2">

Required



</th>
</tr>
<tr>
<td valign="top">

`ID`



</td>
<td valign="top">

The ID of the service binding to view.



</td>
</tr>
<tr>
<td valign="top">

`-sa`, `--subaccount`



</td>
<td valign="top">

The ID of the subaccount in which to view the binding. You can omit this parameter if you have already set the context to the subaccount using `btp target --subaccount ID`.



</td>
</tr>
<tr>
<td valign="top">

`--show-parameters`



</td>
<td valign="top">

Shows the configuration parameters of the service binding.



</td>
</tr>
</table>

