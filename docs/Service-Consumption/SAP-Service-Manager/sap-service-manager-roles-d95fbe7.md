<!-- loiod95fbe7f48fa4f4da2ecfc8eae7fab9a -->

# SAP Service Manager Roles



Describes the SAP Service Manager roles.


<table>
<tr>
<th valign="top">

Roles



</th>
<th valign="top">

Description



</th>
<th valign="top">

Scopes



</th>
</tr>
<tr>
<td valign="top">

Subaccount Service Administrator



</td>
<td valign="top">

Allows to manage resources in the subaccount in which the *service-manager* instance of this plan was created. This includes managing subaccount scoped brokers, platforms, instances and bindings and also reading services, plans and visibilities.



</td>
<td valign="top">

-   subaccount.broker.manage
-   subaccount.broker.read
-   subaccount.platform.manage
-   subaccount.platform.read
-   subaccount.service\_instance.read
-   subaccount.service\_instance.manage
-   subaccount.service\_binding.read
-   subaccount.service\_binding.manage
-   subaccount.service\_plan.read
-   subaccount.service\_offering.read



</td>
</tr>
<tr>
<td valign="top">

Subaccount Service Viewer \[Feature Set B\]



</td>
<td valign="top">

Allows read-only access to the resources in the subaccount in which the*service-manager* instance was created. This includes reading subaccount scoped brokers, platforms, instances and bindings, services, plans, and visibilities.



</td>
<td valign="top">

-   subaccount.broker.read
-   subaccount.platform.read
-   subaccount.service\_instance.read
-   subaccount.service\_binding.read
-   subaccount.service\_plan.read
-   subaccount.service\_offering.read



</td>
</tr>
</table>

