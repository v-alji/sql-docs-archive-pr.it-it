---
title: Gestire le pianificazioni | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.manageschedules.f1
ms.assetid: f56c0736-dccc-41d2-afcf-71344aff143a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6fa18d620d630484815966372d5de83bb52e8caf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627054"
---
# <a name="manage-schedules"></a><span data-ttu-id="8cac6-102">Gestione pianificazioni</span><span class="sxs-lookup"><span data-stu-id="8cac6-102">Manage Schedules</span></span>
  <span data-ttu-id="8cac6-103">Consente di visualizzare e modificare le proprietà per le [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pianificazioni dei processi di Agent.</span><span class="sxs-lookup"><span data-stu-id="8cac6-103">Allows you to view and change properties for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job schedules.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8cac6-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="8cac6-104">Options</span></span>  
 <span data-ttu-id="8cac6-105">**Pianificazioni disponibili**</span><span class="sxs-lookup"><span data-stu-id="8cac6-105">**Available schedules**</span></span>  
 <span data-ttu-id="8cac6-106">Consente di visualizzare l'elenco delle pianificazioni disponibili per questo utente.</span><span class="sxs-lookup"><span data-stu-id="8cac6-106">Lists the schedules available for this user.</span></span> <span data-ttu-id="8cac6-107">Si noti che un processo e una pianificazione devono appartenere allo stesso proprietario.</span><span class="sxs-lookup"><span data-stu-id="8cac6-107">Notice that a job and a schedule must have the same owner.</span></span> <span data-ttu-id="8cac6-108">Nell'elenco sono pertanto incluse solo le pianificazioni appartenenti al proprietario del processo.</span><span class="sxs-lookup"><span data-stu-id="8cac6-108">Therefore, this list only includes schedules owned by the owner of the job.</span></span>  
  
 <span data-ttu-id="8cac6-109">**Nome**</span><span class="sxs-lookup"><span data-stu-id="8cac6-109">**Name**</span></span>  
 <span data-ttu-id="8cac6-110">Consente di visualizzare il nome della pianificazione.</span><span class="sxs-lookup"><span data-stu-id="8cac6-110">Displays the name of the schedule.</span></span>  
  
 <span data-ttu-id="8cac6-111">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="8cac6-111">**Enabled**</span></span>  
 <span data-ttu-id="8cac6-112">Selezionare questa opzione per abilitare la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="8cac6-112">Select this option to enable the schedule.</span></span>  
  
 <span data-ttu-id="8cac6-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="8cac6-113">**Description**</span></span>  
 <span data-ttu-id="8cac6-114">Descrive le condizioni nelle quali la pianificazione esegue il processo.</span><span class="sxs-lookup"><span data-stu-id="8cac6-114">Describes the conditions under which the schedule runs the job.</span></span>  
  
 <span data-ttu-id="8cac6-115">**Processi nella pianificazione**</span><span class="sxs-lookup"><span data-stu-id="8cac6-115">**Jobs in schedule**</span></span>  
 <span data-ttu-id="8cac6-116">Consente di visualizzare l'elenco dei numeri di processo collegati alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="8cac6-116">Lists the job numbers attached to the schedule.</span></span> <span data-ttu-id="8cac6-117">Fare clic su un numero per visualizzare le proprietà del processo.</span><span class="sxs-lookup"><span data-stu-id="8cac6-117">Click a number to view the properties of the job.</span></span>  
  
 <span data-ttu-id="8cac6-118">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="8cac6-118">**New**</span></span>  
 <span data-ttu-id="8cac6-119">Fare clic su questo pulsante per creare una nuova pianificazione.</span><span class="sxs-lookup"><span data-stu-id="8cac6-119">Click this button to create a new schedule.</span></span>  
  
 <span data-ttu-id="8cac6-120">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="8cac6-120">**Delete**</span></span>  
 <span data-ttu-id="8cac6-121">Fare clic su questo pulsante per eliminare la pianificazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="8cac6-121">Click this button to delete the selected schedule.</span></span>  
  
 <span data-ttu-id="8cac6-122">**Proprietà**</span><span class="sxs-lookup"><span data-stu-id="8cac6-122">**Properties**</span></span>  
 <span data-ttu-id="8cac6-123">Fare clic su questo pulsante per modificare le proprietà della pianificazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="8cac6-123">Click this button to change the properties of the selected schedule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cac6-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8cac6-124">See Also</span></span>  
 [<span data-ttu-id="8cac6-125">Creazione e collegamento di pianificazioni ai processi</span><span class="sxs-lookup"><span data-stu-id="8cac6-125">Create and Attach Schedules to Jobs</span></span>](create-and-attach-schedules-to-jobs.md)  
  
  
