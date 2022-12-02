<!-- loio728f1b6de8f24fd382a435988943f9bd -->

# list-instances



<a name="loio728f1b6de8f24fd382a435988943f9bd__section_xcr_2nt_pkb"/>

## Overview



***smctl list-instances*** 

Lists all service instances.



<a name="loio728f1b6de8f24fd382a435988943f9bd__section_fp5_f4t_pkb"/>

## Usage

`smctl list-instances [flags]`



<a name="loio728f1b6de8f24fd382a435988943f9bd__section_ppz_kpt_pkb"/>

## Aliases

`list-instances, li`



<a name="loio728f1b6de8f24fd382a435988943f9bd__section_hdy_lpt_pkb"/>

## Parameters


<table>
<tr>
<th valign="top" colspan="2">

Optional



</th>
<th valign="top">

Global Flag



</th>
</tr>
<tr>
<td valign="top">

`-h`, `--help`



</td>
<td valign="top">

Help for `list-instances` command.



</td>
<td valign="top">

No



</td>
</tr>
<tr>
<td valign="top">

`-o`, `--output`



</td>
<td valign="top">

Output format of the command. Possible options: json, yaml, text



</td>
<td valign="top">

No



</td>
</tr>
<tr>
<td valign="top">

`--config`



</td>
<td valign="top">

Set the path for the **smctl** `config.json` file \(default is `$HOME/.sm/config.json`\).



</td>
<td valign="top">

Yes



</td>
</tr>
<tr>
<td valign="top">

`-v`, `--verbose`



</td>
<td valign="top">

Use verbose mode.



</td>
<td valign="top">

Yes



</td>
</tr>
</table>



<a name="loio728f1b6de8f24fd382a435988943f9bd__section_wv2_4pt_pkb"/>

## Example

```
> smctl list-instances
One service instance.
ID                                    Name             Service Plan ID                       Platform ID      Created                      Updated                     Ready  Usable  Labels
------------------------------------  ---------------  ------------------------------------  ---------------  ---------------------------  --------------------------  -----  ------  ------------------------------------
0c170e73-28bd-47ea-b3f4-f1ad1dbf3e0a  sample-instance  25304783-2fc9-4f50-8dcb-0cbfe017ad15  service-manager  2020-04-09T10:42:12.175051Z  2020-04-09T10:42:13.22521Z  true   true    subaccount_id=subacc-cfdev-tenant-id
```

