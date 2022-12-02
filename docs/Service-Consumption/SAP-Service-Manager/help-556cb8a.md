<!-- loio556cb8ac498a43cbb60cd6f5fe951c8c -->

# help



<a name="loio556cb8ac498a43cbb60cd6f5fe951c8c__section_xcr_2nt_pkb"/>

## Overview



***smctl help*** 

Displays the whole list of available commands. When a specific command is provided, help information for the specified command is displayed.



<a name="loio556cb8ac498a43cbb60cd6f5fe951c8c__section_fp5_f4t_pkb"/>

## Usage

`smctl help [command] [flags]`



<a name="loio556cb8ac498a43cbb60cd6f5fe951c8c__section_ppz_kpt_pkb"/>

## Aliases

`help, -h`



<a name="loio556cb8ac498a43cbb60cd6f5fe951c8c__section_hdy_lpt_pkb"/>

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



<a name="loio556cb8ac498a43cbb60cd6f5fe951c8c__section_wv2_4pt_pkb"/>

## Example

```
> smctl help

smctl controls a Service Management instance.

Usage:
  smctl [command]

Available Commands:
  delete-broker     Deletes brokers
  delete-platform   Deletes platforms
  help              Help about any command
  info              Prints information for logged user
  list-brokers      List brokers
  list-platforms    List platforms
  login             Logs user in
  register-broker   Registers a broker
  register-platform Registers a platform
  update-broker     Updates broker
  update-platform   Updates platform
  version           Prints smctl version

Flags:
      --config string   config file (default is $HOME/.sm/config.json)
  -h, --help            help for smctl
  -v, --verbose         verbose

Use "smctl [command] --help" for more information about a command.
```

