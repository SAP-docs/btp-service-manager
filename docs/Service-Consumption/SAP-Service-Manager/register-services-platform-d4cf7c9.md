<!-- loiod4cf7c9d6b99477b8124c984a2df0a5a -->

# register services/platform



<a name="loiod4cf7c9d6b99477b8124c984a2df0a5a__section_xcr_2nt_pkb"/>

## Overview



***btp register services/platform*** 

Registers a platform to enable service consumption in a subaccount.



<a name="loiod4cf7c9d6b99477b8124c984a2df0a5a__section_fp5_f4t_pkb"/>

## Usage

`btp register services/platform [parameters]`



<a name="loiod4cf7c9d6b99477b8124c984a2df0a5a__section_hdy_lpt_pkb"/>

## Parameters


<table>
<tr>
<th valign="top" colspan="2">

Required



</th>
</tr>
<tr>
<td valign="top">

`-n`, `--name`



</td>
<td valign="top">

Name of the new platform. Use only alphanumeric characters and hyphens \(no spaces\). Must be unique across all service brokers registered with the SAP Service Manager in the provided subaccount.



</td>
</tr>
<tr>
<td valign="top">

`-t`, `--type`



</td>
<td valign="top">

Type of the platform. You can omit this parameter as the default and only supported value is 'kubernetes'.



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

Help for `register services/platform` command.



</td>
</tr>
<tr>
<td valign="top">

`--id`



</td>
<td valign="top">

ID of the platform to be registered. Must be unique across all platforms registered with the SAP Service Manager.



</td>
</tr>
<tr>
<td valign="top">

`-d`, `--description`



</td>
<td valign="top">

Description of the new platform.



</td>
</tr>
<tr>
<td valign="top">

`-l`, `--labels`



</td>
<td valign="top">

Labels of a platform consist of key-value pairs. The key must be a string \(100 characters maximum\) and only consist of alphanumeric characters, periods, hyphens, and underscores. The value must be a non-empty array of unique strings without newline characters \(255 characters maximum\). The labels object must have the following format: `{\"<LABEL_NAME>\": [\"<LABEL_VALUE>\", \"<LABEL_VALUE>\"], \"<OTHER_LABEL_NAME>\": [\"<LABEL_VALUE>\"]}`.



</td>
</tr>
</table>



<a name="loiod4cf7c9d6b99477b8124c984a2df0a5a__section_f5r_g4r_vkb"/>

## Example

```
> btp register services/platform -n my-platform -sa my-subaccount-id

btp register services/platform -n my-platform -sa e4d3e542-7029-4114-8b3b-09d6c921123a
id: my-platform-id
type: kubernetes
name: my-platform
username: my-platform-user
password: my-platform-password
description: ""
created_at: "2020-02-27T14:22:41.798266Z"
updated_at: "2020-02-27T14:22:41.798266Z"
labels: subaccount_id = my-subaccount-id

OK

```

