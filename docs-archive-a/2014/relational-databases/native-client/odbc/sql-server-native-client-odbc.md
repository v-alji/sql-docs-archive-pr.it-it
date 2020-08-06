---
title: SQL Server Native Client (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLNCLI, ODBC
- SQL Server Native Client ODBC driver, about SQL Server Native Client ODBC driver
- data access [SQL Server Native Client], ODBC
- SQL Server Native Client ODBC driver
- ODBC
- SQL Server Native Client, ODBC
- ODBC, about SQL Server Native Client ODBC driver
ms.assetid: 811d5ba3-a2b8-48c0-adbc-8c91f041f458
author: rothja
ms.author: jroth
ms.openlocfilehash: 16c73966e318ed1e7d326fa77f56195ebbd830df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718077"
---
# <a name="sql-server-native-client-odbc"></a><span data-ttu-id="21118-102">SQL Server Native Client (ODBC)</span><span class="sxs-lookup"><span data-stu-id="21118-102">SQL Server Native Client (ODBC)</span></span>
  <span data-ttu-id="21118-103">ODBC è una definizione standard di un'API utilizzata per accedere ai dati nei database ISAM o relazionali o indicizzati.</span><span class="sxs-lookup"><span data-stu-id="21118-103">ODBC is a standard definition of an application programming interface (API) used to access data in relational or indexed sequential access method (ISAM) databases.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="21118-104">supporta ODBC, tramite il driver ODBC di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, come una delle API native per la scrittura delle applicazioni C e C++ mediante le quali è possibile comunicare con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="21118-104">supports ODBC, via the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver, as one of the native APIs for writing C and C++ applications that communicate with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="21118-105">I programmi [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] scritti utilizzando il driver ODBC di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client comunicano con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] attraverso le chiamate di funzioni C.</span><span class="sxs-lookup"><span data-stu-id="21118-105">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] programs that are written using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver communicate with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] through C function calls.</span></span> <span data-ttu-id="21118-106">Le versioni specifiche di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] delle funzioni ODBC vengono implementate nel driver ODBC di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="21118-106">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-specific versions of the ODBC functions are implemented in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span> <span data-ttu-id="21118-107">Il driver passa le istruzioni SQL a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e restituisce i risultati all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="21118-107">The driver passes SQL statements to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and returns the results of the statements to the application.</span></span>  
  
 <span data-ttu-id="21118-108">Il driver ODBC di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client è conforme alla specifica Microsoft Win32 ODBC 3.51.</span><span class="sxs-lookup"><span data-stu-id="21118-108">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver complies with the Microsoft Win32 ODBC 3.51 specification.</span></span> <span data-ttu-id="21118-109">Il driver supporta le applicazioni scritte utilizzando versioni precedenti di ODBC nelle modalità definite nella specifica ODBC 3.51.</span><span class="sxs-lookup"><span data-stu-id="21118-109">The driver supports applications written using earlier versions of ODBC in the manner defined in the ODBC 3.51 specification.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="21118-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="21118-110">In This Section</span></span>  
  
-   [<span data-ttu-id="21118-111">Nomi di origine dati e sistemi operativi a 64 bit</span><span class="sxs-lookup"><span data-stu-id="21118-111">Data Source Names and 64-Bit Operating Systems</span></span>](data-source-names-and-64-bit-operating-systems.md)  
  
-   [<span data-ttu-id="21118-112">Creazione di un'applicazione driver ODBC di SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="21118-112">Creating a SQL Server Native Client ODBC Driver Application</span></span>](creating-a-driver-application.md)  
  
-   [<span data-ttu-id="21118-113">Comunicazione con SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="21118-113">Communicating with SQL Server &#40;ODBC&#41;</span></span>](../../native-client-odbc-communication/communicating-with-sql-server-odbc.md)  
  
-   [<span data-ttu-id="21118-114">Esecuzione di query &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="21118-114">Executing Queries &#40;ODBC&#41;</span></span>](../../native-client-odbc-queries/executing-queries-odbc.md)  
  
-   [<span data-ttu-id="21118-115">Elaborazione dei risultati &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="21118-115">Processing Results &#40;ODBC&#41;</span></span>](../../native-client-odbc-results/processing-results-odbc.md)  
  
-   [<span data-ttu-id="21118-116">Utilizzo di cursori &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="21118-116">Using Cursors &#40;ODBC&#41;</span></span>](../../native-client-odbc-cursors/using-cursors-odbc.md)  
  
-   [<span data-ttu-id="21118-117">Esecuzione di transazioni &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="21118-117">Performing Transactions &#40;ODBC&#41;</span></span>](../../../database-engine/dev-guide/performing-transactions-odbc.md)  
  
-   [<span data-ttu-id="21118-118">Gestione di errori e messaggi</span><span class="sxs-lookup"><span data-stu-id="21118-118">Handling Errors and Messages</span></span>](../../native-client-odbc-error-messages/handling-errors-and-messages.md)  
  
-   [<span data-ttu-id="21118-119">Esecuzione delle stored procedure</span><span class="sxs-lookup"><span data-stu-id="21118-119">Running Stored Procedures</span></span>](../../native-client-odbc-stored-procedures/running-stored-procedures.md)  
  
-   [<span data-ttu-id="21118-120">Uso delle funzioni catalogo</span><span class="sxs-lookup"><span data-stu-id="21118-120">Using Catalog Functions</span></span>](using-catalog-functions.md)  
  
-   [<span data-ttu-id="21118-121">Esecuzione di operazioni di copia bulk &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="21118-121">Performing Bulk Copy Operations &#40;ODBC&#41;</span></span>](../../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md)  
  
-   [<span data-ttu-id="21118-122">Gestione di colonne di tipo text e image</span><span class="sxs-lookup"><span data-stu-id="21118-122">Managing Text and Image Columns</span></span>](../../native-client-odbc-text-image-columns/managing-text-and-image-columns.md)  
  
-   [<span data-ttu-id="21118-123">Profiling delle prestazioni del driver ODBC</span><span class="sxs-lookup"><span data-stu-id="21118-123">Profiling ODBC Driver Performance</span></span>](profiling-odbc-driver-performance.md)  
  
-   [<span data-ttu-id="21118-124">Parametri con valori di tabella &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="21118-124">Table-Valued Parameters &#40;ODBC&#41;</span></span>](../../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md)  
  
-   [<span data-ttu-id="21118-125">Miglioramenti di data e ora &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="21118-125">Date and Time Improvements &#40;ODBC&#41;</span></span>](../../native-client-odbc-date-time/date-and-time-improvements-odbc.md)  
  
-   [<span data-ttu-id="21118-126">Tipi CLR definiti dall'utente di grandi dimensioni &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="21118-126">Large CLR User-Defined Types &#40;ODBC&#41;</span></span>](large-clr-user-defined-types-odbc.md)  
  
-   [<span data-ttu-id="21118-127">Supporto FILESTREAM &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="21118-127">FILESTREAM Support &#40;ODBC&#41;</span></span>](filestream-support-odbc.md)  
  
-   [<span data-ttu-id="21118-128">Nomi SPN &#40;Service Principal Name&#41; nelle connessioni client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="21118-128">Service Principal Names &#40;SPNs&#41; in Client Connections &#40;ODBC&#41;</span></span>](service-principal-names-spns-in-client-connections-odbc.md)  
  
-   [<span data-ttu-id="21118-129">Colonne di tipo sparse supportano &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="21118-129">Sparse Columns Support &#40;ODBC&#41;</span></span>](sparse-columns-support-odbc.md)  
  
-   [<span data-ttu-id="21118-130">SQL Server Native Client &#40;riferimento&#41; ODBC</span><span class="sxs-lookup"><span data-stu-id="21118-130">SQL Server Native Client &#40;ODBC&#41; Reference</span></span>](../../../database-engine/dev-guide/sql-server-native-client-odbc-reference.md)  
  
-   [<span data-ttu-id="21118-131">Procedure per l'utilizzo di ODBC</span><span class="sxs-lookup"><span data-stu-id="21118-131">ODBC How-to Topics</span></span>](../../native-client-odbc-how-to/odbc-how-to-topics.md)  
  
## <a name="see-also"></a><span data-ttu-id="21118-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21118-132">See Also</span></span>  
 <span data-ttu-id="21118-133">[Programmazione SQL Server Native Client](../sql-server-native-client-programming.md) </span><span class="sxs-lookup"><span data-stu-id="21118-133">[SQL Server Native Client Programming](../sql-server-native-client-programming.md) </span></span>  
 [<span data-ttu-id="21118-134">Installazione di SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="21118-134">Installing SQL Server Native Client</span></span>](../applications/installing-sql-server-native-client.md)  
  
  
