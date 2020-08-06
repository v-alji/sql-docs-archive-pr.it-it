---
title: Eliminare tabelle (motore di database) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table deletions [SQL Server]
- deleting tables
- removing tables
- dropping tables
ms.assetid: ca6aa3e9-9885-44c3-bafc-aec441fd97ec
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1e361456534f565f854d348bbef5751c7d66c0f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722668"
---
# <a name="delete-tables-database-engine"></a><span data-ttu-id="5b4f4-102">Elimina tabelle (motore di database)</span><span class="sxs-lookup"><span data-stu-id="5b4f4-102">Delete Tables (Database Engine)</span></span>
  <span data-ttu-id="5b4f4-103">È possibile eliminare una tabella dal database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b4f4-103">You can delete (drop) a table from your database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="5b4f4-104">Prima di eliminare una tabella, valutare le possibili conseguenze.</span><span class="sxs-lookup"><span data-stu-id="5b4f4-104">Think carefully before you delete a table.</span></span> <span data-ttu-id="5b4f4-105">Se query, viste, funzioni definite dall'utente, stored procedure o programmi esistenti fanno riferimento a tale tabella, la modifica renderà non validi tali oggetti.</span><span class="sxs-lookup"><span data-stu-id="5b4f4-105">If existing queries, views, user-defined functions, stored procedures, or programs refer to that table, the deletion will make these objects invalid.</span></span>  
  
 <span data-ttu-id="5b4f4-106">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="5b4f4-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5b4f4-107">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="5b4f4-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5b4f4-108">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="5b4f4-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5b4f4-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5b4f4-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5b4f4-110">**Per eliminare una tabella:**</span><span class="sxs-lookup"><span data-stu-id="5b4f4-110">**To Delete a Table, using:**</span></span>  
  
     [<span data-ttu-id="5b4f4-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5b4f4-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5b4f4-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5b4f4-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5b4f4-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="5b4f4-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5b4f4-114">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="5b4f4-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="5b4f4-115">Non è possibile eliminare una tabella a cui fa riferimento un vincolo FOREIGN KEY.</span><span class="sxs-lookup"><span data-stu-id="5b4f4-115">You cannot drop a table that is referenced by a FOREIGN KEY constraint.</span></span> <span data-ttu-id="5b4f4-116">È prima necessario eliminare il vincolo FOREIGN KEY o la tabella di riferimento.</span><span class="sxs-lookup"><span data-stu-id="5b4f4-116">The referencing FOREIGN KEY constraint or the referencing table must first be dropped.</span></span> <span data-ttu-id="5b4f4-117">Se con la stessa istruzione DROP TABLE si eliminano sia la tabella di riferimento che la tabella che contiene la chiave primaria, è necessario indicare la tabella di riferimento per prima nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="5b4f4-117">If both the referencing table and the table that holds the primary key are being dropped in the same DROP TABLE statement, the referencing table must be listed first.</span></span>  
  
-   <span data-ttu-id="5b4f4-118">Con l'eliminazione di una tabella, le regole o i valori predefiniti della tabella vengono disassociati e i vincoli o trigger associati alla tabella vengono eliminati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5b4f4-118">When a table is dropped, rules or defaults on the table lose their binding, and any constraints or triggers associated with the table are automatically dropped.</span></span> <span data-ttu-id="5b4f4-119">Se la tabella viene ricreata, è necessario associare nuovamente le regole e i valori predefiniti appropriati, ricreare eventuali trigger e aggiungere tutti i vincoli necessari.</span><span class="sxs-lookup"><span data-stu-id="5b4f4-119">If you re-create a table, you must rebind the appropriate rules and defaults, re-create any triggers, and add all required constraints.</span></span>  
  
-   <span data-ttu-id="5b4f4-120">Se si elimina una tabella che contiene una colonna `varbinary (max)` con l'attributo FILESTREAM, non verrà rimosso alcun dato archiviato nel file system.</span><span class="sxs-lookup"><span data-stu-id="5b4f4-120">If you drop a table that contains a `varbinary (max)` column with the FILESTREAM attribute, any data stored in the file system will not be removed.</span></span>  
  
-   <span data-ttu-id="5b4f4-121">DROP TABLE e CREATE TABLE non devono essere eseguiti nella stessa tabella nello stesso batch.</span><span class="sxs-lookup"><span data-stu-id="5b4f4-121">DROP TABLE and CREATE TABLE should not be executed on the same table in the same batch.</span></span> <span data-ttu-id="5b4f4-122">In caso contrario, è possibile che si verifichi un errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="5b4f4-122">Otherwise an unexpected error may occur.</span></span>  
  
-   <span data-ttu-id="5b4f4-123">Le viste o stored procedure che fanno riferimento alla tabella eliminata devono essere eliminate o modificate in modo esplicito per eliminare il riferimento alla tabella.</span><span class="sxs-lookup"><span data-stu-id="5b4f4-123">Any view or stored procedure that references the dropped table must be explicitly deleted or modified to remove the reference to the table.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5b4f4-124">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5b4f4-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5b4f4-125">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="5b4f4-125">Permissions</span></span>  
 <span data-ttu-id="5b4f4-126">È richiesta l'autorizzazione ALTER per lo schema a cui appartiene la tabella, l'autorizzazione CONTROL per la tabella o l'appartenenza al ruolo predefinito del database **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="5b4f4-126">Requires ALTER permission on the schema to which the table belongs, CONTROL permission on the table, or membership in the **db_ddladmin** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5b4f4-127">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5b4f4-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-table-from-the-database"></a><span data-ttu-id="5b4f4-128">Per eliminare una tabella dal database</span><span class="sxs-lookup"><span data-stu-id="5b4f4-128">To delete a table from the database</span></span>  
  
1.  <span data-ttu-id="5b4f4-129">In Esplora oggetti selezionare la tabella che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="5b4f4-129">In Object Explorer, select the table you want to delete.</span></span>  
  
2.  <span data-ttu-id="5b4f4-130">Fare clic con il pulsante destro del mouse sulla tabella, quindi scegliere **Elimina** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="5b4f4-130">Right-click the table and choose **Delete** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="5b4f4-131">Verrà visualizzato un messaggio in cui viene chiesto di confermare l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="5b4f4-131">A message box prompts you to confirm the deletion.</span></span> <span data-ttu-id="5b4f4-132">Fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="5b4f4-132">Click **Yes**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5b4f4-133">Eliminando una tabella verranno eliminate automaticamente anche tutte le corrispondenti relazioni.</span><span class="sxs-lookup"><span data-stu-id="5b4f4-133">Deleting a table automatically removes any relationships to it.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5b4f4-134">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5b4f4-134">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-table-in-query-editor"></a><span data-ttu-id="5b4f4-135">Per eliminare una tabella in Editor di query</span><span class="sxs-lookup"><span data-stu-id="5b4f4-135">To delete a table in Query Editor</span></span>  
  
1.  <span data-ttu-id="5b4f4-136">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b4f4-136">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5b4f4-137">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="5b4f4-137">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5b4f4-138">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="5b4f4-138">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    DROP TABLE dbo.PurchaseOrderDetail;  
  
    ```  
  
 <span data-ttu-id="5b4f4-139">Per altre informazioni, vedere [DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="5b4f4-139">For more information, see [DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql)</span></span>  
  
  
