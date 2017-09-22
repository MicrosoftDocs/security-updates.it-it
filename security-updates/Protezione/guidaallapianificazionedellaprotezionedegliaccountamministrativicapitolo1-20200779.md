---
TOCTitle: 'Guida alla pianificazione della protezione degli account amministrativi - Capitolo 1'
Title: 'Guida alla pianificazione della protezione degli account amministrativi - Capitolo 1'
ms:assetid: 'b3410eae-1912-42c8-be31-0670beffc58e'
ms:contentKeyID: 20200779
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536179(v=TechNet.10)'
---

Guida alla pianificazione della protezione degli account amministrativi
=======================================================================

### Capitolo 1 - Introduzione

Aggiornato: 25/5/2005

##### In questa pagina

[](#ebaa)[Riepilogo generale](#ebaa)
[](#eaaa)[Panoramica della Guida alla pianificazione](#eaaa)

### Riepilogo generale

A causa delle autorizzazioni e della potenza di cui dispongono in modo intrinseco, sui computer che eseguono il sistema operativo Microsoft® Windows Server™ 2003 gli account amministrativi sono contemporaneamente gli account più utili e potenzialmente più pericolosi. Qualsiasi altro account cui si concedono privilegi equivalenti a quelli di un amministratore presenta lo stesso elevato livello di rischio.

Questa guida costituisce una risorsa indispensabile per la pianificazione di strategie di protezione degli account di livello amministrativo nei sistemi operativi basati su Microsoft Windows NT®, come Windows Server 2003 e Windows® XP. Viene affrontato il problema rappresentato dagli intrusi che ottengono le credenziali di un account amministrativo e le utilizzano per compromettere la rete. L'obiettivo principale di questa guida è fornire istruzioni precise sotto forma di operazioni da eseguire per proteggere gli account e i gruppi di livello amministrativo, locali o basati sul dominio. Queste istruzioni si fondano sull'esperienza maturata dal Microsoft Security Center of Excellence (SCoE) negli ambienti dei clienti e rappresentano le procedure ottimali suggerite da Microsoft.

#### Cenni preliminari

Un aspetto importante della protezione di una rete è la gestione di utenti e gruppi che hanno accesso amministrativo al database di account locale su computer indipendenti o membri di un dominio e al servizio di directory Active Directory® sui controller di dominio. Esistono essenzialmente due tipi di aggressori da cui ci si dovrebbe guardare:

-   Malintenzionati che ottengono un accesso di livello amministrativo a server membri o controller di dominio e potrebbero far breccia nella protezione dell'intera rete. Potrebbe trattarsi di utenti non autorizzati che siano venuti in possesso delle password amministrative o di legittimi amministratori in stato di coercizione o scontenti.

-   Utenti cui è stato concesso l'accesso come amministratori. Questi individui potrebbero causare involontariamente problemi poiché non sono in grado di comprendere le implicazioni connesse alle modifiche della configurazione.

Le persone non autorizzate o non competenti che dispongono di privilegi amministrativi possono danneggiare l'organizzazione in modo doloso o casuale se copiano o eliminano dati riservati, diffondono virus o disabilitano la rete. La corretta gestione degli utenti e dei gruppi che hanno controllo amministrativo sui server e sui controller di dominio della rete è di vitale importanza.

Le impostazioni di protezione predefinite di Windows Server 2003 sono sufficienti a proteggere gli account locali e di Active Directory contro molti tipi di minacce. È tuttavia necessario rafforzare alcune delle impostazioni predefinite degli account amministrativi per migliorare il livello di protezione della rete. Questa guida aiuterà a farlo.

La conformità ai principi e alle procedure ottimali esposti in questa guida può aiutare a ridurre il pericolo rappresentato da utenti non autorizzati che ottengono l'accesso amministrativo a controller di dominio, a server membri e ad Active Directory. La protezione degli account amministrativi è un'iniziativa importante per le organizzazioni che cercano di proteggere in modo completo le proprie risorse di rete.

#### Destinatari della guida

Questa guida è rivolta principalmente a consulenti, specialisti della protezione, architetti di sistema e professionisti IT responsabili delle fasi di pianificazione dello sviluppo di applicazioni o infrastrutture e dell'installazione di Windows Server 2003. Tra i ruoli interessati sono incluse le seguenti figure professionali:

-   Architetti di sistema e addetti alla pianificazione responsabili della gestione dell'architettura per i client delle organizzazioni di appartenenza.

-   Specialisti della sicurezza IT che garantiscono la protezione delle piattaforme nelle loro organizzazioni

-   Architetti di impresa che gestiscono l'intera impresa anziché una specifica rete

-   Responsabili IT la cui responsabilità consiste nel determinare la tecnologia da utilizzare per risolvere determinati problemi aziendali

-   Analisti e responsabili dei processi decisionali dell'azienda con il compito di soddisfare obiettivi e requisiti aziendali critici basati sul supporto tecnico per client.

-   Consulenti di servizi Microsoft e partner che necessitano di risorse dettagliate in relazione a informazioni utili per utenti e partner dell'organizzazione.

La *Guida alla pianificazione della protezione degli account amministrativi*, anche se è stata scritta essenzialmente per questi ruoli, può essere utile anche agli specialisti IT di medie e grandi organizzazioni e per i ruoli Infrastruttura, Operativo e Protezione dei team, così come identificati nel modello di team di Microsoft Operations Framework (MOF). Per ulteriori informazioni su MOF, visitare il sito Web [Microsoft Operations Framework](http://www.microsoft.com/technet/itsolutions/cits/mo/mof/default.mspx) all'indirizzo www.microsoft.com/technet/itsolutions/cits/mo/mof/default.mspx.

[](#mainsection)[Inizio pagina](#mainsection)

### Panoramica della Guida alla pianificazione

Questa guida include:

**Capitolo 1: Introduzione**

In questo capitolo vengono fornite una sintesi e una panoramica destinate ai responsabili e vengono indicati i destinatari consigliati per la guida. Vengono inoltre forniti cenni generali dei capitoli contenuti nella guida.

**Capitolo 2: Principi di base per rendere più sicuri gli account amministrativi**

In questo capitolo viene fornita una panoramica degli account utente e dei gruppi amministrativi che è possibile utilizzare per accedere a un computer o a un dominio e descrive i principi da applicare quando si pianifica la protezione degli account amministrativi.

**Capitolo 3: Direttive per rendere più sicuri gli account amministrativi**

Questo capitolo descrive alcune direttive da seguire per proteggere gli account amministrativi, sotto forma di procedure ottimali. Queste direttive seguono i principi introdotti nel capitolo precedente.

**Capitolo 4: Riepilogo**

In questo capitolo vengono riassunte le istruzioni fornite e affrontati i problemi che possono verificarsi durante l'applicazione delle istruzioni. Vengono inoltre forniti collegamenti a ulteriore materiale di riferimento che potrebbe rivelarsi utile.

##### Download

[![](images/Dd536179.icon_exe(it-it,TechNet.10).gif)Guida alla pianificazione del monitoraggio della protezione e della rilevazione degli attacchi](http://go.microsoft.com/fwlink/?linkid=41316)

[](#mainsection)[Inizio pagina](#mainsection)
