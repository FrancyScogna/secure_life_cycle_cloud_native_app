# Standard Crittografici Utilizzati

| Componente       | Algoritmo     | Tipo Chiave / Size        | Libreria / Tool              | Note di Sicurezza                                                            |
| ---------------- | ------------- | ------------------------- | ---------------------------- | ---------------------------------------------------------------------------- |
| Keycloak         | RS256, AES    | RSA 2048-bit, AES 256-bit | Keycloak (built-in)          | Token firmati con RS256, gestione chiavi sicura e configurabile via console  |
| TLS (HTTPS)      | ECDSA SHA-256 | X25519 (ECC)              | Let's Encrypt + Cert Manager | TLS 1.3, forward secrecy, certificati auto-rinnovati, gestione automatizzata |
| JWT Custom Token | HS256         | HMAC, secret 4096-bit     | jsonwebtoken + Vault         | Secret generato random, accesso via Vault CSI, non hardcoded, token con TTL  |
