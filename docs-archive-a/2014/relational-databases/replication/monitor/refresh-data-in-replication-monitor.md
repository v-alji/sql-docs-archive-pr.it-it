---
title: Aggiornare i dati in Monitoraggio replica | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- refreshing data
ms.assetid: e9582244-7d00-45f4-be16-020a65c76a5e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2f097dea21b06540293e9b60b7de9315323b4168
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725511"
---
# <a name="refresh-data-in-replication-monitor"></a><span data-ttu-id="6a7f8-102">Aggiornamento dei dati in Monitoraggio replica</span><span class="sxs-lookup"><span data-stu-id="6a7f8-102">Refresh Data in Replication Monitor</span></span>
  <span data-ttu-id="6a7f8-103">In Monitoraggio replica è possibile aggiornare automaticamente o manualmente la finestra principale e le finestre dei dettagli, ovvero le finestre avviate dalla finestra principale.</span><span class="sxs-lookup"><span data-stu-id="6a7f8-103">In Replication Monitor, the main window and detail windows (those windows launched from the main window) can be refreshed automatically or manually.</span></span> <span data-ttu-id="6a7f8-104">Per aggiornare manualmente una finestra, premere F5.</span><span class="sxs-lookup"><span data-stu-id="6a7f8-104">To refresh a window manually, press F5.</span></span> <span data-ttu-id="6a7f8-105">Per impostazione predefinita, la finestra principale viene aggiornata automaticamente ogni cinque secondi. È possibile personalizzare la frequenza di ogni server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="6a7f8-105">By default, the main window is refreshed automatically every five seconds; the rate can be customized for each Publisher.</span></span>  
  
 <span data-ttu-id="6a7f8-106">I dati visualizzati in Monitoraggio replica provengono da query eseguite nella cache. Per informazioni sul rapporto tra la cache e l'aggiornamento di Monitoraggio replica, vedere [Memorizzazione nella cache, aggiornamento e prestazioni di Monitoraggio replica](caching-refresh-and-replication-monitor-performance.md).</span><span class="sxs-lookup"><span data-stu-id="6a7f8-106">The data displayed in Replication Monitor is queried from a cache; for information about the relationship between the cache and refreshing Replication Monitor, see [Caching, Refresh, and Replication Monitor Performance](caching-refresh-and-replication-monitor-performance.md).</span></span> <span data-ttu-id="6a7f8-107">Per informazioni sull'avvio di Monitoraggio replica, vedere [Avviare Monitoraggio replica](start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="6a7f8-107">For information about starting Replication Monitor, see [Start the Replication Monitor](start-the-replication-monitor.md).</span></span>  
  
### <a name="to-set-refresh-options-for-replication-monitor"></a><span data-ttu-id="6a7f8-108">Per impostare le opzioni di aggiornamento di Monitoraggio replica</span><span class="sxs-lookup"><span data-stu-id="6a7f8-108">To set refresh options for Replication Monitor</span></span>  
  
1.  <span data-ttu-id="6a7f8-109">Fare clic con il pulsante destro del mouse su un server di pubblicazione nel riquadro sinistro di Monitoraggio replica e quindi scegliere **Impostazioni server di pubblicazione**.</span><span class="sxs-lookup"><span data-stu-id="6a7f8-109">Right-click a Publisher in the left pane of Replication Monitor, and then click **Publisher Settings**.</span></span>  
  
2.  <span data-ttu-id="6a7f8-110">Nella finestra di dialogo **Impostazioni server di pubblicazione** , impostare le opzioni **Aggiornamento automatico** e **Frequenza di aggiornamento** .</span><span class="sxs-lookup"><span data-stu-id="6a7f8-110">In the **Publisher Settings** dialog box, set the **Auto refresh** and **Refresh rate** options.</span></span> <span data-ttu-id="6a7f8-111">L'impostazione **Aggiornamento automatico** è valida per la finestra principale di Monitoraggio replica.</span><span class="sxs-lookup"><span data-stu-id="6a7f8-111">The **Auto refresh** setting affects the main window in Replication Monitor.</span></span> <span data-ttu-id="6a7f8-112">L'impostazione **Frequenza di aggiornamento** è valida anche per le finestre dei dettagli sulle quali è stato impostato l'aggiornamento automatico. Le modifiche apportate all'impostazione avranno effetto sulle finestre dei dettagli solo alla loro successiva apertura.</span><span class="sxs-lookup"><span data-stu-id="6a7f8-112">The **Refresh rate** setting also affects any detail windows that are set to refresh automatically (changes to the setting only affect the detail windows opened after the change).</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-specify-that-a-detail-window-should-automatically-refresh"></a><span data-ttu-id="6a7f8-113">Per impostare l'aggiornamento automatico di una finestra dei dettagli</span><span class="sxs-lookup"><span data-stu-id="6a7f8-113">To specify that a detail window should automatically refresh</span></span>  
  
1.  <span data-ttu-id="6a7f8-114">Aprire una finestra dei dettagli in Monitoraggio replica.</span><span class="sxs-lookup"><span data-stu-id="6a7f8-114">Open a detail window in Replication Monitor.</span></span> <span data-ttu-id="6a7f8-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6a7f8-115">For example:</span></span>  
  
    1.  <span data-ttu-id="6a7f8-116">Espandere un gruppo di server di pubblicazione nel riquadro sinistro, espandere un server di pubblicazione e quindi fare clic su una pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="6a7f8-116">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
    2.  <span data-ttu-id="6a7f8-117">Fare clic sulla scheda **Tutte le sottoscrizioni** .</span><span class="sxs-lookup"><span data-stu-id="6a7f8-117">Click the **All Subscriptions** tab.</span></span>  
  
    3.  <span data-ttu-id="6a7f8-118">Fare clic con il pulsante destro del mouse su una sottoscrizione e quindi scegliere **Visualizza dettagli**.</span><span class="sxs-lookup"><span data-stu-id="6a7f8-118">Right-click a subscription, and then click **View Details**.</span></span>  
  
2.  <span data-ttu-id="6a7f8-119">Nella finestra dei dettagli **Sottoscrizione \<SubscriptionName>** fare clic su **Azione** e quindi fare clic su **Aggiornamento automatico**.</span><span class="sxs-lookup"><span data-stu-id="6a7f8-119">In the **Subscription \<SubscriptionName>** detail window, click **Action**, and then click **Auto Refresh**.</span></span> <span data-ttu-id="6a7f8-120">La frequenza di aggiornamento viene determinata dall'impostazione **Frequenza di aggiornamento** nella finestra di dialogo **Impostazioni server di pubblicazione** .</span><span class="sxs-lookup"><span data-stu-id="6a7f8-120">The refresh rate is determined by the **Refresh rate** setting in the **Publisher Settings** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a7f8-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a7f8-121">See Also</span></span>  
 [<span data-ttu-id="6a7f8-122">Monitoraggio della replica</span><span class="sxs-lookup"><span data-stu-id="6a7f8-122">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
