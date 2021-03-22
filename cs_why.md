---

copyright:
  years: 2014, 2021
lastupdated: "2021-03-22"

keywords: kubernetes, iks, containers

subcollection: containers

---

{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}
{:android: data-hd-operatingsystem="android"}
{:api: .ph data-hd-interface='api'}
{:apikey: data-credential-placeholder='apikey'}
{:app_key: data-hd-keyref="app_key"}
{:app_name: data-hd-keyref="app_name"}
{:app_secret: data-hd-keyref="app_secret"}
{:app_url: data-hd-keyref="app_url"}
{:authenticated-content: .authenticated-content}
{:beta: .beta}
{:c#: data-hd-programlang="c#"}
{:cli: .ph data-hd-interface='cli'}
{:codeblock: .codeblock}
{:curl: .ph data-hd-programlang='curl'}
{:deprecated: .deprecated}
{:dotnet-standard: .ph data-hd-programlang='dotnet-standard'}
{:download: .download}
{:external: target="_blank" .external}
{:faq: data-hd-content-type='faq'}
{:fuzzybunny: .ph data-hd-programlang='fuzzybunny'}
{:generic: data-hd-operatingsystem="generic"}
{:generic: data-hd-programlang="generic"}
{:gif: data-image-type='gif'}
{:go: .ph data-hd-programlang='go'}
{:help: data-hd-content-type='help'}
{:hide-dashboard: .hide-dashboard}
{:hide-in-docs: .hide-in-docs}
{:important: .important}
{:ios: data-hd-operatingsystem="ios"}
{:java: .ph data-hd-programlang='java'}
{:java: data-hd-programlang="java"}
{:javascript: .ph data-hd-programlang='javascript'}
{:javascript: data-hd-programlang="javascript"}
{:new_window: target="_blank"}
{:note .note}
{:note: .note}
{:objectc data-hd-programlang="objectc"}
{:org_name: data-hd-keyref="org_name"}
{:php: data-hd-programlang="php"}
{:pre: .pre}
{:preview: .preview}
{:python: .ph data-hd-programlang='python'}
{:python: data-hd-programlang="python"}
{:route: data-hd-keyref="route"}
{:row-headers: .row-headers}
{:ruby: .ph data-hd-programlang='ruby'}
{:ruby: data-hd-programlang="ruby"}
{:runtime: architecture="runtime"}
{:runtimeIcon: .runtimeIcon}
{:runtimeIconList: .runtimeIconList}
{:runtimeLink: .runtimeLink}
{:runtimeTitle: .runtimeTitle}
{:screen: .screen}
{:script: data-hd-video='script'}
{:service: architecture="service"}
{:service_instance_name: data-hd-keyref="service_instance_name"}
{:service_name: data-hd-keyref="service_name"}
{:shortdesc: .shortdesc}
{:space_name: data-hd-keyref="space_name"}
{:step: data-tutorial-type='step'}
{:subsection: outputclass="subsection"}
{:support: data-reuse='support'}
{:swift: .ph data-hd-programlang='swift'}
{:swift: data-hd-programlang="swift"}
{:table: .aria-labeledby="caption"}
{:term: .term}
{:tip: .tip}
{:tooling-url: data-tooling-url-placeholder='tooling-url'}
{:troubleshoot: data-hd-content-type='troubleshoot'}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:tsSymptoms: .tsSymptoms}
{:tutorial: data-hd-content-type='tutorial'}
{:ui: .ph data-hd-interface='ui'}
{:unity: .ph data-hd-programlang='unity'}
{:url: data-credential-placeholder='url'}
{:user_ID: data-hd-keyref="user_ID"}
{:vbnet: .ph data-hd-programlang='vb.net'}
{:video: .video}
 


# Benefits and service offerings
{: #cs_ov}

[{{site.data.keyword.containerlong}}](https://www.ibm.com/cloud/kubernetes-service){: external} delivers powerful tools by combining Docker containers, the Kubernetes technology, an intuitive user experience, and built-in security and isolation to automate the deployment, operation, scaling, and monitoring of containerized apps in a cluster of compute hosts. For more information about certification, see [Compliance on the {{site.data.keyword.cloud_notm}}](https://www.ibm.com/cloud/compliance){: external}.
{: shortdesc}

Check out the following <a href="https://www.ibm.com/demos/collection/Containers-(Kubernetes)-on-IBM-Cloud/?lc=null">videos</a> to learn more about how you can use {{site.data.keyword.containerlong_notm}} to modernize and run containerized apps.
{: tip}


## Benefits of using the service
{: #benefits}

Clusters are deployed on compute hosts that provide native Kubernetes and {{site.data.keyword.IBM_notm}}-specific capabilities.
{: shortdesc}

Ready to get started? Try out the [creating a Kubernetes cluster tutorial](/docs/containers?topic=containers-cs_cluster_tutorial#cs_cluster_tutorial).

|Benefit|Description|
|-------|-----------|
|Choice of container platform provider | <ul><li>Deploy clusters with **{{site.data.keyword.openshiftshort}}** or community **Kubernetes** installed as the container platform orchestrator.</li><li>Choose the developer experience that fits your company, or run workloads across both {{site.data.keyword.openshiftshort}} or community Kubernetes clusters.</li><li>Built-in integrations from the {{site.data.keyword.cloud_notm}} console to the Kubernetes dashboard or {{site.data.keyword.openshiftshort}} web console.</li><li>Single view and management experience of all your {{site.data.keyword.openshiftshort}} or community Kubernetes clusters from {{site.data.keyword.cloud_notm}}.</li><li>For more information, see [Comparison between {{site.data.keyword.openshiftshort}} and community Kubernetes clusters](#openshift_kubernetes).</li></ul>|
|Single-tenant Kubernetes clusters with compute, network, and storage infrastructure isolation|<ul><li>Create your own customized infrastructure that meets the requirements of your organization.</li><li>Choose between [{{site.data.keyword.cloud_notm}} Classic or VPC infrastructure providers](/docs/containers?topic=containers-infrastructure_providers).</li><li>Provision a dedicated and secured Kubernetes master, worker nodes, virtual networks, and storage by using the resources provided by IBM Cloud infrastructure.</li><li>Fully managed Kubernetes master that is continuously monitored and updated by {{site.data.keyword.IBM_notm}} to keep your cluster available.</li><li>Option to provision worker nodes as bare metal servers for compute-intensive workloads such as data, GPU, and AI.</li><li>Store persistent data, share data between Kubernetes pods, and restore data when needed with the integrated and secure volume service.</li><li>Benefit from full support for all native Kubernetes APIs.</li></ul>|
| Multizone clusters to increase high availability | <ul><li>Easily manage worker nodes of the same flavor (CPU, memory, virtual or physical) with worker pools.</li><li>Guard against zone failure by spreading nodes evenly across select multizones and by using anti-affinity pod deployments for your apps.</li><li>Decrease your costs by using multizone clusters instead of duplicating the resources in a separate cluster.</li><li>Benefit from automatic load balancing across apps with the multizone load balancer (MZLB) that is set up automatically for you in each zone of the cluster.</li></ul>|
| Highly available masters | <ul><li>Reduce cluster downtime such as during master updates with highly available masters that are provisioned automatically when you create a cluster.</li><li>Spread your masters across zones in a [multizone cluster](/docs/containers?topic=containers-ha_clusters#multizone) to protect your cluster from zonal failures.</li></ul> |
|Image security compliance with Vulnerability Advisor|<ul><li>Set up your own repo in our secured Docker private image registry where images are stored and shared by all users in the organization.</li><li>Benefit from automatic scanning of images in your private {{site.data.keyword.cloud_notm}} registry.</li><li>Review recommendations specific to the operating system used in the image to fix potential vulnerabilities.</li></ul>|
|Continuous monitoring of the cluster health|<ul><li>Use the cluster dashboard to quickly see and manage the health of your cluster, worker nodes, and container deployments.</li><li>Find detailed consumption metrics by using {{site.data.keyword.mon_full}} and quickly expand your cluster to meet work loads.</li><li>Review logging information by using {{site.data.keyword.la_full}} to see detailed cluster activities.</li></ul>|
|Secure exposure of apps to the public|<ul><li>Choose between a public IP address, an {{site.data.keyword.IBM_notm}} provided route, or your own custom domain to access services in your cluster from the internet.</li></ul>|
|{{site.data.keyword.cloud_notm}} service integration|<ul><li>Add extra capabilities to your app through the integration of {{site.data.keyword.cloud_notm}} services, such as {{site.data.keyword.watson}} APIs, Blockchain, data services, or Internet of Things.</li></ul>|
{: caption="Benefits of the {{site.data.keyword.containerlong_notm}}" caption-side="top"}

<br />


## Comparison of offerings and their combinations
{: #differentiation}

You can run {{site.data.keyword.containerlong_notm}} in {{site.data.keyword.cloud_notm}} Public, in {{site.data.keyword.cloud_notm}} Private, or in a hybrid setup.
{: shortdesc}


<table summary="The columns are read from left to right. The first column has the type of cloud setup. The second column describes the setup.">
<caption>Differences between {{site.data.keyword.containershort_notm}} setups</caption>
<col width="25%">
 <thead>
 <th>{{site.data.keyword.containershort_notm}} setup</th>
 <th>Description</th>
 </thead>
 <tbody>
 <tr>
 <td>{{site.data.keyword.cloud_notm}} Public, off-premises</td>
 <td>With {{site.data.keyword.cloud_notm}} Public on [shared or dedicated hardware or on bare metal machines](/docs/containers?topic=containers-planning_worker_nodes#planning_worker_nodes), you can host your apps in clusters on the cloud by using {{site.data.keyword.containerlong_notm}}. You can also create a cluster with worker pools in multiple zones to increase high availability for your apps. {{site.data.keyword.containerlong_notm}} on {{site.data.keyword.cloud_notm}} Public delivers powerful tools by combining Docker containers, the Kubernetes technology, an intuitive user experience, and built-in security and isolation to automate the deployment, operation, scaling, and monitoring of containerized apps in a cluster of compute hosts.<br><br>For more information, see [{{site.data.keyword.containerlong_notm}} technology](/docs/containers?topic=containers-service-arch).
 <p class="tip">You can also create your cluster in a Virtual Private Cloud (VPC), which gives you the security of a private cloud environment with isolated networking features along with the dynamic scalability of the public cloud. For more information, see [Overview of Classic and VPC infrastructure providers](/docs/containers?topic=containers-infrastructure_providers).</p>
 </td>
 </tr>
 <tr>
 <td>{{site.data.keyword.cloud_notm}} Private, on-premises</td>
 <td>{{site.data.keyword.cloud_notm}} Private is an application platform that can be installed locally on your own machines. You might choose to use Kubernetes in {{site.data.keyword.cloud_notm}} Private when you need to develop and manage on-premises, containerized apps in your own controlled environment behind a firewall. <br><br>For more information, see the [{{site.data.keyword.cloud_notm}} Private product documentation ![External link icon](../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/support/knowledgecenter/SSBS6K_3.2.x/kc_welcome_containers.html).
 </td>
 </tr>
 <tr>
 <td>Hybrid setup</td>
 <td>Hybrid is the combined use of services that run in {{site.data.keyword.cloud_notm}} Public off-premises and other services that run on-premises, such as an app in {{site.data.keyword.cloud_notm}} Private. Examples for a hybrid setup: <ul><li>Provisioning a cluster with {{site.data.keyword.containerlong_notm}} in {{site.data.keyword.cloud_notm}} Public but connecting that cluster to an on-prem database.</li><li>Provisioning a cluster with {{site.data.keyword.containerlong_notm}} in {{site.data.keyword.cloud_notm}} Private and deploying an app into that cluster. However, this app might use an {{site.data.keyword.ibmwatson}} service, such as {{site.data.keyword.toneanalyzershort}}, in {{site.data.keyword.cloud_notm}} Public.</li></ul><br>To enable communication between services that are running in {{site.data.keyword.cloud_notm}} Public or Dedicated and services that are running on-prem, you must [set up a VPN connection](/docs/containers?topic=containers-vpn). For more information, see [Using {{site.data.keyword.containerlong_notm}} with {{site.data.keyword.cloud_notm}} Private](/docs/containers?topic=containers-hybrid_iks_icp).
 </td>
 </tr>
 </tbody>
</table>

<br />

## Comparison of free and standard clusters
{: #cluster_types}

You can create one free cluster or any number of standard clusters. Try out [free clusters](/docs/containers?topic=containers-getting-started#clusters_gs) to get familiar with a few Kubernetes capabilities, or create standard clusters to use the full capabilities of Kubernetes to deploy apps. Free clusters are automatically deleted after 30 days.
{: shortdesc}

If you have a free cluster and want to upgrade to a standard cluster, you can [create a standard cluster](/docs/containers?topic=containers-clusters#clusters_ui). Then, [copy your deployment configuration files](/docs/containers?topic=containers-update_app#copy_apps_cluster) from your free cluster into the standard cluster.

|Characteristics|Free clusters|Standard clusters|
|---------------|-------------|-----------------|
|[In-cluster networking](/docs/containers?topic=containers-security#network)|<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|
|[Public network app access by a NodePort service to a non-stable IP address](/docs/containers?topic=containers-nodeport)|<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|
|[User access management](/docs/containers?topic=containers-users#access_policies)|<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|
|[{{site.data.keyword.cloud_notm}} service access from the cluster and apps](/docs/containers?topic=containers-service-binding#bind-services)|<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|
|[Disk space on worker node for non-persistent storage](/docs/containers?topic=containers-storage_planning#non_persistent_overview)|<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|
| [Provision {{site.data.keyword.openshiftshort}} clusters](/docs/openshift?topic=openshift-getting-started) | | <img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" /> |
| [Create clusters in a Virtual Private Cloud (VPC)](/docs/containers?topic=containers-vpc_ks_tutorial) | | <img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" /> |
|[Ability to create cluster in every {{site.data.keyword.containerlong_notm}} region](/docs/containers?topic=containers-regions-and-zones)| | <img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" /> |
|[Multizone clusters to increase app high availability](/docs/containers?topic=containers-ha_clusters#multizone)| |<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|
|Replicated masters for higher availability| | <img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" /> |
|[Scalable number of worker nodes to increase capacity](/docs/containers?topic=containers-ca)| |<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|
|[Persistent NFS file-based storage with volumes](/docs/containers?topic=containers-file_storage#file_storage)| |<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|
|[Public or private network app access by a network load balancer (NLB) service to a stable IP address](/docs/containers?topic=containers-loadbalancer)| |<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|
|[Public network app access by an Ingress service to a stable IP address and customizable URL](/docs/containers?topic=containers-ingress-about)| |<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|
|[Portable public IP addresses](/docs/containers?topic=containers-subnets#review_ip)| |<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|
|[Logging and monitoring](/docs/containers?topic=containers-health#logging)| |<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|
|[Option to provision your worker nodes on physical (bare metal) servers](/docs/containers?topic=containers-planning_worker_nodes#planning_worker_nodes)| |<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|
{: caption="Characteristics of free and standard clusters" caption-side="top"}

<br />


## Comparison between {{site.data.keyword.openshiftshort}} and community Kubernetes clusters
{: #openshift_kubernetes}

Both {{site.data.keyword.openshiftlong_notm}} and {{site.data.keyword.containerlong_notm}} clusters are production-ready container platforms that are tailored for enterprise workloads. The following table compares and contrasts some common characteristics that can help you choose which container platform is right for your use case.
{: shortdesc}

|Characteristics|Community Kubernetes clusters|{{site.data.keyword.openshiftshort}} clusters|
|---------------|-------------|-----------------|
|Complete cluster management experience through the {{site.data.keyword.containerlong_notm}} automation tools (API, CLI, console)|<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|
|Worldwide availability in single and multizones|<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|
|Consistent container orchestration across hybrid cloud providers|<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|
|Access to {{site.data.keyword.cloud_notm}} services such as AI|<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|
|Software-defined storage Portworx solution available for multizone data use cases|<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|
|Create a cluster in an IBM Virtual Private Cloud (VPC)|<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|
|Ability to create free clusters|<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />| |
|Latest community Kubernetes distribution|<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />| |
|Scope {{site.data.keyword.cloud_notm}} IAM access policies to access groups for service access roles that sync to cluster RBAC |<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />| |
|Classic infrastructure cluster on only the private network|<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />| |
| GPU bare metal worker nodes | <img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" /> | <img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" /> |
|Integrated IBM Cloud Paks and middleware| |<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|
|Built-in container image streams, builds, and tooling ([read more](https://cloudowski.com/articles/why-managing-container-images-on-openshift-is-better-than-on-kubernetes/){: external})| |<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|
|Integrated CI/CD with Jenkins| |<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|
|Stricter app security context set up by default| |<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|
|Simplified Kubernetes developer experience, with an app console that is suited for beginners| |<img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" />|
|Supported operating system| Ubuntu 16.04 x86_64, 18.04 x86_64 |Red Hat Enterprise Linux 7|
|Preferred external traffic networking| Ingress | Router |
|Secured routes encrypted with {{site.data.keyword.hscrypto}} | | <img src="images/confirm.svg" width="32" alt="Feature available" style="width:32px;" /> |
{: caption="Characteristics of community Kubernetes and {{site.data.keyword.openshiftshort}} clusters" caption-side="top"}






