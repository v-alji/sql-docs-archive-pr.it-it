---
title: Copiare colonne da una tabella a un'altra (motore di database) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- copying columns
- columns [SQL Server], copying
ms.assetid: 5f5e70dc-69f9-44b8-bc48-b5d51ac20d77
author: stevestein
ms.author: sstein
ms.openlocfilehash: 37b98bf0910cbbb4c2a1d7fe01f11d52703ec88c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638356"
---
# <a name="copy-columns-from-one-table-to-another-database-engine"></a><span data-ttu-id="0aad4-102">Copia di colonne da una tabella a un'altra (Motore di database)</span><span class="sxs-lookup"><span data-stu-id="0aad4-102">Copy Columns from One Table to Another (Database Engine)</span></span>
  <span data-ttu-id="0aad4-103">In questo argomento viene illustrato come copiare colonne di una tabella a un'altra copiando solo la definizione di colonna oppure la definizione e i dati in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0aad4-103">This topic describes how to copy columns from one table to another, copying either just the column definition, or the definition and data in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="0aad4-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="0aad4-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0aad4-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="0aad4-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0aad4-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="0aad4-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="0aad4-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="0aad4-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0aad4-108">**Per copiare le colonne tramite:**</span><span class="sxs-lookup"><span data-stu-id="0aad4-108">**To coy columns, using:**</span></span>  
  
     [<span data-ttu-id="0aad4-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0aad4-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0aad4-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0aad4-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0aad4-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="0aad4-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="0aad4-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="0aad4-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="0aad4-113">Quando si copia una colonna contenente un tipo di dati alias da un database a un altro, il tipo di dati alias potrebbe non essere disponibile nel database di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0aad4-113">When you copy a column that has an alias data type from one database to another, the alias data type may not be available in the destination database.</span></span> <span data-ttu-id="0aad4-114">In questo caso, alla colonna verrà assegnato il tipo di dati di base più simile tra quelli disponibili nel database.</span><span class="sxs-lookup"><span data-stu-id="0aad4-114">In such a case, the column will be assigned the nearest matching base data type available in that database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0aad4-115">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="0aad4-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0aad4-116">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="0aad4-116">Permissions</span></span>  
 <span data-ttu-id="0aad4-117">È necessario disporre dell'autorizzazione ALTER per la tabella.</span><span class="sxs-lookup"><span data-stu-id="0aad4-117">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0aad4-118">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0aad4-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-copy-column-definitions-from-one-table-to-another"></a><span data-ttu-id="0aad4-119">Per copiare le definizioni delle colonne tra tabelle</span><span class="sxs-lookup"><span data-stu-id="0aad4-119">To copy column definitions from one table to another</span></span>  
  
1.  <span data-ttu-id="0aad4-120">Aprire la tabella contenente le colonne da copiare e quella in cui verranno copiate le colonne facendo clic con il pulsante destro del mouse sulle tabelle, quindi scegliendo **Progetta**.</span><span class="sxs-lookup"><span data-stu-id="0aad4-120">Open the table with columns you want to copy and the one you want to copy into by right-clicking the tables, and then clicking **Design**.</span></span>  
  
2.  <span data-ttu-id="0aad4-121">Fare clic sulla scheda relativa alla tabella contenente le colonne da copiare e selezionarle.</span><span class="sxs-lookup"><span data-stu-id="0aad4-121">Click the tab for the table with the columns you want to copy and select those columns.</span></span>  
  
3.  <span data-ttu-id="0aad4-122">Scegliere **Copia** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="0aad4-122">From the **Edit** menu, click **Copy**.</span></span>  
  
4.  <span data-ttu-id="0aad4-123">Fare clic sulla scheda relativa alla tabella in cui copiare le colonne.</span><span class="sxs-lookup"><span data-stu-id="0aad4-123">Click the tab for the table into which you want to copy the columns.</span></span>  
  
5.  <span data-ttu-id="0aad4-124">Selezionare la colonna prima della quale si desidera che vengano inserite le colonne appena copiate, quindi scegliere **Incolla** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="0aad4-124">Select the column you want to follow the inserted columns and, from the **Edit** menu, click **Paste**.</span></span>  
  
#### <a name="to-copy-data-from-one-table-to-another"></a><span data-ttu-id="0aad4-125">Per copiare dati tra tabelle</span><span class="sxs-lookup"><span data-stu-id="0aad4-125">To copy data from one table to another</span></span>  
  
1.  <span data-ttu-id="0aad4-126">Seguire le istruzioni sopra riportate per copiare le definizioni delle colonne.</span><span class="sxs-lookup"><span data-stu-id="0aad4-126">Follow the directions for copying column definitions above.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0aad4-127">Prima di iniziare a copiare i dati da una tabella a un'altra, assicurarsi che i tipi di dati delle colonne di destinazione siano compatibili con quelli delle colonne di origine.</span><span class="sxs-lookup"><span data-stu-id="0aad4-127">Before you begin to copy data from one table to another, make sure that the data types in the destination columns are compatible with the data types of the source columns</span></span>  
  
2.  <span data-ttu-id="0aad4-128">In Esplora oggetti selezionare con il pulsante destro del mouse il nodo **Viste** , quindi scegliere **Nuova vista**.</span><span class="sxs-lookup"><span data-stu-id="0aad4-128">In Object Explorer, right-click the **Views** node, and then click **New View**.</span></span>  
  
3.  <span data-ttu-id="0aad4-129">Scegliere **Modifica tipo** dal menu **Progettazione query**, quindi **Accodamento**.</span><span class="sxs-lookup"><span data-stu-id="0aad4-129">From the **Query Designer** menu, point to **Change Type**, and then click **Insert Results**.</span></span>  
  
4.  <span data-ttu-id="0aad4-130">Nella finestra di dialogo **Scegliere la tabella di destinazione per Accodamento** selezionare la tabella in cui si desidera copiare i dati, quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="0aad4-130">In the **Choose Target Table for Insert Results** dialog box, select the table into which you want to copy the data, and then click **OK**.</span></span>  
  
     <span data-ttu-id="0aad4-131">Se si sta effettuando la copia di righe all'interno di una stessa tabella, sarà possibile aggiungere la tabella di origine come tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0aad4-131">If you are copying rows within a table, you can add the source table as a destination table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0aad4-132">In**Progettazione query** non è possibile stabilire in anticipo le tabelle e le viste da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="0aad4-132">**Query Designer** cannot determine in advance which tables and views you can update.</span></span> <span data-ttu-id="0aad4-133">Pertanto, nell'elenco delle tabelle nella finestra di dialogo **Scegliere la tabella di destinazione per Accodamento** sono visualizzate tutte le tabelle e le viste disponibili nella connessione dati su cui si esegue la query, anche quelle che potrebbero non essere valide come tabelle o viste di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0aad4-133">Therefore, the list of tables in the **Choose Target Table for Insert Results** dialog box shows all available tables and views in the data connection you are querying, even those that you might not be able to copy rows to.</span></span>  
  
5.  <span data-ttu-id="0aad4-134">Fare clic con il pulsante destro del mouse nel corpo del riquadro Diagramma, quindi scegliere **Aggiungi tabella a diagramma**dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="0aad4-134">Right-click in the body of the diagram pane and, from the shortcut menu, click **Add Table to Diagram**.</span></span>  
  
6.  <span data-ttu-id="0aad4-135">Nella finestra di dialogo **Aggiungi tabella** selezionare le singole tabelle da cui si desidera copiare i dati, fare clic su **Aggiungi**, quindi su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="0aad4-135">In the **Add Table** dialog box, select each table from which you want to copy data, click **Add**, and then click **Close**.</span></span>  
  
     <span data-ttu-id="0aad4-136">Le tabelle verranno visualizzate in forma abbreviata nel riquadro Diagramma.</span><span class="sxs-lookup"><span data-stu-id="0aad4-136">The tables, in an abbreviated form, appear in the diagram pane.</span></span>  
  
7.  <span data-ttu-id="0aad4-137">Nelle tabelle in forma abbreviata selezionare le caselle relative alle colonne da cui si desidera copiare i dati.</span><span class="sxs-lookup"><span data-stu-id="0aad4-137">In the abbreviated tables, check the boxes for any columns from which you want to copy data.</span></span>  
  
8.  <span data-ttu-id="0aad4-138">Nella colonna **Accodamento** del riquadro Criteri selezionare per ogni colonna di destinazione una colonna da cui copiare i dati.</span><span class="sxs-lookup"><span data-stu-id="0aad4-138">In the criteria pane, in the **Append** column, for each target column choose a column from which you want to copy data.</span></span>  
  
9. <span data-ttu-id="0aad4-139">Specificare le righe da copiare immettendo le condizioni di ricerca nel riquadro Criteri.</span><span class="sxs-lookup"><span data-stu-id="0aad4-139">Specify the rows to copy by entering search conditions in the criteria pane.</span></span> <span data-ttu-id="0aad4-140">Per i dettagli, vedere [Definire condizioni di ricerca &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0aad4-140">For details, see [Specify Search Conditions &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="0aad4-141">Se non si specifica alcuna condizione di ricerca, tutte le righe della tabella di origine verranno copiate nella tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0aad4-141">If you do not specify a search condition, all rows from the source table will be copied to the destination table.</span></span>  
  
10. <span data-ttu-id="0aad4-142">Se si desidera copiare le informazioni di riepilogo, specificare le opzioni **di raggruppamento** .</span><span class="sxs-lookup"><span data-stu-id="0aad4-142">If you want to copy summary information, specify **Group By** options.</span></span> <span data-ttu-id="0aad4-143">Per i dettagli, vedere [Riepilogare o aggregare valori per tutte le righe di una tabella &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/summarize-or-aggregate-values-for-all-rows-in-a-table-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0aad4-143">For details, see [Summarize or Aggregate Values for All Rows in a Table &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/summarize-or-aggregate-values-for-all-rows-in-a-table-visual-database-tools.md).</span></span>  
  
11. <span data-ttu-id="0aad4-144">Scegliere il pulsante **Esegui SQL** per eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="0aad4-144">Click the **Execute SQL button** to run the query.</span></span>  
  
     <span data-ttu-id="0aad4-145">Quando si esegue una query di Accodamento, non viene restituito alcun risultato nel [riquadro risultati](../../ssms/visual-db-tools/results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0aad4-145">When you execute an insert results query, no results are reported in the [Results Pane](../../ssms/visual-db-tools/results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="0aad4-146">Viene invece visualizzato un messaggio che indica il numero di righe copiate.</span><span class="sxs-lookup"><span data-stu-id="0aad4-146">Instead, a message appears indicating how many rows were copied.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0aad4-147">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0aad4-147">Using Transact-SQL</span></span>  
  
#### <a name="to-copy-column-definitions-from-one-table-to-another"></a><span data-ttu-id="0aad4-148">Per copiare le definizioni delle colonne tra tabelle</span><span class="sxs-lookup"><span data-stu-id="0aad4-148">To copy column definitions from one table to another</span></span>  
  
1.  <span data-ttu-id="0aad4-149">Non è possibile copiare singole colonne da una tabella a un'altra tramite istruzioni Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="0aad4-149">You cannot copy individual columns from one table to another existing table by using Transact-SQL statements.</span></span> <span data-ttu-id="0aad4-150">È tuttavia possibile creare una nuova tabella nel filegroup predefinito e inserirvi le righe restituite dalla query.</span><span class="sxs-lookup"><span data-stu-id="0aad4-150">However, you can create a new table in the default filegroup and inserts the resulting rows from the query into it by using SELECT INTO.</span></span> <span data-ttu-id="0aad4-151">Per altre informazioni, vedere [Clausola INTO &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-into-clause-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0aad4-151">For more information, see [INTO Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-into-clause-transact-sql).</span></span>  
  
#### <a name="to-copy-data-from-one-table-to-another"></a><span data-ttu-id="0aad4-152">Per copiare dati tra tabelle</span><span class="sxs-lookup"><span data-stu-id="0aad4-152">To copy data from one table to another</span></span>  
  
1.  <span data-ttu-id="0aad4-153">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0aad4-153">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0aad4-154">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="0aad4-154">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0aad4-155">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="0aad4-155">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE dbo.EmployeeSales  
    ( BusinessEntityID   varchar(11) NOT NULL,  
      SalesYTD money NOT NULL  
    );  
    GO  
    INSERT INTO dbo.EmployeeSales  
        SELECT BusinessEntityID, SalesYTD   
        FROM Sales.SalesPerson;  
    GO  
    ```  
  
  
