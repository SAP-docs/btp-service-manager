<!-- loio573514d539444c63a56cd43e9887f3b4 -->

# unregister services/broker



<a name="loio573514d539444c63a56cd43e9887f3b4__section_xcr_2nt_pkb"/>

## Overview



***btp unregister services/broker*** 

Unregisters an existing service broker in a subaccount.



<a name="loio573514d539444c63a56cd43e9887f3b4__section_fp5_f4t_pkb"/>

## Usage

`btp unregister services/broker [parameters]`



<a name="loio573514d539444c63a56cd43e9887f3b4__section_hdy_lpt_pkb"/>

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

ID of the broker.



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

Help for `unregister services/broker` command.



</td>
</tr>
</table>



<a name="loio573514d539444c63a56cd43e9887f3b4__section_r4y_3lr_vkb"/>

## Example

```
> btp unregister services/broker my-broker-id -sa my-subaccount-id

{}

OK

```

