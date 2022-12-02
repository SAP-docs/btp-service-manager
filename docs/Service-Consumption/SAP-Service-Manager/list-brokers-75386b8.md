<!-- loio75386b8655374aeb9ca8ae4721b8ba1b -->

# list-brokers



<a name="loio75386b8655374aeb9ca8ae4721b8ba1b__section_xcr_2nt_pkb"/>

## Overview



***smctl list-brokers*** 

Lists all service brokers registered in the SAP Service Manager instance.



<a name="loio75386b8655374aeb9ca8ae4721b8ba1b__section_fp5_f4t_pkb"/>

## Usage

`smctl list-brokers [flags]`



<a name="loio75386b8655374aeb9ca8ae4721b8ba1b__section_ppz_kpt_pkb"/>

## Aliases

`list-brokers, lb`



<a name="loio75386b8655374aeb9ca8ae4721b8ba1b__section_hdy_lpt_pkb"/>

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

Help for `list-brokers` command.



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



<a name="loio75386b8655374aeb9ca8ae4721b8ba1b__section_wv2_4pt_pkb"/>

## Example

```
> smctl list-brokers

One broker registered.
ID                                    Name             URL                             Description                                      Created               Updated               
------------------------------------  ---------------  ------------------------------  -----------------------------------------------  --------------------  --------------------  
a52be735-30e5-4849-af23-83d65d592464  sample-broker-1  https://demobroker.domain.com/  Service broker providing some valuable services  2018-06-22T13:04:19Z  2018-06-22T13:04:19Z
```

