---
title: Impostare le opzioni del cursore (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], options
ms.assetid: 0e72b48a-fc5a-4656-8cf5-39f57d8c1565
author: rothja
ms.author: jroth
ms.openlocfilehash: 877c2596c87ce50295a15912493661c6dd4e0305
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723807"
---
# <a name="set-cursor-options-odbc"></a><span data-ttu-id="545d1-102">Impostare le opzioni del cursore (ODBC)</span><span class="sxs-lookup"><span data-stu-id="545d1-102">Set Cursor Options (ODBC)</span></span>
  <span data-ttu-id="545d1-103">Per impostare le opzioni del cursore, chiamare [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) per impostare o [SQLGetStmtAttr](../../native-client-odbc-api/sqlgetstmtattr.md) per ottenere le opzioni di istruzione che controllano il comportamento del cursore.</span><span class="sxs-lookup"><span data-stu-id="545d1-103">To set cursor options, Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set or [SQLGetStmtAttr](../../native-client-odbc-api/sqlgetstmtattr.md) to get the statement options that control cursor behavior.</span></span>  
  
|<span data-ttu-id="545d1-104">*Attributo*</span><span class="sxs-lookup"><span data-stu-id="545d1-104">*Attribute*</span></span>|<span data-ttu-id="545d1-105">Specifica</span><span class="sxs-lookup"><span data-stu-id="545d1-105">Specifies</span></span>|  
|-----------------|---------------|  
|<span data-ttu-id="545d1-106">SQL_ATTR_CURSOR_TYPE</span><span class="sxs-lookup"><span data-stu-id="545d1-106">SQL_ATTR_CURSOR_TYPE</span></span>|<span data-ttu-id="545d1-107">Tipo di cursore: forward only, statico, dinamico o gestito da keyset</span><span class="sxs-lookup"><span data-stu-id="545d1-107">Cursor type of forward-only, static, dynamic, or keyset-driven</span></span>|  
|<span data-ttu-id="545d1-108">SQL_ATTR_CONCURRENCY</span><span class="sxs-lookup"><span data-stu-id="545d1-108">SQL_ATTR_CONCURRENCY</span></span>|<span data-ttu-id="545d1-109">Opzione di controllo della concorrenza: di sola lettura, di blocco, ottimistica che utilizza timestamp o ottimistica che utilizza valori</span><span class="sxs-lookup"><span data-stu-id="545d1-109">Concurrency control option of read-only, locking, optimistic using timestamps, or optimistic using values</span></span>|  
|<span data-ttu-id="545d1-110">SQL_ATTR_ROW_ARRAY_SIZE</span><span class="sxs-lookup"><span data-stu-id="545d1-110">SQL_ATTR_ROW_ARRAY_SIZE</span></span>|<span data-ttu-id="545d1-111">Numero di righe recuperate in ogni operazione di recupero</span><span class="sxs-lookup"><span data-stu-id="545d1-111">Number of rows retrieved in each fetch</span></span>|  
|<span data-ttu-id="545d1-112">SQL_ATTR_CURSOR_SENSITIVITY</span><span class="sxs-lookup"><span data-stu-id="545d1-112">SQL_ATTR_CURSOR_SENSITIVITY</span></span>|<span data-ttu-id="545d1-113">Cursore che mostra o non mostra aggiornamenti a righe di cursore create da altre connessioni</span><span class="sxs-lookup"><span data-stu-id="545d1-113">Cursor that does or does not show updates to cursor rows made by other connections</span></span>|  
|<span data-ttu-id="545d1-114">SQL_ATTR_CURSOR_SCROLLABLE</span><span class="sxs-lookup"><span data-stu-id="545d1-114">SQL_ATTR_CURSOR_SCROLLABLE</span></span>|<span data-ttu-id="545d1-115">Cursore che è possibile scorrere in avanti e indietro</span><span class="sxs-lookup"><span data-stu-id="545d1-115">Cursor that can be scrolled forward and backward</span></span>|  
  
 <span data-ttu-id="545d1-116">I valori predefiniti per questi attributi (forward only, di sola lettura, dimensione 1 del set di righe) non determinano l'utilizzo dei cursori server.</span><span class="sxs-lookup"><span data-stu-id="545d1-116">The default values for these attributes (forward-only, read-only, rowset size of 1) do not use server cursors.</span></span> <span data-ttu-id="545d1-117">Per utilizzare i cursori server, è necessario che almeno uno di questi attributi sia impostato su un valore diverso dall'impostazione predefinita e che l'istruzione eseguita sia un'istruzione SELECT singola o una stored procedure che contiene un'istruzione SELECT singola.</span><span class="sxs-lookup"><span data-stu-id="545d1-117">To use server cursors, at least one of these attributes must be set to a value other than the default, and the statement being executed must be a single SELECT statement or a stored procedure that contains a single SELECT statement.</span></span> <span data-ttu-id="545d1-118">In caso di utilizzo di cursori server, le istruzioni SELECT non possono utilizzare le clausole non supportate dai cursori server: COMPUTE, COMPUTE BY, FOR BROWSE e INTO.</span><span class="sxs-lookup"><span data-stu-id="545d1-118">When using server cursors, SELECT statements cannot use clauses not supported by server cursors: COMPUTE, COMPUTE BY, FOR BROWSE, and INTO.</span></span>  
  
 <span data-ttu-id="545d1-119">È possibile controllare il tipo di cursore utilizzato impostando SQL_ATTR_CURSOR_TYPE e SQL_ATTR_CONCURRENCY oppure impostando SQL_ATTR_CURSOR_SENSITIVITY e SQL_ATTR_CURSOR_SCROLLABLE.</span><span class="sxs-lookup"><span data-stu-id="545d1-119">You can control the type of cursor used either by setting SQL_ATTR_CURSOR_TYPE and SQL_ATTR_CONCURRENCY, or by setting SQL_ATTR_CURSOR_SENSITIVITY and SQL_ATTR_CURSOR_SCROLLABLE.</span></span> <span data-ttu-id="545d1-120">È consigliabile non combinare i due metodi di definizione del comportamento del cursore.</span><span class="sxs-lookup"><span data-stu-id="545d1-120">You should not mix the two methods of specifying cursor behavior.</span></span>  
  
## <a name="example"></a><span data-ttu-id="545d1-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="545d1-121">Example</span></span>  
 <span data-ttu-id="545d1-122">Nell'esempio seguente viene allocato un handle di istruzione, viene impostato un tipo di cursore dinamico con concorrenza ottimistica del controllo delle versioni delle righe, quindi viene eseguita un'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="545d1-122">The following sample allocates a statement handle, sets a dynamic cursor type with row versioning optimistic concurrency, and then executes a SELECT.</span></span>  
  
```  
retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
retcode = SQLSetStmtAttr(hstmt1, SQL_ATTR_CURSOR_TYPE, (SQLPOINTER)SQL_CURSOR_DYNAMIC, SQL_IS_INTEGER);  
retcode = SQLSetStmtAttr(hstmt1, SQL_ATTR_CONCURRENCY, SQLPOINTER)SQL_CONCUR_ROWVER, SQL_IS_INTEGER);  
retcode = SQLExecDirect(hstmt1, SELECT au_lname FROM authors", SQL_NTS);  
```  
  
## <a name="example"></a><span data-ttu-id="545d1-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="545d1-123">Example</span></span>  
 <span data-ttu-id="545d1-124">Nell'esempio seguente viene allocato un handle di istruzione, viene impostato un cursore scorrevole di tipo sensitive, quindi viene eseguita un'istruzione SELECT</span><span class="sxs-lookup"><span data-stu-id="545d1-124">The following sample allocates a statement handle, sets a scrollable, sensitive cursor, and then executes a SELECT</span></span>  
  
```  
retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
  
// Set the cursor options and execute the statement.  
retcode = SQLSetStmtAttr(hstmt1, SQL_ATTR_CURSOR_SCROLLABLE, SQLPOINTER)SQL_SCROLLABLE, SQL_IS_INTEGER);  
retcode = SQLSetStmtAttr(hstmt1, SQL_ATTR_CURSOR_SENSITIVITY, SQLPOINTER)SQL_INSENSITIVE, SQL_IS_INTEGER);  
retcode = SQLExecDirect(hstmt1, select au_lname from authors", SQL_NTS);  
```  
  
## <a name="see-also"></a><span data-ttu-id="545d1-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="545d1-125">See Also</span></span>  
 [<span data-ttu-id="545d1-126">Procedure relative all'esecuzione di query &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="545d1-126">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](executing-queries-how-to-topics-odbc.md)  
  
  
