# SECURITY_METRICS.md

## Tracciamento delle Vulnerabilità

Il file documenta le vulnerabilità di sicurezza rilevate all'interno del progetto, assegnando un punteggio di **gravità (Impact)**, **probabilità (Likelihood)**, e **rischio complessivo**, accompagnato dallo **stato attuale** e da eventuali **contromisure**.

> Le valutazioni sono effettuate in base alla [OWASP Risk Rating Methodology](https://owasp.org/www-community/OWASP_Risk_Rating_Methodology), tenendo conto sia dell'impatto tecnico che della probabilità di sfruttamento.

---

### Tabella di Valutazione

| **Vulnerabilità**                 | **Gravità (1–5)** | **Probabilità (1–5)** | **Rischio (1–25)** | **Stato** |
| --------------------------------- | ----------------- | --------------------- | ------------------ | --------- |
| Content-Security-Policy assente   | 4                 | 5                     | 20                 | Risolta   |
| X-Frame-Options mancante          | 3                 | 4                     | 12                 | Risolta   |
| Strict-Transport-Security assente | 3                 | 2                     | 6                  | Risolta   |
| X-Content-Type-Options mancante   | 3                 | 3                     | 9                  | Risolta   |
| X-XSS-Protection non configurato  | 2                 | 2                     | 4                  | Risolta   |
| X-Download-Options mancante       | 2                 | 1                     | 2                  | Risolta   |
| Public-Key-Pins (HPKP) mancante   | 1                 | 1                     | 1                  | Ignorata  |

---

### Analisi Dettagliata (Metodo OWASP)

#### Content-Security-Policy assente

- **Likelihood (7.75/9)** → **5/5**
  - Skill: 6, Motive: 9, Opportunity: 8, Size: 8
- **Impact (6.25/9)** → **4/5**
  - Conf: 9, Integ: 6, Avail: 3, Acc: 7
- **Rischio: 20 (ALTO)**

#### X-Frame-Options mancante

- **Likelihood (6.5/9)** → **4/5**
  - Skill: 4, Motive: 7, Opportunity: 7, Size: 8
- **Impact (5.75/9)** → **3/5**
  - Conf: 4, Integ: 7, Avail: 3, Acc: 9
- **Rischio: 12 (MEDIO-ALTO)**

#### Strict-Transport-Security assente

- **Likelihood (4.75/9)** → **2/5**
  - Skill: 6, Motive: 4, Opportunity: 3, Size: 6
- **Impact (5.75/9)** → **3/5**
  - Conf: 8, Integ: 6, Avail: 4, Acc: 5
- **Rischio: 6 (MEDIO)**

#### X-Content-Type-Options mancante

- **Likelihood (5.75/9)** → **3/5**
  - Skill: 4, Motive: 6, Opportunity: 7, Size: 6
- **Impact (5.75/9)** → **3/5**
  - Conf: 6, Integ: 5, Avail: 5, Acc: 7
- **Rischio: 9 (MEDIO)**

#### X-XSS-Protection non configurato

- **Likelihood (4.5/9)** → **2/5**
  - Skill: 3, Motive: 6, Opportunity: 4, Size: 5
- **Impact (4.5/9)** → **2/5**
  - Conf: 6, Integ: 4, Avail: 2, Acc: 6
- **Rischio: 4 (BASSO)**

#### X-Download-Options mancante

- **Likelihood (3/9)** → **1/5**
  - Skill: 3, Motive: 4, Opportunity: 3, Size: 2
- **Impact (4.25/9)** → **2/5**
  - Conf: 4, Integ: 4, Avail: 5, Acc: 4
- **Rischio: 2 (TRASCURABILE)**

#### Public-Key-Pins (HPKP) mancante

- **Likelihood (1/9)** → **1/5**
  - Obsoleta nei browser moderni
- **Impact (1/9)** → **1/5**
  - Nessun impatto reale nel 2025
- **Rischio: 1 (IRRILEVANTE)**

---

### Note

- La colonna **Rischio** è calcolata come: `Gravità × Probabilità`
- La valutazione è ispirata al framework **OWASP Risk Rating**, usando una mappatura da scala 1–9 a 1–5
- Le vulnerabilità considerate "Ignorate" sono obsolete e non più rilevanti nel contesto tecnologico attuale

---

### Aggiornamenti futuri

Per ogni nuova release:

- Eseguire una scansione automatica
- Aggiornare i punteggi e gli stati
- Documentare le mitigazioni applicate
- Versionare questo file con commit chiari

---

_Ultimo aggiornamento: 05/06/2025_
