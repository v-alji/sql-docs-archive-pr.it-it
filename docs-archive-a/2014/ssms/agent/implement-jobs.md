---
title: Implementare processi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent]
- SQL Server Agent jobs
- SQL Server Agent jobs, about jobs
- jobs [SQL Server Agent], about jobs
ms.assetid: 69e06724-25c7-4fb3-8a5b-3d4596f21756
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1925b3113db8d7c57ac4344958c0247763cfd1b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623711"
---
# <a name="implement-jobs"></a><span data-ttu-id="00c6a-102">Implementazione di processi</span><span class="sxs-lookup"><span data-stu-id="00c6a-102">Implement Jobs</span></span>
  <span data-ttu-id="00c6a-103">I processi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent consentono di automatizzare le attività amministrative di routine, in modo da rendere più efficiente l'amministrazione.</span><span class="sxs-lookup"><span data-stu-id="00c6a-103">You can use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs to automate routine administrative tasks and run them on a recurring basis, making administration more efficient.</span></span>  
  
 <span data-ttu-id="00c6a-104">Un processo include una serie di operazioni specificate eseguite in sequenza da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="00c6a-104">A job is a specified series of operations performed sequentially by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="00c6a-105">Un processo può eseguire un'ampia gamma di attività, inclusa l'esecuzione di script [!INCLUDE[tsql](../../includes/tsql-md.md)] , applicazioni della riga di comando, script Microsoft ActiveX, pacchetti di Integration Services, comandi e query di Analysis Services o attività di replica.</span><span class="sxs-lookup"><span data-stu-id="00c6a-105">A job can perform a wide range of activities, including running [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, command-line applications, Microsoft ActiveX scripts, Integration Services packages, Analysis Services commands and queries, or Replication tasks.</span></span> <span data-ttu-id="00c6a-106">I processi possono eseguire attività ripetitive o pianificabili e possono inviare automaticamente agli utenti notifiche sullo stato dei processi tramite la generazione di avvisi, semplificando notevolmente l'amministrazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00c6a-106">Jobs can run repetitive tasks or those that can be scheduled, and they can automatically notify users of job status by generating alerts, thereby greatly simplifying [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administration.</span></span>  
  
 <span data-ttu-id="00c6a-107">È possibile eseguire un processo manualmente oppure configurarlo per l'esecuzione in base a una pianificazione o in risposta ad avvisi.</span><span class="sxs-lookup"><span data-stu-id="00c6a-107">You can run a job manually, or you can configure it to run according to a schedule or in response to alerts.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="00c6a-108">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="00c6a-108">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="00c6a-109">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="00c6a-109">**Description**</span></span>|<span data-ttu-id="00c6a-110">**Argomento**</span><span class="sxs-lookup"><span data-stu-id="00c6a-110">**Topic**</span></span>|  
|<span data-ttu-id="00c6a-111">Contiene informazioni sulla creazione dei processi e sull'assegnazione della proprietà.</span><span class="sxs-lookup"><span data-stu-id="00c6a-111">Contains information about creating jobs and assigning ownership.</span></span>|[<span data-ttu-id="00c6a-112">Creazione di processi</span><span class="sxs-lookup"><span data-stu-id="00c6a-112">Create Jobs</span></span>](create-jobs.md)|  
|<span data-ttu-id="00c6a-113">Contiene informazioni sull'organizzazione dei processi in categorie.</span><span class="sxs-lookup"><span data-stu-id="00c6a-113">Contains information about organizing jobs into categories.</span></span>|[<span data-ttu-id="00c6a-114">organizzare processi</span><span class="sxs-lookup"><span data-stu-id="00c6a-114">Organize Jobs</span></span>](organize-jobs.md)|  
|<span data-ttu-id="00c6a-115">Contiene informazioni sui diversi tipi di passaggi di processo che è possibile creare e sulla rispettiva modalità di gestione.</span><span class="sxs-lookup"><span data-stu-id="00c6a-115">Contains information about the different kinds of job steps you can create and how to manage them.</span></span>|[<span data-ttu-id="00c6a-116">Gestire passaggi di processo</span><span class="sxs-lookup"><span data-stu-id="00c6a-116">Manage Job Steps</span></span>](manage-job-steps.md)|  
|<span data-ttu-id="00c6a-117">Contiene informazioni sulla definizione del momento di avvio dei processi e sulla relativa frequenza di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="00c6a-117">Contains information about how to define when jobs start running and how often they should run.</span></span>|[<span data-ttu-id="00c6a-118">Creazione e collegamento di pianificazioni ai processi</span><span class="sxs-lookup"><span data-stu-id="00c6a-118">Create and Attach Schedules to Jobs</span></span>](create-and-attach-schedules-to-jobs.md)|  
|<span data-ttu-id="00c6a-119">Sono incluse informazioni sull'esecuzione manuale dei processi (senza pianificazione).</span><span class="sxs-lookup"><span data-stu-id="00c6a-119">Contains information about manually running jobs (without a schedule).</span></span>|[<span data-ttu-id="00c6a-120">Esecuzione di processi</span><span class="sxs-lookup"><span data-stu-id="00c6a-120">Run Jobs</span></span>](run-jobs.md)|  
|<span data-ttu-id="00c6a-121">Sono incluse informazioni sulla configurazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent per rispondere ai processi.</span><span class="sxs-lookup"><span data-stu-id="00c6a-121">Contains information about how you can configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to respond to jobs.</span></span> <span data-ttu-id="00c6a-122">È possibile configurare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, ad esempio, in modo da notificare agli amministratori il completamento dei processi.</span><span class="sxs-lookup"><span data-stu-id="00c6a-122">For example, you can configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to notify administrators when jobs are finished.</span></span>|[<span data-ttu-id="00c6a-123">Specifica delle risposte ai processi</span><span class="sxs-lookup"><span data-stu-id="00c6a-123">Specify Job Responses</span></span>](specify-job-responses.md)|  
|<span data-ttu-id="00c6a-124">Contiene informazioni sulla visualizzazione dei processi esistenti e sulla cronologia processo eseguiti, nonché sulle modalità di modifica dei processi.</span><span class="sxs-lookup"><span data-stu-id="00c6a-124">Contains information about how to view existing jobs, their history once executes, and how to modify them.</span></span>|[<span data-ttu-id="00c6a-125">Visualizzare o modificare processi</span><span class="sxs-lookup"><span data-stu-id="00c6a-125">View or Modify Jobs</span></span>](view-or-modify-jobs.md)|  
|<span data-ttu-id="00c6a-126">Contiene informazioni sulla modalità di eliminazione dei processi.</span><span class="sxs-lookup"><span data-stu-id="00c6a-126">Contains information about how to delete jobs.</span></span>|[<span data-ttu-id="00c6a-127">eliminare processi</span><span class="sxs-lookup"><span data-stu-id="00c6a-127">Delete Jobs</span></span>](delete-jobs.md)|  
  
## <a name="see-also"></a><span data-ttu-id="00c6a-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00c6a-128">See Also</span></span>  
 [<span data-ttu-id="00c6a-129">Implementazione della sicurezza di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="00c6a-129">Implement SQL Server Agent Security</span></span>](implement-sql-server-agent-security.md)  
  
  
