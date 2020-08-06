---
title: Editor attività Trasferisci processi (pagina processi) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferjobstask.jobs.f1
helpviewer_keywords:
- Transfer Jobs Task Editor
ms.assetid: e72b1dc7-8cda-4ee6-abb5-d438370f04df
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d2d506da6997965e40d66521f7dccb8218e165fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638463"
---
# <a name="transfer-jobs-task-editor-jobs-page"></a><span data-ttu-id="abef8-102">Editor attività Trasferisci processi (pagina Processi)</span><span class="sxs-lookup"><span data-stu-id="abef8-102">Transfer Jobs Task Editor (Jobs Page)</span></span>
  <span data-ttu-id="abef8-103">Utilizzare la pagina **Processi** della finestra di dialogo **Editor attività Trasferisci processi** per specificare le proprietà relative alla copia di uno o più processi di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent tra due istanze di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="abef8-103">Use the **Jobs** page of the **Transfer Jobs Task Editor** dialog box to specify properties for copying one or more [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs from one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to another.</span></span> <span data-ttu-id="abef8-104">Per ulteriori informazioni sull'attività Trasferisci processi, vedere [Transfer Jobs Task](control-flow/transfer-jobs-task.md).</span><span class="sxs-lookup"><span data-stu-id="abef8-104">For more information about the Transfer Jobs task, see [Transfer Jobs Task](control-flow/transfer-jobs-task.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="abef8-105">Per accedere ai processi nel server di origine, l'utente deve essere un membro almeno del ruolo predefinito del database **SQLAgentUserRole** nel server.</span><span class="sxs-lookup"><span data-stu-id="abef8-105">To access jobs on the source server, users must be a member of at least the **SQLAgentUserRole** fixed database role on the server.</span></span> <span data-ttu-id="abef8-106">Per creare processi nel server di destinazione, l'utente deve essere un membro del ruolo predefinito del server **sysadmin** o di uno dei ruoli predefiniti del database di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="abef8-106">To successfully create jobs on the destination server, the user must be a member of the **sysadmin** fixed server role or one of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent fixed database roles.</span></span> <span data-ttu-id="abef8-107">Per altre informazioni sui ruoli predefiniti del database di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent e sulle relative autorizzazioni, vedere [Ruoli di database predefiniti di SQL Server Agent](../ssms/agent/sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="abef8-107">For more information about [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent fixed database roles and their permissions, see [SQL Server Agent Fixed Database Roles](../ssms/agent/sql-server-agent-fixed-database-roles.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="abef8-108">Opzioni</span><span class="sxs-lookup"><span data-stu-id="abef8-108">Options</span></span>  
 <span data-ttu-id="abef8-109">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="abef8-109">**SourceConnection**</span></span>  
 <span data-ttu-id="abef8-110">Selezionare una gestione connessione SMO nell'elenco oppure fare clic su **\<New connection...>** per creare una nuova connessione al server di origine.</span><span class="sxs-lookup"><span data-stu-id="abef8-110">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="abef8-111">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="abef8-111">**DestinationConnection**</span></span>  
 <span data-ttu-id="abef8-112">Selezionare una gestione connessione SMO nell'elenco oppure fare clic su **\<New connection...>** per creare una nuova connessione al server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="abef8-112">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="abef8-113">**TransferAllJobs**</span><span class="sxs-lookup"><span data-stu-id="abef8-113">**TransferAllJobs**</span></span>  
 <span data-ttu-id="abef8-114">Indicare se l'attività deve copiare dal server di origine nel server di destinazione tutti i processi di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent o solo quelli specificati.</span><span class="sxs-lookup"><span data-stu-id="abef8-114">Select whether the task should copy all or only the specified [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs from the source to the destination server.</span></span>  
  
 <span data-ttu-id="abef8-115">Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="abef8-115">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="abef8-116">valore</span><span class="sxs-lookup"><span data-stu-id="abef8-116">Value</span></span>|<span data-ttu-id="abef8-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="abef8-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="abef8-118">**True**</span><span class="sxs-lookup"><span data-stu-id="abef8-118">**True**</span></span>|<span data-ttu-id="abef8-119">Copia tutti i processi.</span><span class="sxs-lookup"><span data-stu-id="abef8-119">Copy all jobs.</span></span>|  
|<span data-ttu-id="abef8-120">**False**</span><span class="sxs-lookup"><span data-stu-id="abef8-120">**False**</span></span>|<span data-ttu-id="abef8-121">Copia solo i processi specificati.</span><span class="sxs-lookup"><span data-stu-id="abef8-121">Copy only the specified jobs.</span></span>|  
  
 <span data-ttu-id="abef8-122">**JobsList**</span><span class="sxs-lookup"><span data-stu-id="abef8-122">**JobsList**</span></span>  
 <span data-ttu-id="abef8-123">Fare clic sul pulsante con i puntini di sospensione **(...)** per selezionare i processi da copiare.</span><span class="sxs-lookup"><span data-stu-id="abef8-123">Click the browse button **(...)** to select the jobs to copy.</span></span> <span data-ttu-id="abef8-124">È necessario selezionare almeno un processo.</span><span class="sxs-lookup"><span data-stu-id="abef8-124">At least one job must be selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="abef8-125">Prima di selezionare i processi da copiare, specificare la proprietà **SourceConnection** .</span><span class="sxs-lookup"><span data-stu-id="abef8-125">Specify the **SourceConnection** before selecting jobs to copy.</span></span>  
  
 <span data-ttu-id="abef8-126">Quando la proprietà **TransferAllJobs** è impostata su **True** , l'opzione **JobsList**non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="abef8-126">The **JobsList** option is unavailable when **TransferAllJobs** is set to **True**.</span></span>  
  
 <span data-ttu-id="abef8-127">**IfObjectExists**</span><span class="sxs-lookup"><span data-stu-id="abef8-127">**IfObjectExists**</span></span>  
 <span data-ttu-id="abef8-128">Indicare la modalità con cui l'attività deve gestire i processi che hanno lo stesso nome di processi già esistenti nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="abef8-128">Select how the task should handle jobs of the same name that already exist on the destination server.</span></span>  
  
 <span data-ttu-id="abef8-129">Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="abef8-129">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="abef8-130">valore</span><span class="sxs-lookup"><span data-stu-id="abef8-130">Value</span></span>|<span data-ttu-id="abef8-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="abef8-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="abef8-132">**FailTask**</span><span class="sxs-lookup"><span data-stu-id="abef8-132">**FailTask**</span></span>|<span data-ttu-id="abef8-133">L'attività viene interrotta se nel server di destinazione esistono processi con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="abef8-133">Task fails if jobs of the same name already exist on the destination server.</span></span>|  
|<span data-ttu-id="abef8-134">**Overwrite**</span><span class="sxs-lookup"><span data-stu-id="abef8-134">**Overwrite**</span></span>|<span data-ttu-id="abef8-135">L'attività sovrascrive i processi con lo stesso nome che si trovano nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="abef8-135">Task overwrites jobs of the same name on the destination server.</span></span>|  
|<span data-ttu-id="abef8-136">**Skip**</span><span class="sxs-lookup"><span data-stu-id="abef8-136">**Skip**</span></span>|<span data-ttu-id="abef8-137">L'attività ignora i processi con lo stesso nome che si trovano nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="abef8-137">Task skips jobs of the same name that exist on the destination server.</span></span>|  
  
 <span data-ttu-id="abef8-138">**EnableJobsAtDestination**</span><span class="sxs-lookup"><span data-stu-id="abef8-138">**EnableJobsAtDestination**</span></span>  
 <span data-ttu-id="abef8-139">Specificare se i processi copiati nel server di destinazione devono essere attivati.</span><span class="sxs-lookup"><span data-stu-id="abef8-139">Select whether the jobs copied to the destination server should be enabled.</span></span>  
  
 <span data-ttu-id="abef8-140">Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="abef8-140">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="abef8-141">valore</span><span class="sxs-lookup"><span data-stu-id="abef8-141">Value</span></span>|<span data-ttu-id="abef8-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="abef8-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="abef8-143">**True**</span><span class="sxs-lookup"><span data-stu-id="abef8-143">**True**</span></span>|<span data-ttu-id="abef8-144">Attiva i processi nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="abef8-144">Enable jobs on destination server.</span></span>|  
|<span data-ttu-id="abef8-145">**False**</span><span class="sxs-lookup"><span data-stu-id="abef8-145">**False**</span></span>|<span data-ttu-id="abef8-146">Disabilita i processi nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="abef8-146">Disable jobs on destination server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="abef8-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="abef8-147">See Also</span></span>  
 <span data-ttu-id="abef8-148">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="abef8-148">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="abef8-149">[Attività di Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="abef8-149">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="abef8-150">[Editor attività Trasferisci processi &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="abef8-150">[Transfer Jobs Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="abef8-151">[Pagina Espressioni](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="abef8-151">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="abef8-152">Gestione connessione SMO</span><span class="sxs-lookup"><span data-stu-id="abef8-152">SMO Connection Manager</span></span>](connection-manager/smo-connection-manager.md)  
  
  
