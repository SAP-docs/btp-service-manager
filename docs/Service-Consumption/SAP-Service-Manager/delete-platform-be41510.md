<!-- loiobe41510922d546d7a30cc1ddafefe0c2 -->

# delete-platform



<a name="loiobe41510922d546d7a30cc1ddafefe0c2__section_xcr_2nt_pkb"/>

## Overview



***smctl delete-platform*** 

Deletes a set of platforms registered in the SAP Service Manager instance.



<a name="loiobe41510922d546d7a30cc1ddafefe0c2__section_fp5_f4t_pkb"/>

## Usage

`smctl delete-platform <name1> <name2> <name3> ... <nameN> [flags]`



<a name="loiobe41510922d546d7a30cc1ddafefe0c2__section_ppz_kpt_pkb"/>

## Aliases

`delete-platform, dp`



<a name="loiobe41510922d546d7a30cc1ddafefe0c2__section_hdy_lpt_pkb"/>

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

Help for `delete-platform` command.



</td>
<td valign="top">

No



</td>
</tr>
<tr>
<td valign="top">

`--cascade-delete`



</td>
<td valign="top">

Cascade delete for `delete-platform` command.



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



<a name="loiobe41510922d546d7a30cc1ddafefe0c2__section_wv2_4pt_pkb"/>

## Example

```
> smctl delete-platform sample-platform

Platform with name: sample-platform successfully deleted
```

```
> smctl delete-platform sample-platform --cascade-delete
Cascade delete successfully scheduled for platform: sample-platform. To see status of the operation use:
smctl status /v1/platforms/baea022b-64c0-43d4-a9b0-e1ae64af51cd/operations/f8ca64af-e889-4a45-ad41-f1baa2e427c2
```

