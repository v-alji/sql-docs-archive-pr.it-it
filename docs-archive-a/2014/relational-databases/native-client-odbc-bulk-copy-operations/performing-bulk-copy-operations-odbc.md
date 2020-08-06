---
title: Esecuzione di operazioni di copia bulk (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [ODBC]
- ODBC, bulk copy operations
- minimally logged operations [SQL Server Native Client]
- bulk copy [ODBC], about bulk copy
ms.assetid: 5c793405-487c-4f52-88b8-0091d529afb3
author: rothja
ms.author: jroth
ms.openlocfilehash: f2647ebca703eab46d7be0e1cfc2490a65384ee6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724607"
---
# <a name="performing-bulk-copy-operations-odbc"></a><span data-ttu-id="4242a-102">Esecuzione di operazioni di copia bulk (ODBC)</span><span class="sxs-lookup"><span data-stu-id="4242a-102">Performing Bulk Copy Operations (ODBC)</span></span>
  <span data-ttu-id="4242a-103">Lo standard ODBC non supporta direttamente le operazioni di copia bulk [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4242a-103">The ODBC standard does not directly support [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bulk copy operations.</span></span> <span data-ttu-id="4242a-104">In caso di connessione a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] versione 7.0 o successiva, il driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client supporta le funzioni DB-Library che eseguono operazioni di copia bulk [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4242a-104">When connected to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 or later, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports the DB-Library functions that perform [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bulk copy operations.</span></span> <span data-ttu-id="4242a-105">Questa estensione specifica del driver fornisce un percorso di aggiornamento semplice per le applicazioni DB-Library esistenti che utilizzano le funzioni di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="4242a-105">This driver-specific extension provides an easy upgrade path for existing DB-Library applications that use bulk copy functions.</span></span> <span data-ttu-id="4242a-106">Il supporto specifico per la copia bulk è disponibile nei file seguenti:</span><span class="sxs-lookup"><span data-stu-id="4242a-106">The specialized bulk copy support is in the following files:</span></span>  
  
-   <span data-ttu-id="4242a-107">sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="4242a-107">sqlncli.h</span></span>  
  
     <span data-ttu-id="4242a-108">Include prototipi della funzione e definizioni costanti per le funzioni di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="4242a-108">Includes function prototypes and constant definitions for bulk copy functions.</span></span> <span data-ttu-id="4242a-109">sqlncli.h deve essere incluso nell'applicazione ODBC che esegue le operazioni di copia bulk e deve trovarsi nel percorso di inclusione dell'applicazione quando viene compilato.</span><span class="sxs-lookup"><span data-stu-id="4242a-109">sqlncli.h must be included in the ODBC application performing bulk copy operations and must be in the application's include path when it is compiled.</span></span>  
  
-   <span data-ttu-id="4242a-110">sqlncli11.lib</span><span class="sxs-lookup"><span data-stu-id="4242a-110">sqlncli11.lib</span></span>  
  
     <span data-ttu-id="4242a-111">Deve trovarsi nel percorso della libreria del linker e deve essere specificato come un file da collegare.</span><span class="sxs-lookup"><span data-stu-id="4242a-111">Must be in the library path of the linker and specified as a file to be linked.</span></span> <span data-ttu-id="4242a-112">sqlncli11.lib è distribuito con il driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="4242a-112">sqlncli11.lib is distributed with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
-   <span data-ttu-id="4242a-113">sqlncli11.dll</span><span class="sxs-lookup"><span data-stu-id="4242a-113">sqlncli11.dll</span></span>  
  
     <span data-ttu-id="4242a-114">Deve essere presente in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4242a-114">Must be present at execution time.</span></span> <span data-ttu-id="4242a-115">sqlncli11.dll è distribuito con il driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="4242a-115">sqlncli11.dll is distributed with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4242a-116">La funzione ODBC **SQLBulkOperations** non ha alcuna relazione con le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] funzioni di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="4242a-116">The ODBC **SQLBulkOperations** function has no relationship to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bulk copy functions.</span></span> <span data-ttu-id="4242a-117">Per eseguire le operazioni di copia bulk è necessario che le applicazioni utilizzino le funzioni di copia bulk specifiche di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4242a-117">Applications must use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific bulk-copy functions to perform bulk copy operations.</span></span>  
  
## <a name="minimally-logging-bulk-copies"></a><span data-ttu-id="4242a-118">Registrazione minima delle copie bulk</span><span class="sxs-lookup"><span data-stu-id="4242a-118">Minimally Logging Bulk Copies</span></span>  
 <span data-ttu-id="4242a-119">Con un modello di recupero con registrazione completa, tutte le operazioni di inserimento di righe eseguite durante il caricamento bulk vengono registrate in modo completo nel log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="4242a-119">With the Full Recovery model, all row-insert operations performed by bulk load are fully logged in the transaction log.</span></span> <span data-ttu-id="4242a-120">In caso di caricamenti di grandi quantità di dati, questo può causare un rapido esaurimento dello spazio disponibile nel log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="4242a-120">For large data loads, this can cause the transaction log to fill rapidly.</span></span> <span data-ttu-id="4242a-121">In determinate condizioni la registrazione minima è consentita.</span><span class="sxs-lookup"><span data-stu-id="4242a-121">Under certain conditions, minimally logging is possible.</span></span> <span data-ttu-id="4242a-122">Tale registrazione riduce la possibilità che un'operazione di caricamento bulk riempia lo spazio di log e risulta anche più efficiente della registrazione completa.</span><span class="sxs-lookup"><span data-stu-id="4242a-122">Minimal logging reduces the possibility of a bulk load operation filling the log space and is also more efficient than full logging.</span></span>  
  
 <span data-ttu-id="4242a-123">Per informazioni sull'utilizzo della registrazione minima, vedere [prerequisiti per la registrazione minima nell'importazione bulk](../import-export/prerequisites-for-minimal-logging-in-bulk-import.md).</span><span class="sxs-lookup"><span data-stu-id="4242a-123">For information on using minimal logging, see [Prerequisites for Minimal Logging in Bulk Import](../import-export/prerequisites-for-minimal-logging-in-bulk-import.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4242a-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4242a-124">Remarks</span></span>  
 <span data-ttu-id="4242a-125">Quando bcp.exe viene utilizzato in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] o versione successiva, potrebbero essere visualizzati errori nelle situazioni in cui non si presenta alcun errore nelle versioni precedenti a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4242a-125">When using bcp.exe in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later, you might see errors in situations where there were no errors prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="4242a-126">Questo avviene perché nelle versioni successive bcp.exe non esegue più la conversione implicita dei tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="4242a-126">This is because in the later versions, bcp.exe no longer performs implicit data type conversion.</span></span> <span data-ttu-id="4242a-127">Nelle versioni precedenti a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] bcp.exe converte i dati numerici in un tipo di dati money, se la tabella di destinazione contiene tale tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="4242a-127">Prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], bcp.exe converted numeric data to a money data type, if the target table had a money data type.</span></span> <span data-ttu-id="4242a-128">In tale situazione, tuttavia, bcp.exe tronca semplicemente i campi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="4242a-128">However, in that situation, bcp.exe simply truncated extra fields.</span></span> <span data-ttu-id="4242a-129">A partire da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , se i tipi di dati non corrispondono tra il file e la tabella di destinazione, bcp.exe genererà un errore se sono presenti dati che dovrebbero essere troncati per adattarsi alla tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4242a-129">Beginning in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], if data types do not match between the file and the target table, bcp.exe will raise an error if there is any data that would have to be truncated to fit into the target table.</span></span> <span data-ttu-id="4242a-130">Per risolvere questo errore, correggere i dati in modo che corrispondano al tipo di dati di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4242a-130">To resolve this error, fix the data to match the target data type.</span></span> <span data-ttu-id="4242a-131">Se si desidera, è possibile utilizzare il file bcp.exe di una versione precedente a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4242a-131">Optionally, use bcp.exe from a release prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4242a-132">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="4242a-132">In This Section</span></span>  
  
-   [<span data-ttu-id="4242a-133">Utilizzo di file di dati e file di formato</span><span class="sxs-lookup"><span data-stu-id="4242a-133">Using Data Files and Format Files</span></span>](using-data-files-and-format-files.md)  
  
-   [<span data-ttu-id="4242a-134">Copia bulk da variabili di programma</span><span class="sxs-lookup"><span data-stu-id="4242a-134">Bulk Copying from Program Variables</span></span>](bulk-copying-from-program-variables.md)  
  
-   [<span data-ttu-id="4242a-135">Gestione delle dimensioni dei batch di copia bulk</span><span class="sxs-lookup"><span data-stu-id="4242a-135">Managing Bulk Copy Batch Sizes</span></span>](managing-bulk-copy-batch-sizes.md)  
  
-   [<span data-ttu-id="4242a-136">Copia bulk di dati di tipo text e image</span><span class="sxs-lookup"><span data-stu-id="4242a-136">Bulk Copying Text and Image Data</span></span>](bulk-copying-text-and-image-data.md)  
  
-   [<span data-ttu-id="4242a-137">Conversione della copia bulk da DB-Library a ODBC</span><span class="sxs-lookup"><span data-stu-id="4242a-137">Converting from DB-Library to ODBC Bulk Copy</span></span>](converting-from-db-library-to-odbc-bulk-copy.md)  
  
## <a name="see-also"></a><span data-ttu-id="4242a-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4242a-138">See Also</span></span>  
 <span data-ttu-id="4242a-139">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="4242a-139">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 [<span data-ttu-id="4242a-140">Informazioni sull'importazione ed esportazione bulk di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4242a-140">Bulk Import and Export of Data &#40;SQL Server&#41;</span></span>](../import-export/bulk-import-and-export-of-data-sql-server.md)  
  
  
