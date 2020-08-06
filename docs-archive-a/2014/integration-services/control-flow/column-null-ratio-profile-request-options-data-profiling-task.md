---
title: Opzioni di Richiesta profilo Rapporto di valori Null nella colonna (Attività Profiling dati) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling Task Editor
ms.assetid: 157ef8e4-fd23-4f81-8194-eebf74e9fd86
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0e47c09a9a19eae4aed21c0c518430bc19a45648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627940"
---
# <a name="column-null-ratio-profile-request-options-data-profiling-task"></a><span data-ttu-id="6f9e5-102">Opzioni di Richiesta profilo Rapporto di valori Null nella colonna (Attività Profiling dati)</span><span class="sxs-lookup"><span data-stu-id="6f9e5-102">Column Null Ratio Profile Request Options (Data Profiling Task)</span></span>
  <span data-ttu-id="6f9e5-103">Utilizzare il riquadro **Proprietà richiesta** della pagina **Richieste profilo** per impostare le opzioni per la richiesta **Richiesta profilo Rapporto di valori Null nella colonna** selezionata nel riquadro delle richieste.</span><span class="sxs-lookup"><span data-stu-id="6f9e5-103">Use the **Request Properties** pane of the **Profile Requests** page to set the options for the **Column Null Ratio Request** selected in the requests pane.</span></span> <span data-ttu-id="6f9e5-104">Il profilo Rapporto di valori Null nella colonna segnala la percentuale di valori Null nella colonna selezionata</span><span class="sxs-lookup"><span data-stu-id="6f9e5-104">A Column Null Ratio profile reports the percentage of null values in the selected column.</span></span> <span data-ttu-id="6f9e5-105">e consente di identificare eventuali problemi nei dati, ad esempio un rapporto inaspettatamente elevato di valori Null in una colonna.</span><span class="sxs-lookup"><span data-stu-id="6f9e5-105">This profile can help you identify problems in your data such as an unexpectedly high ratio of null values in a column.</span></span> <span data-ttu-id="6f9e5-106">Un profilo Rapporto di valori Null nella colonna può analizzare, ad esempio, una colonna contenente CAP e individuare una percentuale eccessivamente elevata di CAP mancanti.</span><span class="sxs-lookup"><span data-stu-id="6f9e5-106">For example, a Column Null Ratio profile can profile a ZIP Code/Postal Code column and discover an unacceptably high percentage of missing postal codes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6f9e5-107">Le opzioni descritte in questo argomento vengono visualizzate nella pagina **Richieste profilo** in **Editor attività Profiling dati**.</span><span class="sxs-lookup"><span data-stu-id="6f9e5-107">The options described in this topic appear on the **Profile Requests page** of the **Data Profiling Task Editor**.</span></span> <span data-ttu-id="6f9e5-108">Per altre informazioni su questa pagina dell'editor, vedere [Editor attività Profiling dati &#40;pagina Richieste profilo&#41;](data-profiling-task-editor-profile-requests-page.md).</span><span class="sxs-lookup"><span data-stu-id="6f9e5-108">For more information about this page of the editor, see [Data Profiling Task Editor &#40;Profile Requests Page&#41;](data-profiling-task-editor-profile-requests-page.md).</span></span>  
  
 <span data-ttu-id="6f9e5-109">Per altre informazioni su come usare l'attività Profiling dati, vedere [Impostazione dell'attività Profiling dati](data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="6f9e5-109">For more information about how to use the Data Profiling Task, see [Setup of the Data Profiling Task](data-profiling-task.md).</span></span> <span data-ttu-id="6f9e5-110">Per altre informazioni sull'uso del Visualizzatore profilo dati per analizzare l'output dell'attività Profiling dati, vedere [Visualizzatore profilo dati](data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="6f9e5-110">For more information about how to use the Data Profile Viewer to analyze the output of the Data Profiling Task, see [Data Profile Viewer](data-profile-viewer.md).</span></span>  
  
## <a name="request-properties-options"></a><span data-ttu-id="6f9e5-111">Opzioni del riquadro Proprietà richiesta</span><span class="sxs-lookup"><span data-stu-id="6f9e5-111">Request Properties Options</span></span>  
 <span data-ttu-id="6f9e5-112">Nel riquadro **Proprietà richiesta**per **Richiesta profilo Rapporto di valori Null nella colonna** vengono visualizzati i gruppi di opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6f9e5-112">For a **Column Null Ratio Request**, the **Request Properties** pane displays the following groups of options:</span></span>  
  
-   <span data-ttu-id="6f9e5-113">**Dati**che include le opzioni **TableOrView** e **Column**</span><span class="sxs-lookup"><span data-stu-id="6f9e5-113">**Data**, which includes the **TableOrView** and **Column** options</span></span>  
  
-   <span data-ttu-id="6f9e5-114">**Generale**</span><span class="sxs-lookup"><span data-stu-id="6f9e5-114">**General**</span></span>  
  
### <a name="data-options"></a><span data-ttu-id="6f9e5-115">Opzioni dati</span><span class="sxs-lookup"><span data-stu-id="6f9e5-115">Data Options</span></span>  
 <span data-ttu-id="6f9e5-116">**ConnectionManager**</span><span class="sxs-lookup"><span data-stu-id="6f9e5-116">**ConnectionManager**</span></span>  
 <span data-ttu-id="6f9e5-117">Consente di selezionare la gestione connessione [!INCLUDE[vstecado](../../includes/vstecado-md.md)] esistente che usa il provider di dati .NET per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) per la connessione al database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] contenente la tabella o la vista di cui eseguire il profiling.</span><span class="sxs-lookup"><span data-stu-id="6f9e5-117">Select the existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the.NET Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that contains the table or view to be profiled.</span></span>  
  
 <span data-ttu-id="6f9e5-118">**TableOrView**</span><span class="sxs-lookup"><span data-stu-id="6f9e5-118">**TableOrView**</span></span>  
 <span data-ttu-id="6f9e5-119">Consente di selezionare la tabella o la vista esistente che contiene la colonna da analizzare.</span><span class="sxs-lookup"><span data-stu-id="6f9e5-119">Select the existing table or view that contains the column to be profiled.</span></span>  
  
 <span data-ttu-id="6f9e5-120">Per ulteriori informazioni, vedere la sezione "Opzioni TableorView" in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="6f9e5-120">For more information, see the section, "TableorView Options," in this topic.</span></span>  
  
 <span data-ttu-id="6f9e5-121">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="6f9e5-121">**Column**</span></span>  
 <span data-ttu-id="6f9e5-122">Consente di selezionare la colonna esistente da analizzare.</span><span class="sxs-lookup"><span data-stu-id="6f9e5-122">Select the existing column to be profiled.</span></span> <span data-ttu-id="6f9e5-123">Selezionare **(\*)** per analizzare tutte le colonne.</span><span class="sxs-lookup"><span data-stu-id="6f9e5-123">Select **(\*)** to profile all columns.</span></span>  
  
 <span data-ttu-id="6f9e5-124">Per ulteriori informazioni, vedere la sezione "Opzioni Column" in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="6f9e5-124">For more information, see the section, "Column Options," in this topic.</span></span>  
  
#### <a name="tableorview-options"></a><span data-ttu-id="6f9e5-125">Opzioni TableOrView</span><span class="sxs-lookup"><span data-stu-id="6f9e5-125">TableOrView Options</span></span>  
 <span data-ttu-id="6f9e5-126">**Schema**</span><span class="sxs-lookup"><span data-stu-id="6f9e5-126">**Schema**</span></span>  
 <span data-ttu-id="6f9e5-127">Specifica lo schema a cui appartiene la tabella selezionata.</span><span class="sxs-lookup"><span data-stu-id="6f9e5-127">Specifies the schema to which the selected table belongs.</span></span> <span data-ttu-id="6f9e5-128">Questa opzione è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="6f9e5-128">This option is read-only.</span></span>  
  
 <span data-ttu-id="6f9e5-129">**Tabella**</span><span class="sxs-lookup"><span data-stu-id="6f9e5-129">**Table**</span></span>  
 <span data-ttu-id="6f9e5-130">Visualizza il nome della tabella selezionata.</span><span class="sxs-lookup"><span data-stu-id="6f9e5-130">Displays the name of the selected table.</span></span> <span data-ttu-id="6f9e5-131">Questa opzione è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="6f9e5-131">This option is read-only.</span></span>  
  
#### <a name="column-options"></a><span data-ttu-id="6f9e5-132">Opzioni relative alle colonne</span><span class="sxs-lookup"><span data-stu-id="6f9e5-132">Column Options</span></span>  
 <span data-ttu-id="6f9e5-133">**IsWildCard**</span><span class="sxs-lookup"><span data-stu-id="6f9e5-133">**IsWildCard**</span></span>  
 <span data-ttu-id="6f9e5-134">Specifica se è stato selezionato il carattere jolly **(\*)** .</span><span class="sxs-lookup"><span data-stu-id="6f9e5-134">Specifies whether the **(\*)** wildcard has been selected.</span></span> <span data-ttu-id="6f9e5-135">Questa opzione è impostata su **True** se è stato selezionato **(\*)** per profilare tutte le colonne.</span><span class="sxs-lookup"><span data-stu-id="6f9e5-135">This option is set to **True** if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="6f9e5-136">È impostata su **False** se è stata selezionata una singola colonna da analizzare.</span><span class="sxs-lookup"><span data-stu-id="6f9e5-136">It is **False** if you have selected an individual column to be profiled.</span></span> <span data-ttu-id="6f9e5-137">Questa opzione è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="6f9e5-137">This option is read-only.</span></span>  
  
 <span data-ttu-id="6f9e5-138">**ColumnName**</span><span class="sxs-lookup"><span data-stu-id="6f9e5-138">**ColumnName**</span></span>  
 <span data-ttu-id="6f9e5-139">Visualizza il nome della colonna selezionata.</span><span class="sxs-lookup"><span data-stu-id="6f9e5-139">Displays the name of the selected column.</span></span> <span data-ttu-id="6f9e5-140">È vuota se è stato selezionato **(\*)** per profilare tutte le colonne.</span><span class="sxs-lookup"><span data-stu-id="6f9e5-140">This option is blank if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="6f9e5-141">Questa opzione è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="6f9e5-141">This option is read-only.</span></span>  
  
 <span data-ttu-id="6f9e5-142">**StringCompareOptions**</span><span class="sxs-lookup"><span data-stu-id="6f9e5-142">**StringCompareOptions**</span></span>  
 <span data-ttu-id="6f9e5-143">Questa opzione non si applica al profilo Rapporto di valori Null nella colonna.</span><span class="sxs-lookup"><span data-stu-id="6f9e5-143">This option does not apply to the Column Null Ratio Profile.</span></span>  
  
### <a name="general-options"></a><span data-ttu-id="6f9e5-144">Opzioni generali</span><span class="sxs-lookup"><span data-stu-id="6f9e5-144">General Options</span></span>  
 <span data-ttu-id="6f9e5-145">**RequestID**</span><span class="sxs-lookup"><span data-stu-id="6f9e5-145">**RequestID**</span></span>  
 <span data-ttu-id="6f9e5-146">Nome descrittivo per identificare la richiesta di profilo.</span><span class="sxs-lookup"><span data-stu-id="6f9e5-146">Type a descriptive name to identify this profile request.</span></span> <span data-ttu-id="6f9e5-147">Non è in genere necessario modificare il valore generato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6f9e5-147">Typically, you do not have to change the autogenerated value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f9e5-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f9e5-148">See Also</span></span>  
 <span data-ttu-id="6f9e5-149">[Editor attività Profiling dati &#40;pagina Generale&#41;](../general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="6f9e5-149">[Data Profiling Task Editor &#40;General Page&#41;](../general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="6f9e5-150">Form profilo rapido singola tabella &#40;Attività Profiling dati&#41;</span><span class="sxs-lookup"><span data-stu-id="6f9e5-150">Single Table Quick Profile Form &#40;Data Profiling Task&#41;</span></span>](single-table-quick-profile-form-data-profiling-task.md)  
  
  
