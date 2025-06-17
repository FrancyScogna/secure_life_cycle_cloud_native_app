# Threat Modeling – LINDDUN

La seguente tabella elenca i rischi relativi alla privacy secondo il modello **LINDDUN**, includendo impatto, probabilità e mitigazioni applicate.

| Componente  | Categoria       | Descrizione                                                                           | Impatto | Likelihood | Risk Score | Mitigazione Applicata                                                         |
| ----------- | --------------- | ------------------------------------------------------------------------------------- | ------- | ---------- | ---------- | ----------------------------------------------------------------------------- |
| Ingress     | Detectability   | Un attaccante esterno può dedurre pattern di utilizzo (es. orari di login)            | 3       | 2          | 6          | Rate limiting, logging minimizzato                                            |
| Express API | Linkability     | Cross-request correlation tramite cookie o token persistenti                          | 3       | 3          | 9          | Uso di cookie “SameSite”, token brevi e rotazione periodica                   |
| Express API | Unawareness     | Gli utenti non sanno quali dati vengono raccolti durante le chiamate API              | 3       | 3          | 9          | Privacy policy esplicita, banner di consenso                                  |
| Express API | Non-compliance  | Raccolta di dati non strettamente necessari per il servizio                           | 4       | 2          | 8          | Data minimization in input validation, revisione periodica dei campi raccolti |
| Keycloak    | Identifiability | Possibilità di riconoscere univocamente un utente tramite metadata (es. indirizzo IP) | 5       | 3          | 15         | Anonimizzazione IP nei log, TTL corto per UUID, storage cifrato               |
| Keycloak    | Data Disclosure | Esposizione accidentale di credenziali o token                                        | 5       | 2          | 10         | Hashing + salting, access control                                             |
| Keycloak DB | Non-repudiation | Impossibilità di verificare la paternità di operazioni sul DB                         | 4       | 2          | 8          | Log firmati e timestamped, audit trail immutabile                             |
| app-db      | Data Disclosure | Accesso diretto da pod non autorizzati che potrebbe esporre dati utente               | 4       | 2          | 8          | NetworkPolicy Kubernetes, least privilege sui ServiceAccount                  |
| app-db      | Linkability     | Possibilità di correlare record tra tabelle e ricostruire profili utente              | 3       | 2          | 6          | Pseudonimizzazione campi sensibili, separazione fisica o schema dei dati      |
| Tutti i Log | Unawareness     | Gli utenti non sanno che le loro azioni vengono loggate e per quanto tempo conservate | 3       | 4          | 12         | Log retention limitata, comunicazioni trasparenti nella privacy policy        |
| Tutti i DB  | Non-compliance  | Conservazione dati oltre i termini previsti dalla normativa (es. GDPR)                | 4       | 2          | 8          | Implementazione di processi automatici di data purging                        |
