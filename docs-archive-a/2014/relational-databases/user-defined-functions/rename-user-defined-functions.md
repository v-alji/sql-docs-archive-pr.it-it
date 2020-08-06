---
title: Rinominare funzioni definite dall'utente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: c2695a5c-9cc5-4b18-8771-53027ca9a9af
author: rothja
ms.author: jroth
ms.openlocfilehash: ec923be64cf7819c4018ebda71a472f58b29cf8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638329"
---
# <a name="rename-user-defined-functions"></a><span data-ttu-id="dcb27-102">Ridenominare funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="dcb27-102">Rename User-defined Functions</span></span>
  <span data-ttu-id="dcb27-103">È possibile rinominare funzioni definite dall'utente in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dcb27-103">You can rename user-defined functions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="dcb27-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="dcb27-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="dcb27-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="dcb27-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="dcb27-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="dcb27-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="dcb27-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="dcb27-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="dcb27-108">**Rinominare funzioni definite dall'utente tramite:**</span><span class="sxs-lookup"><span data-stu-id="dcb27-108">**To rename user-defined functions, using:**</span></span>  
  
     [<span data-ttu-id="dcb27-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dcb27-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="dcb27-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dcb27-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="dcb27-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="dcb27-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="dcb27-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="dcb27-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="dcb27-113">I nomi di funzione devono essere conformi alla regole per gli [identificatori](../databases/database-identifiers.md).</span><span class="sxs-lookup"><span data-stu-id="dcb27-113">Function names must comply with the rules for [identifiers](../databases/database-identifiers.md).</span></span>  
  
-   <span data-ttu-id="dcb27-114">La ridenominazione di una funzione definita dall'utente non comporta la modifica del nome dell'oggetto corrispondente nella colonna di definizione della vista del catalogo **sys.sql_modules** .</span><span class="sxs-lookup"><span data-stu-id="dcb27-114">Renaming a user-defined function will not change the name of the corresponding object name in the definition column of the **sys.sql_modules** catalog view.</span></span> <span data-ttu-id="dcb27-115">È pertanto consigliabile evitare di rinominare questo tipo di oggetto.</span><span class="sxs-lookup"><span data-stu-id="dcb27-115">Therefore, we recommend that you do not rename this object type.</span></span> <span data-ttu-id="dcb27-116">In alternativa, eliminare e ricreare la stored procedure con il nuovo nome.</span><span class="sxs-lookup"><span data-stu-id="dcb27-116">Instead, drop and re-create the stored procedure with its new name.</span></span>  
  
-   <span data-ttu-id="dcb27-117">La modifica del nome o della definizione di una funzione definita dall'utente può provocare errori degli oggetti dipendenti se questi non vengono aggiornati in base alla modifica apportata alla funzione.</span><span class="sxs-lookup"><span data-stu-id="dcb27-117">Changing the name or definition of a user-defined function can cause dependent objects to fail when the objects are not updated to reflect the changes that have been made to the function.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dcb27-118">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="dcb27-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="dcb27-119">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="dcb27-119">Permissions</span></span>  
 <span data-ttu-id="dcb27-120">Per eliminare la funzione, è necessaria l'autorizzazione ALTER per lo schema a cui appartiene la funzione o l'autorizzazione CONTROL per la funzione.</span><span class="sxs-lookup"><span data-stu-id="dcb27-120">To drop the function, requires either ALTER permission on the schema to which the function belongs or CONTROL permission on the function.</span></span> <span data-ttu-id="dcb27-121">Per ricreare la funzione, sono necessarie l'autorizzazione CREATE FUNCTION per il database e l'autorizzazione ALTER per lo schema in cui viene creata la funzione.</span><span class="sxs-lookup"><span data-stu-id="dcb27-121">To re-create the function, requires CREATE FUNCTION permission in the database and ALTER permission on the schema in which the function is being created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="dcb27-122">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dcb27-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-user-defined-functions"></a><span data-ttu-id="dcb27-123">Per rinominare funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="dcb27-123">To rename user-defined functions</span></span>  
  
1.  <span data-ttu-id="dcb27-124">In **Esplora oggetti**fare clic sul segno più accanto al database che contiene la funzione che si desidera rinominare.</span><span class="sxs-lookup"><span data-stu-id="dcb27-124">In **Object Explorer**, click the plus sign next to the database that contains the function you wish to rename and then</span></span>  
  
2.  <span data-ttu-id="dcb27-125">Fare clic sul segno più accanto alla cartella **Programmabilità** .</span><span class="sxs-lookup"><span data-stu-id="dcb27-125">Click the plus sign next to the **Programmability** folder.</span></span>  
  
3.  <span data-ttu-id="dcb27-126">Fare clic sul segno più accanto alla cartella che contiene la funzione che si desidera rinominare:</span><span class="sxs-lookup"><span data-stu-id="dcb27-126">Click the plus sign next to the folder that contains the function you wish to rename:</span></span>  
  
    -   <span data-ttu-id="dcb27-127">Table-valued Function</span><span class="sxs-lookup"><span data-stu-id="dcb27-127">Table-valued Function</span></span>  
  
    -   <span data-ttu-id="dcb27-128">Funzione a valori scalari</span><span class="sxs-lookup"><span data-stu-id="dcb27-128">Scalar-valued Function</span></span>  
  
    -   <span data-ttu-id="dcb27-129">Funzione di aggregazione</span><span class="sxs-lookup"><span data-stu-id="dcb27-129">Aggregate Function</span></span>  
  
4.  <span data-ttu-id="dcb27-130">Fare clic con il pulsante destro del mouse sulla funzione da rinominare e scegliere **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="dcb27-130">Right-click the function you wish to rename and select **Rename**.</span></span>  
  
5.  <span data-ttu-id="dcb27-131">Immettere il nuovo nome della funzione.</span><span class="sxs-lookup"><span data-stu-id="dcb27-131">Enter the function's new name.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="dcb27-132">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dcb27-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="dcb27-133">**Per rinominare funzioni definite dall'utente**</span><span class="sxs-lookup"><span data-stu-id="dcb27-133">**To rename user-defined functions**</span></span>  
  
 <span data-ttu-id="dcb27-134">Non è possibile eseguire questa attività utilizzando istruzioni Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="dcb27-134">This task cannot be performed using Transact-SQL statements.</span></span> <span data-ttu-id="dcb27-135">Per rinominare una funzione definita dall'utente tramite Transact-SQL, è innanzitutto necessario eliminare la funzione esistente e quindi ricrearla con il nuovo nome.</span><span class="sxs-lookup"><span data-stu-id="dcb27-135">To rename a user-defined function using Transact-SQL, you must first delete the existing function and then re-create it with the new name.</span></span> <span data-ttu-id="dcb27-136">Assicurarsi che tutto il codice e tutte le applicazioni in cui è stato usato il nome precedente della funzione usino ora il nuovo nome.</span><span class="sxs-lookup"><span data-stu-id="dcb27-136">Ensure that all code and applications that used the function's old name now use the new name.</span></span>  
  
 <span data-ttu-id="dcb27-137">Per altre informazioni, vedere [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) e [DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dcb27-137">For more information, see [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) and [DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcb27-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dcb27-138">See Also</span></span>  
 <span data-ttu-id="dcb27-139">[sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dcb27-139">[sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) </span></span>  
 [<span data-ttu-id="dcb27-140">Visualizzare funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="dcb27-140">View User-defined Functions</span></span>](user-defined-functions.md)  
  
  
