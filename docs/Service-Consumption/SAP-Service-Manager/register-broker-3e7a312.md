<!-- loio3e7a3127429d4ae9b4e4b957074310ce -->

# register-broker



<a name="loio3e7a3127429d4ae9b4e4b957074310ce__section_xcr_2nt_pkb"/>

## Overview



***smctl register-broker*** 

Registers a broker in the SAP Service Manager instance.



<a name="loio3e7a3127429d4ae9b4e4b957074310ce__section_fp5_f4t_pkb"/>

## Usage

`smctl register-broker [name] [url] <description> [flags]`



<a name="loio3e7a3127429d4ae9b4e4b957074310ce__section_ppz_kpt_pkb"/>

## Aliases

`register-broker, rb`



<a name="loio3e7a3127429d4ae9b4e4b957074310ce__section_hdy_lpt_pkb"/>

## Parameters


<table>
<tr>
<th valign="top" colspan="2">

Required



</th>
<th valign="top">

Global Flag



</th>
</tr>
<tr>
<td valign="top">

`-b`, `--basic`



</td>
<td valign="top">

Sets the username and password for basic authentication. Format is ***<username:password\>***.



</td>
<td valign="top">

No



</td>
</tr>
</table>


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

Help for `register-broker` command.



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



<a name="loio3e7a3127429d4ae9b4e4b957074310ce__section_wv2_4pt_pkb"/>

## Example

```
> smctl register-broker sample-broker-1 https://demobroker.domain.com/ "Service broker providing some valuable services" -b user:pass

ID                                    Name             URL                             Description                                      Created               Updated
------------------------------------  ---------------  ------------------------------  -----------------------------------------------  --------------------  --------------------
a52be735-30e5-4849-af23-83d65d592464  sample-broker-1  https://demobroker.domain.com/  Service broker providing some valuable services  2018-06-22T13:04:19Z  2018-06-22T13:04:19Z
```

