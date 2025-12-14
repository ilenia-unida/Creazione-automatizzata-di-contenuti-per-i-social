# ✍️ Flusso Automatico: Generazione Contenuti da Google Sheets a Notion con AI

Un workflow di **Content Automation (Automazione dei Contenuti)** professionale, costruito con **n8n**, che trasforma una riga di dati su Google Sheets in un post pronto per la revisione su Notion. Questo flusso utilizza l'Intelligenza Artificiale (Gemini) per arricchire l'idea iniziale con un contenuto completo.

## ✨ Caratteristiche & Funzionalità

* **Trigger Schedulato:** 🕒 Si avvia automaticamente a intervalli regolari per verificare la presenza di nuove idee.
* **Source of Truth (Google Sheets):** 📑 Legge una lista di idee per post (es. Colonna "Argomento", "Idea per Post") da un foglio di Google designato.
* **Controllo Anti-Duplicazione:** 🚦 Utilizza un nodo **If** per verificare se l'idea è già stata pubblicata o elaborata, evitando di sprecare crediti AI e di creare contenuti duplicati (controllo basato sulla colonna "Pubblicato").
* **AI Content Generation:** 🧠 Il nodo **AI Agent** (Gemini) prende l'argomento e l'idea e genera automaticamente un **Titolo** e il **Contenuto** del post in formato JSON strutturato.
* **Archiviazione finale (Notion):** 🚀 Crea una nuova pagina nel database Notion specificato, impostando i campi (Titolo, Contenuto, Stato) con l'output generato dall'AI.

## 🚀 Struttura del Flusso

Il flusso è composto dai seguenti nodi chiave:

1.  **Schedule trigger:** Avvio programmato.
2.  **Google Sheets:** Legge le righe del foglio di calcolo.
3.  **SplitInBatches:** Elabora le righe una alla volta, ottimizzando la gestione dei dati.
4.  **IF - Non pubblicato:** ⚖️ Logica condizionale per verificare lo stato di pubblicazione.
5.  **AI Agent & Google Gemini:** 💡 Genera il contenuto testuale.
6.  **Format for Notion (Code):** 🧹 Prepara il JSON risultante dall'AI nel formato corretto per il database Notion.
7.  **Notion - Crea pagina:** 💾 Crea il post nel database di destinazione.

## 📺 Video di Spiegazione

Per una spiegazione dettagliata del funzionamento, della logica e della configurazione dei nodi (in particolare la logica condizionale e l'integrazione Notion), guarda il video qui sotto:

[Spiegazione dettagliata del Flusso Content Generation AI su YouTube](https://youtu.be/mC1Fv0yVAkU)

## 🛠️ Requisiti

Per utilizzare questo flusso, è necessario configurare le credenziali per i seguenti servizi:

* **Google Sheets Account**
* **Google Gemini (PaLM) API Account**
* **Notion Account**

---

