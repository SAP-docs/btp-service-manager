<!-- loio4ab18b71bdb241f481b247deec68cf36 -->

# unregister services/platform



<a name="loio4ab18b71bdb241f481b247deec68cf36__section_xcr_2nt_pkb"/>

## Overview



***btp unregister services/platform*** 

Unregisters an existing platform in a subaccount.



<a name="loio4ab18b71bdb241f481b247deec68cf36__section_fp5_f4t_pkb"/>

## Usage

`btp unregister services/platform [parameters]`



<a name="loio4ab18b71bdb241f481b247deec68cf36__section_hdy_lpt_pkb"/>

## Parameters


<table>
<tr>
<th valign="top" colspan="2">

Required



</th>
</tr>
<tr>
<td valign="top">

ID



</td>
<td valign="top">

ID of the platform.



</td>
</tr>
<tr>
<td valign="top">

`-sa`, `--subaccount`



</td>
<td valign="top">

Subaccount ID. To find your subaccount ID, use `btp list accounts/subaccount` or you can omit this parameter if you have already set the context to a subaccount using `btp target --subaccount ID`.



</td>
</tr>
<tr>
<td valign="top">

`--confirm`



</td>
<td valign="top">

Confirms command execution. Providing this parameter will skip the confirmation prompt.



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

Help for `register services/platform` command.



</td>
</tr>
</table>



<a name="loio4ab18b71bdb241f481b247deec68cf36__section_r4y_3lr_vkb"/>

## Example

```
> btp unregister services/platform my-platform-id -sa my-subaccount-id

{}

OK

```

