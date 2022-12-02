<!-- loiodd5faaa2c3f14cbf9d32a9886624845b -->

# Prerequisites

-   You have a Kubernetes cluster and have downloaded the Kubeconfig file:

    -   for [Google Cloud Platform](https://cloud.google.com/kubernetes-engine/docs/how-to/cluster-access-for-kubectl#kubeconfig),

    -   for [Amazon EKS](https://docs.aws.amazon.com/eks/latest/userguide/create-kubeconfig.html),

    -   for [Azure](https://docs.microsoft.com/bs-latn-ba/azure/aks/kubernetes-walkthrough#connect-to-the-cluster),

    -   for [Alibaba Cloud](https://www.alibabacloud.com/help/doc-detail/86798.htm).


-   You've set your *<KUBECONFIG\>* environment variable to instruct kubectl how to connect to your cluster:

    ```
    echo "export KUBECONFIG='<full path to your kubeconfig file>.yaml'" >> ~/.bashrc
    ```

-   kubectl v1.7 or higher, see [https://kubernetes.io/docs/tasks/tools/install-kubectl/](https://kubernetes.io/docs/tasks/tools/install-kubectl/).

-   Service Manager Control \(SMCTL\) CLI v1.10.1, see [Service Manager CLI Releases](https://github.com/Peripli/service-manager-cli/releases),

-   Helm \(a package manager for Kubernetes\) v3.1.2, see [Helm Installation Instructions](https://helm.sh/docs/intro/install/).

-   You have subscribed to the SAP Service Manager, see [Subscribing to SAP Service Manager \[Feature Set A\]](../SAP-Service-Manager/subscribing-to-sap-service-manager-feature-set-a-274d049.md).

-   You have assigned the *Subaccount Service Administrator* *role collection*, see [Assign the Subaccount Service Administrator Collection](../SAP-Service-Manager/assign-the-subaccount-service-administrator-collection-0735965.md).

-   You have logged in to the SAP Service Manager, see [Logging in to SAP Service Manager](../SAP-Service-Manager/logging-in-to-sap-service-manager-22dea57.md).


