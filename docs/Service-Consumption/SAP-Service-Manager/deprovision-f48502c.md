<!-- loiof48502c8c005454b9acdde5416cd4887 -->

# deprovision



<a name="loiof48502c8c005454b9acdde5416cd4887__section_xcr_2nt_pkb"/>

## Overview



***smctl deprovision*** 

Deletes a service instance.



<a name="loiof48502c8c005454b9acdde5416cd4887__section_fp5_f4t_pkb"/>

## Usage

`smctl deprovision [name] [flags]`



<a name="loiof48502c8c005454b9acdde5416cd4887__section_hdy_lpt_pkb"/>

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

Help for `deprovision` command.



</td>
<td valign="top">

No



</td>
</tr>
<tr>
<td valign="top">

`-f`, `--force`



</td>
<td valign="top">

Force delete - without confirmation.



</td>
<td valign="top">

No



</td>
</tr>
<tr>
<td valign="top">

`-id`



</td>
<td valign="top">

ID of the service instance. Required when the service instance name is ambiguous.



</td>
<td valign="top">

No



</td>
</tr>
<tr>
<td valign="top">

`--mode`



</td>
<td valign="top">

How calls to SAP Service Manager are performed. Possible values: ***sync*** or ***async*** \(the default is ***async***\).



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



<a name="loiof48502c8c005454b9acdde5416cd4887__section_wv2_4pt_pkb"/>

## Example

***async*** execution:

```
> smctl deprovision sample-instance
Do you really want to delete instance with name [sample-instance] (Y/n): yes
Service Instance sample-instance successfully scheduled for deletion. To see status of the operation use:
smctl status /v1/service_instances/0c170e73-28bd-47ea-b3f4-f1ad1dbf3e0a/operations/40a748c1-c0f8-4acf-84a0-64e20914531d
```

Checking the status of the call:

```
> smctl status /v1/service_instances/0c170e73-28bd-47ea-b3f4-f1ad1dbf3e0a/operations/40a748c1-c0f8-4acf-84a0-64e20914531d

| ID     | 40a748c1-c0f8-4acf-84a0-64e20914531d  |
| Type   | delete                                |
| State  | succeeded                             |
```

***sync*** execution:

```
> smctl deprovision sample-instance --mode sync
Do you really want to delete instance with name [sample-instance] (Y/n): yes
Service Instance successfully deleted.
```

