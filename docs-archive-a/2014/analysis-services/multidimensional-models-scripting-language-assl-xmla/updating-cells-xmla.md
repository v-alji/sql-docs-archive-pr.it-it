---
title: Aggiornamento di celle (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- modifying cells
- XMLA, cells
- updating cells
- cells [Analysis Services]
- XML for Analysis, cells
ms.assetid: a1c61496-36ee-4bce-98d9-d13440d349aa
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2c3d9a7c27533666c75102d9eac3b8311bfe4af6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723192"
---
# <a name="updating-cells-xmla"></a><span data-ttu-id="f6dee-102">Aggiornamento di celle (XMLA)</span><span class="sxs-lookup"><span data-stu-id="f6dee-102">Updating Cells (XMLA)</span></span>
  <span data-ttu-id="f6dee-103">È possibile utilizzare il comando [UpdateCells](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/updatecells-element-xmla) per modificare il valore di una o più celle in un cubo abilitato per il writeback del cubo.</span><span class="sxs-lookup"><span data-stu-id="f6dee-103">You can use the [UpdateCells](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/updatecells-element-xmla) command to change the value of one or more cells in a cube enabled for cube writeback.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="f6dee-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] archivia le informazioni aggiornate in una tabella writeback separata per ogni partizione che contiene le celle da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="f6dee-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] stores the updated information in a separate writeback table for each partition that contains cells to be updated.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f6dee-105">Il comando `UpdateCells` non supporta le allocazioni durante il writeback del cubo.</span><span class="sxs-lookup"><span data-stu-id="f6dee-105">The `UpdateCells` command does not support allocations during cube writeback.</span></span> <span data-ttu-id="f6dee-106">Per utilizzare il writeback allocato, è necessario utilizzare il comando [Statement](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/statement-element-xmla) per inviare un'istruzione di aggiornamento MDX (Multidimensional Expressions).</span><span class="sxs-lookup"><span data-stu-id="f6dee-106">To use allocated writeback, you should use the [Statement](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/statement-element-xmla) command to send a Multidimensional Expressions (MDX) UPDATE statement.</span></span> <span data-ttu-id="f6dee-107">Per ulteriori informazioni, vedere [istruzione UPDATE CUBE &#40;&#41;MDX ](/sql/mdx/mdx-data-manipulation-update-cube).</span><span class="sxs-lookup"><span data-stu-id="f6dee-107">For more information, see [UPDATE CUBE Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-update-cube).</span></span>  
  
## <a name="specifying-cells"></a><span data-ttu-id="f6dee-108">Specifica di celle</span><span class="sxs-lookup"><span data-stu-id="f6dee-108">Specifying Cells</span></span>  
 <span data-ttu-id="f6dee-109">La proprietà [Cell](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) del `UpdateCells` comando contiene le celle da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="f6dee-109">The [Cell](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) property of the `UpdateCells` command contains the cells to be updated.</span></span> <span data-ttu-id="f6dee-110">Per identificare ogni cella nella proprietà `Cell`, utilizzare i numero ordinale della cella specifica.</span><span class="sxs-lookup"><span data-stu-id="f6dee-110">You identify each cell in the `Cell` property using that cell's ordinal number.</span></span> <span data-ttu-id="f6dee-111">Concettualmente, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] numera le celle di un cubo come se il cubo fosse una matrice *p*-dimensionale, dove *p* è il numero di assi.</span><span class="sxs-lookup"><span data-stu-id="f6dee-111">Conceptually, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] numbers cells in a cube as if the cube were a *p*-dimensional array, where *p* is the number of axes.</span></span> <span data-ttu-id="f6dee-112">Le celle sono indirizzate in ordine di riga.</span><span class="sxs-lookup"><span data-stu-id="f6dee-112">Cells are addressed in row-major order.</span></span> <span data-ttu-id="f6dee-113">Nell'illustrazione seguente viene illustrata la formula per calcolare il numero ordinale di una cella.</span><span class="sxs-lookup"><span data-stu-id="f6dee-113">The following illustration shows the formula for calculating the ordinal number of a cell.</span></span>  
  
 <span data-ttu-id="f6dee-114">![Formula per calcolare la posizione ordinale della cella](../../analysis-services/dev-guide/media/cellordinalformula.gif "Formula per calcolare la posizione ordinale della cella")</span><span class="sxs-lookup"><span data-stu-id="f6dee-114">![Formula to calculate the cell ordinal position](../../analysis-services/dev-guide/media/cellordinalformula.gif "Formula to calculate the cell ordinal position")</span></span>  
  
 <span data-ttu-id="f6dee-115">Quando si conosce il numero ordinale di una cella, è possibile indicare il valore desiderato della cella nella proprietà [value](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/value-element-xmla) della proprietà della [cella](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) .</span><span class="sxs-lookup"><span data-stu-id="f6dee-115">Once you know a cell's ordinal number, you can indicate the intended value of the cell in the [Value](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/value-element-xmla) property of the [Cell](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6dee-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6dee-116">See Also</span></span>  
 <span data-ttu-id="f6dee-117">[Elemento Update &#40;&#41;XMLA](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/update-element-xmla) </span><span class="sxs-lookup"><span data-stu-id="f6dee-117">[Update Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/update-element-xmla) </span></span>  
 [<span data-ttu-id="f6dee-118">Sviluppo con XMLA in Analysis Services</span><span class="sxs-lookup"><span data-stu-id="f6dee-118">Developing with XMLA in Analysis Services</span></span>](../multidimensional-models-scripting-language-assl-xmla/developing-with-xmla-in-analysis-services.md)  
  
  
