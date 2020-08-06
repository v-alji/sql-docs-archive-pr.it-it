---
title: Proprietà SQL Server Agent (pagina Avanzate) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.advanced.f1
ms.assetid: a4d798ee-4c18-40d4-b6af-63d17503738c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8ec0d9d7fbd51f9350bf692588f90c292e54f4e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636524"
---
# <a name="sql-server-agent-properties-advanced-page"></a><span data-ttu-id="c0e6b-102">Proprietà SQL Server Agent (pagina Avanzate)</span><span class="sxs-lookup"><span data-stu-id="c0e6b-102">SQL Server Agent Properties (Advanced Page)</span></span>
  <span data-ttu-id="c0e6b-103">Utilizzare questa pagina per visualizzare e modificare le proprietà avanzate del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] servizio Agent.</span><span class="sxs-lookup"><span data-stu-id="c0e6b-103">Use this page to view and modify advanced properties of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c0e6b-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="c0e6b-104">Options</span></span>  
 <span data-ttu-id="c0e6b-105">**Inoltro eventi SQL Server**</span><span class="sxs-lookup"><span data-stu-id="c0e6b-105">**SQL Server event forwarding**</span></span>  
 <span data-ttu-id="c0e6b-106">Le opzioni di questa categoria consentono di attivare e configurare l'inoltro di eventi.</span><span class="sxs-lookup"><span data-stu-id="c0e6b-106">The options in this category activate and configure event forwarding.</span></span>  
  
 <span data-ttu-id="c0e6b-107">**Inoltra eventi a un altro server**</span><span class="sxs-lookup"><span data-stu-id="c0e6b-107">**Forward events to a different server**</span></span>  
 <span data-ttu-id="c0e6b-108">Gli eventi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent vengono inoltrati a un server diverso.</span><span class="sxs-lookup"><span data-stu-id="c0e6b-108">Forwards [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent events to a different server.</span></span>  
  
 <span data-ttu-id="c0e6b-109">**Server**</span><span class="sxs-lookup"><span data-stu-id="c0e6b-109">**Server**</span></span>  
 <span data-ttu-id="c0e6b-110">Consente di selezionare il nome del server al quale inoltrare gli eventi.</span><span class="sxs-lookup"><span data-stu-id="c0e6b-110">Select the name of the server to forward events to.</span></span>  
  
 <span data-ttu-id="c0e6b-111">**Eventi non gestiti**</span><span class="sxs-lookup"><span data-stu-id="c0e6b-111">**Unhandled events**</span></span>  
 <span data-ttu-id="c0e6b-112">Solo gli eventi non gestiti vengono inoltrati al server specificato.</span><span class="sxs-lookup"><span data-stu-id="c0e6b-112">Forwards only unhandled events to the specified server.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c0e6b-113">Agent inoltra solo gli eventi ai quali non risponde alcun avviso.</span><span class="sxs-lookup"><span data-stu-id="c0e6b-113">Agent forwards only events that no alert responds to.</span></span>  
  
 <span data-ttu-id="c0e6b-114">**Tutti gli eventi**</span><span class="sxs-lookup"><span data-stu-id="c0e6b-114">**All events**</span></span>  
 <span data-ttu-id="c0e6b-115">Vengono inoltrati tutti gli eventi.</span><span class="sxs-lookup"><span data-stu-id="c0e6b-115">Forwards all events.</span></span> <span data-ttu-id="c0e6b-116">Quando un avviso nell'istanza locale risponde a un evento, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent inoltra l'evento ed elabora l'avviso.</span><span class="sxs-lookup"><span data-stu-id="c0e6b-116">When an alert in the local instance responds to the event, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agent will both forward the event and process the alert.</span></span>  
  
 <span data-ttu-id="c0e6b-117">**Eventi con gravità maggiore o uguale a**</span><span class="sxs-lookup"><span data-stu-id="c0e6b-117">**If event has severity at or above**</span></span>  
 <span data-ttu-id="c0e6b-118">Vengono inoltrati solo gli eventi il cui livello di gravità e maggiore o uguale al livello specificato.</span><span class="sxs-lookup"><span data-stu-id="c0e6b-118">Forwards only events with a severity level at or above the level specified.</span></span>  
  
 <span data-ttu-id="c0e6b-119">**Condizione di inattività CPU**</span><span class="sxs-lookup"><span data-stu-id="c0e6b-119">**Idle CPU Condition**</span></span>  
 <span data-ttu-id="c0e6b-120">Le opzioni di questa categoria consentono di definire le condizioni in base alle quali [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent esegue i processi pianificati per l'esecuzione in base alla pianificazione di inattività della CPU.</span><span class="sxs-lookup"><span data-stu-id="c0e6b-120">The options in this category define the conditions under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent runs jobs scheduled to run on the Idle CPU schedule.</span></span>  
  
 <span data-ttu-id="c0e6b-121">**Imposta condizione di inattività CPU**</span><span class="sxs-lookup"><span data-stu-id="c0e6b-121">**Define idle CPU condition**</span></span>  
 <span data-ttu-id="c0e6b-122">Consente di definire le condizioni in base alle quali [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent considera la CPU come inattiva.</span><span class="sxs-lookup"><span data-stu-id="c0e6b-122">Defines the conditions under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent considers the CPU to be idle.</span></span>  
  
 <span data-ttu-id="c0e6b-123">**L'utilizzo medio della CPU è inferiore al**</span><span class="sxs-lookup"><span data-stu-id="c0e6b-123">**Average CPU usage falls below**</span></span>  
 <span data-ttu-id="c0e6b-124">La percentuale di utilizzo della CPU al di sotto della quale la CPU viene considerata inattiva.</span><span class="sxs-lookup"><span data-stu-id="c0e6b-124">Percentage of CPU usage below which the CPU is considered to be idle.</span></span>  
  
 <span data-ttu-id="c0e6b-125">**per almeno**</span><span class="sxs-lookup"><span data-stu-id="c0e6b-125">**And remains below this level for**</span></span>  
 <span data-ttu-id="c0e6b-126">Periodo di tempo durante il quale l'utilizzo medio della CPU deve essere al di sotto del livello specificato prima che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent esegua i processi in base alla pianificazione di inattività della CPU.</span><span class="sxs-lookup"><span data-stu-id="c0e6b-126">Amount of time that the average CPU must below the level specified before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent runs jobs on the Idle CPU schedule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0e6b-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0e6b-127">See Also</span></span>  
 <span data-ttu-id="c0e6b-128">[Creazione e alconnessione di pianificazioni ai processi](create-and-attach-schedules-to-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="c0e6b-128">[Create and Attach Schedules to Jobs](create-and-attach-schedules-to-jobs.md) </span></span>  
 [<span data-ttu-id="c0e6b-129">Gestione di eventi</span><span class="sxs-lookup"><span data-stu-id="c0e6b-129">Manage Events</span></span>](manage-events.md)  
  
  
