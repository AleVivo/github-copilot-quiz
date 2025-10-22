# Guida per Creatori di Contenuti

## Panoramica

Questa guida spiega come creare e aggiungere nuovi quiz all'applicazione GitHub Copilot Quiz.

## Formato dei Dati

### Struttura Base JSON

```json
[
  {
    "domanda": "Testo della domanda",
    "risposte": {
      "a": "Prima opzione",
      "b": "Seconda opzione", 
      "c": "Terza opzione",
      "d": "Quarta opzione"
    },
    "rispostaCorretta": "a",
    "origin": "fonte-della-domanda"
  }
]
```

### Struttura Base YAML

```yaml
- domanda: "Testo della domanda"
  risposte:
    a: "Prima opzione"
    b: "Seconda opzione"
    c: "Terza opzione"
    d: "Quarta opzione"
  rispostaCorretta: "a"
  origin: "fonte-della-domanda"
```

## Campi Obbligatori

### `domanda` (string)
Il testo della domanda. Deve essere chiaro e specifico.

**Esempio:**
```yaml
domanda: "Quale comando MongoDB restituisce tutti i documenti di una collezione?"
```

### `risposte` (object)
Oggetto contenente le quattro opzioni di risposta (a, b, c, d).

**Esempio:**
```yaml
risposte:
  a: "db.collection.find()"
  b: "db.collection.findAll()"
  c: "db.collection.getAll()"
  d: "db.collection.select()"
```

### `rispostaCorretta` (string | array)
La risposta corretta. Può essere:
- **Singola risposta**: `"a"`
- **Risposte multiple**: `["a", "c"]`

### `origin` (string)
La fonte della domanda per riferimento e attribuzione.

**Esempi:**
- `"https://learn.mongodb.com/"` - URL completo MongoDB Learn
- `"https://learn.microsoft.com/en-us/training/paths/copilot/"` - URL completo Microsoft Learn
- `"copilot"` - Domande generate o relative a GitHub Copilot
- `"GPT"` - Domande generate da GPT per test aggiuntivi

**Nota**: Il filtro "Escludi copilot & GPT" rimuove domande con origin "copilot" e "GPT".

## Campi Opzionali

### `codeBlock` (string)
Per domande che includono esempi di codice. Usa la sintassi YAML literal block (`|`).

**Esempio:**
```yaml
domanda: "Dato il seguente codice, qual è l'output?"
codeBlock: |
    db.users.find({age: {$gt: 18}})
    .sort({name: 1})
    .limit(5)
risposte:
  a: "Primi 5 utenti ordinati per nome"
  b: "Utenti maggiorenni ordinati per nome, limitati a 5"
  c: "Tutti gli utenti maggiorenni"
  d: "Errore di sintassi"
rispostaCorretta: "b"
```

## Tipi di Domande

### 1. Domande Semplici
Domande con una sola risposta corretta.

```yaml
- domanda: "Cos'è GitHub Copilot?"
  risposte:
    a: "Un sistema di controllo versione"
    b: "Un assistente AI per la programmazione"
    c: "Un servizio di hosting"
    d: "Un editor di codice"
  rispostaCorretta: "b"
  origin: "copilot"
```

### 2. Domande a Risposta Multipla
Domande con più risposte corrette.

```yaml
- domanda: "Quali sono vantaggi del connection pooling in MongoDB?"
  risposte:
    a: "Riduce la latenza"
    b: "Limita le connessioni al server"
    c: "Elimina l'autenticazione"
    d: "Rimuove la necessità di aprire/chiudere connessioni"
  rispostaCorretta: ["a", "b"]
  origin: "mongodbUniversity"
```

### 3. Domande con Codice
Domande che includono esempi di codice o query.

```yaml
- domanda: "Dato il seguente documento, quale query lo trova?"
  codeBlock: |
      {
        "_id": 1,
        "name": "Mario Rossi",
        "age": 25,
        "city": "Roma"
      }
  risposte:
    a: 'db.users.find({name: "Mario Rossi"})'
    b: 'db.users.findOne({age: 25})'
    c: 'db.users.find({city: "Roma"})'
    d: "Tutte le precedenti"
  rispostaCorretta: "d"
  origin: "custom"
```

## Aggiungere Nuovi Quiz

### 1. Aggiungere a Quiz Esistenti

Per aggiungere domande a collezioni esistenti:

1. **Apri il file appropriato**:
   - `data/GCP-quizzes-query.json` per GitHub Copilot (formato JSON)
   - `data/MongoDB-JD-Associate-quizzes-query.yaml` per MongoDB (formato YAML)

2. **Aggiungi le nuove domande** seguendo il formato esistente
   - Mantieni la struttura dei campi obbligatori
   - Usa origin appropriato per il filtro
   - Formatta il codice con YAML literal syntax se necessario

3. **Testa il formato** usando un validatore JSON/YAML
4. **Verifica il filtro origine** se usi origin "copilot" o "GPT"

### 2. Creare Nuove Collezioni

Per creare una nuova collezione di quiz:

1. **Crea un nuovo file** in `data/` (es. `data/react-quiz.json`)

2. **Aggiungi la collezione** a `data/quizzes-topics.json`:
```json
{
  "title": "React Development",
  "description": "Quiz su React e sviluppo frontend",
  "resource": "data/react-quiz.json"
}
```

3. **Popola il file** con le domande nel formato corretto

## Best Practices

### Scrittura delle Domande
- **Sii specifico**: Evita domande ambigue
- **Usa esempi concreti**: Includi codice quando appropriato
- **Mantieni coerenza**: Usa terminologia consistente
- **Testa le domande**: Verifica che abbiano senso per il target

### Formattazione del Codice
- **Indentazione corretta**: Mantieni la formattazione originale
- **Sintassi valida**: Assicurati che il codice sia corretto
- **Commenti utili**: Aggiungi commenti quando necessario
- **Lunghezza appropriata**: Evita blocchi di codice troppo lunghi

### Gestione delle Risposte
- **Opzioni plausibili**: Tutte le opzioni dovrebbero sembrare ragionevoli
- **Una sola risposta ovvia**: Evita ambiguità nella risposta corretta
- **Varietà nelle posizioni**: Non mettere sempre la risposta corretta in "a"
- **Lunghezza simile**: Mantieni le opzioni di lunghezza comparabile

## Validazione

### Controlli Automatici
L'applicazione verifica automaticamente:
- Presenza di tutti i campi obbligatori
- Formato corretto delle risposte multiple
- Validità della sintassi JSON/YAML

### Controlli Manuali
Prima di pubblicare, verifica:
- [ ] Ortografia e grammatica corrette
- [ ] Codice funzionante e formattato
- [ ] Risposte corrette verificate
- [ ] Attribuzione delle fonti presente

## Esempi Completi

### Quiz MongoDB Completo
```yaml
- domanda: "Quale operatore MongoDB trova documenti con un campo che contiene un valore specifico in un array?"
  risposte:
    a: "$in"
    b: "$elemMatch" 
    c: "$all"
    d: "$contains"
  rispostaCorretta: "a"
  origin: "mongodbUniversity"

- domanda: "Dato il seguente aggregation pipeline, cosa fa?"
  codeBlock: |
      db.orders.aggregate([
        { $match: { status: "completed" } },
        { $group: { _id: "$customerId", total: { $sum: "$amount" } } },
        { $sort: { total: -1 } }
      ])
  risposte:
    a: "Trova tutti gli ordini completati"
    b: "Calcola il totale per cliente e ordina per importo decrescente"
    c: "Conta gli ordini per stato"
    d: "Trova il cliente con più ordini"
  rispostaCorretta: "b"
  origin: "mongodbUniversity"
```

---

[← Manuale Utente](user-guide.md) | [Documentazione Tecnica →](technical.md)