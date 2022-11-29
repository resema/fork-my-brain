#architecture #security #pattern #web #firewall

Designed to protect web applications from attacks over [HTTP](/techstack/network/HTTP.md) ([SQL injection](/architecture/patterns/security/SQL%20injection.md), [HTML injection](/architecture/patterns/security/HTML%20injection.md), [cross-site scripting](/architecture/patterns/security/cross-site%20scripting.md), others...). Compared to classic [firewall](/firewall)s and [intrusion detection systems](/intrusion%20detection%20systems) (IDS), [WAF](/architecture/patterns/security/web%20application%20firewall.md) examines communication at the application level. Species are [reverse proxy](/techstack/k8s/reverse%20proxy.md), [appliance](/appliance), directly integrated in the web server, others/

- examines all incoming requests and responses of the web server
- access is prevented in the case of suspicious content
- application security scanner (ASS)
	- classification of dangerous or prohibited actions
	- profiles for permissible actions
	- control of the web pages of the web application and try out of contained form fields by ASS
- permitted and non-permitted entries are recorded in a log file

##### Pros & Cons
![](/_diag/waf.png)

