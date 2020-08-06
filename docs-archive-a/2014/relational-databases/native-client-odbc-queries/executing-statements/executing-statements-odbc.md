---
title: Esecuzione di istruzioni (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, statements
- statements [ODBC]
- ODBC applications, statements
- statements [ODBC], executing
ms.assetid: 063fc40d-ff81-490d-9c9b-2faefb729f37
author: rothja
ms.author: jroth
ms.openlocfilehash: 3066a09cb1f5e63105ca3ffe2441f19e4bbe0101
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624115"
---
# <a name="executing-statements-odbc"></a><span data-ttu-id="cdb11-102">Esecuzione di istruzioni (ODBC)</span><span class="sxs-lookup"><span data-stu-id="cdb11-102">Executing Statements (ODBC)</span></span>
  <span data-ttu-id="cdb11-103">Il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC di Native Client offre diversi modi per eseguire istruzioni SQL in un [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database:</span><span class="sxs-lookup"><span data-stu-id="cdb11-103">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver offers a variety ways to execute SQL statements in a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database:</span></span>  
  
-   <span data-ttu-id="cdb11-104">Esecuzione diretta</span><span class="sxs-lookup"><span data-stu-id="cdb11-104">Direct execution</span></span>  
  
-   <span data-ttu-id="cdb11-105">Esecuzione preparata</span><span class="sxs-lookup"><span data-stu-id="cdb11-105">Prepared execution</span></span>  
  
 <span data-ttu-id="cdb11-106">L'esecuzione diretta implica la compilazione di una stringa di caratteri contenente un' [!INCLUDE[tsql](../../../includes/tsql-md.md)] istruzione e l'invio per l'esecuzione tramite la funzione **SQLExecDirect** .</span><span class="sxs-lookup"><span data-stu-id="cdb11-106">Direct execution involves building a character string containing a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement and submitting it for execution using the **SQLExecDirect** function.</span></span> <span data-ttu-id="cdb11-107">L'esecuzione preparata implica la compilazione di una stringa di caratteri contenente un'istruzione [!INCLUDE[tsql](../../../includes/tsql-md.md)] e la successiva esecuzione di questa in due fasi.</span><span class="sxs-lookup"><span data-stu-id="cdb11-107">Prepared execution involves building a character string containing a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement and then executing it in two stages.</span></span> <span data-ttu-id="cdb11-108">Nella prima fase viene utilizzata la funzione [SQLPrepare function](https://go.microsoft.com/fwlink/?LinkId=59360) per analizzare e compilare il piano di esecuzione per l'istruzione in [!INCLUDE[ssDE](../../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cdb11-108">The first stage uses the [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360) function to parse and compile the execution plan for the statement in the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span> <span data-ttu-id="cdb11-109">Nella seconda fase viene utilizzata la funzione **SQLExecute** per eseguire il piano di esecuzione preparato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="cdb11-109">The second stage uses the **SQLExecute** function to execute the previously prepared execution plan.</span></span> <span data-ttu-id="cdb11-110">con conseguente risparmio dell'overhead correlato all'analisi e alla compilazione in ogni esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cdb11-110">This saves the parsing and compiling overhead on each execution.</span></span> <span data-ttu-id="cdb11-111">L'esecuzione preparata viene generalmente utilizzata dalle applicazioni per eseguire ripetutamente la stessa istruzione SQL con parametri.</span><span class="sxs-lookup"><span data-stu-id="cdb11-111">Prepared execution is commonly used by applications to repeatedly execute the same, parameterized SQL statement.</span></span>  
  
 <span data-ttu-id="cdb11-112">Sia nel caso dell'esecuzione diretta che in quello dell'esecuzione preparata è possibile eseguire una singola istruzione [!INCLUDE[tsql](../../../includes/tsql-md.md)] o un batch di istruzioni SQL oppure è possibile chiamare una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="cdb11-112">Both direct and prepared execution can execute a single [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement or a batch of SQL statements, or they can call a stored procedure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cdb11-113">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="cdb11-113">In This Section</span></span>  
  
-   [<span data-ttu-id="cdb11-114">Esecuzione diretta</span><span class="sxs-lookup"><span data-stu-id="cdb11-114">Direct Execution</span></span>](direct-execution.md)  
  
-   [<span data-ttu-id="cdb11-115">Esecuzione preparata</span><span class="sxs-lookup"><span data-stu-id="cdb11-115">Prepared Execution</span></span>](prepared-execution.md)  
  
-   [<span data-ttu-id="cdb11-116">Procedure</span><span class="sxs-lookup"><span data-stu-id="cdb11-116">Procedures</span></span>](procedures.md)  
  
-   [<span data-ttu-id="cdb11-117">Batch di istruzioni</span><span class="sxs-lookup"><span data-stu-id="cdb11-117">Batches of Statements</span></span>](batches-of-statements.md)  
  
-   [<span data-ttu-id="cdb11-118">Effetti delle opzioni ISO</span><span class="sxs-lookup"><span data-stu-id="cdb11-118">Effects of ISO Options</span></span>](effects-of-iso-options.md)  
  
## <a name="see-also"></a><span data-ttu-id="cdb11-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cdb11-119">See Also</span></span>  
 [<span data-ttu-id="cdb11-120">Esecuzione di query &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="cdb11-120">Executing Queries &#40;ODBC&#41;</span></span>](../executing-queries-odbc.md)  
  
  
