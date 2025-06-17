# Supply Chain Manifest

Il documento elenca tutte le verifiche e firme applicate agli artefatti critici del progetto, al fine di garantire integrità, provenienza e conformità alla Secure Software Supply Chain (SLSA livello 2).

---

## Immagini Docker firmate con Cosign

### - `express` backend

- **Immagine**: `registry.gitlab.com/felicemicillo13/ssproject/express`
- **Digest**:  
  `sha256:a929d8ba459f5c40bd7e119bf1d4cf78c553671fe5c9e5e63207c8488a22d3e1`
- **Tipo firma**: `cosign container image signature`
- **Verifica eseguita con**:  
  `cosign verify registry.gitlab.com/felicemicillo13/ssproject/express@sha256:a929d8ba459f5c40bd7e119bf1d4cf78c553671fe5c9e5e63207c8488a22d3e1`
- **Output verifica**:

```json
[
  {
    "critical": {
      "identity": {
        "docker-reference": "registry.gitlab.com/felicemicillo13/ssproject/express"
      },
      "image": {
        "docker-manifest-digest": "sha256:a929d8ba459f5c40bd7e119bf1d4cf78c553671fe5c9e5e63207c8488a22d3e1"
      },
      "type": "cosign container image signature"
    },
    "optional": null
  }
]
```

### - `keycloak` authentication

- **Immagine**: `registry.gitlab.com/felicemicillo13/ssproject/keycloak`
- **Digest**:  
  `sha256:b123b65a979d623cb39690b3c805b911686ce65f0b467c179df94b779f569842`
- **Tipo firma**: `cosign container image signature`
- **Verifica eseguita con**:  
  `cosign verify registry.gitlab.com/felicemicillo13/ssproject/keycloak@sha256:b123b65a979d623cb39690b3c805b911686ce65f0b467c179df94b779f569842`
- **Output verifica**:

```json
[
  {
    "critical": {
      "identity": {
        "docker-reference": "registry.gitlab.com/felicemicillo13/ssproject/keycloak"
      },
      "image": {
        "docker-manifest-digest": "sha256:b123b65a979d623cb39690b3c805b911686ce65f0b467c179df94b779f569842"
      },
      "type": "cosign container image signature"
    },
    "optional": null
  }
]
```

---

## File firmati (lockfile NPM)

### - `package-lock.json` – Express Backend

- **Tipo**: File di lock per integrità dipendenze NPM
- **Firma eseguita con**:  
  `cosign sign-blob --key cosign.key package-lock.json`
- **Valore firma**:

```text
MEUCIA0o2ey6oLTXsz/w+WxAm1KEe/PqjFRByhliUf5xv1j7AiEAiK4y6eQVPR7x+nMBO/UhlvILJP4lVcdtPkshLXcoHDc=
```

- **Chiave pubblica utilizzata**:

```pem
-----BEGIN PUBLIC KEY-----
MFkwEwYHKoZIzj0CAQYIKoZIzj0DAQcDQgAEjmaQ//xdym8Veeaog6Ol+hc0GkNU
dmCE4z8MIagKTgh7+PqyNHiWCsIa3zus+3MopxcaRBgLUpVVb4QvvApJLA==
-----END PUBLIC KEY-----
```

- **Verifica eseguita con**:  
  `cosign verify-blob --key cosign.pub --signature package-lock.json.sig package-lock.json`

---

## Conformità e Tracciabilità

- Le immagini sono firmate con **Cosign** e verificate manualmente.
- Il file `package-lock.json` è firmato con Cosign e verificato con la chiave pubblica allegata.
- Tutti i file associati (output `.json`, `.sig`, chiavi, digest) sono conservati nel repository sotto `sigstore/`.

---

## Files associati

| File                    | Descrizione                    |
| ----------------------- | ------------------------------ |
| `package-lock.json.sig` | Firma del lockfile NPM         |
| `cosign.pub`            | Chiave pubblica per verifica   |
| `verify_express.json`   | Output `cosign verify` Express |
| `MANIFEST.md`           | Questo documento               |

---

**Ultimo aggiornamento**: 2025-06-13  
 **A cura di**: | Francesco Scognamiglio | Felice Micillo |
