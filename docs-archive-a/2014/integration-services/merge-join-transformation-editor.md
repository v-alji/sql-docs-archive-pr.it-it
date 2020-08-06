---
title: Editor trasformazione Merge join | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.mergejointransformation.f1
helpviewer_keywords:
- Merge Join Transformation Editor
ms.assetid: ac06f419-30b3-42aa-8b34-42000bec4285
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e0d15d1233c2e0ff836e9dbd17459e56c48183f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629910"
---
# <a name="merge-join-transformation-editor"></a><span data-ttu-id="ea8c8-102">Editor trasformazione Merge join</span><span class="sxs-lookup"><span data-stu-id="ea8c8-102">Merge Join Transformation Editor</span></span>
  <span data-ttu-id="ea8c8-103">Utilizzare la finestra di dialogo **Editor trasformazione Merge join** per specificare il tipo di join, le colonne di join e le colonne di output per l'unione di due input combinati tramite un join.</span><span class="sxs-lookup"><span data-stu-id="ea8c8-103">Use the **Merge Join Transformation Editor** dialog box to specify the join type, the join columns, and the output columns for merging two inputs combined by a join.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ea8c8-104">Per eseguire la trasformazione Merge join, è necessario che i relativi dati di input siano ordinati.</span><span class="sxs-lookup"><span data-stu-id="ea8c8-104">The Merge Join Transformation requires sorted data for its inputs.</span></span> <span data-ttu-id="ea8c8-105">Per altre informazioni su questo requisito importante, vedere [Ordinamento dei dati per le trasformazioni Unione e Merge Join](data-flow/transformations/sort-data-for-the-merge-and-merge-join-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="ea8c8-105">For more information about this important requirement, see [Sort Data for the Merge and Merge Join Transformations](data-flow/transformations/sort-data-for-the-merge-and-merge-join-transformations.md).</span></span>  
  
 <span data-ttu-id="ea8c8-106">Per ulteriori informazioni sulla trasformazione Merge Join, vedere [Merge Join Transformation](data-flow/transformations/merge-join-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="ea8c8-106">To learn more about the Merge Join transformation, see [Merge Join Transformation](data-flow/transformations/merge-join-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ea8c8-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="ea8c8-107">Options</span></span>  
 <span data-ttu-id="ea8c8-108">**Tipo di join**</span><span class="sxs-lookup"><span data-stu-id="ea8c8-108">**Join type**</span></span>  
 <span data-ttu-id="ea8c8-109">Consente di specificare se utilizzare un inner join, un outer join sinistro o un full join.</span><span class="sxs-lookup"><span data-stu-id="ea8c8-109">Specify whether you want to use an inner join, left outer join, or full join.</span></span>  
  
 <span data-ttu-id="ea8c8-110">**Inverti ordine input**</span><span class="sxs-lookup"><span data-stu-id="ea8c8-110">**Swap Inputs**</span></span>  
 <span data-ttu-id="ea8c8-111">Il pulsante **Inverti ordine input** consente di invertire l'ordine degli input.</span><span class="sxs-lookup"><span data-stu-id="ea8c8-111">Switch the order between inputs by using the **Swap Inputs** button.</span></span> <span data-ttu-id="ea8c8-112">Questa selezione può risultare utile in caso si scelga di utilizzare un outer join sinistro.</span><span class="sxs-lookup"><span data-stu-id="ea8c8-112">This selection may be useful with the Left outer join option.</span></span>  
  
 <span data-ttu-id="ea8c8-113">**Input**</span><span class="sxs-lookup"><span data-stu-id="ea8c8-113">**Input**</span></span>  
 <span data-ttu-id="ea8c8-114">Per ogni colonna che si desidera includere nell'output unito, è innanzitutto necessario procedere a una selezione nell'elenco degli input disponibili.</span><span class="sxs-lookup"><span data-stu-id="ea8c8-114">For each column that you want in the merged output, first select from the list of available inputs.</span></span>  
  
 <span data-ttu-id="ea8c8-115">Gli input vengono visualizzati in due tabelle separate.</span><span class="sxs-lookup"><span data-stu-id="ea8c8-115">Inputs are displayed in two separate tables.</span></span> <span data-ttu-id="ea8c8-116">Selezionare le colonne da includere nell'output.</span><span class="sxs-lookup"><span data-stu-id="ea8c8-116">Select columns to include in the output.</span></span> <span data-ttu-id="ea8c8-117">Trascinare le colonne per creare un join tra le tabelle.</span><span class="sxs-lookup"><span data-stu-id="ea8c8-117">Drag columns to create a join between the tables.</span></span> <span data-ttu-id="ea8c8-118">Per eliminare un join, selezionarlo e quindi premere CANC.</span><span class="sxs-lookup"><span data-stu-id="ea8c8-118">To delete a join, select it and then press the DELETE key.</span></span>  
  
 <span data-ttu-id="ea8c8-119">**Colonna di input**</span><span class="sxs-lookup"><span data-stu-id="ea8c8-119">**Input Column**</span></span>  
 <span data-ttu-id="ea8c8-120">Selezionare una colonna da includere nell'output unito dall'elenco delle colonne disponibili nell'input selezionato.</span><span class="sxs-lookup"><span data-stu-id="ea8c8-120">Select a column to include in the merged output from the list of available columns on the selected input.</span></span>  
  
 <span data-ttu-id="ea8c8-121">**Alias di output**</span><span class="sxs-lookup"><span data-stu-id="ea8c8-121">**Output Alias**</span></span>  
 <span data-ttu-id="ea8c8-122">Consente di digitare un alias per ogni colonna di output.</span><span class="sxs-lookup"><span data-stu-id="ea8c8-122">Type an alias for each output column.</span></span> <span data-ttu-id="ea8c8-123">Per impostazione predefinita viene suggerito il nome della colonna di input. È comunque possibile scegliere qualsiasi nome descrittivo univoco.</span><span class="sxs-lookup"><span data-stu-id="ea8c8-123">The default is the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea8c8-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea8c8-124">See Also</span></span>  
 <span data-ttu-id="ea8c8-125">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ea8c8-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="ea8c8-126">[Ordinare i dati per le trasformazioni Unione e merge join](data-flow/transformations/sort-data-for-the-merge-and-merge-join-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="ea8c8-126">[Sort Data for the Merge and Merge Join Transformations](data-flow/transformations/sort-data-for-the-merge-and-merge-join-transformations.md) </span></span>  
 <span data-ttu-id="ea8c8-127">[Estendere un set di dati tramite la trasformazione Merge join](data-flow/transformations/extend-a-dataset-by-using-the-merge-join-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="ea8c8-127">[Extend a Dataset by Using the Merge Join Transformation](data-flow/transformations/extend-a-dataset-by-using-the-merge-join-transformation.md) </span></span>  
 <span data-ttu-id="ea8c8-128">[Trasformazione Unione](data-flow/transformations/merge-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="ea8c8-128">[Merge Transformation](data-flow/transformations/merge-transformation.md) </span></span>  
 [<span data-ttu-id="ea8c8-129">Trasformazione Unione input multipli</span><span class="sxs-lookup"><span data-stu-id="ea8c8-129">Union All Transformation</span></span>](data-flow/transformations/union-all-transformation.md)  
  
  
