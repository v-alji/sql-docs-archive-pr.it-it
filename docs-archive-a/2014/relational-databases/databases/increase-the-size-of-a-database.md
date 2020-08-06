---
title: Aumentare le dimensioni di un database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server], size
- increasing database size
- database size [SQL Server], increasing
- size [SQL Server], databases
ms.assetid: 14f4206d-3afa-4ba9-9849-23e81d63306d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 71dcb00b3f5525f7059fc54911baed929f763008
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725868"
---
# <a name="increase-the-size-of-a-database"></a><span data-ttu-id="7aff0-102">Aumentare le dimensioni di un database</span><span class="sxs-lookup"><span data-stu-id="7aff0-102">Increase the Size of a Database</span></span>
  <span data-ttu-id="7aff0-103">In questo argomento si descrive come aumentare le dimensioni di un database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7aff0-103">This topic describes how to increase the size of a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="7aff0-104">Il database viene espanso aumentando le dimensioni di un file di dati o di log o esistente oppure aggiungendo un nuovo file al database.</span><span class="sxs-lookup"><span data-stu-id="7aff0-104">The database is expanded by either increasing the size of an existing data or log file or by adding a new file to the database.</span></span>  
  
 <span data-ttu-id="7aff0-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="7aff0-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7aff0-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="7aff0-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7aff0-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="7aff0-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="7aff0-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="7aff0-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7aff0-109">**Per aumentare le dimensioni di un database tramite:**</span><span class="sxs-lookup"><span data-stu-id="7aff0-109">**To increase the size of a database, using:**</span></span>  
  
     [<span data-ttu-id="7aff0-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7aff0-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7aff0-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7aff0-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7aff0-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="7aff0-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="7aff0-113">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="7aff0-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="7aff0-114">Non è possibile aggiungere o rimuovere un file durante l'esecuzione di un'istruzione BACKUP.</span><span class="sxs-lookup"><span data-stu-id="7aff0-114">You cannot add or remove a file while a BACKUP statement is running.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7aff0-115">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="7aff0-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7aff0-116">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="7aff0-116">Permissions</span></span>  
 <span data-ttu-id="7aff0-117">È richiesta l'autorizzazione ALTER per il database.</span><span class="sxs-lookup"><span data-stu-id="7aff0-117">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7aff0-118">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7aff0-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-increase-the-size-of-a-database"></a><span data-ttu-id="7aff0-119">Per aumentare le dimensioni di un database</span><span class="sxs-lookup"><span data-stu-id="7aff0-119">To increase the size of a database</span></span>  
  
1.  <span data-ttu-id="7aff0-120">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], quindi espandere questa istanza.</span><span class="sxs-lookup"><span data-stu-id="7aff0-120">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="7aff0-121">Espandere **Database**, fare clic con il pulsante destro del mouse sul database di cui si vuole aumentare le dimensioni e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7aff0-121">Expand **Databases**, right-click the database to increase, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="7aff0-122">In **Proprietà database**selezionare la pagina **File** .</span><span class="sxs-lookup"><span data-stu-id="7aff0-122">In **Database Properties**, select the **Files** page.</span></span>  
  
4.  <span data-ttu-id="7aff0-123">Per aumentare le dimensioni di un file esistente, aumentare il valore nella colonna **Dimensioni iniziali (MB)** per il file.</span><span class="sxs-lookup"><span data-stu-id="7aff0-123">To increase the size of an existing file, increase the value in the **Initial Size (MB)** column for the file.</span></span> <span data-ttu-id="7aff0-124">È necessario aumentare le dimensioni del database almeno di un 1 megabyte.</span><span class="sxs-lookup"><span data-stu-id="7aff0-124">You must increase the size of the database by at least 1 megabyte.</span></span>  
  
5.  <span data-ttu-id="7aff0-125">Per aumentare le dimensioni del database aggiungendo un nuovo file, fare clic su **Aggiungi** , quindi immettere i valori per il nuovo file.</span><span class="sxs-lookup"><span data-stu-id="7aff0-125">To increase the size of the database by adding a new file, click **Add** and then enter the values for the new file.</span></span> <span data-ttu-id="7aff0-126">Per ulteriori informazioni, vedere [Aggiungere file di dati o file di log a un database](add-data-or-log-files-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="7aff0-126">For more information, see [Add Data or Log Files to a Database](add-data-or-log-files-to-a-database.md).</span></span>  
  
6.  <span data-ttu-id="7aff0-127">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7aff0-127">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7aff0-128">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7aff0-128">Using Transact-SQL</span></span>  
  
#### <a name="to-increase-the-size-of-a-database"></a><span data-ttu-id="7aff0-129">Per aumentare le dimensioni di un database</span><span class="sxs-lookup"><span data-stu-id="7aff0-129">To increase the size of a database</span></span>  
  
1.  <span data-ttu-id="7aff0-130">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7aff0-130">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7aff0-131">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="7aff0-131">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7aff0-132">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="7aff0-132">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="7aff0-133">In questo esempio si aumentano le dimensioni del file `test1dat3`.</span><span class="sxs-lookup"><span data-stu-id="7aff0-133">This example increases the size of the file `test1dat3`.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase5](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase5)]  
  
 <span data-ttu-id="7aff0-134">Per altri esempi, vedere [Opzioni per file e filegroup ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span><span class="sxs-lookup"><span data-stu-id="7aff0-134">For more examples, see [ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aff0-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7aff0-135">See Also</span></span>  
 <span data-ttu-id="7aff0-136">[Aggiungere file di dati o file di log a un database](add-data-or-log-files-to-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="7aff0-136">[Add Data or Log Files to a Database](add-data-or-log-files-to-a-database.md) </span></span>  
 [<span data-ttu-id="7aff0-137">Compattare un database</span><span class="sxs-lookup"><span data-stu-id="7aff0-137">Shrink a Database</span></span>](shrink-a-database.md)  
  
  
