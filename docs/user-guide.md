# Manuale Utente - GitHub Copilot Quiz

## Panoramica

GitHub Copilot Quiz è un'applicazione web che ti permette di testare le tue conoscenze su vari argomenti tecnici attraverso quiz interattivi.

## Come Iniziare

### 1. Quiz Predefiniti

I quiz predefiniti sono collezioni curate di domande su argomenti specifici.

**Passi per utilizzare i quiz predefiniti:**

1. **Seleziona l'argomento**: Usa il menu a tendina "Filtra domande per topic"
2. **Scegli l'origine**: Seleziona se includere tutte le domande o escludere quelle da Copilot & GPT
3. **Imposta il numero di domande**: Scegli tra 5, 10, 15, 20, 25 o 30 domande
4. **Genera il quiz**: Clicca su "Genera Quiz"

**Argomenti disponibili:**
- **GitHub Copilot**: Domande su certificazione, Responsible AI e best practices
- **MongoDB Java Developer Associate**: Sviluppo con MongoDB, aggregation pipelines e Java driver

### 2. Quiz Personalizzati

Puoi creare quiz personalizzati importando i tuoi dati in formato JSON o YAML.

**Passi per creare un quiz personalizzato:**

1. **Vai alla tab "Quiz Personalizzato"**
2. **Inserisci i dati**: Incolla il tuo JSON/YAML nell'area di testo
3. **Configura le opzioni**:
   - Scegli se svuotare il campo dopo la generazione
   - Seleziona il numero di domande
4. **Genera il quiz**: Clicca su "Genera Quiz"
5. **Condividi (opzionale)**: Copia il link generato per condividere il quiz

### 3. Esecuzione del Quiz

Una volta generato il quiz:

1. **Leggi attentamente ogni domanda**
2. **Seleziona la risposta**: Clicca sul radio button della risposta corretta
3. **Naviga tra le domande**: Scorri verso il basso per vedere tutte le domande
4. **Invia le risposte**: Clicca su "Conferma" quando hai completato
5. **Visualizza i risultati**: Vedrai il punteggio e le risposte corrette

## Caratteristiche Speciali

### Domande con Codice

Alcune domande includono esempi di codice formattati per una migliore leggibilità:

```javascript
// Esempio di codice nelle domande
db.collection.find({name: "example"})
```

### Domande a Risposta Multipla

Alcune domande possono avere più risposte corrette. Queste sono chiaramente indicate:
- Nel testo della domanda con indicazione del numero di risposte corrette
- Con un avviso visivo sotto la domanda
- Utilizzano checkbox invece di radio button
- Sistema di feedback granulare che distingue tra risposte corrette, non date e incorrette

### Condivisione Quiz

Quando crei un quiz personalizzato, puoi:
1. **Link automatico**: Il sistema genera automaticamente un link compresso
2. **Copia facile**: Usa il pulsante "Copia" per copiare il link negli appunti
3. **Accesso diretto**: Il quiz sarà accessibile direttamente tramite URL
4. **Ordine preservato**: I quiz condivisi mantengono l'ordine originale delle domande
5. **Compressione**: I link sono ottimizzati per la condivisione (usando compressione Pako)

## Suggerimenti per l'Uso

### Per Studenti
- **Ripeti i quiz**: Non c'è limite al numero di volte che puoi ripetere un quiz
- **Studia gli errori**: Dopo ogni quiz, rivedi le risposte sbagliate
- **Usa filtri**: Concentrati su argomenti specifici usando i filtri

### Per Educatori
- **Crea quiz personalizzati**: Importa le tue domande per argomenti specifici
- **Condividi facilmente**: Usa i link generati per distribuire quiz agli studenti
- **Monitora i progressi**: Incoraggia gli studenti a ripetere i quiz per migliorare

## Risoluzione Problemi

### Il quiz non si carica
- Verifica la connessione internet
- Ricarica la pagina
- Controlla che JavaScript sia abilitato

### Errori nei quiz personalizzati
- Verifica che il formato JSON/YAML sia corretto
- Controlla che tutti i campi obbligatori siano presenti
- Consulta la [Guida per Creatori di Contenuti](content-guide.md) per il formato corretto

### Link di condivisione non funziona
- Verifica che l'URL sia completo
- Controlla che non ci siano caratteri speciali danneggiati
- Rigenera il link se necessario

## Supporto

Per problemi tecnici o suggerimenti:
1. Controlla la documentazione tecnica
2. Apri una issue su GitHub
3. Contatta il team di sviluppo

---

[← Torna alla Home](../README.md) | [Guida Contenuti →](content-guide.md)