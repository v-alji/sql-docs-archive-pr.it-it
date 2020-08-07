---
title: Editor origine ODBC (pagina colonne) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcsource.columns.f1
ms.assetid: 565984eb-8318-4be7-bebc-262209cf5065
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7a11ab6a86978366d07fbe63362f1702310b5d89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718575"
---
# <a name="odbc-source-editor-columns-page"></a><span data-ttu-id="d7cc9-102">Editor origine ODBC (pagina Colonne)</span><span class="sxs-lookup"><span data-stu-id="d7cc9-102">ODBC Source Editor (Columns Page)</span></span>
  <span data-ttu-id="d7cc9-103">Usare la pagina **Colonne** della finestra di dialogo **Editor origine ODBC** per eseguire il mapping tra una colonna di output e ogni colonna esterna (di origine).</span><span class="sxs-lookup"><span data-stu-id="d7cc9-103">Use the **Columns** page of the **ODBC Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="d7cc9-104">Per ulteriori informazioni sull'origine ODBC, vedere [ODBC Source](data-flow/odbc-source.md).</span><span class="sxs-lookup"><span data-stu-id="d7cc9-104">To learn more about the ODBC source, see [ODBC Source](data-flow/odbc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="d7cc9-105">Elenco attività</span><span class="sxs-lookup"><span data-stu-id="d7cc9-105">Task List</span></span>  
 <span data-ttu-id="d7cc9-106">**Per aprire ODBC Source Editor (pagina Colonne)**</span><span class="sxs-lookup"><span data-stu-id="d7cc9-106">**To open the ODBC Source Editor Columns Page**</span></span>  
  
1.  <span data-ttu-id="d7cc9-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], aprire il pacchetto [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] che contiene l'origine ODBC.</span><span class="sxs-lookup"><span data-stu-id="d7cc9-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC source.</span></span>  
  
2.  <span data-ttu-id="d7cc9-108">Nella scheda **Flusso di dati** fare doppio clic sull'origine ODBC.</span><span class="sxs-lookup"><span data-stu-id="d7cc9-108">On the **Data Flow** tab, double-click the ODBC source.</span></span>  
  
3.  <span data-ttu-id="d7cc9-109">In **ODBC Source Editor**, fare clic su **Colonne**.</span><span class="sxs-lookup"><span data-stu-id="d7cc9-109">In the **ODBC Source Editor**, click **Columns**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d7cc9-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="d7cc9-110">Options</span></span>  
  
### <a name="available-external-columns"></a><span data-ttu-id="d7cc9-111">Colonne esterne disponibili</span><span class="sxs-lookup"><span data-stu-id="d7cc9-111">Available External Columns</span></span>  
 <span data-ttu-id="d7cc9-112">Elenco delle colonne esterne disponibili nell'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="d7cc9-112">A list of available external columns in the data source.</span></span> <span data-ttu-id="d7cc9-113">Non è possibile utilizzare questa tabella per l'aggiunta o l'eliminazione di colonne.</span><span class="sxs-lookup"><span data-stu-id="d7cc9-113">You cannot use this table to add or delete columns.</span></span> <span data-ttu-id="d7cc9-114">Selezionare le colonne da utilizzare dall'origine.</span><span class="sxs-lookup"><span data-stu-id="d7cc9-114">Select the columns to use from the source.</span></span> <span data-ttu-id="d7cc9-115">Le colonne scelte vengono aggiunte all'elenco **Colonna esterna** nell'ordine in cui vengono selezionate.</span><span class="sxs-lookup"><span data-stu-id="d7cc9-115">The selected columns are added to the **External Column** list in the order they are selected.</span></span>  
  
 <span data-ttu-id="d7cc9-116">Selezionare la casella di controllo **Seleziona tutto** per selezionare tutte le colonne.</span><span class="sxs-lookup"><span data-stu-id="d7cc9-116">Select the **Select All** check box to select all of the columns.</span></span>  
  
### <a name="external-column"></a><span data-ttu-id="d7cc9-117">Colonna esterna</span><span class="sxs-lookup"><span data-stu-id="d7cc9-117">External Column</span></span>  
 <span data-ttu-id="d7cc9-118">Una vista delle colonne esterne (di origine) nell'ordine in cui vengono presentate durante la configurazione di componenti che utilizzano i dati dell'origine ODBC.</span><span class="sxs-lookup"><span data-stu-id="d7cc9-118">A view of the external (source) columns in the order that you see them when configuring components that consume data from the ODBC source.</span></span>  
  
### <a name="output-column"></a><span data-ttu-id="d7cc9-119">Colonna di output</span><span class="sxs-lookup"><span data-stu-id="d7cc9-119">Output Column</span></span>  
 <span data-ttu-id="d7cc9-120">Consente di immettere un nome univoco per ogni colonna di output.</span><span class="sxs-lookup"><span data-stu-id="d7cc9-120">Enter a unique name for each output column.</span></span> <span data-ttu-id="d7cc9-121">Per impostazione predefinita viene suggerito il nome della colonna esterna (di origine) selezionata. È comunque possibile scegliere qualsiasi nome descrittivo univoco.</span><span class="sxs-lookup"><span data-stu-id="d7cc9-121">The default is the name of the selected external (source) column; however, you can choose any unique, descriptive name.</span></span> <span data-ttu-id="d7cc9-122">Il nome immesso viene visualizzato in Progettazione SSIS.</span><span class="sxs-lookup"><span data-stu-id="d7cc9-122">The name entered is displayed in the SSIS Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7cc9-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7cc9-123">See Also</span></span>  
 <span data-ttu-id="d7cc9-124">[Editor origine ODBC &#40;pagina Gestione connessione&#41;](../../2014/integration-services/odbc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="d7cc9-124">[ODBC Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/odbc-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="d7cc9-125">Editor origine ODBC &#40;pagina Output degli errori&#41;</span><span class="sxs-lookup"><span data-stu-id="d7cc9-125">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/odbc-source-editor-error-output-page.md)  
  
  
