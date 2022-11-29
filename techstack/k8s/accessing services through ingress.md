#gcp #cloud #k8s #kubernetes #ingress #cheat #curl

Since [Ingress](/techstack/k8s/Ingress.md)es use virtual hosting to figure out where to forward the [request](/request), you won't get the desired result by simply sending an [HTTP](/techstack/network/HTTP.md) request to the ingress' [IP address](/IP%20address) and [port](/port).
You need to make sure that the Host header in the HTTP request matches one of the rules in the Ingress object.

To achieve this, this requires resolving the host to the Ingress IP, which is normally done by a [DNS](/DNS) server.

But locally, you can use [curl](/curl) for it. The following call will add the hostname to the DNS cache.
```bash
$ curl --resolve \
  <HOST_NAME>:<PORT>:<INGRESS_IP_ADDRESS> \
  http://my-url.com -v
```

If we want to use the web browser instead, we have to add the following entry to the `/etc/hosts` file:
```
<INGRESS_IP_ADDRESS>    my-url.com
```