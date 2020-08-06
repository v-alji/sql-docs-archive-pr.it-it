---
title: Creare una copia di un modello di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], copying
- mining models [Analysis Services], creating
- mining models [Analysis Services], how-to topics
- copying mining models
ms.assetid: 7975bb02-f188-49a0-b7de-5b9b216254ad
author: minewiskan
ms.author: owend
ms.openlocfilehash: a05eb75210ce9f601aeca515cd299f4204908705
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623608"
---
# <a name="make-a-copy-of-a-mining-model"></a><span data-ttu-id="4fcb3-102">Eseguire una copia di un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="4fcb3-102">Make a Copy of a Mining Model</span></span>
  <span data-ttu-id="4fcb3-103">La creazione di una copia di un modello di data mining risulta utile quando si desidera creare rapidamente diversi modelli di data mining basati sugli stessi dati.</span><span class="sxs-lookup"><span data-stu-id="4fcb3-103">Creating a copy of a mining model is useful when you want to quickly create several mining models that are based on the same data.</span></span> <span data-ttu-id="4fcb3-104">Dopo aver copiato il modello, è possibile modificare la nuova copia modificando i parametri o aggiungendo un filtro.</span><span class="sxs-lookup"><span data-stu-id="4fcb3-104">After you copy the model, you can then edit the new copy by changing parameters or adding a filter.</span></span>  
  
 <span data-ttu-id="4fcb3-105">Se ad esempio si dispone di una tabella Customers collegata a una tabella di acquisti, è possibile creare copie per generare modelli di data mining separati in base ai dati demografici di ogni cliente, filtrando in base ad attributi quali età o area geografica.</span><span class="sxs-lookup"><span data-stu-id="4fcb3-105">For example, if you have a Customers table that is linked to a table of purchases, you could create copies to generate separate mining models for each customer demographic, filtering on attributes such as age or region.</span></span>  
  
 <span data-ttu-id="4fcb3-106">Per informazioni sulla copia negli Appunti del contenuto del modello, ad esempio rappresentazione grafica o schemi del modello, per l'uso in altri programmi, vedere [Copiare una vista di un modello di data mining](copy-a-view-of-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="4fcb3-106">For information about how to copy the content of the model (such as the graphical representation or the model patterns) to the Clipboard for use in other programs, see [Copy a View of a Mining Model](copy-a-view-of-a-mining-model.md).</span></span>  
  
### <a name="to-create-a-related-mining-model"></a><span data-ttu-id="4fcb3-107">Per creare un modello di data mining correlato</span><span class="sxs-lookup"><span data-stu-id="4fcb3-107">To create a related mining model</span></span>  
  
1.  <span data-ttu-id="4fcb3-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in Esplora soluzioni, fare clic sulla struttura di data mining che contiene il modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="4fcb3-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in Solution Explorer, click the mining structure that contains the mining model.</span></span>  
  
2.  <span data-ttu-id="4fcb3-109">Fare clic sulla scheda **Modelli di data mining** .</span><span class="sxs-lookup"><span data-stu-id="4fcb3-109">Click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="4fcb3-110">Selezionare il modello, quindi fare clic con il pulsante destro del mouse per aprire il menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="4fcb3-110">Select the model, and right-click to open the shortcut menu.</span></span>  
  
     <span data-ttu-id="4fcb3-111">-oppure-</span><span class="sxs-lookup"><span data-stu-id="4fcb3-111">-or-</span></span>  
  
     <span data-ttu-id="4fcb3-112">Selezionare il modello.</span><span class="sxs-lookup"><span data-stu-id="4fcb3-112">Select the model.</span></span> <span data-ttu-id="4fcb3-113">Scegliere **Nuovo modello di data mining** dal menu **Modello di data mining**.</span><span class="sxs-lookup"><span data-stu-id="4fcb3-113">On the **Mining Model** menu, select **New Mining Model**.</span></span>  
  
4.  <span data-ttu-id="4fcb3-114">Digitare un nome per il nuovo modello di data mining e selezionare un algoritmo.</span><span class="sxs-lookup"><span data-stu-id="4fcb3-114">Type a name for the new mining model, and select an algorithm.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-edit-the-filter-on-the-copied-mining-model"></a><span data-ttu-id="4fcb3-115">Per modificare il filtro sul modello di data mining copiato</span><span class="sxs-lookup"><span data-stu-id="4fcb3-115">To edit the filter on the copied mining model</span></span>  
  
1.  <span data-ttu-id="4fcb3-116">Selezionare il modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="4fcb3-116">Select the mining model.</span></span>  
  
2.  <span data-ttu-id="4fcb3-117">Nella finestra **Proprietà** fare clic sulla casella di testo relativa alla proprietà **filtro** , quindi fare clic sul pulsante Compila **(...)** .</span><span class="sxs-lookup"><span data-stu-id="4fcb3-117">In the **Properties** window, click the text box for the **Filter** property, and the click the build **(...)** button.</span></span>  
  
3.  <span data-ttu-id="4fcb3-118">Cambiare le condizioni di filtro.</span><span class="sxs-lookup"><span data-stu-id="4fcb3-118">Change the filter conditions.</span></span>  
  
     <span data-ttu-id="4fcb3-119">Per altre informazioni sull'uso delle finestre di dialogo Editor filtri, vedere [Applicare un filtro a un modello di data mining](apply-a-filter-to-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="4fcb3-119">For more information about how to use the filter editor dialog boxes, see [Apply a Filter to a Mining Model](apply-a-filter-to-a-mining-model.md).</span></span>  
  
4.  <span data-ttu-id="4fcb3-120">Nella casella **Properties** di testo della finestra proprietà `AlgorithmParameters` fare clic su parametri per l' **algoritmo**e modificare i parametri dell'algoritmo, se lo si desidera.</span><span class="sxs-lookup"><span data-stu-id="4fcb3-120">In the **Properties** window, in the `AlgorithmParameters` text box, click **Setalgorithm parameters**, and change algorithm parameters, if desired.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4fcb3-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4fcb3-121">See Also</span></span>  
 <span data-ttu-id="4fcb3-122">[Filtri per i modelli di data mining &#40;Analysis Services-&#41;di data mining](mining-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="4fcb3-122">[Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](mining-models-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="4fcb3-123">[Attività e procedure relative al modello di data mining](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="4fcb3-123">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="4fcb3-124">Eliminare un filtro da un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="4fcb3-124">Delete a Filter from a Mining Model</span></span>](delete-a-filter-from-a-mining-model.md)  
  
  
