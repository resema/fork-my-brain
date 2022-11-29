#architecture #patterns #web 

- web applications are based on an N-layer architecture
	- 2-tier
		- tier 1: presentations layer
		- tier 2: application and data storage layer
		- Example: [Firestore](/techstack/google/Firestore.md)
	- 3-tier
		- tier 1: presentation layer
		- tier 2: application and processing layer
		- tier 3: data management layer
	- 4-tier
		- tier 1: presentation layer
		- tier 2: web server
			- f.ex. a [LoadBalancer](/techstack/k8s/LoadBalancer.md)
		- tier 3: application server
		- tier 4: data management