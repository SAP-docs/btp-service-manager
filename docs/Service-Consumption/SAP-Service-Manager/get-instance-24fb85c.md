<!-- loio24fb85cad5b44178afdfa31cc7898f28 -->

# get-instance



<a name="loio24fb85cad5b44178afdfa31cc7898f28__section_xcr_2nt_pkb"/>

## Overview



***smctl get-instance*** 

Get detailed information about a specified service instance.



<a name="loio24fb85cad5b44178afdfa31cc7898f28__section_fp5_f4t_pkb"/>

## Usage

`smctl get-instance [name] [flags]`



<a name="loio24fb85cad5b44178afdfa31cc7898f28__section_ppz_kpt_pkb"/>

## Aliases

`get-instance, gi`



<a name="loio24fb85cad5b44178afdfa31cc7898f28__section_hdy_lpt_pkb"/>

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

Help for `get-instance` command.



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

`--show-instance-params`



</td>
<td valign="top">

Show the service instance configuration parameters.



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



<a name="loio24fb85cad5b44178afdfa31cc7898f28__section_wv2_4pt_pkb"/>

## Example

```
> smctl get-instance sample-instance
One service instance.
| ID               | 0c170e73-28bd-47ea-b3f4-f1ad1dbf3e0a  |
| Name             | sample-instance                       |
| Service Plan ID  | 25304783-2fc9-4f50-8dcb-0cbfe017ad15  |
| Platform ID      | service-manager                       |
| Created          | 2020-04-09T10:42:12.175051Z           |
| Updated          | 2020-04-09T10:42:13.22521Z            |
| Ready            | true                                  |
| Usable           | true                                  |
| Labels           | subaccount_id=subacc-cfdev-tenant-id  |
| Last Op          | create succeeded                      |
```

```
> smctl get-instance sample-instance --show-instance-params
Showing parameters for service instance id:  0c170e73-28bd-47ea-b3f4-f1ad1dbf3e0a
The parameters are:
{
   "param1":"value1",
   "param2":"value2"
}
```

