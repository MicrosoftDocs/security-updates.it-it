---
TOCTitle: 'Procedure ottimali per l''amministrazione di RMS'
Title: 'Procedure ottimali per l''amministrazione di RMS'
ms:assetid: '385f8112-da00-417f-a2b8-42dc1e06b717'
ms:contentKeyID: 18824569
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720245(v=WS.10)'
---

Procedure ottimali per l'amministrazione di RMS
===============================================

Per l'amministrazione di RMS, è consigliabile attenersi alle seguenti procedure ottimali.

-   **Non distribuire servizi aggiuntivi sui server RMS**
    Se sui server si eseguono servizi diversi dai servizi RMS, possono verificarsi conflitti che possono condurre a problemi di protezione. Utilizzare contatori di prestazioni per rilevare degrado delle prestazioni o conflitti nei servizi.
-   **Eseguire frequenti backup dei database di configurazione**
    I database di configurazione contengono informazioni vitali per il funzionamento di RMS. Nel database di configurazione del cluster di certificazione principale sono inoltre memorizzate le coppie di chiavi per l'intera installazione. Se si eseguono backup regolari, è possibile fare in modi che RMS torni velocemente in funzione se un server di database si ferma. Oltre a eseguire backup regolari, si dovrebbe anche provare regolarmente la validità dei backup eseguendo ripristini a freddo (in un ambiente di test separato). Per ulteriori informazioni, vedere “Backup e ripristino del sistema RMS” nella sezione "Pianificazione di una distribuzione di RMS", in questa documentazione.
-   **Ripulire regolarmente il database di registrazione attività**
-   **Utilizzare Microsoft Operations Manager (MOM) per eseguire il monitoraggio del server RMS**
    Utilizzare MOM e RMS MOM Pack per rilevare eventi critici o degrado nelle prestazioni e inviare notifiche relative a tali eventi.
