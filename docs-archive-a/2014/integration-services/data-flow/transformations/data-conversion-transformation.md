---
title: Trasformazione Conversione dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataconversiontrans.f1
helpviewer_keywords:
- converting data types [Integration Services]
- Data Conversion transformation
- data types [Integration Services], converting
ms.assetid: fd515bbc-6f49-4d0c-ae7f-6ea3c3f24a1c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 57b1f70c070cdf81dc0bc899ed365d048db26cc9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624277"
---
# <a name="data-conversion-transformation"></a><span data-ttu-id="48604-102">Conversione dati - trasformazione</span><span class="sxs-lookup"><span data-stu-id="48604-102">Data Conversion Transformation</span></span>
  <span data-ttu-id="48604-103">La trasformazione Conversione dati converte i dati in una colonna di input in un tipo di dati diverso e quindi li copia in una nuova colonna di output.</span><span class="sxs-lookup"><span data-stu-id="48604-103">The Data Conversion transformation converts the data in an input column to a different data type and then copies it to a new output column.</span></span> <span data-ttu-id="48604-104">Un pacchetto può ad esempio estrarre dati da più origini e quindi utilizzare questa trasformazione per convertire le colonne nel tipo di dati richiesto dall'archivio dati di destinazione.</span><span class="sxs-lookup"><span data-stu-id="48604-104">For example, a package can extract data from multiple sources, and then use this transformation to convert columns to the data type required by the destination data store.</span></span> <span data-ttu-id="48604-105">È possibile applicare più conversioni a una singola colonna di input.</span><span class="sxs-lookup"><span data-stu-id="48604-105">You can apply multiple conversions to a single input column.</span></span>  
  
 <span data-ttu-id="48604-106">Tramite questa trasformazione un pacchetto può eseguire i tipi di conversioni dei dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="48604-106">Using this transformation, a package can perform the following types of data conversions:</span></span>  
  
-   <span data-ttu-id="48604-107">Modifica del tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="48604-107">Change the data type.</span></span> <span data-ttu-id="48604-108">Per altre informazioni, vedere [Tipi di dati di Integration Services](../integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="48604-108">For more information, see [Integration Services Data Types](../integration-services-data-types.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="48604-109">Se i dati da convertire hanno tipo di dati date o datetime, per la data nella colonna di output verrà utilizzato il formato ISO anche se le impostazioni locali specificano un formato diverso.</span><span class="sxs-lookup"><span data-stu-id="48604-109">If you are converting data to a date or a datetime data type, the date in the output column is in the ISO format, although the locale preference may specify a different format.</span></span>  
  
-   <span data-ttu-id="48604-110">Impostazione della lunghezza di colonna dei dati stringa, nonché della scala e della precisione dei dati numerici.</span><span class="sxs-lookup"><span data-stu-id="48604-110">Set the column length of string data and the precision and scale on numeric data.</span></span> <span data-ttu-id="48604-111">Per altre informazioni, vedere [Precisione, scala e lunghezza &#40;Transact-SQL&#41;](/sql/t-sql/data-types/precision-scale-and-length-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="48604-111">For more information, see [Precision, Scale, and Length &#40;Transact-SQL&#41;](/sql/t-sql/data-types/precision-scale-and-length-transact-sql).</span></span>  
  
-   <span data-ttu-id="48604-112">Impostazione di una tabella codici.</span><span class="sxs-lookup"><span data-stu-id="48604-112">Specify a code page.</span></span> <span data-ttu-id="48604-113">Per altre informazioni, vedere [Comparing String Data](../comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="48604-113">For more information, see [Comparing String Data](../comparing-string-data.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="48604-114">È possibile copiare dati tra colonne con un tipo di dati string solo se le due colonne utilizzano la stessa tabella codici.</span><span class="sxs-lookup"><span data-stu-id="48604-114">When copying between columns with a string data type, the two columns must use the same code page.</span></span>  
  
 <span data-ttu-id="48604-115">Se la lunghezza di una colonna di output con dati di tipo string è minore di quella della colonna di input corrispondente, i dati di output verranno troncati.</span><span class="sxs-lookup"><span data-stu-id="48604-115">If the length of an output column of string data is shorter than the length of its corresponding input column, the output data is truncated.</span></span> <span data-ttu-id="48604-116">Per altre informazioni, vedere [Gestione degli errori nei dati](../error-handling-in-data.md).</span><span class="sxs-lookup"><span data-stu-id="48604-116">For more information, see [Error Handling in Data](../error-handling-in-data.md).</span></span>  
  
 <span data-ttu-id="48604-117">Questa trasformazione include un input, un output e un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="48604-117">This transformation has one input, one output, and one error output.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="48604-118">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="48604-118">Related Tasks</span></span>  
 <span data-ttu-id="48604-119">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="48604-119">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span> <span data-ttu-id="48604-120">Per informazioni sull'utilizzo della trasformazione Conversione dati in Progettazione SSIS, vedere [Conversione di dati in un tipo di dati diverso utilizzando la trasformazione Conversione dati](data-conversion-transformation.md) e [Editor trasformazione Conversione dati](../../data-conversion-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="48604-120">For information about using the Data Conversion Transformation in the SSIS Designer, see [Convert Data to a Different Data Type by Using the Data Conversion Transformation](data-conversion-transformation.md) and [Data Conversion Transformation Editor](../../data-conversion-transformation-editor.md).</span></span> <span data-ttu-id="48604-121">Per informazioni sull'impostazione delle proprietà di questa trasformazione a livello di programmazione, vedere [Proprietà comuni](../../common-properties.md) e [Proprietà personalizzate delle trasformazioni](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="48604-121">For information about setting properties of this transformation programmatically, see [Common Properties](../../common-properties.md) and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="48604-122">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="48604-122">Related Content</span></span>  
 <span data-ttu-id="48604-123">Intervento nel blog sul [confronto delle prestazioni tra le tecniche di conversione dei tipi di dati in SSIS 2008](https://techcommunity.microsoft.com/t5/datacat/performance-comparison-between-data-type-conversion-techniques/ba-p/305035)su blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="48604-123">Blog entry, [Performance Comparison between Data Type Conversion Techniques in SSIS 2008](https://techcommunity.microsoft.com/t5/datacat/performance-comparison-between-data-type-conversion-techniques/ba-p/305035), on blogs.msdn.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48604-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48604-124">See Also</span></span>  
 <span data-ttu-id="48604-125">[Analisi veloce](../../fast-parse.md) </span><span class="sxs-lookup"><span data-stu-id="48604-125">[Fast Parse](../../fast-parse.md) </span></span>  
 <span data-ttu-id="48604-126">[Flusso di dati](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="48604-126">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="48604-127">Trasformazioni di Integration Services</span><span class="sxs-lookup"><span data-stu-id="48604-127">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
