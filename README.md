# LaboratorioSicurezza

# Componenti del Gruppo di Lavoro
*Micucci Simone 1934642*  
*Martignoni Francesco 1934742*  
*Guidone Gennaro*  

# Progetto Scelto
Top Listener:
> Applicazione web dove ci si collega tramite il proprio account spotify.  
In base a gli ultimi 12 mesi verrà valutato di chi siamo i più grandi fan.  
Sulla base di questo verranno creati degli stati che permettono all'utente di vedere eventi esclusivi solo per i fan più accaniti,  
tra cui raduni ed eventi esclusivi organizzati dall'artista stesso.  
Gli artisti possono organizzare eventi di ogni tipo, i "Entusiast" possono organizzare raduni.  
Tramite localizzazione vengono mostrati gli eventi in ordine di vicinanza e interesse.

# User stories

### sintassi di scrittura
*Feature*
Rule  
Example/Scenario  
    *Given, When, Then, And, But, Or*

### come deve essere una user stories funzionale
La user stories deve essere "SMART"
- Specifica         (dettagli programmabili e non ambigui)
- Misurabile        (misure deterministiche e non olistiche)
- Raggiungibile     (complessità minima possibile)
- Rilevante         (di valore per gli stakeholder)
- Scadenzata        (limite temporale per velocizzare lo sviluppo)

*Rule*:     Per lo __status__ ci sono delle specifiche da rispettare  
	*Artista*  
		Almeno 2 album pubblicati.  
		Almeno 10 canzoni pubblicate (album inclusi).  
	*Fan*  
		Almeno 350 ore di ascolto.  
		Almeno 2 album differenti.  
		Almeno 3 canzoni differenti.  
	*Entusiast*  
		Almeno 700 ore di ascolto.  
		Almeno 3 album differenti.  
		Almeno 10 canzoni differenti.  

Lo status di Artista non sostituisce gli altri stati.  
Lo status di Entusiast estende quello di Fan.  
Lo status di Fan o Entusiast è limitato al singolo artista e non viene esteso a tutti gli artisti.  
Lo status di Fan o Entusiast può essere presente su più artisti __(Esempio: User a è Fan di Vasco Rossi, Fan di Lucio Battisti, Entusiast di Rino Gaetano, Entusiast di Franco Battiato)__.

### 01
*Feature*:  User Login  
                L'utente accede tramite Spotify e gli vengono attribuiti i rispettivi status.

### 02
*Feature*:  User Logout  
                L'utente seleziona il tasto logout e ritorna sulla schermata di accesso iniziale.

### 03
*Feature*:  Riconscimento Artista  
                L'utente accede tramite Spotify, vengono controllate le sue pubblicazioni e se rispecchiano i criteri acquisisce lo status di artista riguardo al proprio nome d'arte.

### 04
*Feature*:  Riconscimento Fan  
                L'utente accede tramite Spotify, vengono controllati i suoi ascolti e se rispecchiano i criteri acquisisce lo status di fan riguardo i nomi degli artisti con cui combacia i requisiti.

### 05
*Feature*:  Riconscimento Entusiast  
                L'utente accede tramite Spotify, vengono controllati i suoi ascolti e se rispecchiano i criteri acquisisce lo status di entusiast riguardo i nomi degli artisti con cui combacia i requisiti.

### 06
*Feature*:  Crea Evento(raduno) da Artista -> Success  
                L'utente crea un evento selezionando artista, data e luogo. Se per l'artista selezionato ha lo status di artista può scegliere se includere solo entusiast o tutti i fan, se mettere un costo di ingresso e il numero di posti.

### 07
*Feature*:  Crea Evento(raduno) da Entusiast -> Success  
                L'utente crea un evento selezionando artista, data e luogo. Se per l'artista selezionato ha lo status di entusiast l'evento è aperto a tutti i fan, è gratuito e riporta il numero di posti massimi.

### 08
*Feature*:  Crea Evento(raduno) da Fan -> Fail  
                L'utente crea un evento selezionando artista, data e luogo. Se per l'artista selezionato ha lo status di fan non dovrebbe vedere tra le opzioni di creazione evento il nome di tale artista. Se per nessun artista ha lo status di artista o entusiast non dovrebbe vedere il pulsante "crea evento".

### 09
*Feature*:  Crea Evento(concerto) da Artista -> Success  
                L'utente crea un evento selezionando artista, data e luogo. Se per l'artista selezionato ha lo status di artista può scegliere come tipo di evento concerto, il tipo di fan a cui mostrare questo evento, il costo di ingresso e il numero di posti.

### 10
*Feature*:  Crea Evento(concerto) da Entusiast -> Fail  
                L'utente crea un evento selezionando artista, data, luogo, tipo di evento concerto. Se per lo status di artista risulta non avere autori, non deve essere in grado di selezionare il tipo di evento fallendo. Se ha lo status di artista ma non per quell'artista non dovrebbe permettere di cambiare il tipo di evento fallendo.

### 11
*Feature*:  Crea Evento raduno (Entusiast)  
                L'utente autorizzato seleziona il tasto crea evento, seleziona (se ha lo status di artista non vuoto) la voce raduno, seleziona un autore (il quale rientra nella lista dello stato entusiast), seleziona la data, il nome del posto dove si effettuerà l'evento, il numero di posti massimo, la mail su cui ricevere le iscrizioni, riempe la descrizione dell'evento. 

### 12
*Feature*:  Crea Evento raduno (Artista)  
                L'utente autorizzato seleziona il tasto crea evento, seleziona la voce raduno, seleziona l'autore per cui ha lo status di artista (se stesso), seleziona la data, il nome del posto dove si effettuerà l'evento, il numero di posti massimo, la mail su cui ricevere le iscrizioni, riempe la descrizione dell'evento, indica se l'evento ha un costo e se sì indica a quanto ammonta.

### 13
*Feature*:  Partecipa ad evento per Fan da Fan -> successo  
                L'utente esegue il login, accede alla pagina principale, seleziona l'evento di un artista di cui è fan, partecipa all'evento e lascia la mail sulla quale ricevere ulteriori aggiornamenti.

### 14
*Feature*:  Partecipa ad evento per Fan da Entusiast -> successo  
                L'utente esegue il login, accede alla pagina principale, seleziona l'evento di un artista di cui è entusiast, partecipa all'evento e lascia la mail sulla quale ricevere ulteriori aggiornamenti.

### 15
*Feature*:  Partecipa ad evento per Entusiast da Entusiast -> successo  
                L'utente esegue il login, accede alla pagina principale, seleziona l'evento di un artista di cui è entusiast, partecipa all'evento e lascia la mail sulla quale ricevere ulteriori aggiornamenti.

### 16
*Feature*:  Partecipa ad evento per Entusiast da Fan -> fail-1  
                L'utente esegue il login, accede alla pagina principale, cerca l'evento esclusivo di un artista di cui è fan, fallisce nel tentativo di ricerca.

### 17
*Feature*:  Partecipa ad evento per Entusiast da Fan -> fail-2  
                L'utente esegue il login, accede alla pagina principale, inserisce il link dell'evento esclusivo di un artista di cui è fan, riceve una schermata di errore che invita al ricaricamento e porta alla schermata principale.

### 18
*Feature*:  Partecipa ad evento per Entusiast da Fan -> fail-3  
                L'utente esegue il login, accede alla pagina principale, manda una post per mandare la mail di partecipazione dell'evento esclusivo di un artista di cui è fan, riceve una schermata di errore che invita al ricaricamento e porta alla schermata principale.

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

### 31
*Feature*:  x
                x

### 32
*Feature*:  x
                x

### 33
*Feature*:  x
                x

### 34
*Feature*:  x
                x

### 35
*Feature*:  x
                x

### 36
*Feature*:  x
                x

### 37
*Feature*:  x
                x

### 38
*Feature*:  x
                x

### 39
*Feature*:  x
                x

### 40
*Feature*:  x
                x

### 41
*Feature*:  x
                x

### 42
*Feature*:  x
                x

### 43
*Feature*:  x
                x

### 44
*Feature*:  x
                x

### 45
*Feature*:  x
                x
