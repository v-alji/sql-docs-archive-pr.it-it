---
title: Editor trasformazione script (pagina input e output) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.scriptcomponent.columnproperties.f1
helpviewer_keywords:
- Script Transformation Editor
ms.assetid: 9659d2d2-5d73-4470-9768-e07b77142fc9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 16adf74a1cd8f0c778bc18eaff84437b8fc13603
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712140"
---
# <a name="script-transformation-editor-inputs-and-outputs-page"></a><span data-ttu-id="e6047-102">Editor trasformazione Script (pagina Input e output)</span><span class="sxs-lookup"><span data-stu-id="e6047-102">Script Transformation Editor (Inputs and Outputs Page)</span></span>
  <span data-ttu-id="e6047-103">Utilizzare la pagina **Input e output** della finestra di dialogo **Editor trasformazione Script** per aggiungere, rimuovere e configurare input e output per la trasformazione script.</span><span class="sxs-lookup"><span data-stu-id="e6047-103">Use the **Inputs and Outputs** page of the **Script Transformation Editor** dialog box to add, remove, and configure inputs and outputs for the Script Transformation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e6047-104">I componenti di origine dispongono di output e di nessun input, mentre i componenti di destinazione dispongono di input e di nessun output.</span><span class="sxs-lookup"><span data-stu-id="e6047-104">Source components have outputs and no inputs, while destination components have inputs but no outputs.</span></span> <span data-ttu-id="e6047-105">Le trasformazioni dispongono sia di input che di output.</span><span class="sxs-lookup"><span data-stu-id="e6047-105">Transformations have both inputs and outputs.</span></span>  
  
 <span data-ttu-id="e6047-106">Per ulteriori informazioni sul componente Script, vedere [Script Component](data-flow/transformations/script-component.md) e [Configuring the Script Component in the Script Component Editor](extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span><span class="sxs-lookup"><span data-stu-id="e6047-106">To learn more about the Script component, see [Script Component](data-flow/transformations/script-component.md) and [Configuring the Script Component in the Script Component Editor](extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span></span> <span data-ttu-id="e6047-107">Per informazioni sulla programmazione del componente Script, vedere [Estensione del flusso di dati con il componente script](extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="e6047-107">To learn about programming the Script component, see [Extending the Data Flow with the Script Component](extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="e6047-108">Opzioni</span><span class="sxs-lookup"><span data-stu-id="e6047-108">Options</span></span>  
 <span data-ttu-id="e6047-109">**Inputs and outputs**</span><span class="sxs-lookup"><span data-stu-id="e6047-109">**Inputs and outputs**</span></span>  
 <span data-ttu-id="e6047-110">Selezionare un input o un output a sinistra per visualizzare le proprietà corrispondenti nella tabella a destra.</span><span class="sxs-lookup"><span data-stu-id="e6047-110">Select an input or output on the left to view its properties in the table on the right.</span></span> <span data-ttu-id="e6047-111">Le proprietà modificabili variano in base alla selezione effettuata.</span><span class="sxs-lookup"><span data-stu-id="e6047-111">Properties available for editing vary according to the selection.</span></span> <span data-ttu-id="e6047-112">Molte delle proprietà visualizzate sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="e6047-112">Many of the properties displayed are read-only.</span></span> <span data-ttu-id="e6047-113">Per ulteriori informazioni sulle singole proprietà, vedere gli argomenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="e6047-113">For more information on the individual properties, see the following topics.</span></span>  
  
 [<span data-ttu-id="e6047-114">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="e6047-114">Common Properties</span></span>](../../2014/integration-services/common-properties.md)  
  
 [<span data-ttu-id="e6047-115">Proprietà personalizzate delle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="e6047-115">Transformation Custom Properties</span></span>](data-flow/transformations/transformation-custom-properties.md)  
  
 <span data-ttu-id="e6047-116">**Aggiungi output**</span><span class="sxs-lookup"><span data-stu-id="e6047-116">**Add Output**</span></span>  
 <span data-ttu-id="e6047-117">Consente di aggiungere un ulteriore output all'elenco.</span><span class="sxs-lookup"><span data-stu-id="e6047-117">Add an additional output to the list.</span></span>  
  
 <span data-ttu-id="e6047-118">**Aggiungi colonna**</span><span class="sxs-lookup"><span data-stu-id="e6047-118">**Add Column**</span></span>  
 <span data-ttu-id="e6047-119">Selezionare una cartella in cui posizionare la nuova colonna di output e quindi aggiungere la colonna facendo clic su **Aggiungi colonna**.</span><span class="sxs-lookup"><span data-stu-id="e6047-119">Select a folder in which to place the new output column, and then add the column by clicking **Add Column**.</span></span>  
  
 <span data-ttu-id="e6047-120">**Rimuovi output**</span><span class="sxs-lookup"><span data-stu-id="e6047-120">**Remove Output**</span></span>  
 <span data-ttu-id="e6047-121">Selezionare un output e quindi rimuoverlo facendo clic su **Rimuovi output**.</span><span class="sxs-lookup"><span data-stu-id="e6047-121">Select an output, and then remove it by clicking **Remove Output**.</span></span>  
  
 <span data-ttu-id="e6047-122">**Rimuovi colonna**</span><span class="sxs-lookup"><span data-stu-id="e6047-122">**Remove Column**</span></span>  
 <span data-ttu-id="e6047-123">Selezionare una colonna e quindi rimuoverla facendo clic su **Rimuovi colonna**.</span><span class="sxs-lookup"><span data-stu-id="e6047-123">Select a column, and then remove it by clicking **Remove Column**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6047-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6047-124">See Also</span></span>  
 <span data-ttu-id="e6047-125">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="e6047-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="e6047-126">[Seleziona tipo componente script](../../2014/integration-services/select-script-component-type.md) </span><span class="sxs-lookup"><span data-stu-id="e6047-126">[Select Script Component Type](../../2014/integration-services/select-script-component-type.md) </span></span>  
 <span data-ttu-id="e6047-127">[Editor trasformazione script &#40;pagina colonne di input&#41;](../../2014/integration-services/script-transformation-editor-input-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="e6047-127">[Script Transformation Editor &#40;Input Columns Page&#41;](../../2014/integration-services/script-transformation-editor-input-columns-page.md) </span></span>  
 <span data-ttu-id="e6047-128">[Editor trasformazione script &#40;pagina script&#41;](../../2014/integration-services/script-transformation-editor-script-page.md) </span><span class="sxs-lookup"><span data-stu-id="e6047-128">[Script Transformation Editor &#40;Script Page&#41;](../../2014/integration-services/script-transformation-editor-script-page.md) </span></span>  
 <span data-ttu-id="e6047-129">[Editor trasformazione script &#40;pagina Gestioni connessioni&#41;](../../2014/integration-services/script-transformation-editor-connection-managers-page.md) </span><span class="sxs-lookup"><span data-stu-id="e6047-129">[Script Transformation Editor &#40;Connection Managers Page&#41;](../../2014/integration-services/script-transformation-editor-connection-managers-page.md) </span></span>  
 [<span data-ttu-id="e6047-130">Ulteriori esempi di componente script</span><span class="sxs-lookup"><span data-stu-id="e6047-130">Additional Script Component Examples</span></span>](extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md)  
  
  
