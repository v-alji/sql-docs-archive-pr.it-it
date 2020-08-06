---
title: Rinominare una tabella o una colonna (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.renametableorcolumn.f1
ms.assetid: 88061a39-c5aa-403d-a52b-7fdb365fc235
author: minewiskan
ms.author: owend
ms.openlocfilehash: d3a2e9a9f41434e64f9ec5ea2180861b459e8f97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723120"
---
# <a name="rename-a-table-or-column-ssas-tabular"></a><span data-ttu-id="21e60-102">Rinominare una tabella o una colonna (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="21e60-102">Rename a Table or Column (SSAS Tabular)</span></span>
  <span data-ttu-id="21e60-103">È possibile modificare il nome di una tabella durante il processo di importazione digitando un **Nome descrittivo** nella pagina **Selezione tabelle e viste** dell' **Importazione guidata tabella**.</span><span class="sxs-lookup"><span data-stu-id="21e60-103">You can change the name of a table during the import process by typing a **Friendly Name** in the **Select Tables and Views** page of the **Table Import Wizard**.</span></span> <span data-ttu-id="21e60-104">È possibile modificare anche i nomi di tabelle e colonne se si importano dati specificando una query nella pagina **Specifica di una query SQL** dell' **Importazione guidata tabella**.</span><span class="sxs-lookup"><span data-stu-id="21e60-104">You can also change table and column names if you import data by specifying a query on the **Specify a SQL Query** page of the **Table Import Wizard**.</span></span>  
  
 <span data-ttu-id="21e60-105">Dopo aver aggiunto i dati al modello, il nome o titolo di una tabella viene visualizzato nella scheda della tabella nella parte inferiore di Progettazione modelli.</span><span class="sxs-lookup"><span data-stu-id="21e60-105">After you have added the data to the model, the name (or title) of a table appears on the table tab, at the bottom of the model designer.</span></span> <span data-ttu-id="21e60-106">È possibile modificare il nome della tabella al fine di assegnarne uno più appropriato.</span><span class="sxs-lookup"><span data-stu-id="21e60-106">You can change the name of your table to give it a more appropriate name.</span></span> <span data-ttu-id="21e60-107">È possibile anche rinominare una colonna dopo l'aggiunta dei dati al modello.</span><span class="sxs-lookup"><span data-stu-id="21e60-107">You can also rename a column after the data has been added to the model.</span></span> <span data-ttu-id="21e60-108">Questa opzione risulta particolarmente importante quando si importano dati da più origini e si vuole essere sicuri che le colonne nelle differenti tabelle abbiano nomi facilmente distinguibili.</span><span class="sxs-lookup"><span data-stu-id="21e60-108">This option is especially important when you have imported data from multiple sources, and want to ensure that columns in different tables have names that are easy to distinguish.</span></span>  
  
### <a name="to-rename-a-table"></a><span data-ttu-id="21e60-109">Per rinominare una tabella</span><span class="sxs-lookup"><span data-stu-id="21e60-109">To rename a table</span></span>  
  
1.  <span data-ttu-id="21e60-110">In Progettazione modelli fare clic con il pulsante destro del mouse sulla scheda contenente la tabella da rinominare, quindi scegliere **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="21e60-110">In the model designer, right-click the tab that contains the table that you want to rename, and then click **Rename**.</span></span>  
  
2.  <span data-ttu-id="21e60-111">Digitare il nuovo nome.</span><span class="sxs-lookup"><span data-stu-id="21e60-111">Type the new name.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="21e60-112">È possibile modificare altre proprietà di una tabella, incluse le informazioni di connessione e i mapping di colonne, tramite la finestra di dialogo **Modifica proprietà tabella** .</span><span class="sxs-lookup"><span data-stu-id="21e60-112">You can edit other properties of a table, including the connection information and column mappings, by using the **Edit Table Properties** dialog box.</span></span> <span data-ttu-id="21e60-113">Tuttavia, in questa finestra non è possibile modificare il nome.</span><span class="sxs-lookup"><span data-stu-id="21e60-113">However, you cannot change the name in this dialog box.</span></span>  
  
### <a name="to-rename-a-column"></a><span data-ttu-id="21e60-114">Per rinominare una colonna</span><span class="sxs-lookup"><span data-stu-id="21e60-114">To rename a column</span></span>  
  
1.  <span data-ttu-id="21e60-115">In Progettazione modelli fare doppio clic sull'intestazione della colonna da rinominare o fare clic con il pulsante destro del mouse e selezionare **Rinomina colonna** nel menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="21e60-115">In the model designer, double-click the header of the column that you want to rename, or right-click the header and select **Rename Column** from the context menu.</span></span>  
  
2.  <span data-ttu-id="21e60-116">Digitare il nuovo nome.</span><span class="sxs-lookup"><span data-stu-id="21e60-116">Type the new name.</span></span>  
  
## <a name="naming-requirements-for-columns-and-tables"></a><span data-ttu-id="21e60-117">Requisiti di denominazione per colonne e tabelle</span><span class="sxs-lookup"><span data-stu-id="21e60-117">Naming Requirements for Columns and Tables</span></span>  
 <span data-ttu-id="21e60-118">Nel nome di una tabella o di una colonna non è possibile utilizzare le parole e i caratteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="21e60-118">The following words and characters cannot be used in the name of a table or column:</span></span>  
  
-   <span data-ttu-id="21e60-119">Spazi iniziali o finali</span><span class="sxs-lookup"><span data-stu-id="21e60-119">Leading or trailing spaces</span></span>  
  
-   <span data-ttu-id="21e60-120">Caratteri di controllo</span><span class="sxs-lookup"><span data-stu-id="21e60-120">Control characters</span></span>  
  
-   <span data-ttu-id="21e60-121">I caratteri seguenti (che non sono validi nei nomi degli oggetti Analysis Services):.,;':/ \\ \*|? &% $! + = () [] {}<></span><span class="sxs-lookup"><span data-stu-id="21e60-121">The following characters (which are not valid in the names of Analysis Services objects): .,;':/\\*|?&%$!+=()[]{}<></span></span>  
  
-   <span data-ttu-id="21e60-122">Le parole chiave riservate di Analysis Services, inclusi i nomi delle funzioni e gli operatori MDX (Multidimensional Expressions) e DMX (Data Mining Extensions).</span><span class="sxs-lookup"><span data-stu-id="21e60-122">Analysis Services reserved keywords, including Multidimensional Expressions (MDX) and Data Mining Extensions (DMX) function names and operators.</span></span>  
  
## <a name="effect-of-renaming-on-existing-tables-columns-and-calculations"></a><span data-ttu-id="21e60-123">Effetto della ridenominazione su tabelle, colonne e calcoli esistenti</span><span class="sxs-lookup"><span data-stu-id="21e60-123">Effect of Renaming on Existing Tables, Columns, and Calculations</span></span>  
 <span data-ttu-id="21e60-124">Modificando il nome di una tabella, si modifica il nome dell'oggetto tabella sottostante, che può contenere più colonne o misure.</span><span class="sxs-lookup"><span data-stu-id="21e60-124">Whenever you change the name of a table, you change the name of the underlying table object, which may contain multiple columns or measures.</span></span> <span data-ttu-id="21e60-125">È pertanto necessario aggiornare tutte le colonne presenti nella tabella, nonché tutte le relazioni che coinvolgono la tabella, in modo che utilizzino il nuovo nome nelle relative definizioni.</span><span class="sxs-lookup"><span data-stu-id="21e60-125">Therefore, any columns that are in the table, and any relationships that use the table, must be updated to use the new name in their definitions.</span></span> <span data-ttu-id="21e60-126">Tale aggiornamento viene eseguito automaticamente in alcuni casi.</span><span class="sxs-lookup"><span data-stu-id="21e60-126">This update happens automatically in some cases.</span></span> <span data-ttu-id="21e60-127">Le misure non sono aggiornate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="21e60-127">Measures are not updated automatically.</span></span>  
  
 <span data-ttu-id="21e60-128">È necessario aggiornare inoltre tutti i calcoli che utilizzano la tabella rinominata o le relative colonne, nonché i dati da essi derivati, che devono essere ricalcolati.</span><span class="sxs-lookup"><span data-stu-id="21e60-128">Moreover, any calculations that use the renamed table, or that use columns from the renamed table, must also be updated, and the data derived from those calculations must be refreshed and recalculated.</span></span> <span data-ttu-id="21e60-129">A seconda del numero di tabelle e di calcoli interessati, l'operazione può richiedere del tempo prima di essere completata.</span><span class="sxs-lookup"><span data-stu-id="21e60-129">Depending on how many tables and calculations are affected, this can take some time to complete.</span></span> <span data-ttu-id="21e60-130">Il momento migliore per rinominare le tabelle ricade pertanto nell'arco del processo di importazione o prima dell'inizio della compilazione di relazioni e calcoli complessi.</span><span class="sxs-lookup"><span data-stu-id="21e60-130">Therefore, the best time to rename tables is either during the import process, or before you start to build complex relationships and calculations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21e60-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21e60-131">See Also</span></span>  
 <span data-ttu-id="21e60-132">[Tabelle e colonne &#40;SSAS tabulare&#41;](tables-and-columns-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="21e60-132">[Tables and Columns &#40;SSAS Tabular&#41;](tables-and-columns-ssas-tabular.md) </span></span>  
 <span data-ttu-id="21e60-133">[Importazione da PowerPivot &#40;SSAS tabulare&#41;](import-from-power-pivot-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="21e60-133">[Import from PowerPivot &#40;SSAS Tabular&#41;](import-from-power-pivot-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="21e60-134">Importare da Analysis Services &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="21e60-134">Import from Analysis Services &#40;SSAS Tabular&#41;</span></span>](import-from-analysis-services-ssas-tabular.md)  
  
  
