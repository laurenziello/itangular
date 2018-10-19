# Iniziamo

## Node
Per iniziare con Angular, hai bisogno di installare Node,js. Ci sono diversi modi di installare Node.js, quindi controlla il sito di Node.js per informazioni a riguardo.

**Assicurati di installare Node 8.9.0 o versioni superiore**

Il gestore dei pacchetti Node meglio conosciuto come *npm* è installato come parte di Node.js. Per controllare se *npm* fa parte del nostro ambiente di sviluppo, possiamo aprire un terminale e digitare:

```markdown
$ npm -v
```

Se il numero di versione non viene stampato e ricevi un errore, controlla di aver scaricato il pacchetto di installazione di Node.js che include npm.

## TypeScript
Dopo aver sistemato Node.js, il tuo prossimo passaggio sarà installare TypeScript. Assicurati di installare almeno la versione 2.1 o versioni successive. Per installarlo devi eseguire il seguente comando *npm*:

```markdown
$ npm install -g typescript
```

## Angular CLI
Angular fornisce un utility che permette agli utenti di creare e gestire progetti da linea di comando. Automatizza tasks come creare progetti, aggiungere nuovi controllers, etc. 

Per installare Angular CLI basta eseguire il seguente comando:

```markdown
$ npm install -g @angular/cli
```
Una volta installata sarai capace di eseguirlo da linea di comando usando i comandi *ng*. 
Per controllare che tutto sia installato correttamente puoi eseguire il comando:

```markdown
$ ng --version
```
Se sei un'utente OSX o Linux, potresti ricevere il messaggio:

```markdown
Could not start watchman: falling back to NodeWatcher for file system events.
```
Qeusto significa che non è stato installato il tool watchman. Questo tool aiuta l'Angular CLI quando ha bisogno di monitorare i cambiamenti sui file sul filesystem.
Su OSX è raccomandato installarlo usando Homebrew con il seguente comando:

```markdown
$ brew isntall watchman
```
Se sei un utente Linux sulla pagina https://ember-cli.com/user-guide/#watchman troverai più informazioni su come installare watchman.

Se sei un'utente Windows non avrai bisogno di installare nient'altro perchè Angular CLI userà il watcher nativo di Node.js.

Se sei curioso riguardo tutto quello che Angular CLI può fare puoi eseguire questo comando

```markdown
$ ng --help
```
Non preoccuparti di capire tutte le opzioni disponibili, copriremo i più importanti in questo capitolo.
Ora che abbiamo Angular CLI e le sue dipendenze installate, andiamo ad usare questo tool per creare la nostra pirma applicazione.

## Progetto di esempio
Apri un terminale e esegui il comando *ng new* per creare un nuovo progetto
```markdown
$ ng new angular-hello-world
```
Vedrai una seire di comandi di creazione di file che variano in base alla versione di Angular CLI usata.
Andiamo nella cartella *angular-hello-world* e controlliamo cosa è stato creato
```markdown
|-- README.md                   // un utile README
|-- angular.json                // file condifurazione angular-cli
|-- e2e/                        // end-to-end
|-- node_modules/               // dipendenze installate
|-- package-lock.json           // npm dipendenze file bloccato
|-- package.json                // configurazione npm
|-- src/                        // codice della nostra applicazione
|-- tscondig.json               // configurazione typescript
|-- tslint.json                 // configurazione lint
```
Per adesso siamo interessati al contenuto della cartella *src*, dove ci sarà il codice della nostra applicazione. 
Aprendo il file *index.html* notiamo il classico codice HTML tranne che per un tag *app-root*.
*app-root* è un componente definito dalla nostra applicazione Angular, infatti in Angular possiamo definiere dei tag personalizzati e dargli funzionalità personalizzate. Il tag *app-root* sarà il nostro punto di ingresso per la nostra applicazione nella pagina. 

## Scriviamo il codice dell'applicazione

Prima di qualsiasi modifica carichiamo la nostra app dall'applicazione generale nel browser. L'Angular CLI ha un HTTP server integrato che possiamo usare per eseguire la nostra app. Per usarlo, ritorniamo al terminale, posizioniamoci nella cartella radice della nostra applicazione.

```markdown
$ cd angular-hello-world
$ ng serve
** NG Live Development Server is running on http://localhost:4200. **
// ...
// a bunch of other messages
// ...
Compiled successfully.
```