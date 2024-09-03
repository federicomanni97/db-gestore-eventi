# Argomenti da ripassare

- Database (Tabelle, Relazioni e Data Types)
- Diagramma ER
- PhpMyAdmin (Eseguire query e Importare un database)
- Query SQL (SELECT,  ALIAS, WHERE, ORDER BY, GROUP BY,  SUM, JOIN, HAVING)

# Consegna

📚 **DB Gestore Eventi**
nome repo: ****db-gestore-eventi

****Il nostro cliente vuole creare una  piattaforma per la gestione degli eventi che organizza.

Il gestionale permetterà agli `utenti` di gestire `eventi`  e vedere le `prenotazioni` a loro collegati. 
Ci saranno 4 tipi di utenti, con `ruoli` diversi: 
- chi può amministrate tutti gli utenti
- chi può accedere al gestionale per creare o modificare eventi
- chi può solo accedere al gestionale senza la possibilità di modifica dei dati
- chi non ha accesso al gestionale e può solo prenotarsi agli eventi

Ogni evento potrà avere più `tag`  per definirne la tipologia.
Il cliente organizza eventi solo in una serie di `location` esclusive che tramite il gestionale vuole tenere sempre sott’occhio, per capire quali eventi si terranno in ognuna di esse.

**🎯 Obiettivo**
Progettare il database per la piattaforma in questione, creando il diagramma ER  e poi svolgendo le query fornite.

1️⃣ **Milestone 1 (Diagramma ER)**
Create il diagramma ER. Pensiamo a quali entità (tabelle) creare per il nostro database, definiamo le colonne e i tipi di dato per ognuna di esse e infine stabiliamo le relazioni.

Esportate quindi il diagramma come immagine e caricatelo nella repo.

2️⃣ **Milestone 2 (Query SQL)**
Dopo aver creato un nuovo database su phpMyAdmin e aver importato lo schema fornito (`db_gestionale_eventi.sql`), svolgete le query che trovate nel file `query.pdf`
In ogni query è indicato il numero di risultati previsti, per permettervi di verificare che sia corretta.

Dopo aver testato le vostre query con phpMyAdmin, riportatele in un file txt e caricatelo nella repo.

Buon kata! 🥷
****

# Suggerimenti

Diagramma ER

- La struttura del database serve a definire come verranno salvati i dati dell’applicazione, non a definire la logica di funzionamento di essa. 
Non cadete quindi nel tranello di mettere in conto quelle le funzionalità che implicano solo modifiche lato codice e non condizionano come vengono salvati i dati. 
Concentratevi sul creare una struttura dati che rappresenti al meglio le entità e le relazioni tra loro.
- Se riscontrate difficoltà nel definire le relazioni, provate a ripeterle ad alta voce usando una formula come questa:
Pensiamo a una biblioteca e alle entità “autore” e “libro”:
*“Un autore **ha più** libri, un libro **appartiene a più** autori”*
Quindi la relazione tra autore e libro sarà **molti a molti**
    
    Un altro esempio, con la tabella dei prestiti e la tabella degli tesserati di una biblioteca:
    “Un tesserato **ha più** prestiti, un prestito **appartiene a un** solo tesserato”
    In questo caso quindi avremo una relazione **uno a molti**
    
- Scegliete bene i data types per le colonne delle varie tabelle. 
Un campo ha bisogno di data e ora? Allora dovrò assegnare un data type che mi permette di salvare sia data che ora.
Un campo rappresenta una durata in ore? Di primo impatto vi potrebbe venire in mente di utilizzare un numero intero, ma c’è un data type più adatto a salvare il tempo  .
Aiutatevi con le reference che vi abbiamo fornito [qui sotto](https://www.notion.so/DB-Gestore-Eventi-77bafdd913fd494b9d054600d1fe8644?pvs=21), per trovare il data type più adatto a ogni colonna.
- Pensate bene anche ai data types che userete per i campi della tabella dei ruoli. In consegna sono definiti chiaramente i ruoli disponibili, ad ogni utente ne sarà assegnato uno. 
Esiste un tipo che permette di inserire un valore stringa, scelto da una lista di possibili valori. Anche per questo, trovate qualche suggerimento nelle [reference](https://www.notion.so/DB-Gestore-Eventi-77bafdd913fd494b9d054600d1fe8644?pvs=21).

Query SQL

- In alcune query vi capiterà di dover filtrare dati aggregati. La clausola where non può essere usata in combinazione con le aggregate functions (sum, count, etc). In tal caso esiste un’altra clausola apposita.