---
TOCTitle: Utilizzo del gruppo di utenti con privilegi avanzati
Title: Utilizzo del gruppo di utenti con privilegi avanzati
ms:assetid: '0febcb3e-7124-4e51-971a-1013b928d33b'
ms:contentKeyID: 18824520
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720198(v=WS.10)'
---

Utilizzo del gruppo di utenti con privilegi avanzati
====================================================

Durante il processo di provisioning, tramite RMS, viene creato uno speciale gruppo di utenti con privilegi avanzati, i cui membri dispongono di controllo completo su tutti i contenuti protetti con diritti. I membri del gruppo di utenti con privilegi avanzati dispongono di diritti completi per tutte le licenze d'uso emesse dal server o dal cluster RMS in cui è configurato il gruppo stesso. Di conseguenza, i membri di questo gruppo possono decrittografare qualsiasi file con contenuto protetto e rimuoverne la protezione. I membri di questo gruppo possono, ad esempio, rimuovere la protezione dai file che sono stati pubblicati da un ex dipendente per consentirne la pubblicazione e la gestione da parte di un nuovo proprietario.

Nel gruppo di utenti con privilegi avanzati non viene automaticamente incluso alcun membro, neppure gli amministratori. Quando si utilizza il sito Web Amministrazione, è possibile specificare un gruppo di protezione di Active Directory da utilizzare come gruppo di utenti con privilegi avanzati per RMS. È possibile utilizzare un gruppo di Active Directory esistente oppure crearne uno nuovo appositamente per questo scopo. Il gruppo deve essere incluso nella stessa struttura di Active Directory in cui è presente l'installazione di RMS. Agli account utente membri del gruppo specificato come gruppo di utenti con privilegi avanzati per RMS, vengono automaticamente concesse le autorizzazioni del gruppo di cui fanno parte.

Per informazioni sulle modalità di definizione di un gruppo di utenti con privilegi avanzati per RMS, vedere [Per impostare un gruppo di utenti con privilegi avanzati](https://technet.microsoft.com/f2ef847e-2824-471f-9079-5c343094aba8), più avanti in questo argomento.

| ![](images/Cc720198.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Per poter essere designato come gruppo di utenti con privilegi avanzati per RMS, un gruppo deve essere presente nella stessa struttura di Active Directory in cui è presente l'installazione di RMS. Le proprietà del gruppo devono includere un indirizzo di posta elettronica, compreso un nome di dominio completo (FQDN, Fully Qualified Domain Name) uguale al nome account. L'indirizzo di posta elettronica deve essere specificato in base al formato *nome\_gruppo*@*nome\_dominio*. |
