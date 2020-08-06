---
title: Utilizzo del recupero automatico con i cursori ODBC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC cursors, autofetch
- autofetch option
- cursors [ODBC], autofetch
ms.assetid: 57bd55f4-8945-4d8d-9f58-d30c81d2a514
author: rothja
ms.author: jroth
ms.openlocfilehash: e3d9374cf9ceab4a7e73cc0059783486f2bf9c41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635552"
---
# <a name="using-autofetch-with-odbc-cursors"></a><span data-ttu-id="e0277-102">Utilizzo del recupero automatico con i cursori ODBC</span><span class="sxs-lookup"><span data-stu-id="e0277-102">Using Autofetch with ODBC Cursors</span></span>
  <span data-ttu-id="e0277-103">Quando si è connessi a un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC di Native Client supporta un'opzione di recupero automatico quando si utilizza qualsiasi tipo di cursore del server.</span><span class="sxs-lookup"><span data-stu-id="e0277-103">When connected to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports an autofetch option when using any server cursor type.</span></span> <span data-ttu-id="e0277-104">Con il recupero automatico, la funzione **SQLExecute** o **SQLExecDirect** che apre il cursore dispone anche di una funzione implicita [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md)(SQL_FIRST).</span><span class="sxs-lookup"><span data-stu-id="e0277-104">With autofetch, the **SQLExecute** or **SQLExecDirect** function that opens the cursor also has an implicit [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md)(SQL_FIRST) function.</span></span> <span data-ttu-id="e0277-105">Le righe incluse nel primo set di righe vengono restituite alle variabili di applicazione associate come parte dell'esecuzione dell'istruzione, evitando in questo modo un altro round trip del server nella rete.</span><span class="sxs-lookup"><span data-stu-id="e0277-105">The rows comprising the first rowset are returned to the bound application variables as part of the statement execution, saving another roundtrip across the network to the server.</span></span> <span data-ttu-id="e0277-106">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) non è supportato quando è abilitata l'opzione di recupero automatico; è necessario associare le colonne del set di risultati alle variabili di programma.</span><span class="sxs-lookup"><span data-stu-id="e0277-106">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) is not supported when the autofetch option is enabled; the result set columns must be bound to program variables.</span></span>  
  
 <span data-ttu-id="e0277-107">Le applicazioni richiedono il recupero automatico impostando l'attributo di istruzione SQL_SOPT_SS_CURSOR_OPTIONS specifico del driver su SQL_CO_AF.</span><span class="sxs-lookup"><span data-stu-id="e0277-107">Applications request autofetch by setting the driver-specific SQL_SOPT_SS_CURSOR_OPTIONS statement attribute to SQL_CO_AF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0277-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0277-108">See Also</span></span>  
 [<span data-ttu-id="e0277-109">Dettagli sulla programmazione dei cursori &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="e0277-109">Cursor Programming Details &#40;ODBC&#41;</span></span>](cursor-programming-details-odbc.md)  
  
  
