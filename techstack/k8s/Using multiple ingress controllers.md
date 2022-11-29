#gcp #k8s #kubernetes #ingress 

Since different [Ingress](/techstack/k8s/Ingress.md) implementations provide different additional functionality, you may want to install multiple [Ingress controller](/techstack/k8s/Ingress%20controller.md)s in a cluster.

This is possible by using the [annotation](/annotation), but the correct way to specify the controller to use is through [IngressClass](/IngressClass) objects.