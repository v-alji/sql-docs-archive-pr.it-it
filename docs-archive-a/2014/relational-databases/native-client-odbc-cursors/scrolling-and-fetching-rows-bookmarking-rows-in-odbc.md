---
title: Segnalibro di righe in ODBC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], fetching rows
- ODBC cursors, fetching rows
- cursors [ODBC], scrolling rows
- ODBC cursors, scrolling rows
- bookmarks [ODBC]
ms.assetid: 9cfcd243-c9d4-4c2a-abc4-399dbabe5f6b
author: rothja
ms.author: jroth
ms.openlocfilehash: def05f478c16dcbcdc91771925a11b0b91da2e9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723844"
---
# <a name="bookmarking-rows-in-odbc"></a><span data-ttu-id="d0685-102">Applicazione di segnalibri alle righe in ODBC</span><span class="sxs-lookup"><span data-stu-id="d0685-102">Bookmarking Rows in ODBC</span></span>
  <span data-ttu-id="d0685-103">Un segnalibro è un valore utilizzato per identificare una riga di dati.</span><span class="sxs-lookup"><span data-stu-id="d0685-103">A bookmark is a value used to identify a row of data.</span></span> <span data-ttu-id="d0685-104">Il significato del valore del segnalibro è noto solo al driver o all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="d0685-104">The meaning of the bookmark value is known only to the driver or data source.</span></span> <span data-ttu-id="d0685-105">Un segnalibro, ad esempio, può essere tanto semplice quanto un numero di riga o tanto complesso quanto un indirizzo del disco.</span><span class="sxs-lookup"><span data-stu-id="d0685-105">For example, it might be as simple as a row number or as complex as a disk address.</span></span> <span data-ttu-id="d0685-106">In ODBC l'applicazione richiede un segnalibro per una determinata riga, lo archivia e lo passa nuovamente al cursore per tornare alla riga.</span><span class="sxs-lookup"><span data-stu-id="d0685-106">In ODBC, the application requests a bookmark for a particular row, stores it, and passes it back to the cursor to return to the row.</span></span>  
  
 <span data-ttu-id="d0685-107">Quando si recuperano righe con [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md), un'applicazione può usare un segnalibro come base per la selezione della riga iniziale.</span><span class="sxs-lookup"><span data-stu-id="d0685-107">When fetching rows with [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md), an application can use a bookmark as a basis for selecting the starting row.</span></span> <span data-ttu-id="d0685-108">Si tratta di una forma di indirizzamento assoluto, in quanto non dipende dalla posizione del cursore corrente.</span><span class="sxs-lookup"><span data-stu-id="d0685-108">This is a form of absolute addressing because it does not depend on the current cursor position.</span></span> <span data-ttu-id="d0685-109">Per scorrere fino a una riga con segnalibro, l'applicazione chiama **SQLFetchScroll** con un *FetchOrientation* di SQL_FETCH_BOOKMARK.</span><span class="sxs-lookup"><span data-stu-id="d0685-109">To scroll to a bookmarked row, the application calls **SQLFetchScroll** with a *FetchOrientation* of SQL_FETCH_BOOKMARK.</span></span> <span data-ttu-id="d0685-110">Questa operazione utilizza il segnalibro a cui punta l'attributo dell'opzione SQL_ATTR_FETCH_BOOKMARK_PTR.</span><span class="sxs-lookup"><span data-stu-id="d0685-110">This operation uses the bookmark pointed to by the SQL_ATTR_FETCH_BOOKMARK_PTR option attribute.</span></span> <span data-ttu-id="d0685-111">L'operazione restituisce il set di righe che inizia con la riga identificata dal segnalibro.</span><span class="sxs-lookup"><span data-stu-id="d0685-111">It returns the rowset starting with the row identified by that bookmark.</span></span> <span data-ttu-id="d0685-112">Un'applicazione può specificare un offset per questa operazione nell'argomento *FetchOffset* della chiamata a **SQLFetchScroll**.</span><span class="sxs-lookup"><span data-stu-id="d0685-112">An application can specify an offset for this operation in the *FetchOffset* argument of the call to **SQLFetchScroll**.</span></span> <span data-ttu-id="d0685-113">Quando viene specificato un offset, la prima riga del set di righe restituita è determinata dall'aggiunta del numero nell'argomento FetchOffset al numero della riga identificata dal segnalibro.</span><span class="sxs-lookup"><span data-stu-id="d0685-113">When an offset is specified, the first row of the returned rowset is determined by adding the number in the FetchOffset argument to the number of the row identified by the bookmark.</span></span> <span data-ttu-id="d0685-114">Il driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client supporta solo segnalibri su cursori statici e keyset.</span><span class="sxs-lookup"><span data-stu-id="d0685-114">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver only supports bookmarks on static and keyset cursors.</span></span> <span data-ttu-id="d0685-115">Se viene richiesto un cursore dinamico quando si impostano segnalibri, viene invece aperto un cursore keyset.</span><span class="sxs-lookup"><span data-stu-id="d0685-115">If a dynamic cursor is requested when bookmarks are set on, a keyset cursor is opened instead.</span></span>  
  
 <span data-ttu-id="d0685-116">I segnalibri possono essere usati anche con la funzione **SQLBulkOperations** per eseguire operazioni su un set di righe a partire dal segnalibro.</span><span class="sxs-lookup"><span data-stu-id="d0685-116">Bookmarks can also be used with the **SQLBulkOperations** function to perform operations on a set of rows starting at the bookmark.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0685-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0685-117">See Also</span></span>  
 [<span data-ttu-id="d0685-118">Scorrimento e recupero di righe</span><span class="sxs-lookup"><span data-stu-id="d0685-118">Scrolling and Fetching Rows</span></span>](../native-client-ole-db-rowsets/fetching-rows.md)  
  
  
