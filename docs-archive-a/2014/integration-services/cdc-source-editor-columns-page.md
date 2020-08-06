---
title: Editor origine CDC (pagina colonne) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.cdcsource.columns.f1
ms.assetid: bcf3030e-98d8-4445-967c-33c3f8ecb4fc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: aa30defb5e6873ea05e8e41c733477cf50d0dc4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636839"
---
# <a name="cdc-source-editor-columns-page"></a><span data-ttu-id="aab82-102">Editor origine CDC (pagina Colonne)</span><span class="sxs-lookup"><span data-stu-id="aab82-102">CDC Source Editor (Columns Page)</span></span>
  <span data-ttu-id="aab82-103">Usare la pagina **Colonne** della finestra di dialogo **CDC Source Editor (Editor origine CDC)** per eseguire il mapping tra una colonna di output e ogni colonna esterna (di origine).</span><span class="sxs-lookup"><span data-stu-id="aab82-103">Use the **Columns** page of the **CDC Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="aab82-104">Per ulteriori informazioni sull'origine CDC, vedere [CDC Source](data-flow/cdc-source.md).</span><span class="sxs-lookup"><span data-stu-id="aab82-104">To learn more about the CDC source, see [CDC Source](data-flow/cdc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="aab82-105">Elenco attività</span><span class="sxs-lookup"><span data-stu-id="aab82-105">Task List</span></span>  
 <span data-ttu-id="aab82-106">**Per aprire CDC Source Editor (pagina Colonne)**</span><span class="sxs-lookup"><span data-stu-id="aab82-106">**To open the CDC Source Editor Columns Page**</span></span>  
  
1.  <span data-ttu-id="aab82-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], aprire il pacchetto [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] che contiene l'origine CDC.</span><span class="sxs-lookup"><span data-stu-id="aab82-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the CDC source.</span></span>  
  
2.  <span data-ttu-id="aab82-108">Nella scheda **Flusso di dati** fare doppio clic sull'origine CDC.</span><span class="sxs-lookup"><span data-stu-id="aab82-108">On the **Data Flow** tab, double-click the CDC source.</span></span>  
  
3.  <span data-ttu-id="aab82-109">In **CDC Source Editor**, fare clic su **Colonne**.</span><span class="sxs-lookup"><span data-stu-id="aab82-109">In the **CDC Source Editor**, click **Columns**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="aab82-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="aab82-110">Options</span></span>  
 <span data-ttu-id="aab82-111">**Colonne esterne disponibili**</span><span class="sxs-lookup"><span data-stu-id="aab82-111">**Available External Columns**</span></span>  
 <span data-ttu-id="aab82-112">Elenco delle colonne esterne disponibili nell'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="aab82-112">A list of available external columns in the data source.</span></span> <span data-ttu-id="aab82-113">Non è possibile utilizzare questa tabella per l'aggiunta o l'eliminazione di colonne.</span><span class="sxs-lookup"><span data-stu-id="aab82-113">You cannot use this table to add or delete columns.</span></span> <span data-ttu-id="aab82-114">Selezionare le colonne da utilizzare nell'origine.</span><span class="sxs-lookup"><span data-stu-id="aab82-114">Select the columns to use in the source.</span></span> <span data-ttu-id="aab82-115">Le colonne scelte vengono aggiunte all'elenco **Colonna esterna** nell'ordine in cui vengono selezionate.</span><span class="sxs-lookup"><span data-stu-id="aab82-115">The selected columns are added to the **External Column** list in the order they are selected.</span></span>  
  
 <span data-ttu-id="aab82-116">**Colonna esterna**</span><span class="sxs-lookup"><span data-stu-id="aab82-116">**External Column**</span></span>  
 <span data-ttu-id="aab82-117">Una vista delle colonne esterne (di origine) nell'ordine in cui vengono presentate durante la configurazione di componenti che utilizzano i dati dell'origine CDC.</span><span class="sxs-lookup"><span data-stu-id="aab82-117">A view of the external (source) columns in the order that you see them when configuring components that consume data from the CDC source.</span></span> <span data-ttu-id="aab82-118">Per modificare questo ordine, deselezionare innanzitutto le colonne selezionate nell'elenco **Colonne esterne disponibili** , quindi selezionare le colonne esterne nell'elenco secondo un ordine diverso.</span><span class="sxs-lookup"><span data-stu-id="aab82-118">To change this order, first clear the selected columns in the **Available External Columns** list, and then select external columns from the list in a different order.</span></span> <span data-ttu-id="aab82-119">Le colonne scelte vengono aggiunte all'elenco **Colonna esterna** nell'ordine in cui vengono selezionate.</span><span class="sxs-lookup"><span data-stu-id="aab82-119">The selected columns are added to the **External Column** list in the order you select them.</span></span>  
  
 <span data-ttu-id="aab82-120">**Colonna di output**</span><span class="sxs-lookup"><span data-stu-id="aab82-120">**Output Column**</span></span>  
 <span data-ttu-id="aab82-121">Consente di immettere un nome univoco per ogni colonna di output.</span><span class="sxs-lookup"><span data-stu-id="aab82-121">Enter a unique name for each output column.</span></span> <span data-ttu-id="aab82-122">Per impostazione predefinita viene suggerito il nome della colonna esterna (di origine) selezionata. È comunque possibile scegliere qualsiasi nome descrittivo univoco.</span><span class="sxs-lookup"><span data-stu-id="aab82-122">The default is the name of the selected external (source) column, however you can choose any unique, descriptive name.</span></span> <span data-ttu-id="aab82-123">Il nome immesso viene visualizzato in Progettazione SSIS.</span><span class="sxs-lookup"><span data-stu-id="aab82-123">The name entered is displayed in the SSIS Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aab82-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aab82-124">See Also</span></span>  
 <span data-ttu-id="aab82-125">[Editor origine CDC &#40;pagina Gestione connessione&#41;](../../2014/integration-services/cdc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="aab82-125">[CDC Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/cdc-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="aab82-126">Editor origine CDC &#40;pagina Output degli errori&#41;</span><span class="sxs-lookup"><span data-stu-id="aab82-126">CDC Source Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/cdc-source-editor-error-output-page.md)  
  
  
