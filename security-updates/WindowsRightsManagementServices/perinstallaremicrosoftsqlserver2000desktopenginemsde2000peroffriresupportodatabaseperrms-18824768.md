---
TOCTitle: 'Per installare Microsoft SQL Server 2000 Desktop Engine (MSDE 2000) per offrire supporto database per RMS'
Title: 'Per installare Microsoft SQL Server 2000 Desktop Engine (MSDE 2000) per offrire supporto database per RMS'
ms:assetid: 'c9b9cd08-98c4-424f-b3fc-d685f57c002e'
ms:contentKeyID: 18824768
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747667(v=WS.10)'
---

Per installare Microsoft SQL Server 2000 Desktop Engine (MSDE 2000) per offrire supporto database per RMS
=========================================================================================================

Installazione di Microsoft SQL Server 2000 Desktop Engine (MSDE 2000) per offrire supporto database per RMS
-----------------------------------------------------------------------------------------------------------

#### Per installare Microsoft SQL Server 2000 Desktop Engine (MSDE 2000) per offrire supporto database per RMS

1.  Effettuare l'accesso tramite un account di dominio che faccia parte del gruppo Administrators locale nel server in cui si desidera installare Microsoft SQL Server 2000 Desktop Engine (MSDE 2000).

2.  Scaricare MSDE 2000 dal [sito Web Microsoft](http://www.microsoft.com/) (http://www.microsoft.com/) e salvarlo sul computer.

3.  Eseguire il file MSDE2000A.exe per estrarre il pacchetto di installazione MSDE 2000 in una cartella. Per impostazione predefinita, la cartella viene denominata MSDERelA, ma è anche possibile specificare un nome diverso.

4.  Aprire un prompt dei comandi e passare al percorso in cui è stata salvata l'installazione MSDE 2000.

5.  Digitare il comando riportato di seguito per configurare Microsoft SQL Server 2000 Desktop Engine con le configurazioni adatte per l'utilizzo con RMS e sostituire la *password* con una password complessa di propria scelta.

    **Setup.exe /i setup\\sqlrun10.msi INSTANCENAME=RMS DISABLEAGENTSTARTUP=1 SAPWD=***password*

    | ![](images/Cc747667.Important(WS.10).gif)Importante                                                                                                                                                                                                                   |
    |----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Il servizio MSDE deve essere avviato subito dopo l'installazione. È possibile avviare il servizio da **Servizi** nel **Pannello di controllo**. È consigliabile configurare l'avvio automatico del servizio per assicurare la disponibilità costante del database MSDE quando RMS è in esecuzione. |

Non eseguire il provisioning di RMS in un server in cui non sia presente un database installato che offra il supporto per il database di configurazione di RMS.

Si raccomanda di utilizzare Microsoft SQL Server Desktop Engine per supportare i database RMS solo in ambienti di test, poiché Microsoft SQL Server Desktop Engine non include gli strumenti necessari per gestire e supportare completamente un database a livello di organizzazione. Inoltre, poiché MSDE non supporta connessioni di rete remote, è necessario installarlo sullo stesso server di RMS e non è possibile aggiungere altri server RMS al cluster RMS. Le condizioni per l'utilizzo di Microsoft SQL Server Desktop Engine specificano che è vietato utilizzare gli strumenti client di SQL Server per modificare un database di Microsoft SQL Server Desktop Engine. Questa limitazione impedisce di eseguire il backup e il ripristino del database di configurazione RMS, visualizzare le informazioni di registrazione o modificare direttamente i dati archiviati nel database di configurazione.
