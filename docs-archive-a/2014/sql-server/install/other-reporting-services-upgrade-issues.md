---
title: Altri problemi di aggiornamento Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- command line setup [Reporting Services]
- Setup commands [Reporting Services]
- multivalued parameters [Reporting Services]
- WMI provider [Reporting Services]
- compile errors [Reporting Services]
- single-valued parameters [Reporting Services]
- data processing extensions [Reporting Services]
- report compilation errors [Reporting Services]
- authentication [Reporting Services]
ms.assetid: 42dd2f06-1de9-449e-ab9d-f4ef25f8b728
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 7cba24007534f143e6b8fd4b7cf74357bbfba3a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628174"
---
# <a name="other-reporting-services-upgrade-issues"></a>Altri problemi di aggiornamento di Reporting Services
  In questo argomento vengono descritti problemi noti che potrebbero presentarsi durante la funzionalità di aggiornamento di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]. **Questi problemi non vengono rilevati tramite Preparazione aggiornamento** Per ulteriori informazioni, vedere le [Note sulla versione di SQL Server 2014](https://go.microsoft.com/fwlink/?LinkID=296445)  
  
||  
|-|  
|**[!INCLUDE[applies](../../includes/applies-md.md)]**  Modalità nativa di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] &#124; Modalità SharePoint di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].|  
  
|Problema|Descrizione|Si applica a|  
|-----------|-----------------|----------------|  
|Aggiornamento farm SharePoint|Aggiornare il servizio condiviso [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] solo dopo che tutti gli altri componenti di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] nella farm sono stati aggiornati a [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].<br /><br /> Per eseguire [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] l'aggiornamento in una farm di SharePoint a più nodi a [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , è necessario aggiornare tutte le istanze del [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] componente aggiuntivo per SharePoint nella farm alla [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] versione prima di aggiornare il [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] servizio condiviso.<br /><br /> Il rendering del report non verrà eseguito se il servizio SharePoint Shared di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] è stato aggiornato a [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], ma altri componenti di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] della farm sono ancora nella versione [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].<br /><br /> <br /><br /> Per ulteriori informazioni, vedere [Suggerimenti e risoluzione dei problemi relativi a SQL Server 2014 Reporting Services](https://go.microsoft.com/fwlink/?LinkID=391254).|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] e [!INCLUDE[ssSQL11SP1](../../includes/sssql11sp1-md.md)]|  
|Installazione side-by-side|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]La modalità nativa non può essere eseguita side-by-side con uno dei seguenti elementi:<br /><br /> [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]componente aggiuntivo per SharePoint<br /><br /> [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Servizio SharePoint Shared<br /><br /> <br /><br /> L'installazione side-by-side impedisce l' [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] avvio del servizio Windows in modalità nativa. Nel log degli eventi di Windows saranno presenti messaggi di errore simili ai seguenti:<br /><br /> Descrizione: La versione del database del server di report non è valida.<br /><br /> Descrizione: Il server di report [nome server] non è in grado di connettersi al database del server di report.|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] Modalità nativa|  
|Errore durante il ripristino di un aggiornamento con errori|**Problema:** Si tenta di eseguire un ripristino in seguito a un errore di aggiornamento. Anche l'operazione di ripristino non riesce e vengono visualizzati messaggi simili al seguente nei file di log del programma di installazione:<br /><br /> `(01) 2011-10-27 12:23:15 Slp:` <br /> `(01) 2011-10-27 12:23:15 Slp: Exception type: System.Exception` <br /> `(01) 2011-10-27 12:23:15 Slp:     Message:`  <br /> `(01) 2011-10-27 12:23:15 Slp:         SQLPath element is missing` <br /> `(01) 2011-10-27 12:23:15 Slp:     Data:`  <br /> `(01) 2011-10-27 12:23:15 Slp:       SQL.Setup.FailureCategory = ConfigurationFailure`<br /><br /> Per ulteriori informazioni sui file di log, vedere [visualizzare e leggere SQL Server file di log del programma di installazione](../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md).<br /><br /> **Soluzione:** È necessario disinstallare [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e reinstallare [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] . Non è più possibile eseguire un aggiornamento.|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] e [!INCLUDE[ssSQL11SP1](../../includes/sssql11sp1-md.md)]|  
|Informazioni sull'interattività salvate solo per l'ultima richiesta.|Nelle versioni precedenti di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], gli snapshot salvano tutte le combinazioni possibili di scelte interattive, ad esempio informazioni sulle operazioni di drill-through e opzioni di attivazione/disattivazione. È ad esempio possibile visualizzare la pagina 5 di un report ma attivare e disattivare a livello di programmazione un elemento a pagina 1 tenendo traccia dell'ID corretto dell'operazione.<br /><br /> In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] le informazioni sull'interattività vengono generate e salvate solo per l'ultima richiesta di rendering. Non è possibile visualizzare una pagina e attivare/disattivare a livello di programmazione un elemento in un'altra pagina. È possibile attivare/disattivare solo gli elementi di drill-down presenti nella pagina corrente del report.|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005 SP2|  
|Modifiche apportate al rendering e all'impaginazione.|Il modello a oggetti di rendering (ROM) è stato modificato in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] . Le versioni precedenti di questo modello non sono più supportate. L'accesso al modello di oggetti per il rendering da un'estensione per il rendering multithread e il cambio di contesto da più thread non sono supportati.|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005 SP2|  
|Formato di esportazione di CSV riprogettato.|Nelle versioni precedenti di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], quando si esporta un report in formato di file CSV, i dati vengono formattati in modo da preservare l'aspetto che avevano nella pagina del report. Per le aree dati della matrice, il risultato è un formato di dati poco pratico da importare in altre applicazioni.<br /><br /> In questa versione, quando si esporta un report in un file CSV, è possibile scegliere tra due formati supportati: modalità predefinita e modalità conforme. La modalità predefinita è ottimizzata per Excel. La modalità conforme è ottimizzata per applicazioni di terze parti.<br /><br /> Il formato precedente dei file CSV non è più disponibile. Tuttavia, per i report che non utilizzano aree dati della matrice, è possibile utilizzare la modalità conforme per ottenere un formato di file più vicino al formato di file CSV precedente.|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005 SP2|  
|Funzioni di aggregazione con visibilità condizionale in intestazioni e piè di pagina.|Nelle versioni precedenti di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], renderer diversi utilizzano regole diverse per determinare gli elementi con visibilità condizionale da includere in una pagina di un report. Ad esempio, i calcoli di aggregazione non vengono eseguiti per gli elementi nascosti nei report stampati, mentre vengono eseguiti per gli elementi nascosti dei report visualizzati con un browser o in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Office Excel.<br /><br /> In questa versione tutti i renderer utilizzano lo stesso set di regole per determinare gli elementi da includere in una pagina.|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005 SP2|  
|Nessun supporto delle formule in Excel.|Nelle versioni precedenti di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] è disponibile un supporto limitato per la conversione di espressioni RDL in formule di Excel. In questa versione, quando si esporta un report in Excel, le espressioni RDL non vengono convertite in formule di Excel.|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005 SP2|  
|Elementi sovrapposti.|Nelle versioni precedenti di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], se un report contiene elementi sovrapposti nell'area di progettazione, la pubblicazione del report genera un messaggio di avviso ("Non tutti i renderer supportano elementi del report sovrapposti"), ma gli elementi del report rimangono nella posizione originale nell'area di progettazione. In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], gli elementi del report possono essere spostati per correggere i limiti della sovrapposizione quando viene visualizzato o esportato in un renderer che non supporta elementi sovrapposti.|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005 SP2|  
|Modifica dello spazio dei nomi del modello a oggetti del report.|In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] lo spazio dei nomi del modello a oggetti del report è stato modificato. Questo spazio dei nomi fornisce accesso in sola lettura da codice personalizzato alle raccolte globali come `Fields`, `Parameters` e `ReportItems`. Se il codice personalizzato esistente utilizza in modo esplicito un riferimento completo a uno spazio dei nomi precedente, questa modifica è importante.<br /><br /> Si consiglia di non utilizzare riferimenti completi per l'accesso a raccolte incorporate dal codice. Se si evita di specificare in modo esplicito lo spazio dei nomi, i riferimenti del codice personalizzato si risolvono nella versione del modello a oggetti del report destinata alla versione attualmente installata di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005 SP2|  
|Il provider Strumentazione gestione Windows (WMI) del server di report di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2000 o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005 non è supportato.|In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] è incluso un provider WMI che è possibile utilizzare per configurare a livello di programmazione l'ambiente in cui viene eseguito un server di report. Nella versione di [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] è inclusa una nuova versione del provider WMI che sostituisce completamente la precedente. Le versioni 2000 e 2005 di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non sono supportate in questa versione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005 SP2|  
|Nomi dell'entità servizio (SPN) non ricreati in un server di report aggiornato.|Se è stato creato un nome SPN per il servizio Web ReportServer, verificare che la delega vincolata continui a funzionare per il server di report aggiornato.|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005 SP2|  
|Gli assembly personalizzati devono essere spostati manualmente nella nuova cartella di installazione.|Gli assembly personalizzati non vengono rilevati da Preparazione aggiornamento e devono essere spostati manualmente nella nuova cartella di installazione se si desidera continuare a utilizzare la funzionalità personalizzata nei report.<br /><br /> Se tali assembly vengono installati nella cartella di installazione del server di report, devono essere spostati nella nuova cartella di installazione dopo che l'aggiornamento è stato completato.|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005 SP2|  
  
## <a name="see-also"></a>Vedere anche  
 [Problemi di aggiornamento Reporting Services &#40;preparazione aggiornamento&#41;](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  