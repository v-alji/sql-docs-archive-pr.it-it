---
title: Riordinamento di dati in una tabella gerarchica tramite metodi gerarchici | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: 7b8064c7-62c6-488d-84d2-57a5828fb907
author: stevestein
ms.author: sstein
ms.openlocfilehash: ac6c93f359a81a80af81182120f213564680de0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623977"
---
# <a name="reordering-data-in-a-hierarchical-table-using-hierarchical-methods"></a><span data-ttu-id="f0925-102">Riordinamento di dati in una tabella gerarchica utilizzando metodi gerarchici</span><span class="sxs-lookup"><span data-stu-id="f0925-102">Reordering Data in a Hierarchical Table Using Hierarchical Methods</span></span>
  <span data-ttu-id="f0925-103">La riorganizzazione di una gerarchia è un'attività di manutenzione comune.</span><span class="sxs-lookup"><span data-stu-id="f0925-103">Reorganizing a hierarchy is a common maintenance task.</span></span> <span data-ttu-id="f0925-104">In questa attività verrà usata un'istruzione UPDATE con il metodo [GetReparentedValue](/sql/t-sql/data-types/getreparentedvalue-database-engine) per spostare innanzitutto una singola riga in un percorso nuovo della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="f0925-104">In this task, we will use an UPDATE statement with the [GetReparentedValue](/sql/t-sql/data-types/getreparentedvalue-database-engine) method to first move a single row to a new location in the hierarchy.</span></span> <span data-ttu-id="f0925-105">Verrà quindi spostato un sottoalbero intero in un nuovo percorso.</span><span class="sxs-lookup"><span data-stu-id="f0925-105">Then we will move an entire sub-tree to a new location.</span></span>  
  
 <span data-ttu-id="f0925-106">Il metodo `GetReparentedValue` utilizza due argomenti.</span><span class="sxs-lookup"><span data-stu-id="f0925-106">The `GetReparentedValue` method takes two arguments.</span></span> <span data-ttu-id="f0925-107">Nel primo argomento viene descritta la parte della gerarchia da modificare.</span><span class="sxs-lookup"><span data-stu-id="f0925-107">The first argument describes the part of the hierarchy to be modified.</span></span> <span data-ttu-id="f0925-108">Ad esempio, se una gerarchia è **/1/4/2/3/** e si vuole modificare la sezione **/1/4/** , la gerarchia diventa **/2/1/2/3/**, lasciando gli ultimi due nodi (**2/3/**) inalterati, è necessario specificare i nodi modificati (**/1/4/**) come primo argomento.</span><span class="sxs-lookup"><span data-stu-id="f0925-108">For example, if a hierarchy is **/1/4/2/3/** and you want to change the **/1/4/** section, the hierarchy becomes **/2/1/2/3/**, leaving the last two nodes (**2/3/**) unchanged, you must provide the changing nodes (**/1/4/**) as the first argument.</span></span> <span data-ttu-id="f0925-109">Il secondo argomento specifica il nuovo livello della gerarchia, nell'esempio **/2/1/**.</span><span class="sxs-lookup"><span data-stu-id="f0925-109">The second argument provides the new hierarchy level, in our example **/2/1/**.</span></span> <span data-ttu-id="f0925-110">Non è necessario che i due argomenti contengano lo stesso numero di livelli.</span><span class="sxs-lookup"><span data-stu-id="f0925-110">The two arguments do not have to contain the same number of levels.</span></span>  
  
### <a name="to-move-a-single-row-to-a-new-location-in-the-hierarchy"></a><span data-ttu-id="f0925-111">Per spostare una sola riga in un percorso nuovo nella gerarchia</span><span class="sxs-lookup"><span data-stu-id="f0925-111">To move a single row to a new location in the hierarchy</span></span>  
  
1.  <span data-ttu-id="f0925-112">Attualmente Wanida riporta a Sariya.</span><span class="sxs-lookup"><span data-stu-id="f0925-112">Currently Wanida reports to Sariya.</span></span> <span data-ttu-id="f0925-113">In questa procedura, si sposta Wanida dal nodo corrente **/1/1/,** in modo che riporti a Jill.</span><span class="sxs-lookup"><span data-stu-id="f0925-113">In this procedure, you move Wanida from her current node **/1/1/,** so that she reports to Jill.</span></span> <span data-ttu-id="f0925-114">Il suo nodo nuovo diventerà **/3/1/** e **/1/** diventa il primo argomento, mentre **/3/** diventa il secondo argomento.</span><span class="sxs-lookup"><span data-stu-id="f0925-114">Her new node will become **/3/1/** so **/1/** is the first argument and **/3/** is the second.</span></span> <span data-ttu-id="f0925-115">Gli argomenti corrispondono ai valori **OrgNode** di Sariya e Jill.</span><span class="sxs-lookup"><span data-stu-id="f0925-115">These correspond to the **OrgNode** values of Sariya and Jill.</span></span> <span data-ttu-id="f0925-116">Eseguire il codice seguente per spostare Wanida dall'organizzazione di Sariya a quella di Jill:</span><span class="sxs-lookup"><span data-stu-id="f0925-116">Execute the following code to move Wanida from Sariya's organization to Jill's:</span></span>  
  
    ```  
    DECLARE @CurrentEmployee hierarchyid , @OldParent hierarchyid, @NewParent hierarchyid  
    SELECT @CurrentEmployee = OrgNode FROM HumanResources.EmployeeOrg  
      WHERE EmployeeID = 269 ;   
    SELECT @OldParent = OrgNode FROM HumanResources.EmployeeOrg  
      WHERE EmployeeID = 46 ;   
    SELECT @NewParent = OrgNode FROM HumanResources.EmployeeOrg  
      WHERE EmployeeID = 119 ;   
  
    UPDATE HumanResources.EmployeeOrg  
    SET OrgNode = @CurrentEmployee. GetReparentedValue(@OldParent, @NewParent)   
    WHERE OrgNode = @CurrentEmployee ;  
    GO  
    ```  
  
2.  <span data-ttu-id="f0925-117">Eseguire il codice seguente per visualizzare il risultato:</span><span class="sxs-lookup"><span data-stu-id="f0925-117">Execute the following code to see the result:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode, OrgLevel, EmployeeID, EmpName, Title   
    FROM HumanResources.EmployeeOrg ;  
    GO  
    ```  
  
     <span data-ttu-id="f0925-118">Wanida ora è al nodo **/3/1/**.</span><span class="sxs-lookup"><span data-stu-id="f0925-118">Wanida is now at node **/3/1/**.</span></span>  
  
### <a name="to-reorganize-a-section-of-a-hierarchy"></a><span data-ttu-id="f0925-119">Per riorganizzare una sezione di una gerarchia</span><span class="sxs-lookup"><span data-stu-id="f0925-119">To reorganize a section of a hierarchy</span></span>  
  
1.  <span data-ttu-id="f0925-120">Per dimostrare come spostare contemporaneamente un numero maggiore di persone, eseguire innanzitutto il codice seguente per aggiungere un report del tirocinante a Wanida:</span><span class="sxs-lookup"><span data-stu-id="f0925-120">To demonstrate how to move a larger number of people at the same time, first execute the following code to add an intern reporting to Wanida:</span></span>  
  
    ```  
    EXEC AddEmp 269, 291, 'Kevin', 'Marketing Intern'  ;  
    GO  
    ```  
  
2.  <span data-ttu-id="f0925-121">Ora Kevin riporta a Wanida che riporta a Jill che riporta a David.</span><span class="sxs-lookup"><span data-stu-id="f0925-121">Now Kevin reports to Wanida, who reports to Jill, who reports to David.</span></span> <span data-ttu-id="f0925-122">Questo significa che Kevin è al livello **/3/1/1/**.</span><span class="sxs-lookup"><span data-stu-id="f0925-122">That means that Kevin is at level **/3/1/1/**.</span></span> <span data-ttu-id="f0925-123">Per spostare tutti i subalterni di Jill a un nuovo responsabile, verranno aggiornati tutti i nodi che hanno **/3/** in **OrgNode** con un nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="f0925-123">To move all of Jill's subordinates to a new manager, we will update all nodes that have **/3/** as their **OrgNode** to a new value.</span></span> <span data-ttu-id="f0925-124">Eseguire il codice seguente per aggiornare Wanida in modo che riporti a Sariya, ma lasciando che Kevin riporti a Wanida:</span><span class="sxs-lookup"><span data-stu-id="f0925-124">Execute the following code to update Wanida to report to Sariya, but keep  Kevin reporting to Wanida:</span></span>  
  
    ```  
    DECLARE @OldParent hierarchyid, @NewParent hierarchyid  
    SELECT @OldParent = OrgNode FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 119 ; -- Jill  
    SELECT @NewParent = OrgNode FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 46 ; -- Sariya  
    DECLARE children_cursor CURSOR FOR  
    SELECT OrgNode FROM HumanResources.EmployeeOrg  
    WHERE OrgNode.GetAncestor(1) = @OldParent;  
    DECLARE @ChildId hierarchyid;  
    OPEN children_cursor  
    FETCH NEXT FROM children_cursor INTO @ChildId;  
    WHILE @@FETCH_STATUS = 0  
    BEGIN  
    START:  
        DECLARE @NewId hierarchyid;  
        SELECT @NewId = @NewParent.GetDescendant(MAX(OrgNode), NULL)  
        FROM HumanResources.EmployeeOrg WHERE OrgNode.GetAncestor(1) = @NewParent;  
  
        UPDATE HumanResources.EmployeeOrg  
        SET OrgNode = OrgNode.GetReparentedValue(@ChildId, @NewId)  
        WHERE OrgNode.IsDescendantOf(@ChildId) = 1;  
        IF @@error <> 0 GOTO START -- On error, retry  
            FETCH NEXT FROM children_cursor INTO @ChildId;  
    END  
    CLOSE children_cursor;  
    DEALLOCATE children_cursor;  
  
    ```  
  
3.  <span data-ttu-id="f0925-125">Eseguire il codice seguente per visualizzare il risultato:</span><span class="sxs-lookup"><span data-stu-id="f0925-125">Execute the following code to see the result:</span></span>  
  
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
/1/1//2      0x5AD0  3        291        Kevin   Marketing Intern  
/2/          0x68    1        271        John    Marketing Specialist  
/2/1/        0x6AC0  2        272        Mary    Marketing Assistant  
/3/          0x78    1        119        Jill    Marketing Specialist  
```  
  
 <span data-ttu-id="f0925-126">L'intero albero organizzativo che riportava a Jill (Wanida e Kevin) ora riporta a Sariya.</span><span class="sxs-lookup"><span data-stu-id="f0925-126">The entire organizational tree that had reported to Jill (both Wanida and Kevin) now reports to Sariya.</span></span>  
  
 <span data-ttu-id="f0925-127">Per riorganizzare una sezione di una gerarchia tramite una stored procedure, vedere la sezione [Spostamento di sottoalberi](../hierarchical-data-sql-server.md#BKMK_MovingSubtrees).</span><span class="sxs-lookup"><span data-stu-id="f0925-127">For a stored procedure to reorganize a section of a hierarchy, see the "Moving Subtrees" section of [Moving Subtrees](../hierarchical-data-sql-server.md#BKMK_MovingSubtrees).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="f0925-128">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="f0925-128">Next Task in Lesson</span></span>  
 [<span data-ttu-id="f0925-129">Riepilogo: Gestione dei dati in una tabella gerarchica</span><span class="sxs-lookup"><span data-stu-id="f0925-129">Summary: Managing Data in a Hierarchical Table</span></span>](lesson-2-5-summary-managing-data-in-a-hierarchical-table.md)  
  
  
