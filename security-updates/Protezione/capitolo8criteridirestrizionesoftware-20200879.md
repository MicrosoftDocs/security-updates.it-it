---
TOCTitle: 'Capitolo 8: Criteri di restrizione software'
Title: 'Capitolo 8: Criteri di restrizione software'
ms:assetid: 'b842dd3c-12e5-4724-88c6-141919e232f3'
ms:contentKeyID: 20200879
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536280(v=TechNet.10)'
---

Pericoli e contromisure
=======================

### Capitolo 8: Criteri di restrizione software

I criteri di restrizione software sono nuove funzionalità di Microsoft Windows XP e Microsoft Windows Server 2003. Costituiscono un sistema basato su criteri attraverso il quale è possibile specificare i programmi che possono essere eseguiti.

##### In questa pagina

[](#ebaa)[Pericolo di software dannoso](#ebaa)
[](#eaaa)[Ulteriori informazioni](#eaaa)

### Pericolo di software dannoso

A causa dell'importanza sempre maggiore che Internet e le reti stanno assumendo nel lavoro di ogni giorno, la possibilità di imbattersi in codice dannoso è più alta che mai. I criteri di restrizione software possono essere utili alle organizzazioni che desiderano proteggersi, in quanto forniscono un altro livello di protezione da virus, cavalli di Troia e altri tipi di codice dannosi.

#### Vulnerabilità

Le persone utilizzano reti di computer per collaborare in modi sempre più complessi; utilizzano la posta elettronica, messaggi istantanei e applicazioni peer-to-peer. Con l'aumento delle opportunità di collaborazione, aumenta anche il rischio di virus, worm e altre forme di software dannoso. È importante ricordare che la posta elettronica e i messaggi istantanei possono contenere codice dannoso indesiderato, che può avere molte forme, da un eseguibile Windows nativo (.exe), una macro di un documento di un elaboratore di testi (.doc) o uno script (.vbs).

I virus e i worm sono spesso trasmessi nei messaggi di posta elettronica e contengono il più delle volte tecniche di individuazione di persone vulnerabili che spingono gli utenti a eseguire un'azione che attiva il codice dannoso. Poiché il codice può assumere innumerevoli forme, può essere difficile per gli utenti stabilire cosa può essere eseguito con tranquillità e cosa non può esserlo. Una volta attivato, il codice dannoso può danneggiare il contenuto di un disco rigido, intasare una rete con attacchi di tipo Denial of Service (DoS), inviare informazioni riservate attraverso Internet o violare la protezione di un computer.

#### Contromisura

Impostare accuratamente i criteri di restrizione software dei computer degli utenti finali e testarli a fondo in laboratorio prima di distribuirli in produzione.

#### Impatto potenziale

Implementando i criteri di restrizione software in modo non corretto è possibile che le applicazioni necessarie vengano disabilitate e che quelle pericolose vengano eseguite. Perciò, le organizzazioni devono allocare risorse sufficienti per la gestione e la risoluzione dei problemi dell'implementazione di tali criteri.

**Nota**: i criteri di restrizione software sono uno strumento importante per il miglioramento della protezione dei computer ma non sostituiscono altre misure di sicurezza come i programmi antivirus, i firewall e gli elenchi di controllo di accesso restrittivi (ACL).

[](#mainsection)[Inizio pagina](#mainsection)

### Ulteriori informazioni

I collegamenti riportati di seguito forniscono ulteriori informazioni sulla progettazione e l'utilizzo dei criteri di restrizione software:

-   L'articolo "[Microsoft Windows XP: Using Software Restriction Policies to Protect Against Unauthorized Software](http://technet.microsoft.com/en-us/library/bb457006.aspx)" (in inglese) all'indirizzo www.microsoft.com/technet/prodtechnol/winxppro/
    maintain/rstrplcy.mspx illustra l'implementazione dei criteri di restrizione software sui computer Windows XP.

-   Il [capitolo 6](http://technet.microsoft.com/it-it/library/cc163080.aspx) della *Guida per la protezione di Windows XP* all'indirizzo www.microsoft.com/technet/security/
    prodtech/windowsxp/secwinxp/xpsgch06.mspx riporta informazioni sulla progettazione e la distribuzione di criteri di restrizione software per i computer client Windows XP.

-   L'articolo della Microsoft Knowledge Base "[Come utilizzare i criteri di restrizione software in Windows Server 2003](http://support.microsoft.com/kb/324036/it)" all'indirizzo http://support.microsoft.com/kb/324036/it riporta informazioni sulla distribuzione di criteri di restrizione software sui sistemi Windows Server 2003 e in domini dei servizi directory Active Directory.

**Download**

[Scaricare la Guida a pericoli e contromisure](http://go.microsoft.com/fwlink/?linkid=15160)

**Notifiche di aggiornamento**

[Iscriversi per ottenere aggiornamenti e nuove versioni](http://go.microsoft.com/fwlink/?linkid=54982)

**Commenti e suggerimenti**

[Inviare commenti o suggerimenti](mailto:secwish@microsoft.com?subject=guida%20a%20pericoli%20e%20contromisure)

[](#mainsection)[Inizio pagina](#mainsection)
