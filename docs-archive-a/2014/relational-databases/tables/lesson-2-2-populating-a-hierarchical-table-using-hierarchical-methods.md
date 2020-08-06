---
title: Popolamento di una tabella gerarchica tramite metodi gerarchici | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- HierarchyID
helpviewer_keywords:
- HierarchyID
ms.assetid: 2c95fa60-5b8e-4a05-ac09-cffe2b05900a
author: stevestein
ms.author: sstein
ms.openlocfilehash: ef99d711a772a075f568a83f5d56fcecaaa598f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630404"
---
# <a name="populating-a-hierarchical-table-using-hierarchical-methods"></a><span data-ttu-id="616f2-102">Popolamento di una tabella gerarchica utilizzando metodi gerarchici</span><span class="sxs-lookup"><span data-stu-id="616f2-102">Populating a Hierarchical Table Using Hierarchical Methods</span></span>
  [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] <span data-ttu-id="616f2-103">ha 8 dipendenti che lavorano nel reparto Marketing.</span><span class="sxs-lookup"><span data-stu-id="616f2-103">has 8 employees working in the Marketing department.</span></span> <span data-ttu-id="616f2-104">La gerarchia dei dipendenti è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="616f2-104">The employee hierarchy looks like this:</span></span>  
  
 <span data-ttu-id="616f2-105">**David**, **EmployeeID** 6 è il responsabile marketing.</span><span class="sxs-lookup"><span data-stu-id="616f2-105">**David**, **EmployeeID** 6, is the Marketing Manager.</span></span> <span data-ttu-id="616f2-106">Tre marketing specialist fanno riferimento a **David**:</span><span class="sxs-lookup"><span data-stu-id="616f2-106">Three Marketing Specialists report to **David**:</span></span>  
  
-   <span data-ttu-id="616f2-107">**Sariya**, **EmployeeID** 46</span><span class="sxs-lookup"><span data-stu-id="616f2-107">**Sariya**, **EmployeeID** 46</span></span>  
  
-   <span data-ttu-id="616f2-108">**John**, **EmployeeID** 271</span><span class="sxs-lookup"><span data-stu-id="616f2-108">**John**, **EmployeeID** 271</span></span>  
  
-   <span data-ttu-id="616f2-109">**Jill**, **EmployeeID** 119</span><span class="sxs-lookup"><span data-stu-id="616f2-109">**Jill**, **EmployeeID** 119</span></span>  
  
 <span data-ttu-id="616f2-110">**Wanida** , Marketing Assistant (**EmployeeID** 269), fa riferimento a **Sariya**, mentre **Mary** Marketing Assistant (**EmployeeID** 272), fa riferimento a **John**.</span><span class="sxs-lookup"><span data-stu-id="616f2-110">Marketing Assistant **Wanida** (**EmployeeID** 269), reports to **Sariya**, and Marketing Assistant **Mary** (**EmployeeID** 272), reports to **John**.</span></span>  
  
### <a name="to-insert-the-root-of-the-hierarchy-tree"></a><span data-ttu-id="616f2-111">Per inserire la radice dell'albero gerarchico</span><span class="sxs-lookup"><span data-stu-id="616f2-111">To insert the root of the hierarchy tree</span></span>  
  
1.  <span data-ttu-id="616f2-112">Nell'esempio seguente **David** , il responsabile marketing, è inserito nella tabella alla radice della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="616f2-112">The following example inserts **David** the Marketing Manager into the table at the root of the hierarchy.</span></span> <span data-ttu-id="616f2-113">La colonna **OrdLevel** è una colonna calcolata.</span><span class="sxs-lookup"><span data-stu-id="616f2-113">The **OrdLevel** column is a computed column.</span></span> <span data-ttu-id="616f2-114">Pertanto, non è parte dell'istruzione INSERT.</span><span class="sxs-lookup"><span data-stu-id="616f2-114">Therefore, it is not part of the INSERT statement.</span></span> <span data-ttu-id="616f2-115">Questo primo record usa il metodo [GetRoot()](/sql/t-sql/data-types/getroot-database-engine) per popolarsi come radice della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="616f2-115">This first record uses the [GetRoot()](/sql/t-sql/data-types/getroot-database-engine) method to populate this first record as the root of the hierarchy.</span></span>  
  
    ```  
    INSERT HumanResources.EmployeeOrg (OrgNode, EmployeeID, EmpName, Title)  
    VALUES (hierarchyid::GetRoot(), 6, 'David', 'Marketing Manager') ;  
    GO  
    ```  
  
2.  <span data-ttu-id="616f2-116">Eseguire il seguente codice per esaminare la riga iniziale della tabella:</span><span class="sxs-lookup"><span data-stu-id="616f2-116">Execute the following code to examine initial row in the table:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode, OrgLevel, EmployeeID, EmpName, Title   
    FROM HumanResources.EmployeeOrg ;  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
    ```  
    Text_OrgNode OrgNode OrgLevel EmployeeID EmpName Title  
    ------------ ------- -------- ---------- ------- -----------------  
    /            Ox      0        6          David   Marketing Manager  
    ```  
  
 <span data-ttu-id="616f2-117">Come illustrato nella lezione precedente, si utilizza il metodo `ToString()` per convertire il tipo di dati `hierarchyid` in un formato più facilmente comprensibile.</span><span class="sxs-lookup"><span data-stu-id="616f2-117">As in the previous lesson, we use the `ToString()` method to convert the `hierarchyid` data type to a format that is more easily understood.</span></span>  
  
### <a name="to-insert-a-subordinate-employee"></a><span data-ttu-id="616f2-118">Per inserire un dipendente subordinato</span><span class="sxs-lookup"><span data-stu-id="616f2-118">To insert a subordinate employee</span></span>  
  
1.  <span data-ttu-id="616f2-119">**Sariya** fa riferimento a **David**.</span><span class="sxs-lookup"><span data-stu-id="616f2-119">**Sariya** reports to **David**.</span></span> <span data-ttu-id="616f2-120">Per inserire **il** nodo di Sariya, è necessario creare un valore **OrgNode** appropriato del tipo di dati `hierarchyid` .</span><span class="sxs-lookup"><span data-stu-id="616f2-120">To insert **Sariya's** node, you must create an appropriate **OrgNode** value of data type `hierarchyid`.</span></span> <span data-ttu-id="616f2-121">Il codice seguente crea una variabile di tipo dato `hierarchyid` e la popola con il valore OrgNode radice della tabella.</span><span class="sxs-lookup"><span data-stu-id="616f2-121">The following code creates a variable of data type `hierarchyid` and populates it with the root OrgNode value of the table.</span></span> <span data-ttu-id="616f2-122">A questo punto usa la variabile con il metodo [GetDescendant()](/sql/t-sql/data-types/getdescendant-database-engine) per inserire la riga che è un nodo subordinato.</span><span class="sxs-lookup"><span data-stu-id="616f2-122">Then uses that variable with the [GetDescendant()](/sql/t-sql/data-types/getdescendant-database-engine) method to insert row that is a subordinate node.</span></span> <span data-ttu-id="616f2-123">`GetDescendant` accetta due argomenti.</span><span class="sxs-lookup"><span data-stu-id="616f2-123">`GetDescendant` takes two arguments.</span></span> <span data-ttu-id="616f2-124">Rivedere le opzioni seguenti per i valori dell'argomento:</span><span class="sxs-lookup"><span data-stu-id="616f2-124">Review the following options for the argument values:</span></span>  
  
    -   <span data-ttu-id="616f2-125">Se il padre è NULL, `GetDescendant` restituisce NULL.</span><span class="sxs-lookup"><span data-stu-id="616f2-125">If parent is NULL, `GetDescendant` returns NULL.</span></span>  
  
    -   <span data-ttu-id="616f2-126">Se il padre non è NULL e child1 e child2 sono NULL, `GetDescendant` restituisce un figlio del padre.</span><span class="sxs-lookup"><span data-stu-id="616f2-126">If parent is not NULL, and both child1 and child2 are NULL, `GetDescendant` returns a child of parent.</span></span>  
  
    -   <span data-ttu-id="616f2-127">Se il padre e child1 non sono NULL e child2 è NULL, `GetDescendant` restituisce un figlio del padre maggiore di child1.</span><span class="sxs-lookup"><span data-stu-id="616f2-127">If parent and child1 are not NULL, and child2 is NULL, `GetDescendant` returns a child of parent greater than child1.</span></span>  
  
    -   <span data-ttu-id="616f2-128">Se il padre e child2 non sono NULL e child1 è NULL, `GetDescendant` restituisce un figlio del padre minore di child2.</span><span class="sxs-lookup"><span data-stu-id="616f2-128">If parent and child2 are not NULL and child1 is NULL, `GetDescendant` returns a child of parent less than child2.</span></span>  
  
    -   <span data-ttu-id="616f2-129">Se il padre, child1 e child2 non sono NULL, `GetDescendant` restituisce un figlio del padre maggiore di child1 e uno minore di child2.</span><span class="sxs-lookup"><span data-stu-id="616f2-129">If parent, child1, and child2 are all not NULL, `GetDescendant` returns a child of parent greater than child1 and less than child2.</span></span>  
  
     <span data-ttu-id="616f2-130">Il codice seguente utilizza gli argomenti `(NULL, NULL)` dell'elemento padre radice perché nella tabella non esiste ancora alcuna riga, ad eccezione della radice.</span><span class="sxs-lookup"><span data-stu-id="616f2-130">The following code uses the `(NULL, NULL)` arguments of the root parent because there are not yet any rows in the table except the root.</span></span> <span data-ttu-id="616f2-131">Eseguire il codice seguente per inserire **Sariya**:</span><span class="sxs-lookup"><span data-stu-id="616f2-131">Execute the following code to insert **Sariya**:</span></span>  
  
    ```  
    DECLARE @Manager hierarchyid   
    SELECT @Manager = hierarchyid::GetRoot()  
    FROM HumanResources.EmployeeOrg ;  
  
    INSERT HumanResources.EmployeeOrg (OrgNode, EmployeeID, EmpName, Title)  
    VALUES  
    (@Manager.GetDescendant(NULL, NULL), 46, 'Sariya', 'Marketing Specialist') ;  
  
    ```  
  
2.  <span data-ttu-id="616f2-132">Ripetere la query dalla prima procedura per eseguire una query sulla tabella e verificare come appaiono le voci:</span><span class="sxs-lookup"><span data-stu-id="616f2-132">Repeat the query from the first procedure to query the table and see how the entries appear:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode, OrgLevel, EmployeeID, EmpName, Title   
    FROM HumanResources.EmployeeOrg ;  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
    ```  
    Text_OrgNode OrgNode OrgLevel EmployeeID EmpName Title  
    ------------ ------- -------- ---------- ------- -----------------  
    /            Ox      0        6          David   Marketing Manager  
    /1/          0x58    1        46         Sariya  Marketing Specialist  
    ```  
  
### <a name="to-create-a-procedure-for-entering-new-nodes"></a><span data-ttu-id="616f2-133">Per creare una procedura per l'immissione di nuovi nodi</span><span class="sxs-lookup"><span data-stu-id="616f2-133">To create a procedure for entering new nodes</span></span>  
  
1.  <span data-ttu-id="616f2-134">Per semplificare l'inserimento di dati, creare la stored procedure seguente per aggiungere dipendenti alla tabella **EmployeeOrg** .</span><span class="sxs-lookup"><span data-stu-id="616f2-134">To simplify entering data, create the following stored procedure to add employees to the **EmployeeOrg** table.</span></span> <span data-ttu-id="616f2-135">La procedura accetta valori di input sul dipendente aggiunto.</span><span class="sxs-lookup"><span data-stu-id="616f2-135">The procedure accepts input values about the employee being added.</span></span> <span data-ttu-id="616f2-136">Include il numero **EmployeeID** del responsabile del nuovo dipendente, il numero **EmployeeID** del nuovo dipendente, il nome e il titolo.</span><span class="sxs-lookup"><span data-stu-id="616f2-136">This includes the **EmployeeID** of the new employee's manager, the new employee's **EmployeeID** number, and their first name and title.</span></span> <span data-ttu-id="616f2-137">La procedura usa `GetDescendant()` e anche il metodo [GetAncestor()](/sql/t-sql/data-types/getancestor-database-engine) .</span><span class="sxs-lookup"><span data-stu-id="616f2-137">The procedure uses `GetDescendant()` and also the [GetAncestor()](/sql/t-sql/data-types/getancestor-database-engine) method.</span></span> <span data-ttu-id="616f2-138">Eseguire il codice seguente per creare la procedura:</span><span class="sxs-lookup"><span data-stu-id="616f2-138">Execute the following code to create the procedure:</span></span>  
  
    ```  
    CREATE PROC AddEmp(@mgrid int, @empid int, @e_name varchar(20), @title varchar(20))   
    AS   
    BEGIN  
       DECLARE @mOrgNode hierarchyid, @lc hierarchyid  
       SELECT @mOrgNode = OrgNode   
       FROM HumanResources.EmployeeOrg   
       WHERE EmployeeID = @mgrid  
       SET TRANSACTION ISOLATION LEVEL SERIALIZABLE  
       BEGIN TRANSACTION  
          SELECT @lc = max(OrgNode)   
          FROM HumanResources.EmployeeOrg   
          WHERE OrgNode.GetAncestor(1) =@mOrgNode ;  
  
          INSERT HumanResources.EmployeeOrg (OrgNode, EmployeeID, EmpName, Title)  
          VALUES(@mOrgNode.GetDescendant(@lc, NULL), @empid, @e_name, @title)  
       COMMIT  
    END ;  
    GO  
    ```  
  
2.  <span data-ttu-id="616f2-139">Nell'esempio seguente vengono aggiunti i 4 dipendenti rimanenti che fanno riferimento direttamente o indirettamente a **David**.</span><span class="sxs-lookup"><span data-stu-id="616f2-139">The following example adds the remaining 4 employees that report directly or indirectly to **David**.</span></span>  
  
    ```  
    EXEC AddEmp 6, 271, 'John', 'Marketing Specialist' ;  
    EXEC AddEmp 6, 119, 'Jill', 'Marketing Specialist' ;  
    EXEC AddEmp 46, 269, 'Wanida', 'Marketing Assistant' ;  
    EXEC AddEmp 271, 272, 'Mary', 'Marketing Assistant' ;  
    ```  
  
3.  <span data-ttu-id="616f2-140">Eseguire nuovamente la query seguente per esaminare le righe della tabella **EmployeeOrg** :</span><span class="sxs-lookup"><span data-stu-id="616f2-140">Again, execute the following query examine the rows in the **EmployeeOrg** table:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode, OrgLevel, EmployeeID, EmpName, Title   
    FROM HumanResources.EmployeeOrg ;  
    GO  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
    ```  
    Text_OrgNode OrgNode OrgLevel EmployeeID EmpName Title  
    ------------ ------- -------- ---------- ------- -----------------  
    /            Ox      0        6          David   Marketing Manager  
    /1/          0x58    1        46         Sariya  Marketing Specialist  
    /1/1/        0x5AC0  2        269        Wanida  Marketing Assistant  
    /2/          0x68    1        271        John    Marketing Specialist  
    /2/1/        0x6AC0  2        272        Mary    Marketing Assistant  
    /3/          0x78    1        119        Jill    Marketing Specialist  
    ```  
  
 <span data-ttu-id="616f2-141">La tabella ora è popolata completamente con l'organizzazione Marketing.</span><span class="sxs-lookup"><span data-stu-id="616f2-141">The table is now fully populated with the Marketing organization.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="616f2-142">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="616f2-142">Next Task in Lesson</span></span>  
 [<span data-ttu-id="616f2-143">Esecuzione di query su una tabella gerarchica utilizzando metodi gerarchici</span><span class="sxs-lookup"><span data-stu-id="616f2-143">Querying a Hierarchical Table Using Hierarchy Methods</span></span>](lesson-2-3-querying-a-hierarchical-table-using-hierarchy-methods.md)  
  
  
