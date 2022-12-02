<!-- loiob467515fc2974667aed1bb31f40b2a27 -->

# update services/platform

Update an existing platform registered for service consumption in a subaccount.



<a name="loiob467515fc2974667aed1bb31f40b2a27__section_xcr_2nt_pkb"/>

## Overview



***btp update services/platform*** 



<a name="loiob467515fc2974667aed1bb31f40b2a27__section_fp5_f4t_pkb"/>

## Usage

`btp update services/platform [parameters]`



<a name="loiob467515fc2974667aed1bb31f40b2a27__section_hdy_lpt_pkb"/>

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

ID of the platform to be updated.



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

Help for `update services/platform` command.



</td>
</tr>
<tr>
<td valign="top">

`-n`, `--name`



</td>
<td valign="top">

Name of the platform. Use only alphanumeric characters and hyphens \(no spaces\). Must be unique across all service brokers registered with the SAP Service Manager in the provided subaccount.



</td>
</tr>
<tr>
<td valign="top">

`-d`, `--description`



</td>
<td valign="top">

Description of the platform.



</td>
</tr>
<tr>
<td valign="top">

`-l`, `--labels`



</td>
<td valign="top">

Labels of a platform must be an array of objects. It has the following format: `[{"op": "<OPERATION>", "key": "<LABEL_NAME>", "values": ["<LABEL_VALUE>", "<OTHER_LABEL_VALUE>"]}]`.



</td>
</tr>
<tr>
<td valign="top">

`--regenerate-credentials`



</td>
<td valign="top">

Whether to regenerate credentials for credentials rotation.

> ### Note:  
> Once new credentials are generated, old credentials can no longer be used.



</td>
</tr>
</table>



<a name="loiob467515fc2974667aed1bb31f40b2a27__section_kvq_sjr_vkb"/>

## Example

```
> btp update services/platform my-platform-id -sa my-subaccount-id -d my-platform-description 

id: my-platform-id
type: kubernetes
name: my-platform-name
description: my-platform-description
created_at: "2020-02-27T14:22:41.798266Z"
updated_at: "2020-02-27T14:25:45.671124791Z"
labels: subaccount_id = my-subaccount-id

OK

```

