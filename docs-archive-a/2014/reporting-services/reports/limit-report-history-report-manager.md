---
title: Limitare la cronologia dei report (Gestione report) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- viewing report history
- report history [Reporting Services], viewing history
- report history [Reporting Services], configuring history
- historical data [Reporting Services]
- displaying report history
ms.assetid: 8e255792-d9ef-496f-a26c-9e969c1209a0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 01318b1e1ccf0b0bf4512ab57de90cbf5ebc7365
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713783"
---
# <a name="limit-report-history-report-manager"></a><span data-ttu-id="36a83-102">Limitare la cronologia dei report (Gestione report)</span><span class="sxs-lookup"><span data-stu-id="36a83-102">Limit Report History (Report Manager)</span></span>
  <span data-ttu-id="36a83-103">La cronologia di un report è una raccolta di snapshot del report creati nel tempo.</span><span class="sxs-lookup"><span data-stu-id="36a83-103">Report history is a collection of report snapshots that you create over time.</span></span> <span data-ttu-id="36a83-104">È possibile creare la cronologia del report su richiesta o pianificare la frequenza di creazione di uno snapshot e della relativa aggiunta alla cronologia.</span><span class="sxs-lookup"><span data-stu-id="36a83-104">You can create report history on demand, or schedule how often a snapshot is created and added to report history.</span></span>  
  
 <span data-ttu-id="36a83-105">La cronologia del report viene archiviata nel database del server di report.</span><span class="sxs-lookup"><span data-stu-id="36a83-105">Report history is stored in the report server database.</span></span> <span data-ttu-id="36a83-106">Se gli snapshot del report contengono una quantità di dati elevata, è possibile limitare la cronologia del report per minimizzare l'impatto della memorizzazione degli snapshot sulle dimensione del database.</span><span class="sxs-lookup"><span data-stu-id="36a83-106">If report snapshots contain a large amount of data, you might consider limiting report history to minimize the affect of snapshot retention on database size.</span></span>  
  
### <a name="to-configure-report-history-for-a-report-server"></a><span data-ttu-id="36a83-107">Per configurare la cronologia del report per un server di report</span><span class="sxs-lookup"><span data-stu-id="36a83-107">To configure report history for a report server</span></span>  
  
1.  <span data-ttu-id="36a83-108">In Gestione report fare clic su **Impostazioni sito** sulla barra degli strumenti principale.</span><span class="sxs-lookup"><span data-stu-id="36a83-108">In Report Manager, click **Site Settings** on the global toolbar.</span></span>  
  
2.  <span data-ttu-id="36a83-109">Selezionare **Nessun limite per il numero di snapshot archiviabili nella cronologia** se si desidera mantenere tutta la cronologia del report per un periodo illimitato.</span><span class="sxs-lookup"><span data-stu-id="36a83-109">Select **Keep an unlimited number of snapshots in report history** if you want to keep all report history indefinitely.</span></span> <span data-ttu-id="36a83-110">In alternativa, selezionare **Numero massimo di copie della cronologia** per specificare il numero massimo di snapshot che è possibile mantenere per qualsiasi report.</span><span class="sxs-lookup"><span data-stu-id="36a83-110">Otherwise, select **Limit the copies of report history** to specify the maximum number of snapshots that can be kept for any given report.</span></span>  
  
3.  <span data-ttu-id="36a83-111">Fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="36a83-111">Click **Apply**.</span></span>  
  
### <a name="to-configure-report-history-for-a-specific-report"></a><span data-ttu-id="36a83-112">Per configurare la cronologia per un report specifico</span><span class="sxs-lookup"><span data-stu-id="36a83-112">To configure report history for a specific report</span></span>  
  
1.  <span data-ttu-id="36a83-113">In Gestione report passare al report per il quale si desidera configurare la cronologia e quindi fare clic su di esso per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="36a83-113">In Report Manager, navigate to the report for which you want to configure history, and then click the report to open it.</span></span>  
  
2.  <span data-ttu-id="36a83-114">Fare clic sulla scheda **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="36a83-114">Click the **Properties** tab.</span></span>  
  
3.  <span data-ttu-id="36a83-115">Fare clic sulla scheda **Cronologia**.</span><span class="sxs-lookup"><span data-stu-id="36a83-115">Click the **History** tab.</span></span>  
  
4.  <span data-ttu-id="36a83-116">Selezionare le opzioni per il report e fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="36a83-116">Select the options for your report and click **Apply**.</span></span> <span data-ttu-id="36a83-117">Per informazioni dettagliate su ogni opzione, vedere [Pagina delle proprietà Opzioni snapshot &#40;Gestione report&#41;](../snapshot-options-properties-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="36a83-117">For details about each option, see [Snapshot Options Properties Page &#40;Report Manager&#41;](../snapshot-options-properties-page-report-manager.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36a83-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36a83-118">See Also</span></span>  
 <span data-ttu-id="36a83-119">[Aggiungere uno snapshot alla cronologia del report &#40;Gestione report&#41;](../report-server/add-a-snapshot-to-report-history-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="36a83-119">[Add a Snapshot to Report History &#40;Report Manager&#41;](../report-server/add-a-snapshot-to-report-history-report-manager.md) </span></span>  
 [<span data-ttu-id="36a83-120">Gestione report &#40;modalità nativa SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="36a83-120">Report Manager  &#40;SSRS Native Mode&#41;</span></span>](../report-manager-ssrs-native-mode.md)  
  
  
