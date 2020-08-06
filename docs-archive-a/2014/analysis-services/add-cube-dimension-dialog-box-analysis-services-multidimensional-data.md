---
title: Finestra di dialogo Aggiungi dimensione al cubo (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.addcubedimensiondialog.f1
helpviewer_keywords:
- Add Cube Dimension dialog box
ms.assetid: 625a3b1f-183b-445f-9bb7-96945c324767
author: minewiskan
ms.author: owend
ms.openlocfilehash: d0de75c02c39b0690184f35f2b0b6a07d7ed9a4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625049"
---
# <a name="add-cube-dimension-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="88fe9-102">Finestra di dialogo Aggiungi dimensione al cubo (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="88fe9-102">Add Cube Dimension Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="88fe9-103">Utilizzare la finestra di dialogo **Aggiungi dimensione al cubo** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] per aggiungere a un cubo un riferimento a una dimensione del database.</span><span class="sxs-lookup"><span data-stu-id="88fe9-103">Use the **Add Cube Dimension** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to add a reference to a database dimension to a cube.</span></span> <span data-ttu-id="88fe9-104">Per visualizzare la finestra di dialogo **Aggiungi dimensione al cubo** è possibile eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="88fe9-104">You can display the **Add Cube Dimension** dialog box by doing one of the following:</span></span>  
  
-   <span data-ttu-id="88fe9-105">Fare clic su **Aggiungi dimensione al cubo** nel riquadro **Barra degli strumenti** della scheda **Struttura cubo** o **Utilizzo dimensioni** in Progettazione cubi.</span><span class="sxs-lookup"><span data-stu-id="88fe9-105">Click **Add Cube Dimension** in the **Toolbar** pane on the **Cube Structure** or **Dimension Usage** tab in Cube Designer.</span></span>  
  
-   <span data-ttu-id="88fe9-106">Fare clic con il pulsante destro del mouse nel riquadro **Dimensioni** della scheda **Struttura cubo** in Progettazione cubi e scegliere **Aggiungi dimensione al cubo** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="88fe9-106">Right-click the **Dimensions** pane on the **Cube Structure** tab in Cube Designer and select **Add Cube Dimension** from the context menu.</span></span>  
  
-   <span data-ttu-id="88fe9-107">Fare clic con il pulsante destro del mouse nel riquadro **Griglia** della scheda **Utilizzo dimensioni** in Progettazione cubi e scegliere **Aggiungi dimensione al cubo** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="88fe9-107">Right-click the **Grid** pane on the **Dimension Usage** tab in Cube Designer and select **Add Cube Dimension** from the context menu.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="88fe9-108">Ogni dimensione del cubo può avere solo una relazione con un gruppo di misure.</span><span class="sxs-lookup"><span data-stu-id="88fe9-108">Each cube dimension can have only one relationship to a measure group.</span></span> <span data-ttu-id="88fe9-109">È tuttavia possibile creare più dimensioni del cubo e aggiungerle al cubo, se la dimensione del database su cui si basa la dimensione del cubo è correlata a gruppi di misure mediante più di una relazione nella vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="88fe9-109">However, you can create more than one cube dimension and add it to the cube, if the database dimension on which the cube dimension is based is related to measure groups through more than one relationship in the data source view.</span></span> <span data-ttu-id="88fe9-110">Tali dimensioni sono definite dimensioni con ruoli multipli e sono normalmente presenti nelle dimensioni temporali.</span><span class="sxs-lookup"><span data-stu-id="88fe9-110">Such dimensions are referred to as role-playing dimensions and commonly occur with time dimensions.</span></span>  
  
## <a name="options"></a><span data-ttu-id="88fe9-111">Opzioni</span><span class="sxs-lookup"><span data-stu-id="88fe9-111">Options</span></span>  
 <span data-ttu-id="88fe9-112">**Selezionare una dimensione**</span><span class="sxs-lookup"><span data-stu-id="88fe9-112">**Select dimension**</span></span>  
 <span data-ttu-id="88fe9-113">Consente di selezionare una dimensione del database esistente per aggiungere al cubo selezionato una dimensione del cubo basata su tale dimensione esistente.</span><span class="sxs-lookup"><span data-stu-id="88fe9-113">Select an existing database dimension to add a cube dimension based on it to the selected cube.</span></span> <span data-ttu-id="88fe9-114">È possibile definire più dimensioni del cubo dalla stessa dimensione del database.</span><span class="sxs-lookup"><span data-stu-id="88fe9-114">Multiple cube dimensions can be defined from the same database dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="88fe9-115">Se a un cubo vengono aggiunte più dimensioni del cubo basate sulla stessa dimensione del database, le dimensioni del cubo aggiuntive sono denominate dimensioni con ruoli multipli.</span><span class="sxs-lookup"><span data-stu-id="88fe9-115">If more than one cube dimension based on the same database dimension is added to a cube, the additional cube dimensions are called role-playing dimensions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88fe9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88fe9-116">See Also</span></span>  
 [<span data-ttu-id="88fe9-117">Finestre di progettazione e finestre di dialogo Analysis Services &#40;dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="88fe9-117">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
