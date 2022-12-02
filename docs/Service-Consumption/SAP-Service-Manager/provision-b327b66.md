<!-- loiob327b66b711746b085ec5d2ea16e608e -->

# provision



<a name="loiob327b66b711746b085ec5d2ea16e608e__section_xcr_2nt_pkb"/>

## Overview



***smctl provision*** 

Create a service instance in SAP Service Manager.



<a name="loiob327b66b711746b085ec5d2ea16e608e__section_fp5_f4t_pkb"/>

## Usage

`smctl provision [name] [offering] [plan] [flags]`



<a name="loiob327b66b711746b085ec5d2ea16e608e__section_hdy_lpt_pkb"/>

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

Help for `provision` command.



</td>
<td valign="top">

No



</td>
</tr>
<tr>
<td valign="top">

`-b``--broker-name`



</td>
<td valign="top">

Name of the broker that provides the service offering. Only required when the offering name is ambiguous.



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



<a name="loiob327b66b711746b085ec5d2ea16e608e__section_wv2_4pt_pkb"/>

## Example

***async*** execution:

```
> smctl provision sample-instance overview-service simple
Service Instance sample-instance successfully scheduled for provisioning. To see status of the operation use:
smctl status /v1/service_instances/a6b0dfe6-1bd1-453f-a646-babd425b6b05/operations/32bbbee7-a9d0-48e4-a434-bf47bc471a48
```

```
> smctl status /v1/service_instances/a6b0dfe6-1bd1-453f-a646-babd425b6b05/operations/32bbbee7-a9d0-48e4-a434-bf47bc471a48
				
				| ID     | 32bbbee7-a9d0-48e4-a434-bf47bc471a48  |
				| Type   | create                                |
				| State  | succeeded                             |
```

***sync*** execution:

```
> smctl provision sample-instance overview-service simple --mode sync

| ID               | 0c170e73-28bd-47ea-b3f4-f1ad1dbf3e0a  |
| Name             | sample-instance                       |
| Service Plan ID  | 25304783-2fc9-4f50-8dcb-0cbfe017ad15  |
| Platform ID      | service-manager                       |
| Created          | 2020-04-09T10:42:12.175051Z           |
| Updated          | 2020-04-09T10:42:13.2252101Z          |
| Ready            | true                                  |
| Usable           | true                                  |
| Labels           | subaccount_id=subacc-cfdev-tenant-id  |
| Last Op          | create succeeded                      |
```

