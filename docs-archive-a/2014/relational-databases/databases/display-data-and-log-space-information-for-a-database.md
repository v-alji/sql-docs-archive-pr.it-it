---
title: Visualizzare le informazioni sullo spazio allocato ai dati e ai log per un database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], space
- status information [SQL Server], space
- displaying space information
- disk space [SQL Server], displaying
- databases [SQL Server], space used
- viewing space information
- space allocation [SQL Server], displaying
- data space [SQL Server]
ms.assetid: c7b99463-4bab-4e9b-9217-fcb0898dc757
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1beb8cdedbc2b72eadeeb350ee1c3b6d16218205
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725875"
---
# <a name="display-data-and-log-space-information-for-a-database"></a><span data-ttu-id="fb398-102">Visualizzare le informazioni sullo spazio allocato ai dati e ai log per un database</span><span class="sxs-lookup"><span data-stu-id="fb398-102">Display Data and Log Space Information for a Database</span></span>
  <span data-ttu-id="fb398-103">In questo argomento si illustra come visualizzare le informazioni sullo spazio allocato ai dati e ai log per un database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb398-103">This topic describes how to display the data and log space information for a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="fb398-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="fb398-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="fb398-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="fb398-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="fb398-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="fb398-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="fb398-107">**Per visualizzare le informazioni sullo spazio allocato ai dati e ai log per un database utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="fb398-107">**To display data and log space information for a database, using:**</span></span>  
  
     [<span data-ttu-id="fb398-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fb398-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="fb398-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fb398-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fb398-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="fb398-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fb398-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="fb398-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fb398-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="fb398-112">Permissions</span></span>  
 <span data-ttu-id="fb398-113">L'autorizzazione per eseguire **sp_spaceused** è concessa al ruolo **public** .</span><span class="sxs-lookup"><span data-stu-id="fb398-113">Permission to execute **sp_spaceused** is granted to the **public** role.</span></span> <span data-ttu-id="fb398-114">Solo i membri del ruolo predefinito del database **db_owner** possono specificare il parametro **@updateusage** .</span><span class="sxs-lookup"><span data-stu-id="fb398-114">Only members of the **db_owner** fixed database role can specify the **@updateusage** parameter.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fb398-115">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fb398-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-display-data-and-log-space-information-for-a-database"></a><span data-ttu-id="fb398-116">Per visualizzare le informazioni sullo spazio allocato ai dati e ai log per un database</span><span class="sxs-lookup"><span data-stu-id="fb398-116">To display data and log space information for a database</span></span>  
  
1.  <span data-ttu-id="fb398-117">In Esplora oggetti connettersi a un'istanza del [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , quindi espanderla.</span><span class="sxs-lookup"><span data-stu-id="fb398-117">In Object Explorer, connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="fb398-118">Espandere **Database**.</span><span class="sxs-lookup"><span data-stu-id="fb398-118">Expand **Databases**.</span></span>  
  
3.  <span data-ttu-id="fb398-119">Fare clic con il pulsante destro del mouse su un database, scegliere **Report**, **Report standard**, quindi fare clic su **Utilizzo disco**.</span><span class="sxs-lookup"><span data-stu-id="fb398-119">Right-click a database, point to **Reports**, point to **Standard Reports,**, and then click **Disk Usage**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fb398-120">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fb398-120">Using Transact-SQL</span></span>  
  
#### <a name="to-display-data-and-log-space-information-for-a-database-by-using-sp_spaceused"></a><span data-ttu-id="fb398-121">Per visualizzare le informazioni sullo spazio allocato ai dati e ai log per un database utilizzando sp_spaceused</span><span class="sxs-lookup"><span data-stu-id="fb398-121">To display data and log space information for a database by using sp_spaceused</span></span>  
  
1.  <span data-ttu-id="fb398-122">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb398-122">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="fb398-123">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="fb398-123">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="fb398-124">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="fb398-124">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="fb398-125">In questo esempio viene usata la stored procedure di sistema [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) per fornire le informazioni sullo spazio su disco per la tabella `Vendor` e i relativi indici.</span><span class="sxs-lookup"><span data-stu-id="fb398-125">This example uses the [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) system stored procedure to report disk space information for the `Vendor` table and its indexes.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_spaceused N'Purchasing.Vendor';  
GO  
```  
  
#### <a name="to-display-data-and-log-space-information-for-a-database-by-querying-sysdatabase_files"></a><span data-ttu-id="fb398-126">Per visualizzare le informazioni sullo spazio allocato ai dati e ai log per un database eseguendo una query su sys.database_files</span><span class="sxs-lookup"><span data-stu-id="fb398-126">To display data and log space information for a database by querying sys.database_files</span></span>  
  
1.  <span data-ttu-id="fb398-127">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb398-127">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="fb398-128">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="fb398-128">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="fb398-129">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="fb398-129">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="fb398-130">In questo esempio si esegue una query sulla vista del catalogo [sys.database_files](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) per restituire informazioni specifiche sui file di dati e di log nel database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb398-130">This example queries the [sys.database_files](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) catalog view to return specific information about the data and log files in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT file_id, name, type_desc, physical_name, size, max_size  
FROM sys.database_files ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="fb398-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb398-131">See Also</span></span>  
 <span data-ttu-id="fb398-132">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fb398-132">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 <span data-ttu-id="fb398-133">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fb398-133">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span></span>  
 <span data-ttu-id="fb398-134">[sp_spaceused &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fb398-134">[sp_spaceused &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) </span></span>  
 <span data-ttu-id="fb398-135">[Aggiungere file di dati o file di log a un database](add-data-or-log-files-to-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="fb398-135">[Add Data or Log Files to a Database](add-data-or-log-files-to-a-database.md) </span></span>  
 [<span data-ttu-id="fb398-136">Eliminare file di dati o file di log da un database</span><span class="sxs-lookup"><span data-stu-id="fb398-136">Delete Data or Log Files from a Database</span></span>](delete-data-or-log-files-from-a-database.md)  
  
  
