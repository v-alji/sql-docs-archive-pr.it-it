---
title: Ordinare i dati in una tabella (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 5fa6ad56-bf68-4aac-a226-52556173b7e2
author: minewiskan
ms.author: owend
ms.openlocfilehash: d9a6636c2c11fc571e8d4c1bcbc25c1e02d815fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711039"
---
# <a name="sort-data-in-a-table-ssas-tabular"></a><span data-ttu-id="74719-102">Ordinare i dati di una tabella (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="74719-102">Sort Data in a Table (SSAS Tabular)</span></span>
  <span data-ttu-id="74719-103">È possibile ordinare i dati per testo (da A a Z o da Z ad A) e numeri (dal più piccolo al più grande o dal più grande al più piccolo) in una o più colonne.</span><span class="sxs-lookup"><span data-stu-id="74719-103">You can sort data by text (A to Z or Z to A) and numbers (smallest to largest or largest to smallest) in one or more columns.</span></span>  
  
### <a name="to-sort-the-data-in-a-table-based-on-a-text-column"></a><span data-ttu-id="74719-104">Per ordinare i dati in una tabella basata su una colonna di testo</span><span class="sxs-lookup"><span data-stu-id="74719-104">To sort the data in a table based on a text column</span></span>  
  
1.  <span data-ttu-id="74719-105">In Progettazione modelli selezionare una colonna di dati alfanumerici, un intervallo di celle in una colonna oppure assicurarsi che la cella attiva si trovi in una colonna di una tabella contenente dati alfanumerici, quindi fare clic sulla freccia nell'intestazione della colonna in base alla quale filtrare i dati.</span><span class="sxs-lookup"><span data-stu-id="74719-105">In the model designer, select a column of alphanumeric data, a range of cells in a column, or make sure that the active cell is in a table column that contains alphanumeric data, and then click the arrow in the header of the column that you want to filter by.</span></span>  
  
2.  <span data-ttu-id="74719-106">Nel menu Filtro automatico effettuare uno dei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="74719-106">In the AutoFilter menu, do one of the following:</span></span>  
  
    -   <span data-ttu-id="74719-107">Per ordinare in ordine alfanumerico crescente, fare clic su **Ordina da A a Z**.</span><span class="sxs-lookup"><span data-stu-id="74719-107">To sort in ascending alphanumeric order, click **Sort A to Z**.</span></span>  
  
    -   <span data-ttu-id="74719-108">Per ordinare in ordine alfanumerico decrescente, fare clic su **Ordina da Z a A**.</span><span class="sxs-lookup"><span data-stu-id="74719-108">To sort in descending alphanumeric order, click **Sort Z to A**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="74719-109">In alcuni casi, dati importati da un'altra applicazione potrebbero presentare spazi iniziali inseriti prima dei dati stessi.</span><span class="sxs-lookup"><span data-stu-id="74719-109">In some cases, data imported from another application might have leading spaces inserted before data.</span></span> <span data-ttu-id="74719-110">È necessario rimuovere gli spazi iniziali per ordinare correttamente i dati.</span><span class="sxs-lookup"><span data-stu-id="74719-110">You must remove the leading spaces in order to correctly sort the data.</span></span>  
  
### <a name="to-sort-the-data-in-a-table-based-on-a-numeric-column"></a><span data-ttu-id="74719-111">Per ordinare i dati in una tabella basata su una colonna numerica</span><span class="sxs-lookup"><span data-stu-id="74719-111">To sort the data in a table based on a numeric column</span></span>  
  
1.  <span data-ttu-id="74719-112">In Progettazione modelli selezionare una colonna di dati alfanumerici, un intervallo di celle in una colonna oppure assicurarsi che la cella attiva si trovi in una colonna di una tabella contenente dati alfanumerici, quindi fare clic sulla freccia nell'intestazione della colonna in base alla quale filtrare i dati.</span><span class="sxs-lookup"><span data-stu-id="74719-112">In the model designer, select a column of alphanumeric data, a range of cells in a column, or make sure that the active cell is in a table column that contains alphanumeric data, and then click the arrow in the header of the column that you want to filter by.</span></span>  
  
2.  <span data-ttu-id="74719-113">Nel menu Filtro automatico effettuare uno dei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="74719-113">In the AutoFilter menu, do one of the following:</span></span>  
  
    -   <span data-ttu-id="74719-114">Per l'ordinamento ascendente fare clic su **Ordina dal più piccolo al più grande**.</span><span class="sxs-lookup"><span data-stu-id="74719-114">To sort from low numbers to high numbers, click **Sort Smallest to Largest**.</span></span>  
  
    -   <span data-ttu-id="74719-115">Per l'ordinamento discendente fare clic su **Ordina dal più grande al più piccolo**.</span><span class="sxs-lookup"><span data-stu-id="74719-115">To sort from high numbers to low numbers, click **Sort Largest to Smallest**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="74719-116">Se i risultati non sono quelli previsti, la colonna potrebbe contenere numeri archiviati come testo e non come numeri.</span><span class="sxs-lookup"><span data-stu-id="74719-116">If the results are not what you expected, the column might contain numbers stored as text and not as numbers.</span></span> <span data-ttu-id="74719-117">Ad esempio numeri negativi importati da alcuni sistemi di contabilità o un numero immesso con carattere apostrofo (') iniziale, vengono archiviati come testo.</span><span class="sxs-lookup"><span data-stu-id="74719-117">For example, negative numbers imported from some accounting systems, or a number entered with a leading ' (apostrophe), are stored as text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74719-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74719-118">See Also</span></span>  
 <span data-ttu-id="74719-119">[Filtrare e ordinare dati &#40;SSAS tabulare&#41;](../filter-and-sort-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="74719-119">[Filter and Sort Data &#40;SSAS Tabular&#41;](../filter-and-sort-data-ssas-tabular.md) </span></span>  
 <span data-ttu-id="74719-120">[Prospettive &#40;SSAS tabulare&#41;](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="74719-120">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="74719-121">Ruoli &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="74719-121">Roles &#40;SSAS Tabular&#41;</span></span>](roles-ssas-tabular.md)  
  
  
