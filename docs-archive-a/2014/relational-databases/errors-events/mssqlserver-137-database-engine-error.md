---
title: MSSQLSERVER_137 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 137 (Database Engine error)
ms.assetid: 47fb4212-2165-4fec-bc41-6d548465d7be
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e0142cd53006609e9274972e4f5964132f5982c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636176"
---
# <a name="mssqlserver_137"></a><span data-ttu-id="3ca94-102">MSSQLSERVER_137</span><span class="sxs-lookup"><span data-stu-id="3ca94-102">MSSQLSERVER_137</span></span>
    
## <a name="details"></a><span data-ttu-id="3ca94-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3ca94-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3ca94-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="3ca94-104">Product Name</span></span>|<span data-ttu-id="3ca94-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3ca94-105">SQL Server</span></span>|  
|<span data-ttu-id="3ca94-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="3ca94-106">Event ID</span></span>|<span data-ttu-id="3ca94-107">137</span><span class="sxs-lookup"><span data-stu-id="3ca94-107">137</span></span>|  
|<span data-ttu-id="3ca94-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="3ca94-108">Event Source</span></span>|<span data-ttu-id="3ca94-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3ca94-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3ca94-110">Componente</span><span class="sxs-lookup"><span data-stu-id="3ca94-110">Component</span></span>|<span data-ttu-id="3ca94-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3ca94-111">SQLEngine</span></span>|  
|<span data-ttu-id="3ca94-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="3ca94-112">Symbolic Name</span></span>|<span data-ttu-id="3ca94-113">P_SCALAR_VAR_NOTFOUND</span><span class="sxs-lookup"><span data-stu-id="3ca94-113">P_SCALAR_VAR_NOTFOUND</span></span>|  
|<span data-ttu-id="3ca94-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="3ca94-114">Message Text</span></span>|<span data-ttu-id="3ca94-115">Dichiarare la variabile scalare "%.\*ls".</span><span class="sxs-lookup"><span data-stu-id="3ca94-115">Must declare the scalar variable "%.\*ls".</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3ca94-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="3ca94-116">Explanation</span></span>  
 <span data-ttu-id="3ca94-117">Questo errore si verifica quando una variabile viene utilizzata in uno script SQL senza essere stata dichiarata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="3ca94-117">This error occurs when a variable is used in a SQL script without first declaring the variable.</span></span> <span data-ttu-id="3ca94-118">Nell'esempio seguente viene restituito l'errore 137 per entrambe le istruzioni SET e SELECT perché **@mycol** non è dichiarato.</span><span class="sxs-lookup"><span data-stu-id="3ca94-118">The following example returns error 137 for both the SET and SELECT statements because **@mycol** is not declared.</span></span>  
  
 <span data-ttu-id="3ca94-119">SET @mycol = 'ContactName';</span><span class="sxs-lookup"><span data-stu-id="3ca94-119">SET @mycol = 'ContactName';</span></span>  
  
 <span data-ttu-id="3ca94-120">SELECT @mycol;</span><span class="sxs-lookup"><span data-stu-id="3ca94-120">SELECT @mycol;</span></span>  
  
 <span data-ttu-id="3ca94-121">Una delle cause più complesse di questo errore include l'utilizzo di una variabile dichiarata al di fuori dell'istruzione EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="3ca94-121">One of the more complicated causes of this error includes the use of a variable that is declared outside the EXECUTE statement.</span></span> <span data-ttu-id="3ca94-122">La variabile **@mycol** specificata nell'istruzione SELECT, ad esempio, è locale per l'istruzione SELECT, quindi è esterna all'istruzione Execute.</span><span class="sxs-lookup"><span data-stu-id="3ca94-122">For example, the variable **@mycol** specified in the SELECT statement is local to the SELECT statement; thus it is outside the EXECUTE statement.</span></span>  
  
 <span data-ttu-id="3ca94-123">USE AdventureWorks2012;</span><span class="sxs-lookup"><span data-stu-id="3ca94-123">USE AdventureWorks2012;</span></span>  
  
 <span data-ttu-id="3ca94-124">GO</span><span class="sxs-lookup"><span data-stu-id="3ca94-124">GO</span></span>  
  
 <span data-ttu-id="3ca94-125">DECLARE @mycol nvarchar(20);</span><span class="sxs-lookup"><span data-stu-id="3ca94-125">DECLARE @mycol nvarchar(20);</span></span>  
  
 <span data-ttu-id="3ca94-126">SET @mycol = 'Name';</span><span class="sxs-lookup"><span data-stu-id="3ca94-126">SET @mycol = 'Name';</span></span>  
  
 <span data-ttu-id="3ca94-127">EXECUTE ('SELECT @mycol FROM Production.Product;');</span><span class="sxs-lookup"><span data-stu-id="3ca94-127">EXECUTE ('SELECT @mycol FROM Production.Product;');</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3ca94-128">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="3ca94-128">User Action</span></span>  
 <span data-ttu-id="3ca94-129">Verificare che qualsiasi variabile utilizzata in uno script SQL venga dichiarata prima di essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="3ca94-129">Verify that any variables used in a SQL script are declared before being used elsewhere in the script.</span></span>  
  
 <span data-ttu-id="3ca94-130">Riscrivere lo script in modo che non faccia riferimento a variabili nell'istruzione EXECUTE dichiarate al di fuori dell'istruzione stessa.</span><span class="sxs-lookup"><span data-stu-id="3ca94-130">Rewrite the script so that it does not reference variables in the EXECUTE statement that are declared outside of it.</span></span> <span data-ttu-id="3ca94-131">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3ca94-131">For example:</span></span>  
  
 <span data-ttu-id="3ca94-132">USE AdventureWorks2012;</span><span class="sxs-lookup"><span data-stu-id="3ca94-132">USE AdventureWorks2012;</span></span>  
  
 <span data-ttu-id="3ca94-133">GO</span><span class="sxs-lookup"><span data-stu-id="3ca94-133">GO</span></span>  
  
 <span data-ttu-id="3ca94-134">DECLARE @mycol nvarchar(20) ;</span><span class="sxs-lookup"><span data-stu-id="3ca94-134">DECLARE @mycol nvarchar(20) ;</span></span>  
  
 <span data-ttu-id="3ca94-135">SET @mycol = 'Name';</span><span class="sxs-lookup"><span data-stu-id="3ca94-135">SET @mycol = 'Name';</span></span>  
  
 <span data-ttu-id="3ca94-136">EXECUTE ('SELECT ' + @mycol + ' FROM Production.Product';) ;</span><span class="sxs-lookup"><span data-stu-id="3ca94-136">EXECUTE ('SELECT ' + @mycol + ' FROM Production.Product';) ;</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ca94-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ca94-137">See Also</span></span>  
 <span data-ttu-id="3ca94-138">[EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3ca94-138">[EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql) </span></span>  
 <span data-ttu-id="3ca94-139">[Istruzioni SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3ca94-139">[SET Statements &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statements-transact-sql) </span></span>  
 [<span data-ttu-id="3ca94-140">DECLARE @local_variable &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3ca94-140">DECLARE @local_variable &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/declare-local-variable-transact-sql)  
  
  
