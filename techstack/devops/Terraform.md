#IaC #cheats

Is an infrastructure automation tool aka [[Infrastructure as Code|IaC]].

- declarative language
- template driven
- uses Cloud providers [[API]]
- resources are infrastructure objects
- configuration file guides the management of resources
- already installed in Google Cloud Console

```hcl
resource "google_compute_network" "default" {
  name = "${var.network_name}"
  auto_create_subnetworks = false
}
```
```hcl
<BLOCK_TYPE> "<BLOCK_LABEL>" "<BLOCK_LABEL>" {
	# block body
	<IDENTIFIER> = <EXPRESSION> #arguments
}
```
