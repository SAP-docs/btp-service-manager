<!-- loioae6874a4c7ea4a50b23fa4206c222fac -->

# marketplace



<a name="loioae6874a4c7ea4a50b23fa4206c222fac__section_xcr_2nt_pkb"/>

## Overview



***smctl marketplace*** 

Lists all service offerings with their service plans that are available in SAP Service Manager for this subaccount.



<a name="loioae6874a4c7ea4a50b23fa4206c222fac__section_fp5_f4t_pkb"/>

## Usage

`smctl marketplace [flags]`



<a name="loioae6874a4c7ea4a50b23fa4206c222fac__section_ppz_kpt_pkb"/>

## Aliases

`marketplace, m`



<a name="loioae6874a4c7ea4a50b23fa4206c222fac__section_hdy_lpt_pkb"/>

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

Help for `marketplace` command.



</td>
<td valign="top">

No



</td>
</tr>
<tr>
<td valign="top">

`-s`, `--service`



</td>
<td valign="top">

Detailed information about the plans of a specific service offering.



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



<a name="loioae6874a4c7ea4a50b23fa4206c222fac__section_wv2_4pt_pkb"/>

## Example

```
> smctl marketplace
One service offering.
Name              Plans            Description                                                                                       Broker ID
----------------  ---------------  ------------------------------------------------------------------------------------------------  ------------------------------------
overview-service  simple, complex  Provides an overview of any service instances and bindings that have been created by a platform.  46343c8e-957f-4fde-8176-ca3510d489e0
```

```
> smctl marketplace -s overview-service
2 service plans for this service offering.
Plan     Description               ID
-------  ------------------------  ------------------------------------
simple   A very simple plan.       25304783-2fc9-4f50-8dcb-0cbfe017ad15
complex  A more complicated plan.  52207e8e-1456-4f2e-b3df-3b97fe8d3d6f
```

