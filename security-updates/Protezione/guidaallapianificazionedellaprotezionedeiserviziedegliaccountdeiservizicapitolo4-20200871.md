---
TOCTitle: 'Guida alla pianificazione della protezione dei servizi e degli account dei servizi - Capitolo 4'
Title: 'Guida alla pianificazione della protezione dei servizi e degli account dei servizi - Capitolo 4'
ms:assetid: '03e79b48-7541-40f2-9c61-d0e84faaae5f'
ms:contentKeyID: 20200871
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536272(v=TechNet.10)'
---

Guida alla pianificazione della protezione dei servizi e degli account dei servizi
==================================================================================

### Capitolo 4 - Riepilogo

Aggiornato: 31 maggio 2005

In passato, gli sviluppatori di sistemi operativi di rete davano massima priorità alle problematiche dell'accesso e questo tipo di approccio risultava valido per la maggior parte delle organizzazioni. La produttività degli utenti, infatti, dipendeva essenzialmente dalla capacità di accedere alle risorse o di eseguire i servizi. Queste esigenze avevano un'incidenza molto maggiore rispetto ai possibili rischi derivanti da intrusioni o attacchi. Tuttavia, con l'aumentare della diffusione di virus e codice dannoso e con la crescente destrezza raggiunta dagli autori di questo tipo di programmi, lo scenario attuale è completamente diverso. Per la maggior parte delle organizzazioni, la priorità principale è ora diventata la protezione.

In passato, l'installazione delle applicazioni e dei servizi nell'ambiente aziendale veniva in genere effettuata con il livello più alto possibile di autorizzazioni, in modo da rendere disponibili tutte le funzionalità.

Questa decisione era dovuta a diversi motivi:

-   I fornitori di software, compreso Microsoft, non avevano una visione completa e dettagliata degli ambienti di rete dei clienti.

-   I clienti utilizzavano prodotti di diversi fornitori di software con conseguenti esigenze di interoperabilità.

-   Si presupponeva che le applicazioni fossero installate direttamente dagli utenti che dovevano utilizzarle.

Tali fattori hanno portato le organizzazioni a concedere agli account dei servizi livelli di privilegio molto maggiori rispetto a quelli necessari e a far sì che le applicazioni e i servizi diventassero i principali punti di vulnerabilità per gli attacchi da parte di utenti malintenzionati.

Questo problema è stato in parte risolto dai fornitori di software indipendenti (ISV) attraverso la maggiore integrazione della protezione basata su ruoli all'interno delle applicazioni che utilizzano Microsoft® .NET Framework e un ambiente di sviluppo quale Microsoft Visual Studio® 2005.

Per cercare di risolvere il problema, Microsoft ha inoltre provveduto ad apportare una serie di modifiche rilevanti nell'ultima versione di Microsoft Windows Server™ 2003, in modo da rendere questo sistema operativo molto più sicuro rispetto alle versioni precedenti.

Tra le modifiche apportate al sistema operativo sono incluse la differenziazione delle autorizzazioni predefinite per le risorse di file e cartelle condivise, nonché le modifiche ai criteri di appartenenza al gruppo Everyone, ai diritti di proprietà sugli oggetti, alle impostazioni predefinite per i servizi comuni e al processo di autenticazione.

Per ulteriori informazioni sulle differenze tra le impostazioni di protezione predefinite di Windows Server 2003 e quelle delle versioni precedenti di Windows, vedere [Differences in default security settings](http://technet.microsoft.com/en-us/library/cc772745.aspx) all'indirizzo www.microsoft.com/resources/documentation/WindowsServ/
2003/datacenter/proddocs/en-us/windows\_security\_differences.asp (informazioni in lingua inglese).

I servizi continuano a essere i principali punti di vulnerabilità per gli attacchi degli utenti malintenzionati. Di conseguenza, i servizi eseguiti con un numero eccessivo di privilegi risultano estremamente rischiosi per la protezione del sistema. Se un determinato servizio non è necessario, è opportuno disattivarlo. In questo modo, è possibile restringere immediatamente la superficie di attacco della rete. Una seria minaccia è inoltre rappresentata dai servizi che non eseguono l'autenticazione dei client o che utilizzano protocolli non protetti. Per ulteriori informazioni, vedere [Isolamento del server e del dominio tramite IPsec e criteri di gruppo](http://technet.microsoft.com/it-it/library/dd550626.aspx) all'indirizzo http://go.microsoft.com/fwlink/?linkid=33945.

Per i servizi necessari, è invece indispensabile definire un processo che consenta agli amministratori di individuare i servizi di Windows che utilizzano privilegi elevati, stabilire il livello minimo di privilegio necessario per l'esecuzione dei servizi e quindi, se opportuno, ripetere la distribuzione con un livello di privilegio inferiore.

##### In questa pagina

[](#ebaa)[Passaggi successivi](#ebaa)
[](#eaaa)[Bibliografia essenziale](#eaaa)

### Passaggi successivi

Questa guida contiene informazioni utili per le organizzazioni che desiderano implementare una soluzione per l'esecuzione protetta dei servizi.

Di seguito sono elencate le operazioni principali che devono essere eseguite dalle organizzazioni per definire un sistema efficace per l'esecuzione protetta dei servizi: 

-   Definizione di un processo per individuare i livelli di privilegio esistenti dei servizi di Windows.

-   Individuazione di un metodo per stabilire il livello minimo di privilegio in base al quale verrà eseguito un determinato servizio.

-   Definizione di un metodo sistematico per ridurre i privilegi assegnati ai servizi non predefiniti che abbia un impatto minimo sull'ambiente di produzione.

[](#mainsection)[Inizio pagina](#mainsection)

### Bibliografia essenziale

Per garantire l'integrità di un programma che esegue servizi in modo protetto è necessario prevedere una manutenzione costante. In Microsoft Operations Framework (MOF) vengono fornite informazioni di carattere generale sulle procedure operative consigliate. Per ulteriori informazioni su MOF, visitare il sito Web [Microsoft Operations Framework](http://www.microsoft.com/technet/itsolutions/cits/mo/mof/default.mspx) all'indirizzo www.microsoft.com/technet/itsolutions/cits/mo/mof/default.mspx (informazioni in lingua inglese).

Questa guida è composta essenzialmente da una serie di procedure consigliate. Per ulteriori considerazioni sulle procedure consigliate per l'esecuzione protetta dei servizi, fare riferimento alle seguenti risorse:

-   Per ulteriori informazioni sui servizi di sistema per Windows Server 2003, vedere il Capitolo 7 "System Services" in [Threats and Countermeasures Guide](http://www.microsoft.com/technet/security/topics/serversecurity/tcg/tcgch00.mspx) all'indirizzo www.microsoft.com/technet/security/
    topics/serversecurity/tcg/tcgch00.mspx (informazioni in lingua inglese).

-   Per ulteriori informazioni sui vantaggi offerti da Windows Server 2003 con Service Pack 1 a livello di protezione, affidabilità e amministrazione, visitare il sito Web [Windows Server 2003 Service Pack 1](http://www.microsoft.com/windowsserver2003/downloads/servicepacks/sp1/default.mspx) all'indirizzo www.microsoft.com/windowsserver2003/downloads/
    servicepacks/sp1/default.mspx (informazioni in lingua inglese).

-   Per ulteriori informazioni sull'utilizzo della funzionalità Criteri di gruppo e dell'infrastruttura dei servizi Active Directory® in Windows Server 2003, vedere [Group Policy in Windows Server 2003](http://technet.microsoft.com/en-us/library/cc758751.aspx) all'indirizzo www.microsoft.com/windowsserver2003/
    technologies/management/grouppolicy/default.mspx (informazioni in lingua inglese).

-   Per ulteriori informazioni su MBSA, visitare il sito Web [Microsoft Baseline Security Analyzer (MBSA)](http://www.microsoft.com/technet/security/tools/mbsahome.mspx) all'indirizzo www.microsoft.com/technet/security/tools/mbsahome.mspx (informazioni in lingua inglese).

-   Per ulteriori informazioni su Strumentazione gestione Windows (WMI), vedere:

    -   [WMI: Introduction to Windows Management Instrumentation](http://msdn.microsoft.com/en-us/library/ms799738.aspx) all'indirizzo www.microsoft.com/whdc/system/pnppwr/wmi/WMI-intro.mspx (informazioni in lingua inglese).

    -   [Cenni preliminari su Strumentazione gestione Windows](http://technet.microsoft.com/en-us/library/cc736575.aspx) all'indirizzo www.microsoft.com/windows2000/it/server
        /help/windows\_WMI\_overview.htm?id=751.

-   Per ulteriori informazioni sulla protezione negli attuali sistemi operativi Windows, vedere:

    -   [Windows 2000 Security Hardening Guide](http://go.microsoft.com/fwlink/?linkid=22380) all'indirizzo http://go.microsoft.com/fwlink/?LinkID=22380 (informazioni in lingua inglese).

    -   [Introduzione alla protezione di Windows 2003](http://technet.microsoft.com/it-it/library/cc163140.aspx) all'indirizzo http://go.microsoft.com/fwlink/?LinkId=14845.

    -   [Guida per la protezione di Windows XP](http://technet.microsoft.com/it-it/library/cc163061.aspx) all'indirizzo http://go.microsoft.com/fwlink/?LinkId=14839.

    -   [Requisiti delle porte per il sistema di server Microsoft Windows](http://support.microsoft.com/?kbid=832017) all'indirizzo http://support.microsoft.com/?kbid=832017.

##### Download

[![](images/Dd536272.icon_exe(it-it,TechNet.10).gif)Guida alla pianificazione della protezione dei servizi e degli account dei servizi](http://go.microsoft.com/fwlink/?linkid=41312)

[](#mainsection)[Inizio pagina](#mainsection)
