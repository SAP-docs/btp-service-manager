<!-- loio591007fd3f7e4b979937da3a5281db4c -->

# update services/broker



<a name="loio591007fd3f7e4b979937da3a5281db4c__section_xcr_2nt_pkb"/>

## Overview



***btp update services/broker*** 

Updates an existing service broker in a subaccount.



<a name="loio591007fd3f7e4b979937da3a5281db4c__section_fp5_f4t_pkb"/>

## Usage

`btp update services/broker [parameters]`



<a name="loio591007fd3f7e4b979937da3a5281db4c__section_hdy_lpt_pkb"/>

## Parameters


<table>
<tr>
<th valign="top" colspan="2">

Required



</th>
</tr>
<tr>
<td valign="top">

`ID`



</td>
<td valign="top">

ID of the broker.



</td>
</tr>
<tr>
<td valign="top">

`-sa`, `--subaccount`



</td>
<td valign="top">

Subaccount ID. To find your subaccount ID, use `btp list accounts/subaccount` or you can omit this parameter if you have already set the context to a subaccount using `btp target --subaccount ID`.



</td>
</tr>
</table>


<table>
<tr>
<th valign="top" colspan="2">

Optional



</th>
</tr>
<tr>
<td valign="top">

`-h`, `--help`



</td>
<td valign="top">

Help for `update services/broker` command.



</td>
</tr>
<tr>
<td valign="top">

`-n`, `--name`



</td>
<td valign="top">

Name of the new service broker. Use only alphanumeric characters and hyphens \(no spaces\). Must be unique across all service brokers registered with the SAP Service Manager in the provided subaccount.



</td>
</tr>
<tr>
<td valign="top">

`--url`



</td>
<td valign="top">

URL of the new broker.



</td>
</tr>
<tr>
<td valign="top">

`-u`, `--user`



</td>
<td valign="top">

Username used for basic authentication against the broker.



</td>
</tr>
<tr>
<td valign="top">

`-p`, `--password`



</td>
<td valign="top">

Password used for basic authentication against the broker.



</td>
</tr>
<tr>
<td valign="top">

`-d`, `--description`



</td>
<td valign="top">

Description of the new broker.



</td>
</tr>
<tr>
<td valign="top">

`-l`, `--labels`



</td>
<td valign="top">

Broker labels consist of key-value pairs. The key must be a string with a maximum length of 100 characters and only consist of alphanumeric characters, periods, hyphens, and underscores. The value must be a non-empty array of unique strings without newline characters that doesn't exceed 255 characters. Labels are passed in a JSON object with the following format: `[{"op": "<OPERATION>", "key": "<LABEL_NAME>", "values": ["<LABEL_VALUE>", "<OTHER_LABEL_VALUE>"]}].`.



</td>
</tr>
</table>



<a name="loio591007fd3f7e4b979937da3a5281db4c__section_kvq_sjr_vkb"/>

## Example

```
> btp update services/broker my-broker-id -sa my-subaccount-id -n new-broker-name

id: my-broker-idmy-broker-id
name: new-broker-name
description: my-broker-description
broker_url: my-broker-url
created_at: "2020-02-27T16:04:47.810739Z"
updated_at: "2020-02-27T16:09:27.059740608Z"
labels: subaccount_id = my-subaccount-idmy-subaccount-id

OK

```

