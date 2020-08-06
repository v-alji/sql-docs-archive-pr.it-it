---
title: Change an Item Within a Cell (Report Builder and SSRS) (Modificare un elemento in una cella (Generatore report e SSRS)) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 91a54778-8929-41f9-bb4c-826cec636be4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 80ef171713e6505867e00e343ce17b70cab9045a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726516"
---
# <a name="change-an-item-within-a-cell-report-builder-and-ssrs"></a><span data-ttu-id="f8ce4-102">Modificare un elemento in una cella (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="f8ce4-102">Change an Item Within a Cell (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f8ce4-103">È possibile sostituire con un nuovo elemento del report solo un elemento non contenitore, ad esempio una casella di testo, una linea o un'immagine.</span><span class="sxs-lookup"><span data-stu-id="f8ce4-103">Only a non-container item, such as a text box, line, or image, can be replaced by a new report item.</span></span> <span data-ttu-id="f8ce4-104">È ad esempio possibile trascinare una tabella in una casella di testo per sostituire quest'ultima con la tabella stessa.</span><span class="sxs-lookup"><span data-stu-id="f8ce4-104">For example, you can drag a table into a text box to replace the text box with a table.</span></span>  
  
 <span data-ttu-id="f8ce4-105">Se nella cella è incluso un elemento contenitore, ad esempio un rettangolo, un elenco, una tabella o una matrice, il nuovo elemento verrà aggiunto all'elemento contenitore invece di sostituirlo.</span><span class="sxs-lookup"><span data-stu-id="f8ce4-105">If the cell contains a container item such as a rectangle, list, table, or matrix, the new item is added to the containing item instead of replacing it.</span></span> <span data-ttu-id="f8ce4-106">Per sostituire un elemento contenitore con un nuovo elemento, eliminare il contenitore.</span><span class="sxs-lookup"><span data-stu-id="f8ce4-106">To replace a container item with a new item, delete the container.</span></span> <span data-ttu-id="f8ce4-107">L'eliminazione dell'elemento contenitore ne provoca la sostituzione con una casella di testo, che potrà essere sostituita in seguito con un altro elemento.</span><span class="sxs-lookup"><span data-stu-id="f8ce4-107">Deleting the container item replaces it with a text box, which you can then replace with another item.</span></span>  
  
 <span data-ttu-id="f8ce4-108">Per impostazione predefinita, tutte le celle di un'area dati tabella, matrice o elenco contengono una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="f8ce4-108">By default, all cells in a table, matrix, or list data region contain a text box.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-an-item-within-a-cell"></a><span data-ttu-id="f8ce4-109">Per modificare un elemento all'interno di una cella</span><span class="sxs-lookup"><span data-stu-id="f8ce4-109">To change an item within a cell</span></span>  
  
-   <span data-ttu-id="f8ce4-110">Nel gruppo **Aree dati** o **Elementi del report** della scheda **Inserisci** fare clic sull'elemento che si desidera aggiungere al report, quindi selezionare il report.</span><span class="sxs-lookup"><span data-stu-id="f8ce4-110">On the **Insert** tab, in the **Data Regions** or **Report Items** group, click the item that you want to add to the report, and then click the report.</span></span> <span data-ttu-id="f8ce4-111">L'elemento verrà aggiunto al report.</span><span class="sxs-lookup"><span data-stu-id="f8ce4-111">The item is added to the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f8ce4-112">Quando si trascina un elemento del report immagine in una cella, viene visualizzata la finestra di dialogo **Proprietà immagine** in cui è possibile impostare le proprietà, ad esempio l'origine dell'immagine, prima che l'immagine venga aggiunta alla cella.</span><span class="sxs-lookup"><span data-stu-id="f8ce4-112">The **Image Properties** dialog box opens when you drag an image report item to a cell, where you can set properties such as the source of the image before the image is added to the cell.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8ce4-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8ce4-113">See Also</span></span>  
 <span data-ttu-id="f8ce4-114">[Immagini, caselle di testo, rettangoli e linee &#40;Generatore report e SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f8ce4-114">[Images, Text Boxes, Rectangles, and Lines &#40;Report Builder and SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f8ce4-115">Elenchi &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f8ce4-115">Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
