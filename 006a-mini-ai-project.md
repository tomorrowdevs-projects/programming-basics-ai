## Mini AI Project

#### Scenario
Vuoi costruire un piccolo sistema AI in grado di analizzare messaggi degli utenti e classificarli come:
- "Domanda informativa" (es. orari, prezzi)
- "Feedback positivo"
- "Feedback negativo"

#### Obiettivi didattici
- Integrare dataset, regole e funzioni in un unico progetto
- Usare OOP per organizzare il codice
- Capire la differenza tra rule-based e machine learning

#### Specifiche tecniche
1. Crea un dataset minimo (almeno 12 frasi divise nelle 3 categorie)
2. Implementa una classe SimpleClassifier con metodo train(dataset) e metodo predict(input)
3. Usa keyword spotting (liste di parole chiave per ogni categoria)
4. Se una frase non contiene keyword, ritorna "Non riconosciuto"

#### Comportamento atteso
- Input: "A che ora chiudete stasera?" → Output: "Domanda informativa"
- Input: "Servizio fantastico, complimenti!" → Output: "Feedback positivo"
- Input: "Molto deluso dalla qualità" → Output: "Feedback negativo"
- Input: "Come va la vita?" → Output: "Non riconosciuto"

#### Keyword lists suggerite
- Domanda informativa: quando, dove, come, quanto, orari, prezzo, costo
- Feedback positivo: ottimo, fantastico, eccellente, bravo, perfetto, consiglio
- Feedback negativo: pessimo, terribile, deluso, sbagliato, lento, caro

#### Formato dataset minimo (CSV)
testo,categoria
"A che ora aprite domani?","Domanda informativa"
"Quanto costa la spedizione?","Domanda informativa"
"Dove vi trovate?","Domanda informativa"
"Servizio ottimo, complimenti","Feedback positivo"
"Prodotto fantastico","Feedback positivo"
"Esperienza eccellente","Feedback positivo"
"Molto deluso dal servizio","Feedback negativo"
"Qualità pessima","Feedback negativo"
"Tempi di consegna terribili","Feedback negativo"

#### Come testare
1. Carica il dataset e verifica che le 12 frasi base siano classificate correttamente
2. Testa con frasi nuove che contengono keyword note
3. Testa con frasi ambigue o senza keyword
4. Verifica che la gestione errori funzioni (input vuoti, None, etc.)

#### Deliverables
- Codice funzionante con classe SimpleClassifier
- Dataset in CSV/JSON con almeno 12 esempi
- README che spiega il funzionamento e i limiti del sistema

#### Criteri di accettazione
- Classificazione corretta su tutto il dataset base (12/12)
- Gestione appropriata di input imprevisti ("Non riconosciuto")
- Struttura OOP pulita (classe + metodi separati)
- README documenta chiaramente limiti del sistema rule-based
