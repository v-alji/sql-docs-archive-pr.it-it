---
title: Editor origine Excel (pagina colonne) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.excelsourceadapter.columns.f1
helpviewer_keywords:
- Excel Source Editor
ms.assetid: 50024686-a18d-4824-b20e-c84123f89d0b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0713d8d3d0c1f56bf322684a924a286e8b81af55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629502"
---
# <a name="excel-source-editor-columns-page"></a><span data-ttu-id="d86e7-102">Editor origine Excel (pagina Colonne)</span><span class="sxs-lookup"><span data-stu-id="d86e7-102">Excel Source Editor (Columns Page)</span></span>
  <span data-ttu-id="d86e7-103">Usare la pagina **Colonne** della finestra di dialogo **Editor origine Excel** per eseguire il mapping tra una colonna di output e ogni colonna (di origine) esterna.</span><span class="sxs-lookup"><span data-stu-id="d86e7-103">Use the **Columns** page of the **Excel Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="d86e7-104">Per ulteriori informazioni sull'origine Excel, vedere [Excel Source](data-flow/excel-source.md).</span><span class="sxs-lookup"><span data-stu-id="d86e7-104">To learn more about the Excel source, see [Excel Source](data-flow/excel-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="d86e7-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="d86e7-105">Options</span></span>  
 <span data-ttu-id="d86e7-106">**Colonne esterne disponibili**</span><span class="sxs-lookup"><span data-stu-id="d86e7-106">**Available External Columns**</span></span>  
 <span data-ttu-id="d86e7-107">Consente di visualizzare l'elenco delle colonne esterne disponibili nell'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="d86e7-107">View the list of available external columns in the data source.</span></span> <span data-ttu-id="d86e7-108">Non è possibile utilizzare questa tabella per l'aggiunta o l'eliminazione di colonne.</span><span class="sxs-lookup"><span data-stu-id="d86e7-108">You cannot use this table to add or delete columns.</span></span>  
  
 <span data-ttu-id="d86e7-109">**Colonna esterna**</span><span class="sxs-lookup"><span data-stu-id="d86e7-109">**External Column**</span></span>  
 <span data-ttu-id="d86e7-110">Consente di visualizzare le colonne esterne (origine) nell'ordine in cui verranno lette dall'attività.</span><span class="sxs-lookup"><span data-stu-id="d86e7-110">View external (source) columns in the order in which the task will read them.</span></span> <span data-ttu-id="d86e7-111">È possibile modificare l'ordine deselezionando innanzitutto le colonne selezionate nella tabella sopra descritta e quindi selezionando le colonne esterne nell'elenco secondo un ordine diverso.</span><span class="sxs-lookup"><span data-stu-id="d86e7-111">You can change this order by first clearing the selected columns in the table discussed above, and then selecting external columns from the list in a different order.</span></span>  
  
 <span data-ttu-id="d86e7-112">**Colonna di output**</span><span class="sxs-lookup"><span data-stu-id="d86e7-112">**Output Column**</span></span>  
 <span data-ttu-id="d86e7-113">Consente di specificare un nome univoco per ogni colonna di output.</span><span class="sxs-lookup"><span data-stu-id="d86e7-113">Provide a unique name for each output column.</span></span> <span data-ttu-id="d86e7-114">Per impostazione predefinita viene suggerito il nome della colonna esterna (di origine) selezionata. È comunque possibile scegliere qualsiasi nome descrittivo univoco.</span><span class="sxs-lookup"><span data-stu-id="d86e7-114">The default is the name of the selected external (source) column; however, you can choose any unique, descriptive name.</span></span> <span data-ttu-id="d86e7-115">Il nome specificato verrà visualizzato in Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d86e7-115">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d86e7-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d86e7-116">See Also</span></span>  
 <span data-ttu-id="d86e7-117">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d86e7-117">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="d86e7-118">[Editor origine Excel &#40;pagina Gestione connessione&#41;](../../2014/integration-services/excel-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="d86e7-118">[Excel Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/excel-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="d86e7-119">[Editor origine Excel &#40;pagina output degli errori&#41;](../../2014/integration-services/excel-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="d86e7-119">[Excel Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/excel-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="d86e7-120">[Gestione connessione Excel](connection-manager/excel-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="d86e7-120">[Excel Connection Manager](connection-manager/excel-connection-manager.md) </span></span>  
 [<span data-ttu-id="d86e7-121">Esecuzione di un ciclo su file e tabelle di Excel usando un contenitore Ciclo Foreach</span><span class="sxs-lookup"><span data-stu-id="d86e7-121">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
