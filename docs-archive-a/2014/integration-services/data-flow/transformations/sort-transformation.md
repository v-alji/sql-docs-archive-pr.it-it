---
title: Trasformazione Ordinamento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sorttrans.f1
helpviewer_keywords:
- Sort transformation
- descending sorts
- ascending sorts
- sorting data [Integration Services]
- multiple sorts
- duplicate data [Integration Services]
ms.assetid: 728c9351-84a8-4a89-be4d-d50d4adc04e0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7039d02b6cc55355c3b27e5694474df4666570ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629938"
---
# <a name="sort-transformation"></a><span data-ttu-id="9dc3b-102">Ordinamento - trasformazione</span><span class="sxs-lookup"><span data-stu-id="9dc3b-102">Sort Transformation</span></span>
  <span data-ttu-id="9dc3b-103">La trasformazione Ordinamento consente di disporre i dati di input in ordine crescente o decrescente e di copiare i dati ordinati nell'output della trasformazione.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-103">The Sort transformation sorts input data in ascending or descending order and copies the sorted data to the transformation output.</span></span> <span data-ttu-id="9dc3b-104">A uno stesso input è possibile applicare più ordinamenti, ognuno dei quali è identificato da un numero che ne determina il tipo.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-104">You can apply multiple sorts to an input; each sort is identified by a numeral that determines the sort order.</span></span> <span data-ttu-id="9dc3b-105">La colonna con il numero più basso viene ordinata per prima, quindi viene ordinata quella con il secondo numero più basso e così via.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-105">The column with the lowest number is sorted first, the sort column with the second lowest number is sorted next, and so on.</span></span> <span data-ttu-id="9dc3b-106">Se ad esempio la colonna di nome **CountryRegion** ha come tipo di ordinamento 1 e la colonna di nome **City** ha come tipo di ordinamento 2, l'output verrà ordinato prima per country/region, quindi per city.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-106">For example, if a column named **CountryRegion** has a sort order of 1 and a column named **City** has a sort order of 2, the output is sorted by country/region and then by city.</span></span> <span data-ttu-id="9dc3b-107">Un numero positivo indica che l'ordinamento è crescente, mentre un numero negativo indica che è decrescente.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-107">A positive number denotes that the sort is ascending, and a negative number denotes that the sort is descending.</span></span> <span data-ttu-id="9dc3b-108">Le colonne che non sono ordinate hanno un tipo di ordinamento 0.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-108">Columns that are not sorted have a sort order of 0.</span></span> <span data-ttu-id="9dc3b-109">Le colonne non selezionate per l'ordinamento vengono copiate automaticamente nell'output della trasformazione insieme alle colonne ordinate.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-109">Columns that are not selected for sorting are automatically copied to the transformation output together with the sorted columns.</span></span>  
  
 <span data-ttu-id="9dc3b-110">La trasformazione Ordinamento include un set di opzioni di confronto che consentono di definire la modalità di gestione dei dati stringa in una colonna.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-110">The Sort transformation includes a set of comparison options to define how the transformation handles the string data in a column.</span></span> <span data-ttu-id="9dc3b-111">Per altre informazioni, vedere [Comparing String Data](../comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="9dc3b-111">For more information, see [Comparing String Data](../comparing-string-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9dc3b-112">La trasformazione Ordinamento non dispone i GUID nello stesso ordine della clausola ORDER BY in Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-112">The Sort transformation does not sort GUIDs in the same order as the ORDER BY clause does in Transact-SQL.</span></span> <span data-ttu-id="9dc3b-113">La trasformazione Ordinamento dispone i GUID che iniziano con 0-9 prima di quelli che iniziano con A-F, mentre la clausola ORDER BY li ordina in modo diverso, come implementato in [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9dc3b-113">While the Sort transformation sorts GUIDs that start with 0-9 before GUIDs that start with A-F, the ORDER BY clause, as implemented in the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], sorts them differently.</span></span> <span data-ttu-id="9dc3b-114">Per altre informazioni, vedere [Clausola ORDER BY &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9dc3b-114">For more information, see [ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql).</span></span>  
  
 <span data-ttu-id="9dc3b-115">La trasformazione Ordinamento è inoltre in grado di rimuovere le righe duplicate nell'ambito dell'operazione di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-115">The Sort transformation can also remove duplicate rows as part of its sort.</span></span> <span data-ttu-id="9dc3b-116">Sono considerate duplicate le righe che hanno valori di chiave di ordinamento identici.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-116">Duplicate rows are rows with the same sort key values.</span></span> <span data-ttu-id="9dc3b-117">Il valore della chiave di ordinamento viene generato in base alle opzioni utilizzate per il confronto delle stringhe e questo significa che stringhe letterali diverse possono avere gli stessi valori di chiave di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-117">The sort key value is generated based on the string comparison options being used, which means that different literal strings may have the same sort key values.</span></span> <span data-ttu-id="9dc3b-118">La trasformazione identifica come duplicate le righe delle colonne di input che hanno valori di chiave di ordinamento identici, anche se i valori effettivi sono diversi.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-118">The transformation identifies rows in the input columns that have different values but the same sort key as duplicates.</span></span>  
  
 <span data-ttu-id="9dc3b-119">La trasformazione Ordinamento include la proprietà personalizzata `MaximumThreads`, che può essere aggiornata da un'espressione di proprietà al caricamento del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-119">The Sort transformation includes the `MaximumThreads` custom property that can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="9dc3b-120">Per altre informazioni, vedere [Espressioni di Integration Services &#40;SSIS&#41;](../../expressions/integration-services-ssis-expressions.md), [Utilizzo delle espressioni di proprietà nei pacchetti](../../expressions/use-property-expressions-in-packages.md) e [Proprietà personalizzate delle trasformazioni](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="9dc3b-120">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md), and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="9dc3b-121">Questa trasformazione include un input e un output.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-121">This transformation has one input and one output.</span></span> <span data-ttu-id="9dc3b-122">Non supporta output degli errori.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-122">It does not support error outputs.</span></span>  
  
## <a name="configuration-of-the-sort-transformation"></a><span data-ttu-id="9dc3b-123">Configurazione della trasformazione Ordinamento</span><span class="sxs-lookup"><span data-stu-id="9dc3b-123">Configuration of the Sort Transformation</span></span>  
 <span data-ttu-id="9dc3b-124">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-124">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="9dc3b-125">Per altre informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor trasformazione Ordinamento** , vedere [Editor trasformazione Ordinamento](../../sort-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="9dc3b-125">For information about the properties that you can set in the **Sort Transformation Editor** dialog box, see [Sort Transformation Editor](../../sort-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="9dc3b-126">Nella finestra di dialogo **Editor avanzato** sono disponibili le proprietà che è possibile impostare a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-126">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="9dc3b-127">Per ulteriori informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor avanzato** o a livello di codice, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9dc3b-127">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="9dc3b-128">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="9dc3b-128">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="9dc3b-129">Proprietà personalizzate delle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="9dc3b-129">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="9dc3b-130">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="9dc3b-130">Related Tasks</span></span>  
 <span data-ttu-id="9dc3b-131">Per altre informazioni su come impostare le proprietà del componente, vedere [Impostazione delle proprietà di un componente del flusso di dati](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="9dc3b-131">For more information about how to set properties of the component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="9dc3b-132">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="9dc3b-132">Related Content</span></span>  
 <span data-ttu-id="9dc3b-133">Esempio relativo al [componente SSIS personalizzato SortDeDuplicateDelimitedString](https://go.microsoft.com/fwlink/?LinkId=220821)su codeplex.com.</span><span class="sxs-lookup"><span data-stu-id="9dc3b-133">Sample, [SortDeDuplicateDelimitedString Custom SSIS Component](https://go.microsoft.com/fwlink/?LinkId=220821), on codeplex.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dc3b-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9dc3b-134">See Also</span></span>  
 <span data-ttu-id="9dc3b-135">[Flusso di dati](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="9dc3b-135">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="9dc3b-136">Trasformazioni di Integration Services</span><span class="sxs-lookup"><span data-stu-id="9dc3b-136">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
