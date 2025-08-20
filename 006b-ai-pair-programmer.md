## AI Pair Programmer

#### Scenario
Sei in un piccolo team e ti viene chiesto di sviluppare un modulo semplice: gestione utenti con funzioni per registrazione, login e reset password.

Puoi scrivere il codice base da solo, ma puoi usare un AI come pair programmer per:
1. Suggerire test automatici
2. Scrivere documentazione leggibile (README, commenti)
3. Proporre refactoring del codice

#### Obiettivi didattici
- Capire come integrare un LLM nel flusso di lavoro
- Imparare a validare e non accettare ciecamente output AI
- Documentare il processo di collaborazione human-AI

#### Workflow suggerito
1. Scrivi le funzioni base manualmente (register_user, login_user, reset_password)
2. Chiedi all'AI di generare test per queste funzioni
3. Chiedi all'AI di proporre documentazione (docstring, commenti)
4. Chiedi un refactoring e confronta con il tuo approccio
5. Documenta tutto il processo nel README

#### Template documentazione interazioni
Per ogni richiesta all'AI documenta:
- Prompt inviato: [testo esatto]
- Output ricevuto: [risposta AI]
- Decisione: [accettato/modificato/scartato]
- Motivazione: [perché hai preso questa decisione]

#### Funzioni minime da implementare
- register_user(username, email, password): validazione input + creazione utente
- login_user(username, password): autenticazione + gestione sessione
- reset_password(email): invio link reset + validazione

#### Deliverables
- Codice con funzioni base scritte manualmente
- Test/documentazione generati con supporto AI (ma validati da te)
- README dettagliato con spiegazione delle funzioni, log completo delle interazioni AI, riflessione critica su cosa ha funzionato/non funzionato

#### Criteri di accettazione
- Funzioni base corrette e scritte manualmente (senza AI)
- Uso documentato dell'AI con template richiesto
- Evidenza chiara di valutazione critica (non copia-incolla cieco)
- README dimostra comprensione dei pro/contro dell'AI assistance

#### Domande di riflessione da includere nel README
- In quali task l'AI ti ha aiutato di più?
- Dove hai dovuto correggere o scartare suggerimenti AI?
- Come cambieresti il tuo approccio per la prossima volta?
- Quando useresti l'AI vs quando preferisci lavorare da solo?
