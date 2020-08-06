---
title: Creare un processo di SQL Server Agent per l'archiviazione di messaggi e log eventi di Posta elettronica database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- archiving mail messages and attachments [SQL Server]
- removing mail messages and attachements
- Database Mail [SQL Server], archiving
- saving mail messages and attachments
ms.assetid: 8f8f0fba-f750-4533-9b76-a9cdbcdc3b14
author: stevestein
ms.author: sstein
ms.openlocfilehash: b958b280c358a8aeb752600dee1c2aee31d14db1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626805"
---
# <a name="create-a-sql-server-agent-job-to-archive-database-mail-messages-and-event-logs"></a><span data-ttu-id="08150-102">Creazione di un processo di SQL Server Agent per l'archiviazione di messaggi e log eventi di Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="08150-102">Create a SQL Server Agent Job to Archive Database Mail Messages and Event Logs</span></span>
  <span data-ttu-id="08150-103">Oltre al log eventi di Posta elettronica database, nelle tabelle del database **msdb** viene mantenuta una copia dei messaggi di Posta elettronica database e dei relativi allegati.</span><span class="sxs-lookup"><span data-stu-id="08150-103">Copies of Database Mail messages and their attachments are retained in **msdb** tables along with the Database Mail event log.</span></span> <span data-ttu-id="08150-104">È consigliabile ridurre periodicamente le dimensioni delle tabelle e archiviare i messaggi e gli eventi non più necessari.</span><span class="sxs-lookup"><span data-stu-id="08150-104">Periodically you might want to reduce the size of the tables and archive messages and events that are no longer needed.</span></span> <span data-ttu-id="08150-105">Nelle procedure seguenti viene illustrato come creare un processo di SQL Server Agent per eseguire queste operazioni in modo automatico.</span><span class="sxs-lookup"><span data-stu-id="08150-105">The following procedures create a SQL Server Agent job to automate the process.</span></span>  
  
-   <span data-ttu-id="08150-106">**Prima di iniziare:** [Prerequisiti](#Prerequisites), [Raccomandazioni](#Recommendations), [Autorizzazioni](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="08150-106">**Before you begin:**  , [Prerequisites](#Prerequisites), [Recommendations](#Recommendations), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="08150-107">**Per archiviare messaggi e log di Posta elettronica database utilizzando:**  [SQL Server Agent](#Process_Overview)</span><span class="sxs-lookup"><span data-stu-id="08150-107">**To Archive Database Mail messages and logs using :**  [SQL Server Agent](#Process_Overview)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="08150-108">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="08150-108">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="08150-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="08150-109">Prerequisites</span></span>  
 <span data-ttu-id="08150-110">Le nuove tabelle per archiviare i dati dell'archivio possono trovarsi in un database di archiviazione speciale.</span><span class="sxs-lookup"><span data-stu-id="08150-110">The new tables to store the archive data might be located in a special archive database.</span></span> <span data-ttu-id="08150-111">In alternativa le righe possono essere esportate in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="08150-111">Alternatively the rows could be exported to a text file.</span></span>  
 
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="08150-112">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="08150-112">Recommendations</span></span>  
 <span data-ttu-id="08150-113">Nell'ambiente di produzione è consigliabile aggiungere un ulteriore controllo degli errori e inviare un messaggio di posta elettronica agli operatori se l'esecuzione del processo non viene completata.</span><span class="sxs-lookup"><span data-stu-id="08150-113">In your production environment, you might want to add additional error checking and send an e-mail message to operators if the job fails.</span></span>  
  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="08150-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="08150-114">Permissions</span></span>  
 <span data-ttu-id="08150-115">È necessario essere membri del ruolo predefinito del server **sysadmin** per eseguire le stored procedure descritte in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="08150-115">You must be a member of the **sysadmin** fixed server role to execute the stored procedures described in this topic.</span></span>  
  
  
###  <a name="overview-of-the-process"></a><a name="Process_Overview"></a> <span data-ttu-id="08150-116">Panoramica del processo</span><span class="sxs-lookup"><span data-stu-id="08150-116">Overview of the Process</span></span>  
  
-   <span data-ttu-id="08150-117">La prima procedura consente di creare un processo denominato Archive Database Mail effettuando i passaggi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="08150-117">The first procedure creates a job named Archive Database Mail with the following steps.</span></span>  
  
    1.  <span data-ttu-id="08150-118">Copiare tutti i messaggi dalle tabelle di Posta elettronica database in una nuova tabella con il nome basato sul mese precedente nel formato **DBMailArchive_** _<anno_mese>_ .</span><span class="sxs-lookup"><span data-stu-id="08150-118">Copy all messages from the Database Mail tables to a new table named after the previous month in the format **DBMailArchive_**_<year_month>_.</span></span>  
  
    2.  <span data-ttu-id="08150-119">Copiare gli allegati correlati ai messaggi copiati nel primo passaggio dalle tabelle di Posta elettronica database in una nuova tabella con il nome basato sul mese precedente nel formato **DBMailArchive_Attachments_** _<anno_mese>_ .</span><span class="sxs-lookup"><span data-stu-id="08150-119">Copy the attachments related to the messages copied in the first step, from the Database Mail tables to a new table named after the previous month in the format **DBMailArchive_Attachments_**_<year_month>_.</span></span>  
  
    3.  <span data-ttu-id="08150-120">Copiare gli eventi del registro eventi di Posta elettronica database correlati ai messaggi copiati nel primo passaggio dalle tabelle di Posta elettronica database in una nuova tabella con un nome basato sul mese precedente nel formato **DBMailArchive_Log_** _<anno_mese>_ .</span><span class="sxs-lookup"><span data-stu-id="08150-120">Copy the events from the Database Mail event log that are related to the messages copied in the first step, from the Database Mail tables to a new table named after the previous month in the format **DBMailArchive_Log_**_<year_month>_.</span></span>  
  
    4.  <span data-ttu-id="08150-121">Eliminare dalle tabelle di Posta elettronica database i record degli elementi di posta trasferiti.</span><span class="sxs-lookup"><span data-stu-id="08150-121">Delete the records of the transferred mail items from the Database Mail tables.</span></span>  
  
    5.  <span data-ttu-id="08150-122">Eliminare dal log eventi di Posta elettronica database gli eventi correlati agli elementi di posta trasferiti.</span><span class="sxs-lookup"><span data-stu-id="08150-122">Delete the events related to the transferred mail items from the Database Mail event log.</span></span>  
  
-   <span data-ttu-id="08150-123">Pianificare l'esecuzione periodica del processo.</span><span class="sxs-lookup"><span data-stu-id="08150-123">Schedule the job to run periodically.</span></span>  
 
  
## <a name="to-create-a-sql-server-agent-job"></a><span data-ttu-id="08150-124">Per creare un processo di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="08150-124">To create a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="08150-125">In Esplora oggetti, espandere [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, fare clic con il pulsante destro del mouse su **Processi**, quindi scegliere **Nuovo processo**.</span><span class="sxs-lookup"><span data-stu-id="08150-125">In Object Explorer, expand [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, right-click **Jobs**, and then click **New Job**.</span></span>  
  
2.  <span data-ttu-id="08150-126">Nella finestra di dialogo **Nuovo processo** digitare **Archive Database Mail** nella casella **Nome**.</span><span class="sxs-lookup"><span data-stu-id="08150-126">In the **New Job** dialog box, in the **Name** box, type **Archive Database Mail**.</span></span>  
  
3.  <span data-ttu-id="08150-127">Nella casella **Proprietario** confermare che il proprietario è un membro del ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="08150-127">In the **Owner** box, confirm that the owner is a member of the **sysadmin** fixed server role.</span></span>  
  
4.  <span data-ttu-id="08150-128">Nella casella **Categoria** fare clic su **Manutenzione database**.</span><span class="sxs-lookup"><span data-stu-id="08150-128">In the **Category** box, click the **Database Maintenance**.</span></span>  
  
5.  <span data-ttu-id="08150-129">Nella casella **Descrizione** digitare **Archiviazione messaggi di Posta elettronica database**, quindi fare clic su **Passaggi**.</span><span class="sxs-lookup"><span data-stu-id="08150-129">In the **Description** box, type **Archive Database Mail messages**, and then click **Steps**.</span></span>  
  
  
  
## <a name="to-create-a-step-to-archive-the-database-mail-messages"></a><span data-ttu-id="08150-130">Per creare un passaggio per l'archiviazione dei messaggi di Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="08150-130">To create a step to archive the Database Mail messages</span></span>  
  
1.  <span data-ttu-id="08150-131">Nella pagina **Passaggi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="08150-131">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="08150-132">Nella casella **Nome passaggio** digitare **Copy Database Mail Items**.</span><span class="sxs-lookup"><span data-stu-id="08150-132">In the **Step name** box, type **Copy Database Mail Items**.</span></span>  
  
3.  <span data-ttu-id="08150-133">Nella casella **Tipo** selezionare **Script Transact-SQL (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="08150-133">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="08150-134">Nella casella **Database** selezionare **msdb**.</span><span class="sxs-lookup"><span data-stu-id="08150-134">In the **Database** box, select **msdb**.</span></span>  
  
5.  <span data-ttu-id="08150-135">Nella casella **Comando** , digitare l'istruzione seguente per creare una tabella con il nome basato sul mese precedente e contenente le righe con una data anteriore all'inizio del mese corrente:</span><span class="sxs-lookup"><span data-stu-id="08150-135">In the **Command** box, type the following statement to create a table named after the previous month, containing rows older than the start of the current month:</span></span>  
  
    ```  
    DECLARE @LastMonth nvarchar(12);  
    DECLARE @CopyDate nvarchar(20) ;  
    DECLARE @CreateTable nvarchar(250) ;  
    SET @LastMonth = (SELECT CAST(DATEPART(yyyy,GETDATE()) AS CHAR(4)) + '_' + CAST(DATEPART(mm,GETDATE())-1 AS varchar(2))) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime))  
    SET @CreateTable = 'SELECT * INTO msdb.dbo.[DBMailArchive_' + @LastMonth + '] FROM sysmail_allitems WHERE send_request_date < ''' + @CopyDate +'''';  
    EXEC sp_executesql @CreateTable ;  
    ```  
  
6.  <span data-ttu-id="08150-136">Fare clic su **OK** per salvare il passaggio.</span><span class="sxs-lookup"><span data-stu-id="08150-136">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-create-a-step-to-archive-the-database-mail-attachments"></a><span data-ttu-id="08150-137">Per creare un passaggio per l'archiviazione degli allegati di Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="08150-137">To create a step to archive the Database Mail attachments</span></span>  
  
1.  <span data-ttu-id="08150-138">Nella pagina **Passaggi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="08150-138">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="08150-139">Nella casella **Nome passaggio** digitare **Copy Database Mail Attachments**.</span><span class="sxs-lookup"><span data-stu-id="08150-139">In the **Step name** box, type **Copy Database Mail Attachments**.</span></span>  
  
3.  <span data-ttu-id="08150-140">Nella casella **Tipo** selezionare **Script Transact-SQL (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="08150-140">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="08150-141">Nella casella **Database** selezionare **msdb**.</span><span class="sxs-lookup"><span data-stu-id="08150-141">In the **Database** box, select **msdb**.</span></span>  
  
5.  <span data-ttu-id="08150-142">Nella casella **Comando** , digitare la seguente istruzione per creare una tabella di allegati con il nome basato sul mese precedente e contenente gli allegati corrispondenti ai messaggi trasferiti nel passaggio precedente:</span><span class="sxs-lookup"><span data-stu-id="08150-142">In the **Command** box, type the following statement to create an attachments table named after the previous month, containing the attachments that correspond to the messages transferred in the previous step:</span></span>  
  
    ```  
    DECLARE @LastMonth nvarchar(12);  
    DECLARE @CopyDate nvarchar(20) ;  
    DECLARE @CreateTable nvarchar(250) ;  
    SET @LastMonth = (SELECT CAST(DATEPART(yyyy,GETDATE()) AS CHAR(4)) + '_' + CAST(DATEPART(mm,GETDATE())-1 AS varchar(2))) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime))  
    SET @CreateTable = 'SELECT * INTO msdb.dbo.[DBMailArchive_Attachments_' + @LastMonth + '] FROM sysmail_attachments   
     WHERE mailitem_id in (SELECT DISTINCT mailitem_id FROM [DBMailArchive_' + @LastMonth + '] )';  
    EXEC sp_executesql @CreateTable ;  
    ```  
  
6.  <span data-ttu-id="08150-143">Fare clic su **OK** per salvare il passaggio.</span><span class="sxs-lookup"><span data-stu-id="08150-143">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-create-a-step-to-archive-the-database-mail-log"></a><span data-ttu-id="08150-144">Per creare un passaggio per l'archiviazione del log di Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="08150-144">To create a step to archive the Database Mail log</span></span>  
  
1.  <span data-ttu-id="08150-145">Nella pagina **Passaggi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="08150-145">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="08150-146">Nella casella **Nome passaggio** digitare **Copy Database Mail Log**.</span><span class="sxs-lookup"><span data-stu-id="08150-146">In the **Step name** box, type **Copy Database Mail Log**.</span></span>  
  
3.  <span data-ttu-id="08150-147">Nella casella **Tipo** selezionare **Script Transact-SQL (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="08150-147">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="08150-148">Nella casella **Database** selezionare **msdb**.</span><span class="sxs-lookup"><span data-stu-id="08150-148">In the **Database** box, select **msdb**.</span></span>  
  
5.  <span data-ttu-id="08150-149">Nella casella **Comando** digitare l'istruzione seguente per creare una tabella del log con un nome basato sul mese precedente e contenente le voci del log che corrispondono ai messaggi trasferiti nel primo passaggio:</span><span class="sxs-lookup"><span data-stu-id="08150-149">In the **Command** box, type the following statement to create a log table named after the previous month, containing the log entries that correspond to the messages transferred in the earlier step:</span></span>  
  
    ```  
    DECLARE @LastMonth nvarchar(12);  
    DECLARE @CopyDate nvarchar(20) ;  
    DECLARE @CreateTable nvarchar(250) ;  
    SET @LastMonth = (SELECT CAST(DATEPART(yyyy,GETDATE()) AS CHAR(4)) + '_' + CAST(DATEPART(mm,GETDATE())-1 AS varchar(2))) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime))  
    SET @CreateTable = 'SELECT * INTO msdb.dbo.[DBMailArchive_Log_' + @LastMonth + '] FROM sysmail_Event_Log   
     WHERE mailitem_id in (SELECT DISTINCT mailitem_id FROM [DBMailArchive_' + @LastMonth + '] )';  
    EXEC sp_executesql @CreateTable ;  
    ```  
  
6.  <span data-ttu-id="08150-150">Fare clic su **OK** per salvare il passaggio.</span><span class="sxs-lookup"><span data-stu-id="08150-150">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-create-a-step-to-remove-the-archived-rows-from-database-mail"></a><span data-ttu-id="08150-151">Per creare un passaggio per la rimozione da Posta elettronica database delle righe archiviate</span><span class="sxs-lookup"><span data-stu-id="08150-151">To create a step to remove the archived rows from Database Mail</span></span>  
  
1.  <span data-ttu-id="08150-152">Nella pagina **Passaggi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="08150-152">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="08150-153">Nella casella **Nome passaggio** digitare **Remove rows from Database Mail**.</span><span class="sxs-lookup"><span data-stu-id="08150-153">In the **Step name** box, type **Remove rows from Database Mail**.</span></span>  
  
3.  <span data-ttu-id="08150-154">Nella casella **Tipo** selezionare **Script Transact-SQL (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="08150-154">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="08150-155">Nella casella **Database** selezionare **msdb**.</span><span class="sxs-lookup"><span data-stu-id="08150-155">In the **Database** box, select **msdb**.</span></span>  
  
5.  <span data-ttu-id="08150-156">Nella casella **Comando** digitare l'istruzione seguente per rimuovere dalle tabelle di Posta elettronica database le righe con una data anteriore al mese corrente:</span><span class="sxs-lookup"><span data-stu-id="08150-156">In the **Command** box, type the following statement to remove rows older than the current month from the Database Mail tables:</span></span>  
  
    ```  
    DECLARE @CopyDate nvarchar(20) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime)) ;  
    EXECUTE msdb.dbo.sysmail_delete_mailitems_sp @sent_before = @CopyDate ;  
    ```  
  
6.  <span data-ttu-id="08150-157">Fare clic su **OK** per salvare il passaggio.</span><span class="sxs-lookup"><span data-stu-id="08150-157">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-create-a-step-to-remove-the-archived-items-from-database-mail-event-log"></a><span data-ttu-id="08150-158">Per creare un passaggio per la rimozione dal log eventi di Posta elettronica database degli elementi archiviati</span><span class="sxs-lookup"><span data-stu-id="08150-158">To create a step to remove the archived items from Database Mail event log</span></span>  
  
1.  <span data-ttu-id="08150-159">Nella pagina **Passaggi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="08150-159">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="08150-160">Nella casella **Nome passaggio** digitare **Remove rows from Database Mail event log**.</span><span class="sxs-lookup"><span data-stu-id="08150-160">In the **Step Name** box type **Remove rows from Database Mail event log**.</span></span>  
  
3.  <span data-ttu-id="08150-161">Nella casella **Tipo** selezionare **Script Transact-SQL (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="08150-161">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="08150-162">Nella casella **Comando** digitare l'istruzione seguente per rimuovere dal log eventi di Posta elettronica database le righe con una data anteriore al mese corrente:</span><span class="sxs-lookup"><span data-stu-id="08150-162">In the **Command** box, type the following statement to remove rows older than the current month from the Database Mail event log:</span></span>  
  
    ```  
    DECLARE @CopyDate nvarchar(20) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime)) ;  
    EXECUTE msdb.dbo.sysmail_delete_log_sp @logged_before = @CopyDate ;  
    ```  
  
5.  <span data-ttu-id="08150-163">Fare clic su **OK** per salvare il passaggio.</span><span class="sxs-lookup"><span data-stu-id="08150-163">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-schedule-the-job-to-run-periodically"></a><span data-ttu-id="08150-164">Per pianificare l'esecuzione periodica del processo</span><span class="sxs-lookup"><span data-stu-id="08150-164">To schedule the job to run periodically</span></span>  
  
1.  <span data-ttu-id="08150-165">Nella finestra di dialogo **Nuovo processo** fare clic su **Pianificazioni**.</span><span class="sxs-lookup"><span data-stu-id="08150-165">In the **New Job** dialog box, click **Schedules**.</span></span>  
  
2.  <span data-ttu-id="08150-166">Nella pagina **Pianificazioni** fare clic su **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="08150-166">On the **Schedules** page, click **New**.</span></span>  
  
3.  <span data-ttu-id="08150-167">Nella casella **Nome** digitare **Archive Database Mail**.</span><span class="sxs-lookup"><span data-stu-id="08150-167">In the **Name** box, type **Archive Database Mail**.</span></span>  
  
4.  <span data-ttu-id="08150-168">Nella casella **Tipo pianificazione** selezionare **Periodica**.</span><span class="sxs-lookup"><span data-stu-id="08150-168">In the **Schedule type** box, select **Recurring**.</span></span>  
  
5.  <span data-ttu-id="08150-169">Nell'area **Frequenza** selezionare le opzioni che consentono di eseguire il processo periodicamente, ad esempio una volta al mese.</span><span class="sxs-lookup"><span data-stu-id="08150-169">In the **Frequency** area, select the options to run the job periodically, for example once every month.</span></span>  
  
6.  <span data-ttu-id="08150-170">Nell'area **Frequenza giornaliera** selezionare **Una sola volta alle \<time>** .</span><span class="sxs-lookup"><span data-stu-id="08150-170">In the **Daily frequency** area, select **Occurs once at \<time>**.</span></span>  
  
7.  <span data-ttu-id="08150-171">Verificare che le altre opzioni siano configurate come desiderato, quindi fare clic su **OK** per salvare la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="08150-171">Verify that the other options are configured as you wish, and then click **OK** to save the schedule.</span></span>  
  
8.  <span data-ttu-id="08150-172">Fare clic su **OK** per salvare il processo.</span><span class="sxs-lookup"><span data-stu-id="08150-172">Click **OK** to save the job.</span></span>  
  
  
  
  
