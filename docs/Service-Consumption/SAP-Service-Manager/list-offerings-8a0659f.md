<!-- loio8a0659f7da074e83936623d7681f7adb -->

# list-offerings



<a name="loio8a0659f7da074e83936623d7681f7adb__section_xcr_2nt_pkb"/>

## Overview



***smctl list-offerings*** 

Lists all service offerings that are associated with the SAP Service Manager for this subaccount.



<a name="loio8a0659f7da074e83936623d7681f7adb__section_fp5_f4t_pkb"/>

## Usage

`smctl list-offerings [flags]`



<a name="loio8a0659f7da074e83936623d7681f7adb__section_ppz_kpt_pkb"/>

## Aliases

`list-offerings, lo`



<a name="loio8a0659f7da074e83936623d7681f7adb__section_hdy_lpt_pkb"/>

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

Help for `list-offerings` command.



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



<a name="loio8a0659f7da074e83936623d7681f7adb__section_wv2_4pt_pkb"/>

## Example

```
> smctl list-offerings
One service offering.
ID                                    Name              Description                                                                                       Broker ID                             Ready  Labels
------------------------------------  ----------------  ------------------------------------------------------------------------------------------------  ------------------------------------  -----  ------
54944d91-75b9-442c-aecd-f98821490740  overview-service  Provides an overview of any service instances and bindings that have been created by a platform.  46343c8e-957f-4fde-8176-ca3510d489e0  true
```

