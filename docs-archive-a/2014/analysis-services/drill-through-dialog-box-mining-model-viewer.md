---
title: Finestra di dialogo Drill-through (Visualizzatore modello di data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.drillthrough.f1
ms.assetid: 42b78399-143d-4f44-90e0-b545ffb79e10
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1b00c62017de5a26c4507a04aeaf59aba7522146
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636458"
---
# <a name="drill-through-dialog-box-mining-model-viewer"></a><span data-ttu-id="b7002-102">Finestra di dialogo Drill-through (Visualizzatore modello di data mining)</span><span class="sxs-lookup"><span data-stu-id="b7002-102">Drill Through Dialog Box (Mining Model Viewer)</span></span>
  <span data-ttu-id="b7002-103">Quando si visualizza un modello di data mining tramite la scheda **Visualizzatore modello di data mining** di Progettazione modelli di data mining, è possibile eseguire il drill through ai dettagli dei dati del case, purché nel modello sia abilitato il drill-through.</span><span class="sxs-lookup"><span data-stu-id="b7002-103">When you view a mining model by using the **Mining Model Viewer** tab of Data Mining Designer, you can drill through into details about the case data, provided the model has drillthrough enabled.</span></span> <span data-ttu-id="b7002-104">Inoltre se nella struttura di data mining sottostante è abilitato il drill-through, è anche possibile visualizzare colonne non incluse nel modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="b7002-104">Moreover, if the underlying mining structure has drillthrough enabled, you can also see columns in the mining structure, even if those columns were not included in the mining model.</span></span> <span data-ttu-id="b7002-105">Nell'elenco delle colonne, le colonne della struttura sono precedute dall'etichetta "Structure."</span><span class="sxs-lookup"><span data-stu-id="b7002-105">In the column list, the structure columns are prefixed by the "Structure."</span></span> <span data-ttu-id="b7002-106">etichetta.</span><span class="sxs-lookup"><span data-stu-id="b7002-106">label.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7002-107">Non è possibile abilitare il drill-through in una struttura di data mining esistente.</span><span class="sxs-lookup"><span data-stu-id="b7002-107">You cannot enable drillthrough on an existing mining structure.</span></span> <span data-ttu-id="b7002-108">È invece necessario ricreare la struttura di data mining e abilitare il drill-through durante il processo di creazione.</span><span class="sxs-lookup"><span data-stu-id="b7002-108">Instead, you must re-create the mining structure and enable drillthrough during the creation process.</span></span>  
  
 <span data-ttu-id="b7002-109">Per informazioni sull'accesso ai dati del case da ogni visualizzatore del modello di data mining che supporta il drill-through, **vedere** [Eseguire il drill-through sui dati del case da un modello di data mining](data-mining/drill-through-to-case-data-from-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="b7002-109">For information about how to access case data from each of the mining model viewers that support drillthrough, **see** [Drill Through to Case Data from a Mining Model](data-mining/drill-through-to-case-data-from-a-mining-model.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="b7002-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b7002-110">Options</span></span>  
 <span data-ttu-id="b7002-111">**Case classificati in**</span><span class="sxs-lookup"><span data-stu-id="b7002-111">**Cases Classified To**</span></span>  
 <span data-ttu-id="b7002-112">Viene visualizzata la definizione della regola, del set di elementi e del cluster contenuti nel nodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="b7002-112">Displays the definition of the rule, itemset, and cluster that are contained in the selected node.</span></span>  
  
 <span data-ttu-id="b7002-113">**Elenco colonne**</span><span class="sxs-lookup"><span data-stu-id="b7002-113">**Column list**</span></span>  
 <span data-ttu-id="b7002-114">Visualizza le colonne contenute nel modello, seguite dalle colonne della struttura.</span><span class="sxs-lookup"><span data-stu-id="b7002-114">Displays the columns in the model, followed by the structure columns.</span></span>  
  
 <span data-ttu-id="b7002-115">**Nota** Le colonne della struttura sono visualizzate solo se nella struttura di data mining è abilitato il drill-through e viene selezionata l'opzione **Colonne struttura e modello**.</span><span class="sxs-lookup"><span data-stu-id="b7002-115">**Note** Structure columns are displayed only if drillthrough is enabled on the mining structure, and if you selected the option, **Model and Structure Columns**.</span></span> <span data-ttu-id="b7002-116">Per visualizzare le colonne è inoltre necessario disporre delle autorizzazioni drill-through per il modello di data mining e per la struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="b7002-116">Moreover, you must have drillthrough permissions on both the mining model and the mining structure to view the columns.</span></span>  
  
 <span data-ttu-id="b7002-117">Le colonne della struttura non incluse nel modello vengono visualizzate come \*\*struttura. \<column name> \*\*</span><span class="sxs-lookup"><span data-stu-id="b7002-117">Structure columns that are not included in the model appear as **Structure.\<column name>**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7002-118">È possibile fare clic con il pulsante destro del mouse in un punto della griglia di colonne e selezionare **Copia tutto** per copiare negli Appunti i dati drill-through in formato delimitato da tabulazione.</span><span class="sxs-lookup"><span data-stu-id="b7002-118">You can right-click anywhere in the column grid and select **Copy All** to copy the drillthrough data, in tab-delimited format, to the Clipboard.</span></span> <span data-ttu-id="b7002-119">Nei dati copiati sono inclusi solo i dati dei case, non la definizione del nodo.</span><span class="sxs-lookup"><span data-stu-id="b7002-119">The copied data includes only the case data, not the node definition.</span></span>  
  
 <span data-ttu-id="b7002-120">**Esegui**</span><span class="sxs-lookup"><span data-stu-id="b7002-120">**Play**</span></span>  
 <span data-ttu-id="b7002-121">Fare clic sul pulsante con la freccia verde per aggiornare i dati.</span><span class="sxs-lookup"><span data-stu-id="b7002-121">Click the green arrow button to refresh the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7002-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7002-122">See Also</span></span>  
 <span data-ttu-id="b7002-123">[Query drill-through &#40;&#41;di data mining](data-mining/drillthrough-queries-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="b7002-123">[Drillthrough Queries &#40;Data Mining&#41;](data-mining/drillthrough-queries-data-mining.md) </span></span>  
 <span data-ttu-id="b7002-124">[Visualizzatori modello di data mining &#40;Progettazione modelli di data mining&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="b7002-124">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="b7002-125">Attività e procedure relative al visualizzatore modello di data mining</span><span class="sxs-lookup"><span data-stu-id="b7002-125">Mining Model Viewer Tasks and How-tos</span></span>](data-mining/mining-model-viewer-tasks-and-how-tos.md)  
  
  
