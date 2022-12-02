<!-- loio4d2bb71e2ba14064b3d4ba3283fa55e2 -->

# info



<a name="loio4d2bb71e2ba14064b3d4ba3283fa55e2__section_xcr_2nt_pkb"/>

## Overview



***smctl info*** 

Displays information about the SAP Service Manager instance to which the **SMCTL** is connected.



<a name="loio4d2bb71e2ba14064b3d4ba3283fa55e2__section_fp5_f4t_pkb"/>

## Usage

`smctl info [flags]`



<a name="loio4d2bb71e2ba14064b3d4ba3283fa55e2__section_ppz_kpt_pkb"/>

## Aliases

`info, i`



<a name="loio4d2bb71e2ba14064b3d4ba3283fa55e2__section_hdy_lpt_pkb"/>

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

Help for `info` command.



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



<a name="loio4d2bb71e2ba14064b3d4ba3283fa55e2__section_wv2_4pt_pkb"/>

## Example

```
> smctl info

Service Management URL: https://service-management-url.com/
Logged user: testUser 
```

