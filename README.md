# proj

Progetto Laravel Global Family Service

## INSTALLAZIONE LARAVEL
Deve essere attivo il servizio docker


CLONE REPOSITORY

Accesso in cartella
> cd wefox/service1
> cd wefox/service2

Compilazione macchina docker (deve essere attiva per vedere la pagina)
> docker-compose up --build per lanciare i 2 progetti 1 sulla porta 8000 e l'altro sulla 8001 - configurazione tramite nginx

> l'obiettivo della chiamata api è quello di passare un nome e un cognome di un utente e salvarlo nel db. Il payload 2 non passerà il cognome e perciò restituirà errore, perchè campo obbligatorio.

> è stata creata una migrazione sul servizio 2 per creare la tabella user

> SERVICE 1 - PAYLOAD 1
> attraverso la chiamata /api/payload1 IN GET il servizio 1 chiamerà il servizio 2(TRAMITE HTTP IN POST)  e riceverà un 200 rispondendo con un messaggio di successo 
> il servizio 2 salvera sul db il payload ottenuto

> SERVICE 1 - PAYLOAD 2
> attraverso la chiamata /api/payload2 IN GET il servizio 1 chiamerà il servizio 2(TRAMITE HTTP IN POST) e riceverà un errore di validazione da stampare a video
> il servizio 2 non salvera nessun dato sul db

> Le chiamate sono state effettuate tramite Guzzle

## CONNESSIONE 2 CONTAINER
> per connettere i due db è stato inserito nel docker del servizio 2 la network con il driver bridge, mentre nel servizio 1 è stato richiamata la network del servizio 1
 