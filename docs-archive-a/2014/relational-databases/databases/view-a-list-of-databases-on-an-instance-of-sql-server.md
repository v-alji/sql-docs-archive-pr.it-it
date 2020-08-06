---
title: Visualizzare un elenco di database in un'istanza di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- current databases
- databases currently on server [SQL Server]
- database list [SQL Server]
- viewing database list
- displaying database list
- databases [SQL Server], viewing
- servers [SQL Server], databases listed on
- listing databases
ms.assetid: 7ee7a789-db36-4be9-8a0e-0362a1e152dd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 47283fa9065a0b9d6238dab804094d9a65d17897
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724752"
---
# <a name="view-a-list-of-databases-on-an-instance-of-sql-server"></a><span data-ttu-id="dc38d-102">Visualizzare un elenco di database in un'istanza di SQL Server</span><span class="sxs-lookup"><span data-stu-id="dc38d-102">View a List of Databases on an Instance of SQL Server</span></span>
  <span data-ttu-id="dc38d-103">In questo argomento si illustra come visualizzare un elenco di database in un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc38d-103">This topic describes how to view a list of databases on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="dc38d-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="dc38d-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="dc38d-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="dc38d-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="dc38d-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="dc38d-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="dc38d-107">**Per visualizzare un elenco di database in un'istanza di SQL Server utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="dc38d-107">**To view a list of databases on an instance of SQL Server, using:**</span></span>  
  
     [<span data-ttu-id="dc38d-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dc38d-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="dc38d-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dc38d-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="dc38d-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="dc38d-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dc38d-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="dc38d-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="dc38d-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="dc38d-112">Permissions</span></span>  
 <span data-ttu-id="dc38d-113">Se il chiamante di **sys.databases** non è il proprietario del database e il database non è **master** o **tempdb**, le autorizzazioni minime necessarie per visualizzare la riga corrispondente sono ALTER ANY DATABASE o VIEW ANY DATABASE a livello di server oppure l'autorizzazione CREATE DATABASE nel database **master** .</span><span class="sxs-lookup"><span data-stu-id="dc38d-113">If the caller of **sys.databases** is not the owner of the database and the database is not **master** or **tempdb**, the minimum permissions required to see the corresponding row are ALTER ANY DATABASE or VIEW ANY DATABASE server-level permission, or CREATE DATABASE permission in the **master** database.</span></span> <span data-ttu-id="dc38d-114">Il database a cui è connesso il chiamante può essere sempre visualizzato in **sys.databases**.</span><span class="sxs-lookup"><span data-stu-id="dc38d-114">The database to which the caller is connected can always be viewed in **sys.databases**.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="dc38d-115">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dc38d-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-a-list-of-databases-on-an-instance-of-sql-server"></a><span data-ttu-id="dc38d-116">Per visualizzare un elenco di database in un'istanza di SQL Server</span><span class="sxs-lookup"><span data-stu-id="dc38d-116">To view a list of databases on an instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="dc38d-117">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], quindi espandere questa istanza.</span><span class="sxs-lookup"><span data-stu-id="dc38d-117">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="dc38d-118">Per visualizzare un elenco di tutti i database dell'istanza, espandere **Database**.</span><span class="sxs-lookup"><span data-stu-id="dc38d-118">To see a list of all databases on the instance, expand **Databases**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="dc38d-119">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dc38d-119">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-list-of-databases-on-an-instance-of-sql-server"></a><span data-ttu-id="dc38d-120">Per visualizzare un elenco di database in un'istanza di SQL Server</span><span class="sxs-lookup"><span data-stu-id="dc38d-120">To view a list of databases on an instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="dc38d-121">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc38d-121">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="dc38d-122">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="dc38d-122">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="dc38d-123">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="dc38d-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="dc38d-124">In questo esempio viene restituito un elenco di database nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc38d-124">This example returns a list of databases on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="dc38d-125">Nell'elenco sono inclusi i nomi dei database, i relativi ID di database, nonché le date di creazione dei database.</span><span class="sxs-lookup"><span data-stu-id="dc38d-125">The list includes the names of the databases, their database IDs, and the dates when the databases were created.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT name, database_id, create_date  
FROM sys.databases ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="dc38d-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc38d-126">See Also</span></span>  
 <span data-ttu-id="dc38d-127">[Viste del catalogo di database e file &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/databases-and-files-catalog-views-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dc38d-127">[Databases and Files Catalog Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/databases-and-files-catalog-views-transact-sql) </span></span>  
 [<span data-ttu-id="dc38d-128">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dc38d-128">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
