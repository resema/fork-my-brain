#architecture #security #pattern #web #firewall

Designed to protect web applications from attacks over [[HTTP]] ([[SQL injection]], [[HTML injection]], [[cross-site scripting]], others...). Compared to classic [[firewall]]s and [[intrusion detection systems]] (IDS), [[web application firewall|WAF]] examines communication at the application level. Species are [[reverse proxy]], [[appliance]], directly integrated in the web server, others/

- examines all incoming requests and responses of the web server
- access is prevented in the case of suspicious content
- application security scanner (ASS)
	- classification of dangerous or prohibited actions
	- profiles for permissible actions
	- control of the web pages of the web application and try out of contained form fields by ASS
- permitted and non-permitted entries are recorded in a log file

##### Pros & Cons
![](waf.png)

