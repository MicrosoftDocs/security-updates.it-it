---
TOCTitle: 'Capitolo 1: Introduzione alla difesa antivirus a più livelli'
Title: 'Capitolo 1: Introduzione alla difesa antivirus a più livelli'
ms:assetid: '3d2a64f8-fab1-40bd-9ef1-05d11a23f676'
ms:contentKeyID: 20200783
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536183(v=TechNet.10)'
---

Guida alla difesa antivirus a più livelli
=========================================

### Capitolo 1: Introduzione

Pubblicato: 20 maggio 2004

Sebbene molte organizzazioni abbiano sviluppato software antivirus, nuovi virus, worm e altre forme di *software dannoso* continuano a infettare rapidamente moltissimi sistemi informatici. Non esiste un singolo motivo per questa apparente contraddizione, ma la tendenza appare evidente dalle indicazioni fornite a Microsoft dai professionisti IT e dagli addetti alla protezione di organizzazioni che hanno subito infezioni, con commenti quali:

-   "L'utente ha avviato l'esecuzione del file allegato al messaggio di posta elettronica, anche se era stato informato più volte della pericolosità di tale operazione..."

-   "Il software antivirus avrebbe dovuto intercettare il virus, ma il file di aggiornamento delle definizioni dei virus non era stato ancora installato".

-   "Il virus non avrebbe dovuto superare il firewall; non ci siamo accorti che quelle porte erano esposte agli attacchi".

-   "Non sapevamo che è necessario aggiornare periodicamente i server".

Il successo degli attacchi più recenti evidenzia l'inadeguatezza dell'approccio standard basato sulla distribuzione del software antivirus a tutti i computer dell'organizzazione. Gli attacchi più recenti si sono diffusi con una rapidità allarmante, superiore alla capacità delle industrie del settore di rilevare e identificare i problemi e di produrre strumenti antivirus in grado di offrire una protezione adeguata dagli attacchi. Le tecniche adoperate dalle forme di software dannoso più recenti dimostrano che è stato compiuto un salto di qualità sostanziale, con attacchi che riescono a evitare il rilevamento e ad avviare una rapida propagazione. Tali tecniche sono:

-   **Individuazione di persone vulnerabili**: molti attacchi tentano di accreditarsi come comunicazioni originate da un amministratore di sistema o da servizi ufficiali, per aumentare le probabilità di esecuzione da parte degli utenti finali e di infezione dei sistemi.

-   **Creazione di backdoor**: la maggior parte degli attacchi più recenti ha comportato un tentativo di apertura di una qualche forma di accesso non autorizzato a sistemi già infetti, in modo da consentire a un hacker di accedere ripetutamente ai sistemi. Tale accesso ripetuto viene utilizzato per infettare con nuovo software dannoso i sistemi, utilizzati come "zombi" in attacchi di tipo negazione del servizio (Denial of Service) coordinati o per l'esecuzione di qualsiasi tipo di codice l'hacker desideri.

-   **Appropriazione di indirizzi di posta elettronica**: gli indirizzi di posta elettronica intercettati sui sistemi infetti vengono utilizzati da programmi di software dannoso per la diffusione dell'infezione ad altre vittime. Gli autori del software dannoso possono utilizzare gli indirizzi così raccolti per l'invio di nuove varianti del software dannoso, per un baratto con altri autori di software dannoso in cambio di strumenti o codice sorgente di virus o per la vendita ad altre entità interessate a inviare messaggi di posta elettronica indesiderati.

-   **Motori di posta elettronica integrati**: la posta elettronica è uno dei veicoli preferiti per la propagazione del software dannoso. In molte nuove forme di software dannoso è direttamente integrato un motore di posta elettronica che facilita e velocizza la propagazione del codice dannoso, con una minore probabilità di creare attività insolita che possa essere rilevata. Gli strumenti illeciti di inoltro di grandi quantità di messaggi di posta elettronica ora sfruttano le backdoor dei sistemi infetti per capitalizzare le opportunità di utilizzo di tali motori di posta elettronica. Si ritiene infatti che la maggior parte dei messaggi di posta elettronica indesiderati siano stati inviati proprio tramite sistemi infetti di questo tipo.

-   **Sfruttamento delle vulnerabilità dei prodotti**: per una rapida propagazione, il software dannoso punta sempre più di frequente alle vulnerabilità dei prodotti.

-   **Sfruttamento delle tecnologie Internet**: i nuovi strumenti Internet che arrivano sul mercato vengono immediatamente presi in esame dagli autori di software dannoso che ne esplorano le possibilità di utilizzo per i propri fini. Di recente, messaggistica immediata e reti peer-to-peer (P2P) sono divenuti vettori di attacco ideali.

    I termini e le tecnologie sfruttate dal software dannoso vengono illustrati dettagliatamente nei successivi capitoli della Guida.

Microsoft è sempre attivamente impegnata nella protezione delle applicazioni prodotte e nella collaborazione con i partner aziendali per la lotta al software dannoso. Tra le azioni più recenti adottate da Microsoft per ridurre l'impatto di queste minacce è possibile citare:

-   Stretta collaborazione con i produttori di antivirus per formare la Virus Information Alliance (VIA). I membri della VIA si scambiano informazioni di tipo tecnico sui software dannosi di nuova concezione scoperti, in modo da fornire immediatamente ai clienti informazioni su obiettivi, impatto e possibili rimedi. Per ulteriori informazioni su VIA, consultare la pagina relativa alla Virus Information Alliance (VIA) del sito Microsoft® TechNet all'indirizzo: [http://www.microsoft.com/technet/security/topics/virus/via.mspx](http://technet.microsoft.com/en-us/security/cc165596.aspx) (in inglese).

-   Ricerca di nuove tecnologie di protezione come Active Protection Technology e Dynamic System Protection, per giungere a una protezione efficace della piattaforma Microsoft Windows®. Per ulteriori informazioni su queste azioni, leggere le considerazioni di Bill Gates alla RSA Conference 2004 sul sito Web Microsoft.com all'indirizzo:
    <http://www.microsoft.com/billgates/speeches/2004/02-24rsa.asp> (in inglese).

-   Supporto a normative che tendano a eliminare l'invio di messaggi di posta elettronica indesiderati (spam) e collaborazione con organi di polizia e provider Internet (ISP) per perseguire gli autori di operazioni di spam. Per ulteriori informazioni sui membri del cartello costituito per il raggiungimento di questi obiettivi, vedere America Online, Microsoft e Yahoo! Join Forces Against Spam sul sito Web Microsoft.com all'indirizzo: [http://www.microsoft.com/presspass/press/2003/apr03/04-28JoinForcesAntispamPR.asp](http://www.microsoft.com/presspass/press/2003/apr03/04-28joinforcesantispampr.asp) (in inglese).

-   Annuncio dell'Antivirus Reward Program e stretta collaborazione con le autorità competenti per la riduzione delle minacce create dagli autori di software dannoso. Per ulteriori informazioni sull'Antivirus Reward Program, vedere la pagina Microsoft Announces Antivirus Reward Program nel sito Web Microsoft.com all'indirizzo: [http://www.microsoft.com/presspass/press/2003/nov03/11-05AntiVirusRewardsPR.asp](http://www.microsoft.com/presspass/press/2003/nov03/11-05antivirusrewardspr.asp) (in inglese).

Microsoft ha prodotto queste indicazioni sulla protezione con l'intento di aiutare gli utenti a identificare tutti i punti dell'infrastruttura in cui è consigliabile implementare delle difese antivirus. In questa Guida sono inoltre riportate informazioni su come risolvere i problemi causati dai virus e ripristinare i sistemi infetti.

##### In questa pagina

[](#ebaa)[Destinatari](#ebaa)
[](#eaaa)[Convenzioni stilistiche adottate in questa guida](#eaaa)

### Destinatari

Questa Guida è rivolta principalmente a professionisti IT e addetti alla protezione, per garantire una migliore comprensione delle minacce e dei problemi posti dal software dannoso, per suggerire procedure di difesa contro tali minacce e offrire una risposta rapida e appropriata agli attacchi di software dannosi.

Le considerazioni riportate nella Guida sono soprattutto relative alla difesa antivirus di un'ampia gamma di client e server, ma possono essere in egual modo applicate alle organizzazioni che utilizzano un unico server aziendale. Ciascuna delle considerazioni sulla difesa è rivolta alla protezione dell'ambiente contro la minaccia rappresentata da alcuni tipi specifici di software dannoso, ampliando lo spettro delle organizzazioni interessate. Alcune delle contromisure consigliate, come monitoraggio e gestione dei sistemi, potrebbero non essere attinenti all'ambito o alle esigenze di alcune organizzazioni, tuttavia, per il team che ha prodotto questa Guida, è fondamentale che tutti gli utenti ne prendano visione al fine di comprendere meglio la natura del rischio rappresentato dal software dannoso per i sistemi informatici in tutto il mondo.

[](#mainsection)[Inizio pagina](#mainsection)

### Convenzioni stilistiche adottate in questa guida

Nella tabella riportata di seguito sono indicate le convenzioni stilistiche utilizzate nella** *Guida alla difesa antivirus a più livelli*.

**Tabella 1.1: Convenzioni di stile**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Elemento    </p></th>
<th><p>Significato</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p><strong>Grassetto</strong></p></td>
<td style="border:1px solid black;"><p>Nomi di file ed elementi dell'interfaccia utente sono riportati in grassetto.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p><em>Corsivo</em><br />
- o -<br />
<em>&lt;Corsivo&gt;</em></p></td>
<td style="border:1px solid black;"><p>Il corsivo viene applicato ai caratteri digitati dall'utente e che è possibile modificare. I caratteri in corsivo visualizzati tra parentesi ad angolo rappresentano segnaposto variabili in cui l'utente deve indicare valori specifici. Ad esempio:</p>
<p><em>  &lt;Nomefile.ext&gt;</em> indica che è necessario sostituire il <em> </em><br />  
<em>  nomefile.ext</em> in corsivo con un altro nome di file appropriato per la<br />  
  configurazione.<br />  
</p>  
<p>Il corsivo viene inoltre utilizzato per contraddistinguere i nuovi termini. Ad esempio:</p>  
<p><em>  Identità digitale -</em> Il codice di identificazione univoco e gli attributi descrittivi di<br />
  una persona, un gruppo, una periferica o un servizio.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Stile Testo su schermo</p></td>
<td style="border:1px solid black;"><p>Con questo stile si definisce il testo visualizzato sullo schermo.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><pre><code>Codice a spaziatura fissa</code></pre>
<br />
</td>
<td style="border:1px solid black;"><p>Questo stile viene utilizzato per definire gli esempi di codice. Esempio:<br />
  public override void Install(IDictionary savedState)</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><pre><code>Comando a spaziatura fissa</code></pre>
<br />
</td>
<td style="border:1px solid black;"><p>Con questo stile si definiscono comandi, switch e attributi digitati dall'utente al prompt dei comandi. Esempio:<br />
  Al prompt dei comandi, digitare:<br />
  CScript SetUrlAuth.vbs</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>%SystemRoot%</p></td>
<td style="border:1px solid black;"><p>Cartella di installazione del sistema operativo Windows.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p><strong>Nota</strong></p></td>
<td style="border:1px solid black;"><p>Richiama l'attenzione del lettore su informazioni supplementari.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p><strong>Importante</strong></p></td>
<td style="border:1px solid black;"><p>Richiama l'attenzione del lettore su informazioni supplementari essenziali per il completamento dell'operazione.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p><strong>Avviso</strong></p></td>
<td style="border:1px solid black;"><p>Avvisa il lettore che l’inosservanza di un’azione specifica potrebbe provocare una perdita di dati.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p><strong>Attenzione</strong></p></td>
<td style="border:1px solid black;"><p>Avvisa il lettore che l’inosservanza di un’azione specifica potrebbe provocare lesioni fisiche all’utente o danni all’hardware.</p></td>
</tr>  
</tbody>  
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
