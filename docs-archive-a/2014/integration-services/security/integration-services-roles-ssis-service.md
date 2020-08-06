---
title: Ruoli di Integration Services (servizio SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- security [Integration Services], roles
- db_ssisoperator role
- db_ssisadmin role
- fixed database roles [Integration Services]
- packages [Integration Services], security
- roles [Integration Services]
- db_ssisltduser role
ms.assetid: 9702e90c-fada-4978-a473-1b1423017d80
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5bc65a7a3ff30deb429ceeb8458ac477432a758c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626127"
---
# <a name="integration-services-roles-ssis-service"></a><span data-ttu-id="7f3e6-102">Ruoli Integration Services (servizio SSIS)</span><span class="sxs-lookup"><span data-stu-id="7f3e6-102">Integration Services Roles (SSIS Service)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="7f3e6-103">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]include i tre ruoli predefiniti a livello di database, `db_ssisadmin` , **db_ssisltduser**e **db_ssisoperator**, per il controllo dell'accesso ai pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-103">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes the three fixed database-level roles, `db_ssisadmin`, **db_ssisltduser**, and **db_ssisoperator**, for controlling access to packages.</span></span> <span data-ttu-id="7f3e6-104">I ruoli possono essere implementati solo nei pacchetti salvati `msdb` nel database in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7f3e6-104">Roles can be implemented only on packages that are saved to the `msdb` database in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7f3e6-105">I ruoli vengono assegnati a un pacchetto in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f3e6-105">You assign roles to a package using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="7f3e6-106">Le assegnazioni di ruolo vengono salvate nel `msdb` database.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-106">The role assignments are saved to the `msdb` database.</span></span>  
  
## <a name="read-and-write-actions"></a><span data-ttu-id="7f3e6-107">Azioni di lettura e scrittura</span><span class="sxs-lookup"><span data-stu-id="7f3e6-107">Read and Write Actions</span></span>  
 <span data-ttu-id="7f3e6-108">La tabella seguente descrive le azioni di lettura e scrittura di Windows e i ruoli predefiniti del database in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f3e6-108">The following table describes the read and write actions of Windows and fixed database-level roles in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span>  
  
|<span data-ttu-id="7f3e6-109">Ruolo</span><span class="sxs-lookup"><span data-stu-id="7f3e6-109">Role</span></span>|<span data-ttu-id="7f3e6-110">Azione di lettura</span><span class="sxs-lookup"><span data-stu-id="7f3e6-110">Read action</span></span>|<span data-ttu-id="7f3e6-111">Azione di scrittura</span><span class="sxs-lookup"><span data-stu-id="7f3e6-111">Write action</span></span>|  
|----------|-----------------|------------------|  
|`db_ssisadmin`<br /><br /> <span data-ttu-id="7f3e6-112">oppure</span><span class="sxs-lookup"><span data-stu-id="7f3e6-112">or</span></span><br /><br /> `sysadmin`|<span data-ttu-id="7f3e6-113">Enumerazione dei propri pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-113">Enumerate own packages.</span></span><br /><br /> <span data-ttu-id="7f3e6-114">Enumerazione di tutti i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-114">Enumerate all packages.</span></span><br /><br /> <span data-ttu-id="7f3e6-115">Visualizzazione dei propri pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-115">View own packages.</span></span><br /><br /> <span data-ttu-id="7f3e6-116">Visualizzazione di tutti i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-116">View all packages.</span></span><br /><br /> <span data-ttu-id="7f3e6-117">Esecuzione dei propri pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-117">Execute own packages.</span></span><br /><br /> <span data-ttu-id="7f3e6-118">Esecuzione di tutti i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-118">Execute all packages.</span></span><br /><br /> <span data-ttu-id="7f3e6-119">Esportazione dei propri pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-119">Export own packages.</span></span><br /><br /> <span data-ttu-id="7f3e6-120">Esportazione di tutti i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-120">Export all packages.</span></span><br /><br /> <span data-ttu-id="7f3e6-121">Esecuzione di tutti i pacchetti in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-121">Execute all packages in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>|<span data-ttu-id="7f3e6-122">Importazione di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-122">Import packages.</span></span><br /><br /> <span data-ttu-id="7f3e6-123">Eliminazione dei propri pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-123">Delete own packages.</span></span><br /><br /> <span data-ttu-id="7f3e6-124">Eliminazione di tutti i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-124">Delete all packages.</span></span><br /><br /> <span data-ttu-id="7f3e6-125">Modifica dei propri ruoli di pacchetto.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-125">Change own package roles.</span></span><br /><br /> <span data-ttu-id="7f3e6-126">Modifica di tutti i ruoli di pacchetto.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-126">Change all package roles.</span></span><br /><br /> <br /><br /> <span data-ttu-id="7f3e6-127">I membri \*\* \* \* \* importanti \* \*\* del ruolo db_ssisadmin e il ruolo dc_admin potrebbero essere in grado di elevare i propri privilegi a sysadmin.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-127">**\*\* Important \*\*** Members of the db_ssisadmin role and the dc_admin role may be able to elevate their privileges to sysadmin.</span></span> <span data-ttu-id="7f3e6-128">Questa elevazione dei privilegi può verificarsi perché tali ruoli possono modificare i pacchetti [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] e i pacchetti [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] possono essere eseguiti da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzando il contesto di sicurezza sysadmin di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-128">This elevation of privilege can occur because these roles can modify [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages can be executed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the sysadmin security context of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="7f3e6-129">Per impedire questa elevazione dei privilegi durante l'esecuzione dei piani di manutenzione, set di raccolta dati e altri pacchetti [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , configurare i processi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent che eseguono pacchetti in modo da utilizzare un account proxy con privilegi limitati o aggiungere solo i membri sysadmin ai ruoli db_ssisadmin e dc_admin.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-129">To guard against this elevation of privilege when running maintenance plans, data collection sets, and other [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs that run packages to use a proxy account with limited privileges or only add sysadmin members to the db_ssisadmin and dc_admin roles.</span></span>|  
|<span data-ttu-id="7f3e6-130">**db_ssisltduser**</span><span class="sxs-lookup"><span data-stu-id="7f3e6-130">**db_ssisltduser**</span></span>|<span data-ttu-id="7f3e6-131">Enumerazione dei propri pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-131">Enumerate own packages.</span></span><br /><br /> <span data-ttu-id="7f3e6-132">Enumerazione di tutti i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-132">Enumerate all packages.</span></span><br /><br /> <span data-ttu-id="7f3e6-133">Visualizzazione dei propri pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-133">View own packages.</span></span><br /><br /> <span data-ttu-id="7f3e6-134">Esecuzione dei propri pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-134">Execute own packages.</span></span><br /><br /> <span data-ttu-id="7f3e6-135">Esportazione dei propri pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-135">Export own packages.</span></span>|<span data-ttu-id="7f3e6-136">Importazione di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-136">Import packages.</span></span><br /><br /> <span data-ttu-id="7f3e6-137">Eliminazione dei propri pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-137">Delete own packages.</span></span><br /><br /> <span data-ttu-id="7f3e6-138">Modifica dei propri ruoli di pacchetto.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-138">Change own package roles.</span></span>|  
|<span data-ttu-id="7f3e6-139">**db_ssisoperator**</span><span class="sxs-lookup"><span data-stu-id="7f3e6-139">**db_ssisoperator**</span></span>|<span data-ttu-id="7f3e6-140">Enumerazione di tutti i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-140">Enumerate all packages.</span></span><br /><br /> <span data-ttu-id="7f3e6-141">Visualizzazione di tutti i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-141">View all packages.</span></span><br /><br /> <span data-ttu-id="7f3e6-142">Esecuzione di tutti i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-142">Execute all packages.</span></span><br /><br /> <span data-ttu-id="7f3e6-143">Esportazione di tutti i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-143">Export all packages.</span></span><br /><br /> <span data-ttu-id="7f3e6-144">Esecuzione di tutti i pacchetti in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-144">Execute all packages in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>|<span data-ttu-id="7f3e6-145">Nessuno</span><span class="sxs-lookup"><span data-stu-id="7f3e6-145">None</span></span>|  
|<span data-ttu-id="7f3e6-146">**Amministratori di Windows**</span><span class="sxs-lookup"><span data-stu-id="7f3e6-146">**Windows administrators**</span></span>|<span data-ttu-id="7f3e6-147">Visualizzazione delle informazioni di esecuzione di tutti i pacchetti in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-147">View execution details of all running packages.</span></span>|<span data-ttu-id="7f3e6-148">Arresto di tutti i pacchetti in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-148">Stop all currently running packages.</span></span>|  
  
## <a name="sysssispackages-table"></a><span data-ttu-id="7f3e6-149">Tabella Sysssispackages</span><span class="sxs-lookup"><span data-stu-id="7f3e6-149">Sysssispackages Table</span></span>  
 <span data-ttu-id="7f3e6-150">La tabella **sysssispackages** in `msdb` contiene i pacchetti salvati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7f3e6-150">The **sysssispackages** table in `msdb` contains the packages that are saved to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7f3e6-151">Per altre informazioni, vedere [sysssispackages &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/sysssispackages-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7f3e6-151">For more information, see [sysssispackages &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/sysssispackages-transact-sql).</span></span>  
  
 <span data-ttu-id="7f3e6-152">Le colonne della tabella **sysssispackages** contengono informazioni sui ruoli assegnati ai pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-152">The **sysssispackages** table includes columns that contain information about the roles that are assigned to packages.</span></span>  
  
-   <span data-ttu-id="7f3e6-153">Nella colonna **readerrole** è indicato il ruolo con accesso in lettura al pacchetto.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-153">The **readerrole** column specifies the role that has read access to the package.</span></span>  
  
-   <span data-ttu-id="7f3e6-154">Nella colonna **writerrole** è indicato il ruolo con accesso in scrittura al pacchetto.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-154">The **writerrole** column specifies the role that has write access to the package.</span></span>  
  
-   <span data-ttu-id="7f3e6-155">La colonna **ownersid** include l'ID di sicurezza (SID) univoco dell'utente che ha creato il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-155">The **ownersid** column contains the unique security identifier of the user who created the package.</span></span> <span data-ttu-id="7f3e6-156">Questa colonna definisce pertanto il proprietario del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-156">This column defines the owner of the package.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="7f3e6-157">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="7f3e6-157">Permissions</span></span>  
 <span data-ttu-id="7f3e6-158">Per impostazione predefinita, le autorizzazioni del `db_ssisadmin` e **db_ssisoperator** i ruoli predefiniti a livello di database e l'ID di sicurezza univoco dell'utente che ha creato il pacchetto si applicano al ruolo lettore per i pacchetti, mentre le autorizzazioni del `db_ssisadmin` ruolo e l'ID di sicurezza univoco dell'utente che ha creato il pacchetto si applicano al ruolo writer.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-158">By default, the permissions of the `db_ssisadmin` and **db_ssisoperator** fixed database-level roles and the unique security identifier of the user who created the package apply to the reader role for packages, and the permissions of the `db_ssisadmin` role and the unique security identifier of the user who created the package apply to the writer role.</span></span> <span data-ttu-id="7f3e6-159">`db_ssisadmin`Per disporre dell'accesso in lettura al pacchetto, un utente deve essere un membro del ruolo, **db_ssisltduser**o **db_ssisoperator** .</span><span class="sxs-lookup"><span data-stu-id="7f3e6-159">A user must be a member of the `db_ssisadmin`, **db_ssisltduser**, or **db_ssisoperator** role to have read access to the package.</span></span> <span data-ttu-id="7f3e6-160">Un utente deve essere membro del `db_ssisadmin` ruolo per avere accesso in scrittura.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-160">A user must be a member of the `db_ssisadmin` role to have write access.</span></span>  
  
## <a name="access-to-packages"></a><span data-ttu-id="7f3e6-161">Accesso ai pacchetti</span><span class="sxs-lookup"><span data-stu-id="7f3e6-161">Access to Packages</span></span>  
 <span data-ttu-id="7f3e6-162">I ruoli predefiniti del database funzionano congiuntamente ai ruoli definiti dall'utente,</span><span class="sxs-lookup"><span data-stu-id="7f3e6-162">The fixed database-level roles work in conjunction with user-defined roles.</span></span> <span data-ttu-id="7f3e6-163">ovvero i ruoli creati dall'utente in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e usati per l'assegnazione di autorizzazioni ai pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-163">The user-defined roles are the roles that you create in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and then use to assign permissions to packages.</span></span> <span data-ttu-id="7f3e6-164">Per poter accedere a un pacchetto, un utente deve essere membro del ruolo definito dall'utente e del ruolo predefinito del database di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] appropriato.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-164">To access a package, a user must be a member of the user-defined role and the pertinent [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] fixed database-level role.</span></span> <span data-ttu-id="7f3e6-165">Se, ad esempio, gli utenti sono membri del ruolo definito dall'utente **AuditUsers** assegnato a un pacchetto, devono essere anche membri del `db_ssisadmin` ruolo, **db_ssisltduser**o **db_ssisoperator** per disporre dell'accesso in lettura al pacchetto.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-165">For example, if users are members of the **AuditUsers** user-defined role that is assigned to a package, they must also be members of `db_ssisadmin`, **db_ssisltduser**, or **db_ssisoperator** role to have read access to the package.</span></span>  
  
 <span data-ttu-id="7f3e6-166">Se non si assegna alcun ruolo definito dall'utente ai pacchetti, l'accesso verrà determinato dai ruoli predefiniti a livello di database.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-166">If you do not assign user-defined roles to packages, access to packages is determined by the fixed database-level roles.</span></span>  
  
 <span data-ttu-id="7f3e6-167">Se si desidera utilizzare ruoli definiti dall'utente, è necessario aggiungerli al `msdb` database prima di poterli assegnare ai pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-167">If you want to use user-defined roles, you must add them to the `msdb` database before you can assign them to packages.</span></span> <span data-ttu-id="7f3e6-168">È possibile creare nuovi ruoli del database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f3e6-168">You can create new database roles in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="7f3e6-169">I ruoli a livello di database di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] concedono diritti per le tabelle di sistema di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] nel database msdb.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-169">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] database-level roles grant rights on the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] system tables in the msdb database.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="7f3e6-170">per potersi connettere al motore di database e accedere al database, è necessario avviare il servizio MSSQLSERVER `msdb` .</span><span class="sxs-lookup"><span data-stu-id="7f3e6-170">(the MSSQLSERVER service) must be started before you can connect to the Database Engine and access the `msdb` database.</span></span>  
  
 <span data-ttu-id="7f3e6-171">Per assegnare ruoli ai pacchetti, è necessario completare le attività seguenti.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-171">To assign roles to packages, you need to complete the following tasks.</span></span>  
  
-   <span data-ttu-id="7f3e6-172">**Aprire Esplora oggetti e connettersi a Integration Services**</span><span class="sxs-lookup"><span data-stu-id="7f3e6-172">**Open Object Explorer and Connect to Integration Services**</span></span>  
  
     <span data-ttu-id="7f3e6-173">Per poter assegnare ruoli ai pacchetti in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], è necessario aprire Esplora oggetti in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e connettersi a [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f3e6-173">Before you can assign roles to packages by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you must open Object Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="7f3e6-174">Per poter eseguire la connessione a [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , è necessario che il servizio [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]sia stato avviato.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-174">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service must be started before you can connect to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="7f3e6-175">**Assegnazione dei ruoli lettura e scrittura ai pacchetti**</span><span class="sxs-lookup"><span data-stu-id="7f3e6-175">**Assign Reader and Writer Roles to Packages**</span></span>  
  
     <span data-ttu-id="7f3e6-176">È possibile assegnare un ruolo lettura o scrittura a ogni pacchetto.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-176">You can assign a reader and a writer role to each package.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="7f3e6-177">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="7f3e6-177">Related Tasks</span></span>  
  
-   [<span data-ttu-id="7f3e6-178">Assegnazione di un ruolo lettura e scrittura a un pacchetto</span><span class="sxs-lookup"><span data-stu-id="7f3e6-178">Assign a Reader and Writer Role to a Package</span></span>](../assign-a-reader-and-writer-role-to-a-package.md)  
  
-   [<span data-ttu-id="7f3e6-179">Creazione di un ruolo definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="7f3e6-179">Create a User-Defined Role</span></span>](../create-a-user-defined-role.md)  
  
-   [<span data-ttu-id="7f3e6-180">Connessione a Integration Services</span><span class="sxs-lookup"><span data-stu-id="7f3e6-180">Connect to Integration Services</span></span>](../connect-to-integration-services.md)  
  
  