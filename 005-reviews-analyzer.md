### Analizzatore di recensioni (approccio base)

#### Scenario
Un ristorante vuole etichettare recensioni online come Positive/Negative/Neutral via keyword.

#### Dataset di esempio
- "Il cibo era ottimo, tornerò sicuramente" → Positive
- "Servizio pessimo e lento" → Negative
- "Locale carino ma niente di speciale" → Neutral

#### Regole
- POS = {ottimo, buono, eccellente}
- NEG = {pessimo, lento, scarso}
- Conta occorrenze (case-insensitive):
  - POS > NEG → Positive
  - NEG > POS → Negative
  - Altrimenti → Neutral

#### Comportamento atteso
- "Il cibo era ottimo e buono" → POSITIVE (2 keyword positive, 0 negative)
- "Servizio pessimo e lento" → NEGATIVE (0 positive, 2 negative)
- "Locale carino" → NEUTRAL (0 match nelle liste fornite)
- "Cibo ottimo ma servizio pessimo" → NEUTRAL (1 positive, 1 negative = pareggio)

#### Preprocessing da gestire
- Case-insensitive: "OTTIMO" = "ottimo" = "Ottimo"
- Punteggiatura base: "ottimo!" → "ottimo", "buono," → "buono"
- Spazi extra: rimuovi spazi all'inizio/fine delle parole
- Split parole: dividi la frase in singole parole per il confronto

#### Come testare il tuo programma
1. Test base: verifica che le 3 frasi del dataset di esempio diano il risultato corretto
2. Test comportamento: prova con i 4 esempi di "comportamento atteso"  
3. Dataset esteso: crea un file nuove_recensioni.txt con almeno 10 frasi aggiuntive che inventi tu
4. Flessibilità input: il programma dovrebbe poter analizzare sia singole frasi che leggere da file

#### Formato file suggerito (nuove_recensioni.txt)
Esperienza fantastica, ci tornerei
Staff scortese e cibo freddo
Prezzo giusto per la qualità
Ottimo aperitivo ma dolci scarsi
Locale accogliente, servizio veloce

#### Collegamento ai concetti NLP
Nel README spiega:
- Tokenizzazione: come hai diviso le frasi in parole
- Feature extraction: come le parole diventano "dati" (conteggi)
- Sentiment scoring: come i conteggi diventano classificazione
- Collegamento ai chatbot: come ChatGPT fa qualcosa di simile ma su scala enorme

#### Deliverables
- Script funzionante per classificazione sentiment (singole frasi + file)
- File nuove_recensioni.txt con 10+ esempi e loro classificazione attesa
- README che spiega features vs labels e include il collegamento NLP

#### Criteri di accettazione
- Classifica correttamente tutto il dataset base (7 frasi totali)
- Gestisce correttamente i casi di pareggio come Neutral
- Preprocessing gestisce almeno maiuscole/minuscole e punteggiatura base
- README spiega chiaramente:
  - Cosa sono le "features" (parole chiave) e "labels" (Positive/Negative/Neutral)
  - Come questo si collega al Natural Language Processing
  - Limitazioni dell'approccio keyword-based
- Dataset esteso contiene almeno 10 frasi aggiuntive con risultato atteso

#### Estensioni opzionali
- Peso parole: alcune parole valgono di più (es: "eccellente" vale 2, "buono" vale 1)
- Sinonimi: espandi le liste con varianti ("ottimo" → "ottima", "ottimi")
- Negazioni semplici: gestisci "non buono" come negativo
- Statistiche: conta quante parole positive/negative trovate in totale
