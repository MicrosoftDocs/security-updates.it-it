---
TOCTitle: Cache Active Directory di RMS
Title: Cache Active Directory di RMS
ms:assetid: 'c721a2eb-2fe9-4346-b426-3cc169b97265'
ms:contentKeyID: 18824766
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747662(v=WS.10)'
---

Cache Active Directory di RMS
=============================

Ogni server o cluster di certificazione principale di RMS e ogni server licenze dispone di una cache Active Directory locale contenente i risultati delle query di appartenenza ai gruppi nel catalogo globale di Active Directory. Oltre alla cache presente su ciascun server, esiste una cache condivisa in ogni cluster, memorizzata nel database dei servizi di directory. Lo scopo di queste cache è ridurre il numero di query inviate al catalogo globale nonché il tempo di risposta per le richieste di licenza.

Quando un utente richiede una licenza d'uso, il server incaricato della risposta deve valutare se a tale utente sono stati assegnati i diritti necessari nella licenza di pubblicazione. Nel caso più semplice, il nome dell'utente che richiede una licenza è indicato in modo esplicito nella licenza di pubblicazione. In molti scenari, tuttavia, l'autore concede diritti a un gruppo anziché a singoli utenti.

Se il nome dell'utente richiedente non è indicato in modo esplicito nella licenza di pubblicazione, che assegna invece diritti a un gruppo, il server dovrà valutare le appartenenze ai gruppi dell'utente per verificare se l'utente è un membro di un gruppo a cui sono stati assegnati i diritti necessari. A tale scopo, il server invia una query LDAP al catalogo globale.

I server RMS memorizzano nella cache i risultati di tutte le query di appartenenza ai gruppi, sia nella cache locale di Active Directory cache, sia nel database dei servizi di directory. I server possono quindi ottenere informazioni sulle appartenenze ai gruppi da queste cache, il che consente una riduzione del numero di query da inviare al catalogo globale. Per impostazione predefinita, la query viene inviata al server più vicino; tuttavia, è possibile configurare la chiave del Registro di sistema GC specificando i server del catalogo globale cui inviare le query. Per ulteriori informazioni su questa impostazione, vedere "Modifica delle impostazioni del registro del pool di connessioni" in "Gestione di un server RMS" in questa documentazione.

Per valutare le appartenenze ai gruppi di un utente, il server controlla innanzitutto la propria cache per verificare se sono già state memorizzate informazioni sulle appartenenze ai gruppi dell'utente. In caso contrario, il server controllerà il database dei servizi di directory del cluster. Se in questo database non sono presenti informazioni sulle appartenenze ai gruppi, verrà inviata una query al catalogo globale.

Per gli utenti e i gruppi vengono memorizzati nella cache gli attributi di Active Directory seguenti:

-   mail
-   ProxyAddresses (solo indirizzi di posta elettronica SMTP)
-   objectSID
-   sidHistory
-   memberOf (GUID dei gruppi a cui l'utente o il gruppo appartiene)

Le voci nella cache di Active Directory locale includono un indicatore di data e ora. Le impostazioni del Registro di sistema specificano il periodo di validità delle voci presenti nella cache nonché il numero totale di voci che è possibile memorizzare nella cache. Queste impostazioni possono avere effetto sulle prestazioni dei server. Per ulteriori informazioni, vedere "Modifica delle impostazioni della cache di Active Directory" in "Gestione di un server RMS" in questa documentazione.
