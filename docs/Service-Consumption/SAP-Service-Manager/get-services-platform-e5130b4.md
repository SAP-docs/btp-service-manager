<!-- loioe5130b4562cd41fe9204e10a1de513af -->

# get services/platform



<a name="loioe5130b4562cd41fe9204e10a1de513af__section_xcr_2nt_pkb"/>

## Overview



***btp get services/platform*** 

Gets the details about a specific platform that is registered for service consumption in a subaccount.



<a name="loioe5130b4562cd41fe9204e10a1de513af__section_fp5_f4t_pkb"/>

## Usage

`btp get services/platform [parameters]`



<a name="loioe5130b4562cd41fe9204e10a1de513af__section_hdy_lpt_pkb"/>

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

Help for `btp get services/platform` command.



</td>
</tr>
</table>



<a name="loioe5130b4562cd41fe9204e10a1de513af__section_wv2_4pt_pkb"/>

## Example

```
> btp get services/platform my-platform-id -sa my-subaccount-id

id: my-platform-id
name: my-platform-name
description: ""
platform_url: my-platform-url
created_at: "2020-02-27T16:04:47.810739Z"
updated_at: "2020-02-27T16:04:47.810739Z"
labels: subaccount_id = my-subaccount-id

OK

```

