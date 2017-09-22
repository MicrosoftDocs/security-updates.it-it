---
TOCTitle: 'Guida alla pianificazione della protezione degli account amministrativi - Capitolo 4'
Title: 'Guida alla pianificazione della protezione degli account amministrativi - Capitolo 4'
ms:assetid: '1012e311-91aa-42c9-afa4-8c1305e06eec'
ms:contentKeyID: 20200782
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536182(v=TechNet.10)'
---

Guida alla pianificazione della protezione degli account amministrativi
=======================================================================

### Capitolo 4 - Riepilogo

Aggiornato: 25/5/2005

A causa della loro potenza e delle autorizzazioni intrinseche, gli account amministrativi sono contemporaneamente gli account più utili e potenzialmente più pericolosi.

Le organizzazioni devono essere particolarmente attente quando proteggono gli account Administrator a livello di dominio perché un intruso in grado di manomettere un account amministrativo di un dominio potrebbe ottenere ampio accesso a tutti i computer dei domini e degli insiemi di strutture. Microsoft ha stabilito una procedura per proteggere gli account degli amministratori di dominio sulle reti aziendali ed esorta le altre organizzazioni a comportarsi nello stesso modo.  

Quando si gestisce una rete si dovrebbero utilizzare le procedure ottimali descritte in questa guida e conformarsi ai suoi principi, per ridurre il pericolo che utenti non autorizzati possano ottenere l'accesso amministrativo a risorse di rete sensibili e ai dati del servizio directory Active Directory®.

Garantire la massima sicurezza per gli account Administrator è un'iniziativa importante per le organizzazioni che vogliono proteggere le proprie risorse di rete.

##### In questa pagina

[](#ebaa)[Passaggi successivi](#ebaa)
[](#eaaa)[Ulteriori informazioni](#eaaa)

### Passaggi successivi

Se un'organizzazione non ha ancora messo a punto un programma per la protezione degli account Administrator, questa guida fornisce le basi per pianificare tale programma.

I passaggi principali che le organizzazioni devono implementare per pianificare la protezione degli account Administrator sono:

-   Definire un processo per ridurre il rischio di manomissione degli account Administrator.

-   Identificare le strategie per aumentare la protezione degli account amministrativi in Active Directory.

-   Utilizzare il principio del privilegio minimo.

-   Separare il ruolo di amministratore del dominio da quello di amministratore dell'organizzazione.

-   Utilizzare il Servizio accesso secondario per separare gli account degli utenti dagli account amministrativi.

-   Seguire le direttive indicate nelle procedure ottimali per proteggere gli account amministrativi.

[](#mainsection)[Inizio pagina](#mainsection)

### Ulteriori informazioni

L'integrità di un piano che assicuri gli account a livello di amministratore dipende dalla sua manutenzione a lungo termine. Per ulteriori informazioni sulle procedure operative ottimali, visitare il sito Web [Microsoft® Operations Framework (MOF)](http://technet.microsoft.com/en-us/library/cc506049.aspx) (in inglese) all'indirizzo www.microsoft.com/technet/itsolutions/techguide/mof/default.mspx.

Questa guida per rendere più sicuri gli account amministrativi è essenzialmente una raccolta delle procedure ottimali Microsoft. Per altre considerazioni sulle procedure ottimali per proteggere l'infrastruttura di Active Directory, vedere le seguenti risorse:

-   Per ulteriori informazioni sulle modalità per rendere più sicuri i controller di dominio, vedere [Hardening Windows Server 2003 Domain Controllers](http://www.microsoft.com/technet/security/guidance/secmod120.mspx) nella *Windows Server™ 2003 Security Guide* (in inglese) all'indirizzo www.microsoft.com/technet/security/guidance/secmod120.mspx.

-   Per ulteriori informazioni su come rendere più sicuro Windows Server 2003, scaricare la [Windows Server 2003 Security Guide](http://www.microsoft.com/downloads/details.aspx?familyid=8a2643c1-0685-4d89-b655-521ea6c7b4db&displaylang=en) all'indirizzo http://go.microsoft.com/fwlink/?linkid=14846.

-   Per ulteriori informazioni sulle password e sui criteri pe gli account in Windows Server 2003, vedere il white paper "[Account Passwords and Policies](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/technologies/security/bpactlck.mspx)" (in inglese) all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/
    technologies/security/bpactlck.mspx.

-   Per ulteriori informazioni su come pianificare, creare e mantenere con successo un programma di gestione dei rischi di protezione, vedere [The Security Risk Management Guide](http://www.microsoft.com/technet/security/guidance/secrisk/default.mspx) (in inglese) all'indirizzo www.microsoft.com/technet/security/guidance/secrisk/default.mspx.

-   Per ulteriori informazioni sull'uso di password più potenti e sicure, vedere i seguenti documenti del Security Guidance Center:

    -   "[Enforcing Strong Password Usage Throughout Your Organization](http://www.microsoft.com/smallbusiness/gtm/securityguidance/articles/enforce_strong_passwords.mspx)" (in inglese) all'indirizzo www.microsoft.com/smallbusiness/gtm/securityguidance/
        articles/enforce\_strong\_passwords.mspx.

    -   "[Selecting Secure Passwords](http://www.microsoft.com/smallbusiness/gtm/securityguidance/articles/select_sec_passwords.mspx)" (in inglese) all'indirizzo www.microsoft.com/smallbusiness/gtm/securityguidance/
        articles/select\_sec\_passwords.mspx.

-   Per ulteriori informazioni su come rendere Active Directory più sicuro, vedere:

    -   [Best Practice Guide for Securing Windows Server Active Directory Installations](http://www.microsoft.com/windowsserver2003/techinfo/overview/adsecurity.mspx) (Windows Server 2003) nel sito Web Microsoft disponibile all'indirizzo www.microsoft.com/windowsserver2003/techinfo/overview/adsecurity.mspx.

    -   [Best Practices for Delegating Active Directory Administration](http://technet.microsoft.com/en-us/library/cc773318.aspx) (in inglese) all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/
        technologies/directory/activedirectory/actdid1.mspx.

##### Download

[![](images/Dd536182.icon_exe(it-it,TechNet.10).gif)Guida alla pianificazione del monitoraggio della protezione e della rilevazione degli attacchi](http://go.microsoft.com/fwlink/?linkid=41316)

[](#mainsection)[Inizio pagina](#mainsection)
