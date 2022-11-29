#encryption #security #TLS #TLS/SSL 

An [encryption](/techstack/security/encryption.md) approach:
1. non-secret parameters: prime number `g`
   - primitive root `p` modulo `g`.
2. generation of secret random numbers `(a,b)`
   - will not be transferred!
3. each calculates: `A=g^a mod p` or `B=g^b mod p`
4. transmission of A and B via the unsecure medium
5. everyone now calculates `K=B^a mod p` or `K=A^b mod p`
	1. result equal for both
	2. key for further communication 