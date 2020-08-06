---
title: Sospendere e riprendere le pianificazioni condivise | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- pausing schedules
- report-specific schedules [Reporting Services]
- shared schedules [Reporting Services], resuming
- resuming schedules
- continuing schedules
- schedules [Reporting Services], resuming
- schedules [Reporting Services], pausing
ms.assetid: e416be75-5234-4aa6-a3de-77f60f25169a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f525a15b07b79b5c0d37f9a88ed9483b351af326
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629168"
---
# <a name="pause-and-resume-shared-schedules"></a><span data-ttu-id="a8562-102">Pause and Resume Shared Schedules</span><span class="sxs-lookup"><span data-stu-id="a8562-102">Pause and Resume Shared Schedules</span></span>
  <span data-ttu-id="a8562-103">È possibile sospendere e quindi riprendere una pianificazione condivisa attualmente in uso.</span><span class="sxs-lookup"><span data-stu-id="a8562-103">You can pause and resume a shared schedule that is in use.</span></span> <span data-ttu-id="a8562-104">In genere, si sospende una pianificazione condivisa per bloccare temporaneamente una pianificazione che viene utilizzata per attivare sottoscrizioni e operazioni di elaborazione di report.</span><span class="sxs-lookup"><span data-stu-id="a8562-104">Pausing a shared schedule provides a way to temporarily freeze a schedule that is used to trigger report processing and subscriptions.</span></span> <span data-ttu-id="a8562-105">Solo le pianificazioni condivise possono essere sospese e riprese.</span><span class="sxs-lookup"><span data-stu-id="a8562-105">Only shared schedules can be paused and resumed.</span></span> <span data-ttu-id="a8562-106">Non è possibile sospendere le pianificazioni specifiche dei report.</span><span class="sxs-lookup"><span data-stu-id="a8562-106">You cannot pause report-specific schedules.</span></span>  
  
 <span data-ttu-id="a8562-107">Non è possibile sospendere e riprendere le operazioni di elaborazione dei report in corso.</span><span class="sxs-lookup"><span data-stu-id="a8562-107">You cannot pause and resume report processing that is in progress.</span></span> <span data-ttu-id="a8562-108">È possibile sospendere e riprendere esclusivamente le pianificazioni presenti nella coda del servizio SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="a8562-108">You can only pause and resume schedules that are in the scheduling queue of SQL Server Agent service.</span></span> <span data-ttu-id="a8562-109">Un processo in corso è esterno all'ambito del motore di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="a8562-109">A job that is in progress is outside the scope of the scheduling engine.</span></span> <span data-ttu-id="a8562-110">Per altre informazioni, vedere [Gestire un processo in esecuzione](manage-a-running-process.md)</span><span class="sxs-lookup"><span data-stu-id="a8562-110">For more information, see [Manage a Running Process](manage-a-running-process.md)</span></span>  
  
 <span data-ttu-id="a8562-111">Mentre una pianificazione condivisa è in sospeso, tutte le operazioni che dovevano essere eseguite in tale intervallo di tempo possono essere ignorate.</span><span class="sxs-lookup"><span data-stu-id="a8562-111">While a shared schedule is paused, any operations that would have occurred are allowed to lapse.</span></span> <span data-ttu-id="a8562-112">Quando una pianificazione condivisa viene ripresa, le operazioni di elaborazione dei report e delle sottoscrizioni vengono eseguite in corrispondenza del successivo orario pianificato, utilizzando come riferimento l'ora locale del server di report.</span><span class="sxs-lookup"><span data-stu-id="a8562-112">After you resume a shared schedule, report and subscription processing occurs at the next scheduled time, using the local time of the server.</span></span> <span data-ttu-id="a8562-113">Tramite le applicazioni di servizio SharePoint o il server di report in modalità nativa non vengono eseguite le operazioni pianificate che sarebbero state eseguite se la pianificazione non fosse stata sospesa.</span><span class="sxs-lookup"><span data-stu-id="a8562-113">The native mode report server or SharePoint service applications, do not make up scheduled operations that would have occurred had the schedule not been paused.</span></span>  
  
 <span data-ttu-id="a8562-114">Contenuto dell'argomento:</span><span class="sxs-lookup"><span data-stu-id="a8562-114">In this Topic:</span></span>  
  
-   [<span data-ttu-id="a8562-115">Sospendere e riprendere le pianificazioni condivise (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="a8562-115">Pause and Resume Shared Schedules (Native Mode)</span></span>](#bkmk_native)  
  
-   [<span data-ttu-id="a8562-116">Sospendere e riprendere le pianificazioni condivise (modalità SharePoint)</span><span class="sxs-lookup"><span data-stu-id="a8562-116">Pause and Resume Shared Schedules (SharePoint mode)</span></span>](#bkmk_sharepoint)  
  
##  <a name="pause-and-resume-shared-schedules-native-mode"></a><a name="bkmk_native"></a> <span data-ttu-id="a8562-117">Sospendere e riprendere le pianificazioni condivise (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="a8562-117">Pause and Resume Shared Schedules (Native Mode)</span></span>  
 <span data-ttu-id="a8562-118">Per sospendere e riprendere una pianificazione condivisa, utilizzare la pagina Pianificazioni in Gestione report.</span><span class="sxs-lookup"><span data-stu-id="a8562-118">To pause and resume a shared schedule, use the Schedules page in Report Manager.</span></span> <span data-ttu-id="a8562-119">Non è possibile usare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] perché non ha le opzioni di sospensione e ripresa delle pianificazioni.</span><span class="sxs-lookup"><span data-stu-id="a8562-119">You cannot use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]; it does not provide options for pausing and resuming schedules.</span></span> <span data-ttu-id="a8562-120">Per altre informazioni, vedere [Create, Modify, and Delete Schedules](create-modify-and-delete-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="a8562-120">For more information, see [Create, Modify, and Delete Schedules](create-modify-and-delete-schedules.md).</span></span>  
  
#### <a name="to-pause-or-resume-a-shared-schedule"></a><span data-ttu-id="a8562-121">Per sospendere o riprendere una pianificazione condivisa</span><span class="sxs-lookup"><span data-stu-id="a8562-121">To pause or resume a shared schedule</span></span>  
  
1.  <span data-ttu-id="a8562-122">Da Gestione report fare clic su **Impostazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="a8562-122">From Report Manager Click, **Site Settings**.</span></span>  
  
2.  <span data-ttu-id="a8562-123">Fare clic su **Pianificazioni**.</span><span class="sxs-lookup"><span data-stu-id="a8562-123">Click **Schedules**.</span></span>  
  
3.  <span data-ttu-id="a8562-124">Selezionare la pianificazione e fare clic su **Sospendi** o **Riprendi** nella barra multifunzione.</span><span class="sxs-lookup"><span data-stu-id="a8562-124">Select the schedule, and click **Pause** or **Resume** in the ribbon.</span></span> <span data-ttu-id="a8562-125">Se una pianificazione è attualmente sospesa, nella colonna **Stato** verrà visualizzato **Sospeso**.</span><span class="sxs-lookup"><span data-stu-id="a8562-125">If a Schedule is currently paused, the **Status** column will contain **Paused**.</span></span>  
  
##  <a name="pause-and-resume-shared-schedules-sharepoint-mode"></a><a name="bkmk_sharepoint"></a> <span data-ttu-id="a8562-126">Sospendere e riprendere le pianificazioni condivise (modalità SharePoint)</span><span class="sxs-lookup"><span data-stu-id="a8562-126">Pause and Resume Shared Schedules (SharePoint mode)</span></span>  
 <span data-ttu-id="a8562-127">Per sospende e riprendere una pianificazione condivisa, utilizzare la pagina Impostazioni sito o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a8562-127">To pause and resume a shared schedule, use the Site Settings page or PowerShell.</span></span> <span data-ttu-id="a8562-128">Le pianificazioni sono gestite per sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a8562-128">Schedules are managed per SharePoint site.</span></span>  
  
#### <a name="to-pause-or-resume-a-shared-schedule"></a><span data-ttu-id="a8562-129">Per sospendere o riprendere una pianificazione condivisa</span><span class="sxs-lookup"><span data-stu-id="a8562-129">To pause or resume a shared schedule</span></span>  
  
1.  <span data-ttu-id="a8562-130">Fare clic su **Azioni sito**.</span><span class="sxs-lookup"><span data-stu-id="a8562-130">Click **Site Actions**.</span></span>  
  
2.  <span data-ttu-id="a8562-131">Fare clic su **Impostazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="a8562-131">Click **Site Settings**.</span></span>  
  
3.  <span data-ttu-id="a8562-132">Nella sezione Reporting Services fare clic su **Gestisci pianificazioni condivise**.</span><span class="sxs-lookup"><span data-stu-id="a8562-132">In the Reporting Services section, click **Manage Shared Schedules**.</span></span>  
  
4.  <span data-ttu-id="a8562-133">Selezionare la pianificazione e fare clic su **Sospendi pianificazioni selezionate** o **Esegui pianificazioni selezionate**.</span><span class="sxs-lookup"><span data-stu-id="a8562-133">Select the schedule, and click **Pause Selected Schedules** or **Run Selected Schedules**.</span></span> <span data-ttu-id="a8562-134">Se una pianificazione è attualmente sospesa, nella colonna **Stato** verrà visualizzato **Sospeso**.</span><span class="sxs-lookup"><span data-stu-id="a8562-134">If a Schedule is currently paused, the **Status** column will contain **Paused**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8562-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8562-135">See Also</span></span>  
 <span data-ttu-id="a8562-136">[Pianificazioni](schedules.md) </span><span class="sxs-lookup"><span data-stu-id="a8562-136">[Schedules](schedules.md) </span></span>  
 <span data-ttu-id="a8562-137">[Create, Modify, and Delete Schedules](create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="a8562-137">[Create, Modify, and Delete Schedules](create-modify-and-delete-schedules.md) </span></span>  
 <span data-ttu-id="a8562-138">[Modificare i fusi orari e le impostazioni dell'orologio in un server di report](change-time-zones-and-clock-settings-on-a-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="a8562-138">[Change Time Zones and Clock Settings on a Report Server](change-time-zones-and-clock-settings-on-a-report-server.md) </span></span>  
 [<span data-ttu-id="a8562-139">Gestire un processo in esecuzione</span><span class="sxs-lookup"><span data-stu-id="a8562-139">Manage a Running Process</span></span>](manage-a-running-process.md)  
  
  
