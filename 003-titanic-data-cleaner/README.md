### Titanic Data Cleaner & Baseline

#### Contesto business
Un team deve creare una baseline rapida di analisi per presentare insight sul Titanic. Il focus è dimostrare come la **qualità dei dati** influenzi i risultati (GIGO) e calcolare metriche semplici.

#### Obiettivi
- Eseguire data cleaning (valori mancanti, tipi, outlier basilari).
- Calcolare statistiche descrittive prima/dopo cleaning.
- Implementare una **regola baseline** di sopravvivenza e valutarne l'accuracy.

#### Requisiti funzionali
1. Funzione `load_data(path)` che carica CSV.
2. Funzione `clean_data(df)` che gestisce null (es. età media per NA, drop righe con NA critici).
3. Statistiche richieste: numero passeggeri, % sopravvissuti, età media (prima/dopo cleaning).
4. Regola baseline (esempio): `if Sex==female then survived else not`.
5. Calcolo **accuracy** della baseline rispetto alla colonna `Survived`.

#### Requisiti non funzionali
- Riproducibilità: fissare i passi di cleaning nel README.  
- Trasparenza: ogni trasformazione va documentata.

#### Schema colonne attese (minimo)
- `PassengerId` (int), `Survived` (0/1), `Pclass` (1/2/3), `Name` (str), `Sex` (str), `Age` (float/NA), `SibSp` (int), `Parch` (int), `Fare` (float), `Embarked` (str/NA).

#### File di test fornito
Dataset `dataset.csv` con 50 passeggeri contenente:
- **Valori Age mancanti** (circa 12 righe) per testare l'imputazione
- **Mix di classi** e età per statistiche significative  
- **Distribuzione realistica** di sopravvissuti (60% non sopravvissuti, 40% sopravvissuti)
- **Esempi di ogni classe** (1a, 2a, 3a) per testare regole baseline

#### Passi operativi
1) Carica `titanic_sample.csv` grezzo; conta NA per colonna.  
2) Applica `clean_data`: imputazione età con media per classe, rimozione righe con `Embarked` NA.  
3) Calcola statistiche prima/dopo e salva un **confronto** in tabella.  
4) Implementa la regola baseline e calcola l'accuracy.  
5) Scrivi una breve analisi sui limiti della baseline e su come i NA influenzavano i risultati.

#### Deliverable
- Programma + report (MD o PDF) con tabella **prima/dopo** e accuracy + file `titanic_sample.csv`.

#### Criteri di accettazione (UAT)
- Presenza delle 3 statistiche richieste.  
- Cleaning riproducibile e descritto.  
- Accuracy calcolata correttamente sulla baseline.

#### Estensioni (facoltative)
- Confusion matrix per la baseline.  
- Aggiungere una seconda regola (es. `Sex==female OR Pclass==1`).
