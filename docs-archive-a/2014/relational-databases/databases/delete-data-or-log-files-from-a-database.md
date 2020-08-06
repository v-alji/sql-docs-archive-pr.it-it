---
title: Eliminare file di dati o file di log da un database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], files
- deleting files
- removing files
- removing data
- data deletions [SQL Server]
- file deletion [SQL Server]
- deleting data
ms.assetid: 0db4018c-ce2c-4ba1-bb29-1e4f3791c925
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6f7bd170e085e9bc94b00446545850e905efaa34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725876"
---
# <a name="delete-data-or-log-files-from-a-database"></a><span data-ttu-id="f1c34-102">Eliminare file di dati o file di log da un database</span><span class="sxs-lookup"><span data-stu-id="f1c34-102">Delete Data or Log Files from a Database</span></span>
  <span data-ttu-id="f1c34-103">In questo argomento si descrive come eliminare file di dati o di log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1c34-103">This topic describes how to delete data or log files in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f1c34-104">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="f1c34-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="f1c34-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f1c34-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="f1c34-106">Per poter essere eliminato, un file deve essere vuoto.</span><span class="sxs-lookup"><span data-stu-id="f1c34-106">A file must be empty before it can be deleted.</span></span> <span data-ttu-id="f1c34-107">Per altre informazioni, vedere [Compattare un file](shrink-a-file.md).</span><span class="sxs-lookup"><span data-stu-id="f1c34-107">For more information, see [Shrink a File](shrink-a-file.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f1c34-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="f1c34-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f1c34-109">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="f1c34-109">Permissions</span></span>  
 <span data-ttu-id="f1c34-110">È richiesta l'autorizzazione ALTER per il database.</span><span class="sxs-lookup"><span data-stu-id="f1c34-110">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f1c34-111">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f1c34-111">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-data-or-log-files-from-a-database"></a><span data-ttu-id="f1c34-112">Per eliminare file di dati o di log da un database</span><span class="sxs-lookup"><span data-stu-id="f1c34-112">To delete data or log files from a database</span></span>  
  
1.  <span data-ttu-id="f1c34-113">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere questa istanza.</span><span class="sxs-lookup"><span data-stu-id="f1c34-113">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="f1c34-114">Espandere **Database**, fare clic con il pulsante destro del mouse sul database da cui eliminare il file e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="f1c34-114">Expand **Databases**, right-click the database from which to delete the file, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="f1c34-115">Selezionare la pagina **File** .</span><span class="sxs-lookup"><span data-stu-id="f1c34-115">Select the **Files** page.</span></span>  
  
4.  <span data-ttu-id="f1c34-116">Nella griglia **File di database** selezionare il file da eliminare, quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="f1c34-116">In the **Database files** grid, select the file to delete and then click **Remove**.</span></span>  
  
5.  <span data-ttu-id="f1c34-117">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f1c34-117">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f1c34-118">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f1c34-118">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-data-or-log-files-from-a-database"></a><span data-ttu-id="f1c34-119">Per eliminare file di dati o di log da un database</span><span class="sxs-lookup"><span data-stu-id="f1c34-119">To delete data or log files from a database</span></span>  
  
1.  <span data-ttu-id="f1c34-120">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1c34-120">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f1c34-121">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="f1c34-121">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f1c34-122">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="f1c34-122">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="f1c34-123">In questo esempio si rimuove il file `test1dat4`.</span><span class="sxs-lookup"><span data-stu-id="f1c34-123">This example removes the file `test1dat4`.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase4](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase4)]  
  
 <span data-ttu-id="f1c34-124">Per altri esempi, vedere [Opzioni per file e filegroup ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span><span class="sxs-lookup"><span data-stu-id="f1c34-124">For more examples, see [ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1c34-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1c34-125">See Also</span></span>  
 <span data-ttu-id="f1c34-126">[Compattare un database](shrink-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="f1c34-126">[Shrink a Database](shrink-a-database.md) </span></span>  
 [<span data-ttu-id="f1c34-127">Aggiungere file di dati o file di log a un database</span><span class="sxs-lookup"><span data-stu-id="f1c34-127">Add Data or Log Files to a Database</span></span>](add-data-or-log-files-to-a-database.md)  
  
  
