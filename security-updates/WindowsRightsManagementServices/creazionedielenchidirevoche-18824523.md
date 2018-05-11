---
TOCTitle: Creazione di elenchi di revoche
Title: Creazione di elenchi di revoche
ms:assetid: '1ef75199-3344-4225-84de-a863a777696a'
ms:contentKeyID: 18824523
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720208(v=WS.10)'
---

Creazione di elenchi di revoche
===============================

Per implementare le revoche, è necessario distribuire un elenco di revoche, costituito da un documento XML in cui viene utilizzato il linguaggio XrML (eXtensible Rights Markup Language) e in cui sono elencate le entità che non devono più disporre dell'accesso ai contenuti protetti con RMS. È necessario creare elenchi di revoche che includano indicazioni di data e firma appropriate tramite lo strumento per la firma degli elenchi di revoche (RLsigner.exe) incluso in RMS.

| ![](images/Cc720208.Important(WS.10).gif)Importante                                                 |
|----------------------------------------------------------------------------------------------------------------------------------|
| Per firmare l'elenco di revoche utilizzando RLsigner.exe, è necessario salvare il file dell'elenco di revoche come file unicode. |

Esempio di elenco di revoche
----------------------------

In questo argomento viene riportato un esempio di un elenco di revoche completo che consente di illustrare tutti i possibili meccanismi di revoca. L'esempio può essere utilizzato come modello per la creazione di elenchi di revoche personalizzati.

Un elenco di revoche è un file XML che utilizza il linguaggio XrML.

L'elemento BODY include quattro elementi figlio.

-   **ISSUEDTIME**. Contiene la data e l'ora del rilascio dell'elenco di revoche. RLsigner.exe inserisce questo elemento nel file; l'elemento viene fornito nell'esempio solo per illustrare la struttura globale del file dell'elenco di revoche.
-   **DESCRIPTOR**. Contiene i dati che identificano il file come elenco di revoche.
-   **ISSUER**. Contiene i dati che identificano l'entità che ha emesso l'elenco di revoche.
-   **REVOCATIONLIST**. Contiene gli elementi figlio di REVOKE in cui sono specificate le entità revocate dall'elenco.

Di seguito è riportato un file di elenco di revoche di esempio.

| ![](images/Cc720208.note(WS.10).gif)Nota                                                                                                                                                         |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Gli elementi ISSUEDTIME, PUBLICKEY e SIGNATURE possono essere omessi, poiché vengono inseriti o sovrascritti da RLsigner.exe. |

```
<?xml version="1.0" ?> 
<XrML xml:space=”preserve” version=”1.2”>
  <BODY type="LICENSE" version="3.0">
    <ISSUEDTIME>...</ISSUEDTIME> 
    <DESCRIPTOR>
      <OBJECT type="Revocation-List">
        <ID type="MS-GUID">{d6373cba-01f1-4f32-ac58-260f580af0f8}</ID>
      </OBJECT>
    </DESCRIPTOR>
<ISSUER>
      <OBJECT type="Revocation-List">
        <ID type="acsii-tag">External revocation authority</ID>
        <NAME>Revocation list name</NAME>
        <ADDRESS type="URL">https://somedomain.com/revocation_list_file</ADDRESS>
      </OBJECT>
      <PUBLICKEY>...</PUBLICKEY>
    </ISSUER>
  <REVOCATIONLIST>
    <REVOKE>...<\REVOKE>
    <REVOKE>...<\REVOKE>
  </REVOCATIONLIST>
  <SIGNATURE>...</SIGNATURE>
</XrML>
```

| ![](images/Cc720208.Caution(WS.10).gif)Attenzione                                                                           |
|----------------------------------------------------------------------------------------------------------------------------------------------------------|
| Quando si specifica l'URL nell'elenco di revoche, il percorso UNC non viene più supportato in RMS con SP1 o RMS con SP2. È necessario utilizzare un URL. |

Dopo avere definito gli elementi REVOKE, è necessario firmare l'elenco di revoche.

Utilizzo dell'elemento REVOKE
-----------------------------

Nell'elenco di revoche di esempio nella sezione Esempio di elenco di revoche ciascun elemento REVOKE specifica un'entità da revocare. In ogni tag di apertura, gli attributi di tipo e categoria definiscono l'elemento revocato e il criterio di identificazione utilizzato. Elementi REVOKE diversi includono elementi figlio diversi, in base all'azione specificata dagli attributi di tipo e categoria.

Per ulteriori informazioni su come specificare gli elementi REVOKE, vedere gli esempi riportati di seguito.

-   [Revoca di entità in base a una chiave pubblica](#bkmk_1)
-   [Revoca di certificati e licenze in base al GUID](#bkmk_2)
-   [Revoca di certificati e licenze in base al valore hash](#bkmk_3)
-   [Revoca di certificati e licenze in base alla chiave pubblica dell'emittente](#bkmk_4)
-   [Revoca di certificati e licenze in base all'ID dell'emittente](#bkmk_5)
-   [Revoca di contenuti in base al relativo ID](#bkmk_6)
-   [Revoca di certificati in base all'ID dell'entità](#bkmk_10)
-   [Revoca di entità in base a Windows Live ID](#bkmk_7)

#### Revoca di entità in base a una chiave pubblica
Nell'esempio che segue, viene revocata un'entità in base alla chiave pubblica relativa. Il contenuto del tag <PUBLICKEY> deriva dal nodo <BODY><ISSUEDPRINCIPALS><PRINCIPAL><PUBLICKEY> del certificato che ha emesso la chiave.

```
<REVOKE category="principal" type="principal-key">
        <PUBLICKEY>
          <ALGORITHM>RSA-1024</ALGORITHM>
          <PARAMETER name="public exponent">
            <VALUE encoding="integer32">65537</VALUE>
          </PARAMETER>
          <PARAMETER name="modulus">
            <VALUE encoding="base64" size="1024">
6Jn0kEAWU+1AFWtuUmBYL8Jza8tLhUv/BCmgcq/Pc08Au3DvXkH65s+0MEyZjM+71j3F1xaXUSst+wH2FjApkY1RxgL8VAKIuEvIy9hRrvY1YhJx/0Ite5fZeg2crUFrmoQgZzaJ50FvoakA2QMgZZgxoQmwiGE0y40cEJtIlE0=
            </VALUE>
          </PARAMETER>
        </PUBLICKEY>
      </REVOKE>
```

#### Revoca di certificati e licenze in base al GUID
Nell'esempio che segue, viene revocato un certificato o una licenza in base all'identificatore univoco globale (GUID, Globally Unique Identifier). Quando viene utilizzato questo elenco di revoche, non è possibile utilizzare un certificato o una licenza con un GUID corrispondente. Il contenuto del tag <ID> in questo esempio deriva dal nodo <BODY><DESCRIPTOR><OBJECT><ID> del certificato o della licenza da revocare.. È inoltre possibile revocare le applicazioni tramite questo meccanismo specificando l'ID del file manifesto dell'applicazione.

```
<REVOKE category="license" type="license-id">
        <OBJECT>
          <ID type="MS-GUID">{06BCB94D-43E5-419f-B180-AA9FD321ED7A}</ID>
        </OBJECT>
      </REVOKE>
```

#### Revoca in base al file manifesto dell'applicazione

Per eseguire una revoca utilizzando il file manifesto dell'applicazione, estrarre l'ID dell'emittente, la chiave pubblica dell'emittente, l'ID della licenza o l'hash della licenza dal file manifesto dell'applicazione. Tuttavia, i manifesti dell'applicazione sono codificati su base 64, quindi le informazioni non vengono visualizzate in testo semplice. Con il SDK (Software Development Kit) di Microsoft Windows Rights Management Services, è possibile sviluppare un programma utilizzando i metodi DRMConstructCertificateChain, DRMDeconstructCertificateChain e DRMDecode per decodificare il file manifesto dell'applicazione e ottenere le informazioni richieste.

Per non consentire l'uso del contenuto protetto con RMS a determinate applicazioni, è possibile utilizzare la funzione di esclusione, grazie alla quale viene impedito al cluster RMS di concedere licenze d'uso a tali applicazioni. Il limite della funzione consiste nel fatto che non può impedire la decrittografia del contenuto protetto con RMS da parte di utenti con licenze d'uso valide. Per ulteriori informazioni sull'esclusione di applicazioni, vedere [Esclusione di applicazioni](https://technet.microsoft.com/b68ae4b2-b9ba-44ae-90cb-c88df600ec86), più indietro in questo argomento.

#### Revoca di certificati e licenze in base al valore hash

Nell'esempio che segue, viene revocato un certificato o una licenza in base al relativo hash. Il contenuto del tag \<VALUE\> è costituito dall'hash SHA-1 dei caratteri UNICODE presenti da \<BODY\> a \</BODY\>, compresi, nel certificato o nella licenza. Il valore hash può essere individuato nella sezione \<SIGNATURE\> del certificato o della licenza. È inoltre possibile revocare le applicazioni tramite questo meccanismo specificando l'hash del file manifesto dell'applicazione.

```
<REVOKE category="license" type="license-hash">
        <DIGEST>
          <ALGORITHM>SHA1</ALGORITHM>
          <VALUE encoding="base64" size="160">
            ABfB4mcEslVCMEZR9reACqXHCoQ=
          </VALUE>
        </DIGEST>
      </REVOKE>
```

#### Revoca in base al file manifesto dell'applicazione

Per eseguire una revoca utilizzando il file manifesto dell'applicazione, estrarre l'ID dell'emittente, la chiave pubblica dell'emittente, l'ID della licenza o l'hash della licenza dal file manifesto dell'applicazione. Tuttavia, i manifesti dell'applicazione sono codificati su base 64, quindi le informazioni non vengono visualizzate in testo semplice. Con il SDK di Rights Management Services, è possibile sviluppare un programma utilizzando i metodi DRMConstructCertificateChain, DRMDeconstructCertificateChain e DRMDecode per decodificare il file manifesto dell'applicazione e ottenere le informazioni richieste.

Per non consentire l'uso del contenuto protetto con RMS a determinate applicazioni, è possibile utilizzare la funzione di esclusione, grazie alla quale viene impedito al cluster RMS di concedere licenze d'uso a tali applicazioni. Il limite di questa funzione consiste nel non poter evitare la decrittografia del contenuto protetto con RMS da parte di utenti con licenze d'uso valide. Per ulteriori informazioni sull'esclusione di applicazioni, vedere [Esclusione di applicazioni](https://technet.microsoft.com/b68ae4b2-b9ba-44ae-90cb-c88df600ec86), più indietro in questo argomento.

#### Revoca di certificati e licenze in base alla chiave pubblica dell'emittente

Nell'esempio che segue vengono revocati tutti i certificati e le licenze emessi dal proprietario della chiave pubblica specificata. Il contenuto del tag <PUBLICKEY> deriva dal nodo \<BODY\>\<ISSUER\>\<PUBLICKEY\> dei certificati o delle licenze da revocare.

```
<REVOKE category="license" type="issuer-key">
        <PUBLICKEY>
          <ALGORITHM>RSA-1024</ALGORITHM>
          <PARAMETER name="public exponent">
            <VALUE encoding="integer32">65537</VALUE>
          </PARAMETER>
          <PARAMETER name="modulus">
            <VALUE encoding="base64" size="1024">
AAn0kEAWU+1AFWtuUmBYL8Jza8tLhUv/BCmgcq/Pc08Au3DvXkH65s+0MEyZjM+71j3F1xaXUSst+wH2FjApkY1RxgL8VAKIuEvIy9hRrvY1YhJx/0Ite5fZeg2crUFrmoQgZzaJ50FvoakA2QMgZZgxoQmwiGE0y40cEJtIlE0=
            </VALUE>
          </PARAMETER>
        </PUBLICKEY>
      </REVOKE>
```

#### Revoca di certificati e licenze in base all'ID dell'emittente

Nell'esempio che segue viene revocato un insieme di certificati o licenze in base all'ID dell'emittente. Il contenuto del tag \<ID\> deriva dal nodo \<BODY\>\<ISSUER\>\<OBJECT\>\<ID\> dei certificati o delle licenze da revocare.

```
<REVOKE category="license" type="issuer-id">
        <OBJECT type="MS-DRM-Server">
          <ID type="MS-GUID">{2BE9E200-3040-41B9-8832-D4D0445EBBD6}</ID> 
        </OBJECT>
      </REVOKE>
```

| ![](images/Cc720208.note(WS.10).gif)Nota                                                                
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Quando si specifica il tipo di ID, assicurarsi che non vi sia un ritorno a capo tra l'identificatore univoco globale (GUID) e il tag di chiusura. Se è stato aggiunto inavvertitamente un ritorno a capo, il client RMS non sarà in grado di analizzare l'elenco di revoche. |

#### Revoca di contenuti in base al relativo ID

Nell'esempio che segue vengono revocati contenuti protetti in base al relativo ID. Si tratta del metodo ottimale per la revoca dei contenuti, in quanto l'ID del contenuto è lo stesso per tutte le licenze d'uso create con una determinata licenza di pubblicazione. Il valore del nodo \<OBJECT\> può essere individuato nel nodo \<BODY\>\<WORK\>\<OBJECT\> di una licenza di pubblicazione o di una licenza d'uso per il contenuto.

```
<REVOKE category="content" type="content-id">
        <OBJECT type="Microsoft Office Document">
          <ID type="MS-GUID">{8702641D-3512-4AA4-A584-84C703A5B5C0}</ID>
        </OBJECT>
      </REVOKE>
```

| ![](images/Cc720208.note(WS.10).gif)Nota                                                                                                                                                                                                        |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Quando si specifica il tipo di ID, assicurarsi che non vi sia un ritorno a capo tra l'identificatore univoco globale (GUID) e il tag di chiusura. Se è stato aggiunto inavvertitamente un ritorno a capo, il client RMS non sarà in grado di analizzare l'elenco di revoche. |

#### Revoca di entità in base all'account di Windows

Nell'esempio che segue viene revocato un utente o un'entità di abilitazione in base al relativo account di Windows. Il contenuto dell'elemento \<OBJECT\> deriva dal nodo \<BODY\>\<ISSUEDPRINCIPALS\>\<PRINCIPAL\>\<OBJECT\> di un certificato per account con diritti o di una licenza d'uso.

```
<REVOKE category="principal" type="principal-id">
        <OBJECT type="Group-Identity">
          <ID type="Windows">{Windows account SID}</ID> 
          <NAME>{E-mail address}</NAME> 
        </OBJECT>
      </REVOKE>
```

| ![](images/Cc720208.note(WS.10).gif)Nota                                                                                                                                                                                               |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Quando si specifica il tipo di ID, assicurarsi che non vi sia un ritorno a capo tra il SID dell'account di Windows e il tag di chiusura. Se è stato aggiunto inavvertitamente un ritorno a capo, il client RMS non sarà in grado di analizzare l'elenco di revoche. |

#### Revoca di entità in base a Windows Live ID

In questo esempio viene revocato un utente o un'entità di abilitazione in base al relativo Windows Live ID. Il contenuto dell'elemento \<OBJECT\> deriva dal nodo \<BODY\>\<ISSUEDPRINCIPALS\>\<PRINCIPAL\>\<OBJECT\> di un certificato per account con diritti o di una licenza d'uso.

```
<REVOKE category="principal" type="principal-id">
        <OBJECT type="Group-Identity">
          <ID type="Passport">{PUID}</ID> 
          <NAME>michael@contoso.com</NAME> 
        </OBJECT>
      </REVOKE>
```

| ![](images/Cc720208.note(WS.10).gif)Nota                                                                                                                                                                                                           |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Quando si specifica il tipo di ID, assicurarsi che non vi sia un ritorno a capo tra l'identificatore univoco principale (PUID) e il tag di chiusura. Se è stato aggiunto inavvertitamente un ritorno a capo, il client RMS non sarà in grado di analizzare l'elenco di revoche. |

Aggiunta di una firma in un elenco di revoche
---------------------------------------------

Al termine della creazione di un elenco di revoche, è necessario inserire una firma, come descritto nel presente argomento. È quindi possibile rendere l'elenco di revoche disponibile per gli utenti dall'URL specificato nel modello di criteri per i diritti associato.

Il primo passaggio da eseguire per inserire una firma consiste nella generazione di una coppia di chiavi e di un file della chiave per l'elenco di revoche con lo strumento Sn.exe. Lo strumento Sn.exe è disponibile nell'SDK di Microsoft .NET Framework 1.1 nel sito Web Microsoft all'indirizzo [http://go.microsoft.com/fwlink/?LinkId=104796](http://go.microsoft.com/fwlink/?linkid=104796).

Per firmare il file dell'elenco di revoche utilizzando RLsigner.exe, è necessario che sia stato salvato come file unicode.

**Per utilizzare Sn.exe sia per generare una nuova coppia di chiavi che per scrivere tale coppia in un file**
1.  Creare la chiave privata. Al prompt dei comandi digitare il comando seguente e premere INVIO:

    **sn -k** *file\_chiave\_privata***.snk**

    dove *file\_chiave\_privata* rappresenta il nome del file della chiave.

2.  Utilizzare Sn.exe per estrarre la chiave pubblica dal file della coppia di chiavi creato nel passaggio 1 ed esportarla in un file separato. Digitare il comando seguente e quindi premere INVIO:

    **sn -p** *file\_chiave\_privata file\_chiave\_pubblica*

    dove *file\_chiave\_privata* rappresenta il nome del file della chiave privata creato nel passaggio 1 e *file\_chiave\_pubblica* rappresenta il nome del file in cui verrà memorizzata la chiave pubblica esportata.

3.  Modificare l'estensione del file della chiave privata creato nel passaggio 1 da .snk in .dat per consentirne l'utilizzo con RLsigner.exe.

4.  Utilizzare RLsigner.exe per inserire una firma nel file dell'elenco di revoche. Questo strumento è incluso in RMS. Per impostazione predefinita, lo strumento si trova nella directory %systemdrive%\\Programmi\\Windows Rights Management Services\\Tools.

| ![](images/Cc720208.note(WS.10).gif)Nota |
|-----------------------------------------------------------------------|
| RLsigner.exe non supporta nomi di file contenenti spazi.              |

<span id="BKMK_9"></span>
Utilizzo di RLsigner.exe
------------------------

Quando si esegue RLsigner.exe, viene innanzitutto creata una firma utilizzando la chiave privata inclusa nel file della chiave. Viene quindi creato un file di output basato sul file dell'elenco di revoche specificato.

| ![](images/Cc720208.Important(WS.10).gif)Importante                                  |
|-------------------------------------------------------------------------------------------------------------------|
| Per utilizzare RLsigner.exe, è necessario che il file dell'elenco di revoche sia stato salvato come file unicode. |

Per utilizzare RLsigner.exe per firmare un elenco di revoche, digitare il comando seguente al prompt dei comandi:

**rlsigner.exe***file\_input***{-f***file\_chiave***| -h***nome\_contenitore***CSP}***file\_output*

Utilizzare le informazioni seguenti per completare i parametri di input del comando:

###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Parametro</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><em>file_input</em></td>
<td style="border:1px solid black;">Nome del file dell'elenco di revoche preparato compatibile con XrML.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><em>file_chiave</em></td>
<td style="border:1px solid black;">Nome del file in cui sono presenti le chiavi pubblica e privata generate.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><em>nome_contenitore</em></td>
<td style="border:1px solid black;">Nome del contenitore della chiave</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><em>file_output</em></td>
<td style="border:1px solid black;">Nome del file dell'elenco di revoche firmato che verrà creato dallo strumento.</td>
</tr>
</tbody>
</table>
  
| ![](images/Cc720208.note(WS.10).gif)Nota |  
|-----------------------------------------------------------------------|  
| RLsigner.exe non supporta nomi di file che contengono spazi.          |
  
Nell'esempio che segue viene illustrato come utilizzare RLsigner.exe al prompt dei comandi con diversi provider del servizio di crittografia.
  
-   Esempio di sintassi della riga di comando in cui viene utilizzato un file della chiave:  
    **rlsigner.exe rl.xml -f key.dat output.xml**  
-   Esempio di sintassi della riga di comando in cui viene utilizzato un modulo di protezione hardware:  
    **rlsigner.exe rl.xml -h Container CSP output.xml**
  
Nel codice restituito dallo strumento RLsigner.exe vengono segnalati i principali errori e messaggi di corretto completamento delle operazioni. Nella tabella che segue vengono illustrati i possibili codici restituiti.
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Codice restituito</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">0</td>
<td style="border:1px solid black;">Operazione completata</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">-1</td>
<td style="border:1px solid black;">Impossibile leggere il file di origine</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">-2</td>
<td style="border:1px solid black;">Impossibile leggere il file della chiave</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">-3</td>
<td style="border:1px solid black;">File della chiave non valido</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">-4</td>
<td style="border:1px solid black;">File di origine non valido</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">-5</td>
<td style="border:1px solid black;">Impossibile scrivere nel file di output</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">-6</td>
<td style="border:1px solid black;">Errore sconosciuto</td>
</tr>
</tbody>
</table>
  
È possibile pianificare la firma degli elenchi di revoche in base alla frequenza di aggiornamento specificata per il server.
  
È possibile rendere automatico il processo di firma degli elenchi di revoche tramite uno script. Nell'esempio che segue, tramite VBScript, viene chiamato RLsigner.exe e i risultati vengono scritti nel Registro eventi sistema.
  
```VB
const EVT_SUCCESS       = 0
const EVT_ERROR         = 1  
const EVT_WARNING       = 2  
const EVT_INFORMATION   = 4  
const EVT_AUDIT_SUCCESS = 8  
const EVT_AUDIT_FAILURE = 16  

Dim WshShell, oExec

Set WshShell = CreateObject( "WScript.Shell" )
Set oExec = WshShell.Exec("rlsigner.exe input_file key_file output_file")
Do While oExec.Status = 0
     WScript.Sleep 100
Loop

if WshShell.ExitCode <> 0 Then
    WshShell.LogEvent EVT_ERROR, "RLsigner failed with error """ + WshShell.ExitCode + """"
else
    WshShell.LogEvent EVT_SUCCESS, "RLsigner completed successfully"
end if
```
