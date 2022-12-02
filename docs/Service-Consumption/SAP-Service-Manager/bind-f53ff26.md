<!-- loiof53ff2634e0a46d6bfc72ec075418dcd -->

# bind



<a name="loiof53ff2634e0a46d6bfc72ec075418dcd__section_xcr_2nt_pkb"/>

## Overview



***smctl bind*** 

Creates a binding to a specific instance in the SAP Service Manager.



<a name="loiof53ff2634e0a46d6bfc72ec075418dcd__section_fp5_f4t_pkb"/>

## Usage

`smctl bind [instance-name] [binding-name] [flags]`



<a name="loiof53ff2634e0a46d6bfc72ec075418dcd__section_hdy_lpt_pkb"/>

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

Help for `bind` command.



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

`-c``--parameters`



</td>
<td valign="top">

A valid JSON object containing the instance parameters.



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



<a name="loiof53ff2634e0a46d6bfc72ec075418dcd__section_wv2_4pt_pkb"/>

## Example

***async*** execution:

```
> smctl bind sample-instance sample-binding
Service Binding sample-binding successfully scheduled. To see status of the operation use:
smctl status /v1/service_bindings/6372815d-29b8-4561-9898-016d6671b34b/operations/ea67e94f-ad2f-4544-8b87-6924fe494327
```

Checking the status of the call:

```
> smctl status /v1/service_bindings/6372815d-29b8-4561-9898-016d6671b34b/operations/ea67e94f-ad2f-4544-8b87-6924fe494327

| ID     | ea67e94f-ad2f-4544-8b87-6924fe494327  |
| Type   | create                                |
| State  | succeeded                             |
```

***sync*** execution:

```
smctl bind sample-instance sample-binding --mode sync

| ID                     | 5937785d-6740-4f56-bdd9-8d24544bddac                |
| Name                   | sample-binding                                      |
| Service Instance Name  | sample-instance                                     |
| Service Instance ID    | 742b0c67-37f6-4c63-83d9-e3c5d2cb69f0                |
| Credentials            | {"password":"pass","username":"usr"}  |
| Created                | 2020-04-09T10:57:50.452161Z                         |
| Updated                | 2020-04-09T10:57:51.5058215Z                        |
| Ready                  | true                                                |
| Labels                 | subaccount_id=subacc-cfdev-tenant-id                |
| Last Op                | create succeeded                                    |
```

