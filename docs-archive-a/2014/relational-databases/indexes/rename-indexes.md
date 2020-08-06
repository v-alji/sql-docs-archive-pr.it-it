---
title: Rinominare indici | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- renaming indexes
- index names [SQL Server]
- indexes [SQL Server], renaming
ms.assetid: d3d612a1-ea1b-4d99-85d2-0a2ad54f4b0e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 184d6e20f7857c5ea3535e77e21a0630ffc7b678
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637299"
---
# <a name="rename-indexes"></a><span data-ttu-id="28ed6-102">Ridenominazione di indici</span><span class="sxs-lookup"><span data-stu-id="28ed6-102">Rename Indexes</span></span>
  <span data-ttu-id="28ed6-103">In questo argomento si descrive come rinominare un indice in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28ed6-103">This topic describes how to rename an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="28ed6-104">La ridenominazione di un indice consiste nel sostituire il nome attuale dell'indice con il nuovo nome specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="28ed6-104">Renaming an index replaces the current index name with the new name that you provide.</span></span> <span data-ttu-id="28ed6-105">Il nome specificato deve essere univoco all'interno della tabella o della vista.</span><span class="sxs-lookup"><span data-stu-id="28ed6-105">The specified name must be unique within the table or view.</span></span> <span data-ttu-id="28ed6-106">Ad esempio, due tabelle possono avere un indice denominato **XPK_1**, ma la stessa tabella non può contenere due indici denominati **XPK_1**.</span><span class="sxs-lookup"><span data-stu-id="28ed6-106">For example, two tables can have an index named **XPK_1**, but the same table cannot have two indexes named **XPK_1**.</span></span> <span data-ttu-id="28ed6-107">Non è possibile creare un indice con lo stesso nome di un indice disabilitato esistente.</span><span class="sxs-lookup"><span data-stu-id="28ed6-107">You cannot create an index with the same name as an existing disabled index.</span></span> <span data-ttu-id="28ed6-108">La ridenominazione di un indice non ne causa la ricompilazione.</span><span class="sxs-lookup"><span data-stu-id="28ed6-108">Renaming an index does not cause the index to be rebuilt.</span></span>  
  
 <span data-ttu-id="28ed6-109">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="28ed6-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="28ed6-110">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="28ed6-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="28ed6-111">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="28ed6-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="28ed6-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="28ed6-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="28ed6-113">**Per rinominare un indice utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="28ed6-113">**To rename an index, using:**</span></span>  
  
     [<span data-ttu-id="28ed6-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="28ed6-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="28ed6-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="28ed6-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="28ed6-116">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="28ed6-116">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="28ed6-117">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="28ed6-117">Limitations and Restrictions</span></span>  
 <span data-ttu-id="28ed6-118">Quando si crea un vincolo PRIMARY KEY o UNIQUE in una tabella, viene automaticamente creato un indice per la tabella con lo stesso nome del vincolo.</span><span class="sxs-lookup"><span data-stu-id="28ed6-118">When you create a PRIMARY KEY or UNIQUE constraint on a table, an index with the same name as the constraint is automatically created for the table.</span></span> <span data-ttu-id="28ed6-119">Poiché i nomi di indice di una tabella devono essere univoci, nella tabella non è possibile creare o rinominare un indice in modo che abbia lo stesso nome di un vincolo PRIMARY KEY o UNIQUE esistente.</span><span class="sxs-lookup"><span data-stu-id="28ed6-119">Because index names must be unique within the table, you cannot create or rename an index to have the same name as an existing PRIMARY KEY or UNIQUE constraint on the table.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="28ed6-120">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="28ed6-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="28ed6-121">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="28ed6-121">Permissions</span></span>  
 <span data-ttu-id="28ed6-122">È richiesta l'autorizzazione ALTER per l'indice.</span><span class="sxs-lookup"><span data-stu-id="28ed6-122">Requires ALTER permission on the index.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="28ed6-123">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="28ed6-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-an-index-by-using-the-table-designer"></a><span data-ttu-id="28ed6-124">Per rinominare un indice utilizzando Progettazione tabelle</span><span class="sxs-lookup"><span data-stu-id="28ed6-124">To rename an index by using the Table Designer</span></span>  
  
1.  <span data-ttu-id="28ed6-125">In Esplora oggetti fare clic sul segno più per espandere il database contenente la tabella in cui si desidera rinominare un indice.</span><span class="sxs-lookup"><span data-stu-id="28ed6-125">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to rename an index.</span></span>  
  
2.  <span data-ttu-id="28ed6-126">Fare clic sul segno più per espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="28ed6-126">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="28ed6-127">Fare clic con il pulsante destro del mouse sulla tabella in cui si desidera rinominare un indice e selezionare **Progetta**.</span><span class="sxs-lookup"><span data-stu-id="28ed6-127">Right-click the table on which you want to rename an index and select **Design**.</span></span>  
  
4.  <span data-ttu-id="28ed6-128">Scegliere **Indici/chiavi** nel menu **Progettazione tabelle**.</span><span class="sxs-lookup"><span data-stu-id="28ed6-128">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="28ed6-129">Selezionare l'indice che si desidera rinominare nella casella di testo **Indice o chiave primari/univoci selezionati** .</span><span class="sxs-lookup"><span data-stu-id="28ed6-129">Select the index you want to rename in the **Selected Primary/Unique Key or Index** text box.</span></span>  
  
6.  <span data-ttu-id="28ed6-130">Nella griglia fare clic su **Nome** e digitare un nuovo nome nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="28ed6-130">In the grid, click **Name** and type a new name into the text box.</span></span>  
  
7.  <span data-ttu-id="28ed6-131">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="28ed6-131">Click **Close**.</span></span>  
  
8.  <span data-ttu-id="28ed6-132">Nel menu **File** scegliere **Salva**_table_name_.</span><span class="sxs-lookup"><span data-stu-id="28ed6-132">On the **File** menu, click **Save**_table_name_.</span></span>  
  
#### <a name="to-rename-an-index-by-using-object-explorer"></a><span data-ttu-id="28ed6-133">Per rinominare un indice utilizzando Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="28ed6-133">To rename an index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="28ed6-134">In Esplora oggetti fare clic sul segno più per espandere il database contenente la tabella in cui si desidera rinominare un indice.</span><span class="sxs-lookup"><span data-stu-id="28ed6-134">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to rename an index.</span></span>  
  
2.  <span data-ttu-id="28ed6-135">Fare clic sul segno più per espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="28ed6-135">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="28ed6-136">Fare clic sul segno più per espandere la tabella in cui si desidera rinominare un indice.</span><span class="sxs-lookup"><span data-stu-id="28ed6-136">Click the plus sign to expand the table on which you want to rename an index.</span></span>  
  
4.  <span data-ttu-id="28ed6-137">Fare clic sul segno più per espandere la cartella **Indici** .</span><span class="sxs-lookup"><span data-stu-id="28ed6-137">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="28ed6-138">Fare clic con il pulsante destro del mouse sull'indice che si desidera rinominare e scegliere **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="28ed6-138">Right-click the index you want to rename and select **Rename**.</span></span>  
  
6.  <span data-ttu-id="28ed6-139">Digitare il nuovo nome dell'indice e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="28ed6-139">Type the index's new name and press Enter.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="28ed6-140">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="28ed6-140">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-an-index"></a><span data-ttu-id="28ed6-141">Per rinominare un indice</span><span class="sxs-lookup"><span data-stu-id="28ed6-141">To rename an index</span></span>  
  
1.  <span data-ttu-id="28ed6-142">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28ed6-142">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="28ed6-143">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="28ed6-143">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="28ed6-144">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="28ed6-144">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    --Renames the IX_ProductVendor_VendorID index on the Purchasing.ProductVendor table to IX_VendorID.   
  
    EXEC sp_rename N'Purchasing.ProductVendor.IX_ProductVendor_VendorID', N'IX_VendorID', N'INDEX';   
    GO  
    ```  
  
 <span data-ttu-id="28ed6-145">Per altre informazioni, vedere [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="28ed6-145">For more information, see  [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span></span>  
  
  
