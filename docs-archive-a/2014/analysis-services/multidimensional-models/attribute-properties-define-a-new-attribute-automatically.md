---
title: Definire automaticamente un nuovo attributo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- automatic attribute creation
- attributes [Analysis Services], creating
ms.assetid: 208a050a-5e2f-470c-b645-8d835e123db7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 40f9ae1f00dd0a6520c6d1b06111864fba02e8f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725128"
---
# <a name="define-a-new-attribute-automatically"></a><span data-ttu-id="ea980-102">Definire automaticamente un nuovo attributo</span><span class="sxs-lookup"><span data-stu-id="ea980-102">Define a New Attribute Automatically</span></span>
  <span data-ttu-id="ea980-103">È possibile creare un nuovo attributo in una dimensione utilizzando la funzionalità di modifica tramite trascinamento in Progettazione dimensioni.</span><span class="sxs-lookup"><span data-stu-id="ea980-103">You can create a new attribute in a dimension by using drag-and-drop editing in the Dimension Designer.</span></span>  
  
### <a name="to-create-a-new-attribute-automatically"></a><span data-ttu-id="ea980-104">Per creare un nuovo attributo automaticamente</span><span class="sxs-lookup"><span data-stu-id="ea980-104">To create a new attribute automatically</span></span>  
  
1.  <span data-ttu-id="ea980-105">In Progettazione dimensioni aprire la dimensione in cui si desidera creare l'attributo.</span><span class="sxs-lookup"><span data-stu-id="ea980-105">In Dimension Designer, open the dimension in which you want to create the attribute.</span></span>  
  
2.  <span data-ttu-id="ea980-106">Nella scheda **Struttura dimensione** selezionare la colonna di una tabella nel riquadro **Vista origine dati** alla quale si vuole associare l'attributo e quindi trascinare la colonna nel riquadro **Attributi** .</span><span class="sxs-lookup"><span data-stu-id="ea980-106">On the **Dimension Structure** tab, in the **Data Source View** pane, in the table to which you want to bind the attribute, select the column, and then drag the column to the **Attributes** pane.</span></span>  
  
     [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="ea980-107">crea il nuovo attributo che ha lo stesso nome della colonna alla quale è associato.</span><span class="sxs-lookup"><span data-stu-id="ea980-107">creates the new attribute that has the same name as the column to which it is bound.</span></span> <span data-ttu-id="ea980-108">Se a una stessa colonna sono associati più attributi, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] aggiunge un numero al nome dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="ea980-108">If there are multiple attributes that use the same column, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] appends a number to the attribute name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea980-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea980-109">See Also</span></span>  
 <span data-ttu-id="ea980-110">[Dimensioni nei modelli multidimensionali](dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="ea980-110">[Dimensions in Multidimensional Models](dimensions-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="ea980-111">Riferimento alle proprietà degli attributo delle dimensioni</span><span class="sxs-lookup"><span data-stu-id="ea980-111">Dimension Attribute Properties Reference</span></span>](dimension-attribute-properties-reference.md)  
  
  
