---

copyright: 
  years: 2022, 2022
lastupdated: "2022-09-08"

keywords: kubernetes, containers

subcollection: containers


---

{{site.data.keyword.attribute-definition-list}}

# 1.24 version information and update actions
{: #cs_versions_124}

Review information about version 1.24 of {{site.data.keyword.containerlong}}, released 09 June 2022.
{: shortdesc}

Looking for general information on updating {{site.data.keyword.containerlong}} clusters, or information on a different version? See [Kubernetes version information and update actions](/docs/containers?topic=containers-cs_versions).
{: tip}

![This badge indicates Kubernetes version 1.24 certification for {{site.data.keyword.containerlong_notm}}](images/certified-kubernetes-color.svg){: caption="Figure 1. Kubernetes version 1.24 certification badge" caption-side="bottom"} 

{{site.data.keyword.containerlong_notm}} is a Certified Kubernetes product for version 1.24 under the CNCF Kubernetes Software Conformance Certification program. _Kubernetes® is a registered trademark of The Linux Foundation in the United States and other countries, and is used pursuant to a license from The Linux Foundation._



For more information about Kubernetes project version 1.24, see the [Kubernetes change log](https://kubernetes.io/releases/notes/.){: external}

## Release timeline 
{: #release_timeline_124}

The following table includes the expected release timeline for version 1.24 of {{site.data.keyword.containerlong}}. You can use this information for planning purposes, such as to estimate the general time that the version might become unsupported. 
{: shortdesc}

Dates that are marked with a dagger (`†`) are tentative and subject to change.
{: important}

|  Version | Supported? | {{site.data.keyword.containerlong_notm}} \n release date | {{site.data.keyword.containerlong_notm}} \n unsupported date |
|------|------|----------|----------|
| 1.24 | Yes | 09 Jun 2022 | 29 Nov 2023 `†` |
{: caption="Release timeline for {{site.data.keyword.containerlong_notm}} version 1.24" caption-side="top"}

## Preparing to update
{: #prep-up-124}

This information summarizes updates that are likely to have and impact on deployed apps when you update a cluster to version 1.24. For a complete list of changes, review the [community Kubernetes change log](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.24.md){: external} and [IBM version change log](/docs/containers?topic=containers-changelog_124) for version 1.24. You can also review the [Kubernetes helpful warnings](https://kubernetes.io/blog/2020/09/03/warnings/){: external}. 
{: shortdesc}

### Update before master
{: #before_124}

[Pod security policies](https://kubernetes.io/docs/concepts/security/pod-security-policy/) are scheduled for removal in Kubernetes version 1.25.  See the Kubernetes [Deprecated API migration guide](https://kubernetes.io/docs/reference/using-api/deprecation-guide/#psp-v125){: external} for more information. Customers will have the option to replace Pod Security Policies with [Pod security admission](https://kubernetes.io/docs/concepts/security/pod-security-admission/){: external} or a [third party admission webhook](https://kubernetes.io/docs/reference/access-authn-authz/extensible-admission-controllers/){: external}. IBM Cloud Kubernetes Service will make a beta version of Pod Security available in version 1.24 to aid in the migration, but this support is not yet available.
{: important}

The following table shows the actions that you must take before you update the Kubernetes master.
{: shortdesc}

| Type | Description|
| --- | --- |
| **Unsupported:** CoreDNS wildcard queries via Kubernetes plugin | CoreDNS no longer supports wildcard DNS queries via the Kubernetes plugin. Applications using such queries must be updated to use an alternative DNS query method. You can run the following command against a version 1.23 cluster to determine if your cluster apps are performing such queries: `kubectl logs -n kube-system -l k8s-app=kube-dns --tail=-1 \| grep "deprecated wildcard queries received"`. |
| IBM Cloud Block Storage driver and plug-in installation | The IBM Cloud Block Storage driver and plug-in component is now installed on clusters running classic infrastructure. If you installed the [IBM Cloud Block Storage driver and plug-in via the Helm chart](/docs/containers?topic=containers-block_storage#install_block), you must [uninstall the Helm chart](/docs/containers?topic=containers-block_storage#rm_block) before continuing the master update. Note that your existing persistent volume claims (PVCs) will continue to work after the Helm chart is uninstalled, but you are not able to provision new PVCs until the master update is completed. |
{: caption="Changes to make after you update the master to Kubernetes 1.24" caption-side="top"}
{: summary="The rows are read from left to right. The type of update action is in the first column, and a description of the update action type is in the second column."}


### Update after master
{: #124_after}

The following table shows the actions that you must take after you update the Kubernetes master.
{: shortdesc}

| Type | Description|
| --- | --- |
| **Unsupported:** `kubectl expose` removes `--container-port` and `--generator` flags | The `kubectl expose` command no longer supports the deprecated `--container-port` and `--generator` flags. If your scripts rely on these flags, update them. |
| **Unsupported:** `kubectl run` removes several flags | The `kubectl run` command no longer supports the deprecated `--serviceaccount`, `--hostport`, `--requests` and `--limits` flags. If your scripts rely on these flags, update them. |
{: caption="Changes to make after you update the master to Kubernetes 1.24" caption-side="top"}
{: summary="The rows are read from left to right. The type of update action is in the first column, and a description of the update action type is in the second column."}

