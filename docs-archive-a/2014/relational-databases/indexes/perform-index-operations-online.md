---
title: Eseguire operazioni online sugli indici | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index online operations [SQL Server]
- online index operations
- ONLINE option
ms.assetid: 1e43537c-bf67-4db3-9908-3cb45c6fdaa1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4d09bd99a0eaec5fdb433bd8c33351d7622957a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637300"
---
# <a name="perform-index-operations-online"></a><span data-ttu-id="e9f03-102">Eseguire operazioni online sugli indici</span><span class="sxs-lookup"><span data-stu-id="e9f03-102">Perform Index Operations Online</span></span>
  <span data-ttu-id="e9f03-103">In questo argomento si illustra come creare, ricompilare o eliminare gli indici online in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9f03-103">This topic describes how to create, rebuild, or drop indexes online in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="e9f03-104">L'opzione ONLINE consente l'accesso simultaneo degli utenti alla tabella sottostante o ai dati dell'indice cluster e a qualsiasi indice non cluster associato durante l'esecuzione di queste operazioni sugli indici.</span><span class="sxs-lookup"><span data-stu-id="e9f03-104">The ONLINE option allows concurrent user access to the underlying table or clustered index data and any associated nonclustered indexes during these index operations.</span></span> <span data-ttu-id="e9f03-105">Durante la ricompilazione di un indice cluster da parte di un utente, ad esempio, tale utente e altri utenti possono continuare ad aggiornare ed eseguire query sui dati sottostanti.</span><span class="sxs-lookup"><span data-stu-id="e9f03-105">For example, while a clustered index is being rebuilt by one user, that user and others can continue to update and query the underlying data.</span></span> <span data-ttu-id="e9f03-106">Quando si eseguono operazioni DDL (Data Definition Language) offline, ad esempio la compilazione o la ricompilazione di un indice cluster, tali operazioni mantengono blocchi esclusivi sui dati sottostanti e gli indici associati.</span><span class="sxs-lookup"><span data-stu-id="e9f03-106">When you perform data definition language (DDL) operations offline, such as building or rebuilding a clustered index; these operations hold exclusive locks on the underlying data and associated indexes.</span></span> <span data-ttu-id="e9f03-107">Questo comportamento impedisce modifiche e query nei dati sottostanti fino al termine dell'operazione sull'indice.</span><span class="sxs-lookup"><span data-stu-id="e9f03-107">This prevents modifications and queries to the underlying data until the index operation is complete.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e9f03-108">Le operazioni sugli indici online sono disponibili solo in alcune edizioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9f03-108">Online index operations are not available in every [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] edition.</span></span> <span data-ttu-id="e9f03-109">Per ulteriori informazioni, vedere [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="e9f03-109">For more information, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="e9f03-110">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="e9f03-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e9f03-111">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="e9f03-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e9f03-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="e9f03-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e9f03-113">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e9f03-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e9f03-114">**Per ricompilare un indice online tramite:**</span><span class="sxs-lookup"><span data-stu-id="e9f03-114">**To rebuild an index online, using:**</span></span>  
  
     [<span data-ttu-id="e9f03-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e9f03-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e9f03-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e9f03-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e9f03-117">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e9f03-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e9f03-118">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="e9f03-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="e9f03-119">È consigliabile eseguire operazioni online sugli indici per ambiti aziendali in funzione 24 ore al giorno e sette giorni su sette, in cui l'esigenza di attività simultanee durante le operazioni sugli indici rappresenta un elemento essenziale.</span><span class="sxs-lookup"><span data-stu-id="e9f03-119">We recommend performing online index operations for business environments that operate 24 hours a day, seven days a week, in which the need for concurrent user activity during index operations is vital.</span></span>  
  
-   <span data-ttu-id="e9f03-120">L'opzione ONLINE è disponibile nelle istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] seguenti.</span><span class="sxs-lookup"><span data-stu-id="e9f03-120">The ONLINE option is available in the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
    -   [<span data-ttu-id="e9f03-121">CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="e9f03-121">CREATE INDEX</span></span>](/sql/t-sql/statements/create-index-transact-sql)  
  
    -   [<span data-ttu-id="e9f03-122">ALTER INDEX</span><span class="sxs-lookup"><span data-stu-id="e9f03-122">ALTER INDEX</span></span>](/sql/t-sql/statements/alter-index-transact-sql)  
  
    -   [<span data-ttu-id="e9f03-123">DROP INDEX</span><span class="sxs-lookup"><span data-stu-id="e9f03-123">DROP INDEX</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
    -   <span data-ttu-id="e9f03-124">[ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) (per aggiungere o eliminare vincoli UNIQUE o PRIMARY KEY con l'opzione di indice CLUSTERED)</span><span class="sxs-lookup"><span data-stu-id="e9f03-124">[ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) (To add or drop UNIQUE or PRIMARY KEY constraints with CLUSTERED index option)</span></span>  
  
-   <span data-ttu-id="e9f03-125">Per altre limitazioni e restrizioni relative alla creazione, alla ricompilazione o all'eliminazione degli indici online, vedere [Linee guida per le operazioni di indice online](guidelines-for-online-index-operations.md).</span><span class="sxs-lookup"><span data-stu-id="e9f03-125">For more limitations and restrictions concerning creating, rebuilding, or dropping indexes online, see [Guidelines for Online Index Operations](guidelines-for-online-index-operations.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e9f03-126">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e9f03-126">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e9f03-127">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="e9f03-127">Permissions</span></span>  
 <span data-ttu-id="e9f03-128">È richiesta l'autorizzazione ALTER per la tabella o la vista.</span><span class="sxs-lookup"><span data-stu-id="e9f03-128">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e9f03-129">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e9f03-129">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rebuild-an-index-online"></a><span data-ttu-id="e9f03-130">Per ricompilare un indice online</span><span class="sxs-lookup"><span data-stu-id="e9f03-130">To rebuild an index online</span></span>  
  
1.  <span data-ttu-id="e9f03-131">In Esplora oggetti fare clic sul segno più per espandere il database contenente la tabella in cui si desidera ricompilare un indice online.</span><span class="sxs-lookup"><span data-stu-id="e9f03-131">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to rebuild an index online.</span></span>  
  
2.  <span data-ttu-id="e9f03-132">Espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="e9f03-132">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="e9f03-133">Fare clic sul segno più per espandere la tabella in cui si desidera ricompilare un indice online.</span><span class="sxs-lookup"><span data-stu-id="e9f03-133">Click the plus sign to expand the table on which you want to rebuild an index online.</span></span>  
  
4.  <span data-ttu-id="e9f03-134">Espandere la cartella **Indici** .</span><span class="sxs-lookup"><span data-stu-id="e9f03-134">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="e9f03-135">Fare clic con il pulsante destro del mouse sull'indice da ricompilare online e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="e9f03-135">Right-click the index that you want to rebuild online and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="e9f03-136">In **Selezione pagina**selezionare **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="e9f03-136">Under **Select a page**, select **Options**.</span></span>  
  
7.  <span data-ttu-id="e9f03-137">Selezionare **Consenti elaborazione DML online**, quindi selezionare **True** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="e9f03-137">Select **Allow online DML processing**, and then select **True** from the list.</span></span>  
  
8.  <span data-ttu-id="e9f03-138">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9f03-138">Click **OK**.</span></span>  
  
9. <span data-ttu-id="e9f03-139">Fare clic con il pulsante destro del mouse sull'indice da ricompilare online e selezionare **Ricompila**.</span><span class="sxs-lookup"><span data-stu-id="e9f03-139">Right-click the index that you want to rebuild online and select **Rebuild**.</span></span>  
  
10. <span data-ttu-id="e9f03-140">Nella finestra di dialogo **Ricompila indici** verificare che nella griglia **Indici da ricompilare** sia presente l'indice corretto e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9f03-140">In the **Rebuild Indexes** dialog box, verify that the correct index is in the **Indexes to rebuild** grid and click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e9f03-141">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e9f03-141">Using Transact-SQL</span></span>  
  
#### <a name="to-create-rebuild-or-drop-an-index-online"></a><span data-ttu-id="e9f03-142">Per creare, ricompilare o eliminare un indice online</span><span class="sxs-lookup"><span data-stu-id="e9f03-142">To create, rebuild, or drop an index online</span></span>  
  
1.  <span data-ttu-id="e9f03-143">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9f03-143">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e9f03-144">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="e9f03-144">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e9f03-145">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="e9f03-145">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="e9f03-146">Nell'esempio viene ricompilato un indice online esistente</span><span class="sxs-lookup"><span data-stu-id="e9f03-146">The example rebuilds an existing online</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER INDEX AK_Employee_NationalIDNumber ON HumanResources.Employee  
    REBUILD WITH (ONLINE = ON);  
    GO  
    ```  
  
     <span data-ttu-id="e9f03-147">Nell'esempio seguente viene eliminato un indice cluster online e la tabella risultante (heap) viene spostata nel filegroup `NewGroup` tramite la clausola `MOVE TO` .</span><span class="sxs-lookup"><span data-stu-id="e9f03-147">The following example deletes a clustered index online and moves the resulting table (heap) to the filegroup `NewGroup` by using the `MOVE TO` clause.</span></span> <span data-ttu-id="e9f03-148">Vengono eseguite query sulle viste del catalogo `sys.indexes`, `sys.tables`e `sys.filegroups` per verificare la posizione dell'indice e della tabella nei filegroup prima e dopo lo spostamento.</span><span class="sxs-lookup"><span data-stu-id="e9f03-148">The `sys.indexes`, `sys.tables`, and `sys.filegroups` catalog views are queried to verify the index and table placement in the filegroups before and after the move.</span></span>  
  
     [!code-sql[IndexDDL#DropIndex4](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/dropindex.sql#dropindex4)]  
  
 <span data-ttu-id="e9f03-149">Per altre informazioni, vedere [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e9f03-149">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
  
