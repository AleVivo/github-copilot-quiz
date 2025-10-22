# GitHub Copilot Quiz

Una applicazione web per testare le tue conoscenze su GitHub Copilot, MongoDB e altre tecnologie di sviluppo attraverso quiz interattivi con feedback avanzato.

## 🚀 Demo Live

[Accedi all'applicazione](https://your-username.github.io/github-copilot-quiz)

## ✨ Caratteristiche

- **Quiz Predefiniti**: Scegli tra diversi argomenti con opzioni di filtro avanzate
  - Filtro per topic (GitHub Copilot, MongoDB, ecc.)
  - Filtro per origine (escludi fonti specifiche come Copilot & GPT)
  - Numero di domande configurabile (5-30 domande)
- **Quiz Personalizzati**: Importa i tuoi quiz in formato JSON/YAML con validazione automatica
- **Condivisione Quiz**: Genera link compressi e condivisibili per distribuzione collaborativa
- **Sistema di Punteggio Avanzato**: Feedback visivo sofisticato con riconoscimento granulare delle risposte
  - Risposte completamente corrette (verde con sfondo positivo)
  - Risposte non date ma corrette (bordo grigio tratteggiato)
  - Risposte incorrette (rosso con testo barrato)
- **Supporto Domande Multiple**: Gestione sofisticata di domande con più risposte corrette
- **Esempi di Codice**: Supporto per blocchi di codice formattati nelle domande
- **Interfaccia Responsive**: Design ottimizzato per desktop e dispositivi mobili

## 📚 Argomenti Disponibili

- **GitHub Copilot**: Domande su certificazione, best practices, prompt engineering, e Responsible AI
- **MongoDB Java Developer Associate**: Domande su sviluppo MongoDB, aggregation pipelines, indexing e Java driver
- Supporto per aggiungere nuovi argomenti tramite file JSON/YAML

## 🎯 Come Usare

### Quiz Predefiniti
1. Seleziona un argomento dal menu "Filtra domande per topic"
2. Scegli l'origine delle domande (tutte o escludi Copilot & GPT)
3. Imposta il numero di domande (5-30)
4. Clicca "Genera Quiz" per iniziare

### Quiz Personalizzati
1. Vai alla tab "Quiz Personalizzato"
2. Incolla il tuo contenuto JSON/YAML nell'area di testo
3. Configura le opzioni (svuotamento automatico, numero domande)
4. Genera il quiz e ottieni un link condivisibile

### Condivisione Quiz
- I quiz personalizzati generano automaticamente link compressi
- Condividi il link per permettere ad altri di eseguire lo stesso quiz
- I quiz condivisi mantengono l'ordine originale delle domande

## 📖 Documentazione

- [📖 Manuale Utente](docs/help.html) - Guida completa all'utilizzo (HTML interattivo)
- [📋 Guida Utente](docs/user-guide.md) - Come utilizzare l'applicazione
- [✍️ Guida per Creatori di Contenuti](docs/content-guide.md) - Come aggiungere nuovi quiz
- [🔧 Documentazione Tecnica](docs/technical.md) - Architettura e sviluppo

## 🛠️ Sviluppo Locale

```bash
# Clona il repository
git clone https://github.com/your-username/github-copilot-quiz.git
cd github-copilot-quiz

# Avvia un server locale (scegli uno)
python -m http.server 8000
# oppure
npx serve .
# oppure
php -S localhost:8000

# Apri http://localhost:8000
```

### Struttura del Progetto
```
├── index.html                 # Entry point dell'applicazione
├── src/
│   ├── js/                   # Moduli JavaScript ES6+
│   │   ├── main.js          # Inizializzazione e gestione eventi
│   │   ├── quiz-generator.js # Generazione e rendering quiz
│   │   ├── quiz-loader.js   # Caricamento dati quiz
│   │   ├── quiz-sharing.js  # Condivisione URL compressi
│   │   └── ui-manager.js    # Gestione interfaccia utente
│   └── styles/
│       └── style.css        # Stili responsive
├── data/                    # Dati quiz in JSON/YAML
│   ├── quizzes-topics.json  # Configurazione argomenti
│   ├── GCP-quizzes-query.json # Quiz GitHub Copilot
│   └── MongoDB-JD-Associate-quizzes-query.yaml # Quiz MongoDB
├── docs/                    # Documentazione completa
└── .kiro/                   # Configurazione Kiro AI
```

## 🧪 Caratteristiche Tecniche

- **Architettura Client-Side**: Nessuna dipendenza backend, completamente statico
- **Moduli ES6+**: Organizzazione del codice con import/export
- **Compressione URL**: Utilizzo di Pako per link condivisibili ottimizzati
- **Parsing Multi-formato**: Supporto nativo per JSON e YAML
- **Validazione Automatica**: Controllo formato dati e campi obbligatori
- **Responsive Design**: CSS Grid e Flexbox per tutti i dispositivi

## 🎨 Tipi di Domande Supportate

- **Domande Semplici**: Una sola risposta corretta
- **Domande Multiple**: Più risposte corrette con feedback parziale
- **Domande con Codice**: Blocchi di codice formattati (MongoDB queries, JavaScript, ecc.)
- **Filtri Avanzati**: Per topic e origine delle domande

## 🤝 Contribuire

1. Fork del progetto
2. Crea un branch per la tua feature (`git checkout -b feature/AmazingFeature`)
3. Implementa le modifiche seguendo le convenzioni del progetto
4. Testa localmente con un server HTTP
5. Commit delle modifiche (`git commit -m 'Add some AmazingFeature'`)
6. Push al branch (`git push origin feature/AmazingFeature`)
7. Apri una Pull Request

### Aggiungere Nuovi Quiz
1. Crea un file JSON/YAML in `data/`
2. Aggiungi l'entry in `data/quizzes-topics.json`
3. Segui il formato documentato nella [Guida per Creatori di Contenuti](docs/content-guide.md)

## 📄 Licenza

Questo progetto è distribuito sotto licenza MIT. Vedi il file `LICENSE` per maggiori dettagli.

## 🙏 Riconoscimenti

- **Contenuti Quiz**: Basati su materiali di formazione Microsoft Learn e MongoDB University
- **Design UX**: Ispirato alle migliori pratiche per applicazioni educative interattive
- **Tecnologie**: Vanilla JavaScript, CSS3, HTML5 con librerie esterne minimali