#protocol #cloud #network #http 

- encryption and authentication
- syntactically identical to [HTTP](/techstack/network/HTTP.md)
	- additionally: [encryption](/techstack/security/encryption.md) with SSL/TLS
	- [HTTP](/techstack/network/HTTP.md): data transmission in plain text

#### Vulnerabilities
- [encryption](/techstack/security/encryption.md) and implementation
- switched off warnings for mixed operations [HTTP](/techstack/network/HTTP.md)/HTTPS
- [SSL](/SSL) terminations
	- breaking the data connection with [proxy](/proxy) to check for malware
	- further [encryption](/techstack/security/encryption.md) then takes place with certificate of the [proxy](/proxy)
		- user no longer sees original certificate
		- did the proxy really do the validation?