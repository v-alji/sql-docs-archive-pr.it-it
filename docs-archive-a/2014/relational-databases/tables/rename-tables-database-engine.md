---
title: Rinominare tabelle (motore di database) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table renaming [SQL Server]
- table names [SQL Server]
- tables [SQL Server], Visual Database Tools
- renaming tables
ms.assetid: 2f5c922d-4d71-4694-9fca-28dd99375799
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6e73bbb92d8fd3fdcaa7756ce1dcb74d8cd598b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635968"
---
# <a name="rename-tables-database-engine"></a><span data-ttu-id="16145-102">Ridenominazione di tabelle (motore di database)</span><span class="sxs-lookup"><span data-stu-id="16145-102">Rename Tables (Database Engine)</span></span>
  <span data-ttu-id="16145-103">È possibile rinominare una tabella in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16145-103">You can rename a table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="16145-104">Fare attenzione prima di rinominare una tabella.</span><span class="sxs-lookup"><span data-stu-id="16145-104">Think carefully before you rename a table.</span></span> <span data-ttu-id="16145-105">Se query, viste, funzioni definite dall'utente, stored procedure o programmi esistenti fanno riferimento a tale tabella, la modifica del nome renderà questi oggetti non validi.</span><span class="sxs-lookup"><span data-stu-id="16145-105">If existing queries, views, user-defined functions, stored procedures, or programs refer to that table, the name modification will make these objects invalid.</span></span>  
  
 <span data-ttu-id="16145-106">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="16145-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="16145-107">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="16145-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="16145-108">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="16145-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="16145-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="16145-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="16145-110">**Per rinominare una tabella:**</span><span class="sxs-lookup"><span data-stu-id="16145-110">**To rename a table, using:**</span></span>  
  
     [<span data-ttu-id="16145-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="16145-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="16145-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="16145-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="16145-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="16145-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="16145-114">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="16145-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="16145-115">Se una tabella viene ridenominata, i riferimenti a tale tabella non vengono ridenominati automaticamente</span><span class="sxs-lookup"><span data-stu-id="16145-115">Renaming a table will not automatically rename references to that table.</span></span> <span data-ttu-id="16145-116">ed è necessario modificare manualmente tutti gli oggetti che fanno riferimento alla tabella rinominata.</span><span class="sxs-lookup"><span data-stu-id="16145-116">You must manually modify any objects that reference the renamed table.</span></span> <span data-ttu-id="16145-117">Se, ad esempio, si rinomina una tabella a cui viene fatto riferimento all'interno di un trigger, è necessario modificare il trigger in base al nuovo nome della tabella.</span><span class="sxs-lookup"><span data-stu-id="16145-117">For example, if you rename a table and that table is referenced in a trigger, you must modify the trigger to reflect the new table name.</span></span> <span data-ttu-id="16145-118">Utilizzare [sys.sql_expression_dependencies](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) per elencare le dipendenze della tabella prima di rinominarla.</span><span class="sxs-lookup"><span data-stu-id="16145-118">Use [sys.sql_expression_dependencies](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) to list dependencies on the table before renaming it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="16145-119">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="16145-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="16145-120">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="16145-120">Permissions</span></span>  
 <span data-ttu-id="16145-121">È necessario disporre dell'autorizzazione ALTER per la tabella.</span><span class="sxs-lookup"><span data-stu-id="16145-121">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="16145-122">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="16145-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-table"></a><span data-ttu-id="16145-123">Per rinominare una tabella</span><span class="sxs-lookup"><span data-stu-id="16145-123">To rename a table</span></span>  
  
1.  <span data-ttu-id="16145-124">In Esplora oggetti fare clic con il pulsante destro del mouse sulla tabella da rinominare, quindi selezionare **Progetta** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="16145-124">In Object Explorer, right-click the table you want to rename and choose **Design** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="16145-125">Scegliere **Proprietà** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="16145-125">From the **View** menu, choose **Properties**.</span></span>  
  
3.  <span data-ttu-id="16145-126">Nella finestra **Proprietà** digitare un nuovo nome per la tabella nel campo relativo al valore **Nome** .</span><span class="sxs-lookup"><span data-stu-id="16145-126">In the field for the **Name** value in the **Properties** window, type a new name for the table.</span></span>  
  
4.  <span data-ttu-id="16145-127">Per annullare questa azione, premere ESC prima di uscire dal campo.</span><span class="sxs-lookup"><span data-stu-id="16145-127">To cancel this action, press the ESC key before leaving this field.</span></span>  
  
5.  <span data-ttu-id="16145-128">Scegliere **Salva**_nome tabella_dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="16145-128">From the **File** menu choose **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="16145-129">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="16145-129">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-a-table"></a><span data-ttu-id="16145-130">Per rinominare una tabella</span><span class="sxs-lookup"><span data-stu-id="16145-130">To rename a table</span></span>  
  
1.  <span data-ttu-id="16145-131">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16145-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="16145-132">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="16145-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="16145-133">Nell'esempio seguente la tabella `SalesTerritory` viene rinominata in `SalesTerr` nello schema `Sales` .</span><span class="sxs-lookup"><span data-stu-id="16145-133">The following example renames the `SalesTerritory` table to `SalesTerr` in the `Sales` schema.</span></span> <span data-ttu-id="16145-134">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="16145-134">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    EXEC sp_rename 'Sales.SalesTerritory', 'SalesTerr';  
    ```  
  
 <span data-ttu-id="16145-135">Per altri esempi, vedere [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="16145-135">For additional examples, see [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span></span>  
  
  
