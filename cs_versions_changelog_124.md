---

copyright: 
  years: 2022, 2022
lastupdated: "2022-08-01"

keywords: kubernetes, containers

subcollection: containers


---

# Kubernetes version 1.24 change log
{: #changelog_124}

View information about version changes for major, minor, and patch updates that are available for your {{site.data.keyword.containerlong}} clusters that run version 1.24. Changes include updates to Kubernetes and {{site.data.keyword.cloud_notm}} Provider components.
{: shortdesc}

## Overview
{: #changelog_overview_124}

Unless otherwise noted in the change logs, the {{site.data.keyword.containerlong_notm}} provider version enables Kubernetes APIs and features that are at beta. Kubernetes alpha features, which are subject to change, are disabled.

For more information about major, minor, and patch versions and preparation actions between minor versions, see [Kubernetes versions](/docs/containers?topic=containers-cs_versions).
{: tip}

Check the [Security Bulletins on {{site.data.keyword.cloud_notm}} Status](https://cloud.ibm.com/status?component=containers-kubernetes&selected=security) for security vulnerabilities that affect {{site.data.keyword.containerlong_notm}}. You can filter the results to view only Kubernetes Cluster security bulletins that are relevant to {{site.data.keyword.containerlong_notm}}. Change log entries that address other security vulnerabilities but don't also refer to an {{site.data.keyword.IBM_notm}} security bulletin are for vulnerabilities that are not known to affect {{site.data.keyword.containerlong_notm}} in normal usage. If you run privileged containers, run commands on the workers, or execute untrusted code, then you might be at risk.

Some change logs are for _worker node fix packs_, and apply only to worker nodes. You must [apply these patches](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_update) to ensure security compliance for your worker nodes. These worker node fix packs can be at a higher version than the master because some build fix packs are specific to worker nodes. Other change logs are for _master fix packs_, and apply only to the cluster master. Master fix packs might not be automatically applied. You can choose to [apply them manually](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_update). For more information about patch types, see [Update types](/docs/containers?topic=containers-cs_versions#update_types).
{: note}

## Version 1.24 change log
{: #124_changelog}

Review the version 1.24 change log.
{: shortdesc}













### Change log for worker node fix pack 1.24.3_1532, released 01 August 2022
{: #1243_1532}

The following table shows the changes that are in the worker node fix pack 1.24.3_1532. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 18.04 packages |N/A|N/A| Worker node kernel & package updates for [CVE-2022-27404](https://nvd.nist.gov/vuln/detail/CVE-2022-27404){: external},[CVE-2022-27405](https://nvd.nist.gov/vuln/detail/CVE-2022-27405){: external},[CVE-2022-27406](https://nvd.nist.gov/vuln/detail/CVE-2022-27406){: external},[CVE-2022-29217](https://nvd.nist.gov/vuln/detail/CVE-2022-29217){: external},[CVE-2022-31782](https://nvd.nist.gov/vuln/detail/CVE-2022-31782){: external}. |
| Kubernetes | 1.24.2 | 1.24.3 | For more information, see the [change log](https://github.com/kubernetes/kubernetes/releases/tag/v1.24.3){: external}. |
{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.24.2_1529" caption-side="top"}

### Change log for master fix pack 1.24.3_1531, released 26 July 2022
{: #1243_1531}

The following table shows the changes that are in the master fix pack 1.24.3_1531. Master patch updates are applied automatically. 
{: shortdesc}


| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Calico | v3.23.1 | v3.23.3 | See the [Calico release notes](https://docs.projectcalico.org/releases){: external}. Updated the Calico custom resource definitions to include `preserveUnknownFields: false`. |
| Cluster health image | v1.3.8 | v1.3.9 | Updated `Go` dependencies and to use `Go` version `1.18.4`. Fixed minor typo in addon `daemonset not available` health status. |
| Gateway-enabled cluster controller | 1680 | 1792 | Updated to use `Go` version `1.17.11`. Updated image for [CVE-2022-2097](https://nvd.nist.gov/vuln/detail/CVE-2022-2097){: external} and [CVE-2022-29458](https://nvd.nist.gov/vuln/detail/CVE-2022-29458){: external}. |
| GPU device plug-in and installer | 2b0b6d1 | d8f1be0 | Updated `Go` dependencies and to use `Go` version `1.18.3`. |
| {{site.data.keyword.IBM_notm}} Calico extension | 980 | 997 | Updated to use `Go` version `1.17.11`. Updated universal base image (UBI) to version `8.6-854` to resolve CVEs. |
| {{site.data.keyword.cloud_notm}} Block Storage driver and plug-in | v2.2.6 | v2.2.8 | Updated to use `Go` version `1.18.3`. Updated universal base image (UBI) to version `8.6-854` to resolve CVEs. |
| {{site.data.keyword.cloud_notm}} Controller Manager | v1.24.1-7 | v1.24.2-8 | Updated `Go` dependencies and to use `Go` version `1.18.3`. Updated to support the Kubernetes `1.24.2` release. [Disabling load balancer NodePort allocation](https://kubernetes.io/docs/concepts/services-networking/service/#load-balancer-nodeport-allocation){: external} is now prevented for VPC load balancers. |
| {{site.data.keyword.filestorage_full_notm}} plug-in and monitor | 410 | 412 | Updated to use `Go` version `1.18.3`. Updated universal base image (UBI) to version `8.6-854` to resolve CVEs. Improved Kubernetes resource watch configuration. |
| {{site.data.keyword.cloud_notm}} RBAC Operator | 8c96932 | 0a187a4 | Updated universal base image (UBI) to resolve CVEs. |
| Key Management Service provider | v2.5.6 | v2.5.7 | Updated `Go` dependencies and to use `Go` version `1.18.4`. |
| Kubernetes | v1.24.2 | v1.24.3 | See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.24.3){: external}. |
| Kubernetes NodeLocal DNS cache | 1.22.2 | 1.22.5 | See the [Kubernetes NodeLocal DNS cache release notes](https://github.com/kubernetes/dns/releases/tag/1.22.5){: external}. |
| Load balancer and load balancer monitor for {{site.data.keyword.cloud_notm}} Provider | 1998 | 2058 | Updated image for [CVE-2022-2097](https://nvd.nist.gov/vuln/detail/CVE-2022-2097){: external}. |
| Portieris admission controller | v0.12.4 | v0.12.5 | See the [Portieris admission controller release notes](https://github.com/{{site.data.keyword.IBM_notm}}/portieris/releases/tag/v0.12.5){: external}. |

{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.24.2_1526" caption-side="top"}

### Change log for worker node fix pack 1.24.2_1529, released 18 July 2022
{: #1242_1529}

The following table shows the changes that are in the worker node fix pack 1.24.2_1529. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 18.04 packages | 4.15.0-188 | 4.15.0-189 | Worker node kernel & package updates for [CVE-2015-20107](https://nvd.nist.gov/vuln/detail/CVE-2015-20107){: external}, [CVE-2022-2097](https://nvd.nist.gov/vuln/detail/CVE-2022-2097){: external},[CVE-2022-22747](https://nvd.nist.gov/vuln/detail/CVE-2022-22747){: external}, [CVE-2022-24765](https://nvd.nist.gov/vuln/detail/CVE-2022-24765){: external}, [CVE-2022-29187](https://nvd.nist.gov/vuln/detail/CVE-2022-29187){: external},[CVE-2022-34480](https://nvd.nist.gov/vuln/detail/CVE-2022-34480){: external},[CVE-2022-34903](https://nvd.nist.gov/vuln/detail/CVE-2022-34903){: external}. |
| Kubernetes |N/A|N/A|N/A|
{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.24.2_1527" caption-side="top"}

### Change log for worker node fix pack 1.24.2_1527, released 05 July 2022
{: #1242_1527}

The following table shows the changes that are in the worker node fix pack 1.24.2_1527. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 18.04 packages | 4.15.0-187 | 4.15.0-188 | Worker node kernel & package updates for [CVE-2022-1292](https://nvd.nist.gov/vuln/detail/CVE-2022-1292){: external},[CVE-2022-2068](https://nvd.nist.gov/vuln/detail/CVE-2022-2068){: external},[CVE-2022-2084](https://nvd.nist.gov/vuln/detail/CVE-2022-2084){: external},[CVE-2022-28388](https://nvd.nist.gov/vuln/detail/CVE-2022-28388){: external},[CVE-2022-32206](https://nvd.nist.gov/vuln/detail/CVE-2022-32206){: external},[CVE-2022-32208](https://nvd.nist.gov/vuln/detail/CVE-2022-32208){: external}. |
| Kubernetes |N/A|N/A|N/A|

{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.24.2_1526" caption-side="top"}

### Change log for master fix pack 1.24.2_1526, released 22 June 2022
{: #master_1242_1526}

The following table shows the changes that are in the master fix pack 1.24.2_1526. Master patch updates are applied automatically. 
{: shortdesc}


| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| {{site.data.keyword.cloud_notm}} Block Storage driver and plug-in | v2.2.4 | v2.2.6 | Bug fixes for the driver installation. Block plugin base images were updated to `ubi`: `8.6-751.1655117800` for CVE-2022-1271 |
| Kubernetes | v1.24.1 | v1.24.2 | See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.24.2){: external}. |
| Kubernetes add-on resizer | 1.8.14 | 1.8.15 | See the [Kubernetes add-on resizer release notes](https://github.com/kubernetes/autoscaler/releases/tag/addon-resizer-1.18.15){: external}. |
{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.24.1_1523" caption-side="top"}

### Change log for worker node fix pack 1.24.2_1526, released 20 June 2022
{: #1242_1526}

The following table shows the changes that are in the worker node fix pack 1.24.2_1526. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 18.04 packages | 4.15.0-180 | 4.15.0-187 | Worker node kernel & package updates for [CVE-2021-46790](https://nvd.nist.gov/vuln/detail/CVE-2021-46790){: external}, [CVE-2022-1304](https://nvd.nist.gov/vuln/detail/CVE-2022-1304){: external}, [CVE-2022-1419](https://nvd.nist.gov/vuln/detail/CVE-2022-1419){: external}, [CVE-2022-1966](https://nvd.nist.gov/vuln/detail/CVE-2022-1966){: external}, [CVE-2022-21123](https://nvd.nist.gov/vuln/detail/CVE-2022-21123){: external}, [CVE-2022-21125](https://nvd.nist.gov/vuln/detail/CVE-2022-21125){: external}, [CVE-2022-21166](https://nvd.nist.gov/vuln/detail/CVE-2022-21166){: external}, [CVE-2022-21499](https://nvd.nist.gov/vuln/detail/CVE-2022-21499){: external}, [CVE-2022-28390](https://nvd.nist.gov/vuln/detail/CVE-2022-28390){: external}, [CVE-2022-30783](https://nvd.nist.gov/vuln/detail/CVE-2022-30783){: external}, [CVE-2022-30784](https://nvd.nist.gov/vuln/detail/CVE-2022-30784){: external}, [CVE-2022-30785](https://nvd.nist.gov/vuln/detail/CVE-2022-30785){: external}, [CVE-2022-30786](https://nvd.nist.gov/vuln/detail/CVE-2022-30786){: external}, [CVE-2022-30787](https://nvd.nist.gov/vuln/detail/CVE-2022-30787){: external}, [CVE-2022-30788](https://nvd.nist.gov/vuln/detail/CVE-2022-30788){: external}, [CVE-2022-30789](https://nvd.nist.gov/vuln/detail/CVE-2022-30789){: external}. |
| Haproxy | 468c09 | 04f862 | [CVE-2022-1271](https://nvd.nist.gov/vuln/detail/CVE-2022-1271){: external}. |
| containerd | v1.6.4 | v1.6.6 | See the [change log](https://github.com/containerd/containerd/releases/tag/v1.6.6){: external}, the [security bulletin](https://www.ibm.com/support/pages/node/6597989){: external} for [CVE-2022-31030](https://nvd.nist.gov/vuln/detail/CVE-2022-31030){: external}, and the [security bulletin](https://www.ibm.com/support/pages/node/6598049){: external} for [CVE-2022-29162](https://nvd.nist.gov/vuln/detail/CVE-2022-29162){: external}. |
| Kubernetes | 1.24.1 | 1.24.2 | For more information, see the [change log](https://github.com/kubernetes/kubernetes/releases/tag/v1.24.2){: external}. | 
{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.24.1_1522" caption-side="top"}

### Change log for master fix pack 1.24.1_1523 and worker node fix pack 1.24.1_1522, released 9 June 2022
{: #1241_1522}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Calico | v3.21.5 | v3.23.1 | See the [Calico release notes](https://projectcalico.docs.tigera.io/archive/v3.23/release-notes/){: external}. The **default** BGP configuration found in the `default` [BGPConfiguration](https://projectcalico.docs.tigera.io/reference/resources/bgpconfig){: external} resource has been updated to set `nodeMeshMaxRestartTime` to `30m`.  This default change is only applied if the cluster does not have a custom BGP configuration. The previous default value was `120s`. |
| CoreDNS | 1.8.7 | 1.9.2 | See the [CoreDNS release notes](https://github.com/coredns/coredns/blob/v1.9.2/notes/coredns-1.9.2.md){: external}. |
| etcd | v3.4.18 | v3.5.4 | See the [etcd release notes](https://github.com/etcd-io/etcd/releases/v3.5.4){: external}. |
| GPU device plug-in and installer | 382ada9 | 2b0b6d1 | Updated image for [CVE-2018-25032](https://nvd.nist.gov/vuln/detail/CVE-2018-25032){: external}, [CVE-2021-3634](https://nvd.nist.gov/vuln/detail/CVE-2021-3634){: external}, [CVE-2021-3737](https://nvd.nist.gov/vuln/detail/CVE-2021-3737){: external} and [CVE-2021-4189](https://nvd.nist.gov/vuln/detail/CVE-2021-4189){: external}. |
| {{site.data.keyword.blockstoragefull}} driver and plug-in | None | v2.2.5 | The {{site.data.keyword.blockstoragefull}} driver and plug-in component is now installed on clusters running classic infrastructure. |
| {{site.data.keyword.cloud_notm}} Controller Manager | v1.23.7-4 | v1.24.1-4 | Updated to support the Kubernetes `1.24.1` release and `Go` version `1.18.2`. [Disabling load balancer NodePort allocation](https://kubernetes.io/docs/concepts/services-networking/service/#load-balancer-nodeport-allocation){: external} is not supported for VPC load balancers. |
| Kubernetes | v1.23.7 | v1.24.1 | See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.24.1){: external}. |
| Kubernetes configuration | N/A | N/A | Updated the [feature gate configuration](/docs/containers?topic=containers-service-settings#feature-gates). |
| Kubernetes CSI snapshotter CRDs | v4.2.1 | v5.0.1 | See the [Kubernetes container storage interface (CSI) snapshotter release notes](https://github.com/kubernetes-csi/external-snapshotter/releases/tag/v5.0.1){: external}. |
| Kubernetes Dashboard | v2.4.0 | v2.5.0 | See the [Kubernetes Dashboard release notes](https://github.com/kubernetes/dashboard/releases/tag/v2.5.0){: external}. |
| Kubernetes DNS autoscaler | 1.8.4 | 1.8.5 | See the [Kubernetes DNS autoscaler release notes](https://github.com/kubernetes-sigs/cluster-proportional-autoscaler/releases/tag/1.8.5){: external}. |
| Kubernetes Metrics Server | v0.6.0 | v0.6.0 | Updated to run with a highly available configuration. For more information on this configuration, see the [Kubernetes Metrics Server release notes](https://github.com/kubernetes-sigs/metrics-server/releases/tag/v0.6.0){: external}. |
| Kubernetes NodeLocal DNS cache | 1.21.4 | 1.22.2 | See the [Kubernetes NodeLocal DNS cache release notes](https://github.com/kubernetes/dns/releases/tag/1.22.2){: external}. |
| Pause container image | 3.6 | 3.7 | See the [pause container image release notes](https://github.com/kubernetes/kubernetes/blob/master/build/pause/CHANGELOG.md){: external}. | 
{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.23.7_1531 (master) and 1.23.7_1532 (worker node)" caption-side="top"}
