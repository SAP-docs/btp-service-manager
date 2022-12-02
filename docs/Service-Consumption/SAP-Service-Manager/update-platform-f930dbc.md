<!-- loiof930dbc7ae5845599a50e3f6010ff384 -->

# update-platform



<a name="loiof930dbc7ae5845599a50e3f6010ff384__section_xcr_2nt_pkb"/>

## Overview



***smctl update-platform*** 

Updates a platform with the SAP Service Manager instance.



<a name="loiof930dbc7ae5845599a50e3f6010ff384__section_fp5_f4t_pkb"/>

## Usage

`smctl update-platform [name] <json_platform> [flags]`



<a name="loiof930dbc7ae5845599a50e3f6010ff384__section_rqw_db2_tkb"/>

## Input Example

```
smctl update-platform platform '{"name": "new-name", "description": "new-description", "type": "new-type"}'
```



<a name="loiof930dbc7ae5845599a50e3f6010ff384__section_ppz_kpt_pkb"/>

## Aliases

`update-platform, up`



<a name="loiof930dbc7ae5845599a50e3f6010ff384__section_hdy_lpt_pkb"/>

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

Help for `update-platform` command.



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

`--regenerate-credentials`



</td>
<td valign="top">

Whether to regenerate credentials for credentials rotation.

> ### Note:  
> Once new credentials are generated, old credentials can no longer be used.



</td>
<td valign="top">

 



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



<a name="loiof930dbc7ae5845599a50e3f6010ff384__section_wv2_4pt_pkb"/>

## Output Example

```
> smctl update-platform sample-platform '{"description": "Sample platform instance"}' 

ID                                    Name             Type    Description               Created               Updated               
------------------------------------  ---------------  ------  ------------------------  --------------------  --------------------  
6352fca0-c252-43ab-9cb3-d23613749b59  sample-platform  sample  Sample platform instance  2018-07-18T07:06:40Z  2018-07-18T07:09:48Z  
```

