---
title: Visualizzazione di dati spaziali in Esplora oggetti
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 59cca562-e3f5-4257-b868-adcbcc0142cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 881adf69ee83ee4b7536afae0b190fbec90f132c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629327"
---
# <a name="view-spatial-data-in-object-explorer"></a><span data-ttu-id="3274b-102">Visualizzazione di dati spaziali in Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="3274b-102">View Spatial Data in Object Explorer</span></span>
  <span data-ttu-id="3274b-103">La finestra **Risultati spaziali** dell'editor di query fornisce strumenti di mapping visivo per la visualizzazione di risultati di dati spaziali in aggiunta alla visualizzazione dei dati in formato griglia nella finestra **Risultati** .</span><span class="sxs-lookup"><span data-stu-id="3274b-103">The **Spatial results** window in Query Editor provides visual mapping tools for viewing spatial data results in addition to the data displayed in grid format in the **Results** window.</span></span> <span data-ttu-id="3274b-104">Per visualizzare i dati spaziali nella finestra **Risultati spaziali** , i risultati delle query devono contenere almeno una colonna di dati spaziali con dati geometrici e geografici.</span><span class="sxs-lookup"><span data-stu-id="3274b-104">To display spatial data in the **Spatial Results** window, your query results must contain at least one spatial data column with either geometry or geography data.</span></span>  
  
### <a name="to-view-spatial-data-in-the-spatial-results-window"></a><span data-ttu-id="3274b-105">Per visualizzare i dati spaziali nella finestra Risultati spaziali</span><span class="sxs-lookup"><span data-stu-id="3274b-105">To view spatial data in the Spatial results window</span></span>  
  
1.  <span data-ttu-id="3274b-106">Nell'editor di query fare clic sulla scheda **Risultati spaziali** .</span><span class="sxs-lookup"><span data-stu-id="3274b-106">In Query Editor, click the **Spatial results** tab.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3274b-107">Questa finestra non è disponibile se i risultati delle query non contengono dati spaziali o si richiede la restituzione dei risultati come testo.</span><span class="sxs-lookup"><span data-stu-id="3274b-107">This window is not available if your query results do not contain spatial data or if you specify that your results are returned as text.</span></span>  
  
2.  <span data-ttu-id="3274b-108">Selezionare la colonna che si desidera visualizzare nell'elenco **Selezionare la colonna spaziale** .</span><span class="sxs-lookup"><span data-stu-id="3274b-108">Select the column you want to view from the **Select spatial column** list.</span></span> <span data-ttu-id="3274b-109">Se la tabella contiene una sola colonna spaziale, questa sarà l'opzione predefinita dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="3274b-109">If there is only one spatial column in your table, this column is the default option in the list.</span></span>  
  
3.  <span data-ttu-id="3274b-110">Selezionare la colonna non spaziale che si vuole usare come etichette dei dati nell'elenco **Selezionare la colonna etichetta** .</span><span class="sxs-lookup"><span data-stu-id="3274b-110">Select the non-spatial column you want to use as data labels from the **Select label columns** list.</span></span>  
  
4.  <span data-ttu-id="3274b-111">Selezionare la proiezione desiderata per i dati geografici nell'elenco **Selezionare la proiezione** .</span><span class="sxs-lookup"><span data-stu-id="3274b-111">Select the projection you want for geography data from the **Select projection** list.</span></span> <span data-ttu-id="3274b-112">La proiezione predefinita è Equirectangular. Le altre proiezioni disponibili sono Mercator, Robinson e Bonne.</span><span class="sxs-lookup"><span data-stu-id="3274b-112">The default projection is Equirectangular; other projections available are Mercator, Robinson, or Bonne.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3274b-113">**Selezionare la proiezione** non è disponibile se la colonna spaziale contiene dati geometrici.</span><span class="sxs-lookup"><span data-stu-id="3274b-113">**Select projection** is not available if your spatial column contains geometry data.</span></span>  
  
5.  <span data-ttu-id="3274b-114">Regolare il dispositivo di scorrimento **Zoom** per aumentare la dimensione visiva degli elementi di cui è stato eseguito il mapping.</span><span class="sxs-lookup"><span data-stu-id="3274b-114">Adjust the **Zoom** slider to increase the visual size of mapped elements.</span></span> <span data-ttu-id="3274b-115">Per le forme poligonali, l'etichetta è visibile solo se la forma è grande abbastanza da contenere il testo dell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="3274b-115">For polygon shapes, the label is visible only when the shape is large enough to hold the label text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3274b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3274b-116">See Also</span></span>  
 <span data-ttu-id="3274b-117">[Finestra Risultati spaziali](spatial-results-window.md) </span><span class="sxs-lookup"><span data-stu-id="3274b-117">[Spatial Results Window](spatial-results-window.md) </span></span>  
 <span data-ttu-id="3274b-118">[Editor di query del motore di database &#40;SQL Server Management Studio&#41;](database-engine-query-editor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="3274b-118">[Database Engine Query Editor &#40;SQL Server Management Studio&#41;](database-engine-query-editor-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="3274b-119">Editor di query e di testo &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3274b-119">Query and Text Editors &#40;SQL Server Management Studio&#41;</span></span>](query-and-text-editors-sql-server-management-studio.md)  
  
  
