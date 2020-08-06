---
title: SQLFetchScroll | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLFetchScroll function
ms.assetid: 524a3985-a08d-4445-99e0-bb551a666615
author: rothja
ms.author: jroth
ms.openlocfilehash: eecf9714a97577ff490b642cee5b9c380333e40b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626783"
---
# <a name="sqlfetchscroll"></a><span data-ttu-id="bf1fc-102">SQLFetchScroll</span><span class="sxs-lookup"><span data-stu-id="bf1fc-102">SQLFetchScroll</span></span>
  <span data-ttu-id="bf1fc-103">**SQLFetchScroll** restituisce un set di righe di dati all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bf1fc-103">**SQLFetchScroll** returns one row set of data to the application.</span></span> <span data-ttu-id="bf1fc-104">Le dimensioni del set di righe vengono impostate utilizzando [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="bf1fc-104">The size of the row set is set using [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span> <span data-ttu-id="bf1fc-105">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client supporta tutte le istruzioni di recupero definite, ad esempio SQL_FETCH_RELATIVE, con le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf1fc-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports all defined fetch instructions (for example, SQL_FETCH_RELATIVE) with the following limitations:</span></span>  
  
-   <span data-ttu-id="bf1fc-106">Se per l'istruzione è definito un cursore forward-only, è necessario specificare SQL_FETCH_NEXT e qualsiasi tentativo di recupero effettuato con altre modalità comporterà la restituzione di un errore.</span><span class="sxs-lookup"><span data-stu-id="bf1fc-106">If a forward-only cursor is defined for the statement, SQL_FETCH_NEXT is required and attempts to fetch in any other fashion will result in an error return.</span></span>  
  
-   <span data-ttu-id="bf1fc-107">SQL_FETCH_BOOKMARK è supportato solo per i cursori statici e gestiti da keyset.</span><span class="sxs-lookup"><span data-stu-id="bf1fc-107">SQL_FETCH_BOOKMARK is supported for static and keyset-driven cursors only.</span></span>  
  
## <a name="sqlfetchscroll-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="bf1fc-108">Supporto di SQLFetchScroll per le caratteristiche avanzate di data e ora</span><span class="sxs-lookup"><span data-stu-id="bf1fc-108">SQLFetchScroll Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="bf1fc-109">I valori della colonna dei risultati dei tipi data/ora vengono convertiti come descritto in [conversioni da SQL a C](../native-client-odbc-date-time/datetime-data-type-conversions-from-sql-to-c.md).</span><span class="sxs-lookup"><span data-stu-id="bf1fc-109">Result column values of date/time types are converted as described in [Conversions from SQL to C](../native-client-odbc-date-time/datetime-data-type-conversions-from-sql-to-c.md).</span></span>  
  
 <span data-ttu-id="bf1fc-110">Per ulteriori informazioni, vedere [miglioramenti di data e ora &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="bf1fc-110">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlfetchscroll-support-for-large-clr-udts"></a><span data-ttu-id="bf1fc-111">Supporto SQLFetchScroll per i tipi CLR definiti dall'utente di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="bf1fc-111">SQLFetchScroll Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="bf1fc-112">**SQLFetchScroll** supporta i tipi CLR definiti dall'utente di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="bf1fc-112">**SQLFetchScroll** supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="bf1fc-113">Per ulteriori informazioni, vedere [tipi CLR definiti dall'utente di grandi dimensioni &#40;&#41;ODBC ](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="bf1fc-113">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf1fc-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf1fc-114">See Also</span></span>  
 <span data-ttu-id="bf1fc-115">[SQLFetchScroll (funzione)](https://go.microsoft.com/fwlink/?LinkId=59343) </span><span class="sxs-lookup"><span data-stu-id="bf1fc-115">[SQLFetchScroll Function](https://go.microsoft.com/fwlink/?LinkId=59343) </span></span>  
 [<span data-ttu-id="bf1fc-116">Dettagli di implementazione dell'API ODBC</span><span class="sxs-lookup"><span data-stu-id="bf1fc-116">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
