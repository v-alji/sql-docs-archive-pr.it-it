---
title: Usare Resource Governor per limitare l'utilizzo della CPU da parte della compressione dei backup (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup compression [SQL Server], Resource Governor
- backup compression [SQL Server], CPU usage
- compression [SQL Server], backup compression
- backups [SQL Server], compression
- Resource Governor, backup compression
ms.assetid: 01796551-578d-4425-9b9e-d87210f7ba72
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 19a95cfa5c6780fbdf71ae58bd141aa9aa351efa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725992"
---
# <a name="use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql"></a><span data-ttu-id="e70ec-102">Utilizzo di Resource Governor per limitare l'utilizzo della CPU da parte della compressione dei backup (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e70ec-102">Use Resource Governor to Limit CPU Usage by Backup Compression (Transact-SQL)</span></span>
  <span data-ttu-id="e70ec-103">Per impostazione predefinita, l'esecuzione di backup mediante la compressione aumenta in modo significativo l'utilizzo della CPU e la CPU aggiuntiva utilizzata dal processo di compressione può avere un impatto negativo sulle operazioni simultanee.</span><span class="sxs-lookup"><span data-stu-id="e70ec-103">By default, backing up using compression significantly increases CPU usage, and the additional CPU consumed by the compression process can adversely impact concurrent operations.</span></span> <span data-ttu-id="e70ec-104">È necessario quindi creare un backup compresso con priorità bassa in una sessione con utilizzo della CPU limitato da[Resource Governor](../resource-governor/resource-governor.md) nel caso in cui si verifichi una contesa di CPU.</span><span class="sxs-lookup"><span data-stu-id="e70ec-104">Therefore, you might want to create a low-priority compressed backup in a session whose CPU usage is limited by[Resource Governor](../resource-governor/resource-governor.md) when CPU contention occurs.</span></span> <span data-ttu-id="e70ec-105">In questo argomento viene presentato uno scenario che classifica le sessioni di un particolare utente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eseguendone mapping a un gruppo del carico di lavoro di Resource Governor che limita l'utilizzo della CPU in tali casi.</span><span class="sxs-lookup"><span data-stu-id="e70ec-105">This topic presents a scenario that classifies the sessions of a particular [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user by mapping them to a Resource Governor workload group that limits CPU usage in such cases.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e70ec-106">In uno scenario di Resource Governor specifico la classificazione della sessione potrebbe essere basata su un nome utente, un nome di applicazione o qualsiasi altro elemento in grado di differenziare una connessione.</span><span class="sxs-lookup"><span data-stu-id="e70ec-106">In a given Resource Governor scenario, session classification might be based on a user name, an application name, or anything else that can differentiate a connection.</span></span> <span data-ttu-id="e70ec-107">Per ulteriori informazioni, vedere [Resource Governor Classifier Function](../resource-governor/resource-governor-classifier-function.md) e [Resource Governor Workload Group](../resource-governor/resource-governor-workload-group.md).</span><span class="sxs-lookup"><span data-stu-id="e70ec-107">For more information, see [Resource Governor Classifier Function](../resource-governor/resource-governor-classifier-function.md) and [Resource Governor Workload Group](../resource-governor/resource-governor-workload-group.md).</span></span>  
  
##  <a name="this-topic-contains-the-following-set-of-scenarios-which-are-presented-in-sequence"></a><a name="Top"></a> <span data-ttu-id="e70ec-108">In questo argomento è contenuto il set seguente di scenari, che vengono presentati in sequenza:</span><span class="sxs-lookup"><span data-stu-id="e70ec-108">This topic contains the following set of scenarios, which are presented in sequence:</span></span>  
  
1.  [<span data-ttu-id="e70ec-109">Impostazione di un account di accesso e di un utente per operazioni con priorità bassa</span><span class="sxs-lookup"><span data-stu-id="e70ec-109">Setting Up a Login and User for Low-Priority Operations</span></span>](#setup_login_and_user)  
  
2.  [<span data-ttu-id="e70ec-110">Configurazione di Resource Governor per limitare l'utilizzo di CPU</span><span class="sxs-lookup"><span data-stu-id="e70ec-110">Configuring Resource Governor to Limit CPU Usage</span></span>](#configure_RG)  
  
3.  [<span data-ttu-id="e70ec-111">Verifica della classificazione della sessione corrente (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e70ec-111">Verifying the Classification of the Current Session (Transact-SQL)</span></span>](#verifying)  
  
4.  [<span data-ttu-id="e70ec-112">Compressione di backup utilizzando una sessione con utilizzo della CPU limitato</span><span class="sxs-lookup"><span data-stu-id="e70ec-112">Compressing Backups Using a Session with Limited CPU</span></span>](#creating_compressed_backup)  
  
##  <a name="setting-up-a-login-and-user-for-low-priority-operations"></a><a name="setup_login_and_user"></a> <span data-ttu-id="e70ec-113">Impostazione di un account di accesso e di un utente per operazioni con priorità bassa</span><span class="sxs-lookup"><span data-stu-id="e70ec-113">Setting Up a Login and User for Low-Priority Operations</span></span>  
 <span data-ttu-id="e70ec-114">Per lo scenario presentato in questo argomento sono necessari un account di accesso e un utente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con priorità bassa.</span><span class="sxs-lookup"><span data-stu-id="e70ec-114">The scenario in this topic requires a low-priority [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and user.</span></span> <span data-ttu-id="e70ec-115">Il nome utente verrà utilizzato per classificare sessioni in esecuzione con l'account di accesso e per indirizzarle a un gruppo del carico di lavoro di Resource Governor che limita l'utilizzo della CPU.</span><span class="sxs-lookup"><span data-stu-id="e70ec-115">The user name will be used to classify sessions running in the login and route them to a Resource Governor workload group that limits CPU usage.</span></span>  
  
 <span data-ttu-id="e70ec-116">Nella procedura seguente vengono descritte le operazioni necessarie per impostare un account di accesso e un utente. Viene quindi illustrato l'esempio [!INCLUDE[tsql](../../includes/tsql-md.md)] "Esempio A: Impostazione di un account di accesso e di un utente (Transact-SQL)".</span><span class="sxs-lookup"><span data-stu-id="e70ec-116">The following procedure describes the steps for setting up a login and user for this purpose, followed by a [!INCLUDE[tsql](../../includes/tsql-md.md)] example, "Example A: Setting Up a Login and User (Transact-SQL)."</span></span>  
  
### <a name="to-set-up-a-login-and-database-user-for-classifying-sessions"></a><span data-ttu-id="e70ec-117">Per impostare un account di accesso e un utente del database per classificare sessioni</span><span class="sxs-lookup"><span data-stu-id="e70ec-117">To set up a login and database user for classifying sessions</span></span>  
  
1.  <span data-ttu-id="e70ec-118">Definire un account di accesso [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per la creazione di backup compressi con priorità bassa.</span><span class="sxs-lookup"><span data-stu-id="e70ec-118">Create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login for creating low-priority compressed backups.</span></span>  
  
     <span data-ttu-id="e70ec-119">**Per creare un account di accesso**</span><span class="sxs-lookup"><span data-stu-id="e70ec-119">**To create a login**</span></span>  
  
    -   [<span data-ttu-id="e70ec-120">Creare un account di accesso</span><span class="sxs-lookup"><span data-stu-id="e70ec-120">Create a Login</span></span>](../security/authentication-access/create-a-login.md)  
  
    -   [<span data-ttu-id="e70ec-121">CREATE LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e70ec-121">CREATE LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-login-transact-sql)  
  
2.  <span data-ttu-id="e70ec-122">Facoltativamente, concedere l'autorizzazione VIEW SERVER STATE a tale account di accesso.</span><span class="sxs-lookup"><span data-stu-id="e70ec-122">Optionally, grant VIEW SERVER STATE to this login.</span></span>  
  
    -   [<span data-ttu-id="e70ec-123">GRANT - autorizzazioni per oggetti di sistema &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e70ec-123">GRANT System Object Permissions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/grant-system-object-permissions-transact-sql)  
  
     <span data-ttu-id="e70ec-124">Per altre informazioni, vedere [GRANT - autorizzazioni per entità di database &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-principal-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e70ec-124">For more information, see [GRANT Database Principal Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-principal-permissions-transact-sql).</span></span>  
  
3.  <span data-ttu-id="e70ec-125">Creare un utente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per tale account di accesso.</span><span class="sxs-lookup"><span data-stu-id="e70ec-125">Create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user for this login.</span></span>  
  
     <span data-ttu-id="e70ec-126">**Per creare un utente**</span><span class="sxs-lookup"><span data-stu-id="e70ec-126">**To create a user**</span></span>  
  
    -   [<span data-ttu-id="e70ec-127">Creazione di un utente di database</span><span class="sxs-lookup"><span data-stu-id="e70ec-127">Create a Database User</span></span>](../security/authentication-access/create-a-database-user.md)  
  
    -   [<span data-ttu-id="e70ec-128">CREATE USER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e70ec-128">CREATE USER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-user-transact-sql)  
  
4.  <span data-ttu-id="e70ec-129">Per consentire alle sessioni relative agli account di accesso e all'utente creati di eseguire il backup di un database specifico, aggiungere l'utente al ruolo db_backupoperator del database.</span><span class="sxs-lookup"><span data-stu-id="e70ec-129">To enable sessions of this login and user to back up a given database, add the user to the db_backupoperator database role of that database.</span></span> <span data-ttu-id="e70ec-130">Effettuare questa operazione per ogni database di cui l'utente eseguirà il backup.</span><span class="sxs-lookup"><span data-stu-id="e70ec-130">Do this for each database that this user will back up.</span></span> <span data-ttu-id="e70ec-131">Facoltativamente, aggiungere l'utente agli altri ruoli predefiniti del database.</span><span class="sxs-lookup"><span data-stu-id="e70ec-131">Optionally, add the user to other fixed database roles.</span></span>  
  
     <span data-ttu-id="e70ec-132">**Per aggiungere un utente a un ruolo predefinito del database**</span><span class="sxs-lookup"><span data-stu-id="e70ec-132">**To add a user to a fixed database role**</span></span>  
  
    -   [<span data-ttu-id="e70ec-133">sp_addrolemember &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e70ec-133">sp_addrolemember &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql)  
  
     <span data-ttu-id="e70ec-134">Per altre informazioni, vedere [GRANT - autorizzazioni per entità di database &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-principal-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e70ec-134">For more information, see [GRANT Database Principal Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-principal-permissions-transact-sql).</span></span>  
  
### <a name="example-a-setting-up-a-login-and-user-transact-sql"></a><span data-ttu-id="e70ec-135">Esempio A: Impostazione di un account di accesso e di un utente (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e70ec-135">Example A: Setting Up a Login and User (Transact-SQL)</span></span>  
 <span data-ttu-id="e70ec-136">L'esempio seguente è rilevante solo se si sceglie di creare un nuovo account di accesso e un nuovo utente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per eseguire backup con priorità bassa.</span><span class="sxs-lookup"><span data-stu-id="e70ec-136">The following example is relevant only if you choose to create a new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and user for low-priority backups.</span></span> <span data-ttu-id="e70ec-137">In alternativa, è possibile utilizzare un account di accesso e un utente esistenti, se appropriati.</span><span class="sxs-lookup"><span data-stu-id="e70ec-137">Alternatively, you can use an existing login and user, if an appropriate one exists.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e70ec-138">L'esempio seguente usa un accesso e un nome utente di esempio, *domain_name*`\MAX_CPU`.</span><span class="sxs-lookup"><span data-stu-id="e70ec-138">The following example uses a sample login and user name, *domain_name*`\MAX_CPU`.</span></span> <span data-ttu-id="e70ec-139">Sostituire questi nomi con quelli dell'account di accesso e dell'utente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che si intende utilizzare nella creazione dei backup compressi con priorità bassa.</span><span class="sxs-lookup"><span data-stu-id="e70ec-139">Replace these with the names of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and user that you plan to use when creating your low-priority compressed backups.</span></span>  
  
 <span data-ttu-id="e70ec-140">Questo esempio crea un accesso per l'account di Windows *domain_name*`\MAX_CPU` e concede l'autorizzazione VIEW SERVER STATE all'accesso.</span><span class="sxs-lookup"><span data-stu-id="e70ec-140">This example creates a login for the *domain_name*`\MAX_CPU` Windows account and then grants VIEW SERVER STATE permission to the login.</span></span> <span data-ttu-id="e70ec-141">che consente di verificare la classificazione di Resource Governor delle sessioni dell'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="e70ec-141">This permission enables you to verify the Resource Governor classification of sessions of the login.</span></span> <span data-ttu-id="e70ec-142">L'esempio crea quindi un utente per *domain_name*`\MAX_CPU` e lo aggiunge al ruolo predefinito del database db_backupoperator per il database di esempio [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e70ec-142">The example then creates a user for *domain_name*`\MAX_CPU` and adds it to the db_backupoperator fixed database role for the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="e70ec-143">Tale nome utente verrà utilizzato dalla funzione di classificazione di Resource Governor.</span><span class="sxs-lookup"><span data-stu-id="e70ec-143">This user name will be used by the Resource Governor classifier function.</span></span>  
  
```sql  
-- Create a SQL Server login for low-priority operations  
USE master;  
CREATE LOGIN [domain_name\MAX_CPU] FROM WINDOWS;  
GRANT VIEW SERVER STATE TO [domain_name\MAX_CPU];  
GO  
-- Create a SQL Server user in AdventureWorks2012 for this login  
USE AdventureWorks2012;  
CREATE USER [domain_name\MAX_CPU] FOR LOGIN [domain_name\MAX_CPU];  
EXEC sp_addrolemember 'db_backupoperator', 'domain_name\MAX_CPU';  
GO  
  
```  
  
 [<span data-ttu-id="e70ec-144">&#91;Torna all'inizio&#93;</span><span class="sxs-lookup"><span data-stu-id="e70ec-144">&#91;Top&#93;</span></span>](#Top)  
  
##  <a name="configuring-resource-governor-to-limit-cpu-usage"></a><a name="configure_RG"></a> <span data-ttu-id="e70ec-145">Configurazione di Resource Governor per limitare l'utilizzo di CPU</span><span class="sxs-lookup"><span data-stu-id="e70ec-145">Configuring Resource Governor to Limit CPU Usage</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e70ec-146">Verificare che Resource Governor sia abilitato.</span><span class="sxs-lookup"><span data-stu-id="e70ec-146">Ensure that Resource Governor is enabled.</span></span> <span data-ttu-id="e70ec-147">Per altre informazioni, vedere [Abilitare Resource Governor](../resource-governor/enable-resource-governor.md).</span><span class="sxs-lookup"><span data-stu-id="e70ec-147">For more information, see [Enable Resource Governor](../resource-governor/enable-resource-governor.md).</span></span>  
  
 <span data-ttu-id="e70ec-148">In questo scenario di Resource Governor la configurazione include i passaggi di base seguenti:</span><span class="sxs-lookup"><span data-stu-id="e70ec-148">In this Resource Governor scenario, configuration comprises the following basic steps:</span></span>  
  
1.  <span data-ttu-id="e70ec-149">Creazione e configurazione di un pool di risorse di Resource Governor che limita il valore massimo della larghezza di banda media della CPU assegnata alle richieste nel pool di risorse quando si verifica una contesa di CPU.</span><span class="sxs-lookup"><span data-stu-id="e70ec-149">Create and configure a Resource Governor resource pool that limits the maximum average CPU bandwidth that will be given to requests in the resource pool when CPU contention occurs.</span></span>  
  
2.  <span data-ttu-id="e70ec-150">Creazione e configurazione di un gruppo del carico di lavoro di Resource Governor che utilizza tale pool.</span><span class="sxs-lookup"><span data-stu-id="e70ec-150">Create and configure a Resource Governor workload group that uses this pool.</span></span>  
  
3.  <span data-ttu-id="e70ec-151">Creazione di una *funzione di classificazione*, ovvero di una funzione definita dall'utente i cui valori restituiti vengono usati da Resource Governor per classificare le sessioni in modo da indirizzarle al gruppo di carico di lavoro appropriato.</span><span class="sxs-lookup"><span data-stu-id="e70ec-151">Create a *classifier function*, which is a user-defined function (UDF) whose return values are used by Resource Governor for classifying sessions so that they are routed to the appropriate workload group.</span></span>  
  
4.  <span data-ttu-id="e70ec-152">Registrazione della funzione di classificazione con Resource Governor.</span><span class="sxs-lookup"><span data-stu-id="e70ec-152">Register the classifier function with Resource Governor.</span></span>  
  
5.  <span data-ttu-id="e70ec-153">Applicazione delle modifiche alla configurazione in memoria di Resource Governor.</span><span class="sxs-lookup"><span data-stu-id="e70ec-153">Apply the changes to the Resource Governor in-memory configuration.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e70ec-154">Per informazioni sui pool di risorse, i gruppi di carico di lavoro e la classificazione di Resource Governor, vedere [Resource Governor](../resource-governor/resource-governor.md).</span><span class="sxs-lookup"><span data-stu-id="e70ec-154">For information about Resource Governor resource pools, workload groups, and classification, see [Resource Governor](../resource-governor/resource-governor.md).</span></span>  
  
 <span data-ttu-id="e70ec-155">Le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] per questi passaggi vengono descritte nella procedura "Per configurare Resource Governor per limitare l'utilizzo della CPU", al termine della quale viene illustrato un esempio [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e70ec-155">The [!INCLUDE[tsql](../../includes/tsql-md.md)] statements for these steps are described in the procedure, "To configure Resource Governor for limiting CPU usage," which is followed by a [!INCLUDE[tsql](../../includes/tsql-md.md)] example of the procedure.</span></span>  
  
 <span data-ttu-id="e70ec-156">**Per configurare Resource Governor (SQL Server Management Studio)**</span><span class="sxs-lookup"><span data-stu-id="e70ec-156">**To configure Resource Governor (SQL Server Management Studio)**</span></span>  
  
-   [<span data-ttu-id="e70ec-157">Configurare Resource Governor usando un modello</span><span class="sxs-lookup"><span data-stu-id="e70ec-157">Configure Resource Governor Using a Template</span></span>](../resource-governor/configure-resource-governor-using-a-template.md)  
  
-   [<span data-ttu-id="e70ec-158">Creare un pool di risorse</span><span class="sxs-lookup"><span data-stu-id="e70ec-158">Create a Resource Pool</span></span>](../resource-governor/create-a-resource-pool.md)  
  
-   [<span data-ttu-id="e70ec-159">Creare un gruppo di carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="e70ec-159">Create a Workload Group</span></span>](../resource-governor/create-a-workload-group.md)  
  
### <a name="to-configure-resource-governor-for-limiting-cpu-usage-transact-sql"></a><span data-ttu-id="e70ec-160">Per configurare Resource Governor per limitare l'utilizzo della CPU (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e70ec-160">To configure Resource Governor for limiting CPU usage (Transact-SQL)</span></span>  
  
1.  <span data-ttu-id="e70ec-161">Eseguire un'istruzione [CREATE RESOURCE POOL](/sql/t-sql/statements/create-resource-pool-transact-sql) per creare un pool di risorse.</span><span class="sxs-lookup"><span data-stu-id="e70ec-161">Issue a [CREATE RESOURCE POOL](/sql/t-sql/statements/create-resource-pool-transact-sql) statement to create a resource pool.</span></span> <span data-ttu-id="e70ec-162">Nell'esempio relativo a questa procedura viene utilizzata la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="e70ec-162">The example for this procedure uses the following syntax:</span></span>  
  
     <span data-ttu-id="e70ec-163">*CREATE RESOURCE POOL nome_pool* WITH ( MAX_CPU_PERCENT = *valore* );</span><span class="sxs-lookup"><span data-stu-id="e70ec-163">*CREATE RESOURCE POOL pool_name* WITH ( MAX_CPU_PERCENT = *value* );</span></span>  
  
     <span data-ttu-id="e70ec-164">*Value* è un integer compreso tra 1 e 100 che indica la percentuale del valore massimo della larghezza di banda media della CPU.</span><span class="sxs-lookup"><span data-stu-id="e70ec-164">*Value* is an integer from 1 to 100 that indicates the percentage of maximum average CPU bandwidth.</span></span> <span data-ttu-id="e70ec-165">Il valore appropriato dipende dall'ambiente.</span><span class="sxs-lookup"><span data-stu-id="e70ec-165">The appropriate value depends on your environment.</span></span> <span data-ttu-id="e70ec-166">A scopo illustrativo, nell'esempio in questo argomento viene utilizzato il valore 20% (MAX_CPU_PERCENT = 20).</span><span class="sxs-lookup"><span data-stu-id="e70ec-166">For the purpose of illustration, the example in this topic uses 20%  percent (MAX_CPU_PERCENT = 20.)</span></span>  
  
2.  <span data-ttu-id="e70ec-167">Eseguire un'istruzione [CREATE WORKLOAD GROUP](/sql/t-sql/statements/create-workload-group-transact-sql) per creare un gruppo di carico di lavoro per le operazioni con priorità bassa per cui si vuole controllare l'utilizzo della CPU.</span><span class="sxs-lookup"><span data-stu-id="e70ec-167">Issue a [CREATE WORKLOAD GROUP](/sql/t-sql/statements/create-workload-group-transact-sql) statement to create a workload group for low-priority operations whose CPU usage you want to govern.</span></span> <span data-ttu-id="e70ec-168">Nell'esempio relativo a questa procedura viene utilizzata la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="e70ec-168">The example for this procedure uses the following syntax:</span></span>  
  
     <span data-ttu-id="e70ec-169">CREATE WORKLOAD GROUP *nome_gruppo* USING *nome_pool*;</span><span class="sxs-lookup"><span data-stu-id="e70ec-169">CREATE WORKLOAD GROUP *group_name* USING *pool_name*;</span></span>  
  
3.  <span data-ttu-id="e70ec-170">Eseguire un'istruzione [CREATE FUNCTION](/sql/t-sql/statements/create-function-transact-sql) per creare una funzione di classificazione che esegue il mapping del gruppo di carico di lavoro creato nel passaggio precedente all'utente relativo all'account di accesso con priorità bassa.</span><span class="sxs-lookup"><span data-stu-id="e70ec-170">Issue a [CREATE FUNCTION](/sql/t-sql/statements/create-function-transact-sql) statement to create a classifier function that maps the workload group created in the preceding step to the user of the low-priority login.</span></span> <span data-ttu-id="e70ec-171">Nell'esempio relativo a questa procedura viene utilizzata la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="e70ec-171">The example for this procedure uses the following syntax:</span></span>  
  
     <span data-ttu-id="e70ec-172">CREATE FUNCTION [*nome_schema*.]*nome_funzione*() RETURNS sysname</span><span class="sxs-lookup"><span data-stu-id="e70ec-172">CREATE FUNCTION [*schema_name*.]*function_name*() RETURNS sysname</span></span>  
  
     <span data-ttu-id="e70ec-173">WITH SCHEMABINDING</span><span class="sxs-lookup"><span data-stu-id="e70ec-173">WITH SCHEMABINDING</span></span>  
  
     <span data-ttu-id="e70ec-174">AS</span><span class="sxs-lookup"><span data-stu-id="e70ec-174">AS</span></span>  
  
     <span data-ttu-id="e70ec-175">BEGIN</span><span class="sxs-lookup"><span data-stu-id="e70ec-175">BEGIN</span></span>  
  
     <span data-ttu-id="e70ec-176">DECLARE @workload_group_name AS *sysname*</span><span class="sxs-lookup"><span data-stu-id="e70ec-176">DECLARE @workload_group_name AS *sysname*</span></span>  
  
     <span data-ttu-id="e70ec-177">IF (SUSER_NAME() = '*utente_accesso_bassa_priorità*')</span><span class="sxs-lookup"><span data-stu-id="e70ec-177">IF (SUSER_NAME() = '*user_of_low_priority_login*')</span></span>  
  
     <span data-ttu-id="e70ec-178">SET @workload_group_name = '*nome_gruppo_carico_di_lavoro*'</span><span class="sxs-lookup"><span data-stu-id="e70ec-178">SET @workload_group_name = '*workload_group_name*'</span></span>  
  
     <span data-ttu-id="e70ec-179">RETURN @workload_group_name</span><span class="sxs-lookup"><span data-stu-id="e70ec-179">RETURN @workload_group_name</span></span>  
  
     <span data-ttu-id="e70ec-180">FINE</span><span class="sxs-lookup"><span data-stu-id="e70ec-180">END</span></span>  
  
     <span data-ttu-id="e70ec-181">Per informazioni sui componenti di questa istruzione CREATE FUNCTION, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="e70ec-181">For information about the components of this CREATE FUNCTION statement, see:</span></span>  
  
    -   [<span data-ttu-id="e70ec-182">DECLARE @local_variable &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e70ec-182">DECLARE @local_variable &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/declare-local-variable-transact-sql)  
  
    -   [<span data-ttu-id="e70ec-183">SUSER_SNAME &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e70ec-183">SUSER_SNAME &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/suser-sname-transact-sql)  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="e70ec-184">SUSER_NAME è solo una delle numerose funzioni di sistema che possono essere utilizzate in una funzione di classificazione.</span><span class="sxs-lookup"><span data-stu-id="e70ec-184">SUSER_NAME is just one of several system functions that can be used in a classifier function.</span></span> <span data-ttu-id="e70ec-185">Per altre informazioni, vedere [Creare e testare una funzione di classificazione definita dall'utente](../resource-governor/create-and-test-a-classifier-user-defined-function.md).</span><span class="sxs-lookup"><span data-stu-id="e70ec-185">For more information, see [Create and Test a Classifier User-Defined Function](../resource-governor/create-and-test-a-classifier-user-defined-function.md).</span></span>  
  
    -   <span data-ttu-id="e70ec-186">[SET @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/set-local-variable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e70ec-186">[SET @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/set-local-variable-transact-sql).</span></span>  
  
4.  <span data-ttu-id="e70ec-187">Eseguire un'istruzione [ALTER RESOURCE GOVERNOR](/sql/t-sql/statements/alter-resource-governor-transact-sql) per registrare la funzione di classificazione con Resource Governor.</span><span class="sxs-lookup"><span data-stu-id="e70ec-187">Issue an [ALTER RESOURCE GOVERNOR](/sql/t-sql/statements/alter-resource-governor-transact-sql) statement to register the classifier function with Resource Governor.</span></span> <span data-ttu-id="e70ec-188">Nell'esempio relativo a questa procedura viene utilizzata la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="e70ec-188">The example for this procedure uses the following syntax:</span></span>  
  
     <span data-ttu-id="e70ec-189">ALTER RESOURCE GOVERNOR WITH (CLASSIFIER_FUNCTION = *nome_schema*.*nome_funzione*);</span><span class="sxs-lookup"><span data-stu-id="e70ec-189">ALTER RESOURCE GOVERNOR WITH (CLASSIFIER_FUNCTION = *schema_name*.*function_name*);</span></span>  
  
5.  <span data-ttu-id="e70ec-190">Eseguire una seconda istruzione ALTER RESOURCE GOVERNOR per applicare le modifiche alla configurazione in memoria di Resource Governor, come descritto di seguito:</span><span class="sxs-lookup"><span data-stu-id="e70ec-190">Issue a second ALTER RESOURCE GOVERNOR statement to apply the changes to the Resource Governor in-memory configuration, as follows:</span></span>  
  
    ```  
    ALTER RESOURCE GOVERNOR RECONFIGURE;  
    ```  
  
### <a name="example-b-configuring-resource-governor-transact-sql"></a><span data-ttu-id="e70ec-191">Esempio B: Configurazione di Resource Governor (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e70ec-191">Example B: Configuring Resource Governor (Transact-SQL)</span></span>  
 <span data-ttu-id="e70ec-192">Nell'esempio seguente vengono effettuati i passaggi seguenti all'interno di un'unica transazione:</span><span class="sxs-lookup"><span data-stu-id="e70ec-192">The following example performs the following steps within a single transaction:</span></span>  
  
1.  <span data-ttu-id="e70ec-193">Creazione del pool di risorse `pMAX_CPU_PERCENT_20` .</span><span class="sxs-lookup"><span data-stu-id="e70ec-193">Creates the `pMAX_CPU_PERCENT_20` resource pool.</span></span>  
  
2.  <span data-ttu-id="e70ec-194">Creazione del gruppo del carico di lavoro `gMAX_CPU_PERCENT_20` .</span><span class="sxs-lookup"><span data-stu-id="e70ec-194">Creates the `gMAX_CPU_PERCENT_20` workload group.</span></span>  
  
3.  <span data-ttu-id="e70ec-195">Creazione della funzione di classificazione `rgclassifier_MAX_CPU()` che utilizza il nome utente creato nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="e70ec-195">Creates the `rgclassifier_MAX_CPU()` classifier function, which uses the user name created in the preceding example.</span></span>  
  
4.  <span data-ttu-id="e70ec-196">Registrazione della funzione di classificazione con Resource Governor.</span><span class="sxs-lookup"><span data-stu-id="e70ec-196">Registers the classifier function with Resource Governor.</span></span>  
  
 <span data-ttu-id="e70ec-197">Dopo l'esecuzione del commit della transazione, nell'esempio vengono applicate le modifiche di configurazione richieste nell'istruzione ALTER WORKLOAD GROUP o ALTER RESOURCE POOL.</span><span class="sxs-lookup"><span data-stu-id="e70ec-197">After committing the transaction, the example applies the configuration changes requested in the ALTER WORKLOAD GROUP or ALTER RESOURCE POOL statements.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e70ec-198">Nell'esempio seguente viene usato il nome dell'utente di esempio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creato in "Esempio A: Impostazione di un accesso e di un utente (Transact-SQL)", *nome_dominio*`\MAX_CPU`.</span><span class="sxs-lookup"><span data-stu-id="e70ec-198">The following example uses the user name of the sample [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user created in "Example A: Setting Up a Login and User (Transact-SQL)," *domain_name*`\MAX_CPU`.</span></span> <span data-ttu-id="e70ec-199">Sostituire questo nome con quello dell'utente relativo all'account di accesso che si intende utilizzare per la creazione di backup compressi con priorità bassa.</span><span class="sxs-lookup"><span data-stu-id="e70ec-199">Replace this with the name of the user of the login that you plan to use for creating low-priority compressed backups.</span></span>  
  
```sql  
-- Configure Resource Governor.  
BEGIN TRAN  
USE master;  
-- Create a resource pool that sets the MAX_CPU_PERCENT to 20%.   
CREATE RESOURCE POOL pMAX_CPU_PERCENT_20  
   WITH  
      (MAX_CPU_PERCENT = 20);  
GO  
-- Create a workload group to use this pool.   
CREATE WORKLOAD GROUP gMAX_CPU_PERCENT_20  
USING pMAX_CPU_PERCENT_20;  
GO  
-- Create a classification function.  
-- Note that any request that does not get classified goes into   
-- the 'Default' group.  
CREATE FUNCTION dbo.rgclassifier_MAX_CPU() RETURNS sysname   
WITH SCHEMABINDING  
AS  
BEGIN  
    DECLARE @workload_group_name AS sysname  
      IF (SUSER_NAME() = 'domain_name\MAX_CPU')  
          SET @workload_group_name = 'gMAX_CPU_PERCENT_20'  
    RETURN @workload_group_name  
END;  
GO  
  
-- Register the classifier function with Resource Governor.  
ALTER RESOURCE GOVERNOR WITH (CLASSIFIER_FUNCTION= dbo.rgclassifier_MAX_CPU);  
COMMIT TRAN;  
GO  
-- Start Resource Governor  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
  
```  
  
 [<span data-ttu-id="e70ec-200">&#91;Torna all'inizio&#93;</span><span class="sxs-lookup"><span data-stu-id="e70ec-200">&#91;Top&#93;</span></span>](#Top)  
  
##  <a name="verifying-the-classification-of-the-current-session-transact-sql"></a><a name="verifying"></a> <span data-ttu-id="e70ec-201">Verifica della classificazione della sessione corrente (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e70ec-201">Verifying the Classification of the Current Session (Transact-SQL)</span></span>  
 <span data-ttu-id="e70ec-202">Facoltativamente, accedere come l'utente specificato nella funzione di classificazione e verificare la classificazione della sessione eseguendo l'istruzione [SELECT](/sql/t-sql/queries/select-transact-sql) seguente in Esplora oggetti:</span><span class="sxs-lookup"><span data-stu-id="e70ec-202">Optionally, log in as the user that you specified in your classifier function, and verify the session classification by issuing the following [SELECT](/sql/t-sql/queries/select-transact-sql) statement in Object Explorer:</span></span>  
  
```sql  
USE master;  
SELECT sess.session_id, sess.login_name, sess.group_id, grps.name   
FROM sys.dm_exec_sessions AS sess   
JOIN sys.dm_resource_governor_workload_groups AS grps   
    ON sess.group_id = grps.group_id  
WHERE session_id > 50;  
GO  
```  
  
 <span data-ttu-id="e70ec-203">Nella colonna **name** del riquadro dei risultati dovrebbero essere elencate una o più sessioni per il nome del gruppo di carico di lavoro specificato nella funzione di classificazione.</span><span class="sxs-lookup"><span data-stu-id="e70ec-203">In the results pane, the **name** column should list one or more sessions for the workload-group name that you specified in your classifier function.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e70ec-204">Per informazioni sulle viste a gestione dinamica chiamate da questa istruzione SELECT, vedere [sys.dm_exec_sessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) e [sys.dm_resource_governor_workload_groups &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-workload-groups-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e70ec-204">For information about the dynamic management views called by this SELECT statement, see [sys.dm_exec_sessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) and [sys.dm_resource_governor_workload_groups &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-workload-groups-transact-sql).</span></span>  
  
 [<span data-ttu-id="e70ec-205">&#91;Torna all'inizio&#93;</span><span class="sxs-lookup"><span data-stu-id="e70ec-205">&#91;Top&#93;</span></span>](#Top)  
  
##  <a name="compressing-backups-using-a-session-with-limited-cpu"></a><a name="creating_compressed_backup"></a> <span data-ttu-id="e70ec-206">Compressione di backup utilizzando una sessione con utilizzo della CPU limitato</span><span class="sxs-lookup"><span data-stu-id="e70ec-206">Compressing Backups Using a Session with Limited CPU</span></span>  
 <span data-ttu-id="e70ec-207">Per creare un backup compresso in una sessione con un utilizzo massimo della CPU limitato, accedere come l'utente specificato nella funzione di classificazione.</span><span class="sxs-lookup"><span data-stu-id="e70ec-207">To create a compressed backup in a session with a limited maximum CPU, log in as the user specified in your classifier function.</span></span> <span data-ttu-id="e70ec-208">Nel comando di backup specificare WITH COMPRESSION ( [!INCLUDE[tsql](../../includes/tsql-md.md)] ) o selezionare **Comprimi backup** ( [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="e70ec-208">In your backup command, either specify WITH COMPRESSION ([!INCLUDE[tsql](../../includes/tsql-md.md)]) or select **Compress backup** ([!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]).</span></span> <span data-ttu-id="e70ec-209">Per creare un backup compresso del database, vedere [Creazione di un backup completo del database &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e70ec-209">To create a compressed database backup, see [Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span></span>  
  
### <a name="example-c-creating-a-compressed-backup-transact-sql"></a><span data-ttu-id="e70ec-210">Esempio C: Creazione di un backup compresso (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e70ec-210">Example C: Creating a Compressed Backup (Transact-SQL)</span></span>  
 <span data-ttu-id="e70ec-211">Nell'esempio seguente [BACKUP](/sql/t-sql/statements/backup-transact-sql) viene creato un backup compresso completo del database [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] nel nuovo file di backup formattato `Z:\SQLServerBackups\AdvWorksData.bak`.</span><span class="sxs-lookup"><span data-stu-id="e70ec-211">The following [BACKUP](/sql/t-sql/statements/backup-transact-sql) example creates a compressed full backup of the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database in a newly formatted backup file, `Z:\SQLServerBackups\AdvWorksData.bak`.</span></span>  
  
```sql  
--Run backup statement in the gBackup session.  
BACKUP DATABASE AdventureWorks2012 TO DISK='Z:\SQLServerBackups\AdvWorksData.bak'   
WITH   
   FORMAT,   
   MEDIADESCRIPTION='AdventureWorks2012 Compressed Data Backups'  
   DESCRIPTION='First database backup on AdventureWorks2012 Compressed Data Backups media set'  
   COMPRESSION;  
GO  
```  
  
 [<span data-ttu-id="e70ec-212">&#91;Torna all'inizio&#93;</span><span class="sxs-lookup"><span data-stu-id="e70ec-212">&#91;Top&#93;</span></span>](#Top)  
  
## <a name="see-also"></a><span data-ttu-id="e70ec-213">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e70ec-213">See Also</span></span>  
 <span data-ttu-id="e70ec-214">[Creare e testare una funzione di classificazione definita dall'utente](../resource-governor/create-and-test-a-classifier-user-defined-function.md) </span><span class="sxs-lookup"><span data-stu-id="e70ec-214">[Create and Test a Classifier User-Defined Function](../resource-governor/create-and-test-a-classifier-user-defined-function.md) </span></span>  
 [<span data-ttu-id="e70ec-215">Resource Governor</span><span class="sxs-lookup"><span data-stu-id="e70ec-215">Resource Governor</span></span>](../resource-governor/resource-governor.md)  
  
  
