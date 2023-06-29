# LaboratorioSicurezza

# Componenti del Gruppo di Lavoro
*Micucci Simone 1934642*  
*Martignoni Francesco 1934742* 

# Progetto Event Listener:
L'applicazione Event Listener fornisce la possibilità di creare dei Raduni da parte degli Artisti e ai propri di Fan di parteciparvi. 
Per accedere è richiesta contemporaneamente la registrazione/login al sito e l'accesso a Spotify e, all'interno, l'utente viene riconosciuto con un certo status. Ad ogni nostro accesso verrà valutato di quali Artisti siamo i più grandi Fan secondo dei criteri prestabiliti. Gli Artisti possono poi creare degli Eventi di tipo Raduno e solo i Fan di quell'Artista vi possono partecipare.

__status__:
    *Artista*:
        Un Artista è considerato tale se ha pubblicato almeno una canzone
    *Fan*:
        Almeno 10 ore di ascolto di un Artista
    *Listener*:
        Account che non soddisfa i requisiti di Artista e Fan

- Ogni account è un Listener
- Ogni account può essere Fan di più Artisti, viene poi considerato come un Listener per gli Artisti di cui non è Fan
- Ogni Artista può essere Fan di altri Artisti
- Possono partecipare ai Raduni creati dagli Artisti solo i Fan di quell'Artista
- Non si può accedere al sito senza aver effettuato Registrazione/Login del sito + Login con Spotify
- Una volta effettuato l'accesso l'utente vede sulla sua sinistra gli Artisti di cui è Fan e sulla destra i Raduni a cui si è iscritto, a meno  che non sia un Listener, il quale non visualizza nessuna di queste due categorie. Nel caso in cui sia anche un Artista, vengono visualizzati sulla destra anche gli Eventuali Raduni creati

**USER STORIES**

### 1 - ACCESSO:
### 01
*Feature*:  Registrazione Event Listener:  
                Un nuovo utente deve registrarsi con:
                - nome
                - cognome
                - data di nascita(>=16 anni)
                - mail
                - password(requisiti minimi di sicurezza)
### 02
*Feature*:  Login Event Listener:  
                Un utente già registrato deve fare il login prima di accedere al sito
### 03
*Feature*:  Login Spotify:  
                L'utente inserisce le proprie credenziali di Spotify e si procede con il controllo dello status. Successivamente si viene reindirizzati sulla homepage
### 04
*Feature*: Riconoscimento:  
                Dopo il login viene controllato se un utente è un Listerner, un Fan o un'Artista
### 05
*Feature*:  Logout:  
                Il Listener esce dall'account e si viene reindirizzati alla pagina di accesso iniziale
### 06
*Feature*:  Ricordami:  
                Il Listener che accede all'app, se ancora non l'ha fatto, ha la possibilità di cliccare su "ricordami" per salvare email e pw per i futuri accessi sia per Event Listener che per Spotify

### 2 - VISIONE SEZIONE RADUNO:
### 07
*Feature*:  Visualizzazione Artisti di cui si è Fan:  
                Non appena si accede all'applicazione vengono visualizzati sulla sinistra tutti gli Artisti di cui si è Fan, se presenti
### 08
*Feature*:  Visualizzazione Raduni prenotati:  
                Non appena si accede all'applicazione vengono visualizzati sulla destra tutti i Raduni a cui ci si è prenotati, se presenti
### 09
*Feature*:  Visualizzazione Raduni creati:  
                Non appena un Artista accede all'applicazione vengono visualizzati sulla destra tutti i Raduni da lui creati, se presenti
### 10
*Feature*:  Sezione visita Raduno da Listener:  
                Un Listener(che non è Fan di nessun Artista) non può visitare la sezione Raduni
### 11
*Feature*:  Sezione visita Raduno da Fan:  
                Un Fan può visitare la sezione Raduni e vede solo i Raduni degli Artisti di cui è Fan, a cui può accedere e partecipare

### 3 - CREAZIONE RADUNO:
### 12
*Feature*:  Sezione Crea Raduno da Listener:  
                Se si è solo Listener o Fan la sezione Crea Raduno è visibile, ma opaca e non selezionabile
### 13
*Feature*:  Sezione Crea Raduno da Artista:  
                Se il Listener è un'Artista la sezione Crea Raduno diventa ben visibile e selezionabile
### 14
*Feature*:  Crea Raduno da Artista:  
                L'Artista può creare eventi di tipo Raduno. Non ci sono limiti di posti o costi di accesso. Possono accedervi solo i Fan di quell'Artista. 
                Quando si clicca sulla sezione apposita per creare il Raduno si apre un form con informazioni da inserire:    
                    - breve descrizione testuale(max 50 char) del tipo di Raduno(uscita disco, performance, video del nuovo singolo ecc)  
                    - data  
                    - orario  
                    - luogo 
### 15
*Feature*:  Visualizzazione Raduno creato:  
                Una volta creato correttamente il Raduno si viene reindirizzati alla homepage e quel Raduno viene visualizzato sulla destra. In esso è presente anche un pulsante per modificare il Raduno o per cancellarlo

### 4 - PARTECIPAZIONE RADUNO:
### 16
*Feature*:  Partecipazione Raduno da Fan:  
                Il Fan clicca sul Raduno per partecipare e deve iscriversi con:
                    - età(eventuali prerequisiti di età minima)
                    - mail
### 17
*Feature*:  Controllo campi inseriti per i Fan:  
                Se un Fan cerca di iscriversi ad un Raduno e non soddisfa o non compila correttamente i campi richiesti ne viene segnalato l'errore. Altrimenti l'iscrizione procede con la mail di conferma e si viene reindirizzati alla homepage
### 18
*Feature*:  Conferma partecipazione al Raduno:  
                Il Fan che si è iscritto al Raduno correttamente riceve una mail(stessa usata per il login) con le informazioni di conferma per la partecipazione con:
                    - nome d'arte organizzatore
                    - breve descrizione testuale del tipo di Raduno(uscita disco, performance, video del nuovo singolo ecc)
                    - data
                    - orario
                    - luogo
### 19
*Feature*:  Cancellazione partecipazione al Raduno:  
                Il Fan che si è iscritto al Raduno può cancellare la sua partecipazione con un pulsante apposito sul raduno stesso
### 20
*Feature*:  Informazioni sul Raduno:  
                L'organizzatore del Raduno riceve una mail settimanalmente con le informazioni di quanti partecipanti ci sono al Raduno

### 5 - MODIFICA IMPOSTAZIONI RADUNO:
### 21
*Feature*:  Modifica organizzazione Raduno:  
                L'organizzatore del Raduno può modificare quest'ultimo cliccando su di un apposito pulsante del Raduno che viene visualizzato lateralmente sulla homepage. Questo ci reindirizza allo stesso form di compilazione di quando si deve creare il Raduno ma con i campi precompilati. Una volta fatto il cambiamento si ritorna sulla homepage
### 22
*Feature*:  Notifica di modifica organizzazione Raduno:  
                L'applicazione non appena un Raduno viene modificato manda un messaggio(mail broadcast) a tutti gli iscritti con i cambiamenti apportati. La mail viene mandata solo se c'è almeno un cambiamento nelle informazioni scritte
### 23
*Feature*:  Cancellazione Raduno:  
                L'organizzatore del Raduno può eliminare quest'ultimo cliccando su di un apposito pulsante del Raduno che viene visualizzato lateralmente sulla homepage. Viene chiesta la conferma dell'operazione prima di procedere e una volta eliminato il Raduno scompare. Questa operazione viene fatta tutta sulla homepage
### 24
*Feature*:  Notifica di cancellazione Raduno:  
                L'applicazione non appena un Raduno viene cancellato manda un messaggio(mail broadcast) a tutti gli iscritti con la cancellazione del Raduno


**TEST VERTICALI:**

**1** -> Fallimento creazione Raduno da Listener:  
                Il Listener non autorizzato prova a creare il raduno(ad esempio con un link mandato da un altro utente autorizzato a crearlo) ma viene riportato alla homepage e viene notificato dell'errore 
**2** -> Fallimento creazione Raduno da Listener:  
                Il Listener manda una POST HTTP al server con le informazioni per creare un raduno. Non viene creato il raduno e l'utente viene notificato dell'errore

**3** -> Fallimento partecipazione Raduno da Listener:  
                Il Listener non autorizzato prova a visualizzare il raduno(ad esempio con un link mandato da un altro utente autorizzato a visualizzarlo) ma viene riportato alla homepage  e viene notificato dell'errore
**4** -> Fallimento partecipazione Raduno da Listener:  
                Il Listener manda una POST HTTP al server con la richiesta di partecipazione ad un raduno a cui non è autorizzato a partecipare. Non viene iscritto il raduno e viene notificato dell'errore