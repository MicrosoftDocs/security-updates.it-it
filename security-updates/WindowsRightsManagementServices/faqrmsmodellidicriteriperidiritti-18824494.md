---
TOCTitle: 'FAQ - RMS: Modelli di criteri per i diritti'
Title: 'FAQ - RMS: Modelli di criteri per i diritti'
ms:assetid: '01515f08-9844-4c1a-9ab5-a5a60a901b50'
ms:contentKeyID: 18824494
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720175(v=WS.10)'
---

FAQ - RMS: Modelli di criteri per i diritti
===========================================

FAQ - Modelli di RMS
--------------------

-   [È possibile applicare un modello RMS predefinito su tutto il contenuto creato all'interno di un'organizzazione, in modo che l'organizzazione possa garantire un insieme minimo di diritti?](#bkmk_57)
-   [Dove si trovano i modelli dei criteri RMS?](#bkmk_58)
-   [Quando vengono creati, ai modelli sono collegati alias utente ed elenchi di distribuzione (DL). Un'organizzazione con più reparti come può fornire modelli degli stessi diritti di base, ma concedere tali diritti a gruppi diversi in funzione del contenuto?](#bkmk_59)
-   [I diritti applicati a un documento sono statici? Se un file viene inviato e in seguito si rivela necessario modificare i diritti, si può eseguire questa operazione se la licenza di pubblicazione è incorporata nel file e non sul server "criteri" RMS?](#bkmk_60)

<span id="BKMK_57"></span>
#### È possibile applicare un modello RMS predefinito su tutto il contenuto creato all'interno di un'organizzazione, in modo che l'organizzazione possa garantire un insieme minimo di diritti?

Sì. Con l'SDK di Rights Management Services si può sviluppare un'applicazione personalizzata per applicare un modello richiesto. Tuttavia, l'implementazione di Information Rights Management in Office 2003 e versioni successive non supporta l'applicazione di modelli in base al contenuto.

<span id="BKMK_58"></span>
#### Dove si trovano i modelli dei criteri RMS?

L'ubicazione dei modelli è determinata dall'applicazione abilitata per RMS. Per Office 2003 e versioni successive, è memorizzata come impostazione utente nel registro di sistema, nella seguente posizione:

**HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\11.0\\Common\\DRM\\AdminTemplatePath**

-oppure-

**HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\12.0\\Common\\DRM\\AdminTemplatePath** per Microsoft Office 2007.

| ![](images/Cc720175.note(WS.10).gif)Nota                                                                                                                                         |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Se la voce indica una cartella locale dell'utente, i file dei modelli devono essere copiati sul client. Se la voce indica una cartella di rete condivisa, non sarà disponibile quando l'utente è disconnesso. |

<span id="BKMK_59"></span>
#### Quando vengono creati, ai modelli sono collegati alias utente ed elenchi di distribuzione (DL). Un'organizzazione con più reparti come può fornire modelli degli stessi diritti di base, ma concedere tali diritti a gruppi diversi in funzione del contenuto?

Esistono due soluzioni a questo scenario:

-   Creare un unico modello denominato "Materiale aziendale riservato" fornito su licenza a tutti i dipendenti dell'unità aziendale, quindi utilizzare tale modello in un messaggio di posta elettronica e indirizzarlo alle persone specifiche. Il vantaggio è la necessità di un unico modello per ciascuna unità aziendale per la posta elettronica, i cui utenti possono essere limitati ai destinatari a cui lo si invia. Lo svantaggio è che chiunque al di fuori dal gruppo a cui è stato inviato in origine potrebbe comunque leggerlo.
-   In alternativa, creare più modelli, incluso uno per ciascun elenco di distribuzione. In questo modo si ottiene un controllo molto più preciso, ma il reparto IT dovrà supportare più modelli.

<span id="BKMK_60"></span>
#### I diritti applicati a un documento sono statici? Se un file viene inviato e in seguito si rivela necessario modificare i diritti, si può eseguire questa operazione se la licenza di pubblicazione è incorporata nel file e non sul server "criteri" RMS?

Sì, è possibile quando si utilizza un modello di criterio RMS: Quando il contenuto viene pubblicato utilizzando un modello di criterio RMS, la definizione del criterio resta sul server e può essere modificata da un amministratore dopo la pubblicazione del contenuto. Quando un utente richiede una licenza di pubblicazione per il contenuto, la licenza di pubblicazione concederà i diritti secondo il criterio attualmente definito sul server. Se i diritti vengono modificati dopo che è stata emessa una licenza d'uso per un utente, all'utente continueranno a essere concessi i diritti attivi al momento dell'emissione della licenza d'uso. Per consentire l'applicazione di un nuovo modello di criteri per i diritti dopo la pubblicazione del contenuto, abilitare un criterio per la scadenza del modello e specificare l'opzione **Le licenze d'uso per il contenuto devono essere rinnovate ogni: n giorni**. Al posto di n, specificare il numero di giorni dopo i quali un utente deve richiedere una nuova licenza d'uso.
