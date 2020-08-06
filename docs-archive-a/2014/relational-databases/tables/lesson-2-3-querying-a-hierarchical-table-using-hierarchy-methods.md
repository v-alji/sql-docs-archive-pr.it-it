---
title: Esecuzione di query su una tabella gerarchica tramite metodi gerarchici | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: 3b4f7dae-65b5-4d8d-8641-87aba9aa692d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6c86c8e8678fc821dc3796a511349c1c3498bdb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629739"
---
# <a name="querying-a-hierarchical-table-using-hierarchy-methods"></a><span data-ttu-id="08df3-102">Esecuzione di query su una tabella gerarchica utilizzando metodi gerarchici</span><span class="sxs-lookup"><span data-stu-id="08df3-102">Querying a Hierarchical Table Using Hierarchy Methods</span></span>
  <span data-ttu-id="08df3-103">Ora che la tabella HumanResources.EmployeeOrg è completamente popolata, in questa attività verrà illustrato come eseguire una query sulla gerarchia utilizzando alcuni dei metodi gerarchici.</span><span class="sxs-lookup"><span data-stu-id="08df3-103">Now that the HumanResources.EmployeeOrg table is fully populated, this task will show you how to query the hierarchy using some of the hierarchical methods.</span></span>  
  
### <a name="to-find-subordinate-nodes"></a><span data-ttu-id="08df3-104">Per trovare nodi subordinati</span><span class="sxs-lookup"><span data-stu-id="08df3-104">To find subordinate nodes</span></span>  
  
1.  <span data-ttu-id="08df3-105">Sariya ha un dipendente subordinato.</span><span class="sxs-lookup"><span data-stu-id="08df3-105">Sariya has one subordinate employee.</span></span> <span data-ttu-id="08df3-106">Per eseguire una query sui subalterni di Sariya, eseguire la query seguente che usa il metodo [IsDescendantOf](/sql/t-sql/data-types/isdescendantof-database-engine) :</span><span class="sxs-lookup"><span data-stu-id="08df3-106">To query for Sariya's subordinates, execute the following query that uses the [IsDescendantOf](/sql/t-sql/data-types/isdescendantof-database-engine) method:</span></span>  
  
    ```  
    DECLARE @CurrentEmployee hierarchyid  
  
    SELECT @CurrentEmployee = OrgNode  
    FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 46 ;  
  
    SELECT *  
    FROM HumanResources.EmployeeOrg  
    WHERE OrgNode.IsDescendantOf(@CurrentEmployee ) = 1 ;  
    ```  
  
     <span data-ttu-id="08df3-107">I risultati indicano sia Sariya sia Wanida.</span><span class="sxs-lookup"><span data-stu-id="08df3-107">The result lists both Sariya and Wanida.</span></span> <span data-ttu-id="08df3-108">Sariya viene indicata perché rappresenta l'elemento discendente al livello 0.</span><span class="sxs-lookup"><span data-stu-id="08df3-108">Sariya is listed because she is the descendant at the 0 level.</span></span> <span data-ttu-id="08df3-109">Wanida rappresenta l'elemento discendente al livello 1.</span><span class="sxs-lookup"><span data-stu-id="08df3-109">Wanida is the descendant at the 1 level.</span></span>  
  
2.  <span data-ttu-id="08df3-110">È anche possibile eseguire una query per ottenere tali informazioni usando il metodo [GetAncestor](/sql/t-sql/data-types/getancestor-database-engine) .</span><span class="sxs-lookup"><span data-stu-id="08df3-110">You can also query for this information by using the [GetAncestor](/sql/t-sql/data-types/getancestor-database-engine) method.</span></span> <span data-ttu-id="08df3-111">`GetAncestor` accetta un argomento per il livello che si tenta di restituire.</span><span class="sxs-lookup"><span data-stu-id="08df3-111">`GetAncestor` takes an argument for the level that you are trying to return.</span></span> <span data-ttu-id="08df3-112">Poiché Wanida è un livello sotto Sariya, utilizzare `GetAncestor(1)` come dimostrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="08df3-112">Since Wanida is one level underneath Sariya, use `GetAncestor(1)` as demonstrated in the following code:</span></span>  
  
    ```  
    DECLARE @CurrentEmployee hierarchyid  
  
    SELECT @CurrentEmployee = OrgNode  
    FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 46 ;  
  
    SELECT OrgNode.ToString() AS Text_OrgNode, *  
    FROM HumanResources.EmployeeOrg  
    WHERE OrgNode.GetAncestor(1) = @CurrentEmployee  
    ```  
  
     <span data-ttu-id="08df3-113">Questa volta nei risultati viene indicata solo Wanida.</span><span class="sxs-lookup"><span data-stu-id="08df3-113">This time the result lists only Wanida.</span></span>  
  
3.  <span data-ttu-id="08df3-114">Ora impostare `@CurrentEmployee` su David (EmployeeID 6) e il livello su 2.</span><span class="sxs-lookup"><span data-stu-id="08df3-114">Now change the `@CurrentEmployee` to David (EmployeeID 6) and the level to 2.</span></span> <span data-ttu-id="08df3-115">Eseguire quanto segue per restituire anche Wanida:</span><span class="sxs-lookup"><span data-stu-id="08df3-115">Execute the following to also return Wanida:</span></span>  
  
    ```  
    DECLARE @CurrentEmployee hierarchyid  
  
    SELECT @CurrentEmployee = OrgNode  
    FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 6 ;  
  
    SELECT OrgNode.ToString() AS Text_OrgNode, *  
    FROM HumanResources.EmployeeOrg  
    WHERE OrgNode.GetAncestor(2) = @CurrentEmployee  
    ```  
  
     <span data-ttu-id="08df3-116">Questa volta, due livelli più in basso, viene indicata anche Mary che riporta a David.</span><span class="sxs-lookup"><span data-stu-id="08df3-116">This time, you also receive Mary who also reports to David, two levels down.</span></span>  
  
### <a name="to-use-getroot-and-getlevel"></a><span data-ttu-id="08df3-117">Utilizzo di GetRoot e GetLevel</span><span class="sxs-lookup"><span data-stu-id="08df3-117">To use GetRoot, and GetLevel</span></span>  
  
1.  <span data-ttu-id="08df3-118">Con il crescere della gerarchia diventa più difficile determinare la posizione dei membri nella stessa.</span><span class="sxs-lookup"><span data-stu-id="08df3-118">As the hierarchy grows larger it is more difficult to determine where the members are in the hierarchy.</span></span> <span data-ttu-id="08df3-119">Usare il metodo [GetLevel](/sql/t-sql/data-types/getlevel-database-engine) per scoprire quanti livelli ci sono al di sotto di ogni riga della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="08df3-119">Use the [GetLevel](/sql/t-sql/data-types/getlevel-database-engine) method to find how many levels down each row is in the hierarchy.</span></span> <span data-ttu-id="08df3-120">Eseguire il codice seguente per visualizzare i livelli di tutte le righe:</span><span class="sxs-lookup"><span data-stu-id="08df3-120">Execute the following code to view the levels of all the rows:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode.GetLevel() AS EmpLevel, *  
    FROM HumanResources.EmployeeOrg ;  
    GO  
  
    ```  
  
2.  <span data-ttu-id="08df3-121">Usare il metodo [GetRoot](/sql/t-sql/data-types/getroot-database-engine) per cercare il nodo radice della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="08df3-121">Use the [GetRoot](/sql/t-sql/data-types/getroot-database-engine) method to find the root node in the hierarchy.</span></span> <span data-ttu-id="08df3-122">Il codice seguente restituisce la singola riga che è la radice:</span><span class="sxs-lookup"><span data-stu-id="08df3-122">The following code returns the single row which is the root:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode, *  
    FROM HumanResources.EmployeeOrg  
    WHERE OrgNode = hierarchyid::GetRoot() ;  
    GO  
  
    ```  
  
 <span data-ttu-id="08df3-123">L'attività successiva riorganizzerà la gerarchia.</span><span class="sxs-lookup"><span data-stu-id="08df3-123">The next task will reorganize the hierarchy.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="08df3-124">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="08df3-124">Next Task in Lesson</span></span>  
 [<span data-ttu-id="08df3-125">Riordinamento di dati in una tabella gerarchica utilizzando metodi gerarchici</span><span class="sxs-lookup"><span data-stu-id="08df3-125">Reordering Data in a Hierarchical Table Using Hierarchical Methods</span></span>](lesson-2-4-reordering-data-in-a-hierarchical-table-using-hierarchical-methods.md)  
  
  
