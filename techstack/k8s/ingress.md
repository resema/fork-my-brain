#gcp #cloud #ingress

- Ingress is a layer higher than [[service]]s. A bit like a [[service]] for [[service]]s.
	- its a [[reverse proxy]]
- Exposes a single [[IP address]]
	- in [[multi-zonal]] [[cluster]]s a single ingress can handle traffic for all of them
- most popular [[techstack/k8s/Ingress controller|Ingress controller]]s
	- [[Nginx]], [[Ambassador]], [[Contour]] and [[Traefik]]
		- most of these use [[Nginx]], [[HAProxy]] or [[Envoy]] as the [[reverse proxy]]

- Combines an Google cloud [[LoadBalancer]] with [[kubernetes]] [[service]]s
- Ingress can direct traffic to:
	- [[NodePort]] services
	- [[LoadBalancer]] services
		- still have the [[double-hop dilemma]]
			- can be migrated by using the [[Local external-traffic policy]] in the [[service]] [[manifest]]
	- Ingress object conatins [[techstack/k8s/rules|rules]] that specify to which [[service]] to forward traffic based on the information in the [[HTTP]] [[request]]
		- public [[DNS]] entries for the services all point to the same Ingress
- Multiple Ingress objects are also an option
	- normally each Ingress object get its own [[IP address]]
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
- supports multiple host names for the same [[IP address]]
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
	- [[identity aware proxy|IAP]]
	- [[Google Cloud Armor]]
	- [[Cloud CDN]]
- provides [[TLS]] termination
- multiple [[SSL]] certificates
- [[HTTP/2]] and [[gRPC]]
- [[multi-cluster]] and [[multi-region]] support