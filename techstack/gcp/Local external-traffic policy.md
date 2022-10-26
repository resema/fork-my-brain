#gcp #cloud #loadbalancer 

This solves the [[double-hop dilemma]]. Just add the local value for the external-traffic policy
```yaml
apiVersion: v1
kind: Service
metadata:
  name: my-service
spec:
  type: LoadBalancer
    externalTrafficPolicy: Local
  selector:
    app: external
  ports:
    - protocol: TCP
      port: 80
      targetPort: 9376
```

#### Question for what's the usecase
- lowest possible latency?
	- set `externalTrafficPolicy: Local`
		- [[kube-proxy]] choses always a [[pod]] on the receiving [[node]]
- best distributed load balancing?
	- allow double hops 