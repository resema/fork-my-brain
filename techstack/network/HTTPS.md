#protocol #cloud #network #http 

- encryption and authentication
- syntactically identical to [[HTTP]]
	- additionally: [[encryption]] with SSL/TLS
	- [[HTTP]]: data transmission in plain text

#### Vulnerabilities
- [[encryption]] and implementation
- switched off warnings for mixed operations [[HTTP]]/HTTPS
- [[SSL]] terminations
	- breaking the data connection with [[proxy]] to check for malware
	- further [[encryption]] then takes place with certificate of the [[proxy]]
		- user no longer sees original certificate
		- did the proxy really do the validation?