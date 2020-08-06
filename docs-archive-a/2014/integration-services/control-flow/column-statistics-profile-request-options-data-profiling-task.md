---
title: Opzioni di Richiesta profilo Statistiche di colonna (Attività Profiling dati) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling Task Editor
ms.assetid: 87205984-507a-49f3-b27c-36a0075c234d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9ce5c062a12e38d147f3cef95ea09b4c80f7c256
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627937"
---
# <a name="column-statistics-profile-request-options-data-profiling-task"></a><span data-ttu-id="9fc11-102">Opzioni di Richiesta profilo Statistiche di colonna (Attività Profiling dati)</span><span class="sxs-lookup"><span data-stu-id="9fc11-102">Column Statistics Profile Request Options (Data Profiling Task)</span></span>
  <span data-ttu-id="9fc11-103">Usare il riquadro **Proprietà richiesta** della pagina **Richieste profilo** per impostare le opzioni di **Richiesta profilo Statistiche di colonna** selezionata nel riquadro delle richieste.</span><span class="sxs-lookup"><span data-stu-id="9fc11-103">Use the **Request Properties** pane of the **Profile Requests** page to set the options for the **Column Statistics Profile Request** selected in the requests pane.</span></span> <span data-ttu-id="9fc11-104">Il profilo Statistiche di colonna segnala le statistiche, ad esempio relative a deviazione minima, massima, media e standard, per le colonne numeriche, nonché la deviazione minima e massima per le colonne di tipo `datetime`.</span><span class="sxs-lookup"><span data-stu-id="9fc11-104">A Column Statistics profile reports statistics such as minimum, maximum, average, and standard deviation for numeric columns, and minimum and maximum for `datetime` columns.</span></span> <span data-ttu-id="9fc11-105">Consente inoltre di identificare eventuali problemi nei dati, ad esempio le date non valide.</span><span class="sxs-lookup"><span data-stu-id="9fc11-105">This profile can help you identify problems in your data such as invalid dates.</span></span> <span data-ttu-id="9fc11-106">Si analizza, ad esempio, una colonna di date cronologiche e si individua una data massima successiva alla data corrente.</span><span class="sxs-lookup"><span data-stu-id="9fc11-106">For example, you profile a column of historical dates and discover a maximum date that is in the future.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9fc11-107">Le opzioni descritte in questo argomento vengono visualizzate nella pagina **Richieste profilo** in **Editor attività Profiling dati**.</span><span class="sxs-lookup"><span data-stu-id="9fc11-107">The options described in this topic appear on the **Profile Requests page** of the **Data Profiling Task Editor**.</span></span> <span data-ttu-id="9fc11-108">Per altre informazioni su questa pagina dell'editor, vedere [Editor attività Profiling dati &#40;pagina Richieste profilo&#41;](data-profiling-task-editor-profile-requests-page.md).</span><span class="sxs-lookup"><span data-stu-id="9fc11-108">For more information about this page of the editor, see [Data Profiling Task Editor &#40;Profile Requests Page&#41;](data-profiling-task-editor-profile-requests-page.md).</span></span>  
  
 <span data-ttu-id="9fc11-109">Per altre informazioni su come usare l'attività Profiling dati, vedere [Impostazione dell'attività Profiling dati](data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="9fc11-109">For more information about how to use the Data Profiling Task, see [Setup of the Data Profiling Task](data-profiling-task.md).</span></span> <span data-ttu-id="9fc11-110">Per altre informazioni sull'uso del Visualizzatore profilo dati per analizzare l'output dell'attività Profiling dati, vedere [Visualizzatore profilo dati](data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="9fc11-110">For more information about how to use the Data Profile Viewer to analyze the output of the Data Profiling Task, see [Data Profile Viewer](data-profile-viewer.md).</span></span>  
  
## <a name="request-properties-options"></a><span data-ttu-id="9fc11-111">Opzioni del riquadro Proprietà richiesta</span><span class="sxs-lookup"><span data-stu-id="9fc11-111">Request Properties Options</span></span>  
 <span data-ttu-id="9fc11-112">Nel riquadro **Proprietà richiesta**per **Richiesta profilo Statistiche di colonna** vengono visualizzati i gruppi di opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9fc11-112">For a **Column Statistics Profile Request**, the **Request Properties** pane displays the following groups of options:</span></span>  
  
-   <span data-ttu-id="9fc11-113">**Dati**che include le opzioni **TableOrView** e **Column**</span><span class="sxs-lookup"><span data-stu-id="9fc11-113">**Data**, which includes the **TableOrView** and **Column** options</span></span>  
  
-   <span data-ttu-id="9fc11-114">**Generale**</span><span class="sxs-lookup"><span data-stu-id="9fc11-114">**General**</span></span>  
  
### <a name="data-options"></a><span data-ttu-id="9fc11-115">Opzioni dati</span><span class="sxs-lookup"><span data-stu-id="9fc11-115">Data Options</span></span>  
 <span data-ttu-id="9fc11-116">**ConnectionManager**</span><span class="sxs-lookup"><span data-stu-id="9fc11-116">**ConnectionManager**</span></span>  
 <span data-ttu-id="9fc11-117">Consente di selezionare la gestione connessione [!INCLUDE[vstecado](../../includes/vstecado-md.md)] esistente che usa il provider di dati .NET per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) ai fini della connessione al database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] contenente la tabella o la vista di cui eseguire il profiling.</span><span class="sxs-lookup"><span data-stu-id="9fc11-117">Select the existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the .NET Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that contains the table or view to be profiled.</span></span>  
  
 <span data-ttu-id="9fc11-118">**TableOrView**</span><span class="sxs-lookup"><span data-stu-id="9fc11-118">**TableOrView**</span></span>  
 <span data-ttu-id="9fc11-119">Consente di selezionare la tabella o la vista esistente che contiene la colonna da analizzare.</span><span class="sxs-lookup"><span data-stu-id="9fc11-119">Select the existing table or view that contains the column to be profiled.</span></span>  
  
 <span data-ttu-id="9fc11-120">Per ulteriori informazioni, vedere la sezione "Opzioni TableorView" in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="9fc11-120">For more information, see the section, "TableorView Options," in this topic.</span></span>  
  
 <span data-ttu-id="9fc11-121">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="9fc11-121">**Column**</span></span>  
 <span data-ttu-id="9fc11-122">Consente di selezionare la colonna esistente da analizzare.</span><span class="sxs-lookup"><span data-stu-id="9fc11-122">Select the existing column to be profiled.</span></span> <span data-ttu-id="9fc11-123">Selezionare **(\*)** per analizzare tutte le colonne.</span><span class="sxs-lookup"><span data-stu-id="9fc11-123">Select **(\*)** to profile all columns.</span></span>  
  
 <span data-ttu-id="9fc11-124">Per ulteriori informazioni, vedere la sezione "Opzioni Column" in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="9fc11-124">For more information, see the section, "Column Options," in this topic.</span></span>  
  
#### <a name="tableorview-options"></a><span data-ttu-id="9fc11-125">Opzioni TableOrView</span><span class="sxs-lookup"><span data-stu-id="9fc11-125">TableOrView Options</span></span>  
 <span data-ttu-id="9fc11-126">**Schema**</span><span class="sxs-lookup"><span data-stu-id="9fc11-126">**Schema**</span></span>  
 <span data-ttu-id="9fc11-127">Specifica lo schema a cui appartiene la tabella selezionata.</span><span class="sxs-lookup"><span data-stu-id="9fc11-127">Specifies the schema to which the selected table belongs.</span></span> <span data-ttu-id="9fc11-128">Questa opzione è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="9fc11-128">This option is read-only.</span></span>  
  
 <span data-ttu-id="9fc11-129">**Tabella**</span><span class="sxs-lookup"><span data-stu-id="9fc11-129">**Table**</span></span>  
 <span data-ttu-id="9fc11-130">Visualizza il nome della tabella selezionata.</span><span class="sxs-lookup"><span data-stu-id="9fc11-130">Displays the name of the selected table.</span></span> <span data-ttu-id="9fc11-131">Questa opzione è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="9fc11-131">This option is read-only.</span></span>  
  
#### <a name="column-options"></a><span data-ttu-id="9fc11-132">Opzioni relative alle colonne</span><span class="sxs-lookup"><span data-stu-id="9fc11-132">Column Options</span></span>  
 <span data-ttu-id="9fc11-133">**IsWildCard**</span><span class="sxs-lookup"><span data-stu-id="9fc11-133">**IsWildCard**</span></span>  
 <span data-ttu-id="9fc11-134">Specifica se è stato selezionato il carattere jolly **(\*)** .</span><span class="sxs-lookup"><span data-stu-id="9fc11-134">Specifies whether the **(\*)** wildcard has been selected.</span></span> <span data-ttu-id="9fc11-135">Questa opzione è impostata su **True** se è stato selezionato **(\*)** per profilare tutte le colonne.</span><span class="sxs-lookup"><span data-stu-id="9fc11-135">This option is set to **True** if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="9fc11-136">È impostata su **False** se è stata selezionata una singola colonna da analizzare.</span><span class="sxs-lookup"><span data-stu-id="9fc11-136">It is **False** if you have selected an individual column to be profiled.</span></span> <span data-ttu-id="9fc11-137">Questa opzione è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="9fc11-137">This option is read-only.</span></span>  
  
 <span data-ttu-id="9fc11-138">**ColumnName**</span><span class="sxs-lookup"><span data-stu-id="9fc11-138">**ColumnName**</span></span>  
 <span data-ttu-id="9fc11-139">Visualizza il nome della colonna selezionata.</span><span class="sxs-lookup"><span data-stu-id="9fc11-139">Displays the name of the selected column.</span></span> <span data-ttu-id="9fc11-140">È vuota se è stato selezionato **(\*)** per profilare tutte le colonne.</span><span class="sxs-lookup"><span data-stu-id="9fc11-140">This option is blank if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="9fc11-141">Questa opzione è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="9fc11-141">This option is read-only.</span></span>  
  
 <span data-ttu-id="9fc11-142">**StringCompareOptions**</span><span class="sxs-lookup"><span data-stu-id="9fc11-142">**StringCompareOptions**</span></span>  
 <span data-ttu-id="9fc11-143">Questa opzione non si applica al profilo Statistiche di colonna.</span><span class="sxs-lookup"><span data-stu-id="9fc11-143">This option does not apply to the Column Statistics Profile.</span></span>  
  
### <a name="general-options"></a><span data-ttu-id="9fc11-144">Opzioni generali</span><span class="sxs-lookup"><span data-stu-id="9fc11-144">General Options</span></span>  
 <span data-ttu-id="9fc11-145">**RequestID**</span><span class="sxs-lookup"><span data-stu-id="9fc11-145">**RequestID**</span></span>  
 <span data-ttu-id="9fc11-146">Nome descrittivo per identificare la richiesta di profilo.</span><span class="sxs-lookup"><span data-stu-id="9fc11-146">Type a descriptive name to identify this profile request.</span></span> <span data-ttu-id="9fc11-147">Non è in genere necessario modificare il valore generato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9fc11-147">Typically, you do not have to change the autogenerated value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fc11-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9fc11-148">See Also</span></span>  
 <span data-ttu-id="9fc11-149">[Editor attività Profiling dati &#40;pagina Generale&#41;](../general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="9fc11-149">[Data Profiling Task Editor &#40;General Page&#41;](../general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="9fc11-150">Form profilo rapido singola tabella &#40;Attività Profiling dati&#41;</span><span class="sxs-lookup"><span data-stu-id="9fc11-150">Single Table Quick Profile Form &#40;Data Profiling Task&#41;</span></span>](single-table-quick-profile-form-data-profiling-task.md)  
  
  
