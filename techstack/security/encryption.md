#TLS/SSL #security #cloud #network 

- encryption takes place below the level of the [[HTTP]] protocol
- in the [[OSI]] model located in layer 5 (session layer)
- known implementations: [[OpenSSL]] and [[GnuTLS]]

1. protected indentification and authentication of the communication partners with [[SSL]] handshake protocol
2. exchange of shared symmetric session keys using asymmetric encryption of [[Diffie-Hellman]] key exchange
3. encryption of user data with exchanged key