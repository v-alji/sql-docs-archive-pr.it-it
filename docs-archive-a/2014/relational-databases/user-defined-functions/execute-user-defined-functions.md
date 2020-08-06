---
title: Eseguire funzioni definite dall'utente | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- invoking user-defined functions
- user-defined functions [SQL Server], executing
ms.assetid: 0de7744d-9b73-463f-ae80-e31a020004b5
author: rothja
ms.author: jroth
ms.openlocfilehash: 4446f3b3a132488fdac6e859f30abaca40a193d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638332"
---
# <a name="execute-user-defined-functions"></a><span data-ttu-id="92fc6-102">Eseguire funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="92fc6-102">Execute User-defined Functions</span></span>
  <span data-ttu-id="92fc6-103">È possibile eseguire una funzione definita dall'utente in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92fc6-103">You can execute a user defined function in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="92fc6-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="92fc6-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="92fc6-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="92fc6-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="92fc6-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="92fc6-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="92fc6-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="92fc6-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="92fc6-108">**Per eseguire una funzione definita dall'utente tramite:**</span><span class="sxs-lookup"><span data-stu-id="92fc6-108">**To execute a user-defined function, using:**</span></span>  
  
     [<span data-ttu-id="92fc6-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="92fc6-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="92fc6-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="92fc6-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="92fc6-111">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="92fc6-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="92fc6-112">In Transact-SQL è possibile specificare parametri tramite *valore* o*parameter_name*=*valore.*</span><span class="sxs-lookup"><span data-stu-id="92fc6-112">In Transact-SQL, parameters can be supplied either by using *value* or by using @*parameter_name*=*value.*</span></span> <span data-ttu-id="92fc6-113">Un parametro non fa parte di una transazione. Se un parametro viene modificato in una transazione per la quale verrà eseguito il rollback, il valore del parametro non viene ripristinato al suo valore precedente.</span><span class="sxs-lookup"><span data-stu-id="92fc6-113">A parameter is not part of a transaction; therefore, if a parameter is changed in a transaction that is later rolled back, the value of the parameter does not revert to its previous value.</span></span> <span data-ttu-id="92fc6-114">Il valore restituito al chiamante corrisponde sempre al valore specificato al termine del modulo.</span><span class="sxs-lookup"><span data-stu-id="92fc6-114">The value returned to the caller is always the value at the time the module returns.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="92fc6-115">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="92fc6-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="92fc6-116">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="92fc6-116">Permissions</span></span>  
 <span data-ttu-id="92fc6-117">Per eseguire l'istruzione EXECUTE, non è necessario disporre di autorizzazioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="92fc6-117">Permissions are not required to run the EXECUTE statement.</span></span> <span data-ttu-id="92fc6-118">Sono tuttavia richieste autorizzazioni per le entità a protezione diretta a cui viene fatto riferimento all'interno della stringa EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="92fc6-118">However, permissions are required on the securables that are referenced within the EXECUTE string.</span></span> <span data-ttu-id="92fc6-119">Se, ad esempio, la stringa include un'istruzione INSERT, il chiamante dell'istruzione EXECUTE deve disporre dell'autorizzazione INSERT per la tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="92fc6-119">For example, if the string contains an INSERT statement, the caller of the EXECUTE statement must have INSERT permission on the target table.</span></span> <span data-ttu-id="92fc6-120">Le autorizzazioni vengono verificate non appena viene rilevata l'istruzione EXECUTE, anche se l'istruzione è inclusa in un modulo.</span><span class="sxs-lookup"><span data-stu-id="92fc6-120">Permissions are checked at the time EXECUTE statement is encountered, even if the EXECUTE statement is included within a module.</span></span> <span data-ttu-id="92fc6-121">Per altre informazioni, vedere [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="92fc6-121">For more information, see [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql)</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="92fc6-122">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="92fc6-122">Using Transact-SQL</span></span>  
  
#### <a name="to-execute-a-user-defined-function"></a><span data-ttu-id="92fc6-123">Per eseguire una funzione definita dall'utente</span><span class="sxs-lookup"><span data-stu-id="92fc6-123">To execute a user-defined function</span></span>  
  
1.  <span data-ttu-id="92fc6-124">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92fc6-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="92fc6-125">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="92fc6-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="92fc6-126">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="92fc6-126">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Declares a variable and sets it to zero.  
    -- This variable is used to return the results of the function.  
    DECLARE @ret nvarchar(15)= NULL;   
  
    -- Executes the dbo.ufnGetSalesOrderStatusText function.  
    --The function requires a value for one parameter, @Status.   
    EXEC @ret = dbo.ufnGetSalesOrderStatusText @Status= 5;   
    --Returns the result in the message tab.  
    PRINT @ret;  
    ```  
  
 <span data-ttu-id="92fc6-127">Per altre informazioni, vedere [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="92fc6-127">For more information, see [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span></span>  
  
  
