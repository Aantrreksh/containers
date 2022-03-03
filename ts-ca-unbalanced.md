---

copyright: 
  years: 2014, 2022
lastupdated: "2022-03-03"

keywords: kubernetes, help, network, connectivity, autoscaler

subcollection: containers

content-type: troubleshoot

---


# Why are my autoscaled worker pools unbalanced?
{: #ts-ca-unbalanced}

During a scale-up, the cluster autoscaler balances nodes across zones, with a permitted difference of plus or minus one (+/- 1) worker node. 
{: tsSymptoms}


Your pending workloads might not request enough capacity to make each zone balanced.
{: tsCauses}

In this case, if you want to manually balance the worker pools, [update your cluster autoscaler configmap](/docs/containers?topic=containers-cluster-scaling-enable) to remove the unbalanced worker pool. Then, run the `ibmcloud ks worker-pool rebalance` [command](/docs/containers?topic=containers-kubernetes-service-cli#cs_rebalance), and add the worker pool back to the cluster autoscaler configmap.
{: tsResolve} 



