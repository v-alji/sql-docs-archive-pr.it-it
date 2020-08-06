---
title: Scollegamento e collegamento di database DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 830e33bc-dd15-4f8e-a4ac-d8634b78fe45
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3bcac9d1f53b10cf6356b878ce4006f66c198d99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625568"
---
# <a name="detaching-and-attaching-dqs-databases"></a><span data-ttu-id="894f8-102">Scollegamento e collegamento di database DQS</span><span class="sxs-lookup"><span data-stu-id="894f8-102">Detaching and Attaching DQS Databases</span></span>
  <span data-ttu-id="894f8-103">In questo argomento viene descritto come scollegare e collegare i database DQS.</span><span class="sxs-lookup"><span data-stu-id="894f8-103">This topic describes how to detach and attach the DQS databases.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="894f8-104">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="894f8-104">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Limitations"></a> <span data-ttu-id="894f8-105">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="894f8-105">Limitations and Restrictions</span></span>  
 <span data-ttu-id="894f8-106">Per un elenco delle limitazioni e restrizioni, vedere [Collegamento e scollegamento di un database &#40;SQL Server&#41;](../relational-databases/databases/database-detach-and-attach-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="894f8-106">For a list of limitations and restrictions, see [Database Detach and Attach &#40;SQL Server&#41;](../relational-databases/databases/database-detach-and-attach-sql-server.md).</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="894f8-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="894f8-107">Prerequisites</span></span>  
  
-   <span data-ttu-id="894f8-108">Assicurarsi che non vi siano attività o processi in esecuzione in DQS.</span><span class="sxs-lookup"><span data-stu-id="894f8-108">Ensure that there are no running activities or processes in DQS.</span></span> <span data-ttu-id="894f8-109">È possibile verificare utilizzando la schermata **Monitoraggio attività** .</span><span class="sxs-lookup"><span data-stu-id="894f8-109">This can be verified using the **Activity Monitoring** screen.</span></span> <span data-ttu-id="894f8-110">Per informazioni dettagliate su funzionamento di questa schermata, vedere [Monitor DQS Activities](../../2014/data-quality-services/monitor-dqs-activities.md).</span><span class="sxs-lookup"><span data-stu-id="894f8-110">For detailed information about working in this screen, see [Monitor DQS Activities](../../2014/data-quality-services/monitor-dqs-activities.md).</span></span>  
  
-   <span data-ttu-id="894f8-111">Assicurarsi che non vi siano utenti connessi al [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="894f8-111">Ensure that there are no users logged on the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="894f8-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="894f8-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="894f8-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="894f8-113">Permissions</span></span>  
  
-   <span data-ttu-id="894f8-114">È necessario che l'account utente di Windows sia membro del ruolo predefinito del server db_owner nell'istanza di SQL Server per scollegare i database DQS.</span><span class="sxs-lookup"><span data-stu-id="894f8-114">Your Windows user account must be a member of the db_owner fixed server role in the SQL Server instance to detach DQS databases.</span></span>  
  
-   <span data-ttu-id="894f8-115">L'account utente di Windows deve disporre dell'autorizzazione CREATE DATABASE, CREATE ANY DATABASE o ALTER ANY DATABASE per collegare un database.</span><span class="sxs-lookup"><span data-stu-id="894f8-115">Your Windows user account must have CREATE DATABASE, CREATE ANY DATABASE, or ALTER ANY DATABASE permission to attach a database.</span></span>  
  
-   <span data-ttu-id="894f8-116">È necessario disporre del ruolo dqs_administrator sul database DQS_MAIN per interrompere qualsiasi attività in esecuzione o arrestare processi in corso in DQS.</span><span class="sxs-lookup"><span data-stu-id="894f8-116">You must have the dqs_administrator role on the DQS_MAIN database to terminate any running activities or stop any running processes in DQS.</span></span>  
  
##  <a name="detach-dqs-databases"></a><a name="Detach"></a><span data-ttu-id="894f8-117">Scollega database DQS</span><span class="sxs-lookup"><span data-stu-id="894f8-117">Detach DQS Databases</span></span>  
 <span data-ttu-id="894f8-118">Quando si scollega un database DQS utilizzando SQL Server Management Studio, i file scollegati non vengono eliminati dal computer e possono essere ricollegati alla stessa istanza di SQL Server o possono essere spostati in un altro server dove vengono collegati.</span><span class="sxs-lookup"><span data-stu-id="894f8-118">When you detach a DQS database using SQL Server Management Studio, the detached files remain on your computer, and can be reattached to the same SQL Server instance or can be can be moved to another server and attached there.</span></span> <span data-ttu-id="894f8-119">I file del database DQS sono in genere disponibili nel seguente percorso nel computer Data Quality Services: C:\Programmi\Microsoft SQL Server\MSSQL12. *<Instance_Name>* \Mssql\Data.</span><span class="sxs-lookup"><span data-stu-id="894f8-119">The DQS database files are typically available at the following location on your Data Quality Services computer: C:\Program Files\Microsoft SQL Server\MSSQL12.*<Instance_Name>* \MSSQL\DATA.</span></span>  
  
1.  <span data-ttu-id="894f8-120">Avviare Microsoft SQL Server Management Studio e connettersi all'istanza di SQL Server appropriata.</span><span class="sxs-lookup"><span data-stu-id="894f8-120">Start Microsoft SQL Server Management Studio, and connect to the appropriate SQL Server instance.</span></span>  
  
2.  <span data-ttu-id="894f8-121">In Esplora oggetti espandere il nodo **Database** .</span><span class="sxs-lookup"><span data-stu-id="894f8-121">In Object Explorer, expand the **Databases** node.</span></span>  
  
3.  <span data-ttu-id="894f8-122">Fare clic con il pulsante destro del mouse sul database **DQS_MAIN** , scegliere **Attività**, quindi fare clic su **Scollega**.</span><span class="sxs-lookup"><span data-stu-id="894f8-122">Right-click the **DQS_MAIN** database, point to **Tasks**, and then click **Detach**.</span></span> <span data-ttu-id="894f8-123">Verrà visualizzata la finestra di dialogo **Scollega database** .</span><span class="sxs-lookup"><span data-stu-id="894f8-123">The **Detach Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="894f8-124">Selezionare la casella di controllo nella colonna **Rilascia** e fare clic su **OK** per scollegare il database DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="894f8-124">Select the check box under the **Drop** column, and click **OK** to detach the DQS_MAIN database.</span></span>  
  
5.  <span data-ttu-id="894f8-125">Ripetere i passaggi 3 e 4 con i database DQS_PROJECTS e DQS_STAGING_DATA per scollegarli.</span><span class="sxs-lookup"><span data-stu-id="894f8-125">Repeat steps 3 and 4 with the DQS_PROJECTS and DQS_STAGING_DATA databases to detach them.</span></span>  
  
 <span data-ttu-id="894f8-126">È inoltre possibile scollegare i database DQS tramite le istruzioni Transact-SQL utilizzando la stored procedure sp_detach_db.</span><span class="sxs-lookup"><span data-stu-id="894f8-126">You can also detach DQS databases using the Transact-SQL statements by using the sp_detach_db stored procedure.</span></span> <span data-ttu-id="894f8-127">Per ulteriori informazioni sullo scollegamento di database tramite istruzioni Transact-SQL, vedere [Using Transact-SQL](../relational-databases/databases/detach-a-database.md#TsqlProcedure) in [Detach a Database](../relational-databases/databases/detach-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="894f8-127">For more information about detaching databases using Transact-SQL statements, see [Using Transact-SQL](../relational-databases/databases/detach-a-database.md#TsqlProcedure) in [Detach a Database](../relational-databases/databases/detach-a-database.md).</span></span>  
  
##  <a name="attach-dqs-databases"></a><a name="Attach"></a><span data-ttu-id="894f8-128">Connetti database DQS</span><span class="sxs-lookup"><span data-stu-id="894f8-128">Attach DQS Databases</span></span>  
 <span data-ttu-id="894f8-129">Utilizzare le istruzioni seguenti per collegare un database DQS alla stessa istanza di SQL Server, da cui è stato scollegato, o a un'istanza di SQL Server diversa in cui è installato [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="894f8-129">Use the following instructions to attach a DQS database to the same SQL Server instance (from where you detached) or a different SQL Server instance where [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] is installed.</span></span>  
  
1.  <span data-ttu-id="894f8-130">Avviare Microsoft SQL Server Management Studio e connettersi all'istanza di SQL Server appropriata.</span><span class="sxs-lookup"><span data-stu-id="894f8-130">Start Microsoft SQL Server Management Studio, and connect to the appropriate SQL Server instance.</span></span>  
  
2.  <span data-ttu-id="894f8-131">In Esplora oggetti fare clic con il pulsante destro del mouse su **Database**, quindi fare clic su **Collega**.</span><span class="sxs-lookup"><span data-stu-id="894f8-131">In Object Explorer, right-click **Databases**, and then click **Attach**.</span></span> <span data-ttu-id="894f8-132">Verrà visualizzata la finestra di dialogo **Collega database** .</span><span class="sxs-lookup"><span data-stu-id="894f8-132">The **Attach Databases** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="894f8-133">Per specificare il database da collegare, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="894f8-133">To specify the database to be attached, click **Add**.</span></span> <span data-ttu-id="894f8-134">Verrà visualizzata la finestra di dialogo **Individua file di database** .</span><span class="sxs-lookup"><span data-stu-id="894f8-134">The **Locate Database Files** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="894f8-135">Selezionare l'unità disco in cui si trova il database ed espandere l'albero di directory per individuare e selezionare il file con estensione mdf del database.</span><span class="sxs-lookup"><span data-stu-id="894f8-135">Select the disk drive where the database resides and expand the directory tree to find and select the .mdf file of the database.</span></span> <span data-ttu-id="894f8-136">Ad esempio, per il database DQS_MAIN:</span><span class="sxs-lookup"><span data-stu-id="894f8-136">For example, for the DQS_MAIN database:</span></span>  
  
    ```  
    C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\DQS_MAIN.mdf  
    ```  
  
5.  <span data-ttu-id="894f8-137">Nel riquadro (inferiore) **Dettagli database** vengono visualizzati i nomi dei file da collegare.</span><span class="sxs-lookup"><span data-stu-id="894f8-137">The **database details** (lower) pane displays the names of the files to be attached.</span></span> <span data-ttu-id="894f8-138">Per verificare o modificare il percorso di un file, fare clic sul pulsante **Sfoglia** ( ... ).</span><span class="sxs-lookup"><span data-stu-id="894f8-138">To verify or change the pathname of a file, click the **Browse** button (...).</span></span>  
  
6.  <span data-ttu-id="894f8-139">Fare clic su **OK** per collegare il database DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="894f8-139">Click **OK** to attach the DQS_MAIN database.</span></span>  
  
7.  <span data-ttu-id="894f8-140">Ripetere i passaggi da 2 a 6 per il collegamento dei database DQS_PROJECTS e DQS_STAGING_DATA.</span><span class="sxs-lookup"><span data-stu-id="894f8-140">Repeat steps 2-6 for the DQS_PROJECTS and DQS_STAGING_DATA databases to attach them.</span></span>  
  
8.  <span data-ttu-id="894f8-141">È inoltre necessario eseguire le istruzioni Transact-SQL nel passaggio successivo al ripristino del database DQS_MAIN; in caso contrario, viene visualizzato un messaggio di errore quando si tenta una connessione al server Data Quality tramite l'applicazione client Data Quality e la connessione non può essere stabilita.</span><span class="sxs-lookup"><span data-stu-id="894f8-141">You must also run the Transact-SQL statements in the next step after restoring the DQS_MAIN database otherwise an error message is displayed when you try to connect to Data Quality Server by using the Data Quality Client application, and you cannot connect.</span></span> <span data-ttu-id="894f8-142">Tuttavia, non è necessario effettuare i passaggi 9 e 10 se è stato aggiunto solo il database DQS_STAGING_DATA o DQS_PROJECTS e non DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="894f8-142">However, you do not need to perform steps 9 and 10 if you have just attached the DQS_PROJECTS or DQS_STAGING_DATA database, and not DQS_MAIN.</span></span>  
  
     <span data-ttu-id="894f8-143">Per eseguire le istruzioni Transact-SQL, in Esplora oggetti fare clic con il pulsante destro del mouse sul server, quindi scegliere **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="894f8-143">To run the Transact-SQL statements, in Object Explorer, right-click the server, and then click **New Query**.</span></span>  
  
9. <span data-ttu-id="894f8-144">Nella finestra dell'editor di query copiare le istruzioni SQL seguenti:</span><span class="sxs-lookup"><span data-stu-id="894f8-144">In the Query Editor window, copy the following SQL statements:</span></span>  
  
    ```sql  
    ALTER DATABASE [DQS_MAIN] SET TRUSTWORTHY ON;  
    EXEC sp_configure 'clr enabled', 1;  
    RECONFIGURE WITH OVERRIDE  
    ALTER DATABASE [DQS_MAIN] SET ENABLE_BROKER  
    ALTER AUTHORIZATION ON DATABASE::[DQS_MAIN] TO [##MS_dqs_db_owner_login##]  
    ALTER AUTHORIZATION ON DATABASE::[DQS_PROJECTS] TO [##MS_dqs_db_owner_login##]  
    ```  
  
10. <span data-ttu-id="894f8-145">Premere F5 per eseguire le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="894f8-145">Press F5 to execute the statements.</span></span> <span data-ttu-id="894f8-146">Esaminare il riquadro dei risultati per verificare che le istruzioni siano state eseguite correttamente.</span><span class="sxs-lookup"><span data-stu-id="894f8-146">Check the Results pane to verify that the statements have executed successfully.</span></span> <span data-ttu-id="894f8-147">Verrà visualizzato il messaggio seguente: `Configuration option 'clr enabled' changed from 1 to 1. Run the RECONFIGURE statement to install.`</span><span class="sxs-lookup"><span data-stu-id="894f8-147">You will see the following message: `Configuration option 'clr enabled' changed from 1 to 1. Run the RECONFIGURE statement to install.`</span></span>  
  
11. <span data-ttu-id="894f8-148">Connettersi al server Data Quality utilizzando il client Data Quality per verificare se è possibile stabilire correttamente la connessione.</span><span class="sxs-lookup"><span data-stu-id="894f8-148">Connect to the Data Quality Server using the Data Quality Client to verify if you can connect successfully.</span></span>  
  
 <span data-ttu-id="894f8-149">È inoltre possibile collegare i database DQS utilizzando le istruzioni Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="894f8-149">You can also attach DQS databases using the Transact-SQL statements.</span></span> <span data-ttu-id="894f8-150">Per ulteriori informazioni sul collegamento di database tramite istruzioni Transact-SQL, vedere [Using Transact-SQL](../relational-databases/databases/attach-a-database.md#TsqlProcedure) in [Attach a Database](../relational-databases/databases/attach-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="894f8-150">For more information about attaching databases using Transact-SQL statements, see [Using Transact-SQL](../relational-databases/databases/attach-a-database.md#TsqlProcedure) in [Attach a Database](../relational-databases/databases/attach-a-database.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="894f8-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="894f8-151">See Also</span></span>  
 [<span data-ttu-id="894f8-152">Manage DQS Databases</span><span class="sxs-lookup"><span data-stu-id="894f8-152">Manage DQS Databases</span></span>](../../2014/data-quality-services/manage-dqs-databases.md)  
  
  
