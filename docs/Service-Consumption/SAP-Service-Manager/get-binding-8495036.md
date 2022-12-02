<!-- loio8495036f13a84bd382b43ec1a8f47658 -->

# get-binding



<a name="loio8495036f13a84bd382b43ec1a8f47658__section_xcr_2nt_pkb"/>

## Overview



***smctl get-binding*** 

Get detailed information about a specific service binding.



<a name="loio8495036f13a84bd382b43ec1a8f47658__section_fp5_f4t_pkb"/>

## Usage

`smctl get-binding [name] [flags]`



<a name="loio8495036f13a84bd382b43ec1a8f47658__section_ppz_kpt_pkb"/>

## Aliases

`get-binding, gsb`



<a name="loio8495036f13a84bd382b43ec1a8f47658__section_hdy_lpt_pkb"/>

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

Help for `get-binding` command.



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

`--show-binding-params`



</td>
<td valign="top">

Show service binding configuration parameters.



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



<a name="loio8495036f13a84bd382b43ec1a8f47658__section_wv2_4pt_pkb"/>

## Example

```
> smctl get-binding sample-binding
One service binding.
| ID             | 5937785d-6740-4f56-bdd9-8d24544bddac                |
| Name           | sample-binding                                      |
| Instance Name  | sample-instance                                     |
| Credentials    | {"password":"pass","username":"usr"}                |
| Created        | 2020-04-09T10:57:50.452161Z                         |
| Updated        | 2020-04-09T10:57:51.505822Z                         |
| Ready          | true                                                |
| Labels         | subaccount_id=subacc-cfdev-tenant-id                |
| Last Op        | create succeeded                                    |
```

```
> smctl get-binding sample-binding --show-binding-params
Showing parameters for service binding id:  0c170e73-28bd-47ea-b3f4-f1ad1dbf3e0a
The parameters are:
{
   "param1":"value1",
   "param2":"value2"
}
```

