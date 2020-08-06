---
title: Parametri con valori di tabella (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC)
- ODBC, table-valued parameters
ms.assetid: ef06cd13-18e2-4c65-8ede-c3955d820e54
author: rothja
ms.author: jroth
ms.openlocfilehash: fedfd63f7cbafd68d39aeb62dd29c046df8ab100
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624100"
---
# <a name="table-valued-parameters-odbc"></a><span data-ttu-id="74109-102">Parametri con valori di tabella (ODBC)</span><span class="sxs-lookup"><span data-stu-id="74109-102">Table-Valued Parameters (ODBC)</span></span>
  <span data-ttu-id="74109-103">Il supporto ODBC dei parametri con valori di tabella consente a un'applicazione client di inviare più efficientemente i dati con parametri al server, inviando più righe al server con una sola chiamata.</span><span class="sxs-lookup"><span data-stu-id="74109-103">ODBC support for table-valued parameters lets a client application send parameterized data to the server more efficiently, by sending multiple rows to the server with one call.</span></span>  
  
 <span data-ttu-id="74109-104">Per informazioni sui parametri con valori di tabella nel server, vedere [usare i parametri con valori di tabella &#40;motore di database&#41;](../tables/use-table-valued-parameters-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="74109-104">For information about table-valued parameters on the server, see [Use Table-Valued Parameters &#40;Database Engine&#41;](../tables/use-table-valued-parameters-database-engine.md).</span></span>  
  
 <span data-ttu-id="74109-105">In ODBC è possibile inviare parametri con valori di tabella al server in due modi:</span><span class="sxs-lookup"><span data-stu-id="74109-105">In ODBC, there are two ways that you can send table-valued parameters to the server:</span></span>  
  
-   <span data-ttu-id="74109-106">Tutti i dati dei parametri con valori di tabella possono essere in memoria al momento della chiamata a SQLExecDirect o SQLExecute.</span><span class="sxs-lookup"><span data-stu-id="74109-106">All the table-valued parameter data can be in memory at the time SQLExecDirect or SQLExecute is called.</span></span> <span data-ttu-id="74109-107">Se sono presenti più righe nel valore di tabella, i dati vengono archiviati in matrici.</span><span class="sxs-lookup"><span data-stu-id="74109-107">This data is stored in arrays if there are multiple rows in the table-value.</span></span>  
  
-   <span data-ttu-id="74109-108">Un'applicazione può specificare data-at-execution per un parametro con valori di tabella quando viene chiamato SQLExecDirect o SQLExecute.</span><span class="sxs-lookup"><span data-stu-id="74109-108">An application can specify data-at-execution for a table-valued parameter when SQLExecDirect or SQLExecute is called.</span></span> <span data-ttu-id="74109-109">In tal caso, le righe di dati per il valore di tabella possono essere fornite in batch o uno alla volta per ridurre i requisiti di memoria.</span><span class="sxs-lookup"><span data-stu-id="74109-109">In this case, rows of data for the table-value can be provided in batches, or one at a time to reduce memory requirements.</span></span>  
  
 <span data-ttu-id="74109-110">La prima opzione consente alle stored procedure di incapsulare più logica di business.</span><span class="sxs-lookup"><span data-stu-id="74109-110">The first option enables stored procedures to encapsulate more business logic.</span></span> <span data-ttu-id="74109-111">Ad esempio, una singola stored procedure può incapsulare un'intera transazione di immissione ordini se gli articoli dell'ordine vengono passati come parametro con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="74109-111">For example, a single stored procedure could encapsulate a whole order entry transaction when the order items are passed as a table-valued parameter.</span></span> <span data-ttu-id="74109-112">Questa opzione è molto efficiente poiché è necessario un solo round trip del server.</span><span class="sxs-lookup"><span data-stu-id="74109-112">This option is very efficient, because only a single round trip to the server is required.</span></span> <span data-ttu-id="74109-113">In alternativa, è possibile utilizzare altre procedure per gestire separatamente l'intestazione degli ordini e gli articoli richiedendo più codice e un contratto più complesso tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="74109-113">Alternatively, you could use different procedures to handle the order header and order items separately, which would require more code and a more complex contract between the client and server.</span></span>  
  
 <span data-ttu-id="74109-114">Il secondo metodo fornisce un meccanismo efficiente per le operazioni bulk con quantità elevate di dati</span><span class="sxs-lookup"><span data-stu-id="74109-114">The second method provides an efficient mechanism for bulk operations with very large amounts of data.</span></span> <span data-ttu-id="74109-115">consentendo a un'applicazione di trasmettere un flusso di righe di dati al server senza doverle prima memorizzare nel buffer.</span><span class="sxs-lookup"><span data-stu-id="74109-115">This enables an application to stream rows of data to the server without having to buffer them all in memory first.</span></span>  
  
 <span data-ttu-id="74109-116">È possibile creare vincoli e chiavi primarie durante la creazione della variabile di tabella.</span><span class="sxs-lookup"><span data-stu-id="74109-116">You can create constraints and primary keys when you create the table variable.</span></span> <span data-ttu-id="74109-117">I vincoli rappresentano un ottimo metodo per assicurarsi che i dati di una tabella soddisfino requisiti specifici.</span><span class="sxs-lookup"><span data-stu-id="74109-117">Constraints are a good way to ensure that the data in a table meets specific requirements.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="74109-118">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="74109-118">In This Section</span></span>  
 [<span data-ttu-id="74109-119">Utilizzi dei parametri con valori di tabella in ODBC</span><span class="sxs-lookup"><span data-stu-id="74109-119">Uses of ODBC Table-Valued Parameters</span></span>](uses-of-odbc-table-valued-parameters.md)  
 <span data-ttu-id="74109-120">Vengono descritti gli scenari utente principali per i parametri con valori di tabella e ODBC.</span><span class="sxs-lookup"><span data-stu-id="74109-120">Describes the primary user scenarios for table-valued parameters and ODBC.</span></span>  
  
 [<span data-ttu-id="74109-121">Tipo SQL ODBC per parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="74109-121">ODBC SQL Type for Table-Valued Parameters</span></span>](odbc-sql-type-for-table-valued-parameters.md)  
 <span data-ttu-id="74109-122">Viene descritto il tipo SQL_SS_TABLE.</span><span class="sxs-lookup"><span data-stu-id="74109-122">Describes the SQL_SS_TABLE type.</span></span> <span data-ttu-id="74109-123">Si tratta di un nuovo tipo ODBC SQL che supporta i parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="74109-123">This is a new ODBC SQL type that supports table-valued parameters.</span></span>  
  
 [<span data-ttu-id="74109-124">Campi di descrizione dei parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="74109-124">Table-Valued Parameter Descriptor Fields</span></span>](table-valued-parameter-descriptor-fields.md)  
 <span data-ttu-id="74109-125">Vengono descritti i campi di descrizione che supportano i parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="74109-125">Describes descriptor fields that support table-valued parameters.</span></span>  
  
 [<span data-ttu-id="74109-126">Campi di descrizione per le colonne che costituiscono parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="74109-126">Descriptor Fields for Table-Valued Parameter Constituent Columns</span></span>](descriptor-fields-for-table-valued-parameter-constituent-columns.md)  
 <span data-ttu-id="74109-127">Vengono descritti i campi di descrizione che hanno valenza per i parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="74109-127">Describes descriptor fields that have meaning for table-valued parameters.</span></span>  
  
 [<span data-ttu-id="74109-128">Campi dei record di diagnostica dei parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="74109-128">Table-Valued Parameter Diagnostic Record Fields</span></span>](table-valued-parameter-diagnostic-record-fields.md)  
 <span data-ttu-id="74109-129">Vengono descritti i due campi di diagnostica aggiunti ai record di diagnostica per supportare i parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="74109-129">Describes two diagnostic fields that have been added to diagnostic records to support table-valued parameters.</span></span>  
  
 [<span data-ttu-id="74109-130">Attributi dell'istruzione che influiscono sui parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="74109-130">Statement Attributes that Affect Table-Valued Parameters</span></span>](statement-attributes-that-affect-table-valued-parameters.md)  
 <span data-ttu-id="74109-131">Viene descritto un nuovo campo di intestazione di descrizione che consente l'indirizzamento delle colonne dei parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="74109-131">Describes a new descriptor header field that enables table-valued parameters columns to be addressed.</span></span>  
  
 [<span data-ttu-id="74109-132">Associazione e trasferimento dati di valori di colonna e parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="74109-132">Binding and Data Transfer of Table-Valued Parameters and Column Values</span></span>](binding-and-data-transfer-of-table-valued-parameters-and-column-values.md)  
 <span data-ttu-id="74109-133">Vengono descritti l'associazione dei parametri e il passaggio di un parametro con valori di tabella al server.</span><span class="sxs-lookup"><span data-stu-id="74109-133">Describes parameter binding and how to pass a table-valued parameter to the server.</span></span>  
  
 [<span data-ttu-id="74109-134">Metadati del parametro con valori di tabella per le istruzioni preparate</span><span class="sxs-lookup"><span data-stu-id="74109-134">Table-Valued Parameter Metadata for Prepared Statements</span></span>](table-valued-parameter-metadata-for-prepared-statements.md)  
 <span data-ttu-id="74109-135">Viene descritto il modo in cui un'applicazione può ottenere i metadati per una chiamata alla procedura preparata.</span><span class="sxs-lookup"><span data-stu-id="74109-135">Describes how an application can obtain metadata for a prepared procedure call.</span></span>  
  
 [<span data-ttu-id="74109-136">Metadati aggiuntivi dei parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="74109-136">Additional Table-Valued Parameter Metadata</span></span>](additional-table-valued-parameter-metadata.md)  
 <span data-ttu-id="74109-137">Viene descritto come utilizzare SQLProcedureColumns, SQLTables e SQLColumns per recuperare i metadati per un parametro con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="74109-137">Describes how to use SQLProcedureColumns, SQLTables, and SQLColumns to retrieve metadata for a table-valued parameter.</span></span>  
  
 [<span data-ttu-id="74109-138">Conversione di dati dei parametri con valori di tabella e altri errori e avvisi</span><span class="sxs-lookup"><span data-stu-id="74109-138">Table-Valued Parameter Data Conversion and Other Errors and Warnings</span></span>](table-valued-parameter-data-conversion-and-other-errors-and-warnings.md)  
 <span data-ttu-id="74109-139">Viene descritta l'elaborazione degli errori nei valori delle colonne dei parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="74109-139">Describes how to process errors on table-valued parameter column values.</span></span>  
  
 [<span data-ttu-id="74109-140">Compatibilità tra versioni</span><span class="sxs-lookup"><span data-stu-id="74109-140">Cross-Version Compatibility</span></span>](cross-version-compatibility.md)  
 <span data-ttu-id="74109-141">Vengono descritti i conflitti che possono verificarsi quando i parametri con valori di tabella vengono utilizzati da un client o da un server di una versione precedente di [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74109-141">Describes conflicts that can occur when table-valued parameters are used by a client or server of a version earlier than [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
 [<span data-ttu-id="74109-142">Riepilogo delle API dei parametri con valori di tabella ODBC</span><span class="sxs-lookup"><span data-stu-id="74109-142">ODBC Table-Valued Parameter API Summary</span></span>](odbc-table-valued-parameter-api-summary.md)  
 <span data-ttu-id="74109-143">Vengono descritte le funzioni ODBC che supportano i parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="74109-143">Lists the ODBC functions that support table-valued parameters.</span></span>  
  
 [<span data-ttu-id="74109-144">Esempi di programmazione di parametri con valori di tabella ODBC</span><span class="sxs-lookup"><span data-stu-id="74109-144">ODBC Table-Valued Parameter Programming Examples</span></span>](../../database-engine/dev-guide/odbc-table-valued-parameter-programming-examples.md)  
 <span data-ttu-id="74109-145">Viene descritta l'esecuzione delle attività più comuni.</span><span class="sxs-lookup"><span data-stu-id="74109-145">Describes how to perform common tasks.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74109-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74109-146">See Also</span></span>  
 <span data-ttu-id="74109-147">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="74109-147">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 [<span data-ttu-id="74109-148">Parametri con valori di tabella &#40;SQL Server Native Client&#41;</span><span class="sxs-lookup"><span data-stu-id="74109-148">Table-Valued Parameters &#40;SQL Server Native Client&#41;</span></span>](../native-client/features/table-valued-parameters-sql-server-native-client.md)  
  
  
