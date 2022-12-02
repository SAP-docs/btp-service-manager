<!-- loio7cf9dc5320974258a0829267273e66a3 -->

# create services/binding

Create a service binding between a service instance and an application.



<a name="loio7cf9dc5320974258a0829267273e66a3__section_xcr_2nt_pkb"/>

## Overview



`btp create services/binding` 



<a name="loio7cf9dc5320974258a0829267273e66a3__section_fp5_f4t_pkb"/>

## Usage

`btp create services/binding [parameters]`



<a name="loio7cf9dc5320974258a0829267273e66a3__section_hdy_lpt_pkb"/>

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

The ID of the subaccount in which to bind the service instance to an application. You can omit this parameter if you have already set the context to the subaccount using `btp target --subaccount ID`.



</td>
</tr>
<tr>
<td valign="top">

`-b`, `--binding`



</td>
<td valign="top">

The name of the service binding to create.



</td>
</tr>
<tr>
<td valign="top">

`-n`,`--name`



</td>
<td valign="top">

The name of the service binding to create.

> ### Note:  
> You can use either `--binding` or `--name` to specify the name of the service binding you are creating.



</td>
</tr>
<tr>
<td valign="top">

`-si`, `--service-instance`



</td>
<td valign="top">

The ID of the service instance for which you are creating this binding.



</td>
</tr>
<tr>
<td valign="top">

`--instance-name`



</td>
<td valign="top">

The name of the service instance for which you are creating this binding.

> ### Note:  
> You can use either `--service-instance` or `--instance-name` to specify the ID or name of the service instance for which you are creating this binding.



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

`--parameters`



</td>
<td valign="top">

The parameters of the service binding as a valid JSON object with the following format: `{"parameter1":"value1","parameter2":"value2"}`, provided as a file or in-line using appropriate quotes and escaping that complies with your operating system and shell.



</td>
</tr>
<tr>
<td valign="top">

`-l`, `--labels`



</td>
<td valign="top">

The labels of a service binding are key-value pairs with the following format: <code>{"<i class="varname">&lt;label name&gt;</i>": ["<i class="varname">&lt;label_value&gt;</i>", "<i class="varname">&lt;label_value&gt;</i>"], "<i class="varname">&lt;label_name1&gt;</i>": ["<i class="varname">&lt;label_value2&gt;</i>"]}</code>. You can provide this object as a file or in-line using appropriate quotes and escaping that complies with your operating system and shell. The key must be a string \(100 characters max\) and can only consist of alphanumeric characters, periods, hyphens, and underscores. The value must be a nonempty array of unique strings without newline characters \(255 characters max\).



</td>
</tr>
</table>

