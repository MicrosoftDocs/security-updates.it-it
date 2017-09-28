---
TOCTitle: 'Appendice D: Supporto WPA'
Title: 'Appendice D: Supporto WPA'
ms:assetid: '3626c7f6-7d4f-4d2a-947b-5ad05ad0efb4'
ms:contentKeyID: 21736324
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd772500(v=TechNet.10)'
---

Appendice D: Supporto WPA
=========================

Pubblicato: 10/11//2004 | Aggiornato: 24/11/2004

### Introduzione

La *soluzione Protezione delle reti LAN senza fili con Servizi Certificati* è compatibile con la protezione WPA (Wi -Fi Protected Access) per le reti LAN senza fili (WLAN). La compatibilità WPA è stata verificata in un laboratorio configurato in base alle procedure descritte in questa Guida. In questo documento vengono descritti i vari fattori da prendere in considerazione per la valutazione della modalità di utilizzo dello standard WPA con questa soluzione.

#### Cenni preliminari su WEP e WPA

Lo standard WEP (Wired Equivalent Privacy) è stato definito parte dello standard di rete senza fili 802.11 1999 IEEE (Institute for Electrical Engineers) in grado di fornire un livello di protezione equivalente a un sistema cablato. Lo standard WEP di base (o statico) fornisce la crittografia e il controllo dell'accesso per il traffico senza fili sulla base di una chiave già condivisa. È stato dimostrato che lo standard WEP è vulnerabile agli attacchi di un pirata informatico in grado di superare il controllo della protezione 802.11 nativa.

Il settore delle reti WLAN ha cercato di ovviare alle vulnerabilità dello standard WEP offrendo una soluzione di protezione avanzata denominata WPA. Lo standard WPA aumenta il livello di protezione dei dati e il controllo dell'accesso per i sistemi WLAN tramite una specifica di protezione interoperabile basata sugli standard. Il primo rilascio dello standard WPA è un sottoinsieme dello standard 802.11i che dovrebbe garantire la compatibilità in futuro. Lo standard 802.11i verrà rilasciato come WPA 2.0.

Al momento della pubblicazione, molti componenti hardware WLAN distribuiti in numerose organizzazioni non supportano lo standard WPA. È importante che la soluzione supporti sia questi componenti hardware che le nuove apparecchiature compatibili con lo standard WPA. Sebbene lo standard WPA fornisca un livello di protezione più elevato rispetto al WEP dinamico, quest'ultimo rappresenta una valida alternativa finché non viene eseguito l'aggiornamento di tutti i componenti hardware per il supporto dello standard WPA.

#### L'impatto dello standard WPA su questa soluzione

Lo standard WPA costituisce un'alternativa allo standard WEP nella soluzione *Protezione delle reti LAN senza fili* con *Servizi certificati*. La maggior parte dei componenti della soluzione non vengono influenzati dall'introduzione dello standard WPA. La compatibilità della soluzione con lo standard WPA è stata verificata configurando le apparecchiature di rete abilitate per WPA in maniera analoga alle attrezzature basate sullo standard WEP e apportando modifiche ai computer client.

Poiché lo standard WPA utilizza il protocollo 802.1X per l'autenticazione di rete, RADIUS (Remote Authentication Dial-In User Service), Servizi certificati Microsoft® e la maggior parte delle impostazioni del servizio directory Microsoft Active Directory® funzionano nel modo configurato. È possibile solo configurare le impostazioni WPA tramite i criteri di gruppo se si dispone almeno di un controller di dominio con Windows Server 2003 Service Pack 1 (in alternativa, è possibile configurare le impostazioni dei criteri di gruppo su un membro di dominio con Windows Server 2003 che non è un controller di dominio). Ulteriori informazioni su questo argomento sono disponibili più avanti in questa appendice. La seguente tabella elenca i fattori da prendere in considerazione quando si utilizza lo standard WPA con questa soluzione.

**Tabella D.1. Componenti della soluzione da prendere in considerazione**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Elemento della soluzione</th>
<th>Considerazione</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Driver hardware Microsoft Windows® XP</td>
<td style="border:1px solid black;">Contattare il fornitore delle schede di interfaccia di rete (NIC) per la valutazione delle schede da aggiornare per il supporto WPA e la disponibilità dei driver del client Windows XP.</td>
<td style="border:1px solid black;">Cercare i driver che hanno superato i test condotti da WHQL (Windows Hardware Quality Labs). Il supporto del driver per il servizio Configurazione automatica reti senza fili di Windows consente l'aggiornamento dinamico del firmware della scheda per il supporto dello standard WPA. Confermare il supporto del driver per il servizio WZC con il fornitore.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Configurazione del client Windows XP</td>
<td style="border:1px solid black;">È necessario modificare le impostazioni di configurazione del client. Questa soluzione è stata verificata selezionando lo standard WPA come metodo di autenticazione e TKIP (Temporal Key Integrity Protocol) come protocollo di crittografia.</td>
<td style="border:1px solid black;">Il protocollo TKIP sostituisce lo standard WEP come metodo di crittografia, mentre WPA impone lo standard 802.1X come metodo di autenticazione.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Riautenticazione temporizzata del client</td>
<td style="border:1px solid black;">Questa soluzione utilizza le impostazioni RADIUS per garantire l'esecuzione di una riautenticazione ogni 10 minuti e la conseguente rigenerazione delle chiavi WEP.</td>
<td style="border:1px solid black;">Il protocollo TKIP richiude ogni pacchetto rendendo obsoleti i requisiti di riautenticazione del client per le finalità delle chiavi WEP. La selezione dell'impostazione di esecuzione ogni 10 minuti impone un carico non necessario sui server IAS (Microsoft Internet Authentication Service). Quando si utilizza lo standard WPA, è possibile modificare il timeout della sessione in 10 ore.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Criteri di gruppo di reti senza fili</td>
<td style="border:1px solid black;">I criteri di gruppo delle reti senza fili esistenti, contenuti in Windows Server 2003 prima di SP1, sono stati sviluppati prima che lo standard WPA fosse disponibile e, pertanto, non è possibile configurare le impostazioni WPA del client.</td>
<td style="border:1px solid black;">È necessario utilizzare Windows Server 2003 SP1 per configurare le impostazioni WPA dei criteri di gruppo.<br />
In alternativa, configurare manualmente le impostazioni del client senza fili.</td>
</tr>
</tbody>
</table>
 

#### Configurazione della soluzione di rete LAN senza fili protetta con WPA

Per configurare la soluzione in modo da poter utilizzare lo standard WPA, effettuare le operazioni seguenti:

1.  Aggiornare il firmware nei punti di accesso senza fili esistenti o distribuire nuovi punti di accesso in grado di supportare lo standard WPA. Assicurarsi che vengano aggiunti nuovi punti di accesso senza fili come client RADIUS ai server IAS in base alle istruzioni contenute in questa Guida. Configurare le impostazioni WPA nei punti di accesso senza fili in base alle specifiche del fornitore.

2.  Aggiornare il driver della scheda di interfaccia di rete (NIC) a una versione compatibile con lo standard WPA. Microsoft collabora con numerosi produttori di schede WLAN per consentire di aggiornare il firmware mediante il driver della scheda.

3.  Rimuovere il computer senza fili dal gruppo di protezione che applica i criteri di gruppo di reti senza fili. Creare un nuovo oggetto Criteri di gruppo (GPO) utilizzando Windows Server 2003 SP1 e configurare le impostazioni del client senza fili per lo standard WPA. Specificare WPA come tipo di autenticazione e TKIP come tipo di crittografia. Creare un gruppo di protezione aggiuntivo e concedere l'autorizzazione per l'applicazione dei criteri nell'oggetto Criteri di gruppo per WPA. Utilizzare questo gruppo per controllare quali client ricevono le impostazioni WPA. Se non è stata effettuata la distribuzione di SP1 di Windows Server 2003, è necessario configurare manualmente le impostazioni del client senza fili per lo standard WPA.

4.  Verificare l'autenticazione sulla rete WLAN mediante lo standard WPA. Nel Registro eventi di sistema, viene memorizzato un messaggio con origine **IAS** e un ID evento **1**. In tal caso, l'autenticazione è riuscita.  

#### Ulteriori informazioni

Per ulteriori informazioni sugli argomenti trattati in questa appendice, consultare le risorse seguenti:

-   [The Cable Guy — March 2003, Wi – Fi Protected Access (WPA) Overview](http://www.microsoft.com/technet/community/columns/cableguy/cg0303.mspx) su Microsoft TechNet all'indirizzo http://www.microsoft.com/technet/community/columns/cableguy/cg0303.mspx.

-   Articolo della Microsoft Knowledge Base 815485 “[Panoramica dell'aggiornamento per la protezione wireless WPA in Windows XP](http://support.microsoft.com/?kbid=815485)” all'indirizzo http://support.microsoft.com/?kbid=815485.

-   [Microsoft Press Pass Announcement](http://www.microsoft.com/presspass/press/2003/mar03/03-31wifiprotectedaccesspr.asp) sulla disponibilità dello standard WPA all'indirizzo http://www.microsoft.com/presspass/press/2003/mar03/03-31WiFiProtectedAccessPR.asp.

-   [IEEE 802.11 Wireless LAN Security with Microsoft Windows XP](http://www.microsoft.com/downloads/details.aspx?familyid=67fdeb48-74ec-4ee8-a650-334bb8ec38a9&displaylang=en) all'indirizzo http://www.microsoft.com/downloads/details.aspx?FamilyID=67fdeb48-74ec-4ee8-a650-334bb8ec38a9&displaylang=en.

[](#mainsection)[Inizio pagina](#mainsection)
