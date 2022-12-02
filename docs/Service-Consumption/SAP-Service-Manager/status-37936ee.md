<!-- loio37936ee16cc1410889089de0d18ae948 -->

# status



<a name="loio37936ee16cc1410889089de0d18ae948__section_xcr_2nt_pkb"/>

## Overview



***smctl status*** 

Get the status of an asynchronous operation.



<a name="loio37936ee16cc1410889089de0d18ae948__section_fp5_f4t_pkb"/>

## Usage

`smctl status [operation URL path] [flags]`



<a name="loio37936ee16cc1410889089de0d18ae948__section_hdy_lpt_pkb"/>

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

Help for `status` command.



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



<a name="loio37936ee16cc1410889089de0d18ae948__section_wv2_4pt_pkb"/>

## Example

```
> smctl status /v1/service_bindings/5937785d-6740-4f56-bdd9-8d24544bddac/operations/6066bd46-79d4-4f8e-be50-9ad2e5ca035a

| ID     | 6066bd46-79d4-4f8e-be50-9ad2e5ca035a  |
| Type   | delete                                |
| State  | succeeded                             |
```

