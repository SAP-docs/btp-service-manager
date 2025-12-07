<!-- loio2f4c42b28848491c8a57def106869ef7 -->

# share-instance



<a name="loio2f4c42b28848491c8a57def106869ef7__section_xcr_2nt_pkb"/>

## Overview



`smctl share-instance` 

Share a service instance so that it can be consumed across different environments in a subaccount.

Instance can be shared only in a subaccount and if it was created with the plan that supports instance sharing. For more information, see the documentation of the service whose instance you want to share. To check if the service instance was created with a shareable plan, use `smctl list-plans`, search for the `shareable` parameter, and verify that its value is `true`.



<a name="loio2f4c42b28848491c8a57def106869ef7__section_fp5_f4t_pkb"/>

## Usage

`smctl share-instance [name] --id service-instance-id`



<a name="loio2f4c42b28848491c8a57def106869ef7__section_hdy_lpt_pkb"/>

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

Help for `share` command.

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

`--id`

</td>
<td valign="top">

The ID of the instance to share.

</td>
<td valign="top">

No

</td>
</tr>
</table>



<a name="loio2f4c42b28848491c8a57def106869ef7__section_wv2_4pt_pkb"/>

## Example

Execution:

```
> smctl share-instance sample-instance --id 32bbbee7-a9d0-48e4-a434-bf47bc471a48
 
```

Response:

```
> smctl provision sample-instance overview-service simple --mode sync

| ID               | 32bbbee7-a9d0-48e4-a434-bf47bc471a48                |
| Name             | sample-instance                                 |
| Service Plan ID  | 86350d33-4e51-4ce2-919c-233ece4a9806                |
| Platform ID      | service-manager                                     |
| Shared           | true                                                |
| Created          | 2021-06-16T09:30:01.99892Z                          |
| Updated          | 2021-06-16T09:33:27.596884Z                         |
| Ready            | true                                                |
| Usable           | true                                                |
| Labels           | subaccount_id=27f8e23b-5a21-4a76-8a86-344a2bdd6bb1  |
```

