---
TOCTitle: 'Appendice B: Impostazioni principali da considerare'
Title: 'Appendice B: Impostazioni principali da considerare'
ms:assetid: '22b7ca9a-8713-4a2a-8255-3666a82da9ee'
ms:contentKeyID: 20213198
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc163102(v=TechNet.10)'
---

Guida per la protezione di Windows Server 2003
==============================================

### Appendice B: Impostazioni principali da considerare

Sebbene questa guida descriva molte contromisure e impostazioni di protezione, è importante capire che una parte di esse sono particolarmente importanti. Questa appendice evidenzia tali impostazioni; per una spiegazione su ciò che l'impostazione fa e perché è importante, è possibile far riferimento al capitolo pertinente.

Decidere quali impostazioni includere in questo elenco potrebbe dare luogo a un lungo dibattito. Questo argomento è stato discusso in modo approfondito da un gruppo di esperti di protezione all'interno di Microsoft. Si potrebbe pensare che alcune impostazioni manchino o che alcune delle impostazioni siano elencate a sproposito. Poiché ogni organizzazione ha un ambiente distinto con requisiti aziendali unici, è possibile che si abbiano opinioni diverse a questo riguardo. Tuttavia, questo elenco potrebbe aiutare a dare priorità ai compiti relativi alla protezione avanzata di computer che utilizzano Microsoft Windows.

Contromisure importanti, che non siano impostazioni di protezione, sono:

-   Mantenere aggiornati i computer relativamente a cervice pack e aggiornamenti rapidi con strumenti automatici per il controllo e la distribuzione.

-   Installare e configurare il software firewall distribuito o i criteri IPsec dell'organizzazione.

-   Distribuire e mantenere il software antivirus.

-   Distribuire e mantenere il software antispyware sui computer utilizzati per navigare sui siti Web.

-   Utilizzare un account non amministrativo per gli incarichi giornalieri. Utilizzare solo un account con privilegi di amministratore per eseguire incarichi che richiedono privilegi elevati.

Le impostazioni di protezione principali disponibili con Microsoft Windows sono le seguenti:

-   Criterio password, descritto nel Capitolo 3, "Criteri di Dominio".

    -   Imponi cronologia delle password

    -   Validità massima password

    -   Lunghezza minima password

    -   Le password devono essere conformi ai requisiti di complessità

    -   Consenti archiviazione password con crittografia reversibile per tutti gli utenti del dominio

-   Diritti utente, discussi nel Capitolo 4, "Criterio di base dei server membro".

    -   Accesso al computer dalla rete

    -   Agisci come parte del sistema operativo

    -   Consenti accesso locale

    -   Consenti accesso tramite Servizi terminal

-   I diritti utente, discussi nel Capitolo 4, "Il Criterio di base del server membro."

    -   Account: limitare l'uso locale di account con password vuote all'accesso alla console

    -   Controller di dominio: aggiungi crittografia o firma digitale ai dati del canale protetto (sempre)

    -   Controller di dominio: aggiungi crittografia digitale ai dati del canale protetto (quando possibile)

    -   Controller di dominio: aggiungi crittografia digitale ai dati del canale protetto (quando possibile)

    -   Membro di dominio: richiesta chiave di sessione avanzata (Windows* *2000 o versioni successive)

    -   Accesso di rete: consenti conversione anonima SID/NOME

    -   Accesso di rete: non consentire l'enumerazione anonima degli account SAM

    -   Accesso di rete: non consentire l'enumerazione account e condivisioni SAM

    -   Accesso di rete: consenti l'accesso libero agli utenti anonimi

    -   Accesso di rete: percorsi del Registro di sistema ai quali è possibile accedere in modo remoto

    -   Accesso di rete: limita accesso anonimo a named pipe e condivisioni

    -   Accesso di rete: condivisioni alle quali è possibile accedere in modo anonimo

    -   Accesso di rete: modello di condivisione e protezione per gli account locali

    -   Protezione di rete: non memorizzare il valore hash di LAN Manager al prossimo cambio di password

    -   Protezione di rete: livello di autenticazione di LAN Manager

-   Impostazioni addizionali di registro, discussi nel Capitolo 4, "Criterio di base del server membro".

    -   Modalità sicura di ricerca DLL

**Download**

[Utilizzo della Guida per la protezione di Windows Server 2003](http://go.microsoft.com/fwlink/?linkid=14846)

**Notifiche di aggiornamento**

[Iscriversi per ottenere aggiornamenti e nuove versioni](http://go.microsoft.com/fwlink/?linkid=54982)

**Commenti e suggerimenti**

[Inviare commenti o suggerimenti](mailto:%20secwish@microsoft.com?subject=guida%20per%20la%20protezione%20di%20windows%20server%202003)

[](#mainsection)[Inizio pagina](#mainsection)
