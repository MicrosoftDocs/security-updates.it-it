---
TOCTitle: Rilevamento del servizio di registrazione secondaria
Title: Rilevamento del servizio di registrazione secondaria
ms:assetid: 'b159953a-af38-4a9e-8c87-1aff5fb4e366'
ms:contentKeyID: 18824743
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747641(v=WS.10)'
---

Rilevamento del servizio di registrazione secondaria
====================================================

Il singolo server licenze, o il primo server licenze di un cluster, deve inviare una richiesta di registrazione secondaria al server di certificazione principale di RMS, ottenendo un certificato concessore di licenze server. Per fare ciò, il server licenze ottiene l'URL del servizio di registrazione secondaria di certificazione principale, come indicato di seguito.

Durante il provisioning di un server licenze, il programma di installazione di RMS invia una query ad Active Directory, rilevando il punto di connessione del servizio del cluster di certificazione principale. RMS impiega l'URL memorizzato nel punto di connessione del servizio per localizzare il cluster di certificazione principale, quindi invia la richiesta per un certificato concessore di licenze server dal servizio di registrazione secondaria del server di certificazione principale.

Per inviare una richiesta di servizio di registrazione secondaria, per prima cosa il server licenze richiama da Active Directory l'URL della directory virtuale Certification del server di certificazione principale, dove si trova il servizio di registrazione secondaria. Quindi, vi aggiunge il percorso del servizio di registrazione secondaria.

Ad esempio, l'URL della directory virtuale Certification del server di certificazione principale è memorizzato in Active Directory nel formato seguente:

http://*nome\_server*/\_wmcs/Certification

Quando il server licenze richiede la registrazione secondaria, aggiunge all'URL il nome del file del servizio, come indicato di seguito:

http://nome\_server/\_wmcs/Certification/SubEnrollService.asmx

| ![](images/Cc747641.note(WS.10).gif)Nota                                                                                |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| Qualora SSL sia stato abilitato sul server RMS, gli URL mostrati appariranno con l'indicazione dell'utilizzo del protocollo di connessione https://. |
