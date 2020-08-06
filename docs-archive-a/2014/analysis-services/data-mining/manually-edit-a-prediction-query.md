---
title: Modificare manualmente una query di stima | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying prediction queries
- Mining Model Prediction [Analysis Services], modifying prediction queries
- manual prediction query modification [Analysis Services]
ms.assetid: 9f6a9298-49d5-4675-ad49-977a47dff5a6
author: minewiskan
ms.author: owend
ms.openlocfilehash: e887e935dafcd2428859fd959cb7bc64650c660d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638164"
---
# <a name="manually-edit-a-prediction-query"></a><span data-ttu-id="e556a-102">Modificare manualmente un query di stima</span><span class="sxs-lookup"><span data-stu-id="e556a-102">Manually Edit a Prediction Query</span></span>
  <span data-ttu-id="e556a-103">Dopo avere progettato una query tramite il generatore delle query di stima, è possibile modificarla passando alla visualizzazione Testo query nella scheda **Stima modello di data mining** di Progettazione modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="e556a-103">After you have designed a query by using the Prediction Query Builder, you can modify the query by switching to Query Text view on the **Mining Model Prediction** tab of Data Mining Designer.</span></span> <span data-ttu-id="e556a-104">Nella parte inferiore dello schermo viene visualizzato un editor di testo per visualizzare la query creata tramite il generatore delle query.</span><span class="sxs-lookup"><span data-stu-id="e556a-104">A text editor appears at the bottom of the screen to display the query that the query builder created.</span></span>  
  
 <span data-ttu-id="e556a-105">Il passaggio alla vista Testo della query è utile per effettuare aggiunte alla query.</span><span class="sxs-lookup"><span data-stu-id="e556a-105">Switching to Query Text view is useful for making additions to the query.</span></span> <span data-ttu-id="e556a-106">Ad esempio, è possibile aggiungere una clausola WHERE o ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="e556a-106">For example, you can add a WHERE clause or ORDER BY clause.</span></span>  
  
 <span data-ttu-id="e556a-107">Utilizzare la griglia nel generatore delle query di stima per inserire i nomi di oggetti e colonne e impostare la sintassi per le singole funzioni di stima, quindi passare alla modalità di modifica manuale per modificare i valori di parametro.</span><span class="sxs-lookup"><span data-stu-id="e556a-107">Use the grid in the Prediction Query Builder to insert the names of objects and columns and set up the syntax for individual prediction functions, and then switch to manual editing mode to change parameter values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e556a-108">Se si passa nuovamente alla vista **Progettazione** dalla vista **Testo query** , qualsiasi modifica apportata in **Testo query** andrà persa.</span><span class="sxs-lookup"><span data-stu-id="e556a-108">If you switch back to **Design** view from **Query Text** view, any changes that you made in **Query Text** view will be lost.</span></span>  
  
### <a name="modify-a-query"></a><span data-ttu-id="e556a-109">Modificare una query</span><span class="sxs-lookup"><span data-stu-id="e556a-109">Modify a query</span></span>  
  
1.  <span data-ttu-id="e556a-110">Nella scheda **Stima modello di data mining** di Progettazione modelli di data mining in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]fare clic su **SQL**.</span><span class="sxs-lookup"><span data-stu-id="e556a-110">On the **Mining Model Prediction** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click **SQL**.</span></span>  
  
     <span data-ttu-id="e556a-111">La griglia visualizzata nella parte inferiore dello schermo verrà sostituita da un editor di testo che include la query.</span><span class="sxs-lookup"><span data-stu-id="e556a-111">The grid at the bottom of the screen is replaced by a text editor that contains the query.</span></span> <span data-ttu-id="e556a-112">È possibile digitare le modifiche alla query nell'editor.</span><span class="sxs-lookup"><span data-stu-id="e556a-112">You can type changes to the query in this editor.</span></span>  
  
2.  <span data-ttu-id="e556a-113">Per eseguire la query, scegliere **Risultato** dal menu **Modello di data mining**o fare clic sul pulsante per passare ai risultati della query.</span><span class="sxs-lookup"><span data-stu-id="e556a-113">To run the query, on the **Mining Model** menu, select **Result**, or click the button to switch to query results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e556a-114">Se la query creata non è valida, nella finestra Risultati non verrà segnalato un errore e non verrà visualizzato alcun risultato.</span><span class="sxs-lookup"><span data-stu-id="e556a-114">If the query that you have created is invalid, the Results window does not display an error and does not display any results.</span></span> <span data-ttu-id="e556a-115">Fare clic sul pulsante **Progettazione** oppure scegliere **Progettazione** o **Query** dal menu **Modello di data mining** per correggere il problema ed eseguire nuovamente la query.</span><span class="sxs-lookup"><span data-stu-id="e556a-115">Click the **Design** button, or select **Design** or **Query** from the **Mining Model** menu to correct the problem and run the query again.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e556a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e556a-116">See Also</span></span>  
 <span data-ttu-id="e556a-117">[Query di data mining](data-mining-queries.md) </span><span class="sxs-lookup"><span data-stu-id="e556a-117">[Data Mining Queries](data-mining-queries.md) </span></span>  
 <span data-ttu-id="e556a-118">[Generatore di query di stima &#40;&#41;di data mining](../prediction-query-builder-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="e556a-118">[Prediction Query Builder &#40;Data Mining&#41;](../prediction-query-builder-data-mining.md) </span></span>  
 [<span data-ttu-id="e556a-119">Lezione 6: Creazione e utilizzo di stime &#40;Esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="e556a-119">Lesson 6: Creating and Working with Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../tutorials/lesson-6-creating-and-working-with-predictions-basic-data-mining-tutorial.md)  
  
  
