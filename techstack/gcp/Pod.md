#gcp #k8s #kubernetes #google 

A Pod is a group of [[container]]s with shared storage and networking.

Pod-to-Pod communication on the same [[Node]].
Because each node maintains a sepearate [[IP address]] space for its [[Pod]]s, the [[Node]]s don't need to perform Network Address Translation ([[NAT]]) on the Pod IP addresses. 

The pods can **directly** connect to each other using their native IP addresses.