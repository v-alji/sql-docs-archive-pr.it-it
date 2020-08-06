---
title: Scheda matrice di classificazione (visualizzazione Grafico accuratezza modello di data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.accuracychart.confusionmatrix.f1
ms.assetid: 85d5a047-d656-41e0-8a31-400271c2a620
author: minewiskan
ms.author: owend
ms.openlocfilehash: d202d552b25095d0d0845ff64f9c0e289f7bba0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625779"
---
# <a name="classification-matrix-tab-mining-accuracy-chart-view"></a><span data-ttu-id="5ac73-102">Scheda Matrice di classificazione (visualizzazione Grafico accuratezza modello di data mining)</span><span class="sxs-lookup"><span data-stu-id="5ac73-102">Classification Matrix Tab (Mining Accuracy Chart View)</span></span>
  <span data-ttu-id="5ac73-103">Nella scheda **matrice di classificazione** viene visualizzata una matrice di classificazione per ogni modello selezionato nella griglia dei modelli nella scheda **Mapping colonne** . La matrice di classificazione è disponibile solo se la colonna stimabile selezionata nella scheda **Mapping colonne** non è continua.</span><span class="sxs-lookup"><span data-stu-id="5ac73-103">The **Classification Matrix** tab displays a classification matrix for each model selected in the models grid on the **Column Mapping** tab. The classification matrix is only available if the predictable column that is selected in the **Column Mapping** tab is not continuous.</span></span> <span data-ttu-id="5ac73-104">Per una descrizione più dettagliata della scheda **Matrice di classificazione** , vedere [Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="5ac73-104">For a more detailed description of the **Classification Matrix** tab, see [Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="5ac73-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="5ac73-105">Options</span></span>  
 <span data-ttu-id="5ac73-106">**Copia**</span><span class="sxs-lookup"><span data-stu-id="5ac73-106">**Copy**</span></span>  
 <span data-ttu-id="5ac73-107">Consente di copiare il contenuto di ogni matrice di classificazione negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="5ac73-107">Copies the content of each classification matrix to the clipboard.</span></span>  
  
 <span data-ttu-id="5ac73-108">**Conteggi per \<model> il\< predictable column>**</span><span class="sxs-lookup"><span data-stu-id="5ac73-108">**Counts for \<model> on \< predictable column>**</span></span>  
 <span data-ttu-id="5ac73-109">Visualizza una matrice di classificazione per ogni modello di data mining nella struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="5ac73-109">Displays a classification matrix for each mining model in the mining structure.</span></span> <span data-ttu-id="5ac73-110">La matrice contiene le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="5ac73-110">The matrix contains the following columns:</span></span>  
  
|<span data-ttu-id="5ac73-111">Valore</span><span class="sxs-lookup"><span data-stu-id="5ac73-111">Value</span></span>|<span data-ttu-id="5ac73-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5ac73-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5ac73-113">**Stimati**</span><span class="sxs-lookup"><span data-stu-id="5ac73-113">**Predicted**</span></span>|<span data-ttu-id="5ac73-114">Include una riga per ogni stato della colonna stimabile.</span><span class="sxs-lookup"><span data-stu-id="5ac73-114">Contains a row for each state of the predictable column.</span></span>|  
|<span data-ttu-id="5ac73-115">**\<states>reale**</span><span class="sxs-lookup"><span data-stu-id="5ac73-115">**\<states> (actual)**</span></span>|<span data-ttu-id="5ac73-116">Una colonna per ogni stato nella colonna stimabile.</span><span class="sxs-lookup"><span data-stu-id="5ac73-116">A column for each state in the predictable column.</span></span> <span data-ttu-id="5ac73-117">Se lo stato della riga e della colonna corrispondono, la cella rappresenta il numero effettivo di volte in cui lo stato si è verificato nel database.</span><span class="sxs-lookup"><span data-stu-id="5ac73-117">If the state of the row and the column correspond, the cell represents the actual number of times the state exists in the database.</span></span> <span data-ttu-id="5ac73-118">In caso contrario, la cella rappresenta l'errore della stima.</span><span class="sxs-lookup"><span data-stu-id="5ac73-118">If they do not correspond, the cell represents the error of the prediction.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5ac73-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ac73-119">See Also</span></span>  
 <span data-ttu-id="5ac73-120">[Progettazione Grafico accuratezza modello di data mining &#40;&#41;di data mining](mining-accuracy-chart-designer-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="5ac73-120">[Mining Accuracy Chart Designer &#40;Data Mining&#41;](mining-accuracy-chart-designer-data-mining.md) </span></span>  
 <span data-ttu-id="5ac73-121">[Attività e procedure di test e convalida &#40;di data mining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="5ac73-121">[Testing and Validation Tasks and How-tos &#40;Data Mining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span></span>  
 [<span data-ttu-id="5ac73-122">Test e convalida &#40;Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="5ac73-122">Testing and Validation &#40;Data Mining&#41;</span></span>](data-mining/testing-and-validation-data-mining.md)  
  
  
