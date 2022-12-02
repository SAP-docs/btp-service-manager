<!-- loio917a8a7c926444cf99d0230c82db1831 -->

# SAP Service Manager Broker Plans



Describes the SAP Service Manager plans.


<table>
<tr>
<th valign="top">

Broker Plans



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

Subaccount-admin



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

Subaccount-audit



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
<tr>
<td valign="top">

Container



</td>
<td valign="top">

Allows management of service instances and bindings in a reduced scope that corresponds to the service instance. Instances created using the binding credentials of the container instance are visible from the instance itself and from instances of the subaccount-\* plans, but not from other container instances.



</td>
<td valign="top">

-   subaccount.service\_instance.read
-   subaccount.service\_instance.manage
-   subaccount.service\_binding.read
-   subaccount.service\_binding.manage
-   subaccount.service\_plan.read

-   subaccount.service\_offering.read




</td>
</tr>
</table>

