<!-- loio5a44ad89b50249148b9e299f93f43f7a -->

# create services/instance

Create a new service instance.



<a name="loio5a44ad89b50249148b9e299f93f43f7a__section_xcr_2nt_pkb"/>

## Overview



`btp create services/instance` 



<a name="loio5a44ad89b50249148b9e299f93f43f7a__section_fp5_f4t_pkb"/>

## Usage

`btp create services/instance [parameters]`



<a name="loio5a44ad89b50249148b9e299f93f43f7a__section_hdy_lpt_pkb"/>

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

The ID of the subaccount in which to create the service instance. You can omit this parameter if you have already set the context to the subaccount using `btp target --subaccount ID`.



</td>
</tr>
<tr>
<td valign="top">

`-s`, `--service`



</td>
<td valign="top">

The name of the service instance to create.



</td>
</tr>
<tr>
<td valign="top">

`-p`, `--plan`



</td>
<td valign="top">

The ID of the service plan for the service instance.



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

The parameters of the service instance as a valid JSON object with the following format: `{"parameter1":"value1","parameter2":"value2"}`, provided as a file or in-line using appropriate quotes and escaping that complies with your operating system and shell.



</td>
</tr>
<tr>
<td valign="top">

`-l`, `--labels`



</td>
<td valign="top">

The labels of a service instance are key-value pairs with the following format: <code>{"<i class="varname">&lt;label name&gt;</i>": ["<i class="varname">&lt;label_value&gt;</i>", "<i class="varname">&lt;label_value&gt;</i>"], "<i class="varname">&lt;label_name1&gt;</i>": ["<i class="varname">&lt;label_value2&gt;</i>"]}</code>.You can provide this object as a file or in-line using appropriate quotes and escaping that complies with your operating system and shell. The key must be a string \(100 characters max\) and can only consist of alphanumeric characters, periods, hyphens, and underscores. The value must be a nonempty array of unique strings without newline characters \(255 characters max\).



</td>
</tr>
</table>

