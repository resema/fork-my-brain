#security #authentication 

- server prompts for username and password
- clients send [authentication](/techstack/security/authentication%20&%20authorization.md) with Authorization header
  ```
  Authorization: Basic d2lraTpwZWRpYQ==
  ```
- username and password not [encrypted](/techstack/security/encryption.md)
- [encryption](/techstack/security/encryption.md) with [SSL](/SSL)/[TLS](/techstack/security/TLS.md) for [HTTPS](/techstack/network/HTTPS.md)
	- encryption before password transmission