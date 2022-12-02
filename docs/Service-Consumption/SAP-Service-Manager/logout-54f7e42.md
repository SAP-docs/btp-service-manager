<!-- loio54f7e42c56a74e87a44e4e9e780f994b -->

# logout



<a name="loio54f7e42c56a74e87a44e4e9e780f994b__section_xcr_2nt_pkb"/>

## Overview



***smctl logout*** 

Logs the user out and deletes the active client access token.



<a name="loio54f7e42c56a74e87a44e4e9e780f994b__section_fp5_f4t_pkb"/>

## Usage

`smctl logout [flags]`



<a name="loio54f7e42c56a74e87a44e4e9e780f994b__section_ppz_kpt_pkb"/>

## Aliases

`logout, v`



<a name="loio54f7e42c56a74e87a44e4e9e780f994b__section_hdy_lpt_pkb"/>

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

Help for the `logout` command.



</td>
<td valign="top">

No



</td>
</tr>
<tr>
<td valign="top">

`-v`, `--verbose`



</td>
<td valign="top">

Use the verbose mode.



</td>
<td valign="top">

Yes



</td>
</tr>
<tr>
<td valign="top">

`--config`



</td>
<td valign="top">

Use this parameter to specify which configuration file to remove during the logout. If no path is provided, a default path `$HOME/.sm/config.json` is used.



</td>
<td valign="top">

Yes



</td>
</tr>
</table>



<a name="loio54f7e42c56a74e87a44e4e9e780f994b__section_wv2_4pt_pkb"/>

## Example 1

```
> smctl logout


You have successfully logged out.
```

