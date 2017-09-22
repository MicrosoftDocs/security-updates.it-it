---
TOCTitle: Invio automatico di Internet Explorer 7
Title: Invio automatico di Internet Explorer 7
ms:assetid: '7a2b58bd-3b92-4669-b1df-f78e6d8d7cff'
ms:contentKeyID: 13180000
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Bb226738(v=MSDN.10)'
---

Invio automatico di Internet Explorer 7
=======================================

Al fine di garantire agli utenti maggiore protezione e aggiornamenti più tempestivi, Microsoft ha deciso di distribuire Internet Explorer 7 come aggiornamento a priorità alta tramite il servizio Aggiornamenti automatici e i siti Web Windows Update e Microsoft Update. Internet Explorer 7 sarà disponibile per gli utenti in possesso di Windows XP SP2, Windows XP 64-bit Edition e Windows Server 2003 SP1.

Nel presente comunicato vengono fornite informazioni generali relative al processo di distribuzione e vengono illustrate le opzioni a disposizione degli amministratori IT per impedire che Internet Explorer 7 venga distribuito nelle rispettive organizzazioni tramite Aggiornamenti automatici.

Gli utenti che desiderano impedire che Internet Explorer 7 venga distribuito automaticamente nelle rispettive organizzazioni devono adottare apposite misure di blocco entro le date indicate alla fine di questo comunicato. La distribuzione di Internet Explorer 7 tramite Aggiornamenti automatici avverrà lentamente e verrà completata nell'arco di diversi mesi. L’aggiornamento a Internet Explorer 7 potrà risultare disponibile in qualsiasi momento nei prossimi mesi. Microsoft aggiornerà successivamente il presente comunicato con ulteriori informazioni.

### Processo di distribuzione di Aggiornamenti automatici

Il processo di distribuzione automatica avviserà gli utenti della disponibilità dell'aggiornamento, consentendo loro di scegliere se installare o meno Internet Explorer 7. Il processo viene descritto di seguito, anche attraverso le immagini riportate in fondo a questa pagina.

Internet Explorer 7 verrà reso disponibile tramite Aggiornamenti automatici agli utenti che dispongono di account di amministratore locale. Gli utenti in possesso di tale requisito e quelli per i quali Aggiornamenti automatici è configurato per scaricare e installare automaticamente gli aggiornamenti riceveranno una notifica al termine del download di Internet Explorer 7 in modo da poterne confermare l’installazione. Il processo di notifica e installazione verrà avviato solo al momento dell'accesso al computer da parte di un utente in possesso di diritti di amministratore locale. Agli utenti che non dispongono di diritti di amministratore locale non verrà chiesto di installare l’aggiornamento e potranno continuare a utilizzare Internet Explorer 6.

Dopo aver fatto clic sul messaggio di notifica di Aggiornamenti automatici, verrà visualizzata una finestra nella quale vengono illustrate le funzionalità principali di Internet Explorer 7 e le tre opzioni disponibili, ovvero Installa, Non installare e Richiedi in seguito.

-   Se si sceglie "Installa": verrà avviato il processo di installazione. Internet Explorer 7 non verrà sostituito al browser scelto dall’utente come predefinito e ne manterrà le impostazioni relative alla pagina iniziale e ai Preferiti, nonché le impostazioni di ricerca e le barre degli strumenti compatibili. Al primo avvio di Internet Explorer 7, all'utente verranno illustrate tutte le nuove funzionalità e le modifiche apportate.

-   Se si sceglie "Non installare": non verrà più richiesto all'utente di eseguire l’installazione; tuttavia, gli utenti in possesso di diritti di amministratore locale potranno installare Internet Explorer 7 in qualsiasi momento come aggiornamento facoltativo dai siti Web Windows Update e Microsoft Update o dall’Area download Microsoft.

-   Se si sceglie "Richiedi in seguito": l'installazione non verrà avviata e il servizio Aggiornamenti automatici inizierà a visualizzare notifiche relative alla disponibilità dell'aggiornamento entro le successive 24 ore con le consuete modalità.

Internet Explorer 7 sostituirà Internet Explorer 6 nel computer dell’utente. Tuttavia, gli utenti possono tornare a utilizzare Internet Explorer 6 disintallando Internet Explorer 7 mediante l'utilità Installazione applicazioni nel Pannello di controllo di Windows. **Nota:** Se un utente ha installato Internet Explorer 7 e successivamente lo ha rimosso, Aggiornamenti automatici tornerà a proporre l’installazione di Internet Explorer 7 utilizzando il processo descritto sopra, al fine di mantenere il computer sempre aggiornato. In questo caso, l’utente dovrà semplicemente selezionare l’opzione “non installare” nella finestra iniziale. Aggiornamenti automatici non proporrà più l’installazione di Internet Explorer 7.

[](#mainsection)[Inizio pagina](#mainsection)

### Opzioni per bloccare la distribuzione automatica

Microsoft consiglia alle organizzazioni che utilizzano Aggiornamenti automatici nei propri ambienti e che desiderano impedire agli utenti di ricevere automaticamente Internet Explorer 7 di eseguire una o più delle seguenti operazioni:

1.  ***Scaricare e distribuire il Blocker Toolkit (toolkit di blocco) per Internet Explorer 7.*** Il Blocker Toolkit (privo di scadenza) può essere scaricato [dall’Area download Microsoft](http://go.microsoft.com/fwlink/?linkid=65788) ecomprende sia un modello Criteri di gruppo sia uno script che imposta una chiave del Registro di sistema per impedire ad Aggiornamenti automatici e ai siti Web Windows Update e Microsoft Update di proporre Internet Explorer 7 come aggiornamento a priorità alta. Nota: il Blocker Toolkit non impedirà agli utenti in possesso di autorizzazioni di amministratore locale di installare manualmente Internet Explorer 7 attraverso, ad esempio, un supporto esterno o dall’Area download Microsoft. È inoltre possibile consultare la sezione [Blocker Toolkit: Domande frequenti](http://www.microsoft.com/technet/updatemanagement/windowsupdate/ie7blockertoolfaq.mspx) (in inglese)*.*

2.  ***Distribuire una soluzione per la gestione degli aggiornamenti*** che consenta un controllo completo degli aggiornamenti distribuiti ai computer della rete. Microsoft mette a disposizione il prodotto gratuito [Windows Server Update Services](http://www.microsoft.com/windowsserversystem/updateservices/default.mspx) (WSUS) e i più avanzati prodotti per la gestione degli aggiornamenti di [Systems Management Server 2003](http://www.microsoft.com/italy/server/systemcenter/default.mspx) (SMS). È consigliabile che gli amministratori IT che utilizzano una soluzione per la gestione degli aggiornamenti si avvalgano delle funzionalità standard del prodotto in uso, in alternativa al Blocker Toolkit, per gestire la distribuzione di Internet Explorer 7. In questo comunicato vengono fornite informazioni specifiche per gli utenti di WSUS e SMS.

3.  ***Impedire agli utenti di accedere al computer in qualità di amministratori locali.*** L’aggiornamento non verrà proposto agli utenti che non dispongono di diritti di amministratore locale, ai quali può inoltre essere impedito di installare manualmente Internet Explorer 7 (o qualsiasi altra applicazione). Per ulteriori informazioni sulla gestione degli account utente [fare clic qui](http://www.microsoft.com/resources/documentation/windows/xp/all/proddocs/en-us/windows_security_default_settings.mspx?mfr=true). (in inglese)

4.  ***Richiedere agli utenti di rifiutare Internet Explorer 7 quando Aggiornamenti automatici avvisa che l'aggiornamento è disponibile per l'installazione.*** Se le opzioni descritte sopra non sono applicabili, è possibile richiedere agli utenti aziendali di scegliere l’opzione "Non installare" dalla finestra iniziale di Internet Explorer 7. Gli utenti non dovranno eseguire nessuna operazione particolare per ricevere la notifica. Tutti gli utenti potranno rifiutare l’installazione.

Per ulteriori informazioni su Internet Explorer 7, tra cui un toolkit per la preparazione, informazioni tecniche, un riepilogo dettagliato delle funzionalità e il download di Internet Explorer 7 Beta 3, visitare la [pagina Web relativa al prodotto](http://www.microsoft.com/italy/windows/ie/default.mspx).

[](#mainsection)[Inizio pagina](#mainsection)

### Schermate di esempio dell'invio di Aggiornamenti automatici

Di seguito vengono riportate schermate di esempio relative alla notifica:

[![](images/bb226738.screen1(it-it,MSDN.10).jpg)](https://technet.microsoft.com/it-it/bb226738.screen1_big(it-it,msdn.10).jpg)[![](images/bb226738.screen2(it-it,MSDN.10).jpg)](https://technet.microsoft.com/it-it/bb226738.screen2_big(it-it,msdn.10).jpg)![](images/bb226738.IE_Welcome-85p(it-it,MSDN.10).jpg)

Nota: la schermata visualizzata nell'ultima immagine può essere soggetta a modifiche

[](#mainsection)[Inizio pagina](#mainsection)

### Disponibilità di Internet Explorer 7

La distribuzione di Internet Explorer 7 attraverso gli aggiornamenti automatici comincerà subito dopo le date di rilascio indicate sotto. Gli utenti che desiderano impedire che Internet Explorer 7 venga distribuito automaticamente nelle rispettive organizzazioni devono adottare apposite misure di blocco entro le date indicate alla fine di questo comunicato.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p><strong>Lingua di IE7</strong></p></td>
<td style="border:1px solid black;"><p><strong>Date di rilascio di Internet Explorer 7</strong></p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Inglese</p></td>
<td style="border:1px solid black;"><p>1-ott-06</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Tedesco, francese, spagnolo, finlandese, brasiliano, portoghese, arabo, giapponese, italiano, olandese, russo, coreano, cinese semplificato e tradizionale, ebraico</p></td>
<td style="border:1px solid black;"><p>nov-06</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Svedese, danese, norvegese, polacco</p></td>
<td style="border:1px solid black;"><p>dic-07</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Turco, portoghese, ceco, ungherese, ELL</p></td>
<td style="border:1px solid black;"><p>gen-07</p></td>
</tr>  
</tbody>  
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Informazioni applicabili alle soluzioni per la gestione delle patch aziendali
  
Internet Explorer 7 verrà distribuito tramite Microsoft Systems Management Server e Microsoft Windows Server Update Services. Per ulteriori informazioni sulla distribuzione di Internet Explorer 7 tramite Windows Server Update Services [fare clic qui](http://technet2.microsoft.com/windowsserver/en/technologies/featured/wsus/default.mspx).
  
[](#mainsection)[Inizio pagina](#mainsection)
  
##### Link correlati
  
-   [Windows Update, Microsoft Update e Aggiornamenti automatici per professionisti IT (in inglese)](http://www.microsoft.com/technet/updatemanagement/windowsupdate/default.mspx#enc)  
-   [Internet Explorer 7](http://www.microsoft.com/italy/windows/ie/default.mspx)  
-   [Microsoft Application Compatibility Toolkit (ACT) V5.0](http://www.microsoft.com/italy/technet/windowsvista/appcompat/tools.mspx)  
-   [Download di Internet Explorer 7 Blocker Toolkit (in inglese)](http://www.microsoft.com/downloads/details.aspx?familyid=4516a6f7-5d44-482b-9dbd-869b4a90159c&displaylang=en)  
-   [Internet Explorer 7 Blocker Toolkit - Domande e risposte (in inglese)](http://www.microsoft.com/technet/updatemanagement/windowsupdate/ie7blockertoolfaq.mspx)  
-   [Internet Explorer Developer Center (in inglese)](http://msdn.microsoft.com/ie/)  
-   [Toolkit di preparazione per sviluppatori, tester ed esperti IT (in inglese)](http://www.microsoft.com/downloads/details.aspx?familyid=d13ee10d-2718-47f1-aa86-1e32d526383d&displaylang=en)
  
[](#mainsection)[Inizio pagina](#mainsection)
