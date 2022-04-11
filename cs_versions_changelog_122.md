---

copyright:
 years: 2014, 2022
lastupdated: "2022-04-11"

keywords: kubernetes, versions, update, upgrade, BOM, bill of materials, versions, patch, 1.23

subcollection: containers

---

{{site.data.keyword.attribute-definition-list}}


# Kubernetes version 1.22 change log
{: #changelog_122}

View information about version changes for major, minor, and patch updates that are available for your {{site.data.keyword.containerlong}} clusters that run version 1.22. Changes include updates to Kubernetes and {{site.data.keyword.cloud_notm}} Provider components.
{: shortdesc}

## Overview
{: #changelog_overview}

Unless otherwise noted in the change logs, the {{site.data.keyword.containerlong_notm}} provider version enables Kubernetes APIs and features that are at beta. Kubernetes alpha features, which are subject to change, are disabled.

For more information about major, minor, and patch versions and preparation actions between minor versions, see [Kubernetes versions](/docs/containers?topic=containers-cs_versions).
{: tip}

Check the [Security Bulletins on {{site.data.keyword.cloud_notm}} Status](https://cloud.ibm.com/status?component=containers-kubernetes&selected=security) for security vulnerabilities that affect {{site.data.keyword.containerlong_notm}}. You can filter the results to view only Kubernetes Cluster security bulletins that are relevant to {{site.data.keyword.containerlong_notm}}. Change log entries that address other security vulnerabilities but don't also refer to an {{site.data.keyword.IBM_notm}} security bulletin are for vulnerabilities that are not known to affect {{site.data.keyword.containerlong_notm}} in normal usage. If you run privileged containers, run commands on the workers, or execute untrusted code, then you might be at risk.

Some change logs are for _worker node fix packs_, and apply only to worker nodes. You must [apply these patches](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_update) to ensure security compliance for your worker nodes. These worker node fix packs can be at a higher version than the master because some build fix packs are specific to worker nodes. Other change logs are for _master fix packs_, and apply only to the cluster master. Master fix packs might not be automatically applied. You can choose to [apply them manually](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_update). For more information about patch types, see [Update types](/docs/containers?topic=containers-cs_versions#update_types).
{: note}

## Version 1.22 change log
{: #122_changelog}

Review the version 1.22 changelog.
{: shortdesc}

### Change log for worker node fix pack 1.22.8_1548, released 11 April 2022
{: #1228_1548}

The following table shows the changes that are in the worker node fix pack 1.22.8_1548. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 18.04 packages | 4.15.0-173-generic | 4.15.0-175-generic | Kernel and package updates for [CVE-2018-25032](https://nvd.nist.gov/vuln/detail/CVE-2018-25032) [CVE-2021-3426](https://nvd.nist.gov/vuln/detail/CVE-2021-3426) [CVE-2021-4189](https://nvd.nist.gov/vuln/detail/CVE-2021-4189) [CVE-2022-0391](https://nvd.nist.gov/vuln/detail/CVE-2022-0391) [CVE-2022-21712](https://nvd.nist.gov/vuln/detail/CVE-2022-21712) [CVE-2022-21716](https://nvd.nist.gov/vuln/detail/CVE-2022-21716) [CVE-2022-25308](https://nvd.nist.gov/vuln/detail/CVE-2022-25308) [CVE-2022-25309](https://nvd.nist.gov/vuln/detail/CVE-2022-25309) [CVE-2022-25310](https://nvd.nist.gov/vuln/detail/CVE-2022-25310) [CVE-2022-27666](https://nvd.nist.gov/vuln/detail/CVE-2022-27666). | 

{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.22.8_1546" caption-side="top"}


### Change log for master fix pack 1.22.8_1547, released 6 April 2022
{: #1228_1547}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Load balancer and load balancer monitor for {{site.data.keyword.cloud_notm}} Provider | 1865 | 1899 | Revert setting gratuitous arp on LBv1. |
{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.22.8_1545" caption-side="top"}



### Change log for master fix pack 1.22.8_1545, released 30 March 2022
{: #1228_1545}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Calico | v3.20.4 | v3.21.4 | See the [Calico release notes](https://projectcalico.docs.tigera.io/archive/v3.21/release-notes/){: external}. |
| Cluster health image | v1.3.3 | v1.3.5 | Updated image to fix CVEs [CVE-2021-3999](https://nvd.nist.gov/vuln/detail/CVE-2021-3999){: external}, [CVE-2022-23218](https://nvd.nist.gov/vuln/detail/CVE-2022-23218){: external}, [CVE-2022-23219](https://nvd.nist.gov/vuln/detail/CVE-2022-23219){: external}.  Updated golang dependencies. |
| Gateway-enabled cluster controller | 1653 | 1669 | Updated to use `Go` version `1.17.8`. |
| GPU device plug-in and installer | d7daae6 | 13677d2 | Updated GPU images to resolve CVEs. |
| IBM Calico extension | 929 | 950 | Updated to use `Go` version `1.17.8`. Updated universal base image (UBI) to resolve CVEs. |
| IBM Cloud Controller Manager | v1.22.7-2 | v1.22.8-3 | Updated to support the `Kubernetes 1.22.8` release and to use `Go` version `1.16.15`. |
| IBM Cloud {{site.data.keyword.filestorage_short}} plug-in and monitor | 405 | 407 | Updated `Go` to version `1.16.14`.  Updated `UBI` image to version `8.5-240`. |
| IBM Cloud RBAC Operator | 0fc9949 | 6c43ef1 | Upgraded `Go` packages to resolve vulnerabilities |
| Key Management Service provider | v2.4.3 | v2.5.3 | Updated to use `Go` version `1.17.8`. Updated golang dependencies.  Fixed CVE [CVE-2022-24407](https://nvd.nist.gov/vuln/detail/CVE-2022-24407){: external} |
| Konnectivity agent | v0.0.27_a6b5248a_323_iks | v0.0.30_331_iks | See the [Konnectivity release notes](https://github.com/kubernetes-sigs/apiserver-network-proxy/releases/tag/v0.0.30){: external}.  Updated to use `Go` version `1.17.8`. |
| Konnectivity server | v0.0.27_a6b5248a_323_iks | v0.0.30_331_iks | See the [Konnectivity release notes](https://github.com/kubernetes-sigs/apiserver-network-proxy/releases/tag/v0.0.30){: external}.  Updated to use `Go` version `1.17.8`. |
| Kubernetes | v1.22.7 | v1.22.8 | See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.22.8){: external}. |
| Load balancer and Load balancer monitor for IBM Cloud Provider | 1747 | 1865 | Updated the image to resolve CVEs. Updated to use `Go` version `1.17.8`. Set gratuitous arp at the right time on LBv1. |
| Operator Lifecycle Manager | 0.16.1-IKS-15 | 0.16.1-IKS-16 | Resolve [CVE-2022-0778](https://nvd.nist.gov/vuln/detail/CVE-2022-0778){: external}. |
| Portieris admission controller | v0.12.2 | v0.12.3 | See the [Portieris admission controller release notes](https://github.com/IBM/portieris/releases/tag/v0.12.3){: external} |
{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.22.7_1541" caption-side="top"}

### Change log for worker node fix pack 1.22.8_1546, released 28 March 2022
{: #1227_1546}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 18.04 packages | 4.15.0-171-generic | 4.15.0-173-generic | Kernel and package updates for [CVE-2021-20193](https://nvd.nist.gov/vuln/detail/CVE-2021-20193){: external}, [CVE-2021-25220](https://nvd.nist.gov/vuln/detail/CVE-2021-25220){: external}, [CVE-2021-3506](https://nvd.nist.gov/vuln/detail/CVE-2021-3506){: external}, [CVE-2022-0435](https://nvd.nist.gov/vuln/detail/CVE-2022-0435){: external}, [CVE-2022-0492](https://nvd.nist.gov/vuln/detail/CVE-2022-0492){: external}, [CVE-2022-0778](https://nvd.nist.gov/vuln/detail/CVE-2022-0778){: external}, [CVE-2022-0847](https://nvd.nist.gov/vuln/detail/CVE-2022-0847){: external}, [CVE-2022-23308](https://nvd.nist.gov/vuln/detail/CVE-2022-23308){: external}. |
| HA proxy | 15198f | b40c07 | [CVE-2021-45960](https://nvd.nist.gov/vuln/detail/CVE-2021-45960){: external}, [CVE-2021-46143](https://nvd.nist.gov/vuln/detail/CVE-2021-46143){: external}, [CVE-2022-22822](https://nvd.nist.gov/vuln/detail/CVE-2022-22822){: external}, [CVE-2022-22823](https://nvd.nist.gov/vuln/detail/CVE-2022-22823){: external}, [CVE-2022-22824](https://nvd.nist.gov/vuln/detail/CVE-2022-22824){: external}, [CVE-2022-22825](https://nvd.nist.gov/vuln/detail/CVE-2022-22825){: external}, [CVE-2022-22826](https://nvd.nist.gov/vuln/detail/CVE-2022-22826){: external}, [CVE-2022-22827](https://nvd.nist.gov/vuln/detail/CVE-2022-22827){: external}, [CVE-2022-23852](https://nvd.nist.gov/vuln/detail/CVE-2022-23852){: external}, [CVE-2022-25235](https://nvd.nist.gov/vuln/detail/CVE-2022-25235){: external}, [CVE-2022-25236](https://nvd.nist.gov/vuln/detail/CVE-2022-25236){: external}, [CVE-2022-25315](https://nvd.nist.gov/vuln/detail/CVE-2022-25315){: external}, [CVE-2021-3999](https://nvd.nist.gov/vuln/detail/CVE-2021-3999){: external}, [CVE-2022-23218](https://nvd.nist.gov/vuln/detail/CVE-2022-23218){: external}, [CVE-2022-23219](https://nvd.nist.gov/vuln/detail/CVE-2022-23219){: external}, [CVE-2022-23308](https://nvd.nist.gov/vuln/detail/CVE-2022-23308){: external}, [CVE-2021-23177](https://nvd.nist.gov/vuln/detail/CVE-2021-23177){: external}, [CVE-2021-31566](https://nvd.nist.gov/vuln/detail/CVE-2021-31566){: external}. |
Kubernetes | 1.22.7 | 1.22.8 | See [changelogs](https://github.com/kubernetes/kubernetes/releases/tag/v1.22.8){: external}. |
{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.22.7_1543" caption-side="top"}

### Change log for worker node fix pack 1.22.7_1543, released 14 March 2022
{: #1227_1543}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Containerd | v1.5.9 | v1.5.10 | See the [change log](https://github.com/containerd/containerd/releases/tag/v1.5.10){: external} and the [security bulletin](https://www.ibm.com/support/pages/node/6564653){: external}. |
| Ubuntu 18.04 packages | 4.15.0-169-generic | 4.15.0-171-generic | Kernel and package updates for [CVE-2016-10228](https://nvd.nist.gov/vuln/detail/CVE-2016-10228){: external}, [CVE-2019-25013](https://nvd.nist.gov/vuln/detail/CVE-2019-25013){: external}, [CVE-2020-27618](https://nvd.nist.gov/vuln/detail/CVE-2020-27618){: external}, [CVE-2020-29562](https://nvd.nist.gov/vuln/detail/CVE-2020-29562){: external}, [CVE-2020-6096](https://nvd.nist.gov/vuln/detail/CVE-2020-6096){: external}, [CVE-2021-3326](https://nvd.nist.gov/vuln/detail/CVE-2021-3326){: external}, [CVE-2021-35942](https://nvd.nist.gov/vuln/detail/CVE-2021-35942){: external}, [CVE-2021-3999](https://nvd.nist.gov/vuln/detail/CVE-2021-3999){: external}, [CVE-2022-0001](https://nvd.nist.gov/vuln/detail/CVE-2022-0001){: external}, [CVE-2022-23218](https://nvd.nist.gov/vuln/detail/CVE-2022-23218){: external}, [CVE-2022-23219](https://nvd.nist.gov/vuln/detail/CVE-2022-23219){: external}, [CVE-2022-25313](https://nvd.nist.gov/vuln/detail/CVE-2022-25313){: external}, [CVE-2022-25314](https://nvd.nist.gov/vuln/detail/CVE-2022-25314){: external}, [CVE-2022-25315](https://nvd.nist.gov/vuln/detail/CVE-2022-25315){: external}. |
{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.22.7_1542" caption-side="top"}

### Change log for master fix pack 1.22.7_1541, released 3 March 2022
{: #1227_1541}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Calico | v3.20.3 | v3.20.4 | See the [Calico release notes](https://projectcalico.docs.tigera.io/releases){: external}. |
| Cluster health image | v1.2.21 | v1.3.3 | Updated `golang.org/x/crypto` to `v0.0.0-20220214200702-86341886e292`. Adds fix for [CVE-2021-43565](https://www.whitesourcesoftware.com/vulnerability-database/CVE-2021-43565){: external}. Adds Golang dependency updates. |
| Gateway-enabled cluster controller | 1586 | 1653 | Updated to use `Go` version `1.17.7` and updated `Go` modules to fix CVEs. |
| GPU device plug-in and installer | eefc4ae | d7daae6 | Updated GPU images to resolve CVEs. |
| IBM Calico extension | 923 | 929 | Updated universal base image (UBI) to the `8.5-230` version to resolve CVEs. Updated to use `Go` version `1.16.13`. |
| IBM Cloud Controller Manager | v1.22.6-1 | v1.22.7-2 | Updated to support the Kubernetes `1.22.7` release and to use `Go` version `1.16.14`. |
| IBM Cloud {{site.data.keyword.filestorage_short}} plug-in and monitor | 404 | 405 | Adds fix for [CVE-2021-3538](https://www.whitesourcesoftware.com/vulnerability-database/CVE-2021-3538){: external} and adds dependency updates. |
| Key Management Service provider | v2.4.0 | v2.4.3 | Updated `golang.org/x/crypto` to `v0.0.0-20220214200702-86341886e292`. Adds fix for [CVE-2021-43565](https://www.whitesourcesoftware.com/vulnerability-database/CVE-2021-43565){: external}. Adds Golang dependency updates. |
| Konnectivity agent | v0.0.27_309_iks | v0.0.27_a6b5248a_323_iks | See the [Konnectivity release notes](https://github.com/kubernetes-sigs/apiserver-network-proxy/releases/tag/v0.0.27){: external}.  Updated universal base image (UBI) to the `8.5-230` version to resolve CVEs. Updated to use `Go` version `1.17.5`. |
| Konnectivity server | v0.0.27_309_iks | v0.0.27_a6b5248a_323_iks | See the [Konnectivity release notes](https://github.com/kubernetes-sigs/apiserver-network-proxy/releases/tag/v0.0.27){: external}.  Updated universal base image (UBI) to the `8.5-230` version to resolve CVEs. Updated to use `Go` version `1.17.5`. |
| Kubernetes | v1.22.6 | v1.22.7 | See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.22.7){: external}. |
{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.22.6_1537" caption-side="top"}

### Change log for worker node fix pack 1.22.7_1542, released 28 February 2022
{: #1227_1542}

| Component | Previous | Current | Description |
| --------- | -------- | ------- | ----------- |
| Ubuntu 18.04 packages | 4.15.0-167-generic | 4.15.0-169-generic | Kernel and package updates for [CVE-2021-4083](https://nvd.nist.gov/vuln/detail/CVE-2021-4083){: external}, [CVE-2021-4155](https://nvd.nist.gov/vuln/detail/CVE-2021-4155){: external}, [CVE-2021-45960](https://nvd.nist.gov/vuln/detail/CVE-2021-45960){: external}, [CVE-2021-46143](https://nvd.nist.gov/vuln/detail/CVE-2021-46143){: external}, [CVE-2022-0330](https://nvd.nist.gov/vuln/detail/CVE-2022-0330){: external}, [CVE-2022-22822](https://nvd.nist.gov/vuln/detail/CVE-2022-22822){: external}, [CVE-2022-22823](https://nvd.nist.gov/vuln/detail/CVE-2022-22823){: external}, [CVE-2022-22824](https://nvd.nist.gov/vuln/detail/CVE-2022-22824){: external}, [CVE-2022-22825](https://nvd.nist.gov/vuln/detail/CVE-2022-22825){: external}, [CVE-2022-22826](https://nvd.nist.gov/vuln/detail/CVE-2022-22826){: external}, [CVE-2022-22827](https://nvd.nist.gov/vuln/detail/CVE-2022-22827){: external}, [CVE-2022-22942](https://nvd.nist.gov/vuln/detail/CVE-2022-22942){: external}, [CVE-2022-23852](https://nvd.nist.gov/vuln/detail/CVE-2022-23852){: external}, [CVE-2022-23990](https://nvd.nist.gov/vuln/detail/CVE-2022-23990){: external}, [CVE-2022-24407](https://nvd.nist.gov/vuln/detail/CVE-2022-24407){: external}, [CVE-2022-25235](https://nvd.nist.gov/vuln/detail/CVE-2022-25235){: external}, [CVE-2022-25236](https://nvd.nist.gov/vuln/detail/CVE-2022-25236){: external}. |
| Kubernetes | v1.22.6 | v1.22.7 | For more information, see the [change logs](https://github.com/kubernetes/kubernetes/releases/tag/v1.22.7){: external}. |
| HA proxy | f6a2b3 | 15198fb | Contains fixes for [CVE-2022-24407](https://nvd.nist.gov/vuln/detail/CVE-2022-24407){: external}. | 
{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.22.6_1539" caption-side="top"}


### Change log for worker node fix pack 1.22.6_1539, released 14 February 2022
{: #1226_1539}

| Component | Previous | Current | Description |
| --------- | -------- | ------- | ----------- |
| Ubuntu 18.04 packages | N/A | N/A | N/A |
| Kubernetes | N/A | N/A | N/A |
| HA proxy | d38fa1 | f6a2b3 | [CVE-2021-3521](https://nvd.nist.gov/vuln/detail/CVE-2021-3521){: external} and [CVE-2021-4122](https://nvd.nist.gov/vuln/detail/CVE-2021-4122){: external}. |{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.22.6_1538" caption-side="top"}

### Change log for worker node fix pack 1.22.6_1538, released 31 January 2022
{: #1226_1538}

| Component | Previous | Current | Description |
| --------- | -------- | ------- | ----------- |
| Ubuntu 18.04 packages | N/A | N/A | Updated worker node images with package updates for [CVE-2018-7169](https://nvd.nist.gov/vuln/detail/CVE-2018-7169){: external}, [CVE-2021-3984](https://nvd.nist.gov/vuln/detail/CVE-2021-3984){: external}, [CVE-2021-4019](https://nvd.nist.gov/vuln/detail/CVE-2021-4019){: external}, [CVE-2021-4034](https://nvd.nist.gov/vuln/detail/CVE-2021-4034){: external}, [CVE-2021-4069](https://nvd.nist.gov/vuln/detail/CVE-2021-4069){: external}. |
| Kubernetes | 1.22.4 | 1.22.6 | For more information, see the [change log](https://github.com/kubernetes/kubernetes/releases/tag/v1.22.6){: external}. |{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.20.13_1567" caption-side="top"}

### Change log for master fix pack 1.22.6_1537, released 26 January 2022
{: #1226_1537}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Calico | N/A | N/A | Changed to improve Calico availability during updates. |
| Cluster health image | v1.2.20 | v1.2.21 | Updated to use `Go` version `1.17.5`, updated Go dependencies and golangci-lint |
| GPU device plug-in and installer | c9bfc8c | eefc4ae | Updated universal base image (UBI) to the `8.5-218` version to resolve CVEs. Updated to use `Go` version `1.16.13`. |
| {{site.data.keyword.IBM_notm}} Calico extension | 900 | 923 | Updated universal base image (UBI) to the `8.5-218` version to resolve CVEs. Updated to use `Go` version `1.16.13`.|
| {{site.data.keyword.cloud_notm}} Controller Manager | v1.22.4-3 | v1.22.6-1 | Updated to support the Kubernetes `1.22.6` release and to use `Go` version `1.16.12`. |
| {{site.data.keyword.filestorage_full_notm}} plug-in and monitor | 402 | 404 | Updated universal base image (UBI) to the `8.5-218` version to resolve CVEs. Updated to use `Go` version `1.16.13`. |
| {{site.data.keyword.cloud_notm}} RBAC Operator | 3430e03 | 0fc9949 | Updated universal base image (UBI) to the `8.5-218` version to resolve CVEs. Updated to use `Go` version `1.16.13`. |
| Key Management Service provider | v2.3.12 | v2.4.0 | Decrypted data encryption key is persisted in memory until the root key is changed, disabled, or rotated. Update multiple go dependencies. |
| Konnectivity agent | v0.0.26_282_iks | v0.0.27_309_iks | See the [Konnectivity release notes](https://github.com/kubernetes-sigs/apiserver-network-proxy/releases/tag/v0.0.27){: external}.  Updated universal base image (UBI) to the `8.5-218` version to resolve CVEs. Updated to use `Go` version `1.17.5`. |
| Konnectivity server | v0.0.26_282_iks | v0.0.27_309_iks | See the [Konnectivity release notes](https://github.com/kubernetes-sigs/apiserver-network-proxy/releases/tag/v0.0.27){: external}.  Updated universal base image (UBI) to the `8.5-218` version to resolve CVEs. Updated to use `Go` version `1.17.5`. |
| Kubernetes | 1.22.4 | 1.22.6 | Changed the duration of worker node certificates from 3 years to 2 years. See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.22.6){: external}
| Kubernetes Metrics Server | v0.5.1 | v0.5.2 | Metrics server now dynamically reloads `NannyConfiguration` updates. See the [Kubernetes Metrics Server release notes](https://github.com/kubernetes-sigs/metrics-server/releases/tag/v0.5.2){: external}. |
| Kubernetes NodeLocal DNS cache | 1.21.1 | 1.21.3 | See the [Kubernetes NodeLocal DNS cache release notes](https://github.com/kubernetes/dns/releases/tag/1.21.3){: external}. |
| Load balancer and load balancer monitor for IBM Cloud Provider | 1659 | 1747 | Updated the Alpine base image to the `3.15` version to resolve CVEs. Updated to use `Go` version `1.17.6`. |
| Portieris admission controller | v0.12.1 | v0.12.2 | See the [Portieris admission controller release notes](https://github.com/IBM/portieris/releases/tag/v0.12.2){: external} |
{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.22.4_1531" caption-side="top"}


### Change log for worker node fix pack 1.22.4_1536, released 18 January 2022
{: #1224_1536}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 18.04 packages | 4.15.0-163-generic | 4.15.0-166-generic | Kernel and package updates for [CVE-2018-25020](https://nvd.nist.gov/vuln/detail/CVE-2018-25020){: external} and [CVE-2021-4002](https://nvd.nist.gov/vuln/detail/CVE-2021-4002){: external}. |
| Containerd | v1.5.8 | v1.5.9 | See the [change log](https://github.com/containerd/containerd/releases/tag/v1.5.9){: external}. |
{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.22.4_1534" caption-side="top"}

### Change log for worker node fix pack 1.22.4_1534, released 4 January 2022
{: #1224_1534}

The following table shows the changes that are in the worker node fix pack patch update `1.22.4_1534`. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| HA proxy | 3b8663 | d38fa1 | Contains fixes for [CVE-2021-3712](https://nvd.nist.gov/vuln/detail/CVE-2021-3712){: external}. |
| Ubuntu 18.04 packages | N/A | N/A | Updated worker node image packages for [CVE-2019-19449](https://nvd.nist.gov/vuln/detail/CVE-2019-19449){: external}, [CVE-2020-16592](https://nvd.nist.gov/vuln/detail/CVE-2020-16592){: external}, [CVE-2020-21913](https://nvd.nist.gov/vuln/detail/CVE-2020-21913){: external}, [CVE-2020-27781](https://nvd.nist.gov/vuln/detail/CVE-2020-27781){: external}, [CVE-2020-36322](https://nvd.nist.gov/vuln/detail/CVE-2020-36322){: external}, [CVE-2020-36385](https://nvd.nist.gov/vuln/detail/CVE-2020-36385){: external}, [CVE-2021-25219](https://nvd.nist.gov/vuln/detail/CVE-2021-25219){: external}, [CVE-2021-28831](https://nvd.nist.gov/vuln/detail/CVE-2021-28831){: external}, [CVE-2021-28950](https://nvd.nist.gov/vuln/detail/CVE-2021-28950){: external}, [CVE-2021-3487](https://nvd.nist.gov/vuln/detail/CVE-2021-3487){: external}, [CVE-2021-3524](https://nvd.nist.gov/vuln/detail/CVE-2021-3524){: external}, [CVE-2021-3531](https://nvd.nist.gov/vuln/detail/CVE-2021-3531){: external}, [CVE-2021-3733](https://nvd.nist.gov/vuln/detail/CVE-2021-3733){: external}, [CVE-2021-3737](https://nvd.nist.gov/vuln/detail/CVE-2021-3737){: external}, [CVE-2021-3759](https://nvd.nist.gov/vuln/detail/CVE-2021-3759){: external}, [CVE-2021-3778](https://nvd.nist.gov/vuln/detail/CVE-2021-3778){: external}, [CVE-2021-3796](https://nvd.nist.gov/vuln/detail/CVE-2021-3796){: external}, [CVE-2021-3800](https://nvd.nist.gov/vuln/detail/CVE-2021-3800){: external}, [CVE-2021-38199](https://nvd.nist.gov/vuln/detail/CVE-2021-38199){: external}, [CVE-2021-3903](https://nvd.nist.gov/vuln/detail/CVE-2021-3903){: external}, [CVE-2021-3927](https://nvd.nist.gov/vuln/detail/CVE-2021-3927){: external}, [CVE-2021-3928](https://nvd.nist.gov/vuln/detail/CVE-2021-3928){: external}, [CVE-2021-40490](https://nvd.nist.gov/vuln/detail/CVE-2021-40490){: external}, [CVE-2021-42374](https://nvd.nist.gov/vuln/detail/CVE-2021-42374){: external}, [CVE-2021-42378](https://nvd.nist.gov/vuln/detail/CVE-2021-42378){: external}, [CVE-2021-42384](https://nvd.nist.gov/vuln/detail/CVE-2021-42384){: external}, and [CVE-2021-43527](https://nvd.nist.gov/vuln/detail/CVE-2021-43527){: external}. |
{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.22.4_1532" caption-side="top"}

### Change log for master fix pack 1.22.4_1531, released 7 December 2021
{: #1224_1531}

The following table shows the changes that are in the master fix pack update `1.22.4_1531`. Master patch updates are applied automatically.
{: shortdesc}


| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Calico | v3.20.1 | v3.20.3 | See the [Calico release notes](https://projectcalico.docs.tigera.io/releases){: external}. Calico now adds the `node.kubernetes.io/network-unavailable` node taint when Calico shuts down on a node. The taint continues to be removed when Calico starts on a node. |
| Cluster health image | v1.2.18 | v1.2.20 | Updated universal base image (UBI) to the latest `8.4` version to resolve CVEs. Updated to use `Go` version `1.16.10`. |
| Gateway-enabled cluster controller | 1567 | 1586 | Updated Alpine base image to the latest `3.14` version to resolve CVEs. Updated to use `Go` version `1.16.10`. |
| GPU device plug-in and installer | 7fd867d | c9bfc8c | Updated universal base image (UBI) to the `8.5-204` version to resolve CVEs. Updated to use `Go` version `1.16.10`. |
| {{site.data.keyword.IBM_notm}} Calico extension | 864 | 900 | Updated universal base image (UBI) to the `8.5-204` version to resolve CVEs. Updated to use `Go` version `1.16.10`. |
| {{site.data.keyword.cloud_notm}} Controller Manager | v1.22.3-2 | v1.22.4-3 | Updated to support the Kubernetes `1.22.4` release and to use `Go` version `1.16.10`. |
| {{site.data.keyword.filestorage_full_notm}} plug-in and monitor | 401 | 402 | Updated universal base image (UBI) to the `8.5-204` version to resolve CVEs. Updated to use `Go` version `1.16.10`. |
| {{site.data.keyword.cloud_notm}} RBAC Operator | 4ca5637 | 3430e03 | Updated universal base image (UBI) to the latest `8.5` version to resolve CVEs. Updated to use `Go` version `1.16.10`. |
| Key Management Service provider | v2.3.10 | v2.3.12 | Updated universal base image (UBI) to the latest `8.4` version to resolve CVEs. Updated to use `Go` version `1.16.10`. |
| Konnectivity agent | v0.0.24_268_iks | v0.0.26_282_iks | See the [Konnectivity release notes](https://github.com/kubernetes-sigs/apiserver-network-proxy/releases/tag/v0.0.26){: external}. |
| Konnectivity server | v0.0.24_268_iks | v0.0.26_282_iks | See the [Konnectivity release notes](https://github.com/kubernetes-sigs/apiserver-network-proxy/releases/tag/v0.0.26){: external}. Updated to use TLS version 1.3 ciphers.|
| Kubernetes | v1.22.3 | v1.22.4 | See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.22.4){: external}. |
| Load balancer and load balancer monitor for {{site.data.keyword.IBM_notm}} Cloud Provider | 1590 | 1659 | Updated Alpine base image to the latest `3.14` version to resolve CVEs. Updated to use `Go` version `1.16.10`. |
| Operator Lifecycle Manager | 0.16.1-IKS-14 | 0.16.1-IKS-15 | Updated image for [CVE-2021-42374](https://nvd.nist.gov/vuln/detail/CVE-2021-42374){: external}, [CVE-2021-42375](https://nvd.nist.gov/vuln/detail/CVE-2021-42375){: external}, [CVE-2021-42378](https://nvd.nist.gov/vuln/detail/CVE-2021-42378){: external}, [CVE-2021-42379](https://nvd.nist.gov/vuln/detail/CVE-2021-42379){: external}, [CVE-2021-42380](https://nvd.nist.gov/vuln/detail/CVE-2021-42380){: external}, [CVE-2021-42381](https://nvd.nist.gov/vuln/detail/CVE-2021-42381){: external}, [CVE-2021-42382](https://nvd.nist.gov/vuln/detail/CVE-2021-42382){: external}, [CVE-2021-42383](https://nvd.nist.gov/vuln/detail/CVE-2021-42383){: external}, [CVE-2021-42384](https://nvd.nist.gov/vuln/detail/CVE-2021-42384){: external}, [CVE-2021-42385](https://nvd.nist.gov/vuln/detail/CVE-2021-42385){: external} and [CVE-2021-42386](https://nvd.nist.gov/vuln/detail/CVE-2021-42386){: external}. |
| Portieris admission controller | v0.12.0 | v0.12.1 | See the [Portieris admission controller release notes](https://github.com/IBM/portieris/releases/tag/v0.12.1){: external}. |
{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.22.3_1529" caption-side="top"}



### Change log for worker node fix pack 1.22.4_1532, released 6 December 2021
{: #1224_1532}

The following table shows the changes that are in the worker node fix pack patch update `1.22.4_1532`. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 18.04 packages | 4.15.0-162 | 4.15.0-163 | Updated worker node images and kernel with package updates. Contains fixes for [CVE-2021-43527](https://nvd.nist.gov/vuln/detail/CVE-2021-43527){: external} |
| Kubernetes | 1.22.3 | 1.22.4 | See the [change log](https://github.com/kubernetes/kubernetes/releases/tag/v1.22.4){: external}. | 
| Containerd | v1.5.7 | v1.5.8 | See the [change log](https://github.com/containerd/containerd/releases/tag/v1.5.8){: external} and the [security bulletin](https://www.ibm.com/support/pages/node/6524974){: external} | 
{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.22.3_1530" caption-side="top"}

### Change log for worker node fix pack 1.22.3_1530, released 22 November 2021
{: #1223_1530}

The following table shows the changes that are in the worker node fix pack patch update `1.22.3_1530`. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Kubernetes | 1.22.2 | 1.22.3 | For more information, see the [change log](https://github.com/kubernetes/kubernetes/releases/tag/v1.22.3){: external}. | 
| HA proxy | 07f1e9e | 3b8663 | Contains fixes for [CVE-2021-20231](https://nvd.nist.gov/vuln/detail/CVE-2021-20231){: external}, [CVE-2021-20232](https://nvd.nist.gov/vuln/detail/CVE-2021-20232){: external}, [CVE-2021-3580](https://nvd.nist.gov/vuln/detail/CVE-2021-3580){: external}, [CVE-2021-22946](https://nvd.nist.gov/vuln/detail/CVE-2021-22946){: external}, [CVE-2021-22947](https://nvd.nist.gov/vuln/detail/CVE-2021-22947){: external}, [CVE-2021-22876](https://nvd.nist.gov/vuln/detail/CVE-2021-22876){: external}, [CVE-2021-22898](https://nvd.nist.gov/vuln/detail/CVE-2021-22898){: external}, [CVE-2021-22925](https://nvd.nist.gov/vuln/detail/CVE-2021-22925){: external}, [CVE-2019-20838](https://nvd.nist.gov/vuln/detail/CVE-2019-20838){: external}, [CVE-2020-14155](https://nvd.nist.gov/vuln/detail/CVE-2020-14155){: external}, [CVE-2018-20673](https://nvd.nist.gov/vuln/detail/CVE-2018-20673){: external}, [CVE-2021-42574](https://nvd.nist.gov/vuln/detail/CVE-2021-42574){: external}, [CVE-2019-17594](https://nvd.nist.gov/vuln/detail/CVE-2019-17594){: external}, [CVE-2019-17595](https://nvd.nist.gov/vuln/detail/CVE-2019-17595){: external}, [CVE-2020-12762](https://nvd.nist.gov/vuln/detail/CVE-2020-12762){: external}, [CVE-2020-16135](https://nvd.nist.gov/vuln/detail/CVE-2020-16135){: external}, [CVE-2021-3445](https://nvd.nist.gov/vuln/detail/CVE-2021-3445){: external}, [CVE-2021-36084](https://nvd.nist.gov/vuln/detail/CVE-2021-36084){: external}, [CVE-2021-36085](https://nvd.nist.gov/vuln/detail/CVE-2021-36085){: external}, [CVE-2021-36086](https://nvd.nist.gov/vuln/detail/CVE-2021-36086){: external}, [CVE-2021-36087](https://nvd.nist.gov/vuln/detail/CVE-2021-36087){: external}, [CVE-2021-20266](https://nvd.nist.gov/vuln/detail/CVE-2021-20266){: external}, [CVE-2019-18218](https://nvd.nist.gov/vuln/detail/CVE-2019-18218){: external}, [CVE-2021-23840](https://nvd.nist.gov/vuln/detail/CVE-2021-23840){: external}, [CVE-2021-23841](https://nvd.nist.gov/vuln/detail/CVE-2021-23841){: external}, [CVE-2021-27645](https://nvd.nist.gov/vuln/detail/CVE-2021-27645){: external}, [CVE-2021-33574](https://nvd.nist.gov/vuln/detail/CVE-2021-33574){: external}, [CVE-2021-35942](https://nvd.nist.gov/vuln/detail/CVE-2021-35942){: external}, [CVE-2021-33560](https://nvd.nist.gov/vuln/detail/CVE-2021-33560){: external}, [CVE-2019-13750](https://nvd.nist.gov/vuln/detail/CVE-2019-13750){: external}, [CVE-2019-13751](https://nvd.nist.gov/vuln/detail/CVE-2019-13751){: external}, [CVE-2019-19603](https://nvd.nist.gov/vuln/detail/CVE-2019-19603){: external}, [CVE-2019-5827](https://nvd.nist.gov/vuln/detail/CVE-2019-5827){: external}, [CVE-2020-13435](https://nvd.nist.gov/vuln/detail/CVE-2020-13435){: external}, [CVE-2020-24370](https://nvd.nist.gov/vuln/detail/CVE-2020-24370){: external}, [CVE-2021-28153](https://nvd.nist.gov/vuln/detail/CVE-2021-28153){: external}, [CVE-2021-3800](https://nvd.nist.gov/vuln/detail/CVE-2021-3800){: external}, [CVE-2021-33928](https://nvd.nist.gov/vuln/detail/CVE-2021-33928){: external}, [CVE-2021-33929](https://nvd.nist.gov/vuln/detail/CVE-2021-33929){: external}, [CVE-2021-33930](https://nvd.nist.gov/vuln/detail/CVE-2021-33930){: external}, [CVE-2021-33938](https://nvd.nist.gov/vuln/detail/CVE-2021-33938){: external}, and[CVE-2021-3200](https://nvd.nist.gov/vuln/detail/CVE-2021-3200){: external} |
| Ubuntu 18.04 packages | 4.15.0-161 | 4.15.0-162  | Updated worker node images and kernel with package fixes for[CVE-2019-19449](https://nvd.nist.gov/vuln/detail/CVE-2019-1944){: external}, [CVE-2020-36322](https://nvd.nist.gov/vuln/detail/CVE-2020-3632){: external}, [CVE-2020-36385](https://nvd.nist.gov/vuln/detail/CVE-2020-3638){: external}, [CVE-2021-28950](https://nvd.nist.gov/vuln/detail/CVE-2021-2895){: external}, [CVE-2021-3759](https://nvd.nist.gov/vuln/detail/CVE-2021-3759){: external}, [CVE-2021-38199](https://nvd.nist.gov/vuln/detail/CVE-2021-38199){: external}, [CVE-2021-3903](https://nvd.nist.gov/vuln/detail/CVE-2021-3903){: external}, [CVE-2021-3927](https://nvd.nist.gov/vuln/detail/CVE-2021-3927){: external}, and [CVE-2021-3928](https://nvd.nist.gov/vuln/detail/CVE-2021-3928){: external}. |
{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.22.2_1528" caption-side="top"}

### Change log for master fix pack 1.22.3_1529, released 17 November 2021
{: #1223_1529}

The following table shows the changes that are in the master fix pack update `1.22.3_1529`. Master patch updates are applied automatically.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Cluster health image | v1.2.16 | v1.2.18 | Updated `Go` module dependencies and to use `Go` version `1.16.9`.  Updated image for [CVE-2021-22946](https://nvd.nist.gov/vuln/detail/CVE-2021-22946){: external}, [CVE-2021-22947](https://nvd.nist.gov/vuln/detail/CVE-2021-22947){: external}, [CVE-2021-33928](https://nvd.nist.gov/vuln/detail/CVE-2021-33928){: external}, [CVE-2021-33929](https://nvd.nist.gov/vuln/detail/CVE-2021-33929){: external} and [CVE-2021-33930](https://nvd.nist.gov/vuln/detail/CVE-2021-33930){: external}. |
| etcd | v3.4.17 | v3.4.18 | See the [etcd release notes](https://github.com/etcd-io/etcd/releases/v3.4.18){: external}. |
| Gateway-enabled cluster controller | 1510 | 1567 | Updated to use `Go` version `1.16.9`. |
| GPU device plug-in and installer | 58d7589 | 7fd867d | Updated image for [CVE-2021-36222](https://nvd.nist.gov/vuln/detail/CVE-2021-36222){: external}, [CVE-2021-37750](https://nvd.nist.gov/vuln/detail/CVE-2021-37750){: external}, [CVE-2021-22922](https://nvd.nist.gov/vuln/detail/CVE-2021-22922){: external}, [CVE-2021-22923](https://nvd.nist.gov/vuln/detail/CVE-2021-22923){: external} and [CVE-2021-22924](https://nvd.nist.gov/vuln/detail/CVE-2021-22924){: external}. |
| {{site.data.keyword.cloud_notm}} Controller Manager | v1.22.2-3 | v1.22.3-2 | Updated to support the Kubernetes `1.22.3` release and to use `Go` version `1.16.9`. Updated image for [DLA-2797-1](https://www.debian.org/lts/security/2021/dla-2797){: external}. |
| {{site.data.keyword.cloud_notm}} RBAC Operator | e3cb629 | 4ca5637 | Updated universal base image (UBI) to the latest `8.4` version to resolve CVEs. |
| Key Management Service provider | v2.3.8 | v2.3.10 | Updated `Go` module dependencies and to use `Go` version `1.16.9`.  Updated image for [CVE-2021-22946](https://nvd.nist.gov/vuln/detail/CVE-2021-22946){: external}. |
| Konnectivity agent | v0.0.24_262_iks | v0.0.24_268_iks | Update to use `Go` version `1.16.9`. |
| Konnectivity server | v0.0.24_262_iks | v0.0.24_268_iks | Update to use `Go` version `1.16.9`. |
| Kubernetes | v1.22.2 | v1.22.3 | See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.22.3){: external}. Changed the duration of the Kubernetes API server certificate from 825 days to 365 days. Changed the duration of the cluster CA certificate from 30 to 10 years. |
| Load balancer and load balancer monitor for {{site.data.keyword.cloud_notm}} Provider | 1547 | 1590 | Updated to use `Go` version `1.16.9`. |
{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.22.2_1526" caption-side="top"}

### Change log for worker node fix pack 1.22.2_1528, released 10 November 2021
{: #1222_1528}

The following table shows the changes that are in the worker node fix pack patch update `1.22.2_1528`. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 18.04 packages | N/A | N/A | Updated worker node image packages for [CVE-2020-16592](https://nvd.nist.gov/vuln/detail/CVE-2020-16592){: external}, [CVE-2020-27781](https://nvd.nist.gov/vuln/detail/CVE-2020-27781){: external}, [CVE-2021-25219](https://nvd.nist.gov/vuln/detail/CVE-2021-25219){: external}, [CVE-2021-3487](https://nvd.nist.gov/vuln/detail/CVE-2021-3487){: external}, [CVE-2021-3524](https://nvd.nist.gov/vuln/detail/CVE-2021-3524){: external}, [CVE-2021-3531](https://nvd.nist.gov/vuln/detail/CVE-2021-3531){: external}, and [CVE-2021-40490](https://nvd.nist.gov/vuln/detail/CVE-2021-40490){: external}. |
{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.22.2_1527" caption-side="top"}

### Change log for worker node fix pack 1.22.2_1527, released 25 October 2021
{: #1222_1527}

The following table shows the changes that are in the worker node fix pack patch update `1.22.2_1527`. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 18.04 packages | N/A | N/A | Updated worker node images with package updates. Contains fix for cloud-init performance problem. |
| Worker-pool taint automation | N/A | N/A | Fixes known issue related to worker-pool taint automation that prevents workers from getting providerID. |
{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.22.2_1524" caption-side="top"}

### Change log for master fix pack 1.22.2_1526, released 29 October 2021
{: #1222_1526}

The following table shows the changes that are in the master fix pack update `1.22.2_1526`.  Master patch updates are applied automatically.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Cluster health image | v1.2.15 | v1.2.16 | Updated universal base image (UBI) to the latest `8.4` version to resolve CVEs:  [CVE-2021-36222](https://nvd.nist.gov/vuln/detail/CVE-2021-36222){: external}, [CVE-2021-37750](https://nvd.nist.gov/vuln/detail/CVE-2021-37750){: external}, [CVE-2021-22922](https://nvd.nist.gov/vuln/detail/CVE-2021-22922){: external}, [CVE-2021-22923](https://nvd.nist.gov/vuln/detail/CVE-2021-22923){: external}, and [CVE-2021-22924](https://nvd.nist.gov/vuln/detail/CVE-2021-22924){: external}. |
| CoreDNS | 1.8.4 | 1.8.6 | See the [CoreDNS release notes](https://coredns.io/2021/10/07/coredns-1.8.6-release/){: external}. |
| etcd | v3.4.16 | v3.4.17 | See the [etcd release notes](https://github.com/etcd-io/etcd/releases/v3.4.17){: external}. |
| {{site.data.keyword.IBM_notm}}  Calico extension | 763 | 864 | Updated to use `Go` version `1.16.9`. Updated universal base image (UBI) to the latest `8.4` version to resolve CVEs. |
| {{site.data.keyword.cloud_notm}} Controller Manager | v1.22.2-1 | v1.22.2-3 | Updated to ignore VPC load balancer (LB) state when a LB delete is requested. |
| {{site.data.keyword.cloud_notm}} {{site.data.keyword.filestorage_short}} plug-in and monitor | 400 | 401 | Updated universal base image (UBI) to the latest `8.4-210` version to resolve CVEs. |
| Key Management Service provider | v2.3.7 | v2.3.8 | Updated universal base image (UBI) to the latest `8.4` version to resolve CVEs:  [CVE-2021-36222](https://nvd.nist.gov/vuln/detail/CVE-2021-36222){: external}, [CVE-2021-37750](https://nvd.nist.gov/vuln/detail/CVE-2021-37750){: external}, [CVE-2021-22922](https://nvd.nist.gov/vuln/detail/CVE-2021-22922){: external}, [CVE-2021-22923](https://nvd.nist.gov/vuln/detail/CVE-2021-22923){: external}, and [CVE-2021-22924](https://nvd.nist.gov/vuln/detail/CVE-2021-22924){: external}. |
| Konnectivity agent | v0.0.23_245_iks | v0.0.24_262_iks | See the [Konnectivity release notes](https://github.com/kubernetes-sigs/apiserver-network-proxy/releases/tag/v0.0.24){: external}.  Modified Konnectivity agent CPU and memory resource requests and memory resource limit and removed the CPU resource limit. |
| Konnectivity server | v0.0.23_245_iks | v0.0.24_262_iks | See the [Konnectivity release notes](https://github.com/kubernetes-sigs/apiserver-network-proxy/releases/tag/v0.0.24){: external}. |
| Kubernetes Metrics Server | v0.5.0 | v0.5.1 | See the [Kubernetes Metrics Server release notes](https://github.com/kubernetes-sigs/metrics-server/releases/tag/v0.5.1){: external}. |
| Kubernetes NodeLocal DNS cache | 1.20.0 | 1.21.1 | See the [Kubernetes NodeLocal DNS cache release notes](https://github.com/kubernetes/dns/releases/tag/1.21.1){: external}. |
| Portieris admission controller | v0.11.0 | v0.12.0 | See the [Portieris admission controller release notes](https://github.com/IBM/portieris/releases/tag/v0.12.0){: external} |
{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.22.2_1522" caption-side="top"}

### Change log for worker node fix pack 1.22.2_1524, released 11 October 2021
{: #1222_1524}

The following table shows the changes that are in the worker node fix pack patch update `1.22.2_1524`. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Containerd | v1.5.5 | v1.5.7 | See the [security bulletin](https://www.ibm.com/support/pages/node/6501867){: external} and the [change log](https://github.com/containerd/containerd/releases/tag/v1.5.7){: external}. |
| Ubuntu 18.04 packages | 4.15.0-158 | 4.15.0-159 | Updated worker node images and kernel with package updates [CVE-2021-3778](https://nvd.nist.gov/vuln/detail/CVE-2021-3778){: external} and [CVE-2021-3796](https://nvd.nist.gov/vuln/detail/CVE-2021-3796){: external}. |
{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.22.2_1523" caption-side="top"}

### Change log for master fix pack 1.22.2_1522 and worker node fix pack 1.22.2_1523, released 29 Sept 2021
{: #1222_1522_and_1222_1523}

The following table shows the changes that are in the master fix pack `1.22.2_1522` and the worker node fix pack patch update `1.22.2_1523`. Master patch updates are applied automatically. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Calico | v3.19.3 | v3.20.1 | See the [Calico release notes](https://projectcalico.docs.tigera.io/releases){: external}. |
| containerd configuration | N/A | N/A | Cluster administrators may now update the containerd registry host configurations on their clusters. See [Updating your cluster's containerd registry host configuration](/docs/containers?topic=containers-registry#update_containerd_registry_config) and the [containerd CRI plugin configuration guide](https://github.com/containerd/containerd/blob/v1.5.5/docs/cri/config.md#registry-configuration){: external}.|
| {{site.data.keyword.cloud_notm}} Controller Manager | v1.21.5-1 | v1.22.2-1 | Updated to support the Kubernetes `1.22.2` release. In addition, the code for this component is now [open source](https://github.com/IBM-Cloud/cloud-provider-ibm){: external}. |
| Kubernetes | v1.21.5 | v1.22.2 | See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.22.2){: external}. This update resolves [CVE-2021-25741](https://nvd.nist.gov/vuln/detail/CVE-2021-25741){: external}. For more information, see the [IBM security bulletin](https://www.ibm.com/support/pages/node/6496649){: external}). |
| Kubernetes add-on resizer | 1.8.13 | 1.8.14 | See the [Kubernetes add-on resizer release notes](https://github.com/kubernetes/autoscaler/releases/tag/addon-resizer-1.8.14){: external}. |
| Kubernetes admission controllers configuration | N/A | N/A | Added `PodSecurity` to the `--disable-admission-plugins` option for the cluster's [Kubernetes API server](/docs/containers?topic=containers-service-settings#kube-apiserver). Pod security continues to be [configured via pod security policies](/docs/containers?topic=containers-psp). |
| Kubernetes configuration | N/A | N/A | Updated the [feature gate configuration](/docs/containers?topic=containers-service-settings#feature-gates). |
| Kubernetes CSI snapshotter CRDs | v3.0.2 | v4.0.0 | See the [Kubernetes container storage interface (CSI) snapshotter release notes](https://github.com/kubernetes-csi/external-snapshotter/releases/tag/v4.0.0){: external}. |
| Kubernetes Metrics Server | v0.4.4 | v0.5.0 | See the [Kubernetes Metrics Server release notes](https://github.com/kubernetes-sigs/metrics-server/releases/tag/v0.5.0){: external}. The `metrics-server-nanny` container configuration has been updated to use a 30 second poll period (previously 5 minutes) in order to allow faster scaling of the metrics server. |
| Kubernetes NodeLocal DNS cache | 1.17.3 | 1.20.0 | Increased memory resource requests from `5Mi` to `10Mi` to better align with normal resource utilization. See the [Kubernetes NodeLocal DNS cache release notes](https://github.com/kubernetes/dns/releases/tag/1.20.0){: external}. |
| Portieris admission controller | v0.10.3 | v0.11.0 | See the [Portieris admission controller release notes](https://github.com/IBM/portieris/releases/tag/v0.11.0){: external}. |
{: summary="The rows are read from left to right. The first column is the changed component. The second column is the previous version number of the component. The third column is the current version number of the component. The fourth column contains a brief description of the change made to the component."}
{: caption="Changes since version 1.21.5_1531 (master) and 1.21.5_1532 (worker node)." caption-side="top"}
