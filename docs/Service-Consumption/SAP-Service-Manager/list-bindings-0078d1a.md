<!-- loio0078d1af20fd483d87ea3aea08b3a6e0 -->

# list-bindings



<a name="loio0078d1af20fd483d87ea3aea08b3a6e0__section_xcr_2nt_pkb"/>

## Overview



***smctl list-bindings*** 

Lists all service bindings created in SAP Service Manager for the associated subaccount.



<a name="loio0078d1af20fd483d87ea3aea08b3a6e0__section_fp5_f4t_pkb"/>

## Usage

`smctl list-bindings [flags]`



<a name="loio0078d1af20fd483d87ea3aea08b3a6e0__section_ppz_kpt_pkb"/>

## Aliases

`list-bindings, lsb`



<a name="loio0078d1af20fd483d87ea3aea08b3a6e0__section_hdy_lpt_pkb"/>

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

Help for `list-bindings` command.



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



<a name="loio0078d1af20fd483d87ea3aea08b3a6e0__section_wv2_4pt_pkb"/>

## Example

```
> smctl list-bindings
One service binding.
ID                                    Name            Instance Name    Credentials                                         Created                      Updated                      Ready  Labels
------------------------------------  --------------  ---------------  --------------------------------------------------  ---------------------------  ---------------------------  -----  ------------------------------------
5937785d-6740-4f56-bdd9-8d24544bddac  sample-binding  sample-instance  {"password":"pass","username":"usr"}  2020-04-09T10:57:50.452161Z  2020-04-09T10:57:51.505822Z  true   subaccount_id=subacc-cfdev-tenant-id
```

