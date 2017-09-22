---
TOCTitle: Certificati per account con diritti
Title: Certificati per account con diritti
ms:assetid: '2ff315cc-211d-4e6e-85e8-56867c2abd94'
ms:contentKeyID: 18824544
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720230(v=WS.10)'
---

Certificati per account con diritti
===================================

Le organizzazioni devono identificare gli utenti che sono entità trusted all'interno del sistema RMS. Per fare ciò, RMS permette l'emissione dei certificati per account con diritti che associano gli account utente a computer specifici. Il certificato per account con diritti dell'utente deve essere incluso nelle richieste di certificati concessore di licenze client e licenze d'uso. Mediante il certificato concessore di licenze client, l'autore può pubblicare il contenuto protetto con RMS, ad esempio file e messaggi elettronici, anche quando non è in linea. Con la licenza d'uso, l'utente è in grado di utilizzare il contenuto protetto con RMS. In ogni certificato per account con diritti è presente la chiave pubblica dell'utente, la quale viene impiegata per crittografare i dati destinati all'utente.

Esistono due tipi di certificati per account con diritti, standard e temporaneo. È possibile specificare il periodo di validità per entrambi i tipi. I certificati standard hanno una durata che viene espressa in giorni (l'impostazione predefinita è 365 giorni). I certificati per account temporanei hanno una durata che viene espressa in minuti (l'impostazione predefinita è 15 minuti). I certificati temporanei per account consentono agli utenti di utilizzare il contenuto temporaneamente, ad esempio in un computer pubblico, quando non possono accedere al computer normalmente utilizzato. In questo modo è possibile evitare che un altro utente utilizzi il contenuto da questo computer in un secondo momento.
