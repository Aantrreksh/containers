---

copyright:
  years: 2014, 2021
lastupdated: "2021-02-25"

keywords: kubernetes, iks, help

subcollection: containers
content-type: troubleshoot

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



# Apps and services
{: #cs_troubleshoot_app}

As you use {{site.data.keyword.containerlong}}, consider these techniques for troubleshooting app deployments and integrated services.
{: shortdesc}

**Infrastructure provider**:
  * <img src="images/icon-classic.png" alt="Classic infrastructure provider icon" width="15" style="width:15px; border-style: none"/> Classic
  * <img src="images/icon-vpc.png" alt="VPC infrastructure provider icon" width="15" style="width:15px; border-style: none"/> VPC Generation 2 compute

While you troubleshoot, you can use the [{{site.data.keyword.containerlong_notm}} Diagnostics and Debug Tool](/docs/containers?topic=containers-cs_troubleshoot#debug_utility) to run tests and gather pertinent information from your cluster.
{: tip}

## Debugging app deployments
{: #debug_apps}

Review the options that you have to debug your app deployments and find the root causes for failures.

Before you begin, ensure you have the [**Writer** or **Manager** {{site.data.keyword.cloud_notm}} IAM service role](/docs/containers?topic=containers-users#platform) for the namespace where your app is deployed.

1. Look for abnormalities in the service or deployment resources by running the `describe` command.
    ```
    kubectl describe service <service_name>
    ```
    {: pre}

2. [Check whether the containers are stuck in the `ContainerCreating` state](/docs/containers?topic=containers-cs_troubleshoot_storage#stuck_creating_state).

3. Check whether the cluster is in the `Critical` state. If the cluster is in a `Critical` state, check the firewall rules and verify that the master can communicate with the worker nodes.

4. Verify that the service is listening on the correct port.
   1. Get the name of a pod.
      ```
      kubectl get pods
      ```
      {: pre}
   2. Log in to a container.
      ```
      kubectl exec -it <pod_name> -- /bin/bash
      ```
      {: pre}
   3. Curl the app from within the container. If the port is not accessible, the service might not be listening on the correct port or the app might have issues. Update the configuration file for the service with the correct port and redeploy or investigate potential issues with the app.
      ```
      curl localhost: <port>
      ```
      {: pre}

5. Verify that the service is linked correctly to the pods.
   1. Get the name of a pod.
      ```
      kubectl get pods
      ```
      {: pre}
   2. Log in to a container.
      ```
      kubectl exec -it <pod_name> -- /bin/bash
      ```
      {: pre}
   3. Curl the cluster IP address and port of the service.
      ```
      curl <cluster_IP>:<port>
      ```
      {: pre}
   4. If the IP address and port are not accessible, look at the endpoints for the service.
      * If no endpoints are listed, then the selector for the service does not match the pods. For example, your app deployment might have the label `app=foo`, but the service might have the selector `run=foo`.
      * If endpoints are listed, then look at the target port field on the service and make sure that the target port is the same as what is being used for the pods. For example, your app might listen on port 9080, but the service might listen on port 80.

6. For Ingress services, verify that the service is accessible from within the cluster.
   1. Get the name of a pod.
      ```
      kubectl get pods
      ```
      {: pre}
   2. Log in to a container.
      ```
      kubectl exec -it <pod_name> -- /bin/bash
      ```
      {: pre}
   2. Curl the URL specified for the Ingress service. If the URL is not accessible, check for a firewall issue between the cluster and the external endpoint.
      ```
      curl <host_name>.<domain>
      ```
      {: pre}

<br />



## Failed to pull image from registry with `ImagePullBackOff` or authorization errors
{: #ts_image_pull}

{: tsSymptoms}

When you deploy a workload that pulls an image from {{site.data.keyword.registrylong_notm}}, your pods fail with an **`ImagePullBackOff`** status.

```
kubectl get pods
```
{: pre}

```
NAME         READY     STATUS             RESTARTS   AGE
<pod_name>   0/1       ImagePullBackOff   0          2m
```
{: screen}

When you describe the pod, you see authentication errors similar to the following.

```
kubectl describe pod <pod_name>
```
{: pre}

```
Failed to pull image "<region>.icr.io/<namespace>/<image>:<tag>" ... unauthorized: authentication required
Failed to pull image "<region>.icr.io/<namespace>/<image>:<tag>" ... 401 Unauthorized
```
{: screen}

```
Failed to pull image "registry.ng.bluemix.net/<namespace>/<image>:<tag>" ... unauthorized: authentication required
Failed to pull image "registry.ng.bluemix.net/<namespace>/<image>:<tag>" ... 401 Unauthorized
```
{: screen}

{: tsCauses}
Your cluster uses an API key or token that is stored in an [image pull secret](/docs/containers?topic=containers-registry#cluster_registry_auth) to authorize the cluster to pull images from {{site.data.keyword.registrylong_notm}}. By default, new clusters have image pull secrets that use API keys so that the cluster can pull images from any regional `icr.io` registry for containers that are deployed to the `default` Kubernetes namespace.

For clusters that were created before **1 July 2019**, the cluster might have an image pull secret that uses a token. Tokens grant access to {{site.data.keyword.registrylong_notm}} for only certain regional registries that use the deprecated `<region>.registry.bluemix.net` domains.

{: tsResolve}

1.  Verify that you use the correct name and tag of the image in your deployment YAML file.
    ```
    ibmcloud cr images
    ```
    {: pre}
2.  Check your [pull traffic and storage quota](/docs/Registry?topic=Registry-registry_quota). If the limit is reached, free up used storage or ask your registry administrator to increase the quota.
    ```
    ibmcloud cr quota
    ```
    {: pre}
3.  Get the pod configuration file of a failing pod, and look for the `imagePullSecrets` section.
    ```
    kubectl get pod <pod_name> -o yaml
    ```
    {: pre}

    Example output:
    ```
    ...
    imagePullSecrets:
    - name: all-icr-io
    ...
    ```
    {: screen}
4.  If no image pull secrets are listed, set up the image pull secret in your namespace.
    1.  Verify that the `default` namespace has `icr-io` image pull secrets for each regional registry that you want to use. If no `icr-io` secrets are listed in the namespace, [use the `ibmcloud ks cluster pull-secret apply --cluster <cluster_name_or_ID>` command](/docs/containers?topic=containers-registry#imagePullSecret_migrate_api_key) to create the image pull secrets in the `default` namespace.
        ```
        kubectl get secrets -n default | grep "icr-io"
        ```
        {: pre}
    2.  [Copy the `all-icr-io` image pull secret from the `default` Kubernetes namespace to the namespace where you want to deploy your workload](/docs/containers?topic=containers-registry#copy_imagePullSecret).
    3.  [Add the image pull secret to the service account for this Kubernetes namespace](/docs/containers?topic=containers-registry#store_imagePullSecret) so that all pods in the namespace can use the image pull secret credentials.
5.  If image pull secrets are listed in the pod, determine what type of credentials you use to access {{site.data.keyword.registrylong_notm}}.
    *   **Deprecated**: If the secret has `bluemix` in the name, you use a registry token to authenticate with the deprecated `registry.<region>.bluemix.net` domain names. Continue with [Troubleshooting image pull secrets that use tokens](#ts_image_pull_token).
    *   If the secret has `icr` in the name, you use an API key to authenticate with the `icr.io` domain names. Continue with [Troubleshooting image pull secrets that use API keys](#ts_image_pull_apikey).
    *   If you have both types of secrets, then you use both authentication methods. Going forward, use the `icr.io` domain names in your deployment YAMLs for the container image. Continue with [Troubleshooting image pull secrets that use API keys](#ts_image_pull_apikey).

<br>
<br>

**Troubleshooting image pull secrets that use API keys**
{: #ts_image_pull_apikey}

If your pod configuration has an image pull secret that uses an API key, check that the API key credentials are set up correctly.
{: shortdesc}

The following steps assume that the API key stores the credentials of a service ID. If you set up your image pull secret to use an API key of an individual user, you must verify that user's {{site.data.keyword.cloud_notm}} IAM permissions and credentials.
{: note}

1.  Find the service ID that API key uses for the image pull secret by reviewing the **Description**. The service ID that is created with the cluster is named `cluster-<cluster_ID>` and is used in the `default` Kubernetes namespace. If you created another service ID such as to access a different Kubernetes namespace or to modify {{site.data.keyword.cloud_notm}} IAM permissions, you customized the description.
    ```
    ibmcloud iam service-ids
    ```
    {: pre}

    Example output:
    ```
    UUID                Name               Created At              Last Updated            Description                                                                                                                                                                                         Locked
    ServiceId-aa11...   <service_ID_name>  2019-02-01T19:01+0000   2019-02-01T19:01+0000   ID for <cluster_name>                                                                                                                                         false
    ServiceId-bb22...   <service_ID_name>  2019-02-01T19:01+0000   2019-02-01T19:01+0000   Service ID for IBM Cloud Container Registry in Kubernetes cluster <cluster_name> namespace <namespace>                                                                                                                                         false
    ```
    {: screen}
2.  Verify that the service ID is assigned at least an {{site.data.keyword.cloud_notm}} IAM **Reader** [service access role policy for {{site.data.keyword.registrylong_notm}}](/docs/Registry?topic=Registry-user#create). If the service ID does not have the **Reader** service role, [edit the IAM policies](/docs/account?topic=account-serviceids#update_serviceid). If the policies are correct, continue with the next step to see if the credentials are valid.
    ```
    ibmcloud iam service-policies <service_ID_name>
    ```
    {: pre}

    Example output:
    ```
    Policy ID:   a111a111-b22b-333c-d4dd-e555555555e5
    Roles:       Reader
    Resources:
                  Service Name       container-registry
                  Service Instance
                  Region
                  Resource Type      namespace
                  Resource           <registry_namespace>
    ```
    {: screen}
3.  Check if the image pull secret credentials are valid.
    1.  Get the image pull secret configuration. If the pod is not in the `default` namespace, include the `-n` flag.
        ```
        kubectl get secret <image_pull_secret_name> -o yaml [-n <namespace>]
        ```
        {: pre}
    2.  In the output, copy the base64 encoded value of the `.dockerconfigjson` field.
        ```
        apiVersion: v1
        kind: Secret
        data:
          .dockerconfigjson: eyJyZWdp...==
        ...
        ```
        {: screen}
    3.  Decode the base64 string. For example, on OS X you can run the following command.
        ```
        echo -n "<base64_string>" | base64 --decode
        ```
        {: pre}

        Example output:
        ```
        {"auths":{"<region>.icr.io":{"username":"iamapikey","password":"<password_string>","email":"<name@abc.com>","auth":"<auth_string>"}}}
        ```
        {: screen}
    4.  Compare the image pull secret regional registry domain name with the domain name that you specified in the container image. By default, new clusters have image pull secrets for each regional registry domain name for containers that run in the `default` Kubernetes namespace. However, if you modified the default settings or are using a different Kubernetes namespace, you might not have an image pull secret for the regional registry. [Copy an image pull secret](/docs/containers?topic=containers-registry#copy_imagePullSecret) for the regional registry domain name.
    5.  Log in to the registry from your local machine by using the `username` and `password` from your image pull secret. If you cannot log in, you might need to fix the service ID.
        ```
        docker login -u iamapikey -p <password_string> <region>.icr.io
        ```
        {: pre}
        1.  Re-create the cluster service ID, {{site.data.keyword.cloud_notm}} IAM policies, API key, and image pull secrets for containers that run in the `default` Kubernetes namespace.
            ```
            ibmcloud ks cluster pull-secret apply --cluster <cluster_name_or_ID>
            ```
            {: pre}
        2.  Re-create your deployment in the `default` Kubernetes namespace. If you still see an authorization error message, repeat Steps 1-5 with the new image pull secrets. If you still cannot log in, [open an {{site.data.keyword.cloud_notm}} Support case](/docs/containers?topic=containers-get-help).
    6.  If the login succeeds, pull an image locally. If the command fails with an `access denied` error, the registry account is in a different {{site.data.keyword.cloud_notm}} account than the one your cluster is in. [Create an image pull secret to access images in the other account](/docs/containers?topic=containers-registry#other_registry_accounts). If you can pull an image to your local machine, then your API key has the right permissions, but the API setup in your cluster is not correct. You cannot resolve this issue. [Open an {{site.data.keyword.cloud_notm}} Support case](/docs/containers?topic=containers-get-help).
        ```
        docker pull <region>icr.io/<namespace>/<image>:<tag>
        ```
        {: pre}

<br>
<br>

**Deprecated: Troubleshooting image pull secrets that use tokens**
{: #ts_image_pull_token}

If your pod configuration has an image pull secret that uses a token, check that the token credentials are valid.
{: shortdesc}

This method of using a token to authorize cluster access to {{site.data.keyword.registrylong_notm}} for the `registry.bluemix.net` domain names is deprecated. Before tokens become unsupported, update your deployments to [use the API key method](/docs/containers?topic=containers-registry#cluster_registry_auth) to authorize cluster access to the new `icr.io` registry domain names.
{: deprecated}

1.  Get the image pull secret configuration. If the pod is not in the `default` namespace, include the `-n` flag.
    ```
    kubectl get secret <image_pull_secret_name> -o yaml [-n <namespace>]
    ```
    {: pre}
2.  In the output, copy the base64 encoded value of the `.dockercfg` field.
    ```
    apiVersion: v1
    kind: Secret
    data:
      .dockercfg: eyJyZWdp...==
    ...
    ```
    {: screen}
3.  Decode the base64 string. For example, on OS X you can run the following command.
    ```
    echo -n "<base64_string>" | base64 --decode
    ```
    {: pre}

    Example output:
    ```
    {"auths":{"registry.<region>.bluemix.net":{"username":"token","password":"<password_string>","email":"<name@abc.com>","auth":"<auth_string>"}}}
    ```
    {: screen}
4.  Compare the registry domain name with the domain name that you specified in the container image. For example, if the image pull secret authorizes access to the `registry.ng.bluemix.net` domain but you specified an image that is stored in `registry.eu-de.bluemix.net`, you must [create a token to use in an image pull secret](/docs/containers?topic=containers-images#token_other_regions_accounts) for `registry.eu-de.bluemix.net`.
5.  Log in to the registry from your local machine by using the `username` and `password` from the image pull secret. If you cannot log in, the token has an issue that you cannot resolve. [Open an {{site.data.keyword.cloud_notm}} Support case](/docs/containers?topic=containers-get-help).
    ```
    docker login -u token -p <password_string> registry.<region>.bluemix.net
    ```
    {: pre}
6.  If the login succeeds, pull an image locally. If the command fails with an `access denied` error, the registry account is in a different {{site.data.keyword.cloud_notm}} account than the one your cluster is in. [Create an image pull secret to access images in the other account](/docs/containers?topic=containers-images#token_other_regions_accounts). If the command succeeds, [open an {{site.data.keyword.cloud_notm}} Support case](/docs/containers?topic=containers-get-help).
    ```
    docker pull registry.<region>.bluemix.net/<namespace>/<image>:<tag>
    ```
    {: pre}

<br />

## Containers do not start
{: #containers_do_not_start}

{: tsSymptoms}
The pods deploy successfully to clusters, but the containers do not start.

{: tsCauses}
Containers might not start when the registry quota is reached.

{: tsResolve}
[Free up storage in {{site.data.keyword.registrylong_notm}}.](/docs/Registry?topic=Registry-registry_quota#registry_quota_freeup)

<br />


## Pods fail to deploy because of a pod security policy
{: #cs_psp}

{: tsSymptoms}
After creating a pod or running `kubectl get events` to check on a pod deployment, you see an error message similar to the following.

```
unable to validate against any pod security policy
```
{: screen}

{: tsCauses}
[The `PodSecurityPolicy` admission controller](/docs/containers?topic=containers-psp) checks the authorization of the user or service account that tried to create the pod. If no pod security policy supports the user or service account, then the `PodSecurityPolicy` admission controller prevents the pods from being created.

If you deleted one of the pod security policy resources for [{{site.data.keyword.IBM_notm}} cluster management](/docs/containers?topic=containers-psp#ibm_psp), you might experience similar issues.

{: tsResolve}
Make sure that the user or service account is authorized by a pod security policy. You might need to [modify an existing policy](/docs/containers?topic=containers-psp#customize_psp).

If you deleted an {{site.data.keyword.IBM_notm}} cluster management resource, refresh the Kubernetes master to restore it.

1.  [Log in to your account. If applicable, target the appropriate resource group. Set the context for your cluster.](/docs/containers?topic=containers-cs_cli_install#cs_cli_configure)
2.  Refresh the Kubernetes master to restore it.

    ```
    ibmcloud ks cluster master refresh
    ```
    {: pre}

<br />


## Pods remain in pending state
{: #cs_pods_pending}

{: tsSymptoms}
When you run `kubectl get pods`, you can see pods that remain in a **Pending** state.

{: tsCauses}
If you just created the Kubernetes cluster, the worker nodes might still be configuring.

If this cluster is an existing one:
*  You might not have enough capacity in your cluster to deploy the pod.
*  The pod might have exceeded a resource request or limit.

{: tsResolve}
This task requires the {{site.data.keyword.cloud_notm}} IAM [**Administrator** platform role](/docs/containers?topic=containers-users#platform) for the cluster and the [**Manager** service role](/docs/containers?topic=containers-users#platform) for all namespaces.

If you just created the Kubernetes cluster, run the following command and wait for the worker nodes to initialize.

```
kubectl get nodes
```
{: pre}

If this cluster is an existing one, check your cluster capacity.


1.  Set the proxy with the default port number.

  ```
  kubectl proxy
  ```
   {: pre}

2.  Open the Kubernetes dashboard.

  ```
  http://localhost:8001/ui
  ```
  {: pre}

3.  Check if you have enough capacity in your cluster to deploy your pod.

4.  If you don't have enough capacity in your cluster, resize your worker pool to add more nodes.

    1.  Review the current sizes and flavors of your worker pools to decide which one to resize.

        ```
        ibmcloud ks worker-pool ls
        ```
        {: pre}

    2.  Resize your worker pools to add more nodes to each zone that the pool spans.

        ```
        ibmcloud ks worker-pool resize --worker-pool <worker_pool> --cluster <cluster_name_or_ID> --size-per-zone <workers_per_zone>
        ```
        {: pre}

5.  Optional: Check your pod resource requests.

    1.  Confirm that the `resources.requests` values are not larger than the worker node's capacity. For example, if the pod request `cpu: 4000m`, or 4 cores, but the worker node size is only 2 cores, the pod cannot be deployed.

        ```
        kubectl get pod <pod_name> -o yaml
        ```
        {: pre}

    2.  If the request exceeds the available capacity, [add a new worker pool](/docs/containers?topic=containers-add_workers#add_pool) with worker nodes that can fulfill the request.

6.  If your pods still stay in a **pending** state after the worker node is fully deployed, review the [Kubernetes documentation](https://kubernetes.io/docs/tasks/debug-application-cluster/debug-pod-replication-controller/#my-pod-stays-pending){: external} to further troubleshoot the pending state of your pod.

<br />



## Pods repeatedly fail to restart or are unexpectedly removed
{: #pods_fail}

{: tsSymptoms}
Your pod was healthy but unexpectedly gets removed or gets stuck in a restart loop.

{: tsCauses}
Your containers might exceed their resource limits, or your pods might be replaced by higher priority pods.

{: tsResolve}
To see if a container is being killed because of a resource limit:
<ol><li>Get the name of your pod. If you used a label, you can include it to filter your results.<pre class="pre"><code>kubectl get pods --selector='app=wasliberty'</code></pre></li>
<li>Describe the pod and look for the **Restart Count**.<pre class="pre"><code>kubectl describe pod</code></pre></li>
<li>If the pod restarted many times in a short period of time, fetch its status. <pre class="pre"><code>kubectl get pod <pod_name> -n <namespace> -o go-template='{{range.status.containerStatuses}}{{"Container Name: "}}{{.name}}{{"\r\nLastState: "}}{{.lastState}}{{end}}'</code></pre></li>
<li>Review the reason. For example, `OOM Killed` means "out of memory," indicating that the container is crashing because of a resource limit.</li>
<li>Add capacity to your cluster so that the resources can be fulfilled.</li></ol>

<br>

To see if your pod is being replaced by higher priority pods:
1.  Get the name of your pod.

    ```
    kubectl get pods
    ```
    {: pre}

2.  Describe your pod YAML.

    ```
    kubectl get pod <pod_name> -o yaml
    ```
    {: pre}

3.  Check the `priorityClassName` field.

    1.  If there is no `priorityClassName` field value, then your pod has the `globalDefault` priority class. If your cluster admin did not set a `globalDefault` priority class, then the default is zero (0), or the lowest priority. Any pod with a higher priority class can preempt, or remove, your pod.

    2.  If there is a `priorityClassName` field value, get the priority class.

        ```
        kubectl get priorityclass <priority_class_name> -o yaml
        ```
        {: pre}

    3.  Note the `value` field to check your pod's priority.

4.  List existing priority classes in the cluster.

    ```
    kubectl get priorityclasses
    ```
    {: pre}

5.  For each priority class, get the YAML file and note the `value` field.

    ```
    kubectl get priorityclass <priority_class_name> -o yaml
    ```
    {: pre}

6.  Compare your pod's priority class value with the other priority class values to see if it is higher or lower in priority.

7.  Repeat steps 1 to 3 for other pods in the cluster, to check what priority class they are using. If those other pods' priority class is higher than your pod, your pod is not provisioned unless there is enough resources for your pod and every pod with higher priority.

8.  Contact your cluster admin to add more capacity to your cluster and confirm that the right priority classes are assigned.

<br />

## Binding a service to a cluster results in same name error
{: #cs_duplicate_services}

{: tsSymptoms}
When you run `ibmcloud ks cluster service bind --cluster <cluster_name> --namespace <namespace> --service <service_instance_name>`, you see the following message.

```
Multiple services with the same name were found.
Run 'ibmcloud service list' to view available Bluemix service instances...
```
{: screen}

{: tsCauses}
Multiple service instances might have the same name in different regions.

{: tsResolve}
Use the service GUID instead of the service instance name in the `ibmcloud ks cluster service bind` command.

1. [Log in to the {{site.data.keyword.cloud_notm}} region that includes the service instance to bind.](/docs/containers?topic=containers-regions-and-zones#bluemix_regions)

2. Get the GUID for the service instance.
  ```
  ibmcloud service show <service_instance_name> --guid
  ```
  {: pre}

  Output:
  ```
  Invoking 'cf service <service_instance_name> --guid'...
  <service_instance_GUID>
  ```
  {: screen}
3. Bind the service to the cluster again.
  ```
  ibmcloud ks cluster service bind --cluster <cluster_name> --namespace <namespace> --service <service_instance_GUID>
  ```
  {: pre}

<br />

## Binding a service to a cluster results in service not found error
{: #cs_not_found_services}

{: tsSymptoms}
When you run `ibmcloud ks cluster service bind --cluster <cluster_name> --namespace <namespace> --service <service_instance_name>`, you see the following message.

```
Binding service to a namespace...
FAILED

The specified IBM Cloud service could not be found. If you just created the service, wait a little and then try to bind it again. To view available IBM Cloud service instances, run 'ibmcloud service list'. (E0023)
```
{: screen}

{: tsCauses}
To bind services to a cluster, you must have the Cloud Foundry developer user role for the space where the service instance is provisioned. In addition, you must have the {{site.data.keyword.cloud_notm}} IAM Editor platform access to {{site.data.keyword.containerlong_notm}}. To access the service instance, you must be logged in to the space where the service instance is provisioned.

{: tsResolve}

**As the user:**

1. Log in to {{site.data.keyword.cloud_notm}}.
   ```
   ibmcloud login
   ```
   {: pre}

2. Target the org and the space where the service instance is provisioned.
   ```
   ibmcloud target -o <org> -s <space>
   ```
   {: pre}

3. Verify that you are in the right space by listing your service instances.
   ```
   ibmcloud service list
   ```
   {: pre}

4. Try binding the service again. If you get the same error, then contact the account administrator and verify that you have sufficient permissions to bind services (see the following account admin steps).

**As the account admin:**

1. Verify that the user who experiences this problem has [Editor permissions for {{site.data.keyword.containerlong_notm}}](/docs/containers?topic=containers-users#platform).

2. Verify that the user who experiences this problem has the [Cloud Foundry developer role for the space](/docs/account?topic=account-mngcf#update_cf_access) where the service is provisioned.

3. If the correct permissions exists, try assigning a different permission and then re-assigning the required permission.

4. Wait a few minutes, then let the user try to bind the service again.

5. If this does not resolve the problem, then the {{site.data.keyword.cloud_notm}} IAM permissions are out of sync and you cannot resolve the issue yourself. [Contact IBM support](/docs/get-support?topic=get-support-using-avatar) by opening a support case. Make sure to provide the cluster ID, the user ID, and the service instance ID.
   1. Retrieve the cluster ID.
      ```
      ibmcloud ks cluster ls
      ```
      {: pre}

   2. Retrieve the service instance ID.
      ```
      ibmcloud service show <service_name> --guid
      ```
      {: pre}


<br />

## Binding a service to a cluster results in service does not support service keys error
{: #cs_service_keys}

{: tsSymptoms}
When you run `ibmcloud ks cluster service bind --cluster <cluster_name> --namespace <namespace> --service <service_instance_name>`, you see the following message.

```
This service doesn't support creation of keys
```
{: screen}

{: tsCauses}

Some services in {{site.data.keyword.cloud_notm}}, such as {{site.data.keyword.keymanagementservicelong}} do not support the creation of service credentials, also referred to as service keys. Without the support of service keys, the service is not bindable to a cluster. To find a list of services that support the creation of service keys, see [Enabling external apps to use {{site.data.keyword.cloud_notm}} services](/docs/account?topic=account-externalapp#externalapp).


{: tsResolve}
To integrate services that do not support service keys, check if the service provides an API that you can use to access the service directly from your app. For example, if you want to use {{site.data.keyword.keymanagementservicelong}}, see the [API reference](https://cloud.ibm.com/apidocs/key-protect){: external}.

<br />

## Cannot install a Helm chart with updated configuration values
{: #cs_helm_install}

{: tsSymptoms}
When you try to install an updated Helm chart by running `helm install <release_name> <helm_repo>/<chart_name> -f config.yaml`, you get the `Error: failed to download "<helm_repo>/<chart_name>"` error message.

{: tsCauses}
You might need to update your Helm installation because of the following reasons:
* The URL to the {{site.data.keyword.cloud_notm}} Helm repository that is configured on your local machine might be incorrect.
* The name of your local Helm repository might not match the Helm repository name or URL of the installation command that you copied from the Helm chart instructions.
* The Helm chart that you want to install does not support the version of Helm that you installed on your local machine.
* Your cluster network setup changed from public access to private-only access, but Helm was not updated.

{: tsResolve}
To troubleshoot your Helm chart:

1.  List the {{site.data.keyword.cloud_notm}} Helm repositories currently available in your Helm instance.
    ```
    helm repo list
    ```
    {: pre}
2.  Remove the {{site.data.keyword.cloud_notm}} Helm repositories.
    ```
    helm repo remove <helm_repo>
    ```
    {: pre}
3.  Reinstall the Helm version that matches a supported version of the Helm chart that you want to install. As part of the reinstallation, you add and update the {{site.data.keyword.cloud_notm}} Helm repositories. For more information, see [Installing Helm v3 in your cluster](/docs/containers?topic=containers-helm#install_v3).


Now, you can follow the instructions in the Helm chart `README` to install the Helm chart in your cluster.

<br />
