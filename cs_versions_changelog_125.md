---

copyright: 
  years: 2022, 2022
lastupdated: "2022-10-11"

keywords: kubernetes, containers, change log, 125 change log, 125 updates

subcollection: containers


---

# Kubernetes version 1.25 change log
{: #changelog_125}

View information about version changes for major, minor, and patch updates that are available for your {{site.data.keyword.containerlong}} clusters that run version 1.25. Changes include updates to Kubernetes and {{site.data.keyword.cloud_notm}} Provider components.
{: shortdesc}

## Overview
{: #changelog_overview_125}

Unless otherwise noted in the change logs, the {{site.data.keyword.containerlong_notm}} provider version enables Kubernetes APIs and features that are at beta. Kubernetes alpha features, which are subject to change, are disabled.

For more information about major, minor, and patch versions and preparation actions between minor versions, see [Kubernetes versions](/docs/containers?topic=containers-cs_versions).
{: tip}

Check the [Security Bulletins on {{site.data.keyword.cloud_notm}} Status](https://cloud.ibm.com/status?component=containers-kubernetes&selected=security){: external} for security vulnerabilities that affect {{site.data.keyword.containerlong_notm}}. You can filter the results to view only Kubernetes Cluster security bulletins that are relevant to {{site.data.keyword.containerlong_notm}}. Change log entries that address other security vulnerabilities but don't also refer to an {{site.data.keyword.IBM_notm}} security bulletin are for vulnerabilities that are not known to affect {{site.data.keyword.containerlong_notm}} in normal usage. If you run privileged containers, run commands on the workers, or execute untrusted code, then you might be at risk.

Some change logs are for _worker node fix packs_, and apply only to worker nodes. You must [apply these patches](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_update) to ensure security compliance for your worker nodes. These worker node fix packs can be at a higher version than the master because some build fix packs are specific to worker nodes. Other change logs are for _master fix packs_, and apply only to the cluster master. Master fix packs might not be automatically applied. You can choose to [apply them manually](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_update). For more information about patch types, see [Update types](/docs/containers?topic=containers-cs_versions#update_types).
{: note}

## Version 1.25 change log
{: #125_changelog}

Review the version 1.25 change log.
{: shortdesc}


### Change log for master fix pack 1.25.2_1517 and worker node fix pack 1.25.2_1516, released 6 October 2022
{: #1252_1517_and_1252_1516}


| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Calico | v3.23.3 | v3.24.1 | See the [Calico release notes](https://projectcalico.docs.tigera.io/archive/v3.24/release-notes/){: external}. In addition, a `default` `FelixConfiguration` resource is created if it doesn't exist. The resource has `natPortRange` set to `32768:65535`. For more information, see [Why am I seeing SNAT port issues and egress connection failures?](/docs/containers?topic=containers-ts-network-snat-125){: external} |
| CoreDNS | 1.9.3 | 1.10.0 | See the [CoreDNS release notes](https://github.com/coredns/coredns/blob/v1.10.0/notes/coredns-1.10.0.md){: external}. |
| IBM Cloud Controller Manager | v1.24.5-1 | v1.25.2-2 | Updated to support the Kubernetes `1.25.2` release and `Go` version `1.19.1`. |
| Kubernetes | v1.24.6 | v1.25.2 | See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.25.2){: external}. |
| Kubernetes admission controllers configuration | N/A | N/A | Enabled the `PodSecurity` and removed the `PodSecurityPolicy` admission controllers. [Pod Security Policies](https://kubernetes.io/docs/concepts/security/pod-security-policy/){: external} have been removed in Kubernetes version 1.25. See the Kubernetes [Deprecated API Migration Guide](https://kubernetes.io/docs/reference/using-api/deprecation-guide/#psp-v125){: external} for more information. {{site.data.keyword.containerlong_notm}} version 1.25 now configures [Pod Security Admission](https://kubernetes.io/docs/concepts/security/pod-security-admission/){: external} and no longer supports [Pod Security Policies](https://kubernetes.io/docs/concepts/security/pod-security-policy/){: external}. |
| Kubernetes configuration | N/A | N/A | Updated the [feature gate configuration](/docs/containers?topic=containers-service-settings#feature-gates). |
| Kubernetes CSI snapshot CRDs | v5.0.1 | v6.0.1 | See the [Kubernetes container storage interface (CSI) snapshotter release notes](https://github.com/kubernetes-csi/external-snapshotter/releases/tag/v6.0.1){: external}. |
| Kubernetes CSI snapshot controller | None | v6.0.1 | See the [Kubernetes container storage interface (CSI) snapshotter release notes](https://github.com/kubernetes-csi/external-snapshotter/releases/tag/v6.0.1){: external}. |
| Kubernetes Dashboard | v2.6.1 | v2.7.0 | See the [Kubernetes Dashboard release notes](https://github.com/kubernetes/dashboard/releases/tag/v2.7.0){: external}. |
| Kubernetes DNS autoscaler | 1.8.5 | 1.8.6 | See the [Kubernetes DNS autoscaler release notes](https://github.com/kubernetes-sigs/cluster-proportional-autoscaler/releases/tag/1.8.6){: external}. In addition, CPU resource requests were reduced from `5m` to `1m` to better align with normal resource utilization. |
| Pause container image | 3.7 | 3.8 | See the [pause container image release notes](https://github.com/kubernetes/kubernetes/blob/master/build/pause/CHANGELOG.md){: external}. |
{: caption="Changes since version 1.24.6_1538 master and 1.24.6_1539 worker node."}








