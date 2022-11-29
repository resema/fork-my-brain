#design #convention #gcp

- each Google Cloud service exposes a [REST](/techstack/network/REST.md) API
	- functions are in the form: `service.collection.verb`
	- parameters are passed either in the [URL](/techstack/network/URL.md) or in the request body in [JSON](/JSON) format
- for example, the Compute Engine API has
	- a service endpoint at: `https://compute.googleapis.com`
	- collections include `instances`, `instanceGroups`, `instanceTemplates`, etc.
	- Verbs in the [HTTP](/techstack/network/HTTP.md) include `insert`, `list`, `get`, etc.

