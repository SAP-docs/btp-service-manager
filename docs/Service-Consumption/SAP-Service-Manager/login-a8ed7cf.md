<!-- loioa8ed7cf2a2e44dd890b7d11eb691ed75 -->

# login



<a name="loioa8ed7cf2a2e44dd890b7d11eb691ed75__section_xcr_2nt_pkb"/>

## Overview



***smctl login*** 

Authenticates user against a SAP Service Manager instance.



<a name="loioa8ed7cf2a2e44dd890b7d11eb691ed75__section_fp5_f4t_pkb"/>

## Usage

`smctl login [flags]`



<a name="loioa8ed7cf2a2e44dd890b7d11eb691ed75__section_ppz_kpt_pkb"/>

## Aliases

`login, l`



<a name="loioa8ed7cf2a2e44dd890b7d11eb691ed75__section_hdy_lpt_pkb"/>

## Parameters


<table>
<tr>
<th valign="top" colspan="2">

Required



</th>
<th valign="top">

Global Flag



</th>
</tr>
<tr>
<td valign="top">

`-a`, `--url`



</td>
<td valign="top">

Base URL for SAP Service Manager.



</td>
<td valign="top">

No



</td>
</tr>
<tr>
<td valign="top">

`--param`



</td>
<td valign="top">

Use it to add more parameters. Parameters are specified as `key=value` pairs.

> ### Note:  
> The `subdomain` parameter is mandatory for login.



</td>
<td valign="top">

No



</td>
</tr>
</table>


<table>
<tr>
<th valign="top" colspan="3">

Optional



</th>
<th valign="top">

Global Flag



</th>
</tr>
<tr>
<td valign="top" colspan="2">

`-h`, `--help`



</td>
<td valign="top">

Help for the `login` command.



</td>
<td valign="top">

No



</td>
</tr>
<tr>
<td valign="top" colspan="2">

`-p`, `--password`



</td>
<td valign="top">

User password



</td>
<td valign="top">

No



</td>
</tr>
<tr>
<td valign="top" colspan="2">

`--skip-ssl-validation`



</td>
<td valign="top">

Skip verification of the OAuth endpoint. Not recommended.



</td>
<td valign="top">

No



</td>
</tr>
<tr>
<td valign="top" colspan="2">

`-u`, `--user`



</td>
<td valign="top">

User ID



</td>
<td valign="top">

No



</td>
</tr>
<tr>
<td valign="top" colspan="2">

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
<td valign="top" colspan="2">

`-v`, `--verbose`



</td>
<td valign="top">

Use the verbose mode.



</td>
<td valign="top">

Yes



</td>
</tr>
<tr>
<td valign="top" colspan="2">

`–-auth-flow`



</td>
<td valign="top">

Specify the authorization flow.

You have the following two options:

-   `password`

-   `client-credentials`


If not specified, `password` flow is used.



</td>
<td valign="top">

No



</td>
</tr>
<tr>
<td valign="top">

`--client-id`



</td>
<td valign="top">

`--client-secret`



</td>
<td valign="top">

You specify these parameters if you chose the `client-credentials` authorization flow and if you created the binding object with the **default** credentials type.

See the example of a binding object created with the default credentials type: [Create a SAP Service Manager Instance and Binding](create-a-sap-service-manager-instance-and-binding-1ca5bbe.md).



</td>
<td valign="top">

No



</td>
</tr>
<tr>
<td valign="top">

`--cert`



</td>
<td valign="top">

`–-key`



</td>
<td valign="top">

You specify these parameters if you chose the `client-credentials` authorization flow and if you created the binding object with the **X.509** credentials type.

Their values are paths to files that contain public and private keys respectively that were generated upon the creation of the binding object with X.509 credentials type.

See the example of a binding object created with X.509 credentials type: [Create a SAP Service Manager Instance and Binding](create-a-sap-service-manager-instance-and-binding-1ca5bbe.md).



</td>
<td valign="top">

No



</td>
</tr>
</table>



<a name="loioa8ed7cf2a2e44dd890b7d11eb691ed75__section_wv2_4pt_pkb"/>

## Password Flow Login Examples

```
> smctl login -a https://service-management-url.com

User: user                # entering username
Password:                 # entering password (password visibility is disabled)
Logged in successfully.
```

```
> smctl login -a https://service-management-url.com -u user -p pass

Logged in successfully.
```



<a name="loioa8ed7cf2a2e44dd890b7d11eb691ed75__section_umf_3pz_qqb"/>

## Client Credentials Login Examples



### Client Credentials with the Default Type

```
> smctl login -a https://service-manager-url.com --auth-flow=client-credentials --client-id=id --client-secret=secret

          Logged in successfully.

```



### Client Credentials with the X.509 Type

```
smctl login -a https://service-manager-url.com --auth-flow=client-credentials --client-id=id --cert=cert.pem --key=key.pem

        Logged in successfully.
```



> ### Note:  
> SAP Service Manager Control \(SMCTL\) command-line also supports the explicit logout command and session timeout period of 30 minutes to better secure users' data and avoid malicious access.

**Related Information**  


[Logging in to SAP Service Manager](logging-in-to-sap-service-manager-22dea57.md)

