# Secure Software Lifecycle – Project Repository

La seguente repository raccoglie il materiale completo prodotto durante il progetto finale del corso di **Software Security**, svolto da **Francesco Scognamiglio** e **Felice Micillo**, con un focus sull’applicazione pratica del **Microsoft Security Development Lifecycle (SDL)** ad un’architettura cloud-native su **Kubernetes**.

## 📌 Contenuto della Repository

### 📄 `SS_Documentazione`
Documentazione tecnica dettagliata che descrive l’integrazione del *Secure Software Development Lifecycle* all’interno di un’infrastruttura backend moderna.

🔍 **Abstract del progetto:**
Il lavoro descrive la progettazione di un’architettura a microservizi sicura e osservabile, sviluppata con:
- **Node.js/Express** per il backend
- **Keycloak** per la gestione delle identità
- **PostgreSQL**, **Vault**, **Prometheus**, **Grafana**
- **GitLab CI/CD** per una pipeline DevSecOps automatizzata
- **SAST**, **DAST**, **Trivy**, **Kubescape**, **Tetragon**

La sicurezza è integrata in ogni fase: dalla definizione dei requisiti alla threat modeling (STRIDE, LINDDUN), fino alla crittografia, all’analisi delle dipendenze, alla verifica dei container e ai test dinamici.

📚 **Indice della documentazione**:
- Define Security Requirements
- Define Metrics and Compliance Reporting
- Perform Threat Modeling (DFD, STRIDE, LINDDUN)
- Use Cryptography Standards
- Manage Third-Party Risk
- Use Approved Tools
- Perform SAST/DAST con GitLab

---

### 🎓 `SS_Laboratori`
Serie completa dei laboratori assegnati durante il corso di **Software Security**, ognuno corredato da spiegazioni, soluzioni, codici e osservazioni pratiche.

🧪 **Tematiche trattate nei laboratori**:
- **Lab 1**: Buffer Overflow & Shell Exploits
- **Lab 2**: Web Security (CSRF, XSS, SQLi, CSP)
- **Lab 3**: Fuzzing con AFL
- **Lab 4**: Static Analysis
- **Lab 5**: Cyber Threat Intelligence & MITRE ATT&CK
- **Lab 6**: Basic Malware Analysis
- **Lab 7**: Advanced Malware Techniques (Process Injection, DNS, IDA)
- **Lab 8**: Malware Detection (YARA, Snort, Sigma)

---

### 🎥 `SS_Presentazione`
Presentazione PowerPoint utilizzata per l’esposizione del progetto, che sintetizza:
- Obiettivi del progetto
- Architettura e flusso DevSecOps
- Toolchain adottata
- Minacce affrontate e contromisure
- Pipeline GitLab con controlli automatici
- Risultati e impatti sulla sicurezza

---

## ⚙️ Tecnologie e Strumenti Utilizzati
- **Kubernetes**, **Helm**
- **GitLab CI/CD**
- **ESLint**, **NodeJsScan**
- **OWASP ZAP**, **Trivy**, **Kubescape**
- **Vault**, **Cert-Manager**, **NetworkPolicy**
- **Tetragon**, **Loki**, **Prometheus/Grafana**

## 🔐 DevSecOps in Azione
Questo progetto rappresenta un caso concreto di integrazione dei principi DevSecOps in un contesto real-world, con **monitoraggio continuo**, **risposta agli incidenti**, e **garanzie di compliance** grazie all’automazione e alla visibilità fornita dai tool utilizzati.

---

## 📁 Struttura dei File
| File/Cartella                          | Descrizione                                                                 |
|----------------------------------------|-----------------------------------------------------------------------------|
| `SS_Documentazione_Progetto_*.pdf`     | Documentazione completa del progetto Secure Lifecycle                      |
| `SS_Laboratori_Svolti_*.pdf`           | Laboratori di Software Security svolti (Buffer Overflow, Web, Malware…)   |
| `SS_Presentazione_Progetto_*.pptx`     | Presentazione PowerPoint del progetto DevSecOps su Kubernetes              |

---

## ✍️ Autori
- **Francesco Scognamiglio**
- **Felice Micillo**

---

## 📅 Corso di riferimento
**Software Security** – Università degli Studi di Napoli Federico II  
Anno Accademico: *2024/2025*

---

