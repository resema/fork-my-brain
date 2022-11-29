#gcp #k8s #cloud #ingress

- The ingress controller is the software component that brings the [Ingress](/techstack/k8s/Ingress.md) object to life.
- The controller connects to the Kubernetes [API](/techstack/google/API.md) server and monitors the [Ingress](/techstack/k8s/Ingress.md), [Service](/techstack/gcp/service.md), and [Endpoints](/Endpoints) or [EndpointSlice](/EndpointSlice) objects.
- configures the [reverse proxy](/techstack/k8s/reverse%20proxy.md)
- watches the connected objects (see above)
- support [TLS](/techstack/security/TLS.md) termination at the [Ingress](/techstack/k8s/Ingress.md) [proxy](/proxy)
	- terminates the [TLS](/techstack/security/TLS.md) connection between the client and itself
	- forwards the [HTTP](/techstack/network/HTTP.md) request unencrypted to the backend pod