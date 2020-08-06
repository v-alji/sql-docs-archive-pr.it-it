---
title: Origine file flat | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfilesource.f1
helpviewer_keywords:
- sources [Integration Services], Flat File
- text file reading [Integration Services]
- flat files
- Flat File source
ms.assetid: 4a64f7f3-f25d-4db0-93b3-a29496030e58
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b1ca0f38c457256b3f2ed2ddb81bfbd0dc06b6c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726096"
---
# <a name="flat-file-source"></a><span data-ttu-id="c910a-102">origine file flat</span><span class="sxs-lookup"><span data-stu-id="c910a-102">Flat File Source</span></span>
  <span data-ttu-id="c910a-103">L'origine file flat legge dati da un file di testo.</span><span class="sxs-lookup"><span data-stu-id="c910a-103">The Flat File source reads data from a text file.</span></span> <span data-ttu-id="c910a-104">Tale file può essere in formato delimitato, a larghezza fissa o misto.</span><span class="sxs-lookup"><span data-stu-id="c910a-104">The text file can be in delimited, fixed width, or mixed format.</span></span>  
  
-   <span data-ttu-id="c910a-105">Nel formato delimitato per definire le righe e le colonne vengono utilizzati delimitatori di riga e colonna.</span><span class="sxs-lookup"><span data-stu-id="c910a-105">Delimited format uses column and row delimiters to define columns and rows.</span></span>  
  
-   <span data-ttu-id="c910a-106">Nel formato a larghezza fissa per definire le righe e le colonne viene utilizzata la larghezza.</span><span class="sxs-lookup"><span data-stu-id="c910a-106">Fixed width format uses width to define columns and rows.</span></span> <span data-ttu-id="c910a-107">In questo formato è inoltre previsto un carattere di riempimento da utilizzare per portare i campi alla lunghezza massima.</span><span class="sxs-lookup"><span data-stu-id="c910a-107">This format also includes a character for padding fields to their maximum width.</span></span>  
  
-   <span data-ttu-id="c910a-108">Nel formato non allineato a destra tutte le colonne sono definite in base alla larghezza, ad eccezione dell'ultima che è delimitata dal delimitatore di riga.</span><span class="sxs-lookup"><span data-stu-id="c910a-108">Ragged right format uses width to define all columns, except for the last column, which is delimited by the row delimiter.</span></span>  
  
 <span data-ttu-id="c910a-109">Per configurare l'origine file flat, procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="c910a-109">You can configure the Flat File source in the following ways:</span></span>  
  
-   <span data-ttu-id="c910a-110">Aggiungere all'output della trasformazione una colonna contenente il nome del file di testo da cui l'origine file flat estrae i dati.</span><span class="sxs-lookup"><span data-stu-id="c910a-110">Add a column to the transformation output that contains the name of the text file from which the Flat File source extracts data.</span></span>  
  
-   <span data-ttu-id="c910a-111">Specificare se le stringhe di lunghezza zero nelle colonne devono essere interpretate come valori Null.</span><span class="sxs-lookup"><span data-stu-id="c910a-111">Specify whether the Flat File source interprets zero-length strings in columns as null values.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c910a-112">Affinché sia possibile interpretare come Null le stringhe di lunghezza zero, la gestione connessione file flat utilizzata dall'origine file flat deve essere configurata per l'utilizzo di un formato delimitato.</span><span class="sxs-lookup"><span data-stu-id="c910a-112">The Flat File connection manager that the Flat File source uses must be configured to use a delimited format to interpret zero-length strings as nulls.</span></span> <span data-ttu-id="c910a-113">Se la gestione connessione utilizza un formato a larghezza fissa o non allineato a destra, i dati costituiti da spazi non potranno essere interpretati come valori Null.</span><span class="sxs-lookup"><span data-stu-id="c910a-113">If the connection manager uses the fixed width or ragged right formats, data that consists of spaces cannot be interpreted as null values.</span></span>  
  
 <span data-ttu-id="c910a-114">Le colonne di output nell'output dell'origine file flat includono la proprietà FastParse.</span><span class="sxs-lookup"><span data-stu-id="c910a-114">The output columns in the output of the Flat File source include the FastParse property.</span></span> <span data-ttu-id="c910a-115">FastParse indica se la colonna usa le routine di analisi più veloci ma indipendenti dalle impostazioni locali disponibili in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] oppure le routine di analisi standard dipendenti dalle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="c910a-115">FastParse indicates whether the column uses the quicker, but locale-insensitive, fast parsing routines that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides or the locale-sensitive standard parsing routines.</span></span> <span data-ttu-id="c910a-116">Per altre informazioni, vedere [Analisi veloce](../fast-parse.md) e [Analisi standard](../standard-parse.md).</span><span class="sxs-lookup"><span data-stu-id="c910a-116">For more information, see [Fast Parse](../fast-parse.md) and [Standard Parse](../standard-parse.md).</span></span>  
  
 <span data-ttu-id="c910a-117">Le colonne di output includono anche la proprietà UseBinaryFormat,</span><span class="sxs-lookup"><span data-stu-id="c910a-117">Output columns also include the UseBinaryFormat property.</span></span> <span data-ttu-id="c910a-118">utilizzata per implementare il supporto per i dati binari, ad esempio i dati con formato decimale packed, all'interno dei file.</span><span class="sxs-lookup"><span data-stu-id="c910a-118">You use this property to implement support for binary data, such as data with the packed decimal format, in files.</span></span> <span data-ttu-id="c910a-119">Per impostazione predefinita, UseBinaryFormat è impostato su `false` .</span><span class="sxs-lookup"><span data-stu-id="c910a-119">By default UseBinaryFormat is set to `false`.</span></span> <span data-ttu-id="c910a-120">Se si desidera utilizzare un formato binario, impostare UseBinaryFormat `true` su e il tipo di dati della colonna di output su `DT_BYTES` .</span><span class="sxs-lookup"><span data-stu-id="c910a-120">If you want to use a binary format, set UseBinaryFormat to `true` and the data type on the output column to `DT_BYTES`.</span></span> <span data-ttu-id="c910a-121">In questo modo, nell'origine file flat viene saltata la conversione dei dati e i dati vengono passati alla colonna di output così come sono.</span><span class="sxs-lookup"><span data-stu-id="c910a-121">When you do this, the Flat File source skips the data conversion and passes the data to the output column as is.</span></span> <span data-ttu-id="c910a-122">È quindi possibile utilizzare una trasformazione, ad esempio Colonna derivata o Conversione dati, per eseguire il cast dei dati `DT_BYTES` in un diverso tipo di dati oppure scrivere uno script personalizzato in una trasformazione Script per interpretare i dati.</span><span class="sxs-lookup"><span data-stu-id="c910a-122">You can then use a transformation such as the Derived Column or Data Conversion to cast the `DT_BYTES` data to a different data type, or you can write custom script in a Script transformation to interpret the data.</span></span> <span data-ttu-id="c910a-123">Per l'interpretazione dei dati è inoltre possibile scrivere un componente del flusso di dati personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c910a-123">You can also write a custom data flow component to interpret the data.</span></span> <span data-ttu-id="c910a-124">Per ulteriori informazioni sui tipi di dati di cui è possibile eseguire il cast `DT_BYTES` , vedere [cast &#40;espressione SSIS&#41;](../expressions/cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="c910a-124">For more information about which data types you can cast `DT_BYTES` to, see [Cast &#40;SSIS Expression&#41;](../expressions/cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="c910a-125">Per accedere al file di testo, questa origine utilizza una gestione connessione file flat.</span><span class="sxs-lookup"><span data-stu-id="c910a-125">This source uses a Flat File connection manager to access the text file.</span></span> <span data-ttu-id="c910a-126">Impostando le proprietà di tale gestione connessione è possibile fornire informazioni sul file e le singole colonne contenute, nonché specificare la modalità con cui l'origine file flat deve gestire i dati del file di testo.</span><span class="sxs-lookup"><span data-stu-id="c910a-126">By setting properties on the Flat File connection manager, you can provide information about the file and each column in it, and specify how the Flat File source should handle the data in the text file.</span></span> <span data-ttu-id="c910a-127">È ad esempio possibile specificare i caratteri che delimitano le righe e le colonne del file, oltre al tipo di dati e alla lunghezza di ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="c910a-127">For example, you can specify the characters that delimit columns and rows in the file, and the data type and the length of each column.</span></span> <span data-ttu-id="c910a-128">Per ulteriori informazioni, vedere [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="c910a-128">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="c910a-129">Questa origine include un output e un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="c910a-129">This source has one output and one error output.</span></span>  
  
## <a name="configuration-of-the-flat-file-source"></a><span data-ttu-id="c910a-130">Configurazione dell'origine file flat</span><span class="sxs-lookup"><span data-stu-id="c910a-130">Configuration of the Flat File Source</span></span>  
 <span data-ttu-id="c910a-131">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="c910a-131">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="c910a-132">Per altre informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor origine file flat**, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c910a-132">For more information about the properties that you can set in the **Flat File Source Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="c910a-133">Editor origine file flat &#40;pagina Gestione connessione&#41;</span><span class="sxs-lookup"><span data-stu-id="c910a-133">Flat File Source Editor &#40;Connection Manager Page&#41;</span></span>](../flat-file-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="c910a-134">Editor origine file flat &#40;pagina Colonne&#41;</span><span class="sxs-lookup"><span data-stu-id="c910a-134">Flat File Source Editor &#40;Columns Page&#41;</span></span>](../flat-file-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="c910a-135">Editor origine file flat &#40;pagina Output degli errori&#41;</span><span class="sxs-lookup"><span data-stu-id="c910a-135">Flat File Source Editor &#40;Error Output Page&#41;</span></span>](../flat-file-source-editor-error-output-page.md)  
  
 <span data-ttu-id="c910a-136">Nella finestra di dialogo **Editor avanzato** sono disponibili le proprietà che è possibile impostare a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="c910a-136">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="c910a-137">Per ulteriori informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor avanzato** o a livello di codice, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c910a-137">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="c910a-138">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="c910a-138">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="c910a-139">Proprietà personalizzate del file flat</span><span class="sxs-lookup"><span data-stu-id="c910a-139">Flat File Custom Properties</span></span>](flat-file-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="c910a-140">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="c910a-140">Related Tasks</span></span>  
 <span data-ttu-id="c910a-141">Per informazioni su come impostare le proprietà di un componente del flusso di dati, vedere [Impostazione delle proprietà di un componente del flusso di dati](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="c910a-141">For details about how to set properties of a data flow component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c910a-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c910a-142">See Also</span></span>  
 <span data-ttu-id="c910a-143">[Destinazione file flat](flat-file-destination.md) </span><span class="sxs-lookup"><span data-stu-id="c910a-143">[Flat File Destination](flat-file-destination.md) </span></span>  
 [<span data-ttu-id="c910a-144">Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="c910a-144">Data Flow</span></span>](data-flow.md)  
  
  
