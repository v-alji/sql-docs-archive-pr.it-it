---
title: Proprietà pianificazione (pagina Report) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.scheduleproperties.reports.f1
ms.assetid: 7db728bd-4b08-43ef-a49a-e8dcdd37cf89
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: da0b5255e73522572fa22da8668329a28f108104
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627068"
---
# <a name="schedule-properties-reports-page"></a><span data-ttu-id="0f2fe-102">Proprietà pianificazione (pagina Report)</span><span class="sxs-lookup"><span data-stu-id="0f2fe-102">Schedule Properties (Reports Page)</span></span>
  <span data-ttu-id="0f2fe-103">Utilizzare questa pagina per visualizzare tutti i report che utilizzano la pianificazione condivisa.</span><span class="sxs-lookup"><span data-stu-id="0f2fe-103">Use this page to view a list of all reports that use this shared schedule.</span></span> <span data-ttu-id="0f2fe-104">È possibile utilizzare le pianificazioni per aggiornare lo snapshot o generare la cronologia del report, attivare una sottoscrizione oppure specificare la data e l'ora di scadenza di una copia del report memorizzata nella cache.</span><span class="sxs-lookup"><span data-stu-id="0f2fe-104">Schedules can be used to refresh report snapshots, generate report history, trigger a subscription, or expire a cached copy of the report.</span></span> <span data-ttu-id="0f2fe-105">Per individuare la modalità di utilizzo della pianificazione, visualizzare le informazioni sulle proprietà e sulla sottoscrizione del report.</span><span class="sxs-lookup"><span data-stu-id="0f2fe-105">To find out how the schedule is used, view the property and subscription information of the report.</span></span>  
  
 <span data-ttu-id="0f2fe-106">Anche se in questa pagina è illustrato ogni report che utilizza la pianificazione condivisa, non viene indicato quante volte la pianificazione condivisa è utilizzata all'interno di un singolo report.</span><span class="sxs-lookup"><span data-stu-id="0f2fe-106">Although this page shows each report that uses the shared schedule, it does not indicate how many times the shared schedule is used within that single report.</span></span> <span data-ttu-id="0f2fe-107">Si supponga, ad esempio che 20 diversi sottoscrittori del report Company Sales utilizzino tutti la stessa pianificazione condivisa per attivare l'elaborazione della sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="0f2fe-107">For example, suppose 20 different subscribers to the Company Sales report all use the same shared schedule to trigger subscription processing.</span></span> <span data-ttu-id="0f2fe-108">In questo caso, il report Company Sales verrà indicato una sola volta nell'elenco, anche se nel report sono presenti 20 riferimenti alla pianificazione condivisa.</span><span class="sxs-lookup"><span data-stu-id="0f2fe-108">In this case, the Company Sales report will only appear once in this list, even though the report has 20 references to the shared schedule.</span></span>  
  
 <span data-ttu-id="0f2fe-109">Per aprire questa pagina, avviare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , connettersi a un server di report, aprire la cartella **pianificazioni condivise** , fare clic con il pulsante destro del mouse su una pianificazione condivisa, scegliere **proprietà**, quindi fare clic su **report**.</span><span class="sxs-lookup"><span data-stu-id="0f2fe-109">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, open the **Shared Schedules** folder, right-click a shared schedule, select **Properties**, and then click **Reports**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0f2fe-110">Questa funzionalità non è disponibile in ogni edizione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f2fe-110">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0f2fe-111">Per un elenco delle funzionalità supportate dalle edizioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vedere [funzionalità supportate dalle edizioni di SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) ( https://go.microsoft.com/fwlink/?linkid=232473) .</span><span class="sxs-lookup"><span data-stu-id="0f2fe-111">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) (https://go.microsoft.com/fwlink/?linkid=232473).</span></span>  
  
## <a name="options"></a><span data-ttu-id="0f2fe-112">Opzioni</span><span class="sxs-lookup"><span data-stu-id="0f2fe-112">Options</span></span>  
 <span data-ttu-id="0f2fe-113">**Cartella**</span><span class="sxs-lookup"><span data-stu-id="0f2fe-113">**Folder**</span></span>  
 <span data-ttu-id="0f2fe-114">Consente di specificare il percorso del report.</span><span class="sxs-lookup"><span data-stu-id="0f2fe-114">Specifies the path of the report.</span></span>  
  
 <span data-ttu-id="0f2fe-115">**Report**</span><span class="sxs-lookup"><span data-stu-id="0f2fe-115">**Report**</span></span>  
 <span data-ttu-id="0f2fe-116">Consente di specificare il nome del report che utilizza la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="0f2fe-116">Specifies the name of the report that uses the schedule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f2fe-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f2fe-117">See Also</span></span>  
 <span data-ttu-id="0f2fe-118">[Create, Modify, and Delete Schedules](../subscriptions/create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="0f2fe-118">[Create, Modify, and Delete Schedules](../subscriptions/create-modify-and-delete-schedules.md) </span></span>  
 <span data-ttu-id="0f2fe-119">[Pianificazioni](../subscriptions/schedules.md) </span><span class="sxs-lookup"><span data-stu-id="0f2fe-119">[Schedules](../subscriptions/schedules.md) </span></span>  
 <span data-ttu-id="0f2fe-120">[Guida sensibile al contesto del server di report Management Studio](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="0f2fe-120">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="0f2fe-121">[Connettersi a un server di report in Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="0f2fe-121">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 [<span data-ttu-id="0f2fe-122">Configurare le proprietà generali per un report &#40;Gestione report&#41;</span><span class="sxs-lookup"><span data-stu-id="0f2fe-122">Configure General Properties for a Report &#40;Report Manager&#41;</span></span>](../configure-general-properties-for-a-report-report-manager.md)  
  
  
