---
title: Popolamento di una tabella con dati gerarchici esistenti | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: fd943d84-dbe6-4a05-912b-c88164998d80
author: stevestein
ms.author: sstein
ms.openlocfilehash: 966548b11ad4697abc06de5c5c239a511f80b7af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713024"
---
# <a name="populating-a-table-with-existing-hierarchical-data"></a><span data-ttu-id="68509-102">Popolamento di una tabella con dati gerarchici esistenti</span><span class="sxs-lookup"><span data-stu-id="68509-102">Populating a Table with Existing Hierarchical Data</span></span>
  <span data-ttu-id="68509-103"> Questa attività consente di creare una nuova tabella e popolarla con i dati della tabella **EmployeeDemo**.</span><span class="sxs-lookup"><span data-stu-id="68509-103">This task creates a new table and populates it with the data in the **EmployeeDemo** table.</span></span> <span data-ttu-id="68509-104">Questa attività prevede i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="68509-104">This task has the following steps:</span></span>  
  
-   <span data-ttu-id="68509-105">Creare una tabella nuova contenente una colonna `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="68509-105">Create a new table that contains a `hierarchyid` column.</span></span> <span data-ttu-id="68509-106">Questa colonna può sostituire le colonne **EmployeeID** e **ManagerID** esistenti.</span><span class="sxs-lookup"><span data-stu-id="68509-106">This column could replace the existing **EmployeeID** and **ManagerID** columns.</span></span> <span data-ttu-id="68509-107">Tuttavia, tali colonne verranno mantenute.</span><span class="sxs-lookup"><span data-stu-id="68509-107">However, you will retain those columns.</span></span> <span data-ttu-id="68509-108">Questo avviene perché le applicazioni esistenti potrebbero riferirsi a tali colonne e potrebbero aiutare a capire i dati dopo il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="68509-108">This is because existing applications might refer to those columns, and also to help you understand the data after the transfer.</span></span> <span data-ttu-id="68509-109">La definizione della tabella specifica che **OrgNode** è la chiave primaria che richiede alla colonna di contenere i valori univoci.</span><span class="sxs-lookup"><span data-stu-id="68509-109">The table definition specifies that **OrgNode** is the primary key, which requires the column to contain unique values.</span></span> <span data-ttu-id="68509-110">L'indice cluster della colonna **OrgNode** archivierà la data nella sequenza **OrgNode** .</span><span class="sxs-lookup"><span data-stu-id="68509-110">The clustered index on the **OrgNode** column will store the date in **OrgNode** sequence.</span></span>  
  
-   <span data-ttu-id="68509-111">Creare una tabella temporanea utilizzata per rilevare il numero di dipendenti che riportano direttamente a ogni responsabile.</span><span class="sxs-lookup"><span data-stu-id="68509-111">Create a temporary table that is used to track how many employees report directly to each manager.</span></span>  
  
-   <span data-ttu-id="68509-112">Popolare la nuova tabella usando i dati dalla tabella **EmployeeDemo** .</span><span class="sxs-lookup"><span data-stu-id="68509-112">Populate the new table by using data from the **EmployeeDemo** table.</span></span>  
  
### <a name="to-create-a-new-table-named-neworg"></a><span data-ttu-id="68509-113">Per creare una nuova tabella denominata NewOrg</span><span class="sxs-lookup"><span data-stu-id="68509-113">To create a new table named NewOrg</span></span>  
  
-   <span data-ttu-id="68509-114">In una finestra dell'editor di query eseguire il codice seguente per creare una nuova tabella denominata **HumanResources.NewOrg**:</span><span class="sxs-lookup"><span data-stu-id="68509-114">In a Query Editor window, run the following code to create a new table named **HumanResources.NewOrg**:</span></span>  
  
    ```  
    CREATE TABLE NewOrg  
    (  
      OrgNode hierarchyid,  
      EmployeeID int,  
      LoginID nvarchar(50),  
      ManagerID int  
    CONSTRAINT PK_NewOrg_OrgNode  
      PRIMARY KEY CLUSTERED (OrgNode)  
    );  
    GO  
    ```  
  
### <a name="to-create-a-temporary-table-named-children"></a><span data-ttu-id="68509-115">Per creare una tabella temporanea denominata #Children</span><span class="sxs-lookup"><span data-stu-id="68509-115">To create a temporary table named #Children</span></span>  
  
1.  <span data-ttu-id="68509-116">Creare una tabella temporanea denominata **#Children** con una colonna denominata **Num** che conterrà il numero di elementi figlio per ogni nodo:</span><span class="sxs-lookup"><span data-stu-id="68509-116">Create a temporary table named **#Children** with a column named **Num** that will contain the number of children for each node:</span></span>  
  
    ```  
    CREATE TABLE #Children   
       (  
        EmployeeID int,  
        ManagerID int,  
        Num int  
    );  
    GO  
    ```  
  
2.  <span data-ttu-id="68509-117">Aggiungere un indice per accelerare significativamente la query che popola la tabella **NewOrg** :</span><span class="sxs-lookup"><span data-stu-id="68509-117">Add an index that will significantly speed up the query that populates the **NewOrg** table:</span></span>  
  
    ```  
    CREATE CLUSTERED INDEX tmpind ON #Children(ManagerID, EmployeeID);  
    GO  
    ```  
  
### <a name="to-populate-the-neworg-table"></a><span data-ttu-id="68509-118">Per popolare la tabella NewOrg</span><span class="sxs-lookup"><span data-stu-id="68509-118">To populate the NewOrg table</span></span>  
  
1.  <span data-ttu-id="68509-119">Le query ricorsive impediscono le sottoquery con aggregazioni.</span><span class="sxs-lookup"><span data-stu-id="68509-119">Recursive queries forbid subqueries with aggregates.</span></span> <span data-ttu-id="68509-120">In alternativa, popolare la tabella **#Children** con il codice seguente che usa il metodo [ROW_NUMBER()](/sql/t-sql/functions/row-number-transact-sql) per popolare la colonna **Num** :</span><span class="sxs-lookup"><span data-stu-id="68509-120">Instead, populate the **#Children** table with the following code, which uses the [ROW_NUMBER()](/sql/t-sql/functions/row-number-transact-sql) method to populate the **Num** column:</span></span>  
  
    ```  
    INSERT #Children (EmployeeID, ManagerID, Num)  
    SELECT EmployeeID, ManagerID,  
      ROW_NUMBER() OVER (PARTITION BY ManagerID ORDER BY ManagerID)   
    FROM EmployeeDemo  
    GO  
  
    ```  
  
2.  <span data-ttu-id="68509-121">Rivedere la tabella **#Children** .</span><span class="sxs-lookup"><span data-stu-id="68509-121">Review the **#Children** table.</span></span> <span data-ttu-id="68509-122">Si noti in che modo la colonna **Num** contiene i numeri sequenziali per ogni responsabile.</span><span class="sxs-lookup"><span data-stu-id="68509-122">Note how the **Num** column contains sequential numbers for each manager.</span></span>  
  
    ```  
    SELECT * FROM #Children ORDER BY ManagerID, Num  
    GO  
  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
     `EmployeeID ManagerID Num`  
  
     `---------- --------- ---`  
  
     `1        NULL       1`  
  
     `2         1         1`  
  
     `3         1         2`  
  
     `4         2         1`  
  
     `5         2         2`  
  
     `6         2         3`  
  
     `7         3         1`  
  
     `8         3         2`  
  
     `9         4         1`  
  
     `10        4         2`  
  
3.  <span data-ttu-id="68509-123">Popolare la tabella **NewOrg** .</span><span class="sxs-lookup"><span data-stu-id="68509-123">Populate the **NewOrg** table.</span></span> <span data-ttu-id="68509-124">Usare i metodi GetRoot e ToString per concatenare i valori **num** nel `hierarchyid` formato e quindi aggiornare la colonna **OrgNode** con i valori gerarchici risultanti:</span><span class="sxs-lookup"><span data-stu-id="68509-124">Use the GetRoot and ToString methods to concatenate the **Num** values into the `hierarchyid` format, and then update the **OrgNode** column with the resultant hierarchical values:</span></span>  
  
    ```  
    WITH paths(path, EmployeeID)   
    AS (  
    -- This section provides the value for the root of the hierarchy  
    SELECT hierarchyid::GetRoot() AS OrgNode, EmployeeID   
    FROM #Children AS C   
    WHERE ManagerID IS NULL   
  
    UNION ALL   
    -- This section provides values for all nodes except the root  
    SELECT   
    CAST(p.path.ToString() + CAST(C.Num AS varchar(30)) + '/' AS hierarchyid),   
    C.EmployeeID  
    FROM #Children AS C   
    JOIN paths AS p   
       ON C.ManagerID = P.EmployeeID   
    )  
    INSERT NewOrg (OrgNode, O.EmployeeID, O.LoginID, O.ManagerID)  
    SELECT P.path, O.EmployeeID, O.LoginID, O.ManagerID  
    FROM EmployeeDemo AS O   
    JOIN Paths AS P   
       ON O.EmployeeID = P.EmployeeID  
    GO  
  
    ```  
  
4.  <span data-ttu-id="68509-125">Una colonna `hierarchyid` è più comprensibile quando viene convertita in un formato carattere.</span><span class="sxs-lookup"><span data-stu-id="68509-125">A `hierarchyid` column is more understandable when you convert it to character format.</span></span> <span data-ttu-id="68509-126">Rivedere i dati nella tabella **NewOrg** eseguendo il codice seguente che contiene due rappresentazioni della colonna **OrgNode** :</span><span class="sxs-lookup"><span data-stu-id="68509-126">Review the data in the **NewOrg** table by executing the following code, which contains two representations of the **OrgNode** column:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS LogicalNode, *   
    FROM NewOrg   
    ORDER BY LogicalNode;  
    GO  
  
    ```  
  
     <span data-ttu-id="68509-127">La colonna **LogicalNode** converte la `hierarchyid` colonna in un formato di testo più leggibile che rappresenta la gerarchia.</span><span class="sxs-lookup"><span data-stu-id="68509-127">The **LogicalNode** column converts the `hierarchyid` column into a more readable text form that represents the hierarchy.</span></span> <span data-ttu-id="68509-128">Nelle attività rimanenti, si utilizzerà il metodo `ToString()` per mostrare il formato logico delle colonne `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="68509-128">In the remaining tasks, you will use the `ToString()` method to show the logical format of the `hierarchyid` columns.</span></span>  
  
5.  <span data-ttu-id="68509-129">Eliminare la tabella temporanea che non risulta più essere necessaria:</span><span class="sxs-lookup"><span data-stu-id="68509-129">Drop the temporary table, which is no longer needed:</span></span>  
  
    ```  
    DROP TABLE #Children  
    GO  
    ```  
  
 <span data-ttu-id="68509-130">L'attività successiva creerà indici per supportare la struttura gerarchica.</span><span class="sxs-lookup"><span data-stu-id="68509-130">The next task will create indexes to support the hierarchical structure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="68509-131">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="68509-131">Next Task in Lesson</span></span>  
 [<span data-ttu-id="68509-132">Ottimizzazione della tabella NewOrg</span><span class="sxs-lookup"><span data-stu-id="68509-132">Optimizing the NewOrg Table</span></span>](lesson-1-3-optimizing-the-neworg-table.md)  
  
  
