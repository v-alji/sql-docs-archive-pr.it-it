---
title: Creare processi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], creating
- SQL Server Agent jobs, creating
ms.assetid: 465fb7fc-7622-4252-a178-ea51691c935b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 706b9348eed5b190f99543a74e7019dc1bde5978
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715048"
---
# <a name="create-jobs"></a><span data-ttu-id="5f816-102">Crea processi</span><span class="sxs-lookup"><span data-stu-id="5f816-102">Create Jobs</span></span>
  <span data-ttu-id="5f816-103">Un processo include una serie di operazioni specificate eseguite in sequenza da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="5f816-103">A job is a specified series of operations performed sequentially by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="5f816-104">Tramite un processo è possibile eseguire un'ampia gamma di attività, inclusa l'esecuzione di script [!INCLUDE[tsql](../../includes/tsql-md.md)] , applicazioni da riga di comando, script Microsoft ActiveX, pacchetti Integration Services, comandi e query di Analysis Services o attività di replica.</span><span class="sxs-lookup"><span data-stu-id="5f816-104">A job can perform a wide range of activities, including running [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, command prompt applications, Microsoft ActiveX scripts, Integration Services packages, Analysis Services commands and queries, or Replication tasks.</span></span> <span data-ttu-id="5f816-105">I processi possono eseguire attività ripetitive o pianificabili e inviare agli utenti notifiche automatiche sullo stato del processo tramite la generazione di avvisi, semplificando significativamente l'amministrazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5f816-105">Jobs can run repetitive or schedulable tasks, and they can automatically notify users of job status by generating alerts, thereby greatly simplifying [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administration.</span></span>  
  
 <span data-ttu-id="5f816-106">Per creare un processo, è necessario che l'utente sia membro di uno dei ruoli predefiniti del database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent o del ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="5f816-106">To create a job, a user must be a member of one of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles or the **sysadmin** fixed server role.</span></span> <span data-ttu-id="5f816-107">Un processo può essere modificato solo dal proprietario o dai membri del ruolo **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="5f816-107">A job can be edited only by its owner or members of the **sysadmin** role.</span></span> <span data-ttu-id="5f816-108">I membri del ruolo **sysadmin** possono assegnare la proprietà di un processo ad altri utenti ed eseguire qualsiasi processo, indipendentemente dal proprietario.</span><span class="sxs-lookup"><span data-stu-id="5f816-108">Members of the **sysadmin** role can assign job ownership to other users, and they can run any job, regardless of the job owner.</span></span> <span data-ttu-id="5f816-109">Per altre informazioni sui ruoli predefiniti del database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, vedere [Ruoli di database predefiniti di SQL Server Agent](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="5f816-109">For more information about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
 <span data-ttu-id="5f816-110">È possibile creare processi da eseguire nell'istanza locale di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oppure in più istanze all'interno di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5f816-110">Jobs can be written to run on the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or on multiple instances across an enterprise.</span></span> <span data-ttu-id="5f816-111">Per eseguire i processi in più server, è necessario impostare almeno un server master e uno o più server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5f816-111">To run jobs on multiple servers, you must set up at least one master server and one or more target servers.</span></span> <span data-ttu-id="5f816-112">Per altre informazioni sui server master e di destinazione, vedere [Amministrazione automatizzata in un'organizzazione](automated-administration-across-an-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="5f816-112">For more information about master and target servers, see [Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md)</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5f816-113">Agent registra i dati relativi al processo e ai passaggi di processo nella cronologia del processo.</span><span class="sxs-lookup"><span data-stu-id="5f816-113">Agent records job and job step information in the job history.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="5f816-114">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="5f816-114">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5f816-115">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="5f816-115">**Description**</span></span>|<span data-ttu-id="5f816-116">**Argomento**</span><span class="sxs-lookup"><span data-stu-id="5f816-116">**Topic**</span></span>|  
|<span data-ttu-id="5f816-117">Viene illustrato come creare un processo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="5f816-117">Describes how to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>|[<span data-ttu-id="5f816-118">Creazione di un processo</span><span class="sxs-lookup"><span data-stu-id="5f816-118">Create a Job</span></span>](create-a-job.md)|  
|<span data-ttu-id="5f816-119">Viene descritto come riassegnare la proprietà dei processi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent a un altro utente.</span><span class="sxs-lookup"><span data-stu-id="5f816-119">Describes how to reassign ownership of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs to another user.</span></span>|[<span data-ttu-id="5f816-120">Give Others Ownership of a Job</span><span class="sxs-lookup"><span data-stu-id="5f816-120">Give Others Ownership of a Job</span></span>](give-others-ownership-of-a-job.md)|  
|<span data-ttu-id="5f816-121">Viene descritto come impostare il log di cronologia processi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="5f816-121">Describes how to set up the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history log.</span></span>|[<span data-ttu-id="5f816-122">Impostare il log di cronologia processi</span><span class="sxs-lookup"><span data-stu-id="5f816-122">Set Up the Job History Log</span></span>](set-up-the-job-history-log.md)|  
  
## <a name="see-also"></a><span data-ttu-id="5f816-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f816-123">See Also</span></span>  
 <span data-ttu-id="5f816-124">[Gestire passaggi di processo](manage-job-steps.md) </span><span class="sxs-lookup"><span data-stu-id="5f816-124">[Manage Job Steps](manage-job-steps.md) </span></span>  
 <span data-ttu-id="5f816-125">[Amministrazione automatizzata in un'organizzazione](automated-administration-across-an-enterprise.md) </span><span class="sxs-lookup"><span data-stu-id="5f816-125">[Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md) </span></span>  
 <span data-ttu-id="5f816-126">[Creazione e alconnessione di pianificazioni ai processi](create-and-attach-schedules-to-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="5f816-126">[Create and Attach Schedules to Jobs](create-and-attach-schedules-to-jobs.md) </span></span>  
 <span data-ttu-id="5f816-127">[Esegui processi](run-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="5f816-127">[Run Jobs](run-jobs.md) </span></span>  
 [<span data-ttu-id="5f816-128">Visualizzare o modificare processi</span><span class="sxs-lookup"><span data-stu-id="5f816-128">View or Modify Jobs</span></span>](view-or-modify-jobs.md)  
  
  
