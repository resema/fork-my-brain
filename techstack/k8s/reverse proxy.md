#gcp #k8s #kubernetes #cloud 

- the component that handles incoming [[HTTP]] [[request]]s and forwards it to the [[service]]
- proxy configuration typically contains a list of [[virtual host]]s and, for each, a list of [[Endpoints]] [[IP]]s
- the proxy uses this information to route the request to an endpoint such as a [[pod]] based on the request path and headers

```plantuml
@startuml
database DNS
component Client
component "Kubernetes cluster" {
portin Proxy
component Pod as p1
component Pod as p2
component Pod as p3
}

Client -u-> DNS
Client --> Proxy
Proxy --> p2
@enduml
```

#### Authorization with Reverse Proxy
![](reverse-proxy-shield.png)

#### Example
- [[LoadBalancer]]
- [[firewall]]
- web server [[Apache]], [[techstack/network/Nginx|Nginx]] 