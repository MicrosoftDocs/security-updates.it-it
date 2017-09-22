---
TOCTitle: Per modificare un modello di criteri per i diritti
Title: Per modificare un modello di criteri per i diritti
ms:assetid: '9580b934-bd6f-4097-9d3c-4fc14a3147fa'
ms:contentKeyID: 18824700
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747684(v=WS.10)'
---

Per modificare un modello di criteri per i diritti
==================================================

Per eseguire questa procedura, è necessario avere effettuato l'accesso locale al sito Web di amministrazione con un account utente di dominio che faccia parte del gruppo Administrators nel computer in cui si sta effettuando l'accesso. La procedura può essere inoltre eseguita dai membri del gruppo Domain Admins. Per garantire maggiore protezione, eseguire la procedura utilizzando **Esegui come**.

Per visualizzare la pagina **Amministrazione globale**, fare clic su **Start**, scegliere **Tutti i programmi**, quindi **Windows RMS** e infine **Amministrazione di Windows RMS**.

Modifica di un modello di criteri per i diritti
-----------------------------------------------

#### Per modificare un modello di criteri per i diritti

1.  Visualizzare la pagina **Amministrazione globale** e selezionare **Amministra RMS in questo sito Web** accanto al sito Web in cui si desidera modificare il modello di criteri per i diritti.

2.  Nell'area **Collegamenti per l'amministrazione,** selezionare **Modelli criteri diritti**.

3.  Nel gruppo **Nome modello,** selezionare il nome del modello da modificare.

4.  Nell'area **Identificazione modello,** modificare le informazioni nei campi **Nome modello**, **Descrizione modello** e **URL richiesta diritti** come necessario.

5.  Nell'area **Utenti e gruppi,** effettuare una o più delle seguenti operazioni.

    -   Per aggiungere un utente o un gruppo, in **Aggiungi utenti o gruppi,** digitare un indirizzo di posta elettronica valido di un utente o un gruppo che si desidera aggiungere, scegliere **Aggiungi** e selezionare il nome in **Utenti o gruppi correnti**. Nell'area **Diritti,** selezionare tutti i diritti che si desidera concedere all'utente o al gruppo selezionato.
    -   Per modificare i diritti di un gruppo o di un utente esistente, selezionare il nome in **Utenti o gruppi correnti** e selezionare o deselezionare le caselle di controllo come necessario.
    -   Per rimuovere un utente o un gruppo, selezionare il nome in **Utenti o gruppi correnti** e scegliere **Rimuovi**.

6.  Nell'area **Criterio scadenza,** modificare le informazioni per cambiare la scadenza delle licenze per i contenuti e la frequenza di rinnovo, come necessario.

7.  Nell'area **Criterio esteso,** modificare le informazioni per cambiare le modalità di implementazione delle licenze dei contenuti, incluse le opzioni relative a durata dei diritti d'autore, supporto dei browser attendibili, durata della licenza nei contenuti e utilizzo di dati specifici dell'applicazione, come necessario.

8.  Nell'area **Criterio revoca,** specificare se per i contenuti creati tramite il modello è necessario un elenco di revoche. Qualora si selezioni **Richiedi revoca**, completare le impostazioni seguenti, in base a quanto necessario.

    -   Nella casella **URL**, digitare l'URL in cui è inserito il file dell'elenco di revoche. Se si desidera offrire supporto agli utenti disconnessi o esterni, tale URL deve essere accessibile sia dalla rete aziendale che da Internet. Per ulteriori informazioni, vedere "[Implementazione delle revoche](https://technet.microsoft.com/4735f060-7197-4ae2-830a-f91bcc4de30a)" più indietro in questo argomento.
    -   In **Intervallo di aggiornamento elenco revoche,** digitare il numero di giorni desiderati per la validità dell'elenco di revoche. Qualora un utente disponga di una copia dell'elenco meno recente rispetto al valore specificato, dovrà ottenere una copia aggiornata per utilizzare il contenuto.
    -   In **Chiave pubblica elenco revoche,** digitare il percorso e il nome del file della chiave pubblica per l'elenco di revoche. Per ulteriori informazioni su questo file, vedere "Aggiunta di una firma in un elenco di revoche", più indietro in questo argomento.

    | ![](images/Cc747684.Caution(WS.10).gif)Attenzione                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
    |---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Prestare attenzione quando si applicano le revoche. In base all'intervallo di aggiornamento specificato, è necessario rinnovare l'elenco di revoche periodicamente affinché non scada automaticamente impedendo di conseguenza agli utenti di utilizzare i contenuti che richiedono tale elenco. Per assicurarsi di non impedire involontariamente agli utenti di utilizzare i contenuti, valutare attentamente l'intervallo necessario per l'aggiornamento dell'elenco di revoche. Per ulteriori informazioni, vedere "[Gestione delle revoche](https://technet.microsoft.com/df732a7d-1fb0-4845-87ca-fab4bc5f98a0)" più indietro in questo argomento. |

9.  Scegliere **Invia**.

Per osservazioni sul modo per eseguire questa procedura, vedere "[Creazione e modifica dei modelli di criteri per i diritti](https://technet.microsoft.com/6014176f-ef71-4d29-b3e3-da129c18563d)" più indietro in questo argomento.
