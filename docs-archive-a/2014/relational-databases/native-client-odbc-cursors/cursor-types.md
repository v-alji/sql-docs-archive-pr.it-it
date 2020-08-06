---
title: Tipi di cursore | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, cursors
- ODBC applications, cursors
- cursors [ODBC], types
- ODBC cursors, types
ms.assetid: 3a916cc7-f352-42cb-8b83-f78e06cef991
author: rothja
ms.author: jroth
ms.openlocfilehash: 6937dbb9ce42cd5631201e0c97be42b211742ada
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626782"
---
# <a name="cursor-types"></a><span data-ttu-id="265f6-102">Tipi di cursore</span><span class="sxs-lookup"><span data-stu-id="265f6-102">Cursor Types</span></span>
  <span data-ttu-id="265f6-103">ODBC definisce quattro tipi di cursore supportati da Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e dal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client.</span><span class="sxs-lookup"><span data-stu-id="265f6-103">ODBC defines four cursor types supported by Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span> <span data-ttu-id="265f6-104">Questi cursori variano in base alla capacità di rilevare le modifiche apportate al set di risultati e alle risorse utilizzate, ad esempio la memoria e lo spazio in **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="265f6-104">These cursors vary in their ability to detect changes to the result set and in the resources they consume, such as memory and space in **tempdb**.</span></span> <span data-ttu-id="265f6-105">Tramite un cursore è possibile rilevare le modifiche apportate alle righe solo quando viene eseguito un secondo tentativo di recupero di tali righe. L'origine dei dati non è in grado di notificare al cursore le eventuali modifiche apportate alle righe in fase di recupero.</span><span class="sxs-lookup"><span data-stu-id="265f6-105">A cursor can detect changes to rows only when it tries to refetch those rows; there is no way for the data source to notify the cursor of changes to the currently fetched rows.</span></span> <span data-ttu-id="265f6-106">La capacità di rilevamento delle modifiche non effettuate di un cursore inoltre varia in base al livello di isolamento delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="265f6-106">A cursor's ability to detect changes that were not made through the cursor is also influenced by the transaction isolation level.</span></span>  
  
 <span data-ttu-id="265f6-107">Di seguito sono indicati i quattro cursori ODBC supportati da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="265f6-107">These are the four ODBC cursor types supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="265f6-108">I cursori forward only non supportano lo scorrimento, ma solo le operazioni di recupero seriale delle righe dall'inizio alla fine del cursore.</span><span class="sxs-lookup"><span data-stu-id="265f6-108">Forward-only cursors do not support scrolling; they only support fetching rows serially from the start to the end of the cursor.</span></span>  
  
-   <span data-ttu-id="265f6-109">I cursori statici vengono compilati in **tempdb** all'apertura del cursore.</span><span class="sxs-lookup"><span data-stu-id="265f6-109">Static cursors are built in **tempdb** when the cursor is opened.</span></span> <span data-ttu-id="265f6-110">Un cursore statico visualizza sempre il set di risultati così come è visualizzato all'apertura del cursore.</span><span class="sxs-lookup"><span data-stu-id="265f6-110">They always display the result set as it was when the cursor was opened.</span></span> <span data-ttu-id="265f6-111">Non riflettono mai modifiche ai dati.</span><span class="sxs-lookup"><span data-stu-id="265f6-111">They never reflect changes to the data.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="265f6-112">sono sempre di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="265f6-112">static cursors are always read-only.</span></span> <span data-ttu-id="265f6-113">Poiché un cursore del server statico viene compilato come una tabella di lavoro in **tempdb**, le dimensioni del set di risultati del cursore non possono superare le dimensioni massime della riga consentite da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="265f6-113">Because a static server cursor is built as a work table in **tempdb**, the size of the cursor result set cannot exceed the maximum row size allowed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="265f6-114">L'appartenenza e l'ordine delle righe di un cursore gestito da keyset vengono fissati al momento dell'apertura del cursore.</span><span class="sxs-lookup"><span data-stu-id="265f6-114">Keyset-driven cursors have the membership and order of rows in the result set fixed when the cursor is opened.</span></span> <span data-ttu-id="265f6-115">Eventuali modifiche alle colonne non chiave sono visibili tramite il cursore.</span><span class="sxs-lookup"><span data-stu-id="265f6-115">Changes to nonkey columns are visible through the cursor.</span></span>  
  
-   <span data-ttu-id="265f6-116">I cursori dinamici sono l'opposto dei cursori statici.</span><span class="sxs-lookup"><span data-stu-id="265f6-116">Dynamic cursors are the opposite of static cursors.</span></span> <span data-ttu-id="265f6-117">Essi riflettono tutte le modifiche apportate alle righe del set di risultati corrispondente.</span><span class="sxs-lookup"><span data-stu-id="265f6-117">Dynamic cursors reflect all changes made to the rows in their result set.</span></span> <span data-ttu-id="265f6-118">I valori di dati, l'ordine e l'appartenenza delle righe del set di risultati possono variare a ogni operazione di recupero.</span><span class="sxs-lookup"><span data-stu-id="265f6-118">The data values, order, and membership of the rows in the result set can change on each fetch.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="265f6-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="265f6-119">See Also</span></span>  
 [<span data-ttu-id="265f6-120">Utilizzo di cursori &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="265f6-120">Using Cursors &#40;ODBC&#41;</span></span>](using-cursors-odbc.md)  
  
  
