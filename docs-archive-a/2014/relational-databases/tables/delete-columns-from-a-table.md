---
title: Eliminare le colonne da una tabella | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], deleting
- removing columns
- deleting columns
- dropping columns
ms.assetid: 0d8f6e4f-bc71-4fa3-8615-74249c8e072d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 62f9bca8ee53ae97bb1ac7f37e597b7814a0c370
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629738"
---
# <a name="delete-columns-from-a-table"></a><span data-ttu-id="cb971-102">Eliminare le colonne da una tabella</span><span class="sxs-lookup"><span data-stu-id="cb971-102">Delete Columns from a Table</span></span>
  <span data-ttu-id="cb971-103">In questo argomento viene descritta la modalità di eliminazione delle colonne tabella in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb971-103">This topic describes how to delete table columns in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="cb971-104">Quando si elimina una colonna da una tabella, tale colonna e tutti i dati in essa contenuti verranno eliminati dal database.</span><span class="sxs-lookup"><span data-stu-id="cb971-104">When you delete a column from a table, it and all the data it contains are deleted from the database.</span></span> <span data-ttu-id="cb971-105">Questa azione non può essere annullata.</span><span class="sxs-lookup"><span data-stu-id="cb971-105">This action cannot be undone.</span></span>  
  
 <span data-ttu-id="cb971-106">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="cb971-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="cb971-107">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="cb971-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="cb971-108">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="cb971-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="cb971-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="cb971-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="cb971-110">**Per eliminare una colonna da una tabella:**</span><span class="sxs-lookup"><span data-stu-id="cb971-110">**To delete a column from a table, using:**</span></span>  
  
     [<span data-ttu-id="cb971-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cb971-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="cb971-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cb971-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cb971-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="cb971-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="cb971-114">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="cb971-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="cb971-115">Non è possibile eliminare una colonna che dispone di un vincolo CHECK.</span><span class="sxs-lookup"><span data-stu-id="cb971-115">You cannot delete a column that has a CHECK constraint.</span></span> <span data-ttu-id="cb971-116">È necessario eliminare prima questo vincolo.</span><span class="sxs-lookup"><span data-stu-id="cb971-116">You must first delete the constraint.</span></span>  
  
 <span data-ttu-id="cb971-117">Non è possibile eliminare una colonna che dispone di vincoli PRIMARY KEY o FOREIGN KEY o altre dipendenze a parte quando si utilizza Progettazione tabelle.</span><span class="sxs-lookup"><span data-stu-id="cb971-117">You cannot delete a column that has PRIMARY KEY or FOREIGN KEY constraints or other dependencies except when using the Table Designer.</span></span> <span data-ttu-id="cb971-118">Quando si utilizza Esplora oggetti o [!INCLUDE[tsql](../../includes/tsql-md.md)], è necessario prima rimuovere tutte le dipendenze sulla colonna.</span><span class="sxs-lookup"><span data-stu-id="cb971-118">When using Object Explorer or [!INCLUDE[tsql](../../includes/tsql-md.md)], you must first remove all dependencies on the column.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cb971-119">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="cb971-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cb971-120">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="cb971-120">Permissions</span></span>  
 <span data-ttu-id="cb971-121">È necessario disporre dell'autorizzazione ALTER per la tabella.</span><span class="sxs-lookup"><span data-stu-id="cb971-121">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="cb971-122">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cb971-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-columns-by-using-object-explorer"></a><span data-ttu-id="cb971-123">Per eliminare le colonne utilizzando Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="cb971-123">To delete columns by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="cb971-124">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb971-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="cb971-125">In **Esplora oggetti**fare clic con il pulsante destro del mouse sulla tabella da cui si vogliono eliminare colonne, quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="cb971-125">In **Object Explorer**, right-click the table from which you want to delete columns and choose **Delete**.</span></span>  
  
3.  <span data-ttu-id="cb971-126">Nella finestra di dialogo **Elimina oggetto** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cb971-126">In **Delete Object** dialog box, click **OK**.</span></span>  
  
 <span data-ttu-id="cb971-127">Se la colonna contiene vincoli o altre dipendenze, un messaggio di errore sarà visualizzato nella finestra di dialogo **Elimina oggetto** .</span><span class="sxs-lookup"><span data-stu-id="cb971-127">If the column contains constraints or other dependencies, an error message will display in the **Delete Object** dialog box.</span></span> <span data-ttu-id="cb971-128">Risolvere l'errore eliminando i vincoli a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="cb971-128">Resolve the error by deleting the referenced constraints.</span></span>  
  
#### <a name="to-delete-columns-by-using-table-designer"></a><span data-ttu-id="cb971-129">Per eliminare le colonne utilizzando Progettazione tabelle.</span><span class="sxs-lookup"><span data-stu-id="cb971-129">To delete columns by using Table Designer</span></span>  
  
1.  <span data-ttu-id="cb971-130">In **Esplora oggetti**fare clic con il pulsante destro del mouse sulla tabella da cui si vogliono eliminare colonne, quindi scegliere **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="cb971-130">In **Object Explorer**, right-click the table from which you want to delete columns and choose **Design**.</span></span>  
  
2.  <span data-ttu-id="cb971-131">Fare clic con il pulsante destro del mouse sulla colonna che si vuole eliminare e scegliere **Elimina colonna** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="cb971-131">Right-click the column you want to delete and choose **Delete Column** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="cb971-132">Se la colonna fa parte di una relazione (FOREIGN KEY o PRIMARY KEY), verrà visualizzato un messaggio in cui viene chiesto di confermare l'eliminazione delle colonne selezionate e delle corrispondenti relazioni.</span><span class="sxs-lookup"><span data-stu-id="cb971-132">If the column participates in a relationship (FOREIGN KEY or PRIMARY KEY), a message prompts you to confirm the deletion of the selected columns and their relationships.</span></span> <span data-ttu-id="cb971-133">Scegliere **Sì**.</span><span class="sxs-lookup"><span data-stu-id="cb971-133">Choose **Yes**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="cb971-134">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cb971-134">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-columns"></a><span data-ttu-id="cb971-135">Per eliminare le colonne</span><span class="sxs-lookup"><span data-stu-id="cb971-135">To delete columns</span></span>  
  
1.  <span data-ttu-id="cb971-136">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb971-136">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="cb971-137">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="cb971-137">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="cb971-138">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="cb971-138">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE dbo.doc_exb DROP COLUMN column_b ;  
    ```  
  
 <span data-ttu-id="cb971-139">Se la colonna contiene vincoli o altre dipendenze, verrà restituito un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="cb971-139">If the column contains constraints or other dependencies, an error message will be returned.</span></span> <span data-ttu-id="cb971-140">Risolvere l'errore eliminando i vincoli a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="cb971-140">Resolve the error by deleting the referenced constraints.</span></span>  
  
 <span data-ttu-id="cb971-141">Per altri esempi, vedere [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cb971-141">For additional examples, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
##  <a name="FollowUp"></a>  
