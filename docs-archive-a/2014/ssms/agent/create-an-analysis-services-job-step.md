---
title: Creare un passaggio di processo di Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- job steps [Analysis Services]
ms.assetid: 03d4bb86-514b-4a55-97b9-c2c0fa08b428
author: stevestein
ms.author: sstein
ms.openlocfilehash: ed0e63c22d4cad270bcb544b03decba269e4f43a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715063"
---
# <a name="create-an-analysis-services-job-step"></a><span data-ttu-id="37b58-102">Create an Analysis Services Job Step</span><span class="sxs-lookup"><span data-stu-id="37b58-102">Create an Analysis Services Job Step</span></span>
  <span data-ttu-id="37b58-103">In questo argomento viene descritto come creare e definire passaggi del processo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] che consentono di eseguire comandi e query di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Analysis Services utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] o SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="37b58-103">This topic describes how to create and define [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job steps in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that execute [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Analysis Services commands and queries by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
-   <span data-ttu-id="37b58-104">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="37b58-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="37b58-105">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="37b58-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="37b58-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="37b58-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="37b58-107">**Per creare i passaggi di un processo di SQL Server utilizzando i comandi e/o le query di Analysis Services con:**</span><span class="sxs-lookup"><span data-stu-id="37b58-107">**To create a SQL Server job steps using Analysis Services commands and/or queries, with:**</span></span>  
  
     [<span data-ttu-id="37b58-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="37b58-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="37b58-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="37b58-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="37b58-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="37b58-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="37b58-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="37b58-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="37b58-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="37b58-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="37b58-113">Se il passaggio del processo utilizza un comando di Analysis Services, l'istruzione del comando deve essere un metodo **Execute** di Servizi di XML for Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="37b58-113">If the job step uses an Analysis Services command, the command statement must be an XML for Analysis Services **Execute** method.</span></span> <span data-ttu-id="37b58-114">L'istruzione non può includere un elemento Envelope SOAP (Simple Object Access Protocol) completo o un metodo **Discover** di XML for Analysis.</span><span class="sxs-lookup"><span data-stu-id="37b58-114">The statement may not contain a complete Simple Object Access Protocol (SOAP) envelope or an XML for Analysis **Discover** method.</span></span> <span data-ttu-id="37b58-115">A differenza di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , i passaggi di processo di **Agent non supportano le buste SOAP complete e il metodo** Discover [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="37b58-115">While [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] supports complete SOAP envelopes and the **Discover** method, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job steps do not.</span></span> <span data-ttu-id="37b58-116">Per altre informazioni su XML for Analysis Services, vedere [Panoramica di XML for Analysis (XMLA)](https://msdn.microsoft.com/library/ms187190.aspx).</span><span class="sxs-lookup"><span data-stu-id="37b58-116">For more information about XML for Analysis Services, see [XML for Analysis Overview (XMLA)](https://msdn.microsoft.com/library/ms187190.aspx).</span></span>  
  
-   <span data-ttu-id="37b58-117">Se il passaggio del processo utilizza una query di Analysis Services, l'istruzione della query deve essere una query di espressioni MDX.</span><span class="sxs-lookup"><span data-stu-id="37b58-117">If the job step uses an Analysis Services query, the query statement must be a multidimensional expressions (MDX) query.</span></span> <span data-ttu-id="37b58-118">Per ulteriori informazioni su MDX, vedere [nozioni fondamentali sulle query mdx &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/mdx/mdx-query-fundamentals-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="37b58-118">For more information about MDX, see [MDX Query Fundamentals &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/mdx/mdx-query-fundamentals-analysis-services).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="37b58-119">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="37b58-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="37b58-120">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="37b58-120">Permissions</span></span>  
  
-   <span data-ttu-id="37b58-121">Per eseguire un passaggio di processo in cui viene utilizzato il sottosistema Analysis Services, è necessario che l'utente sia membro del ruolo predefinito del server **sysadmin** o che sia autorizzato ad accedere a un account proxy valido definito per l'utilizzo di questo sottosistema.</span><span class="sxs-lookup"><span data-stu-id="37b58-121">To run a job step that uses the Analysis Services subsystem, a user must be a member of the **sysadmin** fixed server role or have access to a valid proxy account defined to use this subsystem.</span></span> <span data-ttu-id="37b58-122">L'account del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent o l'account proxy deve inoltre essere amministratore di Analysis Services, nonché un account di dominio Windows valido.</span><span class="sxs-lookup"><span data-stu-id="37b58-122">In addition, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account or the proxy must be an Analysis Services administrator and a valid Windows domain account.</span></span>  
  
-   <span data-ttu-id="37b58-123">Solo i membri del ruolo predefinito del server **sysadmin** sono autorizzati a scrivere l'output di un passaggio del processo in un file.</span><span class="sxs-lookup"><span data-stu-id="37b58-123">Only members of the **sysadmin** fixed server role can write job step output to a file.</span></span> <span data-ttu-id="37b58-124">Se il passaggio del processo viene eseguito da utenti appartenenti al ruolo di database **SQLAgentUserRole** nel database **msdb** , sarà possibile scrivere l'output solo in una tabella.</span><span class="sxs-lookup"><span data-stu-id="37b58-124">If the job step is run by users who are members of the **SQLAgentUserRole** database role in the **msdb** database, then the output can be written only to a table.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="37b58-125">Agent scrive l'output del passaggio di processo nella tabella **sysjobstepslog** del database **msdb** .</span><span class="sxs-lookup"><span data-stu-id="37b58-125">Agent writes job step output to the **sysjobstepslog** table in the **msdb** database.</span></span>  
  
-   <span data-ttu-id="37b58-126">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="37b58-126">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="37b58-127">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="37b58-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-analysis-services-command-job-step"></a><span data-ttu-id="37b58-128">Per creare un passaggio di processo di un comando di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="37b58-128">To create an Analysis Services command job step</span></span>  
  
1.  <span data-ttu-id="37b58-129">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="37b58-129">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="37b58-130">Espandere **SQL Server Agent**, creare un nuovo processo oppure fare clic con il pulsante destro del mouse su un processo esistente e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="37b58-130">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="37b58-131">Per altre informazioni sulla creazione di un processo, vedere [Creazione di processi](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="37b58-131">For more information on creating a job, see [Create Jobs](create-jobs.md).</span></span>  
  
3.  <span data-ttu-id="37b58-132">Nella finestra di dialogo **Proprietà processo** fare clic sulla pagina **Passaggi** e quindi su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="37b58-132">In the **Job Properties** dialog box, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="37b58-133">Nella finestra di dialogo **Nuovo passaggio di processo** digitare il nome del passaggio del processo nella casella **Nome passaggio**.</span><span class="sxs-lookup"><span data-stu-id="37b58-133">In the **New Job Step** dialog box, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="37b58-134">Nell'elenco **Tipo** fare clic su **Comando di SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="37b58-134">In the **Type** list, click **SQL Server Analysis Services Command**.</span></span>  
  
6.  <span data-ttu-id="37b58-135">Nell'elenco **Esegui come** selezionare un proxy definito per l'utilizzo del sottosistema Comando di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="37b58-135">In the **Run as** list, select a proxy that has been defined to use the Analysis Services Command subsystem.</span></span> <span data-ttu-id="37b58-136">Un utente membro del ruolo predefinito del server **sysadmin** è inoltre autorizzato a selezionare **Account del servizio SQL Server Agent** per l'esecuzione di questo passaggio del processo.</span><span class="sxs-lookup"><span data-stu-id="37b58-136">A user who is a member of the **sysadmin** fixed server role can also select **SQL Agent Service Account** to run this job step.</span></span>  
  
7.  <span data-ttu-id="37b58-137">Selezionare il **Server** in cui verrà eseguito il passaggio del processo oppure digitare il nome del server desiderato.</span><span class="sxs-lookup"><span data-stu-id="37b58-137">Select the **Server** where the job step will run, or type the server name.</span></span>  
  
8.  <span data-ttu-id="37b58-138">Nella casella **Comando** immettere l'istruzione da eseguire oppure fare clic su **Apri** per selezionare l'istruzione desiderata.</span><span class="sxs-lookup"><span data-stu-id="37b58-138">In the **Command** box, type the statement to execute, or click **Open** to select a statement.</span></span>  
  
9. <span data-ttu-id="37b58-139">Fare clic sulla pagina **Avanzate** per definire le opzioni relative al passaggio del processo, ad esempio l'azione che dovrà essere eseguita da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in caso di esito positivo o negativo del passaggio del processo, il numero di tentativi di esecuzione del passaggio del processo e il percorso in cui scrivere l'output del passaggio del processo.</span><span class="sxs-lookup"><span data-stu-id="37b58-139">Click the **Advanced** page to define options for this job step, such as what action [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should take if the job step succeeds or fails, how many times the job step should be attempted, and where the job step output should be written.</span></span>  
  
#### <a name="to-create-an-analysis-services-query-job-step"></a><span data-ttu-id="37b58-140">Per creare un passaggio del processo di una query di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="37b58-140">To create an Analysis Services query job step</span></span>  
  
1.  <span data-ttu-id="37b58-141">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="37b58-141">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="37b58-142">Espandere **SQL Server Agent**, creare un nuovo processo oppure fare clic con il pulsante destro del mouse su un processo esistente e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="37b58-142">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="37b58-143">Per altre informazioni sulla creazione di un processo, vedere [Creazione di processi](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="37b58-143">For more information on creating a job, see [Create Jobs](create-jobs.md).</span></span>  
  
3.  <span data-ttu-id="37b58-144">Nella finestra di dialogo **Proprietà processo** fare clic sulla pagina **Passaggi** e quindi su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="37b58-144">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="37b58-145">Nella finestra di dialogo **Nuovo passaggio di processo** digitare il nome del passaggio del processo nella casella **Nome passaggio**.</span><span class="sxs-lookup"><span data-stu-id="37b58-145">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="37b58-146">Nell'elenco **Tipo** fare clic su **Query di SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="37b58-146">In the **Type** list, click **SQL Server Analysis Services Query**.</span></span>  
  
6.  <span data-ttu-id="37b58-147">Nell'elenco **Esegui come** selezionare un proxy definito per l'utilizzo del sottosistema Query di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="37b58-147">In the **Run as** list, select a proxy that has been defined to use the Analysis Services Query subsystem.</span></span> <span data-ttu-id="37b58-148">Un utente membro del ruolo predefinito del server **sysadmin** è inoltre autorizzato a selezionare **Account del servizio SQL Server Agent** per l'esecuzione di questo passaggio del processo.</span><span class="sxs-lookup"><span data-stu-id="37b58-148">A user who is a member of the **sysadmin** fixed server role can also select **SQL Agent Service Account** to run this job step.</span></span>  
  
7.  <span data-ttu-id="37b58-149">Selezionare il **Server** e il **Database** in cui verrà eseguito il passaggio del processo oppure digitare il nome del server o del database desiderato.</span><span class="sxs-lookup"><span data-stu-id="37b58-149">Select the **Server** and the **Database** where the job step will run, or type the server or database name.</span></span>  
  
8.  <span data-ttu-id="37b58-150">Nella casella **Comando** immettere l'istruzione da eseguire oppure fare clic su **Apri** per selezionare l'istruzione desiderata.</span><span class="sxs-lookup"><span data-stu-id="37b58-150">In the **Command** box, type the statement to execute, or click **Open** to select a statement.</span></span>  
  
9. <span data-ttu-id="37b58-151">Fare clic sulla pagina **Avanzate** per definire le opzioni relative al passaggio del processo, ad esempio l'azione che dovrà essere eseguita da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in caso di esito positivo o negativo del passaggio del processo, il numero di tentativi di esecuzione del passaggio del processo e il percorso in cui scrivere l'output del passaggio del processo.</span><span class="sxs-lookup"><span data-stu-id="37b58-151">Click the **Advanced** page to define options for this job step, such as what action [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should take if the job step succeeds or fails, how many times the job step should be attempted, and where the job step output should be written.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="37b58-152">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="37b58-152">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-analysis-services-command-job-step"></a><span data-ttu-id="37b58-153">Per creare un passaggio di processo di un comando di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="37b58-153">To create an Analysis Services command job step</span></span>  
  
1.  <span data-ttu-id="37b58-154">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37b58-154">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="37b58-155">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="37b58-155">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="37b58-156">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="37b58-156">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- Creates a job step that uses XMLA to create a relational data source that references the AdventureWorks2012 Microsoft SQL Server database  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Create a relational data source that references the AdventureWorks2012 Microsoft SQL Server database ',  
        @subsystem = N'ANALYSISCOMMAND',  
        @command = N' <Create xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
        <ParentObject>  
            <DatabaseID>AdventureWorks2012</DatabaseID>  
        </ParentObject>  
        <ObjectDefinition>  
            <DataSource xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RelationalDataSource">  
                <ID>AdventureWorks2012</ID>  
                <Name>Adventure Works 2012</Name>  
                <ConnectionString>Data Source=localhost;Initial Catalog=AdventureWorks2012;Integrated Security=True</ConnectionString>  
                <ImpersonationInfo>  
                    <ImpersonationMode>ImpersonateServiceAccount</ImpersonationMode>  
                </ImpersonationInfo>  
                <ManagedProvider>System.Data.SqlClient</ManagedProvider>  
                <Timeout>PT0S</Timeout>  
            </DataSource>  
        </ObjectDefinition>  
    </Create>', ;  
    GO  
    ```  
  
 <span data-ttu-id="37b58-157">Per ulteriori informazioni, vedere [sp_add_jobstep &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="37b58-157">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
#### <a name="to-create-an-analysis-services-query-job-step"></a><span data-ttu-id="37b58-158">Per creare un passaggio del processo di una query di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="37b58-158">To create an Analysis Services query job step</span></span>  
  
1.  <span data-ttu-id="37b58-159">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37b58-159">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="37b58-160">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="37b58-160">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="37b58-161">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="37b58-161">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- Creates a job step that uses MDX to return data  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Returns the Internet sales amount by state',  
        @subsystem = N'ANALYSISQUERY',  
        @command = N' SELECT  
       [Measures].[Internet Sales Amount] ON COLUMNS,  
       [Customer].[State-Province].Members ON ROWS  
    FROM [AdventureWorks2012]',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="37b58-162">Per ulteriori informazioni, vedere [sp_add_jobstep &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="37b58-162">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="37b58-163">Utilizzo di SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="37b58-163">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="37b58-164">**Per creare un passaggio di processo di uno script di PowerShell**</span><span class="sxs-lookup"><span data-stu-id="37b58-164">**To create a PowerShell Script job step**</span></span>  
  
 <span data-ttu-id="37b58-165">Utilizzare la classe `JobStep` tramite un linguaggio di programmazione, come XMLA o MDX.</span><span class="sxs-lookup"><span data-stu-id="37b58-165">Use the `JobStep` class by using a programming language that you choose, such as XMLA or MDX.</span></span> <span data-ttu-id="37b58-166">Per altre informazioni, vedere [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="37b58-166">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
