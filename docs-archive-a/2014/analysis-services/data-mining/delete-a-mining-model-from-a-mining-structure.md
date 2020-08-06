---
title: Eliminare un modello di data mining da una struttura di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], mining models
- deleting mining models
- removing mining models
- mining models [Analysis Services], deleting
ms.assetid: 9ab1506b-856e-4762-a663-5adf15ac71e3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 72c79dcdccf6225b8e75144f8b090dcab7506c10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636479"
---
# <a name="delete-a-mining-model-from-a-mining-structure"></a><span data-ttu-id="e5625-102">Eliminare un modello di data mining da una struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="e5625-102">Delete a Mining Model from a Mining Structure</span></span>
  <span data-ttu-id="e5625-103">È possibile eliminare i modelli di data mining usando Progettazione modelli di data mining, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]o istruzioni DMX.</span><span class="sxs-lookup"><span data-stu-id="e5625-103">You can delete mining models by using Data Mining Designer, by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], or by using DMX statements.</span></span>  
  
### <a name="delete-a-mining-model-using-sql-server-data-tools"></a><span data-ttu-id="e5625-104">Eliminare un modello di data mining utilizzando SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="e5625-104">Delete a mining model using SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="e5625-105">Selezionare la scheda **Modelli di data mining** in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5625-105">Select the **Mining Models** tab in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="e5625-106">Fare clic con il pulsante destro del mouse sul modello da eliminare e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="e5625-106">Right-click the model that you want to delete, and select **Delete**.</span></span>  
  
     <span data-ttu-id="e5625-107">Verrà visualizzata la finestra di dialogo **Elimina oggetti** .</span><span class="sxs-lookup"><span data-stu-id="e5625-107">The **Delete Objects** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="e5625-108">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5625-108">Click **OK**.</span></span>  
  
### <a name="delete-a-mining-model-using-sql-server-management-studio"></a><span data-ttu-id="e5625-109">Eliminare un modello di data mining utilizzando SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e5625-109">Delete a mining model using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="e5625-110">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]aprire il database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] contenente il modello.</span><span class="sxs-lookup"><span data-stu-id="e5625-110">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database that contains the model.</span></span>  
  
2.  <span data-ttu-id="e5625-111">Espandere **Strutture di data mining**e quindi espandere **Modelli di data mining**.</span><span class="sxs-lookup"><span data-stu-id="e5625-111">Expand **Mining Structures**, and then expand **Mining Models**.</span></span>  
  
3.  <span data-ttu-id="e5625-112">Fare clic con il pulsante destro del mouse sul modello che si vuole eliminare e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="e5625-112">Right-click the model you want to delete, and select **Delete**.</span></span>  
  
     <span data-ttu-id="e5625-113">L'eliminazione del modello non comporta l'eliminazione dei dati di training, ma solo dei metadati e degli schemi creati durante il training del modello.</span><span class="sxs-lookup"><span data-stu-id="e5625-113">Deleting the model does not delete the training data, only the metadata and any patterns created when you trained the model.</span></span>  
  
### <a name="delete-a-mining-model-using-dmx"></a><span data-ttu-id="e5625-114">Eliminare un modello di data mining tramite DMX</span><span class="sxs-lookup"><span data-stu-id="e5625-114">Delete a mining model using DMX</span></span>  
  
-   [<span data-ttu-id="e5625-115">DROP MINING MODEL &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="e5625-115">DROP MINING MODEL &#40;DMX&#41;</span></span>](/sql/dmx/drop-mining-model-dmx)  
  
## <a name="see-also"></a><span data-ttu-id="e5625-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5625-116">See Also</span></span>  
 [<span data-ttu-id="e5625-117">Attività e procedure relative al modello di data mining</span><span class="sxs-lookup"><span data-stu-id="e5625-117">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
