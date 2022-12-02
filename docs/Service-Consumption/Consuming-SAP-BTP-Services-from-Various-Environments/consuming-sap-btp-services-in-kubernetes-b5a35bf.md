<!-- loiob5a35bfa87b5444080e6e6e6d361fa20 -->

# Consuming SAP BTP Services in Kubernetes with SAP BTP Service Operator

Learn how to consume SAP Business Technology Platform \(SAP BTP\) services using the SAP Service Manager service \(technical name: service-manager\) from a Kubernetes cluster not managed by SAP.



<a name="loiob5a35bfa87b5444080e6e6e6d361fa20__section_dby_45y_q4b"/>

## Context

You consume services from an SAP BTP global account and a subaccount.

As subaccounts are bound to specific regions, choose or create a subaccount located close to your Kubernetes cluster to prevent latency drawbacks.

You manage SAP BTP services with the SAP BTP service operator from your Kubernetes cluster in a Kubernetes-native way. The SAP BTP service operator is based on the Kubernetes `CustomResourceDefinition` API with which you can manage SAP BTP services from the cluster by calling the Kubernetes APIs.

For more information, see [SAP BTP Service Operator](https://github.com/SAP/sap-btp-service-operator).

-   **[Setup](setup-e977f23.md)**  

-   **[Working with SAP BTP Service Operator](working-with-sap-btp-service-operator-0ccebd7.md "Use the SAP BTP service
		operator to consume SAP BTP
		services from your Kubernetes cluster.")**  
Use the SAP BTP service operator to consume SAP BTP services from your Kubernetes cluster.

**Related Information**  


[https://developers.sap.com/tutorials/btp-hyperscaler-extension.html](https://developers.sap.com/tutorials/btp-hyperscaler-extension.html)

