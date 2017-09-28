---
TOCTitle: Servizio di rimozione delle autorizzazioni RMS
Title: Servizio di rimozione delle autorizzazioni RMS
ms:assetid: '97677e3b-bc83-47ec-b6db-d326cd94566c'
ms:contentKeyID: 18824704
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747695(v=WS.10)'
---

Servizio di rimozione delle autorizzazioni RMS
==============================================

Il servizio Rimozione autorizzazioni è un servizio Web personalizzato che viene installato dal programma di installazione di RMS. Viene eseguito sia sul cluster principale che sui cluster licenze. Quando si attiva questo servizio, tutti gli altri servizi Web di RMS nel server vengono disattivati.

Questo servizio decrittografa la chiave del contenuto che si trova nella licenza di pubblicazione del contenuto protetto con RMS e la fornisce al client come risposta alla richiesta di licenza. Ciò consente di salvare il contenuto senza la protezione RMS. Il servizio di rimozione delle autorizzazioni registra tutte le richieste client pervenute e le invia al servizio listener per la registrazione attività affinché vengano inserite nel database di registrazione attività.

È possibile attivare il servizio di rimozione delle autorizzazioni dalla pagina **Impostazioni protezione** del sito Web Amministrazione. Dopo avere attivato questo servizio, non è possibile ripristinare una configurazione RMS standard nel server.

Una volta abilitato il servizio, si dovrebbe impostare l'elenco DACL del file decommission.asmx in modo da permettere l'accesso agli utenti appartenenti all'azienda che hanno utilizzato il server per concedere in licenza contenuti, quindi aggiungere il gruppo di servizi RMS all'elenco DACL con autorizzazioni in lettura ed esecuzione, in modo da abilitare la gestione dell'operazione da parte di RMS. Dopo la rimozione della protezione per tutto il contenuto pubblicato da questo server, creare una copia di backup delle informazioni della chiave privata e quindi rimuovere RMS dal server.

L'elenco di controllo di accesso predefinito su questo servizio è illustrato nella seguente tabella:

###  

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Utente o gruppo</th>
<th>Autorizzazione predefinita</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>SISTEMA</p></td>
<td style="border:1px solid black;"><p>Controllo completo</p></td>
</tr>
</tbody>
</table>
