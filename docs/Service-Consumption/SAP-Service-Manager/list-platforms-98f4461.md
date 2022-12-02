<!-- loio98f44611f4c74010b41978fc8332a291 -->

# list-platforms



<a name="loio98f44611f4c74010b41978fc8332a291__section_xcr_2nt_pkb"/>

## Overview



***smctl list-platforms*** 

Lists all platforms registered in the SAP Service Manager instance.



<a name="loio98f44611f4c74010b41978fc8332a291__section_fp5_f4t_pkb"/>

## Usage

`smctl list-platforms [flags]`



<a name="loio98f44611f4c74010b41978fc8332a291__section_ppz_kpt_pkb"/>

## Aliases

`list-platforms, lp`



<a name="loio98f44611f4c74010b41978fc8332a291__section_hdy_lpt_pkb"/>

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

Help for `list-platforms` command.



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



<a name="loio98f44611f4c74010b41978fc8332a291__section_wv2_4pt_pkb"/>

## Example

```
> smctl list-platforms 

One platform registered.
ID                                    Name             Type    Description      Created               Updated               
------------------------------------  ---------------  ------  ---------------  --------------------  --------------------  
6352fca0-c252-43ab-9cb3-d23613749b59  sample-platform  sample  Sample platform  2018-07-18T07:06:40Z  2018-07-18T07:06:40Z
```

