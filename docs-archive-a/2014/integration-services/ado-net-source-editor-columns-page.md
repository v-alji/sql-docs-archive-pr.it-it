---
title: Editor origine ADO NET (pagina colonne) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetsource.columns.f1
ms.assetid: fbc205b9-2001-4737-a76b-1ba777344bd9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0d89f8c926761b9149f19269bc2519c12bcf130e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628940"
---
# <a name="ado-net-source-editor-columns-page"></a><span data-ttu-id="22d8f-102">Editor origine ADO NET (pagina Colonne)</span><span class="sxs-lookup"><span data-stu-id="22d8f-102">ADO NET Source Editor (Columns Page)</span></span>
  <span data-ttu-id="22d8f-103">Usare la pagina **Colonne** della finestra di dialogo **Editor origine ADO NET** per eseguire il mapping tra una colonna di output e ogni colonna esterna (di origine).</span><span class="sxs-lookup"><span data-stu-id="22d8f-103">Use the **Columns** page of the **ADO NET Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="22d8f-104">Per ulteriori informazioni sull'origine ADO NET, vedere [ADO NET Source](data-flow/ado-net-source.md).</span><span class="sxs-lookup"><span data-stu-id="22d8f-104">To learn more about the ADO NET source, see [ADO NET Source](data-flow/ado-net-source.md).</span></span>  
  
 <span data-ttu-id="22d8f-105">**Per aprire la pagina Colonne**</span><span class="sxs-lookup"><span data-stu-id="22d8f-105">**To open the Columns page**</span></span>  
  
1.  <span data-ttu-id="22d8f-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], aprire il pacchetto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] con l'origine ADO NET.</span><span class="sxs-lookup"><span data-stu-id="22d8f-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET source.</span></span>  
  
2.  <span data-ttu-id="22d8f-107">Nella scheda **Flusso di dati** fare doppio clic sull'origine ADO NET.</span><span class="sxs-lookup"><span data-stu-id="22d8f-107">On the **Data Flow** tab, double-click the ADO NET source.</span></span>  
  
3.  <span data-ttu-id="22d8f-108">In **Editor origine ADO NET**, fare clic su **Colonne**.</span><span class="sxs-lookup"><span data-stu-id="22d8f-108">In the **ADO NET Source Editor**, click **Columns**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="22d8f-109">Opzioni</span><span class="sxs-lookup"><span data-stu-id="22d8f-109">Options</span></span>  
 <span data-ttu-id="22d8f-110">**Colonne esterne disponibili**</span><span class="sxs-lookup"><span data-stu-id="22d8f-110">**Available External Columns**</span></span>  
 <span data-ttu-id="22d8f-111">Consente di visualizzare l'elenco delle colonne esterne disponibili nell'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="22d8f-111">View the list of available external columns in the data source.</span></span> <span data-ttu-id="22d8f-112">Non è possibile utilizzare questa tabella per l'aggiunta o l'eliminazione di colonne.</span><span class="sxs-lookup"><span data-stu-id="22d8f-112">You cannot use this table to add or delete columns.</span></span>  
  
 <span data-ttu-id="22d8f-113">**Colonna esterna**</span><span class="sxs-lookup"><span data-stu-id="22d8f-113">**External Column**</span></span>  
 <span data-ttu-id="22d8f-114">Consente di visualizzare le colonne esterne (di origine) nell'ordine in cui verranno presentate durante la configurazione di componenti che utilizzano i dati dell'origine.</span><span class="sxs-lookup"><span data-stu-id="22d8f-114">View external (source) columns in the order in which you will see them when configuring components that consume data from this source.</span></span>  
  
 <span data-ttu-id="22d8f-115">**Colonna di output**</span><span class="sxs-lookup"><span data-stu-id="22d8f-115">**Output Column**</span></span>  
 <span data-ttu-id="22d8f-116">Consente di specificare un nome univoco per ogni colonna di output.</span><span class="sxs-lookup"><span data-stu-id="22d8f-116">Provide a unique name for each output column.</span></span> <span data-ttu-id="22d8f-117">Per impostazione predefinita viene suggerito il nome della colonna esterna (di origine) selezionata. È comunque possibile scegliere qualsiasi nome descrittivo univoco.</span><span class="sxs-lookup"><span data-stu-id="22d8f-117">The default is the name of the selected external (source) column; however, you can choose any unique, descriptive name.</span></span> <span data-ttu-id="22d8f-118">Il nome specificato verrà visualizzato in Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="22d8f-118">The name provided will be displayed within the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22d8f-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22d8f-119">See Also</span></span>  
 <span data-ttu-id="22d8f-120">[Editor origine ADO NET &#40;pagina Gestione connessione&#41;](../../2014/integration-services/ado-net-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="22d8f-120">[ADO NET Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ado-net-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="22d8f-121">[Editor origine ADO NET &#40;pagina output degli errori&#41;](../../2014/integration-services/ado-net-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="22d8f-121">[ADO NET Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/ado-net-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="22d8f-122">Gestione connessione ADO.NET</span><span class="sxs-lookup"><span data-stu-id="22d8f-122">ADO.NET Connection Manager</span></span>](connection-manager/ado-net-connection-manager.md)  
  
  
