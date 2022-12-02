<!-- loio4613e39f89bf485fb38353642791ca3f -->

# list services/offering



<a name="loio4613e39f89bf485fb38353642791ca3f__section_xcr_2nt_pkb"/>

## Overview



***btp list services/offering*** 

List the services your subaccount is entitled to use in your runtime environment.

To list services that you can consume in a Cloud Foundry or Kubernetes-native way, add the `--environment` parameter.



<a name="loio4613e39f89bf485fb38353642791ca3f__section_fp5_f4t_pkb"/>

## Usage

`btp list services/offering [parameters]`



<a name="loio4613e39f89bf485fb38353642791ca3f__section_hdy_lpt_pkb"/>

## Parameters


<table>
<tr>
<th valign="top" colspan="2">

Required



</th>
</tr>
<tr>
<td valign="top">

`-sa`, `--subaccount`



</td>
<td valign="top">

The ID of the subaccount asociated with service offerings. You can omit this parameter if you have already set the context to the subaccount using `btp target --subaccount ID`.



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

`--environment`



</td>
<td valign="top">

List services that are to be consumed in a Cloud Foundry or Kubernetes-native way. Valid values are: `cloudfoundry`, `kubernetes`.

If not used, services that you can consume in other environments by creating the binding objects are returned.

For more information, see [Consuming Services in Other Environments Using the SAP Service Manager Instances](../Consuming-SAP-BTP-Services-from-Various-Environments/consuming-services-in-other-environments-0714ac2.md).



</td>
</tr>
<tr>
<td valign="top">

`--labels-filter`



</td>
<td valign="top">

Filters the response based on the label query. For example, to list all the service offerings associated with the testing environment, use `environment eq 'test'`.

For the full list of the available query options, see [Filtering Parameters and Operators](filtering-parameters-and-operators-3331c6e.md)

.



</td>
</tr>
<tr>
<td valign="top">

`--fields-filter`



</td>
<td valign="top">

Filters the response based on the field query. For example, use `name eq 'my service offering name'`.

For the full list of the available query options, see [Filtering Parameters and Operators](filtering-parameters-and-operators-3331c6e.md).



</td>
</tr>
</table>

