---
title: Creazione di una dimensione di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], dimensions
ms.assetid: 9f0c39e5-3516-43ab-b203-f3f6dbcff89a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 265cf671bbc825258f0b2bd6627690e8c52f252b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711155"
---
# <a name="create-a-data-mining-dimension"></a><span data-ttu-id="7b7f3-102">Creare una dimensione di data mining</span><span class="sxs-lookup"><span data-stu-id="7b7f3-102">Create a Data Mining Dimension</span></span>
  <span data-ttu-id="7b7f3-103">Se la struttura di data mining è basata su un cubo OLAP, è possibile creare una dimensione che includa il contenuto del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="7b7f3-103">If your mining structure is based on an OLAP cube, you can create a dimension that contains the content of the mining model.</span></span> <span data-ttu-id="7b7f3-104">È quindi possibile includere nuovamente la dimensione nel cubo di origine.</span><span class="sxs-lookup"><span data-stu-id="7b7f3-104">You can then incorporate the dimension back into the source cube.</span></span>  
  
 <span data-ttu-id="7b7f3-105">È inoltre possibile esplorare la dimensione, utilizzarla per esplorare i risultati del modello o eseguire una query sulla dimensione tramite MDX.</span><span class="sxs-lookup"><span data-stu-id="7b7f3-105">You can also browse the dimension, use it to explore the model results, or query the dimension using MDX.</span></span>  
  
### <a name="to-create-a-data-mining-dimension"></a><span data-ttu-id="7b7f3-106">Per creare una dimensione di data mining</span><span class="sxs-lookup"><span data-stu-id="7b7f3-106">To create a data mining dimension</span></span>  
  
1.  <span data-ttu-id="7b7f3-107">In Progettazione modelli di data mining in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]selezionare la scheda **Struttura di data mining** o **Modelli di data mining** .</span><span class="sxs-lookup"><span data-stu-id="7b7f3-107">In Data Mining Designer in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], select either the **Mining Structure** tab or the **Mining Models** tab.</span></span>  
  
2.  <span data-ttu-id="7b7f3-108">Scegliere **Crea dimensione di data mining** dal menu **Modello di data mining**.</span><span class="sxs-lookup"><span data-stu-id="7b7f3-108">From the **Mining Model** menu, select **Create a Data Mining Dimension**.</span></span>  
  
     <span data-ttu-id="7b7f3-109">Verrà visualizzata la finestra di dialogo **Crea dimensione di data mining** .</span><span class="sxs-lookup"><span data-stu-id="7b7f3-109">The **Create Data Mining Dimension** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="7b7f3-110">Nell'elenco **Nome modello** della finestra di dialogo **Crea dimensione di data mining** selezionare un modello di data mining OLAP.</span><span class="sxs-lookup"><span data-stu-id="7b7f3-110">In the **Model name** list of the **Create Data Mining Dimension** dialog box, select an OLAP mining model.</span></span>  
  
4.  <span data-ttu-id="7b7f3-111">Nella casella **Nome dimensione** immettere un nome per la nuova dimensione di data mining.</span><span class="sxs-lookup"><span data-stu-id="7b7f3-111">In the **Dimension name** box, enter a name for the new data mining dimension.</span></span>  
  
5.  <span data-ttu-id="7b7f3-112">Per creare un cubo che includa la nuova dimensione di data mining, selezionare **Crea cubo**.</span><span class="sxs-lookup"><span data-stu-id="7b7f3-112">If you want to create a cube that includes the new data mining dimension, select **Create cube**.</span></span> <span data-ttu-id="7b7f3-113">Dopo avere fatto clic su **Crea cubo**, è possibile immettere un nuovo nome per il cubo.</span><span class="sxs-lookup"><span data-stu-id="7b7f3-113">After you select **Create cube**, you can enter a new name for the cube.</span></span>  
  
6.  <span data-ttu-id="7b7f3-114">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7b7f3-114">Click **OK**.</span></span>  
  
     <span data-ttu-id="7b7f3-115">La dimensione di data mining verrà creata e aggiunta alla cartella **Dimensioni** in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="7b7f3-115">The data mining dimension is created and is added to the **Dimensions** folder in Solution Explorer.</span></span> <span data-ttu-id="7b7f3-116">Se è stata selezionata l'opzione **Crea cubo**verrà anche creato un nuovo cubo, che verrà aggiunto alla cartella **Cubi** .</span><span class="sxs-lookup"><span data-stu-id="7b7f3-116">If you selected **Create cube**, a new cube is also created and is added to the **Cubes** folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b7f3-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b7f3-117">See Also</span></span>  
 [<span data-ttu-id="7b7f3-118">Attività e procedure relative alla struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="7b7f3-118">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
