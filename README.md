# scale-ci-starter
Work, status and information related to Scale-CI and OpenShift starter framework integrtion to qualify the clusters.


### What is starter?
Red Hat OpenShift cluster hosted on public cloud and meant for individual learning, experimenting and development.

### Need for Scale-CI Starter integration
Scale-CI automates running various Performance and Scale tests including kubelet density, control plane density, http, networking, storage, prometheus and cluster limits and integration with Starter cluster framework will help qualify the cluster for every build before opening it up for users. 

### Jobs and status of integration
Job   | OCP component/category | Description | Status
----------------- | ------------------------- | ---------------------------- | ------------------------- | 
Node Vertical | Kubelet performance and Cluster Limits | Creates max pods per compute node | :soon: |
Master Vertical | Control plane density | Creates bunch of objects to stress ApiServer, Etcd and Controller | :soon:|
Networking | SDN | uperf benchmarks testing node to node, pod to pod, and svc to svc throughput and latency for TCP and UDP protocols | :soon: |
Prometheus | Monitoring | prometheus density focused test that creates pods, and nodes and some workloads especially for openshift-monitoring | :soon: |
HTTP | Router | Data-plane workload generator that runs http requests through HAProxy into deployed pods | :soon: |
Pod Vertical | Cluster Limits | Tests pods per namespace limit | :soon: |
Deployments per namespaces | Cluster Limits | Tests deployments per namespace limit | :soon: |     
Namespaces per cluster | Cluster Limits | Tests namespaces per cluster limit | :soon: |     
Services per namespace | Cluster Limits | Tests maximum number of services possible per namespace | :soon: |

NOTE: Services per namespace cluster limits test is covered by Deployments per ns test, creating a separate job for it is in progress.

### Requirements
Cluster Limits tests need large sized cluster (~ 150 - 200 nodes ) to validate and push the current Limits. Since the goal of the integration is to qualify/validate the current supported limits, the plan is to run only the limits tests possible at the cluster size supported by OpenShift starter test clusters.
