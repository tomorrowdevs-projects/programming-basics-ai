### Simulatore di rete neurale: classificatore di frutta con pesi

#### Scenario
Simulare il comportamento di una rete neurale semplice che classifica frutta usando il concetto di **pesi**, **soglie** e **layer di elaborazione**.

#### Obiettivi
- Capire come le caratteristiche diventano **numeri** (input layer)
- Sperimentare con **pesi** e **soglie** (hidden layer logic)
- Vedere come si arriva alla **decisione finale** (output layer)
- Collegare questo al funzionamento delle reti neurali vere

#### Concetti da implementare

**Struttura a 3 layer da creare:**

1. **Input Layer**: Converte caratteristiche (colore, forma, dimensione) in valori numerici
   - Assegna "pesi" diversi a caratteristiche diverse
   - Es: "giallo" potrebbe valere più di "verde" per identificare banane

2. **Hidden Layer**: Combina i valori numerici con moltiplicatori
   - Crea 2 "neuroni": uno per riconoscere banane, uno per mele
   - Ogni neurone pesa le caratteristiche in modo diverso
   - Es: neurone-banana dà più importanza a forma "lunga"

3. **Output Layer**: Applica soglia e decide il risultato finale
   - Se punteggio supera una soglia → alta confidenza
   - Confronta i punteggi dei due neuroni per decidere

#### Comportamento atteso

**Test cases da verificare:**
- Input: giallo, lunga, grande → "Banana" (punteggio alto per neurone-banana)
- Input: rosso, tonda, piccola → "Mela" (punteggio basso per neurone-banana)
- Input: verde, tonda, piccola → "Incerto" o "Mela" (punteggi bassi entrambi)
- Input: verde, lunga, grande → "Banana" (forma compensa colore non ottimale)

#### Esperimenti da fare

1. **Test baseline**: implementa con pesi che ti sembrano ragionevoli
2. **Esperimento pesi**: cambia l'importanza delle caratteristiche - cosa succede se il colore diventa meno importante?
3. **Esperimento soglia**: prova soglie diverse - soglia bassa vs alta come cambia i risultati "Incerto"?

#### Come testare
1. Implementa la funzione `classify_fruit(colore, forma, dimensione)`
2. Testa con i 4 casi comportamento atteso + altri 3 che inventi
3. Sperimenta cambiando i pesi numerici
4. Prova diverse soglie di decisione
5. Documenta cosa noti cambiando questi parametri

#### Spunti implementativi
- Pensa a come assegnare numeri a "giallo", "verde", "rosso"
- Come combinare 3 numeri per ottenere un punteggio finale?
- Quale soglia usare per dire "sono sicuro del risultato"?
- Come gestire il caso in cui nessun punteggio è alto?

#### Documenta nel README

1. **Come questo simula una rete neurale**:
   - Che ruolo hanno i 3 layer?
   - Perché usiamo numeri invece di regole if-else?
   
2. **Differenze con rete neurale vera**:
   - Come si comporterebbe diversamente una rete addestrata?
   - Vantaggi e svantaggi del nostro approccio "manuale"

3. **Cosa hai imparato** sperimentando con pesi e soglie diverse

#### Deliverables
- Programma con funzione di classificazione principale
- Report esperimenti con almeno 2 variazioni di pesi/soglie
- README con spiegazione concettuale del collegamento alle reti neurali

#### Criteri di accettazione
- Tutti i test case base funzionano in modo ragionevole
- Almeno 2 esperimenti con parametri diversi documentati
- README spiega chiaramente come questo si collega alle reti neurali vere
- Il sistema usa pesi numerici e soglie (non solo regole if-else semplici)

#### Estensioni opzionali
- Aggiungi una 4a caratteristica (es: "maturità", "texture")
- Crea un 3o tipo di frutto da riconoscere
- Visualizza i punteggi intermedi per capire meglio il processo di decisione
