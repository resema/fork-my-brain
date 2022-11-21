#security #authentication 

- server prompts for username and password
- clients send [[authentication & authorization|authentication]] with Authorization header
  ```
  Authorization: Basic d2lraTpwZWRpYQ==
  ```
- username and password not [[encryption|encrypted]]
- [[encryption]] with [[SSL]]/[[TLS]] for [[HTTPS]]
	- encryption before password transmission