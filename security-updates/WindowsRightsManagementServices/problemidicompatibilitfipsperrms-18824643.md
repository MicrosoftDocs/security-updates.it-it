---
TOCTitle: Problemi di compatibilità FIPS per RMS
Title: Problemi di compatibilità FIPS per RMS
ms:assetid: '720bdace-dcd8-431e-b0fa-01193782fe0b'
ms:contentKeyID: 18824643
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747551(v=WS.10)'
---

Problemi di compatibilità FIPS per RMS
======================================

Servizi Rights Management (RMS) versione 1.0 Service Pack 1 (SP1) è stato progettato per funzionare in modo efficiente in organizzazioni che richiedono l'utilizzo di funzionalità di crittografia valutate secondo gli standard FIPS.

Federal Information Processing Standard 140-1 (FIPS 140-1) e il successivo FIPS 140-2 sono standard pubblicati dal Governo degli Stati Uniti che forniscono un punto di riferimento per l'implementazione di software di crittografia. Essi specificano le procedure ottimali per implementare algoritmi di crittografia, gestire materiale critico e buffer di dati, nonché per utilizzare il sistema operativo.

RMS può essere implementato come parte di un sistema compatibile con gli standard FIPS per fornire un metodo di protezione dei dati riservati.

-   I provider di servizi di crittografia valutati secondo gli standard FIPS limitano la funzionalità a: **TLS\_RSA\_WITH\_3DES\_EDE\_CBC\_SHA**. Questa limitazione obbliga il provider del canale di protezione a negoziare soltanto il protocollo Transport Layer Security (TLS) 1.0 più restrittivo. Potrebbe essere necessario configurare Internet Explorer affinché supporti TLS, tuttavia numerosi server Web di terze parti non supportano TLS. Per ulteriori informazioni su questo problema, consultare l'articolo 811834 della Knowledge Base sul [sito Web Microsoft](http://go.microsoft.com/fwlink/?linkid=43614).

Se si intende utilizzare una protezione della chiave privata basata su software, proteggere la chiave privata RMS con uno dei due provider di servizi di crittografia (CSP) Microsoft predefiniti. Questi CSP hanno superato la procedura di valutazione FIPS 140-1 o FIPS 140-2 prevista dal Governo degli Stati Uniti. Sebbene non sia indispensabile, è consigliabile che i clienti, per i quali la protezione rappresenta un fattore critico, utilizzino moduli di protezione hardware (come quelli prodotti da nCipher o IBM) per proteggere le chiavi private dei server RMS di livello elevato. Se si utilizzano i moduli HSM, è necessario selezionare il CSP appropriato da usare con il modulo. Questa condizione potrebbe richiedere un riavvio del sistema. Per ulteriori informazioni su questo problema, consultare l'articolo 830690 della Knowledge Base sul [sito Web Microsoft](http://go.microsoft.com/fwlink/?linkid=44138).

Quando si implementa un sistema RMS, è necessario effettuare le seguenti selezioni:

-   Seguire le indicazioni della NSA per selezionare una crittografia compatibile con gli standard FIPS in Windows.
-   Attivare i Criteri di protezione locali per la crittografia compatibile con gli standard FIPS.
-   Distribuire i client e i server RMS SP1 nell'ambiente precedentemente descritto.
-   Abilitare il protocollo Transport Layer Security (TLS) in Internet Information Services sul server RMS.
-   Abilitare il protocollo Transport Layer Security (TLS) in Internet Explorer per i client.
-   Abilitare il protocollo SQL Tabular Data Stream (TDS), utilizzato con il provider di protezione TLS/SSL Windows tra i client SQL e SQL Server sul server database.
-   Configurare SQL in modo da richiedere TSL/SSL
