---
title: Eliminare processi | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- delete jobs
ms.assetid: bffb915e-bc84-4417-aa35-183243ca3312
author: stevestein
ms.author: sstein
ms.openlocfilehash: f66387a1334f91c29b8edddad293d76064430b39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722200"
---
# <a name="delete-jobs"></a><span data-ttu-id="cdd97-102">eliminare processi</span><span class="sxs-lookup"><span data-stu-id="cdd97-102">Delete Jobs</span></span>
  <span data-ttu-id="cdd97-103">Un processo è una serie specificata di operazioni eseguite in sequenza tramite SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="cdd97-103">A job is a specified series of operations performed sequentially by SQL Server Agent.</span></span> <span data-ttu-id="cdd97-104">Per impostazione predefinita, i processi non vengono eliminati al termine dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cdd97-104">By default, jobs are not deleted when execution finishes.</span></span> <span data-ttu-id="cdd97-105">È possibile eliminare uno o più processi di [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, indipendentemente dall'esito positivo o negativo del processo.</span><span class="sxs-lookup"><span data-stu-id="cdd97-105">You can delete one or more [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs regardless of success or failure of the job.</span></span> <span data-ttu-id="cdd97-106">È inoltre possibile configurare [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent per eliminare automaticamente determinati processi in caso di esito positivo, esito negativo o completamento.</span><span class="sxs-lookup"><span data-stu-id="cdd97-106">You can also configure [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to automatically delete jobs when they succeed, fail, or complete.</span></span>  
  
 <span data-ttu-id="cdd97-107">Per impostazione predefinita, i membri del ruolo predefinito del server **sysadmin** possono eseguire il [Sp_delete_job &#40;sistema Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-job-transact-sql) stored procedure per eliminare un processo.</span><span class="sxs-lookup"><span data-stu-id="cdd97-107">By default, members of the **sysadmin** fixed server role can execute the [sp_delete_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-job-transact-sql) system stored procedure to delete a job.</span></span> <span data-ttu-id="cdd97-108">Gli altri utenti devono essere membri di uno dei ruoli predefiniti del database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent seguenti nel database **msdb** :</span><span class="sxs-lookup"><span data-stu-id="cdd97-108">Other users must be granted one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the **msdb** database:</span></span>  
  
-   <span data-ttu-id="cdd97-109">**SQLAgentUserRole**</span><span class="sxs-lookup"><span data-stu-id="cdd97-109">**SQLAgentUserRole**</span></span>  
  
-   <span data-ttu-id="cdd97-110">**SQLAgentReaderRole**</span><span class="sxs-lookup"><span data-stu-id="cdd97-110">**SQLAgentReaderRole**</span></span>  
  
-   <span data-ttu-id="cdd97-111">**SQLAgentOperatorRole**</span><span class="sxs-lookup"><span data-stu-id="cdd97-111">**SQLAgentOperatorRole**</span></span>  
  
 <span data-ttu-id="cdd97-112">Per informazioni dettagliate sulle autorizzazioni di questi ruoli, vedere [Ruoli di database predefiniti di SQL Server Agent](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="cdd97-112">For details about the permissions of these roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
 <span data-ttu-id="cdd97-113">I membri del ruolo predefinito del server **sysadmin** possono eseguire **sp_delete_job** per l'eliminazione di qualsiasi processo.</span><span class="sxs-lookup"><span data-stu-id="cdd97-113">Members of the **sysadmin** fixed server role can execute **sp_delete_job** to delete any job.</span></span> <span data-ttu-id="cdd97-114">Se un utente non è un membro del ruolo predefinito del server **sysadmin** , può eliminare solo i processi di sua proprietà.</span><span class="sxs-lookup"><span data-stu-id="cdd97-114">A user that is not a member of the **sysadmin** fixed server role can only delete jobs owned by that user.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="cdd97-115">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="cdd97-115">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cdd97-116">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="cdd97-116">**Description**</span></span>|<span data-ttu-id="cdd97-117">**Argomento**</span><span class="sxs-lookup"><span data-stu-id="cdd97-117">**Topic**</span></span>|  
|<span data-ttu-id="cdd97-118">Informazioni su come eliminare uno o più processi di [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="cdd97-118">Describes how to delete one or more [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span>|[<span data-ttu-id="cdd97-119">Eliminare uno o più processi</span><span class="sxs-lookup"><span data-stu-id="cdd97-119">Delete One or More Jobs</span></span>](delete-one-or-more-jobs.md)|  
|<span data-ttu-id="cdd97-120">Informazioni su come configurare [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent per eliminare automaticamente determinati processi in caso di esito positivo, esito negativo o completamento.</span><span class="sxs-lookup"><span data-stu-id="cdd97-120">Describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to automatically delete jobs when they succeed, fail, or complete.</span></span>|[<span data-ttu-id="cdd97-121">Automatically Delete a Job</span><span class="sxs-lookup"><span data-stu-id="cdd97-121">Automatically Delete a Job</span></span>](automatically-delete-a-job.md)|  
  
  
