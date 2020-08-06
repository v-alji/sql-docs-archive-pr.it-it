---
title: Finestra Risultati spaziali
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c2d5a477-6496-4d01-adee-7322ebdfadf3
author: rothja
ms.author: jroth
ms.openlocfilehash: 5e018ec9f016dfc51ed1bb055ba94abf12bc878f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726864"
---
# <a name="spatial-results-window"></a><span data-ttu-id="f6f21-102">Finestra Risultati spaziali</span><span class="sxs-lookup"><span data-stu-id="f6f21-102">Spatial Results Window</span></span>
  <span data-ttu-id="f6f21-103">La finestra **Risultati spaziali** fornisce strumenti di mapping visivo per la visualizzazione di dati spaziali.</span><span class="sxs-lookup"><span data-stu-id="f6f21-103">The **Spatial results** window provides visual mapping tools for viewing spatial data.</span></span> <span data-ttu-id="f6f21-104">Per visualizzare i risultati spaziali, è necessario che i risultati delle query contengano una colonna spaziale con dati geometrici o geografici.</span><span class="sxs-lookup"><span data-stu-id="f6f21-104">To view spatial results, your query results must include a spatial column with either geometry or geography data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f6f21-105">La finestra **Risultati spaziali** è disponibile solo se i risultati vengono restituiti in una griglia nella finestra **Risultati** .</span><span class="sxs-lookup"><span data-stu-id="f6f21-105">The **Spatial results** window is only available if your results are returned to a grid in the **Results** window.</span></span> <span data-ttu-id="f6f21-106">Se si richiede invece la restituzione dei risultati come testo, tale finestra non sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="f6f21-106">If you specify that your results are returned as text, this window is not available.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f6f21-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="f6f21-107">Options</span></span>  
 <span data-ttu-id="f6f21-108">**Selezionare la colonna spaziale**</span><span class="sxs-lookup"><span data-stu-id="f6f21-108">**Select spatial column**</span></span>  
 <span data-ttu-id="f6f21-109">Consente di specificare la colonna che si desidera visualizzare tra le colonne spaziali nei risultati delle query.</span><span class="sxs-lookup"><span data-stu-id="f6f21-109">Specify the spatial column you want to view from the spatial columns in the query results.</span></span> <span data-ttu-id="f6f21-110">È possibile selezionare solo una colonna alla volta.</span><span class="sxs-lookup"><span data-stu-id="f6f21-110">Only one column can be selected at a time.</span></span>  
  
 <span data-ttu-id="f6f21-111">**Selezionare la colonna etichetta**</span><span class="sxs-lookup"><span data-stu-id="f6f21-111">**Select label column**</span></span>  
 <span data-ttu-id="f6f21-112">Consente di specificare la colonna non spaziale tra le colonne restituite nei risultati delle query per etichettare i dati spaziali.</span><span class="sxs-lookup"><span data-stu-id="f6f21-112">Specify the non-spatial column from the columns returned in the query results to label the spatial data.</span></span> <span data-ttu-id="f6f21-113">È possibile selezionare solo una colonna alla volta.</span><span class="sxs-lookup"><span data-stu-id="f6f21-113">Only one column can be selected at a time.</span></span>  
  
 <span data-ttu-id="f6f21-114">Questa opzione non è disponibile quando in una query vengono restituite solo istanze di punti.</span><span class="sxs-lookup"><span data-stu-id="f6f21-114">This option is not available when only point instances are returned in a query.</span></span>  
  
 <span data-ttu-id="f6f21-115">**Selezionare la proiezione**</span><span class="sxs-lookup"><span data-stu-id="f6f21-115">**Select projection**</span></span>  
 <span data-ttu-id="f6f21-116">Consente di visualizzare i dati geografici in quattro tipi di proiezione, ovvero Equirectangular, Mercator, Robinson e Bonne.</span><span class="sxs-lookup"><span data-stu-id="f6f21-116">Display geography data in one of four projections: Equirectangular, Mercator, Robinson, or Bonne.</span></span>  
  
 <span data-ttu-id="f6f21-117">Questa opzione non è disponibile per i dati geometrici.</span><span class="sxs-lookup"><span data-stu-id="f6f21-117">This option is not available for geometry data.</span></span>  
  
 <span data-ttu-id="f6f21-118">**Zoom**</span><span class="sxs-lookup"><span data-stu-id="f6f21-118">**Zoom**</span></span>  
 <span data-ttu-id="f6f21-119">Consente di regolare la visualizzazione del mapping in una scala esponenziale.</span><span class="sxs-lookup"><span data-stu-id="f6f21-119">Adjust the map display on an exponential scale.</span></span>  
  
 <span data-ttu-id="f6f21-120">**Mostra linee griglia**</span><span class="sxs-lookup"><span data-stu-id="f6f21-120">**Show grid lines**</span></span>  
 <span data-ttu-id="f6f21-121">Consente di attivare o disattivare le linee della griglia delle coordinate.</span><span class="sxs-lookup"><span data-stu-id="f6f21-121">Toggle coordinate gridlines on or off.</span></span>  
  
 <span data-ttu-id="f6f21-122">Per le forme poligonali, l'etichetta viene visualizzata solo se la forma è grande abbastanza da contenere il testo dell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="f6f21-122">For polygon shapes, the label is displayed only when the shape is large enough to hold the label text.</span></span> <span data-ttu-id="f6f21-123">Per visualizzare le etichette di forme di piccole dimensioni, regolare lo zoom.</span><span class="sxs-lookup"><span data-stu-id="f6f21-123">To display labels for small shapes, adjust the zoom.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f6f21-124">Non è possibile etichettare le istanze di punti.</span><span class="sxs-lookup"><span data-stu-id="f6f21-124">Point instances cannot be labeled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6f21-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6f21-125">See Also</span></span>  
 <span data-ttu-id="f6f21-126">[Visualizzazione di dati spaziali in Esplora oggetti](view-spatial-data-in-object-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="f6f21-126">[View Spatial Data in Object Explorer](view-spatial-data-in-object-explorer.md) </span></span>  
 <span data-ttu-id="f6f21-127">[Dati spaziali &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f6f21-127">[Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) </span></span>  
 <span data-ttu-id="f6f21-128">[Editor di query del motore di database &#40;SQL Server Management Studio&#41;](database-engine-query-editor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="f6f21-128">[Database Engine Query Editor &#40;SQL Server Management Studio&#41;](database-engine-query-editor-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="f6f21-129">Editor di query e di testo &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="f6f21-129">Query and Text Editors &#40;SQL Server Management Studio&#41;</span></span>](query-and-text-editors-sql-server-management-studio.md)  
  
  
