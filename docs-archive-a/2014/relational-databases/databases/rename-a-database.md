---
title: Rinominare un database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server], renaming
- renaming databases
ms.assetid: 44c69d35-abcb-4da3-9370-5e0bc9a28496
author: stevestein
ms.author: sstein
ms.openlocfilehash: dd25a78e3d3b9be2e7191ce6ed3d6bdcbb0f9606
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627801"
---
# <a name="rename-a-database"></a><span data-ttu-id="1a0ea-102">Rinominare un database</span><span class="sxs-lookup"><span data-stu-id="1a0ea-102">Rename a Database</span></span>
  <span data-ttu-id="1a0ea-103">In questo argomento si illustra come rinominare un database definito dall'utente in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1a0ea-103">This topic describes how to rename a user-defined database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="1a0ea-104">Nel nome del database è possibile utilizzare qualsiasi carattere conforme alle regole per gli identificatori.</span><span class="sxs-lookup"><span data-stu-id="1a0ea-104">The name of the database can include any characters that follow the rules for identifiers.</span></span>  
  
 <span data-ttu-id="1a0ea-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="1a0ea-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1a0ea-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="1a0ea-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1a0ea-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="1a0ea-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="1a0ea-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="1a0ea-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1a0ea-109">**Per rinominare un database utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="1a0ea-109">**To rename a database, using:**</span></span>  
  
     [<span data-ttu-id="1a0ea-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1a0ea-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1a0ea-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1a0ea-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="1a0ea-112">**Completamento:**  [Dopo la ridenominazione di un database](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="1a0ea-112">**Follow Up:**  [After renaming a database](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1a0ea-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="1a0ea-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="1a0ea-114">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="1a0ea-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="1a0ea-115">I database di sistema non possono essere rinominati.</span><span class="sxs-lookup"><span data-stu-id="1a0ea-115">System databases cannot be renamed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1a0ea-116">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="1a0ea-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1a0ea-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="1a0ea-117">Permissions</span></span>  
 <span data-ttu-id="1a0ea-118">È richiesta l'autorizzazione ALTER per il database.</span><span class="sxs-lookup"><span data-stu-id="1a0ea-118">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1a0ea-119">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1a0ea-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-database"></a><span data-ttu-id="1a0ea-120">Per rinominare un database</span><span class="sxs-lookup"><span data-stu-id="1a0ea-120">To rename a database</span></span>  
  
1.  <span data-ttu-id="1a0ea-121">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], quindi espandere questa istanza.</span><span class="sxs-lookup"><span data-stu-id="1a0ea-121">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="1a0ea-122">Verificare che nessuno stia usando il database e quindi [impostare il database in modalità utente singolo](set-a-database-to-single-user-mode.md).</span><span class="sxs-lookup"><span data-stu-id="1a0ea-122">Make sure that no one is using the database, and then [set the database to single-user mode](set-a-database-to-single-user-mode.md).</span></span>  
  
3.  <span data-ttu-id="1a0ea-123">Espandere **Database**, fare clic con il pulsante destro del mouse sul database che si vuole rinominare, quindi scegliere **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="1a0ea-123">Expand **Databases**, right-click the database to rename, and then click **Rename**.</span></span>  
  
4.  <span data-ttu-id="1a0ea-124">Immettere il nuovo nome del database, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a0ea-124">Enter the new database name, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1a0ea-125">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1a0ea-125">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-a-database"></a><span data-ttu-id="1a0ea-126">Per rinominare un database</span><span class="sxs-lookup"><span data-stu-id="1a0ea-126">To rename a database</span></span>  
  
1.  <span data-ttu-id="1a0ea-127">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1a0ea-127">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1a0ea-128">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="1a0ea-128">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1a0ea-129">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="1a0ea-129">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="1a0ea-130">In questo esempio il nome del database `AdventureWorks2012` viene modificato in `Northwind`.</span><span class="sxs-lookup"><span data-stu-id="1a0ea-130">This example changes the name of the `AdventureWorks2012` database to `Northwind`.</span></span>  
  
```sql  
USE master;  
GO  
ALTER DATABASE AdventureWorks2012  
Modify Name = Northwind ;  
GO  
```  
  
###  <a name="TsqlExample"></a>   
##  <a name="follow-up-after-renaming-a-database"></a><a name="FollowUp"></a> <span data-ttu-id="1a0ea-131">Completamento: Dopo la rinomina di un database</span><span class="sxs-lookup"><span data-stu-id="1a0ea-131">Follow Up: After renaming a database</span></span>  
 <span data-ttu-id="1a0ea-132">Dopo aver rinominato un database, eseguire il backup del database **master** .</span><span class="sxs-lookup"><span data-stu-id="1a0ea-132">Back up the **master** database after you rename any database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a0ea-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a0ea-133">See Also</span></span>  
 <span data-ttu-id="1a0ea-134">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1a0ea-134">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="1a0ea-135">Identificatori del database</span><span class="sxs-lookup"><span data-stu-id="1a0ea-135">Database Identifiers</span></span>](database-identifiers.md)  
  
  
