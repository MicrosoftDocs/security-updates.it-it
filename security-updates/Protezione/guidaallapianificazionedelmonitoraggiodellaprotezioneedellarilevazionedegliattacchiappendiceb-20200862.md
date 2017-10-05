---
TOCTitle: 'Guida alla pianificazione del monitoraggio della protezione e della rilevazione degli attacchi - Appendice B'
Title: 'Guida alla pianificazione del monitoraggio della protezione e della rilevazione degli attacchi - Appendice B'
ms:assetid: 'e0124920-4edd-4629-9251-3d89b16240c7'
ms:contentKeyID: 20200862
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536263(v=TechNet.10)'
---

Guida alla pianificazione del monitoraggio della protezione e della rilevazione degli attacchi
==============================================================================================

### Appendice B - Implementazione delle impostazioni Criteri di gruppo

Aggiornato: 23 maggio 2005

Nella seguente tabella sono elencate le impostazioni da applicare per la corretta configurazione delle impostazioni dei controlli di protezione di Criteri di gruppo. Sono inoltre indicate le impostazioni aggiuntive che hanno effetto sul sistema di monitoraggio della protezione e di rilevazione degli attacchi. Utilizzare questa tabella per verificare le impostazioni correnti nell'ambiente in uso.

**Tabella B.1. Impostazioni dei controlli di protezione di Criteri di gruppo**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Percorso criterio</th>
<th style="border:1px solid black;" >Criterio</th>
<th style="border:1px solid black;" >Impostazione del criterio e commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Criteri locali/
Criteri di controllo</td>
<td style="border:1px solid black;"><strong>Controlla eventi accesso account</strong></td>
<td style="border:1px solid black;">Attivare il controllo sulle operazioni riuscite per tutti i computer, poiché questo evento registra gli utenti che accedono al computer. L'attivazione del controllo sulle operazioni non riuscite deve essere effettuata con cautela. Un utente malintenzionato con accesso alla rete ma senza alcuna credenziale potrebbe infatti causare un attacco di tipo Denial of Service (DoS), poiché il computer utilizza risorse per generare questi eventi. Fare attenzione nell'attivazione del controllo sulle operazioni riuscite, poiché questa impostazione può causare attacchi di tipo DoS se è previsto l'arresto dei computer in caso di riempimento dei registri di controllo. Mettere in relazione gli accessi amministratore con qualsiasi altra voce sospetta.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Criteri locali/
Criteri di controllo</td>
<td style="border:1px solid black;"><strong>Controlla gestione degli account</strong></td>
<td style="border:1px solid black;">Attivare il controllo sia sulle operazioni riuscite che non riuscite. Mettere in relazione tutte le voci di controllo relative alle operazioni riuscite con le autorizzazioni di amministratore. Considerare tutte le operazioni non riuscite come eventi sospetti.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Criteri locali/
Criteri di controllo</td>
<td style="border:1px solid black;"><strong>Controlla accesso al servizio directory</strong></td>
<td style="border:1px solid black;">Questa impostazione è attivata automaticamente dal Criterio di gruppo controller di dominio predefiniti. Configurare le impostazioni di controllo sugli oggetti directory sensibili utilizzando gli elenchi di controllo accesso di sistema (SACL) in Utenti e computer di Active Directory o Active Directory Services Interface Editor (ADSI Edit). Una volta pianificata l'implementazione SACL, prima della distribuzione in un ambiente di produzione è necessario testare gli elenchi SACL in un ambiente di lavoro realistico. Questo approccio evita di sovraccaricare i registri di protezione con una quantità eccessiva di dati.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Criteri locali/
Criteri di controllo</td>
<td style="border:1px solid black;"><strong>Controlla eventi di accesso</strong></td>
<td style="border:1px solid black;">Attivare il controllo sulle operazioni riuscite per tutti i computer, poiché questo evento registra gli utenti che accedono al computer. L'attivazione del controllo sulle operazioni non riuscite deve essere effettuata con cautela. Un utente malintenzionato con accesso alla rete ma senza alcuna credenziale potrebbe infatti causare l'utilizzo di risorse per generare questi eventi.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Criteri locali/
Criteri di controllo</td>
<td style="border:1px solid black;"><strong>Controlla accesso agli oggetti</strong></td>
<td style="border:1px solid black;">Fare attenzione quando si attiva questa impostazione poiché potrebbe causare un volume molto elevato di controlli. Configurare le impostazioni di controllo solo sulle cartelle critiche mediante elenchi SACL e controllare soltanto il numero minimo dei tipi di accesso a cui si è interessati. Se il modello di rischio lo consente, controllare soltanto le scritture (non gli accessi in lettura).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Criteri locali/
Criteri di controllo</td>
<td style="border:1px solid black;"><strong>Modifica del criterio di controllo</strong></td>
<td style="border:1px solid black;">Attivare il controllo sia sulle operazioni riuscite che non riuscite. Mettere in relazione eventuali operazioni riuscite con le autorizzazioni di amministratore. Considerare tutte le operazioni non riuscite come eventi sospetti.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Criteri locali/
Criteri di controllo</td>
<td style="border:1px solid black;"><strong>Controlla uso dei privilegi</strong></td>
<td style="border:1px solid black;">Si consiglia di non attivare questo controllo a causa del volume elevato di eventi generato.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Criteri locali/
Criteri di controllo</td>
<td style="border:1px solid black;"><strong>Controlla tracciato processo</strong></td>
<td style="border:1px solid black;">Non attivare questa impostazione nei server Web Common Gateway Interface (CGI), nei computer di test, nei server su cui sono in esecuzione processi batch o nelle workstation degli sviluppatori. Attivare questa impostazione nei computer vulnerabili e intervenire immediatamente in caso di attività impreviste nelle applicazioni, se necessario mediante l'isolamento fisico del computer. Questa impostazione può causare il riempimento dei registri di eventi.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Criteri locali/
Criteri di controllo</td>
<td style="border:1px solid black;"><strong>Controlla eventi di sistema</strong></td>
<td style="border:1px solid black;">Attivare il controllo sia sulle operazioni riuscite che non riuscite.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Criteri locali/ Assegnazione diritti utente</td>
<td style="border:1px solid black;"><strong>Generazione di controlli di protezione</strong></td>
<td style="border:1px solid black;">Questa impostazione viene assegnata automaticamente agli account Sistema locale, Servizio locale e Servizio di rete. Questo diritto deve essere applicato soltanto agli account dei servizi. Un utente malintenzionato può utilizzare questa impostazione per generare eventi falsi o inesatti nel registro di protezione.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Criteri locali/ Assegnazione diritti utente</td>
<td style="border:1px solid black;"><strong>Gestione file registro di controllo e di protezione</strong></td>
<td style="border:1px solid black;">Utilizzare questa impostazione per impedire agli amministratori con diritti di modifica di controllare le impostazioni relative ai file, alle cartelle e al Registro di sistema. Prendere in considerazione la creazione di un gruppo di protezione per gli amministratori che possono apportare modifiche alle impostazioni di controllo, quindi rimuovere il gruppo Administrators dalle impostazioni di Criteri di protezione locali. Soltanto i membri del nuovo gruppo di protezione devono essere in grado di configurare le impostazioni di controllo.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Criteri locali/ Opzioni di protezione</td>
<td style="border:1px solid black;"><strong>Controllo: controllo accesso oggetti di sistema globale</strong></td>
<td style="border:1px solid black;">Questa impostazione aggiunge elenchi SACL a determinati oggetti di sistema quali eventi di esclusione reciproca, semafori e periferiche MS-DOS. Per impostazione predefinita, in Windows Server 2003 questa opzione non è attivata. Si consiglia di non attivare questa impostazione, poiché causa la generazione di un numero molto elevato di eventi.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Criteri locali/ Opzioni di protezione</td>
<td style="border:1px solid black;"><strong>Controllo: controllo utilizzo dei privilegi di backup e di ripristino</strong></td>
<td style="border:1px solid black;">Le operazioni di backup e ripristino forniscono l'opportunità di appropriarsi di dati protetti dagli ACL. Si consiglia di non attivare questa impostazione, poiché causa la generazione di un numero molto elevato di eventi.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Criteri locali/ Opzioni di protezione</td>
<td style="border:1px solid black;"><strong>Controllo: arresto del sistema immediato se non è possibile registrare i controlli di protezione</strong></td>
<td style="border:1px solid black;">Attivare questa impostazione, dopo un'attenta analisi, soltanto sui computer critici, poiché gli utenti malintenzionati possono utilizzare questa funzionalità per attacchi di tipo DoS.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Registro eventi</td>
<td style="border:1px solid black;"><strong>Dimensione massima registro protezione</strong></td>
<td style="border:1px solid black;">La dimensione massima del registro di protezione deve essere un multiplo di 64 KB. La dimensione media degli eventi è 0,5 KB. Le impostazioni consigliate dipendono dai volumi previsti per gli eventi e dalle impostazioni relative alla gestione dei registri di protezione. Per gli ambienti in cui viene generato un numero elevato di eventi, è preferibile impostare il valore più grande possibile (fino a 250 MB). Poiché la dimensione totale di tutti i registri di eventi non può superare 300 MB, è necessario non superare questo valore.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Registro eventi</td>
<td style="border:1px solid black;"><strong>Impedisci accesso guest locale al registro applicazione</strong></td>
<td style="border:1px solid black;">Per impostazione predefinita, in Windows Server 2003 questa opzione è attivata e non deve essere modificata.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Registro eventi</td>
<td style="border:1px solid black;"><strong>Gestione registro protezione</strong></td>
<td style="border:1px solid black;">Questa impostazione deve essere attivata solo se è selezionata l'opzione Sovrascrivi eventi ogni giorno. Se si utilizza un sistema di correlazione basato sul polling degli eventi, assicurarsi che il numero dei giorni sia almeno il triplo della frequenza di polling, in modo da consentire cicli di polling non riusciti.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Registro eventi</td>
<td style="border:1px solid black;"><strong>Criteri gestione registro protezione</strong></td>
<td style="border:1px solid black;">Negli ambienti con requisiti di protezione elevati si consiglia di attivare l'opzione Non sovrascrivere eventi. In questo caso, occorre definire procedure per lo svuotamento e l'archiviazione periodica dei registri, in particolare se è previsto l'arresto del computer in caso di riempimento del registro di protezione.</td>
</tr>
</tbody>
</table>
  
##### Download
  
[![](images/Dd536263.icon_exe(it-it,TechNet.10).gif)Guida alla pianificazione del monitoraggio della protezione e della rilevazione degli attacchi](http://go.microsoft.com/fwlink/?linkid=41310)
  
[](#mainsection)[Inizio pagina](#mainsection)
