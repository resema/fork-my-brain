#architecture #pattern #security #xsr

![overview](xsr-forgery.png)

1. browser creates [[authentication & authorization|authenticated]] session with secured page
2. request from user via browser to secure page
3. attacker triggers manipulated [[HTTP]] request at the user's side and uses their [[authentication & authorization|authentication]] to perform a particular action

#### Countermeasures
- server side
	- transaction provided with shared secret information (token)
- client side
	- choose your framework wisely :)
	- keep computers free of malware
	- avoid alloweing permantent logins through [[Cookies]]
	- disable JavaScript
- not sufficient by themselves
	- accept [[HTTP]] [[POST]] request only
	- check [[HTTP]] referrers when/before handling requests

- always implement security-relevant checks in the server
	- browser side checks could be skipped/disabled by the user and manipulated at will