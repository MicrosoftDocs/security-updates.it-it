---
TOCTitle: Revoca dei certificati concessore di licenze server
Title: Revoca dei certificati concessore di licenze server
ms:assetid: '8020861d-d196-4431-8282-044675ef5616'
ms:contentKeyID: 18824671
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747578(v=WS.10)'
---

Revoca dei certificati concessore di licenze server
===================================================

Un'organizzazione potrebbe dover revocare un certificato concessore di licenze server a causa di circostanze impreviste che determinano l'impossibilità di utilizzare in modo appropriato il server RMS. Una chiave privata non conservata in un modulo di protezione hardware potrebbe essere stata rubata. Un certificato concessore di licenze server e la sua chiave potrebbero essere compromessi in un'organizzazione da parte di un aggressore che si impadronisca del controllo del server, oppure un dipendente scontento potrebbe rimuovere il certificato o la chiave. La revoca rappresenta un metodo per limitare i danni e il cattivo utilizzo da parte di utenti malintenzionati.

Per impostazione predefinita, ogni licenza o certificato può essere revocato dall'entità che lo ha emesso. Poiché dai server RMS vengono emessi licenze e certificati associati ai contenuti protetti, è sempre possibile revocarli laddove necessario. Se un server licenze viene compromesso, è possibile revocarne il certificato concessore di licenze server. Quando si revoca un certificato concessore di licenze server, anche tutti i certificati e le licenze emessi non sono più validi. Le istruzioni per la revoca di licenze e certificati sono fornite in “[Implementazione delle revoche](https://technet.microsoft.com/4735f060-7197-4ae2-830a-f91bcc4de30a)”, più indietro in questo argomento.

Il cluster di certificazione principale rappresenta tuttavia un caso particolare. Il certificato concessore di licenze server per il cluster di certificazione principale viene emesso dal Servizio di Enrollment Microsoft e, per impostazione predefinita, tale certificato può essere revocato soltanto dal Servizio di Enrollment Microsoft.

Il certificato concessore di licenze server di un server di certificazione principale può essere revocato da Microsoft solo se si riesce a ottenere da un tribunale un'ordinanza in tal senso e si fornisce al tribunale la chiave pubblica del server. Quando il tribunale notifica a Microsoft che è stato emessa un'ordinanza di revoca, Microsoft inserisce il certificato concessore di licenze server nel proprio elenco di revoche specificandone la chiave pubblica e rende disponibile pubblicamente l'elenco. È possibile richiedere a un tribunale un'ordinanza di revoca se si verifica una delle condizioni seguenti in relazione al server la cui licenza deve essere revocata.

-   La richiesta proviene dal proprietario del server e la chiave provata risulta compromessa.
-   La richiesta proviene dal proprietario del contenuto pubblicato sul server e il contenuto è stato pubblicato violando il copyright.

Seguire la procedura descritta in “[Distribuzione di elenchi di revoche](https://technet.microsoft.com/e331338b-66d4-45e4-8d3f-acccf2302ac4)”, più indietro in questa sezione, per ottenere da Microsoft e distribuire elenchi di revoche comprendenti il certificato concessore di licenze server revocato di un server di certificazione principale .

Quando si esegue il provisioning del server di certificazione principale, è possibile specificare una chiave pubblica autorizzata a revocare il certificato concessore di licenze server del cluster di certificazione principale. La chiave pubblica può appartenere all'organizzazione o a una terza parte. Tramite un elenco di revoche firmato con la corrispondente chiave privata, è possibile revocare il certificato concessore di licenze server.

Per revocare il certificato concessore di licenze server del server di certificazione principale, è possibile creare un elenco di revoche in cui sia specificato il certificato concessore di licenze server, firmarlo con la chiave privata dell'organizzazione o della terza parte e quindi distribuire l'elenco di revoche a tutti gli utenti. Per le istruzioni, vedere “Distribuzione di elenchi di revoche aziendali” in “[Distribuzione di elenchi di revoche](https://technet.microsoft.com/e331338b-66d4-45e4-8d3f-acccf2302ac4)”, più indietro in questo argomento.

Per revocare un certificato concessore di licenze server in un elenco di revoche, utilizzare i seguenti parametri.

-   **GUID**. È possibile revocare un certificato concessore di licenze server in base al relativo identificatore univoco globale (GUID, Globally Unique Identifier). Per informazioni sull'uso di questo parametro in un elenco di revoche, vedere “Revoca di certificati e licenze in base al GUID” in "[Creazione di elenchi di revoche](https://technet.microsoft.com/1ef75199-3344-4225-84de-a863a777696a)", più indietro in questo argomento.
-   **Valore hash**. È possibile revocare un certificato concessore di licenze server in base all'hash SHA-1 dei caratteri Unicode presenti nel corpo del certificato. Per informazioni sull'uso di questo parametro in un elenco di revoche, vedere “Revoca di certificati e licenze in base al valore hash” in "[Creazione di elenchi di revoche](https://technet.microsoft.com/1ef75199-3344-4225-84de-a863a777696a)", più indietro in questo argomento.

Per ottenere un certificato concessore di licenze server di un'installazione di RMS, eseguire una query nel database di configurazione di RMS. Nella procedura seguente, viene illustrato come ottenere queste informazioni da un database di configurazione SQL e salvarle in un file che possa essere letto con semplicità tramite un browser.

1.  Aprire SQL Query Analyzer e quindi connettersi al database di configurazione del server di certificazione principale.
2.  Scegliere **Risultati in formato testo** dal menu **Query**.
3.  Scegliere **Opzioni** dal menu **Strumenti** per visualizzare la finestra di dialogo **Opzioni**. Fare clic sulla scheda **Risultati** e quindi impostare **Numero massimo di caratteri per colonna** su **8192**.

```
select DRMS_XrML_Certificate.s_certificate from DRMS_XrML_Certificate, DRMS_LicensorCertificate, DRMS_ClusterConfiguration where DRMS_ClusterConfiguration.CurrentLicensorCertID = DRMS_LicensorCertificate.i_CertID and DRMS_LicensorCertificate.i_CertificateID = DRMS_XrML_Certificate.i_CertificateID
```

1.  Copiare i risultati dalla finestra **Risultati** e incollarli in un editor di testo, ad esempio Blocco note. Salvare i risultati in un file con estensione xml.

Per ulteriori informazioni sull'utilizzo di queste informazioni per un elenco di revoche, vedere “[Creazione di elenchi di revoche](https://technet.microsoft.com/1ef75199-3344-4225-84de-a863a777696a)”, più indietro in questo argomento.

Dopo aver salvato le informazioni del certificato concessore di licenze server come file XML, è possibile estrarre dal file la chiave pubblica eseguendo la procedura descritta di seguito.

1.  Aprire il file XML del certificato concessore di licenze server in un editor di file XML o di file di testo.
2.  Nella sezione &lt;ISSUEDPRINCIPALS&gt;, copiare l'elemento &lt;PUBLICKEY&gt;.
3.  Salvare queste informazioni in un file che possa essere inviato a un tribunale o inserito in un elenco di revoche aziendale.

Quando viene revocato un certificato concessore di licenze server del server di certificazione principale, anche tutti i certificati e le licenze emessi dall'installazione di RMS perdono la validità per quanto riguarda il contenuto che richiede un elenco di revoche. Tale contenuto diventerà di conseguenza inaccessibile. Questo processo è indipendente dal tipo di licenza di cui dispone l'utente. Per conservare il contenuto pubblicato dal server la cui licenza deve essere revocata, è necessario eseguire una delle operazioni seguenti prima di implementare l'elenco di revoche.

-   Salvare il contenuto senza la protezione RMS.
-   Ripubblicare il contenuto senza specificare come requisito l'elenco di revoche.

Sia nel caso di revoca da parte di Microsoft che di una terza parte, l'elenco di revoche viene applicato a tutte le richieste di binding, in quanto è stato firmato dalla chiave privata di un'entità nella catena di trust della licenza d'uso. Tutte le richieste di binding che prevedano licenze emesse dall'installazione di RMS per le quali viene utilizzato il certificato concessore di licenze server revocato avranno pertanto esito negativo.

| ![](images/Cc747578.note(WS.10).gif)Nota                                                            |
|----------------------------------------------------------------------------------------------------------------------------------|
| Il certificato concessore di licenze server verrà revocato da Microsoft solo a seguito di un'ordinanza da parte di un tribunale. |
