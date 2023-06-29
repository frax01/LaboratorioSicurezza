# LaboratorioSicurezza

# Componenti del Gruppo di Lavoro
*Micucci Simone 1934642*  
*Martignoni Francesco 1934742* 

# Progetto Event Listener:
L'applicazione Event Listener fornisce la possibilità di creare dei Raduni da parte degli Artisti e ai propri di Fan di parteciparvi. 
Per entrare nel sito è richiesta la registrazione. Una volta fatta si può collegare il proprio account Spotify(utilizzando OmniAuth). In caso di accesso con Spotify si viene riconosciuti come utenti con un certo status, altrimenti come un Utente. Ad ogni accesso verrà valutato di quali Artisti siamo i più grandi Fan secondo dei criteri prestabiliti. Gli Artisti possono poi creare degli Eventi di tipo Raduno e solo i Fan di quell'Artista vi possono partecipare

__status__:
    *Artista*:
        L'Artista è considerato tale se ha pubblicato almeno una canzone
    *Fan*:
        Almeno 10 ore di ascolto di un Artista
    *Listener*:
        Account che non soddisfa i requisiti di Artista e Fan ma ha fatto l'accesso con Spotify
    *Utente*:
        Account che non soddisfa i requisiti di Artista e Fan, non ha fatto l'accesso con Spotify

- Ogni account è un Listener
- Ogni account può essere Fan di alcuni Artisti ma viene considerato come un Listener per gli Artisti di cui non è Fan
- Ogni Artista può essere Fan di altri Artisti
- Possono partecipare agli Eventi creati dagli Artisti solo i Fan di quell'Artista
- Nella sezione Raduno si vedono sempre tutti i Raduni in programma
- Non si può accedere al sito senza aver effettuato Registrazione/Login
- Una volta fatto il Login con Spotify l'account vede sulla sua sinistra gli Artisti di cui è Fan e sulla destra i Raduni a cui si è iscritto
- Un Utente non vede sulla sua sinistra gli Artisti di cui è Fan e sulla destra i Raduni a cui si è iscritto

### sintassi di scrittura
*Feature*
Rule
Example/Scenario
    Given, When, Then, And, But, Or

### 1 - ACCESSO:
### 01
*Feature*:  Login errato:
                Il Listener prova ad accedere tramite Spotify ma sbaglia ad inserire le credenziali -> ERRORE, Riprovare
### 02
*Feature*:  Login corretto:
                Il Listener accede tramite Spotify e si procede con il controllo dello status. Successivamente si viene reindirizzati sulla homepage
### 03
*Feature*: Riconoscimento Fan
                Dopo il login viene controllato se un Listener è un Fan
### 04
*Feature*: Riconoscimento Artista
                Dopo il login viene controllato se un Listener è un'Artista
### 05
*Feature*:  Logout:
                Il Listener esce dall'account e si viene reindirizzati alla pagina di login iniziale
### 06
*Feature*:  Ricordami:
                Il Listener che accede all'app, se ancora non l'ha fatto, ha la possibilità di cliccare su "ricordami" per salvare email e pw per i futuri accessi
### 07
*Feature*:  Visualizzazione Artisti di cui si è Fan:
                Non appena si accede all'applicazione vengono visualizzati sulla sinistra tutti gli Artisti di cui si è Fan

### 2 - VISIONE SEZIONE RADUNO:
### 08
*Feature*:  Sezione visita Raduno da Utente(cioè un account che non ha fatto l'accesso con Spotify):
                Un Utente vede la sezione Raduno ma per visitarla una volta cliccata viene mostrato un popup di login di Spotify, altrimenti non vi può accedere
### 09
*Feature*:  Sezione visita Raduno da Listener(cioè un Listener che non è Fan di nessun Artista):
                Un Listener può visitare la sezione Raduno ma non può accedere nè selezionare nessuno di essi. Gli Eventi saranno visualizzati in modo più opaco
### 10
*Feature*:  Sezione visita Raduno da Fan:
                Un Fan può visitare la sezione Raduno ma può accedere(e cliccare) solo ai Raduni di cui egli è Fan dell'Artista. Per tutti gli altri Raduni egli è considerato come un Listener e quindi saranno visualizzati opachi e non selezionabili
### 11
*Feature*:  Sezione visita Raduno da Artista:
                Un'Artista, se è un Fan di un altro Artista x, può visitare la sezione Raduno e ci si comporta come nel caso Fan

### 3 - SEZIONE CREA RADUNO:
### 12
*Feature*:  Sezione Crea Raduno da Listener:
                Se si è solo Listener la sezione Crea Raduno è visibile, ma opaca e non selezionabile
### 13
*Feature*:  Sezione Crea Raduno da Fan:
                Se Il Listener è anche un Fan la sezione Crea Raduno è visibile, ma opaca e non selezionabile
### 14
*Feature*:  Sezione Crea Raduno da Artista:
                Se Il Listener è un'Artista la sezione Crea Raduno diventa ben visibile e selezionabile
### 15
*Feature*:  Crea Raduno da Artista:  
                L'Artista può creare eventi di tipo Raduno. Non ci sono limiti di posti o costi di accesso. Possono accedervi solo i Fan di quell'Artista. Quando si clicca sulla sezione apposita per creare il Raduno si apre un form con informazioni da inserire.  
                Le informazioni necessarie da inserire per il Raduno sono:  
                    - breve descrizione testuale(max 50 char) del tipo di Raduno(uscita disco, performance, video del nuovo singolo ecc)  
                    - data  
                    - orario  
                    - luogo 
### 17
*Feature*:  Creazione Raduno da **Listener** -> Fail1:  
                Il Listener non autorizzato(ad esempio con un link che gli viene mandato da un altro utente non autorizzato) prova a creare l'evento ma viene riportato alla homepage
### 17
*Feature*:  Creazione Raduno da **Listener** -> Fail2:
                Il Listener manda una POST HTTP al server con le informazioni per creare un evento. Non viene creato l'evento e viene notificato dell'errore(ALERT)
### 16
*Feature*:  Visualizzazione Raduno creato:  
                Una volta creato correttamente il Raduno si viene reindirizzati alla propria homepage e quel Raduno viene visualizzato lateralmente in una sezione apposita. In esso è presente anche un pulsante per modificare il Raduno o per cancellarlo

### 4 - PARTECIPAZIONE RADUNO:
### 17
*Feature*:  Partecipazione Raduno da Fan:  
                Il Fan clicca sul Raduno per partecipare e deve iscriversi con:
                    - età(eventuali prerequisiti di età minima)
                    - mail
### 17
*Feature*:  Partecipazione Raduno da **Listener** -> Fail1:  
                Il Listener non autorizzato(ad esempio con un link che gli viene mandato da un altro utente non autorizzato) prova a visualizzare l'evento ma viene riportato alla homepage
### 17
*Feature*:  Partecipazione Raduno da **Listener** -> Fail2:
                Il Listener manda una POST HTTP al server con le informazioni per partecipare ad un evento a cui non è autorizzato. Non viene iscritto all'evento e viene notificato dell'errore(ALERT)
### 18
*Feature*:  Controllo campi inseriti per i Fan:
                Se un Fan cerca di iscriversi ad un Raduno e non soddisfa o non compila correttamente i campi richiesti ne viene segnalato l'errore. Altrimenti l'iscrizione procede con la mail di conferma e si viene reindirizzati alla homepage
### 19
*Feature*:  Conferma partecipazione al Raduno:
                Il Fan che si è iscritto al Raduno correttamente riceve una mail(alla stessa usata per il login) con le informazioni di conferma per la partecipazione con:
                    - nome d'arte organizzatore
                    - breve descrizione testuale del tipo di Raduno(uscita disco, performance, video del nuovo singolo ecc)
                    - data
                    - orario
                    - luogo
### 20
*Feature*:  Nuovo partecipante al Raduno:
                L'organizzatore del Raduno riceve una mail settimanalmente con le informazioni di quanti partecipanti ci sono al Raduno

### 5 - MODIFICA MODALITA RADUNO:
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
