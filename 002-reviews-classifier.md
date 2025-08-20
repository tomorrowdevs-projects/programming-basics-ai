## Classificatore di recensioni semplice (keyword-based)

#### Contesto business
Un piccolo e‑commerce vuole una prima etichettatura rapida delle recensioni per priorità al customer care. Budget e tempo sono limitati: niente ML, solo regole temporanee.

#### Obiettivi
- Costruire un classificatore **Positive/Negative/Neutral** basato su keyword.
- Capire **features** (parole chiave) e **labels** (classi). 
- Preparare un dataset **estendibile** per futuri modelli ML.

#### Requisiti funzionali
1. Funzione `predict(review: string) -> {Positive|Negative|Neutral}`.
2. Liste di keyword **positive** (≥5) e **negative** (≥5) configurabili.
3. Normalizzazione: lowercase, rimozione punteggiatura, trim spazi.
4. Conteggio occorrenze: se `pos>neg` → Positive; se `neg>pos` → Negative; altrimenti → Neutral.
5. Gestione di frasi ambigue (pareggio) come Neutral.

#### Requisiti non funzionali
- Semplicità e chiarezza del codice.
- Facilità di aggiungere nuove keyword senza cambiare la logica.

#### Dataset minimo (testo)
1) "Mi piace molto questo prodotto" → Positive (soddisfazione)  
2) "Non sono soddisfatto" → Negative (insoddisfazione)  
3) "Ottimo rapporto qualità prezzo" → Positive (apprezzamento)  
4) "Terribile esperienza" → Negative (emozione negativa)  
5) "È ok, fa il suo dovere" → Neutral (linguaggio neutro)

#### Esempio di comportamento
Input: "Design ottimo ma assistenza pessima" → `pos=1`, `neg=1` → **Neutral** (pareggio).

#### Passi operativi
1) Definisci due insiemi: `POS = {ottimo, eccellente, consigliato, perfetto, piace}`; `NEG = {pessimo, terribile, scarso, non, difettoso}`.  
2) Pre‑processa la review (lowercase, strip punteggiatura).  
3) Conta match in `POS` e `NEG`.  
4) Applica decisione (pos>neg / neg>pos / pareggio).  
5) Aggiungi **almeno 10 nuove recensioni** al dataset e verifica manualmente l'esito.

#### Deliverable
- Programma funzionante + README con elenco keyword, esempi e istruzioni.

#### Criteri di accettazione (UAT)
- Corretta classificazione del dataset minimo (5/5).  
- Gestione corretta dei casi di pareggio → Neutral.  
- Struttura del codice pulita e keyword facilmente estendibili.

#### Estensioni (facoltative)
- Pesi per le parole (es. "terribile" vale 2).  
- Rilevazione di negazioni semplici ("non buono").
