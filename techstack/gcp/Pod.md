#gcp #k8s #kubernetes #google 

A Pod is a group of [[container]]s with shared storage and networking.

Pod-to-Pod communication on the same [[node]].
Because each node maintains a sepearate [[IP address]] space for its [[pod]]s, the [[node]]s don't need to perform Network Address Translation ([[NAT]]) on the Pod IP addresses. 

The pods can **directly** connect to each other using their native IP addresses.

Every new Pod has a new address:
- [[Kubernetes]] has a answer to find the Pod's IP -> [[service]]