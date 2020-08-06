---
title: Creazione di una tabella tramite il tipo di dati hierarchyid | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: 0d1f361f-336c-4571-99d1-f4813b2d9fc4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2c9b59795949e11cabd21b0be8de844b33d73c37
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724468"
---
# <a name="creating-a-table-using-the-hierarchyid-data-type"></a><span data-ttu-id="84e7e-102">Creazione di una tabella utilizzando il tipo di dati hierarchyid</span><span class="sxs-lookup"><span data-stu-id="84e7e-102">Creating a Table Using the hierarchyid Data Type</span></span>
  <span data-ttu-id="84e7e-103">Nell'esempio seguente viene creata una tabella denominata EmployeeOrg che include i dati del dipendente e la gerarchia del report.</span><span class="sxs-lookup"><span data-stu-id="84e7e-103">The following example creates a table named EmployeeOrg, which includes employee data together with their reporting hierarchy.</span></span> <span data-ttu-id="84e7e-104">L'esempio crea la tabella nel database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , ma questo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="84e7e-104">The example creates the table in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, but that is optional.</span></span> <span data-ttu-id="84e7e-105">Per mantenere l'esempio semplice, in questa tabella sono incluse solo cinque colonne:</span><span class="sxs-lookup"><span data-stu-id="84e7e-105">To keep the example simple, this table includes only five columns:</span></span>  
  
-   <span data-ttu-id="84e7e-106">OrgNode è una colonna `hierarchyid` che archivia la relazione gerarchica.</span><span class="sxs-lookup"><span data-stu-id="84e7e-106">OrgNode is a `hierarchyid` column that stores the hierarchical relationship.</span></span>  
  
-   <span data-ttu-id="84e7e-107">OrgLevel è una colonna calcolata in base alla colonna OrgNode che archivia il livello di ciascun nodo nella gerarchia.</span><span class="sxs-lookup"><span data-stu-id="84e7e-107">OrgLevel is a computed column, based on the OrgNode column that stores each nodes level in the hierarchy.</span></span> <span data-ttu-id="84e7e-108">Verrà utilizzata per un indice breadth-first.</span><span class="sxs-lookup"><span data-stu-id="84e7e-108">It will be used for a breadth-first index.</span></span>  
  
-   <span data-ttu-id="84e7e-109">Il numero di identificazione tipico del dipendente, utilizzato per applicazioni quali libro paga, è contenuto in EmployeeID.</span><span class="sxs-lookup"><span data-stu-id="84e7e-109">EmployeeID contains the typical employee identification number that is used for applications such as payroll.</span></span> <span data-ttu-id="84e7e-110">Nello sviluppo di nuove applicazioni, le applicazioni possono utilizzare la colonna OrgNode mentre la colonna separata EmployeeID non è necessaria.</span><span class="sxs-lookup"><span data-stu-id="84e7e-110">In new application development, applications can use the OrgNode column and this separate EmployeeID column is not needed.</span></span>  
  
-   <span data-ttu-id="84e7e-111">EmpName contiene il nome del dipendente.</span><span class="sxs-lookup"><span data-stu-id="84e7e-111">EmpName contains the name of the employee.</span></span>  
  
-   <span data-ttu-id="84e7e-112">Title contiene la posizione del dipendente.</span><span class="sxs-lookup"><span data-stu-id="84e7e-112">Title contains the title of the employee.</span></span>  
  
### <a name="to-create-the-employeeorg-table"></a><span data-ttu-id="84e7e-113">Per creare la tabella EmployeeOrg</span><span class="sxs-lookup"><span data-stu-id="84e7e-113">To create the EmployeeOrg table</span></span>  
  
1.  <span data-ttu-id="84e7e-114">Nella finestra dell'editor di query eseguire il codice seguente per creare la tabella `EmployeeOrg` .</span><span class="sxs-lookup"><span data-stu-id="84e7e-114">In a Query Editor window, run the following code to create the `EmployeeOrg` table.</span></span> <span data-ttu-id="84e7e-115">Specificando la colonna `OrgNode` come chiave primaria con un indice cluster, verrà creato un indice depth-first:</span><span class="sxs-lookup"><span data-stu-id="84e7e-115">Specifying the `OrgNode` column as the primary key with a clustered index will create a depth-first index:</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    GO  
    CREATE TABLE HumanResources.EmployeeOrg  
    (  
       OrgNode hierarchyid PRIMARY KEY CLUSTERED,  
       OrgLevel AS OrgNode.GetLevel(),  
       EmployeeID int UNIQUE NOT NULL,  
       EmpName varchar(20) NOT NULL,  
       Title varchar(20) NULL  
    ) ;  
    GO  
    ```  
  
2.  <span data-ttu-id="84e7e-116">Eseguire il codice riportato di seguito per creare un indice composto per le colonne `OrgLevel` e `OrgNode` al fine di supportare ricerche breadth-first efficienti:</span><span class="sxs-lookup"><span data-stu-id="84e7e-116">Run the following code to create a composite index on the `OrgLevel` and `OrgNode` columns to support efficient breadth-first searches:</span></span>  
  
    ```  
    CREATE UNIQUE INDEX EmployeeOrgNc1   
    ON HumanResources.EmployeeOrg(OrgLevel, OrgNode) ;  
    GO  
    ```  
  
 <span data-ttu-id="84e7e-117">La tabella è ora pronta per i dati.</span><span class="sxs-lookup"><span data-stu-id="84e7e-117">The table is now ready for data.</span></span> <span data-ttu-id="84e7e-118">La prossima attività popolerà la tabella utilizzando metodi gerarchici.</span><span class="sxs-lookup"><span data-stu-id="84e7e-118">The next task will populate the table by using hierarchical methods.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="84e7e-119">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="84e7e-119">Next Task in Lesson</span></span>  
 [<span data-ttu-id="84e7e-120">Popolamento di una tabella gerarchica utilizzando metodi gerarchici</span><span class="sxs-lookup"><span data-stu-id="84e7e-120">Populating a Hierarchical Table Using Hierarchical Methods</span></span>](lesson-2-2-populating-a-hierarchical-table-using-hierarchical-methods.md)  
  
  
