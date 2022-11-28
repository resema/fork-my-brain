#architecture #design #performance #web 

- reduce amount of [[HTTP]] requests
- [[CSS]] sprites
- parallel downloads (e.g. via a [[CDN]])
- inline graphics
- JavaScript/[[CSS]] Minimizer
- limit manipulating the [[DOM]]
- content compression on the Web Server

### [[limiting factors|Limiting Factors]]
- CPU time
	- scalable via hardware
- memory consumption
	- scalable via hardware
- I/O and network
	- difficult to scale
	- changes in the architecture necessary
- access to shared resources
	- not scalable or difficult to scale
	- chagnes in the architecture necessary

#### [[data throughput|Data Throughput]]
- indicates **how many things** you can do **in a given unit of time**

#### [[latency|Latency]]
- is the **minimum time** required **to get a response** from the system, even if it does not have to do **any work at all**
	- [[latency]] + [[processing time]] = [[reposnse time]]
	- causes for latency
		- delay during execution runtime
		- [[serialization]]
		- data logs
		- routing and switching
		- queuing and buffing