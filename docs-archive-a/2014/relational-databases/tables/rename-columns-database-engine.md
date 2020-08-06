---
title: Rinominare colonne (motore di database) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], names
- renaming columns
- column names [SQL Server]
ms.assetid: 7c71ec9f-0180-4398-b32a-4bfb7592e75d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6871ab82eaa17aa5e392e6b2bb3f5c60058f9af9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635971"
---
# <a name="rename-columns-database-engine"></a><span data-ttu-id="9ff25-102">Ridenominazione di colonne (motore di database)</span><span class="sxs-lookup"><span data-stu-id="9ff25-102">Rename Columns (Database Engine)</span></span>
  <span data-ttu-id="9ff25-103">È possibile rinominare un nome tabella in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ff25-103">You can rename a table column in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="9ff25-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="9ff25-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9ff25-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="9ff25-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9ff25-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="9ff25-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="9ff25-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="9ff25-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9ff25-108">**Per rinominare colonne utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="9ff25-108">**To rename columns, using:**</span></span>  
  
     [<span data-ttu-id="9ff25-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9ff25-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9ff25-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9ff25-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9ff25-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="9ff25-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="9ff25-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="9ff25-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="9ff25-113">Se una colonna viene ridenominata, i riferimenti a tale colonna non vengono ridenominati automaticamente</span><span class="sxs-lookup"><span data-stu-id="9ff25-113">Renaming a column will not automatically rename references to that column.</span></span> <span data-ttu-id="9ff25-114">ed è necessario modificare manualmente tutti gli oggetti che fanno riferimento alla colonna rinominata.</span><span class="sxs-lookup"><span data-stu-id="9ff25-114">You must modify any objects that reference the renamed column manually.</span></span> <span data-ttu-id="9ff25-115">Se, ad esempio, si rinomina una colonna di una tabella a cui viene fatto riferimento all'interno di un trigger, è necessario modificare il trigger in base al nuovo nome della colonna.</span><span class="sxs-lookup"><span data-stu-id="9ff25-115">For example, if you rename a table column and that column is referenced in a trigger, you must modify the trigger to reflect the new column name.</span></span> <span data-ttu-id="9ff25-116">Usare [sys.sql_expression_dependencies](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) per elencare le dipendenze dall'oggetto prima di rinominarlo.</span><span class="sxs-lookup"><span data-stu-id="9ff25-116">Use [sys.sql_expression_dependencies](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) to list dependencies on the object before renaming it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9ff25-117">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="9ff25-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9ff25-118">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="9ff25-118">Permissions</span></span>  
 <span data-ttu-id="9ff25-119">È necessario disporre dell'autorizzazione ALTER per l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="9ff25-119">Requires ALTER permission on the object.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9ff25-120">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9ff25-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-column-using-object-explorer"></a><span data-ttu-id="9ff25-121">Per rinominare una colonna utilizzando Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="9ff25-121">To rename a column using Object Explorer</span></span>  
  
1.  <span data-ttu-id="9ff25-122">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ff25-122">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9ff25-123">In **Esplora oggetti**fare clic con il pulsante destro del mouse sulla tabella in cui si vuole rinominare le colonne, quindi selezionare **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="9ff25-123">In **Object Explorer**, right-click the table in which you want to rename columns and choose **Rename**.</span></span>  
  
3.  <span data-ttu-id="9ff25-124">Digitare un nuovo nome colonna.</span><span class="sxs-lookup"><span data-stu-id="9ff25-124">Type a new column name.</span></span>  
  
#### <a name="to-rename-a-column-using-table-designer"></a><span data-ttu-id="9ff25-125">Per rinominare una colonna utilizzando Progettazione tabelle</span><span class="sxs-lookup"><span data-stu-id="9ff25-125">To rename a column using Table Designer</span></span>  
  
1.  <span data-ttu-id="9ff25-126">In **Esplora oggetti**fare clic con il pulsante destro del mouse sulla tabella di cui si vuole rinominare le colonne e selezionare **Progetta**.</span><span class="sxs-lookup"><span data-stu-id="9ff25-126">In **Object Explorer**, right-click the table to which you want to rename columns and choose **Design**.</span></span>  
  
2.  <span data-ttu-id="9ff25-127">In **Nome colonna**, selezionare il nome da cambiare e digitarne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="9ff25-127">Under **Column Name**, select the name you want to change and type a new one.</span></span>  
  
3.  <span data-ttu-id="9ff25-128">Nel menu **File** fare clic su **Salva**_nome tabella_.</span><span class="sxs-lookup"><span data-stu-id="9ff25-128">On the **File** menu, click **Save**_table name_.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9ff25-129">Per cambiare il nome di una colonna, è anche possibile utilizzare la scheda **Proprietà colonne** . A tale scopo, selezionare la colonna di cui si desidera cambiare il nome e digitare un nuovo valore per **Nome**.</span><span class="sxs-lookup"><span data-stu-id="9ff25-129">You can also change the name of a column in the **Column Properties** tab. Select the column whose name you want to change and type a new value for **Name**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9ff25-130">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9ff25-130">Using Transact-SQL</span></span>  
 <span data-ttu-id="9ff25-131">**Per rinominare una colonna**</span><span class="sxs-lookup"><span data-stu-id="9ff25-131">**To rename a column**</span></span>  
  
#### <a name="to-rename-a-column"></a><span data-ttu-id="9ff25-132">Per rinominare una colonna</span><span class="sxs-lookup"><span data-stu-id="9ff25-132">To rename a column</span></span>  
  
1.  <span data-ttu-id="9ff25-133">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ff25-133">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9ff25-134">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="9ff25-134">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9ff25-135">Nell'esempio seguente la colonna `TerritoryID` della tabella `Sales.SalesTerritory` viene rinominata in `TerrID`.</span><span class="sxs-lookup"><span data-stu-id="9ff25-135">The following example renames the column `TerritoryID` in the table `Sales.SalesTerritory` to `TerrID`.</span></span> <span data-ttu-id="9ff25-136">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="9ff25-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_rename 'Sales.SalesTerritory.TerritoryID', 'TerrID', 'COLUMN';  
    GO  
    ```  
  
 <span data-ttu-id="9ff25-137">Per altre informazioni, vedere [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9ff25-137">For more information, see [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span></span>  
  
  
