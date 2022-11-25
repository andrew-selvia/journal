# Create an Ingress to Load Balance over the Cluster

Assuming you have a Google Kubernetes Engine (GKE) cluster with an app running on multiple nodes within the cluster, you will likely want to expose the various pods via a load balancer rather than allowing access to the nodes directly. In that case, you should follow [*Setting up HTTP(S) Load Balancing with Ingress*](https://cloud.google.com/kubernetes-engine/docs/tutorials/http-balancer) which describes how to create an **ingress** which balances the load across your cluster's nodes.
