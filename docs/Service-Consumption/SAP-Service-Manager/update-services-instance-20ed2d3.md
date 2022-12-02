<!-- loio20ed2d3a9698434391e289916fa86af0 -->

# update services/instance

Update an existing service instance.



`btp update services/instance` 



<a name="loio20ed2d3a9698434391e289916fa86af0__section_fp5_f4t_pkb"/>

## Usage

`btp update services/instance [parameters]`



<a name="loio20ed2d3a9698434391e289916fa86af0__section_hdy_lpt_pkb"/>

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

The ID of the subaccount in which to create the service instance. You can omit this parameter if you've already set the context to the subaccount using `btp target --subaccount ID`.



</td>
</tr>
<tr>
<td valign="top">

`-s`, `--service``-n`, `--name`



</td>
<td valign="top">

The name of the service instance to update.



</td>
</tr>
<tr>
<td valign="top">

`-id`



</td>
<td valign="top">

The ID of the service instance to update.



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

`--new-name`



</td>
<td valign="top">

The new name of the service instance.



</td>
</tr>
<tr>
<td valign="top">

`-p``--plan`



</td>
<td valign="top">

The ID of the new service plan to use for the service instance.



</td>
</tr>
<tr>
<td valign="top">

`--plan-name`



</td>
<td valign="top">

The name of the new service plan to use for the service instance.



</td>
</tr>
<tr>
<td valign="top">

`--parameters`



</td>
<td valign="top">

The parameters of the service instance as a valid JSON object with the following format: `{"parameter1":"value1","parameter2":"value2"}`, provided as a file or in-line using appropriate quotes and escaping that complies with your operating system and shell.



</td>
</tr>
</table>

