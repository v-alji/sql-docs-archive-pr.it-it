---
title: Filtrare i dati in una tabella (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.customfilterdb.f1
- sql12.asvs.bidtoolset.autofiltermenu.f1
- sql12.asvs.bidtoolset.notallitemsshowing.f1
ms.assetid: 3223059d-f525-4835-bf88-ebc195d9dbdc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3f4003457df4068713e75e6bb5c0ab78c15ac03c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712519"
---
# <a name="filter-data-in-a-table-ssas-tabular"></a><span data-ttu-id="86a23-102">Filtrare i dati di una tabella (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="86a23-102">Filter Data in a Table (SSAS Tabular)</span></span>
  <span data-ttu-id="86a23-103">È possibile applicare filtri quando si importano dati per controllare le righe caricate in una tabella.</span><span class="sxs-lookup"><span data-stu-id="86a23-103">You can apply filters when you import data to control the rows that are loaded into a table.</span></span> <span data-ttu-id="86a23-104">Dopo aver importato i dati, non è possibile eliminare righe singole.</span><span class="sxs-lookup"><span data-stu-id="86a23-104">After you have imported the data, you cannot delete individual rows.</span></span> <span data-ttu-id="86a23-105">Tuttavia, è possibile applicare filtri personalizzati per controllare la modalità in cui visualizzare tali righe.</span><span class="sxs-lookup"><span data-stu-id="86a23-105">However, you can apply custom filters to control the way that rows are displayed.</span></span> <span data-ttu-id="86a23-106">Le righe che non soddisfano i criteri di filtro sono nascoste.</span><span class="sxs-lookup"><span data-stu-id="86a23-106">Rows that do not meet the filtering criteria are hidden.</span></span> <span data-ttu-id="86a23-107">È possibile filtrare i dati in base a una o più colonne.</span><span class="sxs-lookup"><span data-stu-id="86a23-107">You can filter by one or more columns.</span></span> <span data-ttu-id="86a23-108">I filtri sono additivi, pertanto ciascun filtro aggiuntivo è basato sul filtro corrente e consente di ridurre ulteriormente il subset di dati.</span><span class="sxs-lookup"><span data-stu-id="86a23-108">Filters are additive, which means that each additional filter is based on the current filter and further reduces the subset of data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="86a23-109">La finestra di anteprima del filtro consente di limitare il numero di valori diversi visualizzati.</span><span class="sxs-lookup"><span data-stu-id="86a23-109">The filter preview window limits the number of different values displayed.</span></span> <span data-ttu-id="86a23-110">Se il limite viene superato, viene visualizzato un messaggio.</span><span class="sxs-lookup"><span data-stu-id="86a23-110">If the limit is exceeded, a message is displayed.</span></span>  
  
### <a name="to-filter-data-based-on-column-values"></a><span data-ttu-id="86a23-111">Per filtrare dati in base ai valori della colonna</span><span class="sxs-lookup"><span data-stu-id="86a23-111">To filter data based on column values</span></span>  
  
1.  <span data-ttu-id="86a23-112">In Progettazione modelli selezionare una tabella, quindi fare clic sulla freccia nell'intestazione della colonna in base alla quale filtrare i dati.</span><span class="sxs-lookup"><span data-stu-id="86a23-112">In the model designer, select a table, and then click the arrow in the header of the column that you want to filter by.</span></span>  
  
2.  <span data-ttu-id="86a23-113">Nel menu Filtro automatico effettuare uno dei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="86a23-113">In the AutoFilter menu, do one of the following:</span></span>  
  
    -   <span data-ttu-id="86a23-114">Nell'elenco di valori delle colonne selezionare o deselezionare uno o più valori da utilizzare come filtri, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="86a23-114">In the list of column values, select or clear one or more values to filter by, and then click **OK**.</span></span>  
  
         <span data-ttu-id="86a23-115">Se il numero di valori è estremamente elevato, singoli elementi potrebbero non essere visualizzati nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="86a23-115">If the number of values is extremely large, individual items might not be shown in the list.</span></span> <span data-ttu-id="86a23-116">Verrà invece visualizzato il messaggio, "Troppi elementi da visualizzare".</span><span class="sxs-lookup"><span data-stu-id="86a23-116">Instead, you will see the message, "Too many items to show."</span></span>  
  
    -   <span data-ttu-id="86a23-117">Fare clic su **filtri per numeri** o **filtri per testo** (a seconda del tipo di colonna), quindi fare clic sui comandi dell'operatore di confronto (ad esempio **uguale**a) o su **filtro personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="86a23-117">Click **Number Filters** or **Text Filters** (depending on the type of column), and then clicke of the comparison operator commands (such as **Equals**), or click **Custom Filter**.</span></span> <span data-ttu-id="86a23-118">Nella finestra di dialogo **Filtro personalizzato** creare il filtro, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="86a23-118">In the **Custom Filter** dialog box, create the filter, and then click **OK**.</span></span>  
  
### <a name="to-clear-a-filter-for-a-column"></a><span data-ttu-id="86a23-119">Per cancellare un filtro per una colonna</span><span class="sxs-lookup"><span data-stu-id="86a23-119">To clear a filter for a column</span></span>  
  
1.  <span data-ttu-id="86a23-120">Fare clic sulla freccia nell'intestazione della colonna per la quale si desidera cancellare un filtro.</span><span class="sxs-lookup"><span data-stu-id="86a23-120">Click the arrow in the header of the column for which you want to clear a filter.</span></span>  
  
2.  <span data-ttu-id="86a23-121">Fare clic su \*\*Cancella \<Column Name> filtro da \*\*.</span><span class="sxs-lookup"><span data-stu-id="86a23-121">Click **Clear Filter from \<Column Name>**.</span></span>  
  
### <a name="to-clear-all-filters-for-a-table"></a><span data-ttu-id="86a23-122">Per cancellare tutti i filtri per una tabella</span><span class="sxs-lookup"><span data-stu-id="86a23-122">To clear all filters for a table</span></span>  
  
1.  <span data-ttu-id="86a23-123">In Progettazione modelli selezionare la tabella per la quale si desidera cancellare i filtri.</span><span class="sxs-lookup"><span data-stu-id="86a23-123">In the model designer, select the table for which you want to clear filters.</span></span>  
  
2.  <span data-ttu-id="86a23-124">Fare clic sul menu **Colonna** , quindi scegliere **Cancella tutti i filtri**.</span><span class="sxs-lookup"><span data-stu-id="86a23-124">Click on the **Column** menu, and then click **Clear All Filters**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86a23-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86a23-125">See Also</span></span>  
 <span data-ttu-id="86a23-126">[Filtrare e ordinare dati &#40;SSAS tabulare&#41;](../filter-and-sort-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="86a23-126">[Filter and Sort Data &#40;SSAS Tabular&#41;](../filter-and-sort-data-ssas-tabular.md) </span></span>  
 <span data-ttu-id="86a23-127">[Prospettive &#40;SSAS tabulare&#41;](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="86a23-127">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="86a23-128">Ruoli &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="86a23-128">Roles &#40;SSAS Tabular&#41;</span></span>](roles-ssas-tabular.md)  
  
  
