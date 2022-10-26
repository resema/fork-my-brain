#gcp #cloud #security

- [[pod]]-level [[firewall]] restricting access to other [[pod]]s and [[service]]s
- limit the [[attack surface]] of your [[cluster]]
- lock down traffic to allow only legitmate network pathways

- network policies must be enabled:
	- requires at least 2 [[node]]s of [[n1-standard-1]] or higher
	- requires [[node]]s to be recreated

#### Commands
Enabling a network policy
```sh
# enable a network policy for a new cluster
$ gcloud container clusters create [NAME] --enable-network-policy

# disable a network policy for a cluster
$ gcloud container clusters create [NAME] --no-enable-network-policy
```

```sh
# enable a network policy for an existing cluster
$ gcloud container clusters update [NAME] --update-addons-NetworkPolicy=ENABLED
$ gcloud container clusters update [NAME] --enable-network-policy
```

```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: demo-network-policy
  namespace: default
spec:
  podSelector:
    matchLabels:
      role: demo-app
  policyTypes:
  - Ingress # nothing to do with Ingress Service
  - Egress
  
  ingress:
  - from:
	- ipBlock:
	    cidr: 172.17.0.0/16
	    exepct:
	    - 172.17.1.0./24
	- namespaceSelector:
	    matchLabels:
	      project: myproject
	- podSelector:
	    matchLabels:
	      role: frontend
	ports:
	- protocol: TCP
	  port: 6379

  egress:
  - to:
    - ipBlock:
        cidr: 10.0.0.0/24
    ports:
    - protocol: TCP
      port: 5978
```

#### network policy defaults
```yaml
metadata:
  name: default-deny
```

```yaml
metadata:
  name: allow-all
```