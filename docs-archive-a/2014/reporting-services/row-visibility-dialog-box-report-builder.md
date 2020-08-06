---
title: Finestra di dialogo Visibilità righe (Generatore report) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10126"
ms.assetid: 117fb20c-2fda-437e-bcc5-9010d6d4b53b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 748cf1612f04e02a90a5d8579b56d3856dea0388
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625985"
---
# <a name="row-visibility-dialog-box-report-builder"></a><span data-ttu-id="bda78-102">Finestra di dialogo Visibilità righe (Generatore report)</span><span class="sxs-lookup"><span data-stu-id="bda78-102">Row Visibility Dialog Box (Report Builder)</span></span>
  <span data-ttu-id="bda78-103">Utilizzare la finestra di dialogo **Visibilità righe** per visualizzare o nascondere la riga selezionata quando il report viene eseguito per la prima volta oppure per utilizzare un altro elemento del report per attivare/disattivare la visibilità della riga.</span><span class="sxs-lookup"><span data-stu-id="bda78-103">Use the **Row Visibility** dialog box to show or hide the selected row when the report is first run or to use another report item to toggle the visibility of the row.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bda78-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="bda78-104">Options</span></span>  
 <span data-ttu-id="bda78-105">**Quando il report viene eseguito inizialmente**</span><span class="sxs-lookup"><span data-stu-id="bda78-105">**When the report is initially run**</span></span>  
 <span data-ttu-id="bda78-106">Selezionare un'opzione per indicare come deve essere visualizzata inizialmente la riga nel report.</span><span class="sxs-lookup"><span data-stu-id="bda78-106">Select an option to indicate how the row is initially displayed in the report.</span></span>  
  
 <span data-ttu-id="bda78-107">**Mostra**</span><span class="sxs-lookup"><span data-stu-id="bda78-107">**Show**</span></span>  
 <span data-ttu-id="bda78-108">Selezionare questa opzione per indicare che la riga deve essere visualizzata.</span><span class="sxs-lookup"><span data-stu-id="bda78-108">Select this option to show the row.</span></span>  
  
 <span data-ttu-id="bda78-109">**Nascondi**</span><span class="sxs-lookup"><span data-stu-id="bda78-109">**Hide**</span></span>  
 <span data-ttu-id="bda78-110">Selezionare questa opzione per indicare che la riga deve essere nascosta.</span><span class="sxs-lookup"><span data-stu-id="bda78-110">Select this option to hide the row.</span></span>  
  
 <span data-ttu-id="bda78-111">**Mostra o nascondi in base a un'espressione**</span><span class="sxs-lookup"><span data-stu-id="bda78-111">**Show or hide based on an expression**</span></span>  
 <span data-ttu-id="bda78-112">Selezionare questa opzione per modificare l'impostazione di visibilità iniziale tramite un'espressione.</span><span class="sxs-lookup"><span data-stu-id="bda78-112">Select this option to vary the initial visibility using an expression.</span></span>  
  
 <span data-ttu-id="bda78-113">Digitare un'espressione che restituisca un valore `Boolean``True` per nascondere l'elemento e `False` per visualizzarlo.</span><span class="sxs-lookup"><span data-stu-id="bda78-113">Type an expression that evaluates to a `Boolean` value of `True` to hide the item and `False` to show the item.</span></span> <span data-ttu-id="bda78-114">Fare clic sul pulsante **espressione** (*FX*) per modificare l'espressione.</span><span class="sxs-lookup"><span data-stu-id="bda78-114">Click the **Expression** (*fx*) button to edit the expression.</span></span>  
  
 <span data-ttu-id="bda78-115">**La visualizzazione può essere attivata/disattivata tramite questo elemento del report**</span><span class="sxs-lookup"><span data-stu-id="bda78-115">**Display can be toggled by this report item**</span></span>  
 <span data-ttu-id="bda78-116">Selezionare questa opzione per visualizzare l'immagine dell'elemento Toggle che consente all'utente di visualizzare o nascondere la riga in un visualizzatore di report HTML.</span><span class="sxs-lookup"><span data-stu-id="bda78-116">Choose this option to display a toggle image that enables the user to show or hide this row in an HTML report viewer.</span></span>  
  
 <span data-ttu-id="bda78-117">Digitare o selezionare il nome di una casella di testo del report in cui visualizzare l'immagine dell'elemento Toggle, ad esempio Textbox1.</span><span class="sxs-lookup"><span data-stu-id="bda78-117">Type or select the name of a text box in the report in which to display a toggle image; for example, Textbox1.</span></span> <span data-ttu-id="bda78-118">La casella di testo selezionata deve trovarsi nell'ambito corrente o contenitore dell'elemento del report.</span><span class="sxs-lookup"><span data-stu-id="bda78-118">The text box that you choose must be in the current or containing scope for this report item.</span></span> <span data-ttu-id="bda78-119">Ad esempio, per attivare/disattivare la visibilità di righe associate a un gruppo figlio, selezionare una casella di testo in una riga associata al gruppo padre.</span><span class="sxs-lookup"><span data-stu-id="bda78-119">For example, to toggle visibility of rows associated with a child group, select a text box in a row associated with the parent group.</span></span> <span data-ttu-id="bda78-120">Per attivare/disattivare la visibilità di un grafico, selezionare una casella di testo che si trovi nello stesso ambito contenitore del grafico, ad esempio il corpo del report o un rettangolo.</span><span class="sxs-lookup"><span data-stu-id="bda78-120">To toggle visibility of a chart, select a text box that is in the same containing scope as the chart; for example, the report body or a rectangle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bda78-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bda78-121">See Also</span></span>  
 <span data-ttu-id="bda78-122">[Esempi di espressioni &#40;Generatore report e SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bda78-122">[Expression Examples &#40;Report Builder and SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bda78-123">[Aggiungere un'azione Espandi o Comprimi a un elemento &#40;Generatore report e SSRS&#41;](report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bda78-123">[Add an Expand or Collapse Action to an Item &#40;Report Builder and SSRS&#41;](report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bda78-124">[Immagini &#40;Generatore report e SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bda78-124">[Images &#40;Report Builder and SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bda78-125">[Guida Generatore report per finestre di dialogo, riquadri e procedure guidate](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="bda78-125">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 [<span data-ttu-id="bda78-126">Finestra di dialogo Proprietà immagine, Generale &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bda78-126">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../../2014/reporting-services/image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
