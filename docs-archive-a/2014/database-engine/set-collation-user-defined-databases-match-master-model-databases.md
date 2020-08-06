---
title: Impostare le regole di confronto dei database definiti dall'utente in modo che corrispondano a quelle dei database master e modello | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: c686446f-dae1-4b05-a3df-837b3422988d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b48696fb56c40062d62f04845715170887f84fda
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712344"
---
# <a name="set-the-collation-of-user-defined-databases-to-match-those-of-the-master-and-model-databases"></a><span data-ttu-id="0ce5f-102">Impostazione delle regole di confronto dei database definiti dall'utente in modo che corrispondano a quelle dei database master e modello</span><span class="sxs-lookup"><span data-stu-id="0ce5f-102">Set the Collation of User-defined Databases to Match Those of the master and model Databases</span></span>
  <span data-ttu-id="0ce5f-103">Questa regola consente di controllare se i database definiti dall'utente vengono configurati utilizzando le stesse regole di confronto di quelle per i database master e modello.</span><span class="sxs-lookup"><span data-stu-id="0ce5f-103">This rule checks whether user-defined databases are defined by using a database collation that is the same as the collation for master or model.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="0ce5f-104">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="0ce5f-104">Best Practices Recommendations</span></span>  
 <span data-ttu-id="0ce5f-105">È consigliabile fare in modo che le regole di confronto dei database definiti dall'utente corrispondano a quelle dei database master e modello.</span><span class="sxs-lookup"><span data-stu-id="0ce5f-105">We recommend that the collations of user-defined databases match the collation of master or model.</span></span> <span data-ttu-id="0ce5f-106">In caso contrario, possono verificarsi conflitti relativi alle regole di confronto che potrebbero impedire l'esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="0ce5f-106">Otherwise, collation conflicts can occur that might prevent code from executing.</span></span> <span data-ttu-id="0ce5f-107">Quando, ad esempio, una stored procedure crea un join tra una tabella e una tabella temporanea, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] potrebbe terminare il batch e restituire un errore di conflitto tra regole di confronto se le regole di confronto del database definito dall'utente differiscono da quelle del database modello.</span><span class="sxs-lookup"><span data-stu-id="0ce5f-107">For example, when a stored procedure joins one table to a temporary table, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] might end the batch and return a collation conflict error if the collations of the user-defined database and the model database are different.</span></span> <span data-ttu-id="0ce5f-108">Questo problema si verifica perché le tabelle temporanee vengono create in tempdb, che basa le proprie regole di confronto su quelle del modello.</span><span class="sxs-lookup"><span data-stu-id="0ce5f-108">This occurs because temporary tables are created in tempdb, which bases its collation on that of model.</span></span>  
  
 <span data-ttu-id="0ce5f-109">In caso di errori di conflitto tra regole di confronto, considerare una delle soluzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0ce5f-109">If you experience collation conflict errors, consider one of the following solutions:</span></span>  
  
-   <span data-ttu-id="0ce5f-110">Esportare i dati dal database utente e importarli nelle nuove tabelle che utilizzano le stesse regole di confronto dei database master e modello.</span><span class="sxs-lookup"><span data-stu-id="0ce5f-110">Export the data from the user database and import it into new tables that have the same collation as the master and model databases.</span></span>  
  
-   <span data-ttu-id="0ce5f-111">Ricompilare i database di sistema in modo che vengano utilizzate regole di confronto corrispondenti a quelle del database utente.</span><span class="sxs-lookup"><span data-stu-id="0ce5f-111">Rebuild the system databases to use a collation that matches the user database collation.</span></span> <span data-ttu-id="0ce5f-112">Per ulteriori informazioni su come ricompilare i database di sistema, vedere [ricompilare i database di sistema](../relational-databases/databases/system-databases.md).</span><span class="sxs-lookup"><span data-stu-id="0ce5f-112">For more information about how to rebuild the system databases, see [Rebuild System Databases](../relational-databases/databases/system-databases.md).</span></span>  
  
-   <span data-ttu-id="0ce5f-113">Modificare qualsiasi stored procedure che crea join tra tabelle utente e tabelle in tempdb per creare le tabelle in tempdb utilizzando le regole di confronto del database utente.</span><span class="sxs-lookup"><span data-stu-id="0ce5f-113">Modify any stored procedures that join user tables to tables in tempdb to create the tables in tempdb by using the collation of the user database.</span></span> <span data-ttu-id="0ce5f-114">A tale scopo, aggiungere la clausola `COLLATE database_default` alle definizioni di colonna della tabella temporanea, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0ce5f-114">To do this, add the `COLLATE database_default` clause to the column definitions of the temporary table, as shown in the following example:</span></span>  
  
    ```  
    CREATE TABLE #temp1 ( c1 int, c2 varchar(30) COLLATE database_default )  
    ```  
  
## <a name="for-more-information"></a><span data-ttu-id="0ce5f-115">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="0ce5f-115">For More Information</span></span>  
 [<span data-ttu-id="0ce5f-116">Impostare o modificare le regole di confronto del database</span><span class="sxs-lookup"><span data-stu-id="0ce5f-116">Set or Change the Database Collation</span></span>](../relational-databases/collations/set-or-change-the-database-collation.md)  
  
 [<span data-ttu-id="0ce5f-117">Impostare o modificare le regole di confronto delle colonne</span><span class="sxs-lookup"><span data-stu-id="0ce5f-117">Set or Change the Column Collation</span></span>](../relational-databases/collations/set-or-change-the-column-collation.md)  
  
 [<span data-ttu-id="0ce5f-118">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0ce5f-118">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
 [<span data-ttu-id="0ce5f-119">COLLATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0ce5f-119">COLLATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/collations)  
  
 [<span data-ttu-id="0ce5f-120">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0ce5f-120">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
 [<span data-ttu-id="0ce5f-121">Articolo 325335 della Microsoft Knowledge base</span><span class="sxs-lookup"><span data-stu-id="0ce5f-121">Microsoft Knowledge Base article 325335</span></span>](https://go.microsoft.com/fwlink/?linkid=117751)  
  
 [<span data-ttu-id="0ce5f-122">Procedura: Installazione di SQL Server 2008 dal prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="0ce5f-122">How to: Install SQL Server 2008 from the Command Prompt</span></span>](https://go.microsoft.com/fwlink/?LinkId=81585)  
  
## <a name="see-also"></a><span data-ttu-id="0ce5f-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ce5f-123">See Also</span></span>  
 [<span data-ttu-id="0ce5f-124">Monitorare e applicare le procedure consigliate tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="0ce5f-124">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
