#architecture #design #performance #web 

- reduce amount of [HTTP](/techstack/network/HTTP.md) requests
- [CSS](/CSS) sprites
- parallel downloads (e.g. via a [CDN](/techstack/web/CDN.md))
- inline graphics
- JavaScript/[CSS](/CSS) Minimizer
- limit manipulating the [DOM](/DOM)
- content compression on the Web Server

### [Limiting Factors](/limiting%20factors)
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

#### [Data Throughput](/data%20throughput)
- indicates **how many things** you can do **in a given unit of time**

#### [Latency](/latency)
- is the **minimum time** required **to get a response** from the system, even if it does not have to do **any work at all**
	- [latency](/latency) + [processing time](/processing%20time) = [reposnse time](/reposnse%20time)
	- causes for latency
		- delay during execution runtime
		- [serialization](/serialization)
		- data logs
		- routing and switching
		- queuing and buffing