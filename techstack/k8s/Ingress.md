#gcp #cloud #ingress

- Ingress is a layer higher than [service](/techstack/gcp/service.md)s. A bit like a [service](/techstack/gcp/service.md) for [service](/techstack/gcp/service.md)s.
	- its a [reverse proxy](/techstack/k8s/reverse%20proxy.md)
- Exposes a single [IP address](/IP%20address)
	- in [multi-zonal](/multi-zonal) [cluster](/cluster)s a single ingress can handle traffic for all of them
- most popular [Ingress controller](/techstack/k8s/Ingress%20controller.md)s
	- [nginx](/questions/nginx.md) ([questions](/questions/nginx.md)), [Ambassador](/Ambassador), [Contour](/Contour) and [Traefik](/Traefik)
		- most of these use [nginx](/questions/nginx.md), [HAProxy](/HAProxy) or [Envoy](/Envoy) as the [reverse proxy](/techstack/k8s/reverse%20proxy.md)

- Combines an Google cloud [LoadBalancer](/techstack/k8s/LoadBalancer.md) with [kubernetes](/kubernetes) [service](/techstack/gcp/service.md)s
- Ingress can direct traffic to:
	- [nodePort](/techstack/gcp/nodePort.md) services
	- [LoadBalancer](/techstack/k8s/LoadBalancer.md) services
		- still have the [double-hop dilemma](/techstack/k8s/double-hop%20dilemma.md)
			- can be migrated by using the [Local external-traffic policy](/techstack/gcp/Local%20external-traffic%20policy.md) in the [service](/techstack/gcp/service.md) [manifest](/manifest)
	- Ingress object conatins [rules](/techstack/k8s/rules) that specify to which [service](/techstack/gcp/service.md) to forward traffic based on the information in the [HTTP](/techstack/network/HTTP.md) [request](/request)
		- public [DNS](/DNS) entries for the services all point to the same Ingress
- Multiple Ingress objects are also an option
	- normally each Ingress object get its own [IP address](/IP%20address)
```yaml
apiVersion: network.k8s.io/v1
kind: Ingress
metadata:
  name: test-ingress
spec:
    backend:
        serviceName: demo
        servicePort: 80
```

```yaml
apiVersion: network.k8s.io/v1
kind: Ingress
metadata:
  name: my-Ingress
spec:
  rules:
  - host: demo1.example.com
    http:
      paths:
      - path: /demo1examplepath
          backend:
            serviceName: demo
            serviePort: 80
```
- Ingress: `demo1.example.com/demo1examplepath`
- supports multiple host names for the same [IP address](/IP%20address)
- defining a default backend also possible
  ```yaml
  [...]
  spec:
    backend:
      serviceName: my404service
      servicePort: 80
```

### additional ingress features
- natively supports many Google cloud services
	- [IAP](/identity%20aware%20proxy)
	- [Google Cloud Armor](/Google%20Cloud%20Armor)
	- [Cloud CDN](/Cloud%20CDN)
- provides [TLS](/techstack/security/TLS.md) termination
- multiple [SSL](/SSL) certificates
- [HTTP/2](/HTTP/2) and [gRPC](/techstack/google/gRPC.md)
- [multi-cluster](/multi-cluster) and [multi-region](/multi-region) support