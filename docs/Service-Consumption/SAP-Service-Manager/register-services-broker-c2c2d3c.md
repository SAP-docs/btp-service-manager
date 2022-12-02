<!-- loioc2c2d3ce19624d959fd9155afe52cf74 -->

# register services/broker



<a name="loioc2c2d3ce19624d959fd9155afe52cf74__section_xcr_2nt_pkb"/>

## Overview



***btp register services/broker*** 

Registers a service broker in a subaccount.



<a name="loioc2c2d3ce19624d959fd9155afe52cf74__section_fp5_f4t_pkb"/>

## Usage

`btp register services/broker [parameters]`



<a name="loioc2c2d3ce19624d959fd9155afe52cf74__section_hdy_lpt_pkb"/>

## Parameters


<table>
<tr>
<th valign="top" colspan="2">

Required



</th>
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

Help for `register services/broker` command.



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

Labels of a broker consist of key-value pairs. The key must be a string \(100 characters maximum\) and only consist of alphanumeric characters, periods, hyphens, and underscores. The value must be a non-empty array of unique strings without newline characters \(255 characters maximum\). The labels object must have the following format: `{\"<LABEL_NAME>\": [\"<LABEL_VALUE>\", \"<LABEL_VALUE>\"], \"<OTHER_LABEL_NAME>\": [\"<LABEL_VALUE>\"]}`.



</td>
</tr>
</table>



## Example

```
> btp register services/broker -sa my-subaccount-id -n my-broker-name --url my-broker-url -u my-broker-user -p my-broker-password

btp register services/broker -sa e4d3e542-7029-4114-8b3b-09d6c921123a -n my-broker-name --url https://broker.cfapps.us10.hana.ondemand.com -u admin -p password           
id: my-broker-id
name: my-broker-name
username: my-broker-user
password: my-broker-password
description: "broker description"
broker_url: my-broker-url
created_at: "2020-02-27T16:04:47.810739Z"
updated_at: "2020-02-27T16:04:47.810739Z"
labels: subaccount_id = my-subaccount-id

OK

```

