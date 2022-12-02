<!-- loio19fadcd1051c4061820b791263cbf0ba -->

# unbind



<a name="loio19fadcd1051c4061820b791263cbf0ba__section_xcr_2nt_pkb"/>

## Overview



***smctl unbind*** 

Deletes a service binding with the name provided for a specified service instance.



<a name="loio19fadcd1051c4061820b791263cbf0ba__section_fp5_f4t_pkb"/>

## Usage

`smctl unbind [instance-name] [binding-name] [flags]`



<a name="loio19fadcd1051c4061820b791263cbf0ba__section_hdy_lpt_pkb"/>

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

Help for `unbind` command.



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

ID of the service binding. Required when the service binding name is ambiguous.



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



<a name="loio19fadcd1051c4061820b791263cbf0ba__section_wv2_4pt_pkb"/>

## Example

***async*** execution:

```
> smctl unbind sample-instance sample-binding
Do you really want to delete binding with name [sample-binding] for instance with name sample-instance (Y/n): yes
Service Binding sample-binding successfully scheduled for deletion. To see status of the operation use:
smctl status /v1/service_bindings/5937785d-6740-4f56-bdd9-8d24544bddac/operations/6066bd46-79d4-4f8e-be50-9ad2e5ca035a
```

Checking the status of the call:

```
> mctl status /v1/service_bindings/5937785d-6740-4f56-bdd9-8d24544bddac/operations/6066bd46-79d4-4f8e-be50-9ad2e5ca035a

| ID     | 6066bd46-79d4-4f8e-be50-9ad2e5ca035a  |
| Type   | delete                                |
| State  | succeeded                             |
```

***sync*** execution:

```
> smctl unbind sample-instance sample-binding --mode sync
Do you really want to delete binding with name [sample-binding] for instance with name sample-instance (Y/n): yes
Service Binding successfully deleted.
```

