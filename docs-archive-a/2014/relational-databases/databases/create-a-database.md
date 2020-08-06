---
title: Creare un database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server], creating
- database creation [SQL Server], SQL Server Management Studio
- creating databases
ms.assetid: 4c4beea2-6cbc-4352-9db6-49ea8130bb64
author: stevestein
ms.author: sstein
ms.openlocfilehash: fe42e394482e3abf4d87c00c6e79ee84db6ba278
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627823"
---
# <a name="create-a-database"></a><span data-ttu-id="fad89-102">Creare un database</span><span class="sxs-lookup"><span data-stu-id="fad89-102">Create a Database</span></span>
  <span data-ttu-id="fad89-103">In questo argomento si illustra come creare un database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fad89-103">This topic describes how to create a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="fad89-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="fad89-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="fad89-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="fad89-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="fad89-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="fad89-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="fad89-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="fad89-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="fad89-108">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="fad89-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="fad89-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="fad89-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="fad89-110">**Per creare un database utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="fad89-110">**To create a database, using:**</span></span>  
  
     [<span data-ttu-id="fad89-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fad89-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="fad89-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fad89-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fad89-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="fad89-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="fad89-114">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="fad89-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="fad89-115">In un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]è possibile specificare al massimo 32.767 database.</span><span class="sxs-lookup"><span data-stu-id="fad89-115">A maximum of 32,767 databases can be specified on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="fad89-116">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="fad89-116">Prerequisites</span></span>  
  
-   <span data-ttu-id="fad89-117">L'istruzione CREATE DATABASE deve essere eseguita in modalità autocommit, la modalità predefinita per la gestione delle transazioni, e non è consentita in una transazione esplicita o implicita.</span><span class="sxs-lookup"><span data-stu-id="fad89-117">The CREATE DATABASE statement must run in autocommit mode (the default transaction management mode) and is not allowed in an explicit or implicit transaction.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="fad89-118">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="fad89-118">Recommendations</span></span>  
  
-   <span data-ttu-id="fad89-119">Il backup del database [master](master-database.md) dovrebbe essere eseguito ogni volta che si crea, modifica o si rimuove un database utente.</span><span class="sxs-lookup"><span data-stu-id="fad89-119">The [master](master-database.md) database should be backed up whenever a user database is created, modified, or dropped.</span></span>  
  
-   <span data-ttu-id="fad89-120">Durante la creazione di un database, creare file di dati di dimensioni corrispondenti alla quantità massima di dati che si prevede di includere nel database.</span><span class="sxs-lookup"><span data-stu-id="fad89-120">When you create a database, make the data files as large as possible based on the maximum amount of data you expect in the database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fad89-121">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="fad89-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fad89-122">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="fad89-122">Permissions</span></span>  
 <span data-ttu-id="fad89-123">È richiesta l'autorizzazione CREATE DATABASE per il database master oppure l'autorizzazione CREATE ANY DATABASE o ALTER ANY DATABASE.</span><span class="sxs-lookup"><span data-stu-id="fad89-123">Requires CREATE DATABASE permission in the master database, or requires CREATE ANY DATABASE, or ALTER ANY DATABASE permission.</span></span>  
  
 <span data-ttu-id="fad89-124">Per mantenere il controllo sull'utilizzo del disco per un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], l'autorizzazione per la creazione dei database è in genere limitata a pochi account di accesso.</span><span class="sxs-lookup"><span data-stu-id="fad89-124">To maintain control over disk use on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], permission to create databases is typically limited to a few login accounts.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fad89-125">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fad89-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-database"></a><span data-ttu-id="fad89-126">Per creare un database</span><span class="sxs-lookup"><span data-stu-id="fad89-126">To create a database</span></span>  
  
1.  <span data-ttu-id="fad89-127">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere questa istanza.</span><span class="sxs-lookup"><span data-stu-id="fad89-127">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="fad89-128">Fare clic con il pulsante destro del mouse su **Database**, quindi scegliere **Nuovo database**.</span><span class="sxs-lookup"><span data-stu-id="fad89-128">Right-click **Databases**, and then click **New Database**.</span></span>  
  
3.  <span data-ttu-id="fad89-129">In **Nuovo database**immettere un nome per il database.</span><span class="sxs-lookup"><span data-stu-id="fad89-129">In **New Database**, enter a database name.</span></span>  
  
4.  <span data-ttu-id="fad89-130">Per creare il database accettando tutti i valori predefiniti, scegliere **OK**. In caso contrario, continuare con i passaggi facoltativi seguenti.</span><span class="sxs-lookup"><span data-stu-id="fad89-130">To create the database by accepting all default values, click **OK**; otherwise, continue with the following optional steps.</span></span>  
  
5.  <span data-ttu-id="fad89-131">Per modificare il nome del proprietario, fare clic su ( **...** ) per selezionare un nome diverso.</span><span class="sxs-lookup"><span data-stu-id="fad89-131">To change the owner name, click (**...**) to select another owner.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fad89-132">L'opzione **Usa indicizzazione full-text** è sempre selezionata e visualizzata in grigio, in quanto, a partire da [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], tutti i database utente sono abilitati per la funzionalità full-text.</span><span class="sxs-lookup"><span data-stu-id="fad89-132">The **Use full-text indexing** option is always checked and dimmed because, beginning in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], all user databases are full-text enabled.</span></span>  
  
6.  <span data-ttu-id="fad89-133">Per modificare i valori predefiniti dei file di dati primario e di log delle transazioni, fare clic sulla cella appropriata nella griglia **File di database** , quindi immettere il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="fad89-133">To change the default values of the primary data and transaction log files, in the **Database files** grid, click the appropriate cell and enter the new value.</span></span> <span data-ttu-id="fad89-134">Per ulteriori informazioni, vedere [Aggiungere file di dati o file di log a un database](add-data-or-log-files-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="fad89-134">For more information, see [Add Data or Log Files to a Database](add-data-or-log-files-to-a-database.md).</span></span>  
  
7.  <span data-ttu-id="fad89-135">Per modificare le regole di confronto del database, selezionare la pagina **Opzioni** , quindi selezionare le regole di confronto nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="fad89-135">To change the collation of the database, select the **Options** page, and then select a collation from the list.</span></span>  
  
8.  <span data-ttu-id="fad89-136">Per modificare il modello di recupero, selezionare la pagina **Opzioni** , quindi selezionare un modello di recupero nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="fad89-136">To change the recovery model, select the **Options** page and select a recovery model from the list.</span></span>  
  
9. <span data-ttu-id="fad89-137">Per modificare le opzioni di database, selezionare la pagina **Opzioni** , quindi modificare le opzioni di database.</span><span class="sxs-lookup"><span data-stu-id="fad89-137">To change database options, select the **Options** page, and then modify the database options.</span></span> <span data-ttu-id="fad89-138">Per una descrizione di ogni opzione, vedere [Opzioni ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="fad89-138">For a description of each option, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
10. <span data-ttu-id="fad89-139">Per aggiungere un nuovo filegroup, fare clic sulla pagina **Filegroup** .</span><span class="sxs-lookup"><span data-stu-id="fad89-139">To add a new filegroup, click the **Filegroups** page.</span></span> <span data-ttu-id="fad89-140">Fare clic su **Aggiungi** , quindi immettere i valori per il filegroup.</span><span class="sxs-lookup"><span data-stu-id="fad89-140">Click **Add** and then enter the values for the filegroup.</span></span>  
  
11. <span data-ttu-id="fad89-141">Per aggiungere al database una proprietà estesa, selezionare la pagina **Proprietà estese** .</span><span class="sxs-lookup"><span data-stu-id="fad89-141">To add an extended property to the database, select the **Extended Properties** page.</span></span>  
  
    1.  <span data-ttu-id="fad89-142">Nella colonna **Nome** immettere un nome per la proprietà estesa.</span><span class="sxs-lookup"><span data-stu-id="fad89-142">In the **Name** column, enter a name for the extended property.</span></span>  
  
    2.  <span data-ttu-id="fad89-143">Nella colonna **Valore** immettere il testo della proprietà estesa.</span><span class="sxs-lookup"><span data-stu-id="fad89-143">In the **Value** column, enter the extended property text.</span></span> <span data-ttu-id="fad89-144">Immettere, ad esempio, una o più istruzioni tramite cui viene descritto il database.</span><span class="sxs-lookup"><span data-stu-id="fad89-144">For example, enter one or more statements that describe the database.</span></span>  
  
12. <span data-ttu-id="fad89-145">Per creare il database, scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="fad89-145">To create the database, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fad89-146">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fad89-146">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-database"></a><span data-ttu-id="fad89-147">Per creare un database</span><span class="sxs-lookup"><span data-stu-id="fad89-147">To create a database</span></span>  
  
1.  <span data-ttu-id="fad89-148">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fad89-148">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="fad89-149">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="fad89-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="fad89-150">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="fad89-150">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="fad89-151">In questo esempio si crea il database `Sales`.</span><span class="sxs-lookup"><span data-stu-id="fad89-151">This example creates the database `Sales`.</span></span> <span data-ttu-id="fad89-152">Dal momento che la parola chiave PRIMARY non è specificata, il primo file, cioè`Sales`_`dat`, corrisponde al file primario.</span><span class="sxs-lookup"><span data-stu-id="fad89-152">Because the keyword PRIMARY is not used, the first file (`Sales`_`dat`) becomes the primary file.</span></span> <span data-ttu-id="fad89-153">Poiché nel parametro SIZE non viene specificato il suffisso MB o KB per le dimensioni del file `Sales`\_`dat` , viene utilizzato MB e le dimensioni del file vengono allocate in megabyte.</span><span class="sxs-lookup"><span data-stu-id="fad89-153">Because neither MB nor KB is specified in the SIZE parameter for the `Sales`\_`dat` file, it uses MB and is allocated in megabytes.</span></span> <span data-ttu-id="fad89-154">Il backup del database `Sales`\_`log` vengono allocate in megabyte perché nel parametro `MB` è stato specificato in modo esplicito il suffisso `SIZE` .</span><span class="sxs-lookup"><span data-stu-id="fad89-154">The `Sales`\_`log` file is allocated in megabytes because the `MB` suffix is explicitly stated in the `SIZE` parameter.</span></span>  
  
```sql  
USE master ;  
GO  
CREATE DATABASE Sales  
ON   
( NAME = Sales_dat,  
    FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\saledat.mdf',  
    SIZE = 10,  
    MAXSIZE = 50,  
    FILEGROWTH = 5 )  
LOG ON  
( NAME = Sales_log,  
    FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\salelog.ldf',  
    SIZE = 5MB,  
    MAXSIZE = 25MB,  
    FILEGROWTH = 5MB ) ;  
GO  
```  
  
 <span data-ttu-id="fad89-155">Per altri esempi, vedere [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fad89-155">For more examples, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fad89-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fad89-156">See Also</span></span>  
 <span data-ttu-id="fad89-157">[Database Files and Filegroups](database-files-and-filegroups.md) </span><span class="sxs-lookup"><span data-stu-id="fad89-157">[Database Files and Filegroups](database-files-and-filegroups.md) </span></span>  
 <span data-ttu-id="fad89-158">[Collegamento e scollegamento di un database &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fad89-158">[Database Detach and Attach &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span></span>  
 <span data-ttu-id="fad89-159">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fad89-159">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="fad89-160">Aggiungere file di dati o file di log a un database</span><span class="sxs-lookup"><span data-stu-id="fad89-160">Add Data or Log Files to a Database</span></span>](add-data-or-log-files-to-a-database.md)  
  
  
