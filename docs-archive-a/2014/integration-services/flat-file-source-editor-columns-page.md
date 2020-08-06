---
title: Editor origine file flat (pagina colonne) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfilesourceadapter.columns.f1
helpviewer_keywords:
- Flat File Source Editor
ms.assetid: b5af5f65-c087-44fd-b5ae-d0441245fef2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9b0249b2b17d50fdef4b5cf4aff70a1318614257
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624853"
---
# <a name="flat-file-source-editor-columns-page"></a><span data-ttu-id="c13cf-102">Editor origine file flat (pagina Colonne)</span><span class="sxs-lookup"><span data-stu-id="c13cf-102">Flat File Source Editor (Columns Page)</span></span>
  <span data-ttu-id="c13cf-103">Usare il nodo **Colonne** della finestra di dialogo **Editor origine file flat** per eseguire il mapping tra una colonna di output e ogni colonna esterna (di origine).</span><span class="sxs-lookup"><span data-stu-id="c13cf-103">Use the **Columns** node of the **Flat File Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c13cf-104">La `FileNameColumnName` proprietà dell'origine file flat e la `FastParse` proprietà delle colonne di output non sono disponibili nell' **Editor origine file flat**, ma possono essere impostate tramite il **Editor avanzato**.</span><span class="sxs-lookup"><span data-stu-id="c13cf-104">The `FileNameColumnName` property of the Flat File source and the `FastParse` property of its output columns are not available in the **Flat File Source Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="c13cf-105">Per ulteriori informazioni su queste proprietà, vedere la sezione relativa all'origine file flat in [Flat File Custom Properties](data-flow/flat-file-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c13cf-105">For more information on these properties, see the Flat File Source section of [Flat File Custom Properties](data-flow/flat-file-custom-properties.md).</span></span>  
  
 <span data-ttu-id="c13cf-106">Per ulteriori informazioni sull'origine file flat, vedere [Flat File Source](data-flow/flat-file-source.md).</span><span class="sxs-lookup"><span data-stu-id="c13cf-106">To learn more about the Flat File source, see [Flat File Source](data-flow/flat-file-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c13cf-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="c13cf-107">Options</span></span>  
 <span data-ttu-id="c13cf-108">**Colonne esterne disponibili**</span><span class="sxs-lookup"><span data-stu-id="c13cf-108">**Available External Columns**</span></span>  
 <span data-ttu-id="c13cf-109">Consente di visualizzare l'elenco delle colonne esterne disponibili nell'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="c13cf-109">View the list of available external columns in the data source.</span></span> <span data-ttu-id="c13cf-110">Non è possibile utilizzare questa tabella per l'aggiunta o l'eliminazione di colonne.</span><span class="sxs-lookup"><span data-stu-id="c13cf-110">You cannot use this table to add or delete columns.</span></span>  
  
 <span data-ttu-id="c13cf-111">**Colonna esterna**</span><span class="sxs-lookup"><span data-stu-id="c13cf-111">**External Column**</span></span>  
 <span data-ttu-id="c13cf-112">Consente di visualizzare le colonne esterne (origine) nell'ordine in cui verranno lette dall'attività.</span><span class="sxs-lookup"><span data-stu-id="c13cf-112">View external (source) columns in the order in which the task will read them.</span></span> <span data-ttu-id="c13cf-113">È possibile modificare l'ordine deselezionando innanzitutto le colonne della tabella selezionate e quindi selezionando dall'elenco le colonne esterne in un ordine diverso.</span><span class="sxs-lookup"><span data-stu-id="c13cf-113">You can change this order by first clearing the selected columns in the table, and then selecting external columns from the list in a different order.</span></span>  
  
 <span data-ttu-id="c13cf-114">**Colonna di output**</span><span class="sxs-lookup"><span data-stu-id="c13cf-114">**Output Column**</span></span>  
 <span data-ttu-id="c13cf-115">Consente di specificare un nome univoco per ogni colonna di output.</span><span class="sxs-lookup"><span data-stu-id="c13cf-115">Provide a unique name for each output column.</span></span> <span data-ttu-id="c13cf-116">Per impostazione predefinita viene suggerito il nome della colonna esterna (di origine) selezionata. È comunque possibile scegliere qualsiasi nome descrittivo univoco.</span><span class="sxs-lookup"><span data-stu-id="c13cf-116">The default is the name of the selected external (source) column; however, you can choose any unique, descriptive name.</span></span> <span data-ttu-id="c13cf-117">Il nome specificato verrà visualizzato in Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c13cf-117">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c13cf-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c13cf-118">See Also</span></span>  
 <span data-ttu-id="c13cf-119">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="c13cf-119">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="c13cf-120">[Editor origine file flat &#40;pagina Gestione connessione&#41;](../../2014/integration-services/flat-file-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="c13cf-120">[Flat File Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/flat-file-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="c13cf-121">[Editor origine file flat &#40;pagina output degli errori&#41;](../../2014/integration-services/flat-file-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="c13cf-121">[Flat File Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/flat-file-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="c13cf-122">Gestione connessione file flat</span><span class="sxs-lookup"><span data-stu-id="c13cf-122">Flat File Connection Manager</span></span>](connection-manager/file-connection-manager.md)  
  
  
