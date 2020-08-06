---
title: Visualizzare o modificare le proprietà del server (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- viewing server properties
- server properties [SQL Server]
- displaying server properties
- servers [SQL Server], viewing
ms.assetid: 55f3ac04-5626-4ad2-96bd-a1f1b079659d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 415d4e2d1aaa3166ae4df2dea53b34e064544e06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713471"
---
# <a name="view-or-change-server-properties-sql-server"></a><span data-ttu-id="34970-102">Visualizzare o modificare le proprietà del server (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="34970-102">View or Change Server Properties (SQL Server)</span></span>
  <span data-ttu-id="34970-103">In questo argomento viene illustrato come visualizzare o modificare le proprietà di un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]o Gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="34970-103">This topic describes how to view or change the properties of an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Configuration Manager.</span></span>  
  
 <span data-ttu-id="34970-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="34970-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="34970-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="34970-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="34970-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="34970-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="34970-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="34970-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="34970-108">**Per visualizzare o modificare le proprietà del server tramite:**</span><span class="sxs-lookup"><span data-stu-id="34970-108">**To view or change server properties, using:**</span></span>  
  
     [<span data-ttu-id="34970-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="34970-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="34970-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="34970-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="34970-111">Gestione configurazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="34970-111">SQL Server Configuration Manager</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="34970-112">**Completamento:**  [Dopo la modifica delle proprietà del server](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="34970-112">**Follow Up:**  [After you change server properties](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="34970-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="34970-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="34970-114">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="34970-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="34970-115">Quando si utilizza sp_configure è necessario eseguire RECONFIGURE oppure RECONFIGURE WITH OVERRIDE dopo aver impostato un'opzione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="34970-115">When using sp_configure, you must run either RECONFIGURE or RECONFIGURE WITH OVERRIDE after setting a configuration option.</span></span> <span data-ttu-id="34970-116">L'istruzione RECONFIGURE WITH OVERRIDE è generalmente riservata alle opzioni di configurazione che dovrebbero essere utilizzate con estrema cautela.</span><span class="sxs-lookup"><span data-stu-id="34970-116">The RECONFIGURE WITH OVERRIDE statement is usually reserved for configuration options that should be used with extreme caution.</span></span> <span data-ttu-id="34970-117">È comunque possibile utilizzare l'istruzione RECONFIGURE WITH OVERRIDE con tutte le opzioni di configurazione, anche in sostituzione di RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="34970-117">However, RECONFIGURE WITH OVERRIDE works for all configuration options, and you can use it in place of RECONFIGURE.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="34970-118">L'istruzione RECONFIGURE viene eseguita all'interno di una transazione.</span><span class="sxs-lookup"><span data-stu-id="34970-118">RECONFIGURE executes within a transaction.</span></span> <span data-ttu-id="34970-119">Se una delle operazioni di riconfigurazione ha esito negativo, nessuna operazione di riconfigurazione sarà resa effettiva.</span><span class="sxs-lookup"><span data-stu-id="34970-119">If any of the reconfigure operations fail, none of the reconfigure operations will take effect.</span></span>  
  
-   <span data-ttu-id="34970-120">In alcune pagine delle proprietà sono presenti dati ottenuti tramite il servizio Strumentazione gestione Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="34970-120">Some property pages present information obtained via Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="34970-121">Per visualizzare queste pagine, è necessario che nel computer che esegue [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]sia installato il servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="34970-121">To display those pages, WMI must be installed on the computer running [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="34970-122">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="34970-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="34970-123">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="34970-123">Permissions</span></span>  
 <span data-ttu-id="34970-124">Per altre informazioni, vedere [Ruoli a livello di server](../../relational-databases/security/authentication-access/server-level-roles.md).</span><span class="sxs-lookup"><span data-stu-id="34970-124">For more information, see [Server-Level Roles](../../relational-databases/security/authentication-access/server-level-roles.md).</span></span>  
  
 <span data-ttu-id="34970-125">Per impostazione predefinita, le autorizzazioni Execute su senza `sp_configure` parametri o solo con il primo parametro vengono concesse a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="34970-125">Execute permissions on `sp_configure` with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="34970-126">Per eseguire `sp_configure` con entrambi i parametri per modificare un'opzione di configurazione o per eseguire l'istruzione RECONFIGURE, a un utente deve essere concessa l'autorizzazione a livello di server ALTER Settings.</span><span class="sxs-lookup"><span data-stu-id="34970-126">To execute `sp_configure` with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="34970-127">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="34970-127">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="34970-128">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="34970-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-server-properties"></a><span data-ttu-id="34970-129">Per visualizzare o modificare le proprietà del server</span><span class="sxs-lookup"><span data-stu-id="34970-129">To view or change server properties</span></span>  
  
1.  <span data-ttu-id="34970-130">In Esplora oggetti fare clic con il pulsante destro del mouse su un server, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="34970-130">In Object Explorer, right-click a server, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="34970-131">Nella finestra di dialogo **Proprietà server** fare clic su una pagina per visualizzare o modificare le relative informazioni del server.</span><span class="sxs-lookup"><span data-stu-id="34970-131">In the **Server Properties** dialog box, click a page to view or change server information about that page.</span></span> <span data-ttu-id="34970-132">Alcune proprietà sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="34970-132">Some properties are read-only.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="34970-133">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="34970-133">Using Transact-SQL</span></span>  
  
#### <a name="to-view-server-properties-by-using-the-serverproperty-built-in-function"></a><span data-ttu-id="34970-134">Per visualizzare le proprietà del server tramite la funzione predefinita SERVERPROPERTY</span><span class="sxs-lookup"><span data-stu-id="34970-134">To view server properties by using the SERVERPROPERTY built-in function</span></span>  
  
1.  <span data-ttu-id="34970-135">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34970-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="34970-136">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="34970-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="34970-137">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="34970-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="34970-138">In questo esempio viene usata la funzione predefinita [SERVERPROPERTY](/sql/t-sql/functions/serverproperty-transact-sql) in un'istruzione `SELECT` per restituire informazioni sul server corrente.</span><span class="sxs-lookup"><span data-stu-id="34970-138">This example uses the [SERVERPROPERTY](/sql/t-sql/functions/serverproperty-transact-sql) built-in function in a `SELECT` statement to return information about the current server.</span></span> <span data-ttu-id="34970-139">Ciò risulta utile quando in un server basato su Windows sono installate più istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e il client deve aprire un'altra connessione alla stessa istanza utilizzata dalla connessione corrente.</span><span class="sxs-lookup"><span data-stu-id="34970-139">This scenario is useful when there are multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installed on a Windows-based server, and the client must open another connection to the same instance that is used by the current connection.</span></span>  
  
    ```sql  
    SELECT CONVERT( sysname, SERVERPROPERTY('servername'));  
    GO  
    ```  
  
#### <a name="to-view-server-properties-by-using-the-sysservers-catalog-view"></a><span data-ttu-id="34970-140">Per visualizzare le proprietà del server tramite la vista del catalogo sys.servers</span><span class="sxs-lookup"><span data-stu-id="34970-140">To view server properties by using the sys.servers catalog view</span></span>  
  
1.  <span data-ttu-id="34970-141">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34970-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="34970-142">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="34970-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="34970-143">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="34970-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="34970-144">In questo esempio viene eseguita una query nella vista del catalogo [sys.servers](/sql/relational-databases/system-catalog-views/sys-servers-transact-sql) per restituire il nome (`name`) e l'ID (`server_id`) del server corrente e il nome del provider OLE DB (`provider`) per la connessione a un server collegato.</span><span class="sxs-lookup"><span data-stu-id="34970-144">This example queries the [sys.servers](/sql/relational-databases/system-catalog-views/sys-servers-transact-sql) catalog view to return the name (`name`) and ID (`server_id`) of the current server, and the name of the OLE DB provider (`provider`) for connecting to a linked server.</span></span>  
  
    ```sql  
    USE AdventureWorks2012;   
    GO  
    SELECT name, server_id, provider  
    FROM sys.servers ;   
    GO
    ```  
  
#### <a name="to-view-server-properties-by-using-the-sysconfigurations-catalog-view"></a><span data-ttu-id="34970-145">Per visualizzare le proprietà del server tramite la vista del catalogo sys.configurations</span><span class="sxs-lookup"><span data-stu-id="34970-145">To view server properties by using the sys.configurations catalog view</span></span>  
  
1.  <span data-ttu-id="34970-146">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34970-146">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="34970-147">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="34970-147">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="34970-148">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="34970-148">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="34970-149">In questo esempio viene eseguita una query nella vista del catalogo [sys.configurations](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) per restituire informazioni su ogni opzione di configurazione del server nel server corrente.</span><span class="sxs-lookup"><span data-stu-id="34970-149">This example queries the [sys.configurations](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) catalog view to return information about each server configuration option on the current server.</span></span> <span data-ttu-id="34970-150">Nell'esempio vengono restituiti il nome (`name`) e la descrizione (`description`) dell'opzione e viene indicato se l'opzione è avanzata (`is_advanced`).</span><span class="sxs-lookup"><span data-stu-id="34970-150">The example returns the name (`name`) and description (`description`) of the option and whether the option is an advanced option (`is_advanced`).</span></span>  
  
    ```sql
    USE AdventureWorks2012;
    GO  
    SELECT name, description, is_advanced  
    FROM sys.configurations ;
    GO
    ```  
  
#### <a name="to-change-a-server-property-by-using-sp_configure"></a><span data-ttu-id="34970-151">Per modificare una proprietà del server tramite sp_configure</span><span class="sxs-lookup"><span data-stu-id="34970-151">To change a server property by using sp_configure</span></span>  
  
1.  <span data-ttu-id="34970-152">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34970-152">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="34970-153">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="34970-153">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="34970-154">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="34970-154">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="34970-155">In questo esempio viene illustrato come usare [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) per modificare una proprietà del server.</span><span class="sxs-lookup"><span data-stu-id="34970-155">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to change a server property.</span></span> <span data-ttu-id="34970-156">Nell'esempio il valore dell'opzione `fill factor` viene modificato in `100`.</span><span class="sxs-lookup"><span data-stu-id="34970-156">The example changes the value of the `fill factor` option to `100`.</span></span> <span data-ttu-id="34970-157">Per rendere effettiva la modifica, è necessario riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="34970-157">The server must be restarted before the change can take effect.</span></span>  
  
```sql  
Use AdventureWorks2012;  
GO  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'fill factor', 100;  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="34970-158">Per altre informazioni, vedere [Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md)sia installato il servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="34970-158">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="34970-159">Utilizzo di Gestione configurazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="34970-159">Using SQL Server Configuration Manager</span></span>  
 <span data-ttu-id="34970-160">È possibile visualizzare o modificare alcune proprietà del server tramite Gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="34970-160">Some server properties can be viewed or changed by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="34970-161">Ad esempio, è possibile visualizzare la versione e l'edizione dell'istanza di SQL Server o modificare il percorso in cui sono archiviati i file di log degli errori.</span><span class="sxs-lookup"><span data-stu-id="34970-161">For example, you can view the version and edition of the instance of SQL Server, or change the location where error log files are stored.</span></span> <span data-ttu-id="34970-162">È inoltre possibile visualizzare queste proprietà eseguendo query nelle [Funzioni a gestione dinamica e DMV correlate al server](/sql/relational-databases/system-dynamic-management-views/server-related-dynamic-management-views-and-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="34970-162">These properties can also be viewed by querying the [Server-Related Dynamic Management Views and Functions](/sql/relational-databases/system-dynamic-management-views/server-related-dynamic-management-views-and-functions-transact-sql).</span></span>  
  
#### <a name="to-view-or-change-server-properties"></a><span data-ttu-id="34970-163">Per visualizzare o modificare le proprietà del server</span><span class="sxs-lookup"><span data-stu-id="34970-163">To view or change server properties</span></span>  
  
1.  <span data-ttu-id="34970-164">Fare clic sul menu **Start** , scegliere **Tutti i programmi**, [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], **Strumenti di configurazione**e quindi **Gestione configurazione SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="34970-164">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="34970-165">In **Gestione configurazione SQL Server**fare clic su **Servizi di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="34970-165">In **SQL Server Configuration Manager**, click **SQL Server Services**.</span></span>  
  
3.  <span data-ttu-id="34970-166">Nel riquadro dei dettagli fare clic con il pulsante destro del mouse su **SQL Server (\<***instancename***>)** e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="34970-166">In the details pane, right-click **SQL Server (\<***instancename***>)**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="34970-167">Nella finestra di dialogo **Proprietà - SQL Server (\<***instancename***>)** , modificare le proprietà del server nella scheda **Servizio** o **Avanzate** e fare quindi clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="34970-167">In the **SQL Server (\<***instancename***>) Properties** dialog box, change the server properties on the **Service** tab or the **Advanced** tab, and then click **OK**.</span></span>  
  
##  <a name="follow-up-after-you-change-server-properties"></a><a name="FollowUp"></a><span data-ttu-id="34970-168">Completamento: dopo la modifica delle proprietà del server</span><span class="sxs-lookup"><span data-stu-id="34970-168">Follow Up: After you change server properties</span></span>  
 <span data-ttu-id="34970-169">Per alcune proprietà, potrebbe essere necessario riavviare il server per rendere effettiva la modifica.</span><span class="sxs-lookup"><span data-stu-id="34970-169">For some properties, the server might have to be restarted before the change can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34970-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34970-170">See Also</span></span>  
 <span data-ttu-id="34970-171">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="34970-171">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="34970-172">[Istruzioni SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="34970-172">[SET Statements &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statements-transact-sql) </span></span>  
 <span data-ttu-id="34970-173">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="34970-173">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span></span>  
 <span data-ttu-id="34970-174">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="34970-174">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="34970-175">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="34970-175">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="34970-176">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="34970-176">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 <span data-ttu-id="34970-177">[Configurare WMI per mostrare lo stato del server in Strumenti SQL Server](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md) </span><span class="sxs-lookup"><span data-stu-id="34970-177">[Configure WMI to Show Server Status in SQL Server Tools](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md) </span></span>  
 <span data-ttu-id="34970-178">[Gestione configurazione SQL Server](../../relational-databases/sql-server-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="34970-178">[SQL Server Configuration Manager](../../relational-databases/sql-server-configuration-manager.md) </span></span>  
 <span data-ttu-id="34970-179">[Funzioni di configurazione &#40;Transact-SQL&#41;](/sql/t-sql/functions/configuration-functions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="34970-179">[Configuration Functions &#40;Transact-SQL&#41;](/sql/t-sql/functions/configuration-functions-transact-sql) </span></span>  
 [<span data-ttu-id="34970-180">Funzioni a gestione dinamica e DMV correlate al server &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="34970-180">Server-Related Dynamic Management Views and Functions &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/server-related-dynamic-management-views-and-functions-transact-sql)  
