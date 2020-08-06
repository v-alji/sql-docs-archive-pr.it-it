---
title: Sicurezza dell'agente di raccolta dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- data collection [SQL Server]
- security [data collector]
- data collector [SQL Server], security
ms.assetid: e75d6975-641e-440a-a642-cb39a583359a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c89f1658f6ae1b5bd79de96f20222b0b19529df2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625414"
---
# <a name="data-collector-security"></a><span data-ttu-id="bd336-102">Sicurezza agente di raccolta dati</span><span class="sxs-lookup"><span data-stu-id="bd336-102">Data Collector Security</span></span>
  <span data-ttu-id="bd336-103">L'agente di raccolta dati usano il modello di sicurezza basato sui ruoli implementato da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="bd336-103">The data collector uses the role-based security model implemented by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="bd336-104">Questo modello consente all'amministratore del database di eseguire le varie attività dell'agente di raccolta dati in un contesto di sicurezza che ha solo le autorizzazioni necessarie per eseguire quell'attività.</span><span class="sxs-lookup"><span data-stu-id="bd336-104">This model lets the database administrator run the various data collector tasks in a security context that has only the permissions required to perform that task.</span></span> <span data-ttu-id="bd336-105">Questo approccio è usato anche per operazioni con tabelle interne, a cui è possibile accedere solo mediante una stored procedure o una vista.</span><span class="sxs-lookup"><span data-stu-id="bd336-105">This approach is also used for operations involving internal tables, which can only be accessed by using a stored procedure or view.</span></span> <span data-ttu-id="bd336-106">Per le tabelle interne non vengono concesse autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="bd336-106">No permissions are granted to internal tables.</span></span> <span data-ttu-id="bd336-107">Le autorizzazioni vengono invece controllate sull'utente della stored procedure o della vista usata per accedere a una tabella.</span><span class="sxs-lookup"><span data-stu-id="bd336-107">Instead, permissions are checked on the user of the stored procedure or view that is used to access a table.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bd336-108">Un altro aspetto chiave di questo modello di sicurezza è costituito dalle autorizzazioni concentriche.</span><span class="sxs-lookup"><span data-stu-id="bd336-108">Another key aspect of this security model is concentric permissions.</span></span> <span data-ttu-id="bd336-109">Nelle autorizzazioni concentriche i ruoli con privilegi di livello più alto ereditano le autorizzazioni dei ruoli con privilegi di livello più basso su oggetti (compresi avvisi, operatori, processi, pianificazioni e proxy).</span><span class="sxs-lookup"><span data-stu-id="bd336-109">Under concentric permissions, more privileged roles inherit the permissions of less privileged roles on objects (including alerts, operators, jobs, schedules, and proxies).</span></span> <span data-ttu-id="bd336-110">Per altre informazioni, vedere [SQL Server Agent Fixed Database Roles](../../ssms/agent/sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="bd336-110">For more information, see [SQL Server Agent Fixed Database Roles](../../ssms/agent/sql-server-agent-fixed-database-roles.md).</span></span>  
  
 <span data-ttu-id="bd336-111">Nelle sezioni seguenti vengono descritte la sicurezza della raccolta di dati in generale, nonché i ruoli che è necessario concedere agli utenti affinché possano configurare e usare l'agente di raccolta dati ed eseguire attività associate al data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="bd336-111">The following sections describe data collection security in general, as well as the roles you must grant to users so they can configure and use the data collector, and carry out tasks associated with the management data warehouse.</span></span>  
  
## <a name="general-security"></a><span data-ttu-id="bd336-112">Sicurezza generale</span><span class="sxs-lookup"><span data-stu-id="bd336-112">General Security</span></span>  
 <span data-ttu-id="bd336-113">L'agente di raccolta dati viene installato secondo gli standard documentati specificati per [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd336-113">The data collector is installed according to the documented standards specified for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
### <a name="network-security"></a><span data-ttu-id="bd336-114">Sicurezza di rete</span><span class="sxs-lookup"><span data-stu-id="bd336-114">Network Security</span></span>  
 <span data-ttu-id="bd336-115">Le informazioni riservate possono essere passate tra le istanze di destinazione, l'istanza relazionale associata al server di configurazione, i set di raccolta in esecuzione ed il server che ospita il data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="bd336-115">Sensitive information can be passed between target instances, the relational instance associated with the configuration server, the collection sets that are running, and the server that hosts the management data warehouse.</span></span>  
  
 <span data-ttu-id="bd336-116">Per proteggere i dati trasferiti su una rete vengono implementati i meccanismi di sicurezza standard, ad esempio la crittografia del protocollo per [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd336-116">To protect any data that is transferred over a network, the standard security mechanisms are implemented, such as protocol encryption for [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
## <a name="permissions-for-configuring-and-using-the-data-collector"></a><span data-ttu-id="bd336-117">Autorizzazioni per la configurazione e l'utilizzo dell'agente di raccolta dati</span><span class="sxs-lookup"><span data-stu-id="bd336-117">Permissions for Configuring and Using the Data Collector</span></span>  
 <span data-ttu-id="bd336-118">A seconda dell'attività, gli utenti devono essere membri di uno o più ruoli predefiniti del database forniti per l'agente di raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="bd336-118">Depending on the task, users must be members of one or more of the fixed database roles provided for the data collector.</span></span> <span data-ttu-id="bd336-119">I ruoli sono i seguenti, elencati a partire dall'accesso con privilegi di livello più alto fino a quello con privilegi minimi:</span><span class="sxs-lookup"><span data-stu-id="bd336-119">In order of most-privileged to least-privileged access, the roles are as follows:</span></span>  
  
-   `dc_admin`  
  
-   <span data-ttu-id="bd336-120">**dc_operator**</span><span class="sxs-lookup"><span data-stu-id="bd336-120">**dc_operator**</span></span>  
  
-   <span data-ttu-id="bd336-121">**dc_proxy**</span><span class="sxs-lookup"><span data-stu-id="bd336-121">**dc_proxy**</span></span>  
  
 <span data-ttu-id="bd336-122">Questi ruoli sono archiviati nel database msdb.</span><span class="sxs-lookup"><span data-stu-id="bd336-122">These roles are stored in the msdb database.</span></span> <span data-ttu-id="bd336-123">Per impostazione predefinita, nessun utente è membro di questi ruoli di database.</span><span class="sxs-lookup"><span data-stu-id="bd336-123">By default, no user is a member of these database roles.</span></span> <span data-ttu-id="bd336-124">L'appartenenza dell'utente a questi ruoli deve essere concessa esplicitamente.</span><span class="sxs-lookup"><span data-stu-id="bd336-124">User membership in these roles must be granted explicitly.</span></span>  
  
 <span data-ttu-id="bd336-125">Gli utenti membri del `sysadmin` ruolo predefinito del server hanno accesso completo agli [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oggetti e alle viste dell'agente di raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="bd336-125">Users who are members of the `sysadmin` fixed server role have full access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent objects and data collector views.</span></span> <span data-ttu-id="bd336-126">Tuttavia è necessario che vengano aggiunti esplicitamente ai ruoli dell'agente di raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="bd336-126">However, they need to be explicitly added to data collector roles.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bd336-127">I membri dei ruoli db_ssisadmin e dc_admin potrebbero essere in grado di elevare i loro privilegi a sysadmin.</span><span class="sxs-lookup"><span data-stu-id="bd336-127">Members of the db_ssisadmin role and the dc_admin role may be able to elevate their privileges to sysadmin.</span></span> <span data-ttu-id="bd336-128">Questa elevazione dei privilegi può verificarsi perché tali ruoli possono modificare i pacchetti [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] e i pacchetti [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] possono essere eseguiti da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzando il contesto di sicurezza sysadmin di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="bd336-128">This elevation of privilege can occur because these roles can modify [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages can be executed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the sysadmin security context of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="bd336-129">Per impedire questa elevazione dei privilegi durante l'esecuzione dei piani di manutenzione, set di raccolta dati e altri pacchetti [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , configurare i processi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent che eseguono pacchetti in modo da utilizzare un account proxy con privilegi limitati o aggiungere solo i membri sysadmin ai ruoli db_ssisadmin e dc_admin.</span><span class="sxs-lookup"><span data-stu-id="bd336-129">To guard against this elevation of privilege when running maintenance plans, data collection sets, and other [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs that run packages to use a proxy account with limited privileges or only add sysadmin members to the db_ssisadmin and dc_admin roles.</span></span>  
  
### <a name="dc_admin-role"></a><span data-ttu-id="bd336-130">Ruolo dc_admin</span><span class="sxs-lookup"><span data-stu-id="bd336-130">dc_admin Role</span></span>  
 <span data-ttu-id="bd336-131">Gli utenti assegnati al `dc_admin` ruolo hanno accesso amministratore completo (creazione, lettura, aggiornamento ed eliminazione) alla configurazione dell'agente di raccolta dati in un'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="bd336-131">Users assigned to the `dc_admin` role have full administrator access (Create, Read, Update, and Delete) to the data collector configuration on a server instance.</span></span> <span data-ttu-id="bd336-132">I membri di questo ruolo possono eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="bd336-132">Members of this role can perform the following operations:</span></span>  
  
-   <span data-ttu-id="bd336-133">Impostare proprietà a livello di agente di raccolta</span><span class="sxs-lookup"><span data-stu-id="bd336-133">Set collector-level properties.</span></span>  
  
-   <span data-ttu-id="bd336-134">Aggiungere nuovi set di raccolta</span><span class="sxs-lookup"><span data-stu-id="bd336-134">Add new collection sets.</span></span>  
  
-   <span data-ttu-id="bd336-135">Installare nuovi tipi di raccolta</span><span class="sxs-lookup"><span data-stu-id="bd336-135">Install new collection types.</span></span>  
  
-   <span data-ttu-id="bd336-136">Eseguire tutte le operazioni consentite al ruolo **dc_operator** .</span><span class="sxs-lookup"><span data-stu-id="bd336-136">Perform all the operations permitted to the **dc_operator** role.</span></span>  
  
 <span data-ttu-id="bd336-137">Il `dc_admin` ruolo è membro dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd336-137">The `dc_admin` role is a member of the following roles:</span></span>  
  
-   <span data-ttu-id="bd336-138">**SQLAgentUserRole**.</span><span class="sxs-lookup"><span data-stu-id="bd336-138">**SQLAgentUserRole**.</span></span> <span data-ttu-id="bd336-139">Questo ruolo è necessario per creare pianificazioni ed eseguire processi.</span><span class="sxs-lookup"><span data-stu-id="bd336-139">This role is required to create schedules and run jobs.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bd336-140">I proxy creati per l'agente di raccolta dati devono concedere l'accesso a `dc_admin` per crearli e usarli nei passaggi di processo che richiedono un proxy.</span><span class="sxs-lookup"><span data-stu-id="bd336-140">Proxies created for the data collector must grant access to `dc_admin` to create them and use them in any job steps that require a proxy.</span></span>  
  
-   <span data-ttu-id="bd336-141">**dc_operator**.</span><span class="sxs-lookup"><span data-stu-id="bd336-141">**dc_operator**.</span></span> <span data-ttu-id="bd336-142">I membri di `dc_admin` ereditano le autorizzazioni concesse a **dc_operator**.</span><span class="sxs-lookup"><span data-stu-id="bd336-142">Members of `dc_admin` inherit the permissions given to **dc_operator**.</span></span>  
  
### <a name="dc_operator-role"></a><span data-ttu-id="bd336-143">Ruolo dc_operator</span><span class="sxs-lookup"><span data-stu-id="bd336-143">dc_operator Role</span></span>  
 <span data-ttu-id="bd336-144">I membri del ruolo **dc_operator** hanno accesso in lettura e aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="bd336-144">Members of the **dc_operator** role have Read and Update access.</span></span> <span data-ttu-id="bd336-145">Tale ruolo supporta le attività di operazioni relative all'esecuzione e alla configurazione dei set di raccolta.</span><span class="sxs-lookup"><span data-stu-id="bd336-145">This role supports operations tasks related to running and configuring collection sets.</span></span> <span data-ttu-id="bd336-146">I membri di questo ruolo possono eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="bd336-146">Members of this role can perform the following operations:</span></span>  
  
-   <span data-ttu-id="bd336-147">Avviare o arrestare un set di raccolta.</span><span class="sxs-lookup"><span data-stu-id="bd336-147">Start or stop a collection set.</span></span>  
  
-   <span data-ttu-id="bd336-148">Enumerare set di raccolta esistenti.</span><span class="sxs-lookup"><span data-stu-id="bd336-148">Enumerate existing collection sets.</span></span>  
  
-   <span data-ttu-id="bd336-149">Visualizzare le informazioni dettagliate (ad esempio elementi della raccolta e frequenza di raccolta) associate ad un set di raccolta.</span><span class="sxs-lookup"><span data-stu-id="bd336-149">View the detailed information (for example, collection items, and collection frequency) associated with a collection set.</span></span>  
  
-   <span data-ttu-id="bd336-150">Modificare la frequenza di caricamento per i set di raccolta esistenti.</span><span class="sxs-lookup"><span data-stu-id="bd336-150">Change the upload frequency for existing collection sets.</span></span>  
  
-   <span data-ttu-id="bd336-151">Modificare la frequenza di raccolta per gli elementi della raccolta appartenenti a un set di raccolta esistente.</span><span class="sxs-lookup"><span data-stu-id="bd336-151">Change the collection frequency for collection items that are part of an existing collection set.</span></span>  
  
 <span data-ttu-id="bd336-152">Il ruolo **dc_operator** è un membro dei seguenti ruoli richiesti per l'enumerazione e la visualizzazione dei pacchetti dell'agente di raccolta dati:</span><span class="sxs-lookup"><span data-stu-id="bd336-152">The **dc_operator** role is a member of the following roles that are required for enumerating and viewing data collector packages:</span></span>  
  
-   <span data-ttu-id="bd336-153">**db_ssisltduser**</span><span class="sxs-lookup"><span data-stu-id="bd336-153">**db_ssisltduser**</span></span>  
  
-   <span data-ttu-id="bd336-154">**db_ssisoperator**</span><span class="sxs-lookup"><span data-stu-id="bd336-154">**db_ssisoperator**</span></span>  
  
 <span data-ttu-id="bd336-155">Per altre informazioni, vedere [Ruoli Integration Services &#40;servizio SSIS&#41;](../../integration-services/security/integration-services-roles-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="bd336-155">For more information, see [Integration Services Roles &#40;SSIS Service&#41;](../../integration-services/security/integration-services-roles-ssis-service.md).</span></span>  
  
### <a name="dc_proxy-role"></a><span data-ttu-id="bd336-156">Ruolo dc_proxy</span><span class="sxs-lookup"><span data-stu-id="bd336-156">dc_proxy Role</span></span>  
 <span data-ttu-id="bd336-157">I membri del ruolo **dc_proxy** hanno accesso in lettura ai set di raccolta dell'agente di raccolta dati e alle proprietà a livello di agente di raccolta.</span><span class="sxs-lookup"><span data-stu-id="bd336-157">Members of the **dc_proxy** role have Read access to data collector collection sets and collector-level properties.</span></span> <span data-ttu-id="bd336-158">I membri di questo ruolo possono inoltre eseguire processi di cui sono proprietari e creare passaggi di processo eseguibili come un account proxy esistente.</span><span class="sxs-lookup"><span data-stu-id="bd336-158">Members of this role can also execute jobs that they own and create job steps that run as an existing proxy account.</span></span>  
  
 <span data-ttu-id="bd336-159">I membri di questo ruolo possono eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="bd336-159">Members of this role can perform the following operations:</span></span>  
  
-   <span data-ttu-id="bd336-160">Visualizzare informazioni di configurazione del set di raccolta (ad esempio parametri di input per elementi della raccolta e la frequenza di raccolta per questi elementi).</span><span class="sxs-lookup"><span data-stu-id="bd336-160">View collection set configuration information (for example, input parameters for collection items, and the collection frequency for these items).</span></span>  
  
-   <span data-ttu-id="bd336-161">Ottenere informazioni crittografate interne a cui è possibile accedere soltanto mediante una stored procedure firmata, ad esempio informazioni di connessione al data warehouse usate per il caricamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="bd336-161">Obtain internal encrypted information that can only be accessed by a signed stored procedure (for example, data warehouse connection information used for data uploads).</span></span>  
  
-   <span data-ttu-id="bd336-162">Registrare eventi di runtime del set di raccolta.</span><span class="sxs-lookup"><span data-stu-id="bd336-162">Log collection-set run-time events.</span></span>  
  
 <span data-ttu-id="bd336-163">Il ruolo **dc_proxy** è un membro dei seguenti ruoli richiesti per l'enumerazione e la visualizzazione dei pacchetti dell'agente di raccolta dati:</span><span class="sxs-lookup"><span data-stu-id="bd336-163">The **dc_proxy** role is a member of the following roles that are required for enumerating and viewing data collector packages:</span></span>  
  
-   <span data-ttu-id="bd336-164">**db_ssisltduser**.</span><span class="sxs-lookup"><span data-stu-id="bd336-164">**db_ssisltduser**.</span></span>  
  
-   <span data-ttu-id="bd336-165">**db_ssisoperator**</span><span class="sxs-lookup"><span data-stu-id="bd336-165">**db_ssisoperator**</span></span>  
  
 <span data-ttu-id="bd336-166">Per altre informazioni, vedere [Ruoli Integration Services &#40;servizio SSIS&#41;](../../integration-services/security/integration-services-roles-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="bd336-166">For more information, see [Integration Services Roles &#40;SSIS Service&#41;](../../integration-services/security/integration-services-roles-ssis-service.md).</span></span>  
  
## <a name="permissions-for-configuring-and-using-the-management-data-warehouse"></a><span data-ttu-id="bd336-167">Autorizzazioni per la configurazione e l'utilizzo del data warehouse di gestione</span><span class="sxs-lookup"><span data-stu-id="bd336-167">Permissions for Configuring and Using the Management Data Warehouse</span></span>  
 <span data-ttu-id="bd336-168">A seconda dell'attività, gli utenti devono essere membri di uno o più ruoli predefiniti del database forniti per accedere al data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="bd336-168">Depending on the task, users must be members of one or more of the fixed database roles provided for accessing the management data warehouse.</span></span> <span data-ttu-id="bd336-169">I ruoli sono i seguenti, elencati a partire dall'accesso con privilegi di livello più alto fino a quello con privilegi minimi:</span><span class="sxs-lookup"><span data-stu-id="bd336-169">In order of most-privileged to least-privileged access, the roles are as follows:</span></span>  
  
-   <span data-ttu-id="bd336-170">**mdw_admin**</span><span class="sxs-lookup"><span data-stu-id="bd336-170">**mdw_admin**</span></span>  
  
-   <span data-ttu-id="bd336-171">**mdw_writer**</span><span class="sxs-lookup"><span data-stu-id="bd336-171">**mdw_writer**</span></span>  
  
-   <span data-ttu-id="bd336-172">**mdw_reader**</span><span class="sxs-lookup"><span data-stu-id="bd336-172">**mdw_reader**</span></span>  
  
 <span data-ttu-id="bd336-173">Questi ruoli sono archiviati nel database msdb.</span><span class="sxs-lookup"><span data-stu-id="bd336-173">These roles are stored in the msdb database.</span></span> <span data-ttu-id="bd336-174">Per impostazione predefinita, nessun utente è membro di questi ruoli di database.</span><span class="sxs-lookup"><span data-stu-id="bd336-174">By default, no user is a member of these database roles.</span></span> <span data-ttu-id="bd336-175">L'appartenenza dell'utente a questi ruoli deve essere concessa esplicitamente.</span><span class="sxs-lookup"><span data-stu-id="bd336-175">User membership in these roles must be granted explicitly.</span></span>  
  
 <span data-ttu-id="bd336-176">Gli utenti membri del `sysadmin` ruolo predefinito del server dispongono di accesso completo alle viste dell'agente di raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="bd336-176">Users who are members of the `sysadmin` fixed server role have full access to data collector views.</span></span> <span data-ttu-id="bd336-177">Tuttavia è necessario che vengano aggiunti esplicitamente ai ruoli del database per eseguire altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="bd336-177">However, they need to be explicitly added to database roles to perform other operations.</span></span>  
  
### <a name="mdw_admin-role"></a><span data-ttu-id="bd336-178">Ruolo mdw_admin</span><span class="sxs-lookup"><span data-stu-id="bd336-178">mdw_admin Role</span></span>  
 <span data-ttu-id="bd336-179">I membri del ruolo **mdw_admin** hanno accesso in lettura, scrittura, aggiornamento ed eliminazione al data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="bd336-179">Members of the **mdw_admin** role have Read, Write, Update, and Delete access to the management data warehouse.</span></span>  
  
 <span data-ttu-id="bd336-180">I membri di questo ruolo possono eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="bd336-180">Members of this role can perform the following operations:</span></span>  
  
-   <span data-ttu-id="bd336-181">Modificare lo schema del data warehouse di gestione se necessario (ad esempio per aggiungere una nuova tabella quando viene installato un nuovo tipo di raccolta).</span><span class="sxs-lookup"><span data-stu-id="bd336-181">Change the management data warehouse schema when required (for example, adding a new table when a new collection type is installed).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bd336-182">Se è presente una modifica dello schema, l'utente deve essere anche membro del `dc_admin` ruolo per installare un nuovo tipo di agente di raccolta, poiché questa azione richiede l'autorizzazione per aggiornare la configurazione dell'agente di raccolta dati in msdb.</span><span class="sxs-lookup"><span data-stu-id="bd336-182">Where there is a schema change, the user must also be a member of the `dc_admin` role to install a new collector type, since this action requires permission to update the data collector configuration in msdb.</span></span>  
  
-   <span data-ttu-id="bd336-183">Eseguire processi di manutenzione sul data warehouse di gestione, ad esempio archiviazione o pulizia.</span><span class="sxs-lookup"><span data-stu-id="bd336-183">Run maintenance jobs on the management data warehouse, such as archive or cleanup.</span></span>  
  
### <a name="mdw_writer-role"></a><span data-ttu-id="bd336-184">Ruolo mdw_writer</span><span class="sxs-lookup"><span data-stu-id="bd336-184">mdw_writer Role</span></span>  
 <span data-ttu-id="bd336-185">I membri del ruolo **mdw_writer** possono caricare e scrivere dati nel data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="bd336-185">Members of the **mdw_writer** role can upload and write data to the management data warehouse.</span></span> <span data-ttu-id="bd336-186">Gli agenti di raccolta dati che archiviano dati nel data warehouse di gestione devono essere membri di questo ruolo.</span><span class="sxs-lookup"><span data-stu-id="bd336-186">Any data collector that stores data in the management data warehouse has to be a member of this role.</span></span>  
  
### <a name="mdw_reader-role"></a><span data-ttu-id="bd336-187">Ruolo mdw_reader</span><span class="sxs-lookup"><span data-stu-id="bd336-187">mdw_reader Role</span></span>  
 <span data-ttu-id="bd336-188">I membri del ruolo **mdw_reader** hanno accesso in lettura al data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="bd336-188">Members of the **mdw_reader** role have Read access to the management data warehouse.</span></span> <span data-ttu-id="bd336-189">Poiché lo scopo di questo ruolo è supportare la risoluzione dei problemi fornendo accesso ai dati della cronologia, i membri di questo ruolo non possono visualizzare gli altri elementi dello schema del data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="bd336-189">Because the purpose of this role is to support troubleshooting by providing access to historical data, members of this role cannot view other elements of the management data warehouse schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd336-190">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd336-190">See Also</span></span>  
 [<span data-ttu-id="bd336-191">Implementazione della sicurezza di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="bd336-191">Implement SQL Server Agent Security</span></span>](../../ssms/agent/implement-sql-server-agent-security.md)  
  
  
