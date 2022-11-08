#gcp #k8s #kubernetes #ingress 

Since different [[Ingress]] implementations provide different additional functionality, you may want to install multiple [[Ingress controller]]s in a cluster.

This is possible by using the [[annotation]], but the correct way to specify the controller to use is through [[IngressClass]] objects.