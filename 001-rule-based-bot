### Rule-Based FAQ Bot

#### Contesto business
Una PMI vuole offrire risposte immediate alle domande più comuni nel sito (orari, pagamenti, spedizioni) senza usare ML. Vuole un primo prototipo rule-based estendibile.

#### Obiettivi
- Implementare un chatbot **a regole** che riconosce almeno 5 intent.
- Gestire input non riconosciuti con fallback chiaro.
- Progettare il codice perché sia **estendibile** (nuove regole/intent) e **testabile**.

#### Requisiti funzionali (minimi)
1. Funzione `get_response(user_input: string) -> string`.
2. Normalizzazione dell'input: lowercase, trim, rimozione punteggiatura comune.
3. Matching regole **exact** e **contains** (es. contiene "orari" → intent ORARI).
4. Intent supportati (minimo): ORARI, ASSISTENZA, SEDE, SPEDIZIONI, PAGAMENTI.
5. Fallback: "Mi dispiace, non ho capito la domanda." per intent non riconosciuti.
6. Comando uscita conversazione: "esci" / "quit".
7. Log conversazioni in memoria (array/lista di tuple `[(input, output), ...]`).

#### Requisiti non funzionali
- Codice **commentato** e formattato, nomi chiari.
- Separazione delle **regole** dai **flussi** (es. dizionario `intent -> risposta`).
- Estendibilità: aggiungere un nuovo intent non deve rompere i precedenti (open/closed principle semplificato).

#### Set di regole base (intent → risposta)
- ORARI → "Siamo aperti dal lunedì al venerdì, dalle 9 alle 18."
- ASSISTENZA → "Sì, puoi contattarci via email o telefono."
- SEDE → "La nostra sede è a Milano, in Via Roma 10."
- SPEDIZIONI → "Sì, per ordini superiori a 50€ offriamo spedizione gratuita."
- PAGAMENTI → "Accettiamo le principali carte di credito e PayPal."
- FALLBACK → "Mi dispiace, non ho capito la domanda."

#### Dataset minimo (CSV suggerito)
"domanda","risposta"
"Quali sono gli orari di apertura?","Siamo aperti dal lunedì al venerdì, dalle 9 alle 18."
"Offrite assistenza clienti?","Sì, puoi contattarci via email o telefono."
"Dove vi trovate?","La nostra sede è a Milano, in Via Roma 10."
"Avete spedizioni gratuite?","Sì, per ordini superiori a 50€ offriamo spedizione gratuita."
"Posso pagare con carta di credito?","Accettiamo le principali carte di credito e PayPal."

#### Flusso d'uso (esempi)
- U: "Quali sono gli orari di apertura?" → B: "Siamo aperti dal lunedì al venerdì, dalle 9 alle 18."
- U: "Fate consegne a domicilio?" → B: "Mi dispiace, non ho capito la domanda."

#### Passi operativi
1) Definisci dizionario `intent_keywords` (es. ORARI: ["orario", "orari", "apertura"], ...).  
2) Parsing input: normalizza e cerca keyword; seleziona il **primo intent** con match.  
3) Mappa intent → risposta con `responses[intent]`.  
4) Implementa fallback.  
5) Aggiungi log conversazioni (append di tuple).  
6) Scrivi 5 **test**: uno per ciascun intent + 1 per fallback.

#### Deliverable
- Programma funzionante + README con istruzioni d'uso e come aggiungere nuove regole.

#### Criteri di accettazione (UAT)
- Tutti i 5 intent rispondono correttamente (test verdi).  
- Fallback sempre presente su input non riconosciuti.  
- Codice leggibile, regole separabili/estendibili.  
- Log popolato correttamente (≥5 turni di conversazione di esempio).

#### Estensioni (facoltative)
- Sinonimi (es. "pagare" ~ "pagamenti").  
- Intent HELP che elenca le domande supportate.  
- Persistenza del log su file.
