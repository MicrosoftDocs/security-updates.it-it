---
TOCTitle: Certificati e licenze RMS
Title: Certificati e licenze RMS
ms:assetid: '91916ecb-9e5d-49e8-ab65-ef2c56339b83'
ms:contentKeyID: 18824699
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747600(v=WS.10)'
---

Certificati e licenze RMS
=========================

I differenti componenti di una installazione di RMS dispongono di connessioni trusted rese disponibili mediante un insieme di certificati. L'applicazione della validità di questi certificati è una delle funzioni principali della tecnologia di RMS. Ogni parte di contenuto protetto con RMS viene pubblicata con una licenza che ne specifica le regole di impiego, e ogni utilizzatore di tale contenuto riceve una licenza univoca che legge, interpreta e controlla l'applicazione delle regole di utilizzo. In questo contesto una licenza rappresenta un tipo particolare di certificato.

RMS utilizza un vocabolario XML per esprimere i diritti di utilizzo del contenuto protetto con RMS, eXtensible rights Markup Language (XrML), versione 1.2.1. Per ulteriori informazioni, vedere “XrML” più avanti in questo argomento.

I certificati e le licenze presenti in RMS sono inseriti in una gerarchia, in modo che RMS possa sempre seguire una catena da un particolare certificato o licenza attraverso i certificati trusted, fino ad arrivare a una coppia di chiavi trusted. Per ulteriori informazioni, vedere "[Gerarchia di trust di RMS](https://technet.microsoft.com/2d44182f-a653-4383-aba1-dade53f7cf9a)" più avanti in questo argomento.

In questa sezione, vengono trattati gli argomenti seguenti:

-   [Riepilogo dei certificati e delle licenze RMS](https://technet.microsoft.com/637ccfca-318e-4346-85b5-0945b058fb9c)
-   [Certificati concessori di licenze server](https://technet.microsoft.com/0b35fbcd-25a9-4587-898d-9a30fd1d3c5b)
-   [Certificato concessore di licenze client](https://technet.microsoft.com/bfb36387-3e15-4cde-8b8f-482219569a64)
-   [Certificati computer RMS](https://technet.microsoft.com/1841d53e-d01b-47c3-9d43-3805ceefed5a)
-   [Certificati per account con diritti](https://technet.microsoft.com/2ff315cc-211d-4e6e-85e8-56867c2abd94)
-   [Licenze di pubblicazione](https://technet.microsoft.com/187228fc-370b-4e23-a53a-21bb296b84a1)
-   [Licenze d'uso](https://technet.microsoft.com/6e609db3-49b3-4cac-a34c-8a96da627067)
