---
title: Editor trasformazione script (pagina colonne di input) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.scriptcomponent.inputcolumn.f1
helpviewer_keywords:
- Script Transformation Editor
ms.assetid: d6e4ce84-3335-48e6-82d3-1c359ed87f63
author: chugugrace
ms.author: chugu
ms.openlocfilehash: daffb52b62ad59ae4fe574d7fa27d4820b9cb5a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712144"
---
# <a name="script-transformation-editor-input-columns-page"></a><span data-ttu-id="96970-102">Editor trasformazione Script (pagina Colonne di input)</span><span class="sxs-lookup"><span data-stu-id="96970-102">Script Transformation Editor (Input Columns Page)</span></span>
  <span data-ttu-id="96970-103">Usare la pagina **Colonne di input** della finestra di dialogo **Editor trasformazione Script** per impostare le proprietà delle colonne di input.</span><span class="sxs-lookup"><span data-stu-id="96970-103">Use the **Input Columns** page of the **Script Transformation Editor** dialog box to set properties on input columns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="96970-104">La pagina **Colonne di input** non viene visualizzata per i componenti di origine, che hanno output ma non input.</span><span class="sxs-lookup"><span data-stu-id="96970-104">The **Input Columns** page is not displayed for Source components, which have outputs but no inputs.</span></span>  
  
 <span data-ttu-id="96970-105">Per ulteriori informazioni sul componente Script, vedere [Script Component](data-flow/transformations/script-component.md) e [Configuring the Script Component in the Script Component Editor](extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span><span class="sxs-lookup"><span data-stu-id="96970-105">To learn more about the Script component, see [Script Component](data-flow/transformations/script-component.md) and [Configuring the Script Component in the Script Component Editor](extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span></span> <span data-ttu-id="96970-106">Per informazioni sulla programmazione del componente Script, vedere [Estensione del flusso di dati con il componente script](extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="96970-106">To learn about programming the Script component, see [Extending the Data Flow with the Script Component](extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="96970-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="96970-107">Options</span></span>  
 <span data-ttu-id="96970-108">**Nome input**</span><span class="sxs-lookup"><span data-stu-id="96970-108">**Input name**</span></span>  
 <span data-ttu-id="96970-109">Consente di selezionare un nome nell'elenco degli input disponibili.</span><span class="sxs-lookup"><span data-stu-id="96970-109">Select from the list of available inputs.</span></span>  
  
 <span data-ttu-id="96970-110">**Colonne di input disponibili**</span><span class="sxs-lookup"><span data-stu-id="96970-110">**Available Input Columns**</span></span>  
 <span data-ttu-id="96970-111">Utilizzando le caselle di controllo, specificare le colonne che verranno utilizzate dalla trasformazione script.</span><span class="sxs-lookup"><span data-stu-id="96970-111">Using the check boxes, specify the columns that the script transformation will use.</span></span>  
  
 <span data-ttu-id="96970-112">**Colonna di input**</span><span class="sxs-lookup"><span data-stu-id="96970-112">**Input Column**</span></span>  
 <span data-ttu-id="96970-113">Consente di selezionare una colonna di input nell'elenco delle colonne di input disponibili per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="96970-113">Select from the list of available input columns for each row.</span></span> <span data-ttu-id="96970-114">Le opzioni selezionate corrispondono alle caselle di controllo selezionate nella tabella **Colonne di input disponibili**.</span><span class="sxs-lookup"><span data-stu-id="96970-114">Your selections are reflected in the check box selections in the **Available Input Columns**table.</span></span>  
  
 <span data-ttu-id="96970-115">**Alias di output**</span><span class="sxs-lookup"><span data-stu-id="96970-115">**Output Alias**</span></span>  
 <span data-ttu-id="96970-116">Consente di digitare un alias per ogni colonna di output.</span><span class="sxs-lookup"><span data-stu-id="96970-116">Type an alias for each output column.</span></span> <span data-ttu-id="96970-117">Per impostazione predefinita viene suggerito il nome della colonna di input. È comunque possibile scegliere qualsiasi nome descrittivo univoco.</span><span class="sxs-lookup"><span data-stu-id="96970-117">The default is the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="96970-118">**Tipo di utilizzo**</span><span class="sxs-lookup"><span data-stu-id="96970-118">**Usage Type**</span></span>  
 <span data-ttu-id="96970-119">Consente di specificare se la trasformazione script deve considerare ogni colonna come `ReadOnly` o `ReadWrite`.</span><span class="sxs-lookup"><span data-stu-id="96970-119">Specify whether the Script Transformation will treat each column as `ReadOnly` or `ReadWrite`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96970-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96970-120">See Also</span></span>  
 <span data-ttu-id="96970-121">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="96970-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="96970-122">[Seleziona tipo componente script](../../2014/integration-services/select-script-component-type.md) </span><span class="sxs-lookup"><span data-stu-id="96970-122">[Select Script Component Type](../../2014/integration-services/select-script-component-type.md) </span></span>  
 <span data-ttu-id="96970-123">[Editor trasformazione script &#40;pagina input e output&#41;](../../2014/integration-services/script-transformation-editor-inputs-and-outputs-page.md) </span><span class="sxs-lookup"><span data-stu-id="96970-123">[Script Transformation Editor &#40;Inputs and Outputs Page&#41;](../../2014/integration-services/script-transformation-editor-inputs-and-outputs-page.md) </span></span>  
 <span data-ttu-id="96970-124">[Editor trasformazione script &#40;pagina script&#41;](../../2014/integration-services/script-transformation-editor-script-page.md) </span><span class="sxs-lookup"><span data-stu-id="96970-124">[Script Transformation Editor &#40;Script Page&#41;](../../2014/integration-services/script-transformation-editor-script-page.md) </span></span>  
 <span data-ttu-id="96970-125">[Editor trasformazione script &#40;pagina Gestioni connessioni&#41;](../../2014/integration-services/script-transformation-editor-connection-managers-page.md) </span><span class="sxs-lookup"><span data-stu-id="96970-125">[Script Transformation Editor &#40;Connection Managers Page&#41;](../../2014/integration-services/script-transformation-editor-connection-managers-page.md) </span></span>  
 [<span data-ttu-id="96970-126">Ulteriori esempi di componente script</span><span class="sxs-lookup"><span data-stu-id="96970-126">Additional Script Component Examples</span></span>](extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md)  
  
  
