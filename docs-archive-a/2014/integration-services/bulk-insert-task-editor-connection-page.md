---
title: Editor attività Inserimento bulk (pagina connessione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.bulkinserttask.connection.f1
helpviewer_keywords:
- Bulk Insert Task Editor
ms.assetid: 51252c20-8865-4ede-a3fd-bd73a968f47d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b2cd722fd8520ff011c0d57040a55d624178e15e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723000"
---
# <a name="bulk-insert-task-editor-connection-page"></a><span data-ttu-id="8de7f-102">Editor attività Inserimento bulk (pagina Connessione)</span><span class="sxs-lookup"><span data-stu-id="8de7f-102">Bulk Insert Task Editor (Connection Page)</span></span>
  <span data-ttu-id="8de7f-103">Usare la pagina **Connessione** della finestra di dialogo **Editor attività Inserimento bulk** per specificare l'origine e la destinazione dell'operazione di inserimento bulk e il formato da usare.</span><span class="sxs-lookup"><span data-stu-id="8de7f-103">Use the **Connection** page of the **Bulk Insert Task Editor** dialog box to specify the source and destination of the bulk insert operation and the format to use.</span></span>  
  
 <span data-ttu-id="8de7f-104">Per altre informazioni sulle operazioni di inserimento bulk, vedere [Attività Inserimento bulk](control-flow/bulk-insert-task.md) e [File di formato per l'importazione o l'esportazione di dati &#40;SQL Server&#41;](../relational-databases/import-export/format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="8de7f-104">To learn about working with bulk inserts, see [Bulk Insert Task](control-flow/bulk-insert-task.md) and [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](../relational-databases/import-export/format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="8de7f-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="8de7f-105">Options</span></span>  
 <span data-ttu-id="8de7f-106">**Connection**</span><span class="sxs-lookup"><span data-stu-id="8de7f-106">**Connection**</span></span>  
 <span data-ttu-id="8de7f-107">Selezionare una gestione connessione OLE DB nell'elenco oppure fare clic su \<**New connection...**> per creare una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="8de7f-107">Select an OLE DB connection manager in the list, or click \<**New connection...**> to create a new connection.</span></span>  
  
 <span data-ttu-id="8de7f-108">**Argomenti correlati:** [Gestione connessione OLE DB](connection-manager/ole-db-connection-manager.md), [Configura gestione connessione OLE DB](../../2014/integration-services/configure-ole-db-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="8de7f-108">**Related Topics:** [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md), [Configure OLE DB Connection Manager](../../2014/integration-services/configure-ole-db-connection-manager.md)</span></span>  
  
 <span data-ttu-id="8de7f-109">**DestinationTable**</span><span class="sxs-lookup"><span data-stu-id="8de7f-109">**DestinationTable**</span></span>  
 <span data-ttu-id="8de7f-110">Consente di digitare il nome della tabella o della vista di destinazione o di selezionare una tabella o una vista nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8de7f-110">Type the name of the destination table or view or select a table or view in the list.</span></span>  
  
 <span data-ttu-id="8de7f-111">**Formato**</span><span class="sxs-lookup"><span data-stu-id="8de7f-111">**Format**</span></span>  
 <span data-ttu-id="8de7f-112">Consente di selezionare l'origine del formato per l'inserimento bulk.</span><span class="sxs-lookup"><span data-stu-id="8de7f-112">Select the source of the format for the bulk insert.</span></span> <span data-ttu-id="8de7f-113">Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="8de7f-113">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="8de7f-114">valore</span><span class="sxs-lookup"><span data-stu-id="8de7f-114">Value</span></span>|<span data-ttu-id="8de7f-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8de7f-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8de7f-116">**Usa file**</span><span class="sxs-lookup"><span data-stu-id="8de7f-116">**Use File**</span></span>|<span data-ttu-id="8de7f-117">Consente di selezionare un file contenente la specifica di formato.</span><span class="sxs-lookup"><span data-stu-id="8de7f-117">Select a file containing the format specification.</span></span> <span data-ttu-id="8de7f-118">Selezionando questa opzione viene visualizzata l'opzione dinamica **FormatFile**.</span><span class="sxs-lookup"><span data-stu-id="8de7f-118">Selecting this option displays the dynamic option, **FormatFile**.</span></span>|  
|<span data-ttu-id="8de7f-119">**Specifica**</span><span class="sxs-lookup"><span data-stu-id="8de7f-119">**Specify**</span></span>|<span data-ttu-id="8de7f-120">Consente di specificare il formato.</span><span class="sxs-lookup"><span data-stu-id="8de7f-120">Specify the format.</span></span> <span data-ttu-id="8de7f-121">Selezionando questa opzione vengono visualizzate le opzioni dinamiche `RowDelimiter` e `ColumnDelimiter` .</span><span class="sxs-lookup"><span data-stu-id="8de7f-121">Selecting this option displays the dynamic options, `RowDelimiter` and `ColumnDelimiter`.</span></span>|  
  
 <span data-ttu-id="8de7f-122">**File**</span><span class="sxs-lookup"><span data-stu-id="8de7f-122">**File**</span></span>  
 <span data-ttu-id="8de7f-123">Selezionare una gestione connessione file o file flat nell'elenco o fare clic su \<**New connection...**> per creare una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="8de7f-123">Select a File or Flat File connection manager in the list, or click \<**New connection...**> to create a new connection.</span></span>  
  
 <span data-ttu-id="8de7f-124">Il percorso del file è relativo al Motore di database di SQL Server specificato nella gestione connessione per questa attività.</span><span class="sxs-lookup"><span data-stu-id="8de7f-124">The file location is relative to the SQL Server Database Engine specified in the connection manager for this task.</span></span> <span data-ttu-id="8de7f-125">Il file di testo deve essere accessibile dal Motore di database di SQL Server in un disco rigido locale sul server oppure tramite un'unità condivisa o di cui è stato eseguito il mapping a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8de7f-125">The text file must be accessible by the SQL Server Database Engine either on a local hard drive on the server, or via a share or mapped drive to the SQL Server.</span></span> <span data-ttu-id="8de7f-126">Non è possibile accedere al file tramite SSIS Runtime.</span><span class="sxs-lookup"><span data-stu-id="8de7f-126">The file is not accessed by the SSIS Runtime.</span></span>  
  
 <span data-ttu-id="8de7f-127">Se si accede al file di origine utilizzando una gestione connessione file flat, l'attività Inserimento bulk non utilizzerà il formato specificato nella gestione connessione file flat,</span><span class="sxs-lookup"><span data-stu-id="8de7f-127">If you access the source file by using a Flat File connection manager, the Bulk Insert task does not use the format specified in the Flat File connection manager.</span></span> <span data-ttu-id="8de7f-128">ma userà il formato specificato in un file di formato o i valori delle proprietà RowDelimiter e ColumnDelimiter dell'attività.</span><span class="sxs-lookup"><span data-stu-id="8de7f-128">Instead, the Bulk Insert task uses either the format specified in a format file or the values of the RowDelimiter and ColumnDelimiter properties of the task.</span></span>  
  
 <span data-ttu-id="8de7f-129">**Argomenti correlati:** [Gestione connessione file](connection-manager/file-connection-manager.md), [Editor gestione connessione file](../../2014/integration-services/file-connection-manager-editor.md), [Gestione connessione file flat](connection-manager/flat-file-connection-manager.md), [Editor gestione connessione file flat &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md), [Editor gestione connessione file flat &#40;pagina Colonne&#41;](../../2014/integration-services/flat-file-connection-manager-editor-columns-page.md), [Editor gestione connessione file flat &#40;pagina Avanzate&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md)</span><span class="sxs-lookup"><span data-stu-id="8de7f-129">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md), [Flat File Connection Manager](connection-manager/flat-file-connection-manager.md), [Flat File Connection Manager Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md), [Flat File Connection Manager Editor &#40;Columns Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-columns-page.md), [Flat File Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md)</span></span>  
  
 <span data-ttu-id="8de7f-130">**Aggiorna tabelle**</span><span class="sxs-lookup"><span data-stu-id="8de7f-130">**Refresh Tables**</span></span>  
 <span data-ttu-id="8de7f-131">Consente di aggiornare l'elenco di tabelle e di viste.</span><span class="sxs-lookup"><span data-stu-id="8de7f-131">Refresh the list of tables and views.</span></span>  
  
## <a name="format-dynamic-options"></a><span data-ttu-id="8de7f-132">Opzioni dinamiche di Format</span><span class="sxs-lookup"><span data-stu-id="8de7f-132">Format Dynamic Options</span></span>  
  
### <a name="format--use-file"></a><span data-ttu-id="8de7f-133">Format = Usa file</span><span class="sxs-lookup"><span data-stu-id="8de7f-133">Format = Use File</span></span>  
 <span data-ttu-id="8de7f-134">**FormatFile**</span><span class="sxs-lookup"><span data-stu-id="8de7f-134">**FormatFile**</span></span>  
 <span data-ttu-id="8de7f-135">Digitare il percorso del file di formato oppure fare clic sui puntini di sospensione **(...)** per trovare il file di formato.</span><span class="sxs-lookup"><span data-stu-id="8de7f-135">Type the path of the format file or click the ellipsis button **(...)** to locate the format file.</span></span>  
  
### <a name="format--specify"></a><span data-ttu-id="8de7f-136">Format = Specifica</span><span class="sxs-lookup"><span data-stu-id="8de7f-136">Format = Specify</span></span>  
 `RowDelimiter`  
 <span data-ttu-id="8de7f-137">Consente di specificare il delimitatore di riga nel file di origine.</span><span class="sxs-lookup"><span data-stu-id="8de7f-137">Specify the row delimiter in the source file.</span></span> <span data-ttu-id="8de7f-138">Il valore predefinito è **{CR}{LF}** .</span><span class="sxs-lookup"><span data-stu-id="8de7f-138">The default value is **{CR}{LF}**.</span></span>  
  
 `ColumnDelimiter`  
 <span data-ttu-id="8de7f-139">Consente di specificare il delimitatore di colonna nel file di origine.</span><span class="sxs-lookup"><span data-stu-id="8de7f-139">Specify the column delimiter in the source file.</span></span> <span data-ttu-id="8de7f-140">Il valore predefinito è **Tabulazione**.</span><span class="sxs-lookup"><span data-stu-id="8de7f-140">The default is **Tab**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8de7f-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8de7f-141">See Also</span></span>  
 <span data-ttu-id="8de7f-142">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="8de7f-142">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="8de7f-143">[Editor attività Inserimento bulk &#40;pagina generale&#41;](../../2014/integration-services/bulk-insert-task-editor-general-page.md) </span><span class="sxs-lookup"><span data-stu-id="8de7f-143">[Bulk Insert Task Editor &#40;General Page&#41;](../../2014/integration-services/bulk-insert-task-editor-general-page.md) </span></span>  
 <span data-ttu-id="8de7f-144">[Editor attività Inserimento bulk &#40;pagina Opzioni&#41;](../../2014/integration-services/bulk-insert-task-editor-options-page.md) </span><span class="sxs-lookup"><span data-stu-id="8de7f-144">[Bulk Insert Task Editor &#40;Options Page&#41;](../../2014/integration-services/bulk-insert-task-editor-options-page.md) </span></span>  
 <span data-ttu-id="8de7f-145">[Pagina Espressioni](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="8de7f-145">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="8de7f-146">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8de7f-146">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 [<span data-ttu-id="8de7f-147">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="8de7f-147">Control Flow</span></span>](control-flow/control-flow.md)  
  
  
