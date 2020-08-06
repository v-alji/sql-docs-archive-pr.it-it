---
title: Esame della struttura corrente della tabella Employee | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- examining the current structure of the employee
ms.assetid: d546a820-105a-417d-ac35-44a6d1d70ac6
author: stevestein
ms.author: sstein
ms.openlocfilehash: b7f63773ebc1f28fb24f8f1000c3f87ee4d50544
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623104"
---
# <a name="examining-the-current-structure-of-the-employee-table"></a><span data-ttu-id="29279-102">Esame della struttura corrente della tabella Employee</span><span class="sxs-lookup"><span data-stu-id="29279-102">Examining the Current Structure of the Employee Table</span></span>
  <span data-ttu-id="29279-103"> Il database di esempio [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] contiene una tabella **Employee** nello schema **HumanResources**.</span><span class="sxs-lookup"><span data-stu-id="29279-103">The sample [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database contains an **Employee** table in the **HumanResources** schema.</span></span> <span data-ttu-id="29279-104">Per evitare di modificare la tabella originale, in questo passaggio viene creata una copia della tabella **Employee** denominata **EmployeeDemo**.</span><span class="sxs-lookup"><span data-stu-id="29279-104">To avoid changing the original table, this step makes a copy of the **Employee** table named **EmployeeDemo**.</span></span> <span data-ttu-id="29279-105">Per semplificare l'esempio, copiare solo cinque colonne della tabella originale.</span><span class="sxs-lookup"><span data-stu-id="29279-105">To simplify the example, you only copy five columns from the original table.</span></span> <span data-ttu-id="29279-106">Viene quindi eseguita una query sulla tabella **HumanResources. EmployeeDemo** per esaminare il modo in cui i dati vengono strutturati in una tabella senza utilizzare il `hierarchyid` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="29279-106">Then, you query the **HumanResources.EmployeeDemo** table to review how the data is structured in a table without using the `hierarchyid` data type.</span></span>  
  
### <a name="to-copy-the-employee-table"></a><span data-ttu-id="29279-107">Per copiare la tabella Employee</span><span class="sxs-lookup"><span data-stu-id="29279-107">To copy the Employee table</span></span>  
  
1.  <span data-ttu-id="29279-108">In una finestra editor di query, eseguire il codice seguente per copiare la struttura della tabella e i dati della tabella **Employee** in una tabella nuova denominata **EmployeeDemo**.</span><span class="sxs-lookup"><span data-stu-id="29279-108">In a Query Editor window, run the following code to copy the table structure and data from the **Employee** table into a new table named **EmployeeDemo**.</span></span>  
  
    ```  
    USE AdventureWorks ;  
    GO  
  
    SELECT EmployeeID, LoginID, ManagerID, Title, HireDate   
    INTO HumanResources.EmployeeDemo   
    FROM HumanResources.Employee ;  
    GO  
    ```  
  
### <a name="to-examine-the-structure-and-data-of-the-employeedemo-table"></a><span data-ttu-id="29279-109">Per esaminare la struttura e i dati della tabella EmployeeDemo</span><span class="sxs-lookup"><span data-stu-id="29279-109">To examine the structure and data of the EmployeeDemo table</span></span>  
  
-   <span data-ttu-id="29279-110">Questa nuova tabella **EmployeeDemo** rappresenta una tabella tipica di un database esistente di cui si può eseguire la migrazione a una struttura nuova.</span><span class="sxs-lookup"><span data-stu-id="29279-110">This new **EmployeeDemo** table represents a typical table in an existing database that you might want to migrate to a new structure.</span></span> <span data-ttu-id="29279-111">In una finestra editor di query, eseguire il codice seguente per visualizzare il modo in cui la tabella utilizza un self-join per visualizzare le relazioni dipendente/responsabile:</span><span class="sxs-lookup"><span data-stu-id="29279-111">In a Query Editor window, run the following code to show how the table uses a self join to display the employee/manager relationships:</span></span>  
  
    ```  
    SELECT   
         Mgr.EmployeeID AS MgrID, Mgr.LoginID AS Manager,   
         Emp.EmployeeID AS E_ID, Emp.LoginID, Emp.Title  
    FROM HumanResources.EmployeeDemo AS Emp  
    LEFT JOIN HumanResources.EmployeeDemo AS Mgr  
    ON Emp.ManagerID = Mgr.EmployeeID  
    ORDER BY MgrID, E_ID  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
    ```  
    MgrID Manager                 E_ID LoginID                  Title  
    NULL NULL                      109 adventure-works\ken0     Chief Executive Officer  
    3    adventure-works\roberto0  4   adventure-works\rob0     Senior Tool Designer  
    3    adventure-works\roberto0  9   adventure-works\gail0    Design Engineer  
    3    adventure-works\roberto0  11  adventure-works\jossef0  Design Engineer  
    3    adventure-works\roberto0  158 adventure-works\dylan0   Research and Development Manager  
    3    adventure-works\roberto0  263 adventure-works\ovidiu0  Senior Tool Designer  
    3    adventure-works\roberto0  267 adventure-works\michael8 Senior Design Engineer  
    3    adventure-works\roberto0  270 adventure-works\sharon0  Design Engineer  
    6    adventure-works\david0    2   adventure-works\kevin0   Marketing Assistant  
    ...  
    ```  
  
     <span data-ttu-id="29279-112">Viene generato un totale di 290 righe di risultati.</span><span class="sxs-lookup"><span data-stu-id="29279-112">The results continue for a total of 290 rows.</span></span>  
  
 <span data-ttu-id="29279-113">Con la clausola `ORDER BY`, i report diretti di ogni livello di gestione vengono elencati insieme nell'output.</span><span class="sxs-lookup"><span data-stu-id="29279-113">Notice that the `ORDER BY` clause caused the output to list the direct reports of each management level together.</span></span> <span data-ttu-id="29279-114">Ad esempio, tutti i sette report diretti di **MgrID** 3 (roberto0) vengono elencati uno accanto all'altro.</span><span class="sxs-lookup"><span data-stu-id="29279-114">For instance, all seven of the direct reports of **MgrID** 3 (roberto0) are listed adjacent to each other.</span></span> <span data-ttu-id="29279-115">Anche se non impossibile, è molto più difficile raggruppare tutti coloro che riportano a **MgrID** 3.</span><span class="sxs-lookup"><span data-stu-id="29279-115">Although not impossible, it is much more difficult to group all those who eventually report to **MgrID** 3.</span></span>  
  
 <span data-ttu-id="29279-116">Nell'attività successiva, verrà creata una nuova tabella con un tipo di dati `hierarchyid` e verranno spostati i dati nella nuova tabella.</span><span class="sxs-lookup"><span data-stu-id="29279-116">In the next task, we will create a new table with a `hierarchyid` data type, and move the data into the new table.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="29279-117">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="29279-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="29279-118">Popolamento di una tabella con dati gerarchici esistenti</span><span class="sxs-lookup"><span data-stu-id="29279-118">Populating a Table with Existing Hierarchical Data</span></span>](lesson-1-2-populating-a-table-with-existing-hierarchical-data.md)  
  
  
