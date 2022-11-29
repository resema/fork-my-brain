#TLS/SSL #security #cloud #network 

- encryption takes place below the level of the [HTTP](/techstack/network/HTTP.md) protocol
- in the [OSI](/OSI) model located in layer 5 (session layer)
- known implementations: [OpenSSL](/OpenSSL) and [GnuTLS](/GnuTLS)

1. protected indentification and authentication of the communication partners with [SSL](/SSL) handshake protocol
2. exchange of shared symmetric session keys using asymmetric encryption of [Diffie-Hellman](/techstack/security/Diffie-Hellman.md) key exchange
3. encryption of user data with exchanged key