---
title: Visualizzare un report sui set di raccolta (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dc.reporthistory.calendar.f1
helpviewer_keywords:
- collection sets [SQL Server], viewing reports
- reports [SQL Server], viewing collection set
ms.assetid: c3b1e791-9aa1-4bba-9622-4954568e1820
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cb8755c67e6c03bb318fdb86d703f6d647d5a3eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636222"
---
# <a name="view-a-collection-set-report-sql-server-management-studio"></a><span data-ttu-id="b9d25-102">Visualizzare un report sui set di raccolta (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="b9d25-102">View a Collection Set Report (SQL Server Management Studio)</span></span>
  <span data-ttu-id="b9d25-103">Dopo avere configurato il data warehouse di gestione, è possibile visualizzare un report del set di raccolta in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9d25-103">After you have configured the management data warehouse, you can view a collection set report in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="b9d25-104">I report vengono forniti per i set di raccolta dati di sistema installati durante l'installazione</span><span class="sxs-lookup"><span data-stu-id="b9d25-104">Reports are provided for the System Data collection sets that are installed during Setup.</span></span> <span data-ttu-id="b9d25-105">Sono disponibili i report seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9d25-105">The reports include the following:</span></span>  
  
-   <span data-ttu-id="b9d25-106">Riepilogo utilizzo disco</span><span class="sxs-lookup"><span data-stu-id="b9d25-106">Disk Usage Summary</span></span>  
  
-   <span data-ttu-id="b9d25-107">Cronologia statistiche query</span><span class="sxs-lookup"><span data-stu-id="b9d25-107">Query Statistics History</span></span>  
  
-   <span data-ttu-id="b9d25-108">Cronologia attività server</span><span class="sxs-lookup"><span data-stu-id="b9d25-108">Server Activity History</span></span>  
  
 <span data-ttu-id="b9d25-109">Tramite questa procedura viene visualizzato il report per il set di raccolta **Utilizzo disco** .</span><span class="sxs-lookup"><span data-stu-id="b9d25-109">This procedure displays the report for the **Disk Usage** collection set.</span></span> <span data-ttu-id="b9d25-110">È possibile seguire la stessa procedura generale per visualizzare i report per gli altri set di raccolta dati di sistema.</span><span class="sxs-lookup"><span data-stu-id="b9d25-110">You can follow the same general procedure to view the reports for the other System Data collection sets.</span></span>  
  
### <a name="to-view-a-collection-set-report"></a><span data-ttu-id="b9d25-111">Per visualizzare un report di un set di raccolta</span><span class="sxs-lookup"><span data-stu-id="b9d25-111">To view a collection set report</span></span>  
  
1.  <span data-ttu-id="b9d25-112">Le tabelle necessarie per un report vengono create solo la prima volta che i dati raccolti vengono caricati.</span><span class="sxs-lookup"><span data-stu-id="b9d25-112">The tables for a report are created the first time that the collected data is uploaded.</span></span> <span data-ttu-id="b9d25-113">Se si tenta di visualizzare un report prima che venga effettuato il primo caricamento, si verifica un errore e non viene visualizzato alcun report.</span><span class="sxs-lookup"><span data-stu-id="b9d25-113">If you try to view a report before this first upload, an error occurs and no report is displayed.</span></span> <span data-ttu-id="b9d25-114">Per caricare dati per il set di raccolta Utilizzo disco, in Esplora oggetti espandere la cartella **Gestione** , espandere **Raccolta dati**e **Set di raccolta dati di sistema**, fare clic con il pulsante destro del mouse sul set di raccolta **Utilizzo disco** e quindi scegliere **Raccogli e carica**.</span><span class="sxs-lookup"><span data-stu-id="b9d25-114">To upload data for the Disk Usage collection set, in Object Explorer, expand the **Management** folder, expand **Data Collection**, expand **System Data Collection Sets**, right-click the **Disk Usage** collection set, and then click **Collect and Upload Now**.</span></span>  
  
2.  <span data-ttu-id="b9d25-115">Per visualizzare il report, in Esplora oggetti espandere la cartella **Gestione** , fare clic con il pulsante destro del mouse su **Raccolta dati**, scegliere **Report**, **Data warehouse di gestione**e quindi fare clic su **Riepilogo utilizzo disco**.</span><span class="sxs-lookup"><span data-stu-id="b9d25-115">To view the report, in Object Explorer, expand the **Management** folder, right-click **Data Collection**, point to **Reports**, point to **Management Data Warehouse**, and then click **Disk Usage Summary**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b9d25-116">Alcuni report potrebbero mostrare un pulsante calendario sotto la cronologia della raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="b9d25-116">Some reports might display a calendar button under the data collection timeline.</span></span> <span data-ttu-id="b9d25-117">Fare clic su questo pulsante per accedere al **Calendario report di raccolta dati**.</span><span class="sxs-lookup"><span data-stu-id="b9d25-117">Click this button to access the **Data Collection Report Calendar**.</span></span>  
  
#### <a name="data-collection-report-calendar"></a><span data-ttu-id="b9d25-118">Calendario report di raccolta dati</span><span class="sxs-lookup"><span data-stu-id="b9d25-118">Data Collection Report Calendar</span></span>  
 <span data-ttu-id="b9d25-119">Utilizzare questa finestra di dialogo per specificare la data e l'ora di inizio e la durata relative ai dati per cui si desidera creare il report.</span><span class="sxs-lookup"><span data-stu-id="b9d25-119">Use this dialog box to specify the start date, start time, and duration of the data that you want to report on.</span></span> <span data-ttu-id="b9d25-120">Potrebbe essere necessario ad esempio creare un report relativo all'utilizzo del disco di un server per un periodo specifico di 12 ore mercoledì scorso.</span><span class="sxs-lookup"><span data-stu-id="b9d25-120">For example, you may want to report on the disk usage activity of a server for a specific 12-hour period last Wednesday.</span></span>  
  
 <span data-ttu-id="b9d25-121">**Data inizio**</span><span class="sxs-lookup"><span data-stu-id="b9d25-121">**Start date**</span></span>  
 <span data-ttu-id="b9d25-122">Immettere una data iniziale per i dati del report o selezionarne una dal calendario.</span><span class="sxs-lookup"><span data-stu-id="b9d25-122">Enter a beginning date for the report data, or select one from the calendar.</span></span>  
  
 <span data-ttu-id="b9d25-123">**Ora di inizio**</span><span class="sxs-lookup"><span data-stu-id="b9d25-123">**Start time**</span></span>  
 <span data-ttu-id="b9d25-124">Immettere un'ora iniziale per i dati del report o fare clic sulle frecce per specificarne una.</span><span class="sxs-lookup"><span data-stu-id="b9d25-124">Enter a beginning time for the report data or specify one by clicking the arrows.</span></span>  
  
 <span data-ttu-id="b9d25-125">**Duration**</span><span class="sxs-lookup"><span data-stu-id="b9d25-125">**Duration**</span></span>  
 <span data-ttu-id="b9d25-126">Specificare l'intervallo di tempo da includere nel report.</span><span class="sxs-lookup"><span data-stu-id="b9d25-126">Specify the time range to include in the report.</span></span> <span data-ttu-id="b9d25-127">Il valore predefinito è 240 minuti.</span><span class="sxs-lookup"><span data-stu-id="b9d25-127">The default value is 240 minutes.</span></span> <span data-ttu-id="b9d25-128">I valori che è possibile selezionare sono 15 minuti, 60 minuti, 240 minuti (4 ore), 720 minuti (12 ore) e 1440 minuti (24 ore).</span><span class="sxs-lookup"><span data-stu-id="b9d25-128">The possible values to select from are 15 minutes, 60 minutes, 240 minutes (4 hours), 720 minutes (12 hours), and 1440 minutes (24 hours).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9d25-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9d25-129">See Also</span></span>  
 <span data-ttu-id="b9d25-130">[Raccolta dati](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="b9d25-130">[Data Collection](data-collection.md) </span></span>  
 <span data-ttu-id="b9d25-131">[Report personalizzati in Management Studio](../../ssms/object/custom-reports-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="b9d25-131">[Custom Reports in Management Studio](../../ssms/object/custom-reports-in-management-studio.md) </span></span>  
 [<span data-ttu-id="b9d25-132">Configurazione del data warehouse di gestione &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="b9d25-132">Configure the Management Data Warehouse &#40;SQL Server Management Studio&#41;</span></span>](configure-the-management-data-warehouse-sql-server-management-studio.md)  
  
  
