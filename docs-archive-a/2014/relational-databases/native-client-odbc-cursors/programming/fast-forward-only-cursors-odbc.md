---
title: Cursori fast-Only (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- fast forward-only cursors
- forward-only cursors
- cursors [ODBC], fast forward-only
- ODBC cursors, fast forward-only
ms.assetid: 0707d07e-fc95-42ed-9280-b7e508ac8c62
author: rothja
ms.author: jroth
ms.openlocfilehash: de8d82a0c72ad51741a3785fba2910f691028cba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635558"
---
# <a name="fast-forward-only-cursors-odbc"></a><span data-ttu-id="4d118-102">Cursori fast forward only (ODBC)</span><span class="sxs-lookup"><span data-stu-id="4d118-102">Fast Forward-Only Cursors (ODBC)</span></span>
  <span data-ttu-id="4d118-103">Quando si è connessi a un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC di Native Client supporta le ottimizzazioni delle prestazioni per i cursori di sola lettura e di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="4d118-103">When connected to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports performance optimizations for forward-only, read-only cursors.</span></span> <span data-ttu-id="4d118-104">I cursori fast forward only vengono implementati internamente dal driver e dal server in modo molto simile ai set di risultati predefiniti.</span><span class="sxs-lookup"><span data-stu-id="4d118-104">Fast forward-only cursors are implemented internally by the driver and server in a manner very similar to default result sets.</span></span> <span data-ttu-id="4d118-105">Oltre a offrire prestazioni elevate, i cursori fast forward only possono presentare anche le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d118-105">Besides having high performance, fast forward-only cursors also have these characteristics:</span></span>  
  
-   <span data-ttu-id="4d118-106">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) non è supportato.</span><span class="sxs-lookup"><span data-stu-id="4d118-106">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) is not supported.</span></span> <span data-ttu-id="4d118-107">Le colonne del set di risultati devono essere associate a variabili di programma.</span><span class="sxs-lookup"><span data-stu-id="4d118-107">The result set columns must be bound to program variables.</span></span>  
  
-   <span data-ttu-id="4d118-108">Quando viene rilevata la fine del cursore, questo viene chiuso automaticamente dal server.</span><span class="sxs-lookup"><span data-stu-id="4d118-108">The server automatically closes the cursor when the end of the cursor is detected.</span></span> <span data-ttu-id="4d118-109">L'applicazione deve comunque chiamare [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) o [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md)(SQL_CLOSE), ma il driver non deve inviare la richiesta di chiusura al server.</span><span class="sxs-lookup"><span data-stu-id="4d118-109">The application must still call [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) or [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md)(SQL_CLOSE), but the driver does not have to send the close request to the server.</span></span> <span data-ttu-id="4d118-110">In questo modo viene evitato un round trip del server nella rete.</span><span class="sxs-lookup"><span data-stu-id="4d118-110">This saves a roundtrip across the network to the server.</span></span>  
  
 <span data-ttu-id="4d118-111">L'applicazione richiede cursori fast forward only mediante l'attributo dell'istruzione SQL_SOPT_SS_CURSOR_OPTIONS specifica del driver.</span><span class="sxs-lookup"><span data-stu-id="4d118-111">The application requests fast forward-only cursors using the driver-specific statement attribute SQL_SOPT_SS_CURSOR_OPTIONS.</span></span> <span data-ttu-id="4d118-112">Quando l'attributo è impostato su SQL_CO_FFO, i cursori fast forward only vengono abilitati senza recupero automatico.</span><span class="sxs-lookup"><span data-stu-id="4d118-112">When set to SQL_CO_FFO, fast forward-only cursors are enabled without autofetch.</span></span> <span data-ttu-id="4d118-113">Quando l'attributo è impostato su SQL_CO_FFO_AF, viene abilitata anche l'opzione per il recupero automatico.</span><span class="sxs-lookup"><span data-stu-id="4d118-113">When set to SQL_CO_FFO_AF, the autofetch option is also enabled.</span></span> <span data-ttu-id="4d118-114">Per ulteriori informazioni sul recupero automatico, vedere [utilizzo del recupero automatico con i cursori ODBC](using-autofetch-with-odbc-cursors.md).</span><span class="sxs-lookup"><span data-stu-id="4d118-114">For more information about autofetch, see [Using Autofetch with ODBC Cursors](using-autofetch-with-odbc-cursors.md).</span></span>  
  
 <span data-ttu-id="4d118-115">I cursori fast forward only con recupero automatico possono essere utilizzati per recuperare un set di risultati di piccole dimensioni con un solo round trip del server.</span><span class="sxs-lookup"><span data-stu-id="4d118-115">Fast forward-only cursors with autofetch can be used to retrieve a small result set with only one roundtrip to the server.</span></span> <span data-ttu-id="4d118-116">In questi passaggi, *n* è il numero di righe da restituire:</span><span class="sxs-lookup"><span data-stu-id="4d118-116">In these steps, *n* is the number of rows to be returned:</span></span>  
  
1.  <span data-ttu-id="4d118-117">Impostare SQL_SOPT_SS_CURSOR_OPTIONS su SQL_CO_FFO_AF.</span><span class="sxs-lookup"><span data-stu-id="4d118-117">Set SQL_SOPT_SS_CURSOR_OPTIONS to SQL_CO_FFO_AF.</span></span>  
  
2.  <span data-ttu-id="4d118-118">Impostare SQL_ATTR_ROW_ARRAY_SIZE su *n* + 1.</span><span class="sxs-lookup"><span data-stu-id="4d118-118">Set SQL_ATTR_ROW_ARRAY_SIZE to *n* + 1.</span></span>  
  
3.  <span data-ttu-id="4d118-119">Associare le colonne dei risultati a matrici di *n* + 1 elementi (per essere sicuri se vengono effettivamente recuperate *n* + 1 righe).</span><span class="sxs-lookup"><span data-stu-id="4d118-119">Bind the result columns to arrays of *n* + 1 elements (to be safe if *n* + 1 rows are actually fetched).</span></span>  
  
4.  <span data-ttu-id="4d118-120">Aprire il cursore con **SQLExecDirect** o **SQLExecute**.</span><span class="sxs-lookup"><span data-stu-id="4d118-120">Open the cursor with either **SQLExecDirect** or **SQLExecute**.</span></span>  
  
5.  <span data-ttu-id="4d118-121">Se lo stato restituito è SQL_SUCCESS, chiamare **SQLFreeStmt** o **SQLCloseCursor** per chiudere il cursore.</span><span class="sxs-lookup"><span data-stu-id="4d118-121">If the return status is SQL_SUCCESS, then call **SQLFreeStmt** or **SQLCloseCursor** to close the cursor.</span></span> <span data-ttu-id="4d118-122">Tutti i dati delle righe si troveranno nelle variabili di programma associate.</span><span class="sxs-lookup"><span data-stu-id="4d118-122">All data for the rows will be in the bound program variables.</span></span>  
  
 <span data-ttu-id="4d118-123">Con questi passaggi, **SQLExecDirect** o **SQLExecute** invia una richiesta di apertura del cursore con l'opzione di recupero automatico abilitata.</span><span class="sxs-lookup"><span data-stu-id="4d118-123">With these steps, the **SQLExecDirect** or **SQLExecute** sends a cursor open request with the autofetch option enabled.</span></span> <span data-ttu-id="4d118-124">Nella singola richiesta proveniente dal client il server:</span><span class="sxs-lookup"><span data-stu-id="4d118-124">On that single request from the client, the server:</span></span>  
  
-   <span data-ttu-id="4d118-125">Apre il cursore.</span><span class="sxs-lookup"><span data-stu-id="4d118-125">Opens the cursor.</span></span>  
  
-   <span data-ttu-id="4d118-126">Compila il set di risultati e invia le righe al client.</span><span class="sxs-lookup"><span data-stu-id="4d118-126">Builds the result set and sends the rows to the client.</span></span>  
  
-   <span data-ttu-id="4d118-127">Poiché le dimensioni del set di righe sono impostate sul numero di righe del set di risultati più uno, il server rileva la fine del cursore e lo chiude.</span><span class="sxs-lookup"><span data-stu-id="4d118-127">Because the rowset size was set to 1 more than the number of rows in the result set, the server detects the end of the cursor and closes the cursor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d118-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d118-128">See Also</span></span>  
 [<span data-ttu-id="4d118-129">Dettagli sulla programmazione dei cursori &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="4d118-129">Cursor Programming Details &#40;ODBC&#41;</span></span>](cursor-programming-details-odbc.md)  
  
  
