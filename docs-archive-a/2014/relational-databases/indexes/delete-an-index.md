---
title: Eliminare un indice | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- removing indexes
- deleting indexes
- dropping indexes
- indexes [SQL Server], dropping
- index deletions [SQL Server]
ms.assetid: fd38a0ed-26c4-4c76-9ef7-e0a16147329d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4552ba701782e5790f95f54c0c1c66f82573f1e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724612"
---
# <a name="delete-an-index"></a><span data-ttu-id="c1b0a-102">Eliminare un indice</span><span class="sxs-lookup"><span data-stu-id="c1b0a-102">Delete an Index</span></span>
  <span data-ttu-id="c1b0a-103">In questo argomento si descrive come eliminare (rimuovere) un indice in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1b0a-103">This topic describes how to delete (drop) an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="c1b0a-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="c1b0a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c1b0a-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="c1b0a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c1b0a-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="c1b0a-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c1b0a-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c1b0a-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c1b0a-108">**Per eliminare un indice utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="c1b0a-108">**To delete an index, using:**</span></span>  
  
     [<span data-ttu-id="c1b0a-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c1b0a-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c1b0a-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c1b0a-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c1b0a-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="c1b0a-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c1b0a-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="c1b0a-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="c1b0a-113">Gli indici creati come risultato di un vincolo PRIMARY KEY o UNIQUE non possono essere eliminati mediante questa procedura.</span><span class="sxs-lookup"><span data-stu-id="c1b0a-113">Indexes created as the result of a PRIMARY KEY or UNIQUE constraint cannot be deleted by using this method.</span></span> <span data-ttu-id="c1b0a-114">È infatti necessario eliminare il vincolo.</span><span class="sxs-lookup"><span data-stu-id="c1b0a-114">Instead, the constraint must be deleted.</span></span> <span data-ttu-id="c1b0a-115">Per rimuovere il vincolo e l'indice corrispondente, utilizzare [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) con la clausola DROP CONSTRAINT in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1b0a-115">To remove the constraint and corresponding index, use [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) with the DROP CONSTRAINT clause in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c1b0a-116">Per altre informazioni, vedere [Delete Primary Keys](../tables/delete-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="c1b0a-116">For more information, see [Delete Primary Keys](../tables/delete-primary-keys.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c1b0a-117">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c1b0a-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c1b0a-118">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="c1b0a-118">Permissions</span></span>  
 <span data-ttu-id="c1b0a-119">È richiesta l'autorizzazione ALTER per la tabella o la vista.</span><span class="sxs-lookup"><span data-stu-id="c1b0a-119">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="c1b0a-120">Questa autorizzazione viene concessa per impostazione predefinita al ruolo predefinito del server **sysadmin** e ai ruoli predefiniti del database **db_ddladmin** e **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="c1b0a-120">This permission is granted by default to the **sysadmin** fixed server role and the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c1b0a-121">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c1b0a-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-an-index-by-using-object-explorer"></a><span data-ttu-id="c1b0a-122">Per eliminare un indice utilizzando Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="c1b0a-122">To delete an index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="c1b0a-123">In Esplora oggetti espandere il database contenente la tabella in cui si desidera eliminare un indice.</span><span class="sxs-lookup"><span data-stu-id="c1b0a-123">In Object Explorer, expand the database that contains the table on which you want to delete an index.</span></span>  
  
2.  <span data-ttu-id="c1b0a-124">Espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="c1b0a-124">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="c1b0a-125">Espandere la tabella contenente l'indice che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="c1b0a-125">Expand the table that contains the index you want to delete.</span></span>  
  
4.  <span data-ttu-id="c1b0a-126">Espandere la cartella **Indici** .</span><span class="sxs-lookup"><span data-stu-id="c1b0a-126">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="c1b0a-127">Fare clic con il pulsante destro del mouse sull'indice che si desidera eliminare e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="c1b0a-127">Right-click the index you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="c1b0a-128">Nella finestra di dialogo **Elimina oggetto** verificare che nella griglia **Oggetto da eliminare** sia presente l'indice corretto e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1b0a-128">In the **Delete Object** dialog box, verify that the correct index is in the **Object to be deleted** grid and click **OK**.</span></span>  
  
#### <a name="to-delete-an-index-using-table-designer"></a><span data-ttu-id="c1b0a-129">Per eliminare un indice utilizzando Progettazione tabelle.</span><span class="sxs-lookup"><span data-stu-id="c1b0a-129">To delete an index using Table Designer</span></span>  
  
1.  <span data-ttu-id="c1b0a-130">In Esplora oggetti espandere il database contenente la tabella in cui si desidera eliminare un indice.</span><span class="sxs-lookup"><span data-stu-id="c1b0a-130">In Object Explorer, expand the database that contains the table on which you want to delete an index.</span></span>  
  
2.  <span data-ttu-id="c1b0a-131">Espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="c1b0a-131">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="c1b0a-132">Fare clic con il pulsante destro del mouse sulla tabella contenente l'indice da eliminare e scegliere Progetta.</span><span class="sxs-lookup"><span data-stu-id="c1b0a-132">Right-click the table that contains the index you want to delete and click Design.</span></span>  
  
4.  <span data-ttu-id="c1b0a-133">Scegliere **Indici/chiavi** nel menu **Progettazione tabelle**.</span><span class="sxs-lookup"><span data-stu-id="c1b0a-133">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="c1b0a-134">Nella finestra di dialogo **Indici/chiavi** selezionare l'indice da eliminare.</span><span class="sxs-lookup"><span data-stu-id="c1b0a-134">In the **Indexes/Keys** dialog box, select the index you want to delete.</span></span>  
  
6.  <span data-ttu-id="c1b0a-135">Fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="c1b0a-135">Click **Delete**.</span></span>  
  
7.  <span data-ttu-id="c1b0a-136">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="c1b0a-136">Click **Close**.</span></span>  
  
8.  <span data-ttu-id="c1b0a-137">Selezionare **Salva** table_name **dal menu**_File_.</span><span class="sxs-lookup"><span data-stu-id="c1b0a-137">On the **File** menu, select **Save**_table_name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c1b0a-138">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c1b0a-138">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-an-index"></a><span data-ttu-id="c1b0a-139">Per eliminare un indice</span><span class="sxs-lookup"><span data-stu-id="c1b0a-139">To delete an index</span></span>  
  
1.  <span data-ttu-id="c1b0a-140">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1b0a-140">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c1b0a-141">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="c1b0a-141">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c1b0a-142">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="c1b0a-142">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- delete the IX_ProductVendor_BusinessEntityID index  
    -- from the Purchasing.ProductVendor table  
    DROP INDEX IX_ProductVendor_BusinessEntityID   
        ON Purchasing.ProductVendor;  
    GO  
    ```  
  
 <span data-ttu-id="c1b0a-143">Per altre informazioni, vedere [DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c1b0a-143">For more information, see [DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql).</span></span>  
  
  
