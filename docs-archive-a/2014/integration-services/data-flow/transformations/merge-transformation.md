---
title: Trasformazione Unione | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.mergetrans.f1
helpviewer_keywords:
- merging datasets [Integration Services]
- merging data [Integration Services]
- Merge transformation
- combining datasets
- datasets [Integration Services], merging
ms.assetid: cff8690c-07ac-46a0-aab5-20bd4848c677
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7d1d35e92b5978016b6a53956e5b6f1f6642f5ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724015"
---
# <a name="merge-transformation"></a><span data-ttu-id="dc5fe-102">Unione - trasformazione</span><span class="sxs-lookup"><span data-stu-id="dc5fe-102">Merge Transformation</span></span>
  <span data-ttu-id="dc5fe-103">La trasformazione Unione consente di combinare due set di dati ordinati in un singolo set di dati.</span><span class="sxs-lookup"><span data-stu-id="dc5fe-103">The Merge transformation combines two sorted datasets into a single dataset.</span></span> <span data-ttu-id="dc5fe-104">Le righe di ogni set di dati vengono inserite nell'output in base ai valori delle relative colonne chiave.</span><span class="sxs-lookup"><span data-stu-id="dc5fe-104">The rows from each dataset are inserted into the output based on values in their key columns.</span></span>  
  
 <span data-ttu-id="dc5fe-105">Includendo la trasformazione Unione in un flusso di dati, è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="dc5fe-105">By including the Merge transformation in a data flow, you can perform the following tasks:</span></span>  
  
-   <span data-ttu-id="dc5fe-106">Unire dati da due origini dei dati, ad esempio tabelle e file.</span><span class="sxs-lookup"><span data-stu-id="dc5fe-106">Merge data from two data sources, such as tables and files.</span></span>  
  
-   <span data-ttu-id="dc5fe-107">Creare set di dati complessi, nidificando più trasformazioni Unione.</span><span class="sxs-lookup"><span data-stu-id="dc5fe-107">Create complex datasets by nesting Merge transformations.</span></span>  
  
-   <span data-ttu-id="dc5fe-108">Unire di nuovo le righe dopo aver corretto gli errori nei dati.</span><span class="sxs-lookup"><span data-stu-id="dc5fe-108">Remerge rows after correcting errors in the data.</span></span>  
  
 <span data-ttu-id="dc5fe-109">La trasformazione Unione è simile alle trasformazioni Unione input multipli.</span><span class="sxs-lookup"><span data-stu-id="dc5fe-109">The Merge transformation is similar to the Union All transformations.</span></span> <span data-ttu-id="dc5fe-110">Utilizzare la trasformazione Unione input multipli anziché la trasformazione Unione nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dc5fe-110">Use the Union All transformation instead of the Merge transformation in the following situations:</span></span>  
  
-   <span data-ttu-id="dc5fe-111">Gli input della trasformazione non sono ordinati.</span><span class="sxs-lookup"><span data-stu-id="dc5fe-111">The transformation inputs are not sorted.</span></span>  
  
-   <span data-ttu-id="dc5fe-112">Non è necessario che l'output combinato sia ordinato.</span><span class="sxs-lookup"><span data-stu-id="dc5fe-112">The combined output does not need to be sorted.</span></span>  
  
-   <span data-ttu-id="dc5fe-113">La trasformazione include più di due input.</span><span class="sxs-lookup"><span data-stu-id="dc5fe-113">The transformation has more than two inputs.</span></span>  
  
## <a name="input-requirements"></a><span data-ttu-id="dc5fe-114">Requisiti relativi all'input</span><span class="sxs-lookup"><span data-stu-id="dc5fe-114">Input Requirements</span></span>  
 <span data-ttu-id="dc5fe-115">Per eseguire la trasformazione Unione, è necessario che i relativi dati di input siano ordinati.</span><span class="sxs-lookup"><span data-stu-id="dc5fe-115">The Merge Transformation requires sorted data for its inputs.</span></span> <span data-ttu-id="dc5fe-116">Per altre informazioni su questo requisito importante, vedere [Ordinamento dei dati per le trasformazioni Unione e Merge Join](sort-data-for-the-merge-and-merge-join-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="dc5fe-116">For more information about this important requirement, see [Sort Data for the Merge and Merge Join Transformations](sort-data-for-the-merge-and-merge-join-transformations.md).</span></span>  
  
 <span data-ttu-id="dc5fe-117">La trasformazione Unione richiede inoltre che le colonne da unire nei relativi input abbiano metadati corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="dc5fe-117">The Merge transformation also requires that the merged columns in its inputs have matching metadata.</span></span> <span data-ttu-id="dc5fe-118">Non è ad esempio possibile unire una colonna con tipo di dati numeric a una colonna con tipo di dati character.</span><span class="sxs-lookup"><span data-stu-id="dc5fe-118">For example, you cannot merge a column that has a numeric data type with a column that has a character data type.</span></span> <span data-ttu-id="dc5fe-119">Se i dati sono di tipo string, la lunghezza della colonna nel secondo input dovrà essere minore o uguale a quella della colonna nel primo input, alla quale verrà unita.</span><span class="sxs-lookup"><span data-stu-id="dc5fe-119">If the data has a string data type, the length of the column in the second input must be less than or equal to the length of the column in the first input with which it is merged.</span></span>  
  
 <span data-ttu-id="dc5fe-120">In Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] l'interfaccia utente della trasformazione Unione mappa automaticamente le colonne con gli stessi metadati.</span><span class="sxs-lookup"><span data-stu-id="dc5fe-120">In the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, the user interface for the Merge transformation automatically maps columns that have the same metadata.</span></span> <span data-ttu-id="dc5fe-121">È quindi possibile eseguire il mapping manualmente altre colonne con tipi di dati compatibili.</span><span class="sxs-lookup"><span data-stu-id="dc5fe-121">You can then manually map other columns that have compatible data types.</span></span>  
  
 <span data-ttu-id="dc5fe-122">Questa trasformazione include due input e un output.</span><span class="sxs-lookup"><span data-stu-id="dc5fe-122">This transformation has two inputs and one output.</span></span> <span data-ttu-id="dc5fe-123">Non supporta un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="dc5fe-123">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-merge-transformation"></a><span data-ttu-id="dc5fe-124">Configurazione della trasformazione Unione</span><span class="sxs-lookup"><span data-stu-id="dc5fe-124">Configuration of the Merge Transformation</span></span>  
 <span data-ttu-id="dc5fe-125">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="dc5fe-125">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="dc5fe-126">Per altre informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor trasformazione Unione** , vedere [Editor trasformazione Unione](../../merge-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="dc5fe-126">For more information about the properties that you can set in the **Merge Transformation Editor** dialog box, see [Merge Transformation Editor](../../merge-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="dc5fe-127">Per ulteriori informazioni sulle proprietà che è possibile impostare a livello di codice, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="dc5fe-127">For more information about the properties that you can programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="dc5fe-128">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="dc5fe-128">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="dc5fe-129">Proprietà personalizzate delle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="dc5fe-129">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="dc5fe-130">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="dc5fe-130">Related Tasks</span></span>  
 <span data-ttu-id="dc5fe-131">Per informazioni dettagliate sull'impostazione delle proprietà, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="dc5fe-131">For details about how to set properties, see the following topics:</span></span>  
  
-   [<span data-ttu-id="dc5fe-132">Impostazione delle proprietà di un componente del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="dc5fe-132">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
-   [<span data-ttu-id="dc5fe-133">Ordinare i dati per le trasformazioni Unione e Merge Join</span><span class="sxs-lookup"><span data-stu-id="dc5fe-133">Sort Data for the Merge and Merge Join Transformations</span></span>](sort-data-for-the-merge-and-merge-join-transformations.md)  
  
## <a name="see-also"></a><span data-ttu-id="dc5fe-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc5fe-134">See Also</span></span>  
 <span data-ttu-id="dc5fe-135">[Trasformazione Merge join](merge-join-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="dc5fe-135">[Merge Join Transformation](merge-join-transformation.md) </span></span>  
 <span data-ttu-id="dc5fe-136">[Trasformazione Unione input multipli](union-all-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="dc5fe-136">[Union All Transformation](union-all-transformation.md) </span></span>  
 <span data-ttu-id="dc5fe-137">[Flusso di dati](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="dc5fe-137">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="dc5fe-138">Trasformazioni di Integration Services</span><span class="sxs-lookup"><span data-stu-id="dc5fe-138">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
