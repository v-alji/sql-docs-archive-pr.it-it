---
title: Ottimizzazione della tabella NewOrg | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- optimizing tables
ms.assetid: 89ff6d37-94c0-4773-8be9-dde943fff023
author: stevestein
ms.author: sstein
ms.openlocfilehash: 39c09a3a73051e7a61f3a62a125232d83d1570c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623101"
---
# <a name="optimizing-the-neworg-table"></a><span data-ttu-id="06c7d-102">Ottimizzazione della tabella NewOrg</span><span class="sxs-lookup"><span data-stu-id="06c7d-102">Optimizing the NewOrg Table</span></span>
  <span data-ttu-id="06c7d-103">La tabella **NewOrd** creata nell'attività popolamento di [una tabella con dati gerarchici esistenti](lesson-1-2-populating-a-table-with-existing-hierarchical-data.md) contiene tutte le informazioni sui dipendenti e rappresenta la struttura gerarchica utilizzando un `hierarchyid` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="06c7d-103">The **NewOrd** table that you created in the [Populating a Table with Existing Hierarchical Data](lesson-1-2-populating-a-table-with-existing-hierarchical-data.md) task contains all the employee information, and represents the hierarchical structure by using a `hierarchyid` data type.</span></span> <span data-ttu-id="06c7d-104">Questa attività aggiunge indici nuovi per supportare ricerche nella colonna `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="06c7d-104">This task adds new indexes to support searches on the `hierarchyid` column.</span></span>  
  
## <a name="clustered-index"></a><span data-ttu-id="06c7d-105">Indice cluster</span><span class="sxs-lookup"><span data-stu-id="06c7d-105">Clustered Index</span></span>  
 <span data-ttu-id="06c7d-106">La `hierarchyid` colonna (**OrgNode**) è la chiave primaria per la tabella **NewOrg** .</span><span class="sxs-lookup"><span data-stu-id="06c7d-106">The `hierarchyid` column (**OrgNode**) is the primary key for the **NewOrg** table.</span></span> <span data-ttu-id="06c7d-107">Quando la tabella è stata creata, conteneva un indice cluster denominato **PK_NewOrg_OrgNode** per applicare l'univocità della colonna **OrgNode** .</span><span class="sxs-lookup"><span data-stu-id="06c7d-107">When the table was created, it contained a clustered index named **PK_NewOrg_OrgNode** to enforce the uniqueness of the **OrgNode** column.</span></span> <span data-ttu-id="06c7d-108">Questo indice cluster supporta anche una ricerca in profondità nella tabella.</span><span class="sxs-lookup"><span data-stu-id="06c7d-108">This clustered index also supports a depth-first search of the table.</span></span>  
  
## <a name="nonclustered-index"></a><span data-ttu-id="06c7d-109">Indice non cluster</span><span class="sxs-lookup"><span data-stu-id="06c7d-109">Nonclustered Index</span></span>  
 <span data-ttu-id="06c7d-110">Questo passaggio crea due indici non cluster per supportare le ricerche tipiche.</span><span class="sxs-lookup"><span data-stu-id="06c7d-110">This step creates two nonclustered indexes to support typical searches.</span></span>  
  
#### <a name="to-index-the-neworg-table-for-efficient-searches"></a><span data-ttu-id="06c7d-111">Per indicizzare la tabella NewOrg per eseguire ricerche efficienti</span><span class="sxs-lookup"><span data-stu-id="06c7d-111">To index the NewOrg table for efficient searches</span></span>  
  
1.  <span data-ttu-id="06c7d-112">Per facilitare le query allo stesso livello nella gerarchia, usare il metodo [GetLevel](/sql/t-sql/data-types/getlevel-database-engine) per creare una colonna calcolata contenente il livello della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="06c7d-112">To help queries at the same level in the hierarchy, use the [GetLevel](/sql/t-sql/data-types/getlevel-database-engine) method to create a computed column that contains the level in the hierarchy.</span></span> <span data-ttu-id="06c7d-113">Successivamente, creare un indice composto nel livello e `Hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="06c7d-113">Then, create a composite index on the level and the `Hierarchyid`.</span></span> <span data-ttu-id="06c7d-114">Eseguire il codice seguente per creare la colonna calcolata e l'indice breadth-first:</span><span class="sxs-lookup"><span data-stu-id="06c7d-114">Run the following code to create the computed column and the breadth-first index:</span></span>  
  
    ```  
    ALTER TABLE NewOrg   
       ADD H_Level AS OrgNode.GetLevel() ;  
    CREATE UNIQUE INDEX EmpBFInd   
       ON NewOrg(H_Level, OrgNode) ;  
    GO  
    ```  
  
2.  <span data-ttu-id="06c7d-115">Creare un indice univoco nella colonna **EmployeeID** .</span><span class="sxs-lookup"><span data-stu-id="06c7d-115">Create a unique index on the **EmployeeID** column.</span></span> <span data-ttu-id="06c7d-116">Si tratta della ricerca singleton tradizionale di un solo dipendente in base al numero **EmployeeID** .</span><span class="sxs-lookup"><span data-stu-id="06c7d-116">This is the traditional singleton lookup of a single employee by **EmployeeID** number.</span></span> <span data-ttu-id="06c7d-117">Eseguire il codice seguente per creare un indice in **EmployeeID**:</span><span class="sxs-lookup"><span data-stu-id="06c7d-117">Run the following code to create an index on **EmployeeID**:</span></span>  
  
    ```  
    CREATE UNIQUE INDEX EmpIDs_unq ON NewOrg(EmployeeID) ;  
    GO  
    ```  
  
3.  <span data-ttu-id="06c7d-118">Eseguire il codice seguente per recuperare i dati dalla tabella nell'ordine di ognuno dei tre indici:</span><span class="sxs-lookup"><span data-stu-id="06c7d-118">Run the following code to retrieve data from the table in the order of each of the three indexes:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS LogicalNode,  
    OrgNode, H_Level, EmployeeID, LoginID  
    FROM NewOrg   
    ORDER BY OrgNode;  
  
    SELECT OrgNode.ToString() AS LogicalNode,  
    OrgNode, H_Level, EmployeeID, LoginID   
    FROM NewOrg   
    ORDER BY H_Level, OrgNode;  
  
    SELECT OrgNode.ToString() AS LogicalNode,  
    OrgNode, H_Level, EmployeeID, LoginID   
    FROM NewOrg   
    ORDER BY EmployeeID;  
    GO  
    ```  
  
4.  <span data-ttu-id="06c7d-119">Confrontare i set di risultati per visualizzare il modo in cui l'ordine viene archiviato in ogni tipo di indice.</span><span class="sxs-lookup"><span data-stu-id="06c7d-119">Compare the result sets to see how the order is stored in each type of index.</span></span> <span data-ttu-id="06c7d-120">Seguono solo le prime quattro righe di ogni output.</span><span class="sxs-lookup"><span data-stu-id="06c7d-120">Only the first four rows of each output follow.</span></span>  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
     <span data-ttu-id="06c7d-121">Indice depth-first: i record relativi ai dipendenti vengono archiviati accanto al responsabile.</span><span class="sxs-lookup"><span data-stu-id="06c7d-121">Depth-first index: Employee records are stored adjacent to their manager.</span></span>  
  
     `LogicalNode OrgNode    H_Level EmployeeID LoginID`  
  
     `/             0x         0         1      zarifin`  
  
     `/1/          0x58        1         2      tplate`  
  
     `/1/1/       0x5AC0       2         4      schai`  
  
     `/1/1/1/     0x5AD6       3         9      jwang`  
  
     `/1/1/2/     0x5ADA       3        10      malexander`  
  
     `/1/2/       0x5B40       2         5      elang`  
  
     `/1/3/       0x5BC0       2         6      gsmits`  
  
     `/2/         0x68         1         3      hjensen`  
  
     `/2/1/       0x6AC0       2         7      sdavis`  
  
     `/2/2/       0x6B40       2         8      norint`  
  
     <span data-ttu-id="06c7d-122">**Indice EmployeeID**-first: le righe vengono archiviate nella sequenza di **EmployeeID** .</span><span class="sxs-lookup"><span data-stu-id="06c7d-122">**EmployeeID**-first index: Rows are stored in **EmployeeID** sequence.</span></span>  
  
     `LogicalNode OrgNode    H_Level EmployeeID LoginID`  
  
     `/             0x         0         1      zarifin`  
  
     `/1/          0x58        1         2      tplate`  
  
     `/2/         0x68         1         3      hjensen`  
  
     `/1/1/       0x5AC0       2         4      schai`  
  
     `/1/2/       0x5B40       2         5      elang`  
  
     `/1/3/       0x5BC0       2         6      gsmits`  
  
     `/2/1/       0x6AC0       2         7      sdavis`  
  
     `/2/2/       0x6B40       2         8      norint`  
  
     `/1/1/1/     0x5AD6       3         9      jwang`  
  
     `/1/1/2/     0x5ADA       3        10      malexander`  
  
> [!NOTE]  
>  <span data-ttu-id="06c7d-123">Per i diagrammi che indicano la differenza tra un indice depth-first e un indice breadth-first, vedere [Dati gerarchici &#40;SQL Server&#41;](../hierarchical-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="06c7d-123">For diagrams that show the difference between a depth-first index and a breadth-first index, see [Hierarchical Data &#40;SQL Server&#41;](../hierarchical-data-sql-server.md).</span></span>  
  
#### <a name="to-drop-the-unnecessary-columns"></a><span data-ttu-id="06c7d-124">Per eliminare le colonne non necessarie</span><span class="sxs-lookup"><span data-stu-id="06c7d-124">To drop the unnecessary columns</span></span>  
  
1.  <span data-ttu-id="06c7d-125">La colonna **ManagerID** rappresenta la relazione dipendente/responsabile che ora è rappresentata dalla colonna **OrgNode** .</span><span class="sxs-lookup"><span data-stu-id="06c7d-125">The **ManagerID** column represents the employee/manager relationship, which is now represented by the **OrgNode** column.</span></span> <span data-ttu-id="06c7d-126">Se le altre applicazioni non richiedono la colonna **ManagerID** , si consiglia di eliminarla usando l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="06c7d-126">If other applications do not need the **ManagerID** column, consider dropping it by using the following statement:</span></span>  
  
    ```  
    ALTER TABLE NewOrg DROP COLUMN ManagerID ;  
    GO  
    ```  
  
2.  <span data-ttu-id="06c7d-127">La colonna **EmployeeID** è anche ridondante.</span><span class="sxs-lookup"><span data-stu-id="06c7d-127">The **EmployeeID** column is also redundant.</span></span> <span data-ttu-id="06c7d-128">La colonna **OrgNode** identifica in modo univoco ogni dipendente.</span><span class="sxs-lookup"><span data-stu-id="06c7d-128">The **OrgNode** column uniquely identifies each employee.</span></span> <span data-ttu-id="06c7d-129">Se le altre applicazioni non richiedono la colonna **EmployeeID** , eliminare l'indice e successivamente la colonna usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="06c7d-129">If other applications do not need the **EmployeeID** column, consider dropping the index and then the column by using the following code:</span></span>  
  
    ```  
    DROP INDEX EmpIDs_unq ON NewOrg ;  
    ALTER TABLE NewOrg DROP COLUMN EmployeeID ;  
    GO  
    ```  
  
#### <a name="to-replace-the-original-table-with-the-new-table"></a><span data-ttu-id="06c7d-130">Per sostituire la tabella originale con la tabella nuova</span><span class="sxs-lookup"><span data-stu-id="06c7d-130">To replace the original table with the new table</span></span>  
  
1.  <span data-ttu-id="06c7d-131">Se la tabella originale contiene vincoli o indici aggiuntivi, aggiungerli alla tabella **NewOrg** .</span><span class="sxs-lookup"><span data-stu-id="06c7d-131">If your original table contained any additional indexes or constraints, add them to the **NewOrg** table.</span></span>  
  
2.  <span data-ttu-id="06c7d-132">Sostituire la vecchia colonna **EmployeeDemo** con la nuova tabella.</span><span class="sxs-lookup"><span data-stu-id="06c7d-132">Replace the old **EmployeeDemo** table with the new table.</span></span> <span data-ttu-id="06c7d-133">Eseguire il codice seguente per rilasciare la vecchia tabella e successivamente rinominare la tabella nuova con il nome vecchio:</span><span class="sxs-lookup"><span data-stu-id="06c7d-133">Run the following code to drop the old table, and then rename the new table with the old name:</span></span>  
  
    ```  
    DROP TABLE EmployeeDemo ;  
    GO  
    sp_rename 'NewOrg', EmployeeDemo ;  
    GO  
    ```  
  
3.  <span data-ttu-id="06c7d-134">Eseguire il codice seguente per esaminare la tabella finale:</span><span class="sxs-lookup"><span data-stu-id="06c7d-134">Run the following code to examine the final table:</span></span>  
  
    ```  
    SELECT * FROM EmployeeDemo ;  
    ```  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="06c7d-135">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="06c7d-135">Next Task in Lesson</span></span>  
 [<span data-ttu-id="06c7d-136">Riepilogo: Conversione di una tabella in una struttura gerarchica</span><span class="sxs-lookup"><span data-stu-id="06c7d-136">Summary: Converting a Table to a Hierarchical Structure</span></span>](lesson-1-4-summary-converting-a-table-to-a-hierarchical-structure.md)  
  
  
