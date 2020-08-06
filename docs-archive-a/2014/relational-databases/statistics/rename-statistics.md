---
title: Rinominare statistiche | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- renaming statistics
- statistics [SQL Server], renaming
ms.assetid: a3bed7b7-3dc5-4b33-b1c6-67c27f573764
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1528dcec50a662524531065d597b004fe7f59e5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636623"
---
# <a name="rename-statistics"></a><span data-ttu-id="42c6b-102">Rinominare statistiche</span><span class="sxs-lookup"><span data-stu-id="42c6b-102">Rename Statistics</span></span>
  <span data-ttu-id="42c6b-103">È possibile rinominare un oggetto statistiche in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42c6b-103">You can rename a statistics object in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
 <span data-ttu-id="42c6b-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="42c6b-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="42c6b-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="42c6b-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="42c6b-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="42c6b-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="42c6b-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="42c6b-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="42c6b-108">**Rinominare un oggetto statistiche tramite:**</span><span class="sxs-lookup"><span data-stu-id="42c6b-108">**To rename a statistics object, using:**</span></span>  
  
     [<span data-ttu-id="42c6b-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="42c6b-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="42c6b-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="42c6b-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="42c6b-111">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="42c6b-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="42c6b-112">Per impostazione predefinita, la creazione di un indice comporta la creazione di una statistica per le colonne chiave di tale indice.</span><span class="sxs-lookup"><span data-stu-id="42c6b-112">By default, creating an index creates a statistic on the key columns of that index.</span></span> <span data-ttu-id="42c6b-113">La ridenominazione automatica dell'indice comporta pertanto la ridenominazione dell'oggetto statistiche e viceversa.</span><span class="sxs-lookup"><span data-stu-id="42c6b-113">Therefore, renaming the index automatically renames the statistics object, and vice versa.</span></span>  
  
 <span data-ttu-id="42c6b-114">La modifica di una parte del nome di un oggetto potrebbe compromettere il funzionamento di script e stored procedure.</span><span class="sxs-lookup"><span data-stu-id="42c6b-114">Changing any part of an object name can break scripts and stored procedures.</span></span> <span data-ttu-id="42c6b-115">Anziché rinominare l'oggetto statistiche, è consigliabile eliminarlo e ricrearlo con il nuovo nome.</span><span class="sxs-lookup"><span data-stu-id="42c6b-115">Instead of renaming, we recommend that you drop the statistics object and re-create it with the new name.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="42c6b-116">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="42c6b-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="42c6b-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="42c6b-117">Permissions</span></span>  
 <span data-ttu-id="42c6b-118">È richiesta l'autorizzazione ALTER per la tabella o la vista.</span><span class="sxs-lookup"><span data-stu-id="42c6b-118">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="42c6b-119">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="42c6b-119">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-a-statistics-object"></a><span data-ttu-id="42c6b-120">Per rinominare un oggetto statistiche</span><span class="sxs-lookup"><span data-stu-id="42c6b-120">To rename a statistics object</span></span>  
  
1.  <span data-ttu-id="42c6b-121">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42c6b-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="42c6b-122">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="42c6b-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="42c6b-123">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="42c6b-123">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_rename N'AK_Employee_LoginID', N'AK_Emp_Login', N'STATISTICS';   
    GO  
    ```  
  
 <span data-ttu-id="42c6b-124">Per altre informazioni, vedere [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="42c6b-124">For more information, see [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span></span>  
  
  
