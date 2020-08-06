---
title: Collegare un database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.attachdatabase.f1
helpviewer_keywords:
- database attaching [SQL Server]
- attaching databases [SQL Server]
ms.assetid: b4efb0ae-cfe6-4d81-a4b4-6e4916885caa
author: stevestein
ms.author: sstein
ms.openlocfilehash: cb11b5c257007872e92d3f0a7eadb3e46b4969cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725912"
---
# <a name="attach-a-database"></a><span data-ttu-id="2f4b9-102">Collegare un database</span><span class="sxs-lookup"><span data-stu-id="2f4b9-102">Attach a Database</span></span>
  <span data-ttu-id="2f4b9-103">In questo argomento si illustra come collegare un database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f4b9-103">This topic describes how to attach a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="2f4b9-104">È possibile usare questa funzionalità per copiare, spostare o aggiornare un database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f4b9-104">You can use this feature to copy, move, or upgrade a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="2f4b9-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="2f4b9-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2f4b9-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="2f4b9-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2f4b9-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="2f4b9-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="2f4b9-108">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="2f4b9-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="2f4b9-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="2f4b9-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2f4b9-110">**Per collegare un database utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="2f4b9-110">**To Attach a Database by using:**</span></span>  
  
     [<span data-ttu-id="2f4b9-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2f4b9-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2f4b9-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2f4b9-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="2f4b9-113">**Completamento:**  [Dopo l'aggiornamento di un database](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="2f4b9-113">**Follow Up:**  [After Upgrading a Database](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2f4b9-114">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="2f4b9-114">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="2f4b9-115">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="2f4b9-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="2f4b9-116">Il database deve essere innanzitutto scollegato.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-116">The database must first be detached.</span></span> <span data-ttu-id="2f4b9-117">Se si tenta di collegare un database che non è stato scollegato, verrà restituito un errore.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-117">Attempting to attach a database that has not been detached will return an error.</span></span> <span data-ttu-id="2f4b9-118">Per altre informazioni, vedere [Scollegare un database](detach-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="2f4b9-118">For more information, see [Detach a Database](detach-a-database.md).</span></span>  
  
-   <span data-ttu-id="2f4b9-119">Durante il collegamento di un database è necessario che siano disponibili tutti i file di dati (file MDF e LDF).</span><span class="sxs-lookup"><span data-stu-id="2f4b9-119">When you attach a database, all data files (MDF and LDF files) must be available.</span></span> <span data-ttu-id="2f4b9-120">Se un file di dati si trova in un percorso diverso rispetto al momento della creazione o dell'ultimo collegamento del database, è necessario specificare il percorso corrente.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-120">If any data file has a different path from when the database was first created or last attached, you must specify the current path of the file.</span></span>  
  
-   <span data-ttu-id="2f4b9-121">Quando si collega un database, se i file MDF e LDF si trovano in directory diverse e uno dei percorsi include \\\\?\GlobalRoot, l'operazione avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-121">When you attach a database, if MDF and LDF files are located in different directories and one of the paths includes \\\\?\GlobalRoot, the operation will fail.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="2f4b9-122">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="2f4b9-122">Recommendations</span></span>  
<span data-ttu-id="2f4b9-123">Si consiglia di spostare i database utilizzando la `ALTER DATABASE` procedura di rilocazione pianificata, anziché utilizzare lo scollegamento e il collegamento.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-123">We recommend that you move databases by using the `ALTER DATABASE` planned relocation procedure, instead of using detach and attach.</span></span> <span data-ttu-id="2f4b9-124">Per altre informazioni, vedere [Spostare database utente](move-user-databases.md).</span><span class="sxs-lookup"><span data-stu-id="2f4b9-124">For more information, see [Move User Databases](move-user-databases.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2f4b9-125">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="2f4b9-125">Security</span></span>  
<span data-ttu-id="2f4b9-126">Le autorizzazioni di accesso ai file vengono impostate durante l'esecuzione di alcune operazioni del database, inclusi il collegamento e lo scollegamento.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-126">File access permissions are set during a number of database operations, including detaching or attaching a database.</span></span> <span data-ttu-id="2f4b9-127">Per informazioni sulle autorizzazioni per i file impostate quando un database viene collegato o scollegato, vedere [Protezione dei dati e dei file di log](https://technet.microsoft.com/library/ms189128.aspx) nella documentazione online di [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2f4b9-127">For information about file permissions that are set whenever a database is detached and attached, see [Securing Data and Log Files](https://technet.microsoft.com/library/ms189128.aspx) in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] Books Online.</span></span>  
  
<span data-ttu-id="2f4b9-128">È consigliabile evitare di collegare o ripristinare database provenienti da origini sconosciute o non attendibili.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-128">We recommend that you do not attach or restore databases from unknown or untrusted sources.</span></span> <span data-ttu-id="2f4b9-129">Tali database possono contenere codice dannoso che potrebbe eseguire codice [!INCLUDE[tsql](../../includes/tsql-md.md)] indesiderato o causare errori modificando lo schema o la struttura fisica di database.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-129">Such databases could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema or the physical database structure.</span></span> <span data-ttu-id="2f4b9-130">Prima di utilizzare un database da un'origine sconosciuta o non attendibile, eseguire [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) sul database in un server non di produzione ed esaminare il codice contenuto nel database, ad esempio le stored procedure o altro codice definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-130">Before you use a database from an unknown or untrusted source, run [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database on a nonproduction server and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span> <span data-ttu-id="2f4b9-131">Per altre informazioni sul collegamento di database e sulle modifiche apportate ai metadati in caso di collegamento di un database, vedere [Collegamento e scollegamento di un database &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2f4b9-131">For more information about attaching databases and information about changes that are made to metadata when you attach a database, see [Database Detach and Attach &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2f4b9-132">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="2f4b9-132">Permissions</span></span>  
<span data-ttu-id="2f4b9-133">È necessaria l'autorizzazione `CREATE DATABASE`, `CREATE ANY DATABASE` o `ALTER ANY DATABASE`.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-133">Requires `CREATE DATABASE`, `CREATE ANY DATABASE`, or `ALTER ANY DATABASE` permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2f4b9-134">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2f4b9-134">Using SQL Server Management Studio</span></span>  
  
### <a name="to-attach-a-database"></a><span data-ttu-id="2f4b9-135">Per collegare un database</span><span class="sxs-lookup"><span data-stu-id="2f4b9-135">To Attach a Database</span></span>  
  
1.  <span data-ttu-id="2f4b9-136">In Esplora oggetti di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], quindi espandere questa istanza.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-136">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="2f4b9-137">Fare clic con il pulsante destro del mouse su **Database** , quindi scegliere **Collega**.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-137">Right-click **Databases** and click **Attach**.</span></span>  
  
3.  <span data-ttu-id="2f4b9-138">Nella finestra di dialogo **Collega database** fare clic su **Aggiungi**per specificare il database da collegare, quindi nella finestra di dialogo **Individua file di database** selezionare l'unità disco in cui si trova il database ed espandere l'albero di directory per individuare e selezionare il file con estensione mdf del database, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2f4b9-138">In the **Attach Databases** dialog box, to specify the database to be attached, click **Add**; and in the **Locate Database Files** dialog box, select the disk drive where the database resides and expand the directory tree to find and select the .mdf file of the database; for example:</span></span>  
  
     `C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\AdventureWorks2012_Data.mdf`  
  
    > [!IMPORTANT]  
    > <span data-ttu-id="2f4b9-139">Se si tenta di selezionare un database già collegato, verrà generato un errore.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-139">Trying to select a database that is already attached generates an error.</span></span>  
  
     <span data-ttu-id="2f4b9-140">**Database da collegare**</span><span class="sxs-lookup"><span data-stu-id="2f4b9-140">**Databases to attach**</span></span>  
     <span data-ttu-id="2f4b9-141">Consente di visualizzare informazioni sui database selezionati.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-141">Displays information about the selected databases.</span></span>  
  
     \<no column header>  
     <span data-ttu-id="2f4b9-142">Consente di visualizzare un'icona che indica lo stato dell'operazione di collegamento.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-142">Displays an icon indicating the status of the attach operation.</span></span> <span data-ttu-id="2f4b9-143">Le icone possibili sono illustrate di seguito nella descrizione di **Stato** .</span><span class="sxs-lookup"><span data-stu-id="2f4b9-143">The possible icons are described in the **Status** description, below).</span></span>  
  
     <span data-ttu-id="2f4b9-144">**Percorso file MDF**</span><span class="sxs-lookup"><span data-stu-id="2f4b9-144">**MDF File Location**</span></span>  
     <span data-ttu-id="2f4b9-145">Consente di visualizzare il percorso e il nome del file MDF selezionato.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-145">Displays the path and file name of the selected MDF file.</span></span>  
  
     <span data-ttu-id="2f4b9-146">**Nome database**</span><span class="sxs-lookup"><span data-stu-id="2f4b9-146">**Database Name**</span></span>  
     <span data-ttu-id="2f4b9-147">Consente di visualizzare il nome del database.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-147">Displays the name of the database.</span></span>  
  
     <span data-ttu-id="2f4b9-148">**Collega come**</span><span class="sxs-lookup"><span data-stu-id="2f4b9-148">**Attach As**</span></span>  
     <span data-ttu-id="2f4b9-149">Facoltativamente, è possibile specificare un nome diverso per il database da collegare.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-149">Optionally, specifies a different name for the database to attach as.</span></span>  
  
     <span data-ttu-id="2f4b9-150">**Proprietario**</span><span class="sxs-lookup"><span data-stu-id="2f4b9-150">**Owner**</span></span>  
     <span data-ttu-id="2f4b9-151">Consente di visualizzare un elenco a discesa di possibili proprietari del database in cui è possibile selezionare un proprietario diverso.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-151">Provides a drop-down list of possible database owners from which you can optionally select a different owner.</span></span>  
  
     <span data-ttu-id="2f4b9-152">**Status**</span><span class="sxs-lookup"><span data-stu-id="2f4b9-152">**Status**</span></span>  
     <span data-ttu-id="2f4b9-153">Consente di visualizzare lo stato del base in base alla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-153">Displays the status of the database according to the following table.</span></span>  
  
    |<span data-ttu-id="2f4b9-154">Icona</span><span class="sxs-lookup"><span data-stu-id="2f4b9-154">Icon</span></span>|<span data-ttu-id="2f4b9-155">Testo Stato</span><span class="sxs-lookup"><span data-stu-id="2f4b9-155">Status text</span></span>|<span data-ttu-id="2f4b9-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2f4b9-156">Description</span></span>|  
    |----------|-----------------|-----------------|  
    |<span data-ttu-id="2f4b9-157">(Nessuna icona)</span><span class="sxs-lookup"><span data-stu-id="2f4b9-157">(No icon)</span></span>|<span data-ttu-id="2f4b9-158">(Nessun testo)</span><span class="sxs-lookup"><span data-stu-id="2f4b9-158">(No text)</span></span>|<span data-ttu-id="2f4b9-159">L'operazione di collegamento non è stata avviata o può essere sospesa per questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-159">Attach operation has not been started or may be pending for this object.</span></span> <span data-ttu-id="2f4b9-160">È il valore predefinito all'apertura della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-160">This is the default when the dialog is opened.</span></span>|  
    |<span data-ttu-id="2f4b9-161">Triangolo verde che punta a destra</span><span class="sxs-lookup"><span data-stu-id="2f4b9-161">Green, right-pointing triangle</span></span>|<span data-ttu-id="2f4b9-162">In corso</span><span class="sxs-lookup"><span data-stu-id="2f4b9-162">In progress</span></span>|<span data-ttu-id="2f4b9-163">L'operazione di collegamento è stata avviata ma non ancora completata.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-163">Attach operation has been started but it is not complete.</span></span>|  
    |<span data-ttu-id="2f4b9-164">Segno di spunta verde</span><span class="sxs-lookup"><span data-stu-id="2f4b9-164">Green check mark</span></span>|<span data-ttu-id="2f4b9-165">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="2f4b9-165">Success</span></span>|<span data-ttu-id="2f4b9-166">L'oggetto è stato collegato.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-166">The object has been attached successfully.</span></span>|  
    |<span data-ttu-id="2f4b9-167">Cerchio rosso con croce bianca</span><span class="sxs-lookup"><span data-stu-id="2f4b9-167">Red circle containing a white cross</span></span>|<span data-ttu-id="2f4b9-168">Errore</span><span class="sxs-lookup"><span data-stu-id="2f4b9-168">Error</span></span>|<span data-ttu-id="2f4b9-169">Si è verificato un errore durante l'operazione. Il collegamento non è stato completato.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-169">Attach operation encountered an error and did not complete successfully.</span></span>|  
    |<span data-ttu-id="2f4b9-170">Cerchio con due quadranti neri a destra e a sinistra e due quadranti bianchi in alto e in basso</span><span class="sxs-lookup"><span data-stu-id="2f4b9-170">Circle containing two black quadrants (on left and right) and two white quadrants (on top and bottom)</span></span>|<span data-ttu-id="2f4b9-171">Arrestato</span><span class="sxs-lookup"><span data-stu-id="2f4b9-171">Stopped</span></span>|<span data-ttu-id="2f4b9-172">L'operazione di collegamento non è stata completata perché l'utente ne ha arrestato l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-172">Attach operation was not completed successfully because the user stopped the operation.</span></span>|  
    |<span data-ttu-id="2f4b9-173">Cerchio con freccia curva che punta in senso antiorario.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-173">Circle containing a curved arrow pointing counter-clockwise</span></span>|<span data-ttu-id="2f4b9-174">È stato eseguito il rollback</span><span class="sxs-lookup"><span data-stu-id="2f4b9-174">Rolled Back</span></span>|<span data-ttu-id="2f4b9-175">L'operazione di collegamento è stata completata ma ne è stato eseguito il rollback a causa di un errore durante il collegamento di un altro oggetto.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-175">Attach operation was successful but it has been rolled back due to an error during attachment of another object.</span></span>|  
  
     <span data-ttu-id="2f4b9-176">**Messaggio**</span><span class="sxs-lookup"><span data-stu-id="2f4b9-176">**Message**</span></span>  
     <span data-ttu-id="2f4b9-177">Non viene visualizzato alcun messaggio oppure viene visualizzato il collegamento ipertestuale "Impossibile trovare il file".</span><span class="sxs-lookup"><span data-stu-id="2f4b9-177">Displays either a blank message or a "File not found" hyperlink.</span></span>  
  
     <span data-ttu-id="2f4b9-178">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="2f4b9-178">**Add**</span></span>  
     <span data-ttu-id="2f4b9-179">Consente di individuare i file principali del database necessari.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-179">Find the necessary main database files.</span></span> <span data-ttu-id="2f4b9-180">Se l'utente seleziona un file con estensione mdf, le informazioni appropriate vengono inserite automaticamente nei rispettivi campi della griglia **Database da collegare** .</span><span class="sxs-lookup"><span data-stu-id="2f4b9-180">When the user selects an .mdf file, applicable information is automatically filled in the respective fields of the **Databases to attach** grid.</span></span>  
  
     <span data-ttu-id="2f4b9-181">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="2f4b9-181">**Remove**</span></span>  
     <span data-ttu-id="2f4b9-182">Consente di rimuovere il file selezionato dalla griglia **Database da collegare** .</span><span class="sxs-lookup"><span data-stu-id="2f4b9-182">Removes the selected file from the **Databases to attach** grid.</span></span>  
  
     <span data-ttu-id="2f4b9-183">**"** *<nome_database>* **" dettagli database**</span><span class="sxs-lookup"><span data-stu-id="2f4b9-183">**"** *<database_name>* **" database details**</span></span>  
     <span data-ttu-id="2f4b9-184">Consente di visualizzare i nomi dei file da collegare.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-184">Displays the names of the files to be attached.</span></span> <span data-ttu-id="2f4b9-185">Per verificare o modificare il percorso di un file, fare clic sul pulsante **Sfoglia** ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="2f4b9-185">To verify or change the pathname of a file, click the **Browse** button (**...**).</span></span>  
  
    > [!NOTE]  
    > <span data-ttu-id="2f4b9-186">Se il file non esiste, nella colonna **Messaggio** verrà visualizzato il testo "File non trovato".</span><span class="sxs-lookup"><span data-stu-id="2f4b9-186">If a file does not exist, the **Message** column displays "Not found."</span></span> <span data-ttu-id="2f4b9-187">Se non rilevato, un file di log può trovarsi in un'altra directory o essere stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-187">If a log file is not found, it exists in another directory or has been deleted.</span></span> <span data-ttu-id="2f4b9-188">È necessario aggiornare il percorso del file nella griglia **Dettagli database** in modo che indichi la posizione corretta oppure rimuovere il file di log dalla griglia.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-188">You need to either update the file path in the **database details** grid to point to the correct location or remove the log file from the grid.</span></span> <span data-ttu-id="2f4b9-189">Se non viene rilevato un file di dati con estensione ndf, è necessario aggiornare il percorso nella griglia in modo che indichi la posizione corretta.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-189">If an .ndf data file is not found, you need to update its path in the grid to point to the correct location.</span></span>  
  
     <span data-ttu-id="2f4b9-190">**Nome file originale**</span><span class="sxs-lookup"><span data-stu-id="2f4b9-190">**Original File Name**</span></span>  
     <span data-ttu-id="2f4b9-191">Consente di visualizzare il nome del file collegato appartenente al database.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-191">Displays the name of the attached file belonging to the database.</span></span>  
  
     <span data-ttu-id="2f4b9-192">**Tipo di file**</span><span class="sxs-lookup"><span data-stu-id="2f4b9-192">**File Type**</span></span>  
     <span data-ttu-id="2f4b9-193">Indica il tipo di file, ovvero **Dati** o **Log**.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-193">Indicates the type of file, **Data** or **Log**.</span></span>  
  
     <span data-ttu-id="2f4b9-194">**Percorso file corrente**</span><span class="sxs-lookup"><span data-stu-id="2f4b9-194">**Current File Path**</span></span>  
     <span data-ttu-id="2f4b9-195">Consente di visualizzare il percorso del file di database selezionato.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-195">Displays the path to the selected database file.</span></span> <span data-ttu-id="2f4b9-196">Il percorso può essere modificato manualmente.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-196">The path can be edited manually.</span></span>  
  
     <span data-ttu-id="2f4b9-197">**Messaggio**</span><span class="sxs-lookup"><span data-stu-id="2f4b9-197">**Message**</span></span>  
     <span data-ttu-id="2f4b9-198">Non viene visualizzato alcun messaggio oppure viene visualizzato il collegamento ipertestuale**Impossibile trovare il file**.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-198">Displays either a blank message or a "**File not found**" hyperlink.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2f4b9-199">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2f4b9-199">Using Transact-SQL</span></span>  
  
### <a name="to-attach-a-database"></a><span data-ttu-id="2f4b9-200">Per collegare un database</span><span class="sxs-lookup"><span data-stu-id="2f4b9-200">To attach a database</span></span>  
  
1.  <span data-ttu-id="2f4b9-201">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f4b9-201">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2f4b9-202">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-202">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2f4b9-203">Utilizzare l'istruzione [create database](/sql/t-sql/statements/create-database-sql-server-transact-sql) con la `FOR ATTACH` chiusura.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-203">Use the [CREATE DATABASE](/sql/t-sql/statements/create-database-sql-server-transact-sql) statement with the `FOR ATTACH` close.</span></span>  
  
     <span data-ttu-id="2f4b9-204">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-204">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="2f4b9-205">In questo esempio si collegano i file del database [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] e si rinomina il database in `MyAdventureWorks`.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-205">This example attaches the files of the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database and renames the database to `MyAdventureWorks`.</span></span>  
  
    ```sql  
    CREATE DATABASE MyAdventureWorks   
        ON (FILENAME = 'C:\MySQLServer\AdventureWorks_Data.mdf'),   
        (FILENAME = 'C:\MySQLServer\AdventureWorks_Log.ldf')   
        FOR ATTACH;  
    ```  
  
    > [!NOTE]  
    > <span data-ttu-id="2f4b9-206">In alternativa, è possibile usare la stored procedure [sp_attach_db](/sql/relational-databases/system-stored-procedures/sp-attach-db-transact-sql) o [sp_attach_single_file_db](/sql/relational-databases/system-stored-procedures/sp-attach-single-file-db-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="2f4b9-206">Alternatively, you can use the [sp_attach_db](/sql/relational-databases/system-stored-procedures/sp-attach-db-transact-sql) or [sp_attach_single_file_db](/sql/relational-databases/system-stored-procedures/sp-attach-single-file-db-transact-sql) stored procedure.</span></span> <span data-ttu-id="2f4b9-207">Tuttavia, queste stored procedure verranno eliminate nelle versioni future di Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f4b9-207">However, these procedures will be removed in a future version of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2f4b9-208">Evitare di usare questa funzionalità in un nuovo progetto di sviluppo e prevedere interventi di modifica nelle applicazioni in cui è attualmente implementata.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-208">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span> <span data-ttu-id="2f4b9-209">È consigliabile utilizzare CREATE DATABASE... PER l'associazione.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-209">We recommend that you use CREATE DATABASE ... FOR ATTACH instead.</span></span>  
  
##  <a name="follow-up-after-upgrading-a-sql-server-database"></a><a name="FollowUp"></a> <span data-ttu-id="2f4b9-210">Completamento: Dopo l'aggiornamento di un database di SQL Server</span><span class="sxs-lookup"><span data-stu-id="2f4b9-210">Follow Up: After Upgrading a SQL Server Database</span></span>  
 <span data-ttu-id="2f4b9-211">OPO si aggiorna un database usando il metodo di connessione, il database diventa immediatamente disponibile e viene aggiornato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-211">fter you upgrade a database by using the attach method, the database becomes available immediately and is automatically upgraded.</span></span> <span data-ttu-id="2f4b9-212">Se il database include indici full-text, questi vengono importati, reimpostati o ricompilati dal processo di aggiornamento, a seconda dell'impostazione della proprietà del server **Opzione di aggiornamento full-text** .</span><span class="sxs-lookup"><span data-stu-id="2f4b9-212">If the database has full-text indexes, the upgrade process either imports, resets, or rebuilds them, depending on the setting of the **Full-Text Upgrade Option** server property.</span></span> <span data-ttu-id="2f4b9-213">Se l'opzione di aggiornamento è impostata su **Importa** o **Ricompila**, gli indici full-text non saranno disponibili durante l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-213">If the upgrade option is set to **Import** or **Rebuild**, the full-text indexes will be unavailable during the upgrade.</span></span> <span data-ttu-id="2f4b9-214">A seconda della quantità di dati indicizzati, l'importazione può richiedere diverse ore, mentre la ricompilazione può risultare dieci volte più lunga.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-214">Depending the amount of data being indexed, importing can take several hours, and rebuilding can take up to ten times longer.</span></span> <span data-ttu-id="2f4b9-215">Si noti inoltre che, quando l'opzione di aggiornamento è impostata su **Importa**e un catalogo full-text non è disponibile, gli indici full-text associati vengono ricompilati.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-215">Note also that when the upgrade option is set to **Import**, if a full-text catalog is not available, the associated full-text indexes are rebuilt.</span></span>  
  
<span data-ttu-id="2f4b9-216">Se il livello di compatibilità di un database utente è 100 o superiore prima dell'aggiornamento, rimane invariato dopo l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="2f4b9-216">If the compatibility level of a user database is 100 or higher before upgrade, it remains the same after upgrade.</span></span> <span data-ttu-id="2f4b9-217">Se il livello di compatibilità è 90 prima dell'aggiornamento, nel database aggiornato viene impostato su 100, ovvero sul livello di compatibilità supportato più basso in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f4b9-217">If the compatibility level is 90 before upgrade, in the upgraded database, the compatibility level is set to 100, which is the lowest supported compatibility level in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="2f4b9-218">Per altre informazioni, vedere [Livello di compatibilità ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span><span class="sxs-lookup"><span data-stu-id="2f4b9-218">For more information, see [ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f4b9-219">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f4b9-219">See Also</span></span>  
 <span data-ttu-id="2f4b9-220">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2f4b9-220">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="2f4b9-221">Scollegamento di un database</span><span class="sxs-lookup"><span data-stu-id="2f4b9-221">Detach a Database</span></span>](detach-a-database.md)  
  
  
