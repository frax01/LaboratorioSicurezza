# LaboratorioSicurezza

# Componenti del Gruppo di Lavoro
*Micucci Simone 1934642*  
*Martignoni Francesco 1934742*  
*Guidone Gennaro*  

# Progetto Scelto
Top Listener:
Applicazione web dove ci si collega tramite il proprio account spotify.  
In base a gli ultimi 12 mesi verrà valutato di chi siamo i più grandi fan.  
Sulla base di questo verranno creati degli stati che permettono all'utente di vedere eventi esclusivi solo per i fan più accaniti,  
tra cui raduni ed eventi esclusivi organizzati dall'artista stesso.  
Gli artisti possono organizzare eventi di ogni tipo, i "Top Fan" possono organizzare raduni.  
Tramite localizzazione vengono mostrati gli eventi in ordine di vicinanza.

# User stories

### sintassi di scrittura
*Feature*
Rule
Example/Scenario
    Given, When, Then, And, But, Or

### come deve essere una user stories funzionale
La user stories deve essere "SMART"
- Specifica         (dettagli programmabili e non ambigui)
- Misurabile        (misure deterministiche e non olistiche)
- Raggiungibile     (complessità minima possibile)
- Rilevante         (di valore per gli stakeholder)
- Scadenzata        (limite temporale per velocizzare lo sviluppo)

*Rule*:     Per lo __status__ ci sono delle specifiche da rispettare
            *Artista*
                Per passare da User/Fan a Artista bisogna aver pubblicato almeno una canzone. I Artista possono essere anche Fan
            *Fan*
                Almeno 50 ore di ascolto
                Almeno 2 album differenti
                Almeno 10 canzoni differenti
            *User*
                Utente standard che non soddisfa i requisiti di cui nelle altre categorie

In queste Feature quando parliamo di utenti facciamo riferimento a tutti quelli che si sono registrati, indipendentemente poi dal loro status

### 1 - ACCOUNT:
### 01
*Feature*:  User Register:
                L'utente si registra effettuando un'iscrizione a pagamento e viene riconosciuto come uno User. 
                La registrazione necessita di:
                - Nome
                - Cognome
                - Data di nascita(>=16)
                - Email
                - Password(requisiti minimi di sicurezza)
### 02
*Feature*:  User Login:
                L'utente accede e viene riconosciuto come User/Artista/TopArtista/Fan/TopFan. Tutti gli utenti sono degli User, ma oltre a questa categoria se ne possono aggiungere altre
### 03
*Feature*:  User Logout:
                L'utente esce dal suo account e se vuole può loggarsi di nuovo o cambiare account
### 04
*Feature*:  Ricordami:
                L'utente che accede all'app, se ancora non l'ha fatto, ha la possibilità di cliccare su "ricordami" per salvare email e pw per i futuri accessi
### 05
*Feature*:  Eliminare il proprio account:
                L'utente può eliminare il proprio account e non avere più accesso all'app
### 06
*Feature*:  Centro Assistenza:
                Email a cui scrivere in caso di necessità

### 2 - RADUNO:
### 7
*Feature*:  Crea Evento(raduno) da Artista:
                L'artista può creare eventi di tipo raduno decidendo data e luogo. Non possono esserci limiti di posti o costi di accesso. Esso decide se possono accedervi tutti gli User o solo i Fan
### 8
*Feature*:  Crea Evento(raduno) da Fan -> Fallimento:
                Il Fan non può creare raduni
### 9
*Feature*:  Crea Evento(raduno) da User -> Fallimento:
                L'User non può creare raduni
### 10
*Feature*:  Like:
                Possibilità di mettere like agli eventi raduno da User/TopFan, a seconda di chi può partecipare
### 11
*Feature*:  Commenti:
                Possibilità di mettere commenti agli eventi raduno da User/TopFan, a seconda di chi può partecipare
### 12
*Feature*:  Geolocalizzazione:
                Possibilità di geolocalizzare un raduno solo per chi può partecipare all'evento, quindi User/Fan

### 3 - CONCERTO:
### 13
*Feature*:  Crea Evento(concerto) da Artista:
                L'artista può creare eventi di tipo concerto decidendo data, luogo e numero di posti disponibili. Esso decide se possono accedervi tutti gli User o solo i Fan
### 14
*Feature*:  Crea Evento(concerto) da Fan -> Fallimento:
                Il Fan non può creare concerti
### 15
*Feature*:  Crea Evento(concerto) da User -> Fallimento:
                L'User non può creare concerti
### 16
*Feature*:  Like:
                Possibilità di mettere like agli eventi concerto da User/TopFan, a seconda di chi può partecipare
### 17
*Feature*:  Commenti:
                Possibilità di mettere commenti agli eventi concerto da User/TopFan, a seconda di chi può partecipare
### 18
*Feature*:  Geolocalizzazione:
                Possibilità di geolocalizzare un concerto solo per chi può partecipare all'evento, quindi User/Fan

### 19
*Feature*:  x
                x

### 20
*Feature*:  x
                x

### 21
*Feature*:  x
                x

### 22
*Feature*:  x
                x

### 23
*Feature*:  x
                x

### 24
*Feature*:  x
                x

### 25
*Feature*:  x
                x

### 26
*Feature*:  x
                x

### 27
*Feature*:  x
                x

### 28
*Feature*:  x
                x

### 29
*Feature*:  x
                x

### 30
*Feature*:  x
                x
