#gcp #k8s #cloud 

- The ingress controller is the software component that brings the [[Ingress]] object to life.
- The controller connects to the Kubernetes [[API]] server and monitors the [[Ingress]], [[service|Service]], and [[Endpoints]] or [[EndpointSlice]] objects.
- configures the [[reverse proxy]]
- watches the connected objects (see above)