---
title: Finestra di dialogo Proprietà set di dati, campi (Generatore report) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10021"
ms.assetid: 75c7e54a-3d20-4c9a-88da-ab36dce2ce42
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2b766aa23cce390bc3ffdcf10efdb38efc91f3e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625242"
---
# <a name="dataset-properties-dialog-box-fields-report-builder"></a><span data-ttu-id="af771-102">Finestra di dialogo Proprietà set di dati, Campi (Generatore report)</span><span class="sxs-lookup"><span data-stu-id="af771-102">Dataset Properties Dialog Box, Fields (Report Builder)</span></span>
  <span data-ttu-id="af771-103">Selezionare **Campi** nella finestra di dialogo **Proprietà set di dati** per modificare la raccolta di campi per il set di dati del report.</span><span class="sxs-lookup"><span data-stu-id="af771-103">Select **Fields** on the **Dataset Properties** dialog box to change the field collection for the report dataset.</span></span> <span data-ttu-id="af771-104">L'elenco dei campi viene generato automaticamente, tuttavia è possibile usare la scheda **Campi** per aggiungere, modificare ed eliminare campi di query e calcolati.</span><span class="sxs-lookup"><span data-stu-id="af771-104">The fields list is automatically populated, but you can use **Fields** to add, edit, and delete query and calculated fields.</span></span>  
  
 <span data-ttu-id="af771-105">I campi calcolati sono supportati solo nei set di dati incorporati.</span><span class="sxs-lookup"><span data-stu-id="af771-105">Calculated fields are supported only on embedded datasets.</span></span> <span data-ttu-id="af771-106">Per altre informazioni, vedere [Set di dati condivisi e incorporati del report &#40;Generatore report e SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="af771-106">For more information, see [Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="af771-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="af771-107">Options</span></span>  
 <span data-ttu-id="af771-108">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="af771-108">**Add**</span></span>  
 <span data-ttu-id="af771-109">Consente di aggiungere un nuovo campo di query o calcolato al set di dati.</span><span class="sxs-lookup"><span data-stu-id="af771-109">Add a new query or calculated field to the dataset.</span></span>  
  
 <span data-ttu-id="af771-110">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="af771-110">**Delete**</span></span>  
 <span data-ttu-id="af771-111">Consente di eliminare il campo selezionato dal set di dati.</span><span class="sxs-lookup"><span data-stu-id="af771-111">Delete the selected field from the dataset.</span></span>  
  
 <span data-ttu-id="af771-112">**Nome campo**</span><span class="sxs-lookup"><span data-stu-id="af771-112">**Field Name**</span></span>  
 <span data-ttu-id="af771-113">Consente di digitare un nome per il campo.</span><span class="sxs-lookup"><span data-stu-id="af771-113">Type a name for the field.</span></span> <span data-ttu-id="af771-114">Il campo deve essere univoco nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="af771-114">The field must be unique within the dataset.</span></span> <span data-ttu-id="af771-115">Per ogni campo esistente nel set di dati, il nome viene prepopolato.</span><span class="sxs-lookup"><span data-stu-id="af771-115">For each existing field in the dataset, the name is pre-populated.</span></span>  
  
 <span data-ttu-id="af771-116">**Origine campo**</span><span class="sxs-lookup"><span data-stu-id="af771-116">**Field Source**</span></span>  
 <span data-ttu-id="af771-117">Immettere un valore per il campo.</span><span class="sxs-lookup"><span data-stu-id="af771-117">Enter a value for the field.</span></span>  
  
 <span data-ttu-id="af771-118">Per un campo calcolato, l'origine del campo deve essere il nome di un campo esistente recuperato dalla query del set di dati o da un'espressione creata.</span><span class="sxs-lookup"><span data-stu-id="af771-118">For a calculated field, the field source must be the name of an existing field retrieved by the dataset query, or an expression that you create.</span></span> <span data-ttu-id="af771-119">Ad esempio, per creare un campo che rappresenta 10 volte il valore nel campo Sales della query, utilizzare l'espressione `=10 * Fields!Sales.Value`.</span><span class="sxs-lookup"><span data-stu-id="af771-119">For example, to create a field that represents 10 times the value in the query field Sales, use the expression `=10 * Fields!Sales.Value`.</span></span>  
  
 <span data-ttu-id="af771-120">Per un campo query, l'origine del campo deve essere il nome di un campo esistente recuperato dalla query del set di dati.</span><span class="sxs-lookup"><span data-stu-id="af771-120">For a query field, the field source must be the name of an existing field retrieved by the dataset query.</span></span>  
  
 <span data-ttu-id="af771-121">**Espressione (fx)**</span><span class="sxs-lookup"><span data-stu-id="af771-121">**Expression (fx)**</span></span>  
 <span data-ttu-id="af771-122">Consente di aggiungere o modificare un'espressione per il nuovo campo calcolato.</span><span class="sxs-lookup"><span data-stu-id="af771-122">Add or change an expression for the new calculated field.</span></span> <span data-ttu-id="af771-123">Questo pulsante viene visualizzato solo quando si fa clic su **Aggiungi** e si seleziona **Campo calcolato**.</span><span class="sxs-lookup"><span data-stu-id="af771-123">This button only appears when you click **Add** and select **Calculated Field**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af771-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af771-124">See Also</span></span>  
 <span data-ttu-id="af771-125">[Raccolta di campi del set di dati &#40;Generatore report e SSRS&#41;](report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="af771-125">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="af771-126">[Creare un set di dati condiviso o un set di dati incorporato &#40;Generatore report e SSRS&#41;](report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="af771-126">[Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;](report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="af771-127">[Guida Generatore report per finestre di dialogo, riquadri e procedure guidate](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="af771-127">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="af771-128">[Finestra di dialogo Proprietà set di dati, opzioni &#40;Generatore report&#41;](report-data/dataset-properties-dialog-box-options-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="af771-128">[Dataset Properties Dialog Box, Options &#40;Report Builder&#41;](report-data/dataset-properties-dialog-box-options-report-builder.md) </span></span>  
 <span data-ttu-id="af771-129">[Finestra di dialogo Proprietà set di dati, filtri &#40;Generatore report&#41;](../../2014/reporting-services/dataset-properties-dialog-box-filters-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="af771-129">[Dataset Properties Dialog Box, Filters &#40;Report Builder&#41;](../../2014/reporting-services/dataset-properties-dialog-box-filters-report-builder.md) </span></span>  
 <span data-ttu-id="af771-130">[Finestra di dialogo Proprietà set di dati, parametri &#40;Generatore report&#41;](../../2014/reporting-services/dataset-properties-dialog-box-parameters-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="af771-130">[Dataset Properties Dialog Box, Parameters &#40;Report Builder&#41;](../../2014/reporting-services/dataset-properties-dialog-box-parameters-report-builder.md) </span></span>  
 <span data-ttu-id="af771-131">[Finestra di dialogo Proprietà set di dati, query &#40;Generatore report&#41;](report-data/dataset-properties-dialog-box-query-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="af771-131">[Dataset Properties Dialog Box, Query &#40;Report Builder&#41;](report-data/dataset-properties-dialog-box-query-report-builder.md) </span></span>  
 <span data-ttu-id="af771-132">[Espressioni &#40;Generatore report e SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="af771-132">[Expressions &#40;Report Builder and SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="af771-133">Connessioni dati, origini dati e stringhe di connessione in Generatore report</span><span class="sxs-lookup"><span data-stu-id="af771-133">Data Connections, Data Sources, and Connection Strings in Report Builder</span></span>](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-report-builder.md)  
  
  
