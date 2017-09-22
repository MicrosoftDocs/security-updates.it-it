---
TOCTitle: Esclusione dei certificati per account con diritti
Title: Esclusione dei certificati per account con diritti
ms:assetid: 'cba5e901-942c-4d06-9865-e6c4648c95e6'
ms:contentKeyID: 18824774
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747670(v=WS.10)'
---

Esclusione dei certificati per account con diritti
==================================================

Se un utente è considerato attendibile ma le sue credenziali RMS sono compromesse, è possibile escludere il certificato per account con diritti dell'utente escludendo la relativa chiave pubblica. Eseguendo questa operazione, in RMS vengono rifiutate le richieste di nuove licenze d'uso che prevedono l'utilizzo di tale certificato per account con diritti. Se un certificato per account con diritti viene escluso, la volta successiva che un utente cerca di acquisire una licenza d'uso per un nuovo contenuto, la richiesta viene rifiutata. Per acquisire una licenza d'uso, l'utente dovrà ottenere un nuovo certificato per account con diritti con una nuova coppia di chiavi.

È possibile escludere i certificati per account con diritti tramite la pagina **Criteri di esclusione** del sito Web Amministrazione. Quando si esclude un certificato per account con diritti di un utente, la chiave esclusa, il nome account dell'utente e la data e l'ora dell'esclusione vengono aggiunti alla tabella DRMS\_GicExclusionList del database di configurazione del cluster di certificazione principale tramite RMS. Le informazioni vengono inoltre visualizzate nella pagina **Criteri di esclusione** del sito Web Amministrazione. Vengono inoltre eliminate dalla tabella UD\_Users del database di configurazione sia la chiave pubblica che la chiave privata associate al certificato per account escluso.

Per escludere un certificato per account con diritti che si trova nel server o nel cluster di certificazione principale, specificare l'account di dominio dell'utente nella pagina **Criteri di esclusione** del server di certificazione principale. È necessario escludere un certificato per account con diritti nei server con registrazione secondaria nel sito Web di amministrazione di ogni server. Per escludere un utente in un cluster o in un server licenze con registrazione secondaria, immettere il valore della chiave pubblica del certificato per account con diritti nella pagina **Criteri di esclusione** del sito Web Amministrazione del server licenze. È possibile verificare tale valore nella pagina Criteri di esclusione del sito **Web Amministrazione** del cluster di certificazione principale.

Per semplificare l'esclusione di certificati per account con diritti in una distribuzione di RMS in più cluster, è possibile replicare la tabella DRMS\_GicExclusionList dal database di configurazione del cluster di certificazione principale al database di configurazione di ogni cluster licenze. In tal modo, non sarà necessario immettere manualmente il valore della chiave pubblica in ogni server.
