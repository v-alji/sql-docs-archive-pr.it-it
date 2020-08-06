---
title: Aggiungere file di dati o file di log a un database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], files
- adding data files
- adding files
- adding log files
- file additions [SQL Server], steps
- files [SQL Server], adding
- data additions [SQL Server]
ms.assetid: 8ead516a-1334-4f40-84b2-509d0a8ffa45
author: stevestein
ms.author: sstein
ms.openlocfilehash: f72e00f9dab422652237b4b85579c544d0cda9fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725919"
---
# <a name="add-data-or-log-files-to-a-database"></a><span data-ttu-id="a045a-102">Aggiungere file di dati o file di log a un database</span><span class="sxs-lookup"><span data-stu-id="a045a-102">Add Data or Log Files to a Database</span></span>
  <span data-ttu-id="a045a-103">In questo argomento si descrive come aggiungere file di dati o di log a un database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a045a-103">This topic describes how to add data or log files to a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="a045a-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="a045a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a045a-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="a045a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a045a-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="a045a-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a045a-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a045a-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a045a-108">**Per aggiungere file di dati o file di log a un database utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="a045a-108">**To add data or log files to a database, using:**</span></span>  
  
     [<span data-ttu-id="a045a-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a045a-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a045a-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a045a-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a045a-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="a045a-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a045a-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="a045a-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="a045a-113">Non è possibile aggiungere o rimuovere un file durante l'esecuzione di un'istruzione BACKUP.</span><span class="sxs-lookup"><span data-stu-id="a045a-113">You cannot add or remove a file while a BACKUP statement is running.</span></span>  
  
-   <span data-ttu-id="a045a-114">Per ogni database è possibile specificare un massimo di 32.767 file e 32.767 filegroup.</span><span class="sxs-lookup"><span data-stu-id="a045a-114">A maximum of 32,767 files and 32,767 filegroups can be specified for each database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a045a-115">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a045a-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a045a-116">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="a045a-116">Permissions</span></span>  
 <span data-ttu-id="a045a-117">È richiesta l'autorizzazione ALTER per il database.</span><span class="sxs-lookup"><span data-stu-id="a045a-117">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a045a-118">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a045a-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-add-data-or-log-files-to-a-database"></a><span data-ttu-id="a045a-119">Per aggiungere file di dati o file di log a un database</span><span class="sxs-lookup"><span data-stu-id="a045a-119">To add data or log files to a database</span></span>  
  
1.  <span data-ttu-id="a045a-120">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere questa istanza.</span><span class="sxs-lookup"><span data-stu-id="a045a-120">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="a045a-121">Espandere **Databases**, fare clic con il pulsante destro del mouse sul database dal quale aggiungere i file e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a045a-121">Expand **Databases**, right-click the database from which to add the files, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="a045a-122">Nella finestra di dialogo **Proprietà database** selezionare la pagina **File** .</span><span class="sxs-lookup"><span data-stu-id="a045a-122">In the **Database Properties** dialog box, select the **Files** page.</span></span>  
  
4.  <span data-ttu-id="a045a-123">Per aggiungere un file di dati o di log delle transazioni, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a045a-123">To add a data or transaction log file, click **Add**.</span></span>  
  
5.  <span data-ttu-id="a045a-124">Nella griglia **File di database** immettere un nome logico per il file.</span><span class="sxs-lookup"><span data-stu-id="a045a-124">In the **Database files** grid, enter a logical name for the file.</span></span> <span data-ttu-id="a045a-125">Il nome deve essere univoco all'interno del database.</span><span class="sxs-lookup"><span data-stu-id="a045a-125">The file name must be unique within the database.</span></span>  
  
6.  <span data-ttu-id="a045a-126">Selezionare il tipo di file, dati oppure log.</span><span class="sxs-lookup"><span data-stu-id="a045a-126">Select the file type, data or log.</span></span>  
  
7.  <span data-ttu-id="a045a-127">Per un file di dati, selezionare il filegroup nel quale includere il file dall'elenco oppure selezionare **\<new filegroup>** per creare un nuovo filegroup.</span><span class="sxs-lookup"><span data-stu-id="a045a-127">For a data file, select the filegroup in which the file should be included from the list, or select **\<new filegroup>** to create a new filegroup.</span></span> <span data-ttu-id="a045a-128">Non è possibile inserire log delle transazioni nei filegroup.</span><span class="sxs-lookup"><span data-stu-id="a045a-128">Transaction logs cannot be put in filegroups.</span></span>  
  
8.  <span data-ttu-id="a045a-129">Specificare le dimensioni iniziali del file.</span><span class="sxs-lookup"><span data-stu-id="a045a-129">Specify the initial size of the file.</span></span> <span data-ttu-id="a045a-130">Creare file di dati delle dimensioni maggiori possibili, corrispondenti alla quantità massima di dati che si prevede di includere nel database.</span><span class="sxs-lookup"><span data-stu-id="a045a-130">Make the data file as large as possible, based on the maximum amount of data you expect in the database.</span></span>  
  
9. <span data-ttu-id="a045a-131">Per specificare le modalità di aumento delle dimensioni del file, fare clic su **...** nella colonna **Aumento automatico**.</span><span class="sxs-lookup"><span data-stu-id="a045a-131">To specify how the file should grow, click (**...**) in the **Autogrowth** column.</span></span> <span data-ttu-id="a045a-132">Selezionare una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="a045a-132">Select from the following options:</span></span>  
  
    1.  <span data-ttu-id="a045a-133">Per consentire l'aumento del file attualmente selezionato qualora sia necessario un maggiore spazio per i dati, selezionare la casella di controllo **Abilita aumento automatico dimensioni** e quindi selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a045a-133">To allow for the currently selected file to grow as more data space is required, select the **Enable Autogrowth** check box and then select from the following options:</span></span>  
  
    2.  <span data-ttu-id="a045a-134">Per fare in modo che le dimensioni del file aumentino a incrementi fissi, selezionare **In megabyte** e specificare un valore.</span><span class="sxs-lookup"><span data-stu-id="a045a-134">To specify that the file should grow by fixed increments, select **In Megabytes** and specify a value.</span></span>  
  
    3.  <span data-ttu-id="a045a-135">Per fare in modo che le dimensioni del file aumentino di una quantità pari a una percentuale delle dimensioni correnti del file, selezionare **In percentuale** e specificare un valore.</span><span class="sxs-lookup"><span data-stu-id="a045a-135">To specify that the file should grow by a percentage of the current file size, select **In Percent** and specify a value.</span></span>  
  
10. <span data-ttu-id="a045a-136">Per specificare il limite delle dimensioni del file, impostare le opzioni seguenti nel modo desiderato:</span><span class="sxs-lookup"><span data-stu-id="a045a-136">To specify the maximum file size limit, select from the following options:</span></span>  
  
    1.  <span data-ttu-id="a045a-137">Per specificare le dimensioni massime che possono essere raggiunte dal file, selezionare **Limite aumento in MB** e specificare un valore.</span><span class="sxs-lookup"><span data-stu-id="a045a-137">To specify the maximum size the file should be able to grow to, select **Restricted File Growth (MB)** and specify a value.</span></span>  
  
    2.  <span data-ttu-id="a045a-138">Per fare in modo che le dimensioni del file aumentino secondo le necessità, selezionare **Aumento illimitato**.</span><span class="sxs-lookup"><span data-stu-id="a045a-138">To allow for the file to grow as much as needed, select **Unrestricted File Growth**.</span></span>  
  
    3.  <span data-ttu-id="a045a-139">Per impedire che il file aumenti, deselezionare la casella di controllo **Abilita aumento automatico dimensioni** .</span><span class="sxs-lookup"><span data-stu-id="a045a-139">To prevent the file from growing, clear the **Enable Autogrowth** check box.</span></span> <span data-ttu-id="a045a-140">Le dimensioni del file non aumenteranno oltre il valore specificato nella colonna **Dimensioni iniziali (MB)** .</span><span class="sxs-lookup"><span data-stu-id="a045a-140">The size of the file will not grow beyond the value specified in the **Initial Size (MB)** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a045a-141">Le dimensioni massime del database sono comunque determinate dalla quantità di spazio disponibile su disco e dalle limitazioni previste dalla licenza della versione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in uso.</span><span class="sxs-lookup"><span data-stu-id="a045a-141">The maximum database size is determined by the amount of disk space available and the licensing limits determined by the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you are using.</span></span>  
  
11. <span data-ttu-id="a045a-142">Specificare il percorso per la posizione del file.</span><span class="sxs-lookup"><span data-stu-id="a045a-142">Specify the path for the file location.</span></span> <span data-ttu-id="a045a-143">È necessario che il percorso specificato sia esistente prima dell'aggiunta del file.</span><span class="sxs-lookup"><span data-stu-id="a045a-143">The specified path must exist before adding the file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a045a-144">Per impostazione predefinita, i dati e i log delle transazioni vengono inseriti sulla stessa unità e sullo stesso percorso per sistemi a unità singola, ma questa procedura potrebbe non essere ottimale per ambienti di produzione.</span><span class="sxs-lookup"><span data-stu-id="a045a-144">By default, the data and transaction logs are put on the same drive and path to accommodate single-disk systems, but may not be optimal for production environments.</span></span> <span data-ttu-id="a045a-145">Per altre informazioni, vedere [Database Files and Filegroups](database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="a045a-145">For more information, see [Database Files and Filegroups](database-files-and-filegroups.md).</span></span>  
  
12. <span data-ttu-id="a045a-146">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a045a-146">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a045a-147">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a045a-147">Using Transact-SQL</span></span>  
  
#### <a name="to-add-data-or-log-files-to-a-database"></a><span data-ttu-id="a045a-148">Per aggiungere file di dati o file di log a un database</span><span class="sxs-lookup"><span data-stu-id="a045a-148">To add data or log files to a database</span></span>  
  
1.  <span data-ttu-id="a045a-149">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a045a-149">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a045a-150">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="a045a-150">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a045a-151">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="a045a-151">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="a045a-152">Nell'esempio si aggiunge un filegroup con due file a un database.</span><span class="sxs-lookup"><span data-stu-id="a045a-152">The example adds a filegroup with two files to a database.</span></span> <span data-ttu-id="a045a-153">Inoltre, si crea il filegroup `Test1FG1` nel database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] e si aggiungono due file da 5 MB al filegroup.</span><span class="sxs-lookup"><span data-stu-id="a045a-153">The example creates the filegroup `Test1FG1` in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database and adds two 5-MB files to the filegroup.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase2](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase2)]  
  
 <span data-ttu-id="a045a-154">Per altri esempi, vedere [Opzioni per file e filegroup ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span><span class="sxs-lookup"><span data-stu-id="a045a-154">For more examples, see [ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a045a-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a045a-155">See Also</span></span>  
 <span data-ttu-id="a045a-156">[Database Files and Filegroups](database-files-and-filegroups.md) </span><span class="sxs-lookup"><span data-stu-id="a045a-156">[Database Files and Filegroups](database-files-and-filegroups.md) </span></span>  
 <span data-ttu-id="a045a-157">[Eliminare file di dati o file di log da un database](delete-data-or-log-files-from-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="a045a-157">[Delete Data or Log Files from a Database](delete-data-or-log-files-from-a-database.md) </span></span>  
 [<span data-ttu-id="a045a-158">Aumentare le dimensioni di un database</span><span class="sxs-lookup"><span data-stu-id="a045a-158">Increase the Size of a Database</span></span>](increase-the-size-of-a-database.md)  
  
  
