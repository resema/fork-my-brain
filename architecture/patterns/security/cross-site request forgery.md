#architecture #pattern #security #xsr

![overview](/_diag/xsr-forgery.png)

1. browser creates [authenticated](/techstack/security/authentication%20&%20authorization.md) session with secured page
2. request from user via browser to secure page
3. attacker triggers manipulated [HTTP](/techstack/network/HTTP.md) request at the user's side and uses their [authentication](/techstack/security/authentication%20&%20authorization.md) to perform a particular action

#### Countermeasures
- server side
	- transaction provided with shared secret information (token)
- client side
	- choose your framework wisely :)
	- keep computers free of malware
	- avoid alloweing permantent logins through [Cookies](/techstack/network/Cookies.md)
	- disable JavaScript
- not sufficient by themselves
	- accept [HTTP](/techstack/network/HTTP.md) [POST](/POST) request only
	- check [HTTP](/techstack/network/HTTP.md) referrers when/before handling requests

- always implement security-relevant checks in the server
	- browser side checks could be skipped/disabled by the user and manipulated at will