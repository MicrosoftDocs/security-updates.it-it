---
TOCTitle: Sito Web Amministrazione RMS
Title: Sito Web Amministrazione RMS
ms:assetid: 'f003c1d9-9a17-4e50-9e1e-5d67677552a0'
ms:contentKeyID: 18824845
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747796(v=WS.10)'
---

Sito Web Amministrazione RMS
============================

Ogni cluster principale e ogni cluster licenze ospita un sito Web Amministrazione da cui è possibile gestire RMS. Questo sito Web è disponibile solamente sul server RMS amministrato, oppure attraverso una connessione da desktop remoto.

In questo argomento vengono descritte le funzionalità del sito Web Amministrazione. Le istruzioni per l'uso del sito Web per l'amministrazione di RMS sono contenute in "Procedure RMS" e "Gestione di RMS" in "Utilizzo di RMS", in questa documentazione.

**Nota   **La configurazione dei cluster è un'operazione globale. È possibile gestire la configurazione di un cluster dal sito Web Amministrazione di qualsiasi server incluso nel cluster.

Aprire la pagina **Amministrazione globale** per eseguire le operazioni seguenti:

-   Effettuare il provisioning di RMS in un sito Web.
-   Eseguire il provisioning di un server e aggiungerlo a un cluster.
-   Rimuovere RMS da un sito Web.
-   Accedere alle pagine di amministrazione del cluster.

Aprire la pagina **Amministrazione** di un cluster per eseguire le seguenti operazioni:

-   **Visualizzare informazioni sul cluster.**È possibile visualizzare le informazioni relative a un cluster, ad esempio l'URL di installazione, l'URL del server, il nome del certificato, il server e il nome del database di configurazione e la data di scadenza del certificato.
-   **Registrare o rinnovare il certificato concessore di licenze server.**È possibile registrare o rinnovare il certificato concessore di licenze server di un cluster.
-   **Definire i criteri di trust.** Questo collegamento permette di aprire la pagina Web Criteri di trust, da cui è possibile aggiungere o rimuovere i domini utente trusted e i domini di pubblicazione trusted. Aggiungere o rimuovere utenti dall'elenco di esclusione presente in un dominio utenti trusted. Esportare il certificato concessore di licenze server in un file per consentirne l'importazione in un'altra installazione di RMS.
-   **Configurare i modelli di criteri per i diritti.** Questo collegamento permette di aprire la pagina Web Modello di criteri per i diritti, da cui è possibile creare e modificare i modelli di criteri per i diritti aziendali.
-   **Configurare la registrazione delle attività.** Questo collegamento permette di aprire la pagina Web Impostazioni registrazione attività, da cui è possibile attivare e disattivare la registrazione delle attività, oltre a visualizzare il server e il database di registrazione delle attività.
-   **Specificare l'URL del cluster Extranet.**Questo collegamento permette di aprire la pagina Web Impostazioni URL del cluster Extranet, da cui è possibile specificare l'URL da impiegare per accedere dalla Extranet ai servizi di certificazione del cluster principale.
-   **Specificare le impostazioni del proxy RMS.** Questo collegamento permette di aprire la pagina Web Impostazioni proxy RMS, da cui è possibile specificare l'indirizzo del server proxy, il tipo di autenticazione e il nome utente da utilizzare quando il server RMS deve connettersi a Internet attraverso un server proxy.
-   **Verificare il numero dei certificati per account con diritti distribuiti.**Questo collegamento consente di aprire la pagina Web di verifica dei certificati per account con diritti, da cui è possibile rilevare il numero di certificati per account con diritti distribuiti dal cluster principale, valore utile per avere una stima del numero di licenze di accesso client necessarie.
-   **Gestire le impostazioni di protezione.** Questo collegamento permette di aprire la pagina Web Impostazioni di protezione, da cui è possibile aggiungere o rimuovere i membri di un gruppo di utenti con privilegi avanzati che dispongono di controllo completo su tutto il contenuto concesso in licenza, oltre ad azzerare le password delle chiavi private.
-   **Visualizzare e configurare le impostazioni per i certificati con account.** Questo collegamento permette di aprire la pagina Web Impostazioni certificazione, da cui è possibile specificare la durata della validità dei certificati, oltre a specificare un contatto amministrativo.
-   **Attivare i criteri di esclusione.** Questo collegamento permette di aprire la pagina Web Criteri di esclusione, da cui è possibile abilitare i criteri di esclusione basati sulle versioni di un archivio protetto, versioni di Windows, certificati per account e applicazioni.
-   **Registrare il punto di connessione del servizio** Questo collegamento permette di aprire la pagina Web Punto di connessione del servizio, da cui è possibile eseguire e annullare la registrazione del punto di connessione del servizio di un cluster.

Gli amministratori possono eseguire altre operazioni, tra cui il monitoraggio di eventi e la gestione di Active Directory, Internet Information Services (IIS) e SQL Server, tramite la console MMC (Microsoft Management Console).
