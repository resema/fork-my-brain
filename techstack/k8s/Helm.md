#gcp #cloud #k8s #kubernetes #helm

## The Purpose of Helm

Helm is a tool for managing [Kubernetes](/Kubernetes) packages called _[chart](/chart)s_. Helm can do the following:

-   Create new charts from scratch
-   Package charts into chart archive (tgz) files
-   Interact with chart repositories where charts are stored
-   Install and uninstall charts into an existing Kubernetes [cluster](/cluster)
-   Manage the release cycle of charts that have been installed with Helm

For Helm, there are three important concepts:
1.  The _[chart](/chart)_ is a bundle of information necessary to create an instance of a Kubernetes application.
2.  The _[config](/config)_ contains configuration information that can be merged into a packaged chart to create a releasable object.
3.  A _[release](/release)_ is a running instance of a _chart_, combined with a specific _config_.