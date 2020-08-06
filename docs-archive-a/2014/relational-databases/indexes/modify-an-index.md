---
title: Modificare un indice | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- indexes [SQL Server], modifying
- modifying indexes
- index changes [SQL Server]
ms.assetid: 97e3110d-fde7-4f5d-9309-dc1697960aeb
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2af9293966afce8372f5b83a579418c546c82816
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723875"
---
# <a name="modify-an-index"></a><span data-ttu-id="23d79-102">Modificare un indice</span><span class="sxs-lookup"><span data-stu-id="23d79-102">Modify an Index</span></span>
  <span data-ttu-id="23d79-103">In questo argomento viene descritto come modificare un indice in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23d79-103">This topic describes how to modify an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="23d79-104">Gli indici creati come risultato di un vincolo PRIMARY KEY o UNIQUE non possono essere modificati con questo metodo.</span><span class="sxs-lookup"><span data-stu-id="23d79-104">Indexes created as the result of a PRIMARY KEY or UNIQUE constraint cannot be modified by using this method.</span></span> <span data-ttu-id="23d79-105">È necessario invece modificare il vincolo.</span><span class="sxs-lookup"><span data-stu-id="23d79-105">Instead, the constraint must be modified.</span></span>  
  
 <span data-ttu-id="23d79-106">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="23d79-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="23d79-107">**Per modificare un indice usando:**</span><span class="sxs-lookup"><span data-stu-id="23d79-107">**To modify an index, using:**</span></span>  
  
     [<span data-ttu-id="23d79-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="23d79-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="23d79-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="23d79-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="23d79-110">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="23d79-110">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-an-index"></a><span data-ttu-id="23d79-111">Per modificare un indice</span><span class="sxs-lookup"><span data-stu-id="23d79-111">To modify an index</span></span>  
  
1.  <span data-ttu-id="23d79-112">In Esplora oggetti connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere questa istanza.</span><span class="sxs-lookup"><span data-stu-id="23d79-112">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="23d79-113">Espandere **Database**, espandere il database a cui appartiene la tabella e quindi espandere **Tabelle**.</span><span class="sxs-lookup"><span data-stu-id="23d79-113">Expand **Databases**, expand the database in which the table belongs, and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="23d79-114">Espandere la tabella a cui appartiene l'indice e quindi espandere **Indici**.</span><span class="sxs-lookup"><span data-stu-id="23d79-114">Expand the table in which the index belongs and then expand **Indexes**.</span></span>  
  
4.  <span data-ttu-id="23d79-115">Fare clic con il pulsante destro del mouse sull'indice da modificare l'indice e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="23d79-115">Right-click the index that you want to modify and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="23d79-116">Nella finestra di dialogo **Proprietà indice** apportare le modifiche desiderate.</span><span class="sxs-lookup"><span data-stu-id="23d79-116">In the **Index Properties** dialog box, make the desired changes.</span></span> <span data-ttu-id="23d79-117">È ad esempio possibile aggiungere o rimuovere una colonna dalla chiave di indice o modificare l'impostazione di un'opzione di indice.</span><span class="sxs-lookup"><span data-stu-id="23d79-117">For example, you can add or remove a column from the index key, or change the setting of an index option.</span></span>  
  
#### <a name="to-modify-index-columns"></a><span data-ttu-id="23d79-118">Per modificare le colonne indice</span><span class="sxs-lookup"><span data-stu-id="23d79-118">To modify index columns</span></span>  
  
1.  <span data-ttu-id="23d79-119">Per aggiungere, rimuovere o modificare la posizione di una colonna indice, selezionare la pagina **Generale** della finestra di dialogo **Proprietà indice** .</span><span class="sxs-lookup"><span data-stu-id="23d79-119">To add, remove, or change the position of an index column, select the **General** page from the **Index Properties** dialog box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="23d79-120">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="23d79-120">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-an-index"></a><span data-ttu-id="23d79-121">Per modificare un indice</span><span class="sxs-lookup"><span data-stu-id="23d79-121">To modify an index</span></span>  
  
1.  <span data-ttu-id="23d79-122">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23d79-122">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="23d79-123">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="23d79-123">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="23d79-124">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="23d79-124">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="23d79-125">In questo esempio viene eliminato e ricreato un indice esistente sulla colonna `ProductID` della tabella `Production.WorkOrder` tramite l'opzione `DROP_EXISTING` .</span><span class="sxs-lookup"><span data-stu-id="23d79-125">This example drops and re-creates an existing index on the `ProductID` column of the `Production.WorkOrder` table by using the `DROP_EXISTING` option.</span></span> <span data-ttu-id="23d79-126">Vengono inoltre impostate le opzioni `FILLFACTOR` e `PAD_INDEX` .</span><span class="sxs-lookup"><span data-stu-id="23d79-126">The options `FILLFACTOR` and `PAD_INDEX` are also set.</span></span>  
  
     [!code-sql[IndexDDL#CreateIndex4](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/createindex.sql#createindex4)]  
  
     <span data-ttu-id="23d79-127">Nell'esempio seguente viene usato ALTER INDEX per impostare diverse opzioni sull'indice `AK_SalesOrderHeader_SalesOrderNumber`.</span><span class="sxs-lookup"><span data-stu-id="23d79-127">The following example uses ALTER INDEX to set several options on the index `AK_SalesOrderHeader_SalesOrderNumber`.</span></span>  
  
     [!code-sql[IndexDDL#AlterIndex4](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex4)]  
  
#### <a name="to-modify-index-columns"></a><span data-ttu-id="23d79-128">Per modificare le colonne indice</span><span class="sxs-lookup"><span data-stu-id="23d79-128">To modify index columns</span></span>  
  
1.  <span data-ttu-id="23d79-129">Per aggiungere, rimuovere o modificare la posizione di una colonna dell'indice, è necessario eliminare e ricreare l'indice.</span><span class="sxs-lookup"><span data-stu-id="23d79-129">To add, remove, or change the position of an index column, you must drop and recreate the index.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23d79-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23d79-130">See Also</span></span>  
 <span data-ttu-id="23d79-131">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="23d79-131">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 <span data-ttu-id="23d79-132">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="23d79-132">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="23d79-133">[INDEXPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/indexproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="23d79-133">[INDEXPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/indexproperty-transact-sql) </span></span>  
 <span data-ttu-id="23d79-134">[sys.indexes &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-indexes-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="23d79-134">[sys.indexes &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-indexes-transact-sql) </span></span>  
 <span data-ttu-id="23d79-135">[sys.index_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-index-columns-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="23d79-135">[sys.index_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-index-columns-transact-sql) </span></span>  
 <span data-ttu-id="23d79-136">[Impostare le opzioni di indice](set-index-options.md) </span><span class="sxs-lookup"><span data-stu-id="23d79-136">[Set Index Options](set-index-options.md) </span></span>  
 [<span data-ttu-id="23d79-137">Ridenominazione di indici</span><span class="sxs-lookup"><span data-stu-id="23d79-137">Rename Indexes</span></span>](indexes.md)  
  
  
