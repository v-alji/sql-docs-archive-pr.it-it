---
title: Opzioni di Richiesta profilo Distribuzione lunghezze di colonna (Attività Profiling dati) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling Task Editor
ms.assetid: 1a4de41f-f38d-40ea-ba1b-6c0ef67ea52a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4c0ebb6f1e0a6df2c0e47311f7b8217c5ce6f2df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627942"
---
# <a name="column-length-distribution-profile-request-options-data-profiling-task"></a><span data-ttu-id="85cab-102">Opzioni di Richiesta profilo Distribuzione lunghezze di colonna (Attività Profiling dati)</span><span class="sxs-lookup"><span data-stu-id="85cab-102">Column Length Distribution Profile Request Options (Data Profiling Task)</span></span>
  <span data-ttu-id="85cab-103">Usare il riquadro **Proprietà richiesta** della pagina **Richieste profilo** per impostare le opzioni della richiesta **Richiesta profilo Distribuzione lunghezze di colonna** selezionata nel riquadro delle richieste.</span><span class="sxs-lookup"><span data-stu-id="85cab-103">Use the **Request Properties** pane of the **Profile Requests** page to set the options for the **Column Length Distribution Profile Request** selected in the requests pane.</span></span> <span data-ttu-id="85cab-104">Il profilo Distribuzione lunghezze di colonna segnala tutte le singole lunghezze dei valori stringa nella colonna selezionata e la percentuale di righe nella tabella rappresentata da ogni lunghezza.</span><span class="sxs-lookup"><span data-stu-id="85cab-104">A Column Length Distribution profile reports all the distinct lengths of string values in the selected column and the percentage of rows in the table that each length represents.</span></span> <span data-ttu-id="85cab-105">Questo profilo consente inoltre di identificare eventuali problemi nei dati, ad esempio valori non validi.</span><span class="sxs-lookup"><span data-stu-id="85cab-105">This profile can help you identify problems in your data such as invalid values.</span></span> <span data-ttu-id="85cab-106">Si analizza, ad esempio, una colonna di codici a due caratteri degli stati degli Stati Uniti e si individuano valori con lunghezza maggiore di due caratteri.</span><span class="sxs-lookup"><span data-stu-id="85cab-106">For example, you profile a column of two-character United States state codes and discover values longer than two characters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="85cab-107">Le opzioni descritte in questo argomento vengono visualizzate nella pagina **Richieste profilo** in **Editor attività Profiling dati**.</span><span class="sxs-lookup"><span data-stu-id="85cab-107">The options described in this topic appear on the **Profile Requests page** of the **Data Profiling Task Editor**.</span></span> <span data-ttu-id="85cab-108">Per altre informazioni su questa pagina dell'editor, vedere [Editor attività Profiling dati &#40;pagina Richieste profilo&#41;](data-profiling-task-editor-profile-requests-page.md).</span><span class="sxs-lookup"><span data-stu-id="85cab-108">For more information about this page of the editor, see [Data Profiling Task Editor &#40;Profile Requests Page&#41;](data-profiling-task-editor-profile-requests-page.md).</span></span>  
  
 <span data-ttu-id="85cab-109">Per altre informazioni su come usare l'attività Profiling dati, vedere [Impostazione dell'attività Profiling dati](data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="85cab-109">For more information about how to use the Data Profiling Task, see [Setup of the Data Profiling Task](data-profiling-task.md).</span></span> <span data-ttu-id="85cab-110">Per altre informazioni sull'uso del Visualizzatore profilo dati per analizzare l'output dell'attività Profiling dati, vedere [Visualizzatore profilo dati](data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="85cab-110">For more information about how to use the Data Profile Viewer to analyze the output of the Data Profiling Task, see [Data Profile Viewer](data-profile-viewer.md).</span></span>  
  
## <a name="request-properties-options"></a><span data-ttu-id="85cab-111">Opzioni del riquadro Proprietà richiesta</span><span class="sxs-lookup"><span data-stu-id="85cab-111">Request Properties Options</span></span>  
 <span data-ttu-id="85cab-112">Nel riquadro **Proprietà richiesta**per **Richiesta profilo Distribuzione lunghezze di colonna** vengono visualizzati i gruppi di opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="85cab-112">For a **Column Length Distribution Profile Request**, the **Request Properties** pane displays the following groups of options:</span></span>  
  
-   <span data-ttu-id="85cab-113">**Dati**che include le opzioni **TableOrView** e **Column**</span><span class="sxs-lookup"><span data-stu-id="85cab-113">**Data**, which includes the **TableOrView** and **Column** options</span></span>  
  
-   <span data-ttu-id="85cab-114">**Generale**</span><span class="sxs-lookup"><span data-stu-id="85cab-114">**General**</span></span>  
  
-   <span data-ttu-id="85cab-115">**Opzioni**</span><span class="sxs-lookup"><span data-stu-id="85cab-115">**Options**</span></span>  
  
### <a name="data-options"></a><span data-ttu-id="85cab-116">Opzioni dati</span><span class="sxs-lookup"><span data-stu-id="85cab-116">Data Options</span></span>  
 <span data-ttu-id="85cab-117">**ConnectionManager**</span><span class="sxs-lookup"><span data-stu-id="85cab-117">**ConnectionManager**</span></span>  
 <span data-ttu-id="85cab-118">Consente di selezionare la gestione connessione [!INCLUDE[vstecado](../../includes/vstecado-md.md)] esistente che usa il provider di dati .NET per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) ai fini della connessione al database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] contenente la tabella o la vista di cui eseguire il profiling.</span><span class="sxs-lookup"><span data-stu-id="85cab-118">Select the existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the .NET Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that contains the table or view to be profiled.</span></span>  
  
 <span data-ttu-id="85cab-119">**TableOrView**</span><span class="sxs-lookup"><span data-stu-id="85cab-119">**TableOrView**</span></span>  
 <span data-ttu-id="85cab-120">Consente di selezionare la tabella o la vista esistente che contiene la colonna da analizzare.</span><span class="sxs-lookup"><span data-stu-id="85cab-120">Select the existing table or view that contains the column to be profiled.</span></span>  
  
 <span data-ttu-id="85cab-121">Per ulteriori informazioni, vedere la sezione "Opzioni TableorView" in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="85cab-121">For more information, see the section, "TableorView Options," in this topic.</span></span>  
  
 <span data-ttu-id="85cab-122">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="85cab-122">**Column**</span></span>  
 <span data-ttu-id="85cab-123">Consente di selezionare la colonna esistente da analizzare.</span><span class="sxs-lookup"><span data-stu-id="85cab-123">Select the existing column to be profiled.</span></span> <span data-ttu-id="85cab-124">Selezionare **(\*)** per analizzare tutte le colonne.</span><span class="sxs-lookup"><span data-stu-id="85cab-124">Select **(\*)** to profile all columns.</span></span>  
  
 <span data-ttu-id="85cab-125">Per ulteriori informazioni, vedere la sezione "Opzioni Column" in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="85cab-125">For more information, see the section, "Column Options," in this topic.</span></span>  
  
#### <a name="tableorview-options"></a><span data-ttu-id="85cab-126">Opzioni TableOrView</span><span class="sxs-lookup"><span data-stu-id="85cab-126">TableOrView Options</span></span>  
 <span data-ttu-id="85cab-127">**Schema**</span><span class="sxs-lookup"><span data-stu-id="85cab-127">**Schema**</span></span>  
 <span data-ttu-id="85cab-128">Specifica lo schema a cui appartiene la tabella selezionata.</span><span class="sxs-lookup"><span data-stu-id="85cab-128">Specify the schema to which the selected table belongs.</span></span> <span data-ttu-id="85cab-129">Questa opzione è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="85cab-129">This option is read-only.</span></span>  
  
 <span data-ttu-id="85cab-130">**Tabella**</span><span class="sxs-lookup"><span data-stu-id="85cab-130">**Table**</span></span>  
 <span data-ttu-id="85cab-131">Visualizza il nome della tabella selezionata.</span><span class="sxs-lookup"><span data-stu-id="85cab-131">Displays the name of the selected table.</span></span> <span data-ttu-id="85cab-132">Questa opzione è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="85cab-132">This option is read-only.</span></span>  
  
#### <a name="column-options"></a><span data-ttu-id="85cab-133">Opzioni relative alle colonne</span><span class="sxs-lookup"><span data-stu-id="85cab-133">Column Options</span></span>  
 <span data-ttu-id="85cab-134">**IsWildCard**</span><span class="sxs-lookup"><span data-stu-id="85cab-134">**IsWildCard**</span></span>  
 <span data-ttu-id="85cab-135">Specifica se è stato selezionato il carattere jolly **(\*)** .</span><span class="sxs-lookup"><span data-stu-id="85cab-135">Specifies whether the **(\*)** wildcard has been selected.</span></span> <span data-ttu-id="85cab-136">Questa opzione è impostata su **True** se è stato selezionato **(\*)** per profilare tutte le colonne.</span><span class="sxs-lookup"><span data-stu-id="85cab-136">This option is set to **True** if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="85cab-137">È impostata su **False** se è stata selezionata una singola colonna da analizzare.</span><span class="sxs-lookup"><span data-stu-id="85cab-137">It is **False** if you have selected an individual column to be profiled.</span></span> <span data-ttu-id="85cab-138">Questa opzione è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="85cab-138">This option is read-only.</span></span>  
  
 <span data-ttu-id="85cab-139">**ColumnName**</span><span class="sxs-lookup"><span data-stu-id="85cab-139">**ColumnName**</span></span>  
 <span data-ttu-id="85cab-140">Visualizza il nome della colonna selezionata.</span><span class="sxs-lookup"><span data-stu-id="85cab-140">Displays the name of the selected column.</span></span> <span data-ttu-id="85cab-141">È vuota se è stato selezionato **(\*)** per profilare tutte le colonne.</span><span class="sxs-lookup"><span data-stu-id="85cab-141">This option is blank if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="85cab-142">Questa opzione è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="85cab-142">This option is read-only.</span></span>  
  
 <span data-ttu-id="85cab-143">**StringCompareOptions**</span><span class="sxs-lookup"><span data-stu-id="85cab-143">**StringCompareOptions**</span></span>  
 <span data-ttu-id="85cab-144">Questa opzione non si applica al profilo Distribuzione lunghezze di colonna.</span><span class="sxs-lookup"><span data-stu-id="85cab-144">This option does not apply to the Column Length Distribution Profile.</span></span>  
  
### <a name="general-options"></a><span data-ttu-id="85cab-145">Opzioni generali</span><span class="sxs-lookup"><span data-stu-id="85cab-145">General Options</span></span>  
 <span data-ttu-id="85cab-146">**RequestID**</span><span class="sxs-lookup"><span data-stu-id="85cab-146">**RequestID**</span></span>  
 <span data-ttu-id="85cab-147">Nome descrittivo per identificare la richiesta di profilo.</span><span class="sxs-lookup"><span data-stu-id="85cab-147">Type a descriptive name to identify this profile request.</span></span> <span data-ttu-id="85cab-148">Non è in genere necessario modificare il valore generato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="85cab-148">Typically, you do not have to change the autogenerated value.</span></span>  
  
### <a name="options"></a><span data-ttu-id="85cab-149">Opzioni</span><span class="sxs-lookup"><span data-stu-id="85cab-149">Options</span></span>  
 <span data-ttu-id="85cab-150">**IgnoreLeadingSpaces**</span><span class="sxs-lookup"><span data-stu-id="85cab-150">**IgnoreLeadingSpaces**</span></span>  
 <span data-ttu-id="85cab-151">Indica se ignorare gli spazi iniziali quando il profilo confronta i valori stringa.</span><span class="sxs-lookup"><span data-stu-id="85cab-151">Indicate whether to ignore leading spaces when the profile compares string values.</span></span> <span data-ttu-id="85cab-152">Il valore predefinito di questa opzione è **False**.</span><span class="sxs-lookup"><span data-stu-id="85cab-152">The default value of this option is **False**.</span></span>  
  
 <span data-ttu-id="85cab-153">**IgnoreTrailingSpaces**</span><span class="sxs-lookup"><span data-stu-id="85cab-153">**IgnoreTrailingSpaces**</span></span>  
 <span data-ttu-id="85cab-154">Indica se ignorare gli spazi finali quando il profilo confronta i valori stringa.</span><span class="sxs-lookup"><span data-stu-id="85cab-154">Indicate whether to ignore trailing spaces when the profile compares string values.</span></span> <span data-ttu-id="85cab-155">Il valore predefinito di questa opzione è **True**.</span><span class="sxs-lookup"><span data-stu-id="85cab-155">The default value of this option is **True**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85cab-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85cab-156">See Also</span></span>  
 <span data-ttu-id="85cab-157">[Editor attività Profiling dati &#40;pagina Generale&#41;](../general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="85cab-157">[Data Profiling Task Editor &#40;General Page&#41;](../general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="85cab-158">Form profilo rapido singola tabella &#40;Attività Profiling dati&#41;</span><span class="sxs-lookup"><span data-stu-id="85cab-158">Single Table Quick Profile Form &#40;Data Profiling Task&#41;</span></span>](single-table-quick-profile-form-data-profiling-task.md)  
  
  
