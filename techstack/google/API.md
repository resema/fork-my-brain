#design #convention

- each Google Cloud service exposes a [[REST]] API
	- functions are in the form: `service.collection.verb`
	- parameters are passed either in the [[URL]] or in the request body in [[JSON]] format
- for example, the Compute Engine API has
	- a service endpoint at: `https://compute.googleapis.com`
	- collections include `instances`, `instanceGroups`, `instanceTemplates`, etc.
	- Verbs in the [[HTTP]] include `insert`, `list`, `get`, etc.

