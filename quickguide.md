# Scrivere in markdown

Leggere questo file da github, permette di comprenderne la visualizzazione

Il markdown (.md) è un linguaggio semplice di formattazione (tipo html ma meno spastico e patinato).  
Si basa su più standard, a noi interessa solo quello di git, ci sono delle funzioni aggiuntive per personalizzare ulteriormente, spesso ricalcano la scrittura html.  
Le funzioni principali sono:  
- l'uso del doppio spazio per mandare a capo il testo (altrimenti appare in una unica linea)  
- l'uso del cancelletto per la creazione di titoli e sottotitoli in funzione di quanti se ne utilizzano (seguiti da uno spazio)  
- l'uso indistinto di asterischi e trattini bassi per indicare un tratto in italico o grassetto (\*così\* e non\* così \*)  
- l'uso di un doppio invio per dividere un paragrafo  
- l'uso di un asterico o un trattino all'inizio della riga seguito da uno spazio per fare una lista puntata  
- l'uso di un qualsiasi numero seguito da punto e spazio per una lista numerata (il primo numero da il seguito, attenzione!)  
- l'uso di parentesi quadre e tonde per la creazione di link (il valore nelle parentesi tonde) e del testo (il valore nelle parentesi quadre) \[\]()  

Per ulteriori delucidazioni a riguardo, per sintassi più aggraziate oltre il necessario invito a motori di ricerca o a sistemi di inteliggenza artificiali (**cum grano salis**)

# Utilizzare git

per avere una vita facile con git e github consiglio di creare nella propria macchina virtuale (se vi piace soffrire potete utilizzare la BIAR) nel file _~/.bashrc_ degli alias (nulla vi vieta di scriverli manualmente di volta in volta).  
> `alias git-status="git status -sb"`  
> `alias git-log="git log --all --decorate --graph"`  

ove necessario o desiderato potete aggiungere a `git-log` la voce `--oneline` per avere l'hash del commit interessato in formato corto (sconsiglio se volete leggere la descrizione del commit, consiglio se volete vedere la differenza rispetto al precedente).

un comando importante da fare è `git fetch` e non `git pull` se non volete ritrovarvi a fare dei merge non necessari all'improvviso.  
ulteriore buona pratica è *NON TOCCARE IL MASTER* senza consultare gli altri.  
per lavorare basta fare un `git branch "new_branch"` per creare un nuovo branch, utilizzando `git branch -la` si avrà la lista di tutti i branch esistenti.  
per muoversi da un branch all'altro c'è il comando `git checkout new_head` dove new\_head rappresenta il branch su cui spostarsi.

Per capire chi ha fatto cosa negli ultimi commit (tendenzialmente da utilizzare sul branch master/main) si utilizza (locati nel branch master) il comando `git diff commit_hash` dove con "commit\_hash" si intendono i primi 7 caratteri del commit (ottenibili con il comando `git log --oneline --graph --decorate --all`).
Da qui parte una visione come con less (quindi vi potete muovere su e giù usando le freccette o 'j' e 'k') che mostra in rosso le parti vecchie, in verde le parti nuove (modifica o riscrittura o cancellazione o aggiunta ex novo) chiamando prima il nome del file e poi il test (se modificato).

Ove necessario per cazziare qualcuno c'è il comando `git blame`, personalmente non so bene come funzioni con i suoi flag chiave, però so che indicando uno snippet di codice permette di cazziare chi ha scritto quella roba o mostrare ogni autore cosa ha scritto.

Per rendervi la vita più semplice vi consiglio di modificare sempre sul file _~/.bashrc_ il valore di **PS1** che corrisponde al testo che la bash vi mostra prima di ogni input a terminale (quindi il nome del vostro utente nel computer. Qui vi consiglio di aggiungere una chiamata a funzione che scriverò sotto lasciando lo snippet di ciò che ho impostato io in modo da avere una visione colorata e di rapida consultazione che mi mostra il branch corrente (se sono su una cartella che presenta file .git ovviamente, altrimenti non mostra nulla). Anche non modificare la dicitura "PS1" precedente ma avere una ridefinizione successiva porta al risultato desiderato, quindi potete semplicemente schiaffare lo snippet sul file _~/.bashrc_ in coda e ottenere il risultato desiderato.

```
parse_git_branch(){
	git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
}

RED="\[\e[38;2;255;0;0m\]"
BLUE="\[\e[38;2;0;127;255m\]"
GREEN="\[\e[38;2;0;255;0m\]"
RESET="\[\e[0m\]"

PS1="${BLUE}\u${RESET}@\H: ${GREEN}\w${RED} \$(parse_git_branch)${RESET}\$ "

```
