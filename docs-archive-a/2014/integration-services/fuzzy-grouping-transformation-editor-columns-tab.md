---
title: Editor trasformazione Raggruppamento fuzzy (scheda colonne) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzygroupingtransformation.columns.f1
helpviewer_keywords:
- Fuzzy Grouping Transformation Editor
ms.assetid: 24f4539f-2a9f-4acd-acc7-06228a07f7df
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9d3aef9c30a81760b7f09378a8ecd66fee0dac62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713308"
---
# <a name="fuzzy-grouping-transformation-editor-columns-tab"></a><span data-ttu-id="877ea-102">Editor trasformazione Raggruppamento fuzzy (scheda Colonne)</span><span class="sxs-lookup"><span data-stu-id="877ea-102">Fuzzy Grouping Transformation Editor (Columns Tab)</span></span>
  <span data-ttu-id="877ea-103">Utilizzare la scheda **Colonne** della finestra di dialogo **Editor trasformazione Raggruppamento fuzzy** per specificare le colonne utilizzate per raggruppare le righe contenenti valori duplicati</span><span class="sxs-lookup"><span data-stu-id="877ea-103">Use the **Columns** tab of the **Fuzzy Grouping Transformation Editor** dialog box to specify the columns used to group rows with duplicate values.</span></span>  
  
 <span data-ttu-id="877ea-104">Per ulteriori informazioni sulla trasformazione Raggruppamento fuzzy, vedere [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="877ea-104">To learn more about the Fuzzy Grouping transformation, see [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="877ea-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="877ea-105">Options</span></span>  
 <span data-ttu-id="877ea-106">**Colonne di input disponibili**</span><span class="sxs-lookup"><span data-stu-id="877ea-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="877ea-107">Consente di selezionare le colonne di input utilizzate per raggruppare le righe contenenti valori duplicati.</span><span class="sxs-lookup"><span data-stu-id="877ea-107">Select from this list the input columns used to group rows with duplicate values.</span></span>  
  
 <span data-ttu-id="877ea-108">**Nome**</span><span class="sxs-lookup"><span data-stu-id="877ea-108">**Name**</span></span>  
 <span data-ttu-id="877ea-109">Consente di visualizzare i nomi delle colonne di input disponibili.</span><span class="sxs-lookup"><span data-stu-id="877ea-109">View the names of available input columns.</span></span>  
  
 <span data-ttu-id="877ea-110">**Pass-through**</span><span class="sxs-lookup"><span data-stu-id="877ea-110">**Pass Through**</span></span>  
 <span data-ttu-id="877ea-111">Consente di includere la colonna di input nell'output della trasformazione.</span><span class="sxs-lookup"><span data-stu-id="877ea-111">Select whether to include the input column in the output of the transformation.</span></span> <span data-ttu-id="877ea-112">Tutte le colonne utilizzate per il raggruppamento vengono copiate automaticamente nell'output.</span><span class="sxs-lookup"><span data-stu-id="877ea-112">All columns used for grouping are automatically copied to the output.</span></span> <span data-ttu-id="877ea-113">Selezionando questa colonna è possibile includere colonne aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="877ea-113">You can include additional columns by checking this column.</span></span>  
  
 <span data-ttu-id="877ea-114">**Colonna di input**</span><span class="sxs-lookup"><span data-stu-id="877ea-114">**Input Column**</span></span>  
 <span data-ttu-id="877ea-115">Consente di selezionare una delle colonne di input selezionate precedentemente nell'elenco **Colonne di input disponibili** .</span><span class="sxs-lookup"><span data-stu-id="877ea-115">Select one of the input columns selected earlier in the **Available Input Columns** list.</span></span>  
  
 <span data-ttu-id="877ea-116">**Alias di output**</span><span class="sxs-lookup"><span data-stu-id="877ea-116">**Output Alias**</span></span>  
 <span data-ttu-id="877ea-117">Consente di immettere un nome descrittivo per la colonna di output corrispondente.</span><span class="sxs-lookup"><span data-stu-id="877ea-117">Enter a descriptive name for the corresponding output column.</span></span> <span data-ttu-id="877ea-118">Per impostazione predefinita, il nome della colonna di output corrisponde al nome della colonna di input.</span><span class="sxs-lookup"><span data-stu-id="877ea-118">By default, the output column name is the same as the input column name.</span></span>  
  
 <span data-ttu-id="877ea-119">**Alias di output gruppo**</span><span class="sxs-lookup"><span data-stu-id="877ea-119">**Group Output Alias**</span></span>  
 <span data-ttu-id="877ea-120">Consente di immettere un nome descrittivo per la colonna che conterrà il valore canonico per i duplicati raggruppati.</span><span class="sxs-lookup"><span data-stu-id="877ea-120">Enter a descriptive name for the column that will contain the canonical value for the grouped duplicates.</span></span> <span data-ttu-id="877ea-121">Il nome predefinito di questa colonna di output è il nome della colonna di input con l'aggiunta di _clean.</span><span class="sxs-lookup"><span data-stu-id="877ea-121">The default name of this output column is the input column name with _clean appended.</span></span>  
  
 <span data-ttu-id="877ea-122">**Tipo di corrispondenza**</span><span class="sxs-lookup"><span data-stu-id="877ea-122">**Match Type**</span></span>  
 <span data-ttu-id="877ea-123">Consente di selezionare la corrispondenza fuzzy o esatta.</span><span class="sxs-lookup"><span data-stu-id="877ea-123">Select fuzzy or exact matching.</span></span> <span data-ttu-id="877ea-124">Le righe vengono considerate duplicati se sono sufficientemente simili in tutte le colonne della corrispondenza fuzzy.</span><span class="sxs-lookup"><span data-stu-id="877ea-124">Rows are considered duplicates if they are sufficiently similar across all columns with a fuzzy match type.</span></span> <span data-ttu-id="877ea-125">Se inoltre si specifica la corrispondenza esatta su determinate colonne, vengono considerati possibili duplicati solo le righe contenenti valori identici nelle colonne della corrispondenza esatta.</span><span class="sxs-lookup"><span data-stu-id="877ea-125">If you also specify exact matching on certain columns, only rows that contain identical values in the exact matching columns are considered as possible duplicates.</span></span> <span data-ttu-id="877ea-126">Se si sa pertanto che una determinata colonna non contiene errori o inconsistenze, è possibile specificare la corrispondenza esatta su tale colonna per aumentare la precisione della corrispondenza fuzzy su altre colonne.</span><span class="sxs-lookup"><span data-stu-id="877ea-126">Therefore, if you know that a certain column contains no errors or inconsistencies, you can specify exact matching on that column to increase the accuracy of the fuzzy matching on other columns.</span></span>  
  
 <span data-ttu-id="877ea-127">**Somiglianza minima**</span><span class="sxs-lookup"><span data-stu-id="877ea-127">**Minimum Similarity**</span></span>  
 <span data-ttu-id="877ea-128">Consente di impostare la soglia di somiglianza minima a livello di join tramite un dispositivo di scorrimento.</span><span class="sxs-lookup"><span data-stu-id="877ea-128">Set the similarity threshold at the join level by using the slider.</span></span> <span data-ttu-id="877ea-129">Più il valore è vicino a 1, maggiore deve essere la somiglianza tra il valore di ricerca e il valore di origine per essere considerata una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="877ea-129">The closer the value is to 1, the closer the resemblance of the lookup value to the source value must be to qualify as a match.</span></span> <span data-ttu-id="877ea-130">L'aumento della soglia può migliorare la velocità di confronto, poiché verrà considerato un numero minore di record candidati.</span><span class="sxs-lookup"><span data-stu-id="877ea-130">Increasing the threshold can improve the speed of matching since fewer candidate records need to be considered.</span></span>  
  
 <span data-ttu-id="877ea-131">**Alias di output somiglianza**</span><span class="sxs-lookup"><span data-stu-id="877ea-131">**Similarity Output Alias**</span></span>  
 <span data-ttu-id="877ea-132">Consente di specificare il nome di una nuova colonna di output contenente i punteggi di somiglianza per il join selezionato.</span><span class="sxs-lookup"><span data-stu-id="877ea-132">Specify the name for a new output column that contains the similarity scores for the selected join.</span></span> <span data-ttu-id="877ea-133">Se non si specifica un valore, la colonna di output non viene creata.</span><span class="sxs-lookup"><span data-stu-id="877ea-133">If you leave this value empty, the output column is not created.</span></span>  
  
 <span data-ttu-id="877ea-134">**Numerali**</span><span class="sxs-lookup"><span data-stu-id="877ea-134">**Numerals**</span></span>  
 <span data-ttu-id="877ea-135">Consente di specificare l'importanza dei numerali iniziali e finali nel confronto dei dati della colonna.</span><span class="sxs-lookup"><span data-stu-id="877ea-135">Specify the significance of leading and trailing numerals in comparing the column data.</span></span> <span data-ttu-id="877ea-136">Ad esempio, se i numerali iniziali sono significativi, "2005 Vendite" non verrà raggruppato con "2004 Vendite".</span><span class="sxs-lookup"><span data-stu-id="877ea-136">For example, if leading numerals are significant, "123 Main Street" will not be grouped with "456 Main Street."</span></span>  
  
|<span data-ttu-id="877ea-137">Valore</span><span class="sxs-lookup"><span data-stu-id="877ea-137">Value</span></span>|<span data-ttu-id="877ea-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="877ea-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="877ea-139">**Nessuno**</span><span class="sxs-lookup"><span data-stu-id="877ea-139">**Neither**</span></span>|<span data-ttu-id="877ea-140">I numerali iniziali e finali non sono significativi.</span><span class="sxs-lookup"><span data-stu-id="877ea-140">Leading and trailing numerals are not significant.</span></span>|  
|<span data-ttu-id="877ea-141">**Leader**</span><span class="sxs-lookup"><span data-stu-id="877ea-141">**Leading**</span></span>|<span data-ttu-id="877ea-142">Sono significativi solo i numerali iniziali.</span><span class="sxs-lookup"><span data-stu-id="877ea-142">Only leading numerals are significant.</span></span>|  
|<span data-ttu-id="877ea-143">**Finali**</span><span class="sxs-lookup"><span data-stu-id="877ea-143">**Trailing**</span></span>|<span data-ttu-id="877ea-144">Sono significativi solo i numerali finali.</span><span class="sxs-lookup"><span data-stu-id="877ea-144">Only trailing numerals are significant.</span></span>|  
|<span data-ttu-id="877ea-145">**Iniziali e finali**</span><span class="sxs-lookup"><span data-stu-id="877ea-145">**LeadingAndTrailing**</span></span>|<span data-ttu-id="877ea-146">Sono significativi i numerali sia iniziali che finali.</span><span class="sxs-lookup"><span data-stu-id="877ea-146">Both leading and trailing numerals are significant.</span></span>|  
  
 <span data-ttu-id="877ea-147">**Flag di confronto**</span><span class="sxs-lookup"><span data-stu-id="877ea-147">**Comparison Flags**</span></span>  
 <span data-ttu-id="877ea-148">Per altre informazioni sulle opzioni per il confronto di stringhe, vedere [Confronto di dati stringa](data-flow/comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="877ea-148">For information about the string comparison options, see [Comparing String Data](data-flow/comparing-string-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="877ea-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="877ea-149">See Also</span></span>  
 <span data-ttu-id="877ea-150">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="877ea-150">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="877ea-151">Identificazione di righe di dati simili tramite la trasformazione Raggruppamento fuzzy</span><span class="sxs-lookup"><span data-stu-id="877ea-151">Identify Similar Data Rows by Using the Fuzzy Grouping Transformation</span></span>](data-flow/transformations/identify-similar-data-rows-by-using-the-fuzzy-grouping-transformation.md)  
  
  
