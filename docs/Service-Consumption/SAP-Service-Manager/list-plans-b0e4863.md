<!-- loiob0e486325d3d41be9f7d316bee2b3f22 -->

# list-plans



<a name="loiob0e486325d3d41be9f7d316bee2b3f22__section_xcr_2nt_pkb"/>

## Overview



***smctl list-plans*** 

Lists all service plans that are associated with the SAP Service Manager for this subaccount.



<a name="loiob0e486325d3d41be9f7d316bee2b3f22__section_fp5_f4t_pkb"/>

## Usage

`smctl list-plans [flags]`



<a name="loiob0e486325d3d41be9f7d316bee2b3f22__section_hdy_lpt_pkb"/>

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

Help for `list-plans` command.



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



<a name="loiob0e486325d3d41be9f7d316bee2b3f22__section_wv2_4pt_pkb"/>

## Example

```
> smctl list-plans
2 service plans.
ID                                    Name     Description               Offering ID                           Ready  Labels
------------------------------------  -------  ------------------------  ------------------------------------  -----  ------
aec1cdac-9faa-4aa4-aeb7-6dbcc275208d  simple   A very simple plan.       a56dc9b4-70f9-45e3-a8a1-3b3a06289aa5  true
eb2ce3e0-d64c-4977-b51e-2f682ec2d835  complex  A more complicated plan.  a56dc9b4-70f9-45e3-a8a1-3b3a06289aa5  true
```

