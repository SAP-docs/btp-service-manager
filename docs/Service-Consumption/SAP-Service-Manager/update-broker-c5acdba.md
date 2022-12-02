<!-- loioc5acdba3d78049c5bf274ddfa5a9bce8 -->

# update-broker



<a name="loioc5acdba3d78049c5bf274ddfa5a9bce8__section_xcr_2nt_pkb"/>

## Overview



***smctl update-broker*** 

Updates a service broker with the provided name in the SAP Service Manager instance.



<a name="loioc5acdba3d78049c5bf274ddfa5a9bce8__section_fp5_f4t_pkb"/>

## Usage

`smctl update-broker [name] <json_broker> [flags]`



<a name="loioc5acdba3d78049c5bf274ddfa5a9bce8__section_bq5_yl5_pkb"/>

## Example

```
smctl update-broker broker '{"name": "new-name", "description": "new-description", "broker-url": "http://broker.com", "credentials": { "basic": { "username": "admin", "password": "admin" } }}'
```



<a name="loioc5acdba3d78049c5bf274ddfa5a9bce8__section_ppz_kpt_pkb"/>

## Aliases

`update-broker, ub`



<a name="loioc5acdba3d78049c5bf274ddfa5a9bce8__section_hdy_lpt_pkb"/>

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

Help for `update-broker` command.



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

Output format of the command. Possible options: json, yaml, text.



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



<a name="loioc5acdba3d78049c5bf274ddfa5a9bce8__section_wv2_4pt_pkb"/>

## Example

```
> smctl update-broker sample-broker-1 '{"description": "Updated sample-broker description"}' 

ID                                    Name             URL                             Description                        Created               Updated               
------------------------------------  ---------------  ------------------------------  ---------------------------------  --------------------  --------------------  
a52be735-30e5-4849-af23-83d65d592464  sample-broker-1  https://demobroker.domain.com/  Updated sample-broker description  2018-06-22T13:04:19Z  2018-06-22T13:04:19Z
```

