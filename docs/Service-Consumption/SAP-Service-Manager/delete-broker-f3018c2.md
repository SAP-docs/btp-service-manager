<!-- loiof3018c2fb3204eb9b294079d61be770e -->

# delete-broker



<a name="loiof3018c2fb3204eb9b294079d61be770e__section_xcr_2nt_pkb"/>

## Overview



***smctl delete-broker*** 

Deletes a set of brokers registered in the SAP Service Manager instance.



<a name="loiof3018c2fb3204eb9b294079d61be770e__section_fp5_f4t_pkb"/>

## Usage

`smctl delete-broker [name] <name2 <name3> ... <nameN> [flags]`



<a name="loiof3018c2fb3204eb9b294079d61be770e__section_ppz_kpt_pkb"/>

## Aliases

`delete-broker, db`



<a name="loiof3018c2fb3204eb9b294079d61be770e__section_hdy_lpt_pkb"/>

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

Help for `delete-broker` command.



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



<a name="loiof3018c2fb3204eb9b294079d61be770e__section_wv2_4pt_pkb"/>

## Example

```
> smctl delete-broker sample-broker-1

Broker with name: sample-broker-1 successfully deleted
```

