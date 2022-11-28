#architecture #pattern #web 

#### General
- server returns the entire JavaScript applications on first call
	- client controls (UI/Form) changes
	- no reloading of the entire page necessary
- communication with server only for read/write data
	- [[Ajax]]
	- data format: JSON or XML
- server acts only as data supplier
- processing is moved to the browser

#### Details
- JavaScript functionality uses the [[DOM]] to generate dynamic [[HTML]] elements
  ==> Strong [[coupling]] of program logic to design
- painpoints: 
	- page bounce/leave
	- HTML rendering
	- synchronization with the server
	- memory management
	- ensuring data consistency
 ==> clean architecture
 ==> usefully [[encapsulation|encapsulated]] data structures
 ==> decoupling design from logic
