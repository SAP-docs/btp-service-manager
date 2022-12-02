<!-- loiobdf3de188cd24b43bd5d161f2030e4a4 -->

# get services/broker



<a name="loiobdf3de188cd24b43bd5d161f2030e4a4__section_xcr_2nt_pkb"/>

## Overview



***btp get services/broker*** 

Gets the details about a specific service broker registered in a subaccount.



<a name="loiobdf3de188cd24b43bd5d161f2030e4a4__section_fp5_f4t_pkb"/>

## Usage

`btp get services/broker [parameters]`



<a name="loiobdf3de188cd24b43bd5d161f2030e4a4__section_hdy_lpt_pkb"/>

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

Help for `get services/broker` command.



</td>
</tr>
</table>



<a name="loiobdf3de188cd24b43bd5d161f2030e4a4__section_wv2_4pt_pkb"/>

## Example

```
> btp get services/broker my-broker-id -sa my-subaccount-id

id: my-broker-id
name: my-broker-name
description: ""
broker_url: my-broker-url
created_at: "2020-02-27T16:04:47.810739Z"
updated_at: "2020-02-27T16:04:47.810739Z"
labels: subaccount_id = my-subaccount-id

OK

```

