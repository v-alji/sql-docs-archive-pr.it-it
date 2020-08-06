---
title: Guida sensibile al contesto Visualizzatore profilo dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dataprofileviewer.f1
helpviewer_keywords:
- Data Profile Viewer [Integration Services]
- Data Profiling task [Integration Services], viewer
ms.assetid: 3469c60a-8f4f-46ba-999a-cb9070197fea
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7003e1299938bd53a6d16a5597d4566ba5c46579
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625481"
---
# <a name="data-profile-viewer-f1-help"></a><span data-ttu-id="6ef28-102">Guida sensibile al contesto del Visualizzatore profilo dati</span><span class="sxs-lookup"><span data-stu-id="6ef28-102">Data Profile Viewer F1 Help</span></span>
  <span data-ttu-id="6ef28-103">Utilizzare il Visualizzatore profilo dati per visualizzare l'output dell'attività Profiling dati.</span><span class="sxs-lookup"><span data-stu-id="6ef28-103">Use the Data Profile Viewer to view the output of the Data Profiling task.</span></span>  
  
 <span data-ttu-id="6ef28-104">Per altre informazioni sull'uso del Visualizzatore profilo dati, vedere [Visualizzatore profilo dati](control-flow/data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="6ef28-104">For more information about how to use the Data Profile Viewer, see [Data Profile Viewer](control-flow/data-profile-viewer.md).</span></span> <span data-ttu-id="6ef28-105">Per altre informazioni sull'uso dell'attività Profiling dati che crea l'output del profilo analizzato nel Visualizzatore profilo dati, vedere [Impostazione dell'attività Profiling Dati](control-flow/data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="6ef28-105">For more information about how to use the Data Profiling task, which creates the profile output that you analyze in the Data Profile Viewer, see [Setup of the Data Profiling Task](control-flow/data-profiling-task.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="6ef28-106">Opzioni statiche</span><span class="sxs-lookup"><span data-stu-id="6ef28-106">Static Options</span></span>  
 <span data-ttu-id="6ef28-107">**Apri**</span><span class="sxs-lookup"><span data-stu-id="6ef28-107">**Open**</span></span>  
 <span data-ttu-id="6ef28-108">Consente di accedere al file salvato che contiene l'output dell'attività Profiling dati.</span><span class="sxs-lookup"><span data-stu-id="6ef28-108">Click to browse for the saved file that contains the output of the Data Profiling task.</span></span>  
  
 <span data-ttu-id="6ef28-109">Riquadro**Profili**</span><span class="sxs-lookup"><span data-stu-id="6ef28-109">**Profiles** pane</span></span>  
 <span data-ttu-id="6ef28-110">Espandere l'albero nel riquadro **Profili** per visualizzare i profili inclusi nell'output.</span><span class="sxs-lookup"><span data-stu-id="6ef28-110">Expand the tree in the **Profiles** pane to see the profiles that are included in the output.</span></span> <span data-ttu-id="6ef28-111">Selezionare un profilo per visualizzarne i risultati.</span><span class="sxs-lookup"><span data-stu-id="6ef28-111">Select a profile to view the results for that profile.</span></span>  
  
 <span data-ttu-id="6ef28-112">Riquadro**Messaggio**</span><span class="sxs-lookup"><span data-stu-id="6ef28-112">**Message** pane</span></span>  
 <span data-ttu-id="6ef28-113">Visualizza i messaggi di stato.</span><span class="sxs-lookup"><span data-stu-id="6ef28-113">Displays status messages.</span></span>  
  
 <span data-ttu-id="6ef28-114">Riquadro**Drill-down**</span><span class="sxs-lookup"><span data-stu-id="6ef28-114">**Drilldown** pane</span></span>  
 <span data-ttu-id="6ef28-115">Visualizza le righe di dati che corrispondono a un valore nell'output, se l'origine dati utilizzata dall'attività Profiling dati è disponibile.</span><span class="sxs-lookup"><span data-stu-id="6ef28-115">Displays the rows of data that match a value in the output, if the data source that is used by the Data Profiling task is available.</span></span>  
  
 <span data-ttu-id="6ef28-116">Se, ad esempio, si visualizza l'output di un profilo Distribuzione valori di colonna per una colonna US State, il riquadro **Distribuzione dettagliata valori** potrebbe contenere una riga per "WA".</span><span class="sxs-lookup"><span data-stu-id="6ef28-116">For example, if you are viewing the output of a Column Value Distribution profile for a US State column, the **Detailed Value Distribution** pane might contain a row for "WA".</span></span> <span data-ttu-id="6ef28-117">Fare doppio clic sulla riga nel riquadro **Distribuzione dettagliata valori** per visualizzare le righe di dati in cui il valore della colonna di stato è "WA" nel riquadro di drill-down.</span><span class="sxs-lookup"><span data-stu-id="6ef28-117">Double-click the row in the **Detailed Value Distribution** pane to see the rows of data where the value of the state column is "WA" in the drilldown pane.</span></span>  
  
## <a name="dynamic-options"></a><span data-ttu-id="6ef28-118">Opzioni dinamiche</span><span class="sxs-lookup"><span data-stu-id="6ef28-118">Dynamic Options</span></span>  
  
### <a name="profile-type--column-length-distribution-profile"></a><span data-ttu-id="6ef28-119">Tipo di profilo: profilo Distribuzione lunghezze di colonna</span><span class="sxs-lookup"><span data-stu-id="6ef28-119">Profile Type = Column Length Distribution Profile</span></span>  
  
#### <a name="column-length-distribution-profile---column-pane"></a><span data-ttu-id="6ef28-120">Profilo Distribuzione lunghezze di colonna - Riquadro \<column></span><span class="sxs-lookup"><span data-stu-id="6ef28-120">Column Length Distribution Profile - \<column> pane</span></span>  
 <span data-ttu-id="6ef28-121">**Lunghezza minima**</span><span class="sxs-lookup"><span data-stu-id="6ef28-121">**Minimum Length**</span></span>  
 <span data-ttu-id="6ef28-122">Visualizza la lunghezza minima dei valori nella colonna.</span><span class="sxs-lookup"><span data-stu-id="6ef28-122">Displays the minimum length of values in this column.</span></span>  
  
 <span data-ttu-id="6ef28-123">**Lunghezza massima**</span><span class="sxs-lookup"><span data-stu-id="6ef28-123">**Maximum Length**</span></span>  
 <span data-ttu-id="6ef28-124">Visualizza la lunghezza massima dei valori nella colonna.</span><span class="sxs-lookup"><span data-stu-id="6ef28-124">Displays the maximum length of values in this column.</span></span>  
  
 <span data-ttu-id="6ef28-125">**Ignora spazi iniziali**</span><span class="sxs-lookup"><span data-stu-id="6ef28-125">**Ignore Leading Spaces**</span></span>  
 <span data-ttu-id="6ef28-126">Indica se il profilo è stato calcolato con un valore `IgnoreLeadingSpaces` impostato su True o False.</span><span class="sxs-lookup"><span data-stu-id="6ef28-126">Displays whether this profile was computed with an `IgnoreLeadingSpaces` value of True or False.</span></span> <span data-ttu-id="6ef28-127">Questa proprietà è stata impostata nella pagina **Richieste profilo** in Editor attività Profiling dati.</span><span class="sxs-lookup"><span data-stu-id="6ef28-127">This property was set on the **Profile Requests** page of the Data Profiling Task Editor.</span></span>  
  
 <span data-ttu-id="6ef28-128">**Ignora spazi finali**</span><span class="sxs-lookup"><span data-stu-id="6ef28-128">**Ignore Trailing Spaces**</span></span>  
 <span data-ttu-id="6ef28-129">Indica se il profilo è stato calcolato con un valore `IgnoreTrailingSpaces` impostato su True o False.</span><span class="sxs-lookup"><span data-stu-id="6ef28-129">Displays whether this profile was computed with an `IgnoreTrailingSpaces` value of True or False.</span></span> <span data-ttu-id="6ef28-130">Questa proprietà è stata impostata nella pagina **Richieste profilo** in Editor attività Profiling dati.</span><span class="sxs-lookup"><span data-stu-id="6ef28-130">This property was set on the **Profile Requests** page of the Data Profiling Task Editor.</span></span>  
  
 <span data-ttu-id="6ef28-131">**Conteggio righe**</span><span class="sxs-lookup"><span data-stu-id="6ef28-131">**Row Count**</span></span>  
 <span data-ttu-id="6ef28-132">Visualizza il numero di righe della tabella o della vista.</span><span class="sxs-lookup"><span data-stu-id="6ef28-132">Displays the number of rows in the table or view.</span></span>  
  
#### <a name="detailed-length-distribution-pane"></a><span data-ttu-id="6ef28-133">Riquadro Distribuzione dettagliata lunghezze</span><span class="sxs-lookup"><span data-stu-id="6ef28-133">Detailed Length Distribution pane</span></span>  
 <span data-ttu-id="6ef28-134">**Lunghezza**</span><span class="sxs-lookup"><span data-stu-id="6ef28-134">**Length**</span></span>  
 <span data-ttu-id="6ef28-135">Visualizza le lunghezze di colonna rilevate nella colonna analizzata.</span><span class="sxs-lookup"><span data-stu-id="6ef28-135">Displays the column lengths found in the profiled column.</span></span>  
  
 <span data-ttu-id="6ef28-136">**Numero**</span><span class="sxs-lookup"><span data-stu-id="6ef28-136">**Count**</span></span>  
 <span data-ttu-id="6ef28-137">Visualizza il numero di righe in cui il valore della colonna analizzata ha la lunghezza indicata nella colonna **Lunghezza** .</span><span class="sxs-lookup"><span data-stu-id="6ef28-137">Displays the number of rows in which the value of the profiled column has the length shown in the **Length** column.</span></span>  
  
 <span data-ttu-id="6ef28-138">**Percentuale**</span><span class="sxs-lookup"><span data-stu-id="6ef28-138">**Percentage**</span></span>  
 <span data-ttu-id="6ef28-139">Visualizza la percentuale di righe in cui il valore della colonna analizzata ha la lunghezza indicata nella colonna **Lunghezza** .</span><span class="sxs-lookup"><span data-stu-id="6ef28-139">Displays the percentage of rows in which the value of the profiled column has the length shown in the **Length** column.</span></span>  
  
### <a name="profile-type--column-null-ratio-profile"></a><span data-ttu-id="6ef28-140">Tipo di profilo: profilo Rapporto di valori Null nella colonna</span><span class="sxs-lookup"><span data-stu-id="6ef28-140">Profile Type = Column Null Ratio Profile</span></span>  
  
#### <a name="column-null-ratio-profile---column-pane"></a><span data-ttu-id="6ef28-141">Profilo Rapporto di valori Null nella colonna - Riquadro \<column></span><span class="sxs-lookup"><span data-stu-id="6ef28-141">Column Null Ratio Profile - \<column> pane</span></span>  
 <span data-ttu-id="6ef28-142">**Conteggio valori Null**</span><span class="sxs-lookup"><span data-stu-id="6ef28-142">**Null Count**</span></span>  
 <span data-ttu-id="6ef28-143">Visualizza il numero di righe in cui il valore della colonna analizzata è un valore Null.</span><span class="sxs-lookup"><span data-stu-id="6ef28-143">Displays the number of rows in which the profiled column has a null value.</span></span>  
  
 <span data-ttu-id="6ef28-144">**Percentuale valori Null**</span><span class="sxs-lookup"><span data-stu-id="6ef28-144">**Null Percentage**</span></span>  
 <span data-ttu-id="6ef28-145">Visualizza la percentuale di righe in cui il valore della colonna analizzata è un valore Null.</span><span class="sxs-lookup"><span data-stu-id="6ef28-145">Displays the percentage of rows in which the profiled column has a null value.</span></span>  
  
 <span data-ttu-id="6ef28-146">**Conteggio righe**</span><span class="sxs-lookup"><span data-stu-id="6ef28-146">**Row Count**</span></span>  
 <span data-ttu-id="6ef28-147">Visualizza il numero di righe della tabella o della vista.</span><span class="sxs-lookup"><span data-stu-id="6ef28-147">Displays the number of rows in the table or view.</span></span>  
  
### <a name="profile-type--column-pattern-profile"></a><span data-ttu-id="6ef28-148">Tipo di profilo: profilo Criteri di ricerca colonna</span><span class="sxs-lookup"><span data-stu-id="6ef28-148">Profile Type = Column Pattern Profile</span></span>  
  
#### <a name="column-pattern-profile---column-pane"></a><span data-ttu-id="6ef28-149">Profilo Criteri di ricerca colonna - Riquadro \<column></span><span class="sxs-lookup"><span data-stu-id="6ef28-149">Column Pattern Profile - \<column> pane</span></span>  
 <span data-ttu-id="6ef28-150">**Conteggio righe**</span><span class="sxs-lookup"><span data-stu-id="6ef28-150">**Row Count**</span></span>  
 <span data-ttu-id="6ef28-151">Visualizza il numero di righe della tabella o della vista.</span><span class="sxs-lookup"><span data-stu-id="6ef28-151">Displays the number of rows in the table or view.</span></span>  
  
#### <a name="pattern-distribution-pane"></a><span data-ttu-id="6ef28-152">Riquadro Distribuzione criteri di ricerca</span><span class="sxs-lookup"><span data-stu-id="6ef28-152">Pattern Distribution pane</span></span>  
 <span data-ttu-id="6ef28-153">**Modello**</span><span class="sxs-lookup"><span data-stu-id="6ef28-153">**Pattern**</span></span>  
 <span data-ttu-id="6ef28-154">Visualizza i modelli calcolati per la colonna analizzata.</span><span class="sxs-lookup"><span data-stu-id="6ef28-154">Displays the patterns computed for the profiled column.</span></span>  
  
 <span data-ttu-id="6ef28-155">**Percentuale**</span><span class="sxs-lookup"><span data-stu-id="6ef28-155">**Percentage**</span></span>  
 <span data-ttu-id="6ef28-156">Visualizza la percentuale di righe i cui valori corrispondono al modello visualizzato nella colonna **Modello** .</span><span class="sxs-lookup"><span data-stu-id="6ef28-156">Displays the percentage of rows whose values match the pattern displayed in the **Pattern** column.</span></span>  
  
### <a name="profile-type--column-statistics-profile"></a><span data-ttu-id="6ef28-157">Tipo di profilo: profilo Statistiche di colonna</span><span class="sxs-lookup"><span data-stu-id="6ef28-157">Profile Type = Column Statistics Profile</span></span>  
  
#### <a name="column-statistics-profile---column-pane"></a><span data-ttu-id="6ef28-158">Profilo Statistiche di colonna - Riquadro \<column></span><span class="sxs-lookup"><span data-stu-id="6ef28-158">Column Statistics Profile - \<column> pane</span></span>  
 <span data-ttu-id="6ef28-159">**Minimi**</span><span class="sxs-lookup"><span data-stu-id="6ef28-159">**Minimum**</span></span>  
 <span data-ttu-id="6ef28-160">Visualizza il valore minimo rilevato nella colonna analizzata.</span><span class="sxs-lookup"><span data-stu-id="6ef28-160">Displays the minimum value found in the profiled column.</span></span>  
  
 <span data-ttu-id="6ef28-161">**Massimo**</span><span class="sxs-lookup"><span data-stu-id="6ef28-161">**Maximum**</span></span>  
 <span data-ttu-id="6ef28-162">Visualizza il valore massimo rilevato nella colonna analizzata.</span><span class="sxs-lookup"><span data-stu-id="6ef28-162">Displays the maximum value found in the profiled column.</span></span>  
  
 <span data-ttu-id="6ef28-163">**Media**</span><span class="sxs-lookup"><span data-stu-id="6ef28-163">**Mean**</span></span>  
 <span data-ttu-id="6ef28-164">Visualizza la media dei valori rilevati nella colonna analizzata.</span><span class="sxs-lookup"><span data-stu-id="6ef28-164">Displays the mean of the values found in the profiled column.</span></span>  
  
 <span data-ttu-id="6ef28-165">**Deviazione standard**</span><span class="sxs-lookup"><span data-stu-id="6ef28-165">**Standard Deviation**</span></span>  
 <span data-ttu-id="6ef28-166">Visualizza la deviazione standard dei valori rilevati nella colonna analizzata.</span><span class="sxs-lookup"><span data-stu-id="6ef28-166">Displays the standard deviation of the values found in the profiled column.</span></span>  
  
### <a name="profile-type--column-value-distribution-profile"></a><span data-ttu-id="6ef28-167">Tipo di profilo: profilo Distribuzione valori di colonna</span><span class="sxs-lookup"><span data-stu-id="6ef28-167">Profile Type = Column Value Distribution Profile</span></span>  
  
#### <a name="column-value-distribution-profile---column-pane"></a><span data-ttu-id="6ef28-168">Profilo Distribuzione valori di colonna - Riquadro \<column></span><span class="sxs-lookup"><span data-stu-id="6ef28-168">Column Value Distribution Profile - \<column> pane</span></span>  
 <span data-ttu-id="6ef28-169">**Numero di valori distinct**</span><span class="sxs-lookup"><span data-stu-id="6ef28-169">**Number of Distinct Values**</span></span>  
 <span data-ttu-id="6ef28-170">Visualizza il conteggio dei valori distinct rilevati nella colonna analizzata.</span><span class="sxs-lookup"><span data-stu-id="6ef28-170">Displays the count of distinct values found in the profiled column.</span></span>  
  
 <span data-ttu-id="6ef28-171">**Conteggio righe**</span><span class="sxs-lookup"><span data-stu-id="6ef28-171">**Row Count**</span></span>  
 <span data-ttu-id="6ef28-172">Visualizza il numero di righe della tabella o della vista.</span><span class="sxs-lookup"><span data-stu-id="6ef28-172">Displays the number of rows in the table or view.</span></span>  
  
#### <a name="detailed-value-distribution-pane"></a><span data-ttu-id="6ef28-173">Riquadro Distribuzione dettagliata valori</span><span class="sxs-lookup"><span data-stu-id="6ef28-173">Detailed Value Distribution pane</span></span>  
 <span data-ttu-id="6ef28-174">**Valore**</span><span class="sxs-lookup"><span data-stu-id="6ef28-174">**Value**</span></span>  
 <span data-ttu-id="6ef28-175">Visualizza i valori distinct rilevati nella colonna analizzata.</span><span class="sxs-lookup"><span data-stu-id="6ef28-175">Displays the distinct values found in the profiled column.</span></span>  
  
 <span data-ttu-id="6ef28-176">**Numero**</span><span class="sxs-lookup"><span data-stu-id="6ef28-176">**Count**</span></span>  
 <span data-ttu-id="6ef28-177">Visualizza il numero di righe in cui la colonna analizzata ha il valore indicato nella colonna **Valore** .</span><span class="sxs-lookup"><span data-stu-id="6ef28-177">Displays the number of rows in which the profiled column has the value shown in the **Value** column.</span></span>  
  
 <span data-ttu-id="6ef28-178">**Percentuale**</span><span class="sxs-lookup"><span data-stu-id="6ef28-178">**Percentage**</span></span>  
 <span data-ttu-id="6ef28-179">Visualizza la percentuale di righe in cui la colonna analizzata ha il valore indicato nella colonna **Valore** .</span><span class="sxs-lookup"><span data-stu-id="6ef28-179">Displays the percentage of rows in which the profiled column has the value shown in the **Value** column.</span></span>  
  
### <a name="profile-type--candidate-key-profile"></a><span data-ttu-id="6ef28-180">Tipo di profilo: profilo Chiave candidata</span><span class="sxs-lookup"><span data-stu-id="6ef28-180">Profile Type = Candidate Key Profile</span></span>  
  
#### <a name="candidate-key-profile---table-pane"></a><span data-ttu-id="6ef28-181">Profilo Chiave candidata - Riquadro \<table></span><span class="sxs-lookup"><span data-stu-id="6ef28-181">Candidate Key Profile - \<table> pane</span></span>  
 <span data-ttu-id="6ef28-182">**Colonne chiave**</span><span class="sxs-lookup"><span data-stu-id="6ef28-182">**Key Columns**</span></span>  
 <span data-ttu-id="6ef28-183">Visualizza le colonne selezionate per l'analisi come chiave candidata.</span><span class="sxs-lookup"><span data-stu-id="6ef28-183">Displays the columns that were selected for profiling as a candidate key.</span></span>  
  
 <span data-ttu-id="6ef28-184">**Attendibilità chiave**</span><span class="sxs-lookup"><span data-stu-id="6ef28-184">**Key Strength**</span></span>  
 <span data-ttu-id="6ef28-185">Visualizza il livello di attendibilità (come percentuale) della colonna o combinazione di colonne chiave candidata.</span><span class="sxs-lookup"><span data-stu-id="6ef28-185">Displays the strength (as a percentage) of the candidate key column or combination of columns.</span></span> <span data-ttu-id="6ef28-186">Un livello di attendibilità inferiore al 100% indica la presenza di valori duplicati.</span><span class="sxs-lookup"><span data-stu-id="6ef28-186">A key strength of less than 100% indicates that duplicate values exist.</span></span>  
  
#### <a name="key-violations-pane"></a><span data-ttu-id="6ef28-187">Riquadro Violazioni chiave</span><span class="sxs-lookup"><span data-stu-id="6ef28-187">Key Violations pane</span></span>  
 <span data-ttu-id="6ef28-188">**\<column1>\<column2> così via.**</span><span class="sxs-lookup"><span data-stu-id="6ef28-188">**\<column1>, \<column2>, etc.**</span></span>  
 <span data-ttu-id="6ef28-189">Visualizza i valori duplicati rilevati nella colonna analizzata.</span><span class="sxs-lookup"><span data-stu-id="6ef28-189">Displays the duplicate values that were found in the profiled column.</span></span>  
  
 <span data-ttu-id="6ef28-190">**Numero**</span><span class="sxs-lookup"><span data-stu-id="6ef28-190">**Count**</span></span>  
 <span data-ttu-id="6ef28-191">Visualizza il numero di righe in cui la colonna specificata ha il valore indicato nella prima colonna.</span><span class="sxs-lookup"><span data-stu-id="6ef28-191">Displays the number of rows in which the specified column has the value shown in the first column.</span></span>  
  
### <a name="profile-type--functional-dependency-profile"></a><span data-ttu-id="6ef28-192">Tipo di profilo: profilo Dipendenza funzionale</span><span class="sxs-lookup"><span data-stu-id="6ef28-192">Profile Type = Functional Dependency Profile</span></span>  
  
#### <a name="functional-dependency-profile-pane"></a><span data-ttu-id="6ef28-193">Riquadro Profilo Dipendenza funzionale</span><span class="sxs-lookup"><span data-stu-id="6ef28-193">Functional Dependency Profile pane</span></span>  
 <span data-ttu-id="6ef28-194">**Colonne determinanti**</span><span class="sxs-lookup"><span data-stu-id="6ef28-194">**Determinant Columns**</span></span>  
 <span data-ttu-id="6ef28-195">Visualizza la colonna o le colonne selezionate come colonne determinanti.</span><span class="sxs-lookup"><span data-stu-id="6ef28-195">Displays the column or columns selected as the determinant column.</span></span> <span data-ttu-id="6ef28-196">Nell'esempio in cui uno stesso codice postale ZIP (Stati Uniti) deve essere associato sempre allo stesso stato, il codice postale rappresenta la colonna determinante.</span><span class="sxs-lookup"><span data-stu-id="6ef28-196">In the example where the same United States Zip Code should always have the same state, the Zip Code is the determinant column.</span></span>  
  
 <span data-ttu-id="6ef28-197">**Colonna dipendente**</span><span class="sxs-lookup"><span data-stu-id="6ef28-197">**Dependent Columns**</span></span>  
 <span data-ttu-id="6ef28-198">Visualizza la colonna o le colonne selezionate come colonne dipendenti.</span><span class="sxs-lookup"><span data-stu-id="6ef28-198">Displays the column or columns selected as the dependent column.</span></span> <span data-ttu-id="6ef28-199">Nell'esempio in cui uno stesso codice postale ZIP (Stati Uniti) deve essere associato sempre allo stesso stato, lo stato rappresenta la colonna dipendente.</span><span class="sxs-lookup"><span data-stu-id="6ef28-199">In the example where the same United States Zip Code should always have the same state, the state is the dependent column.</span></span>  
  
 <span data-ttu-id="6ef28-200">**Attendibilità dipendenza funzionale**</span><span class="sxs-lookup"><span data-stu-id="6ef28-200">**Functional Dependency Strength**</span></span>  
 <span data-ttu-id="6ef28-201">Visualizza il livello di attendibilità (come percentuale) della dipendenza funzionale tra colonne.</span><span class="sxs-lookup"><span data-stu-id="6ef28-201">Displays the strength (as a percentage) of the functional dependency between columns.</span></span> <span data-ttu-id="6ef28-202">Un livello di attendibilità inferiore al 100% indica che vi sono casi in cui il valore determinante non determina il valore dipendente.</span><span class="sxs-lookup"><span data-stu-id="6ef28-202">A key strength of less than 100% indicates that there are cases where the determinant value does not determine the dependent value.</span></span> <span data-ttu-id="6ef28-203">Nell'esempio in cui uno stesso codice postale ZIP (Stati Uniti) deve essere associato sempre allo stesso stato, tale livello di attendibilità indica che alcuni valori di stato non sono validi.</span><span class="sxs-lookup"><span data-stu-id="6ef28-203">In the example where the same United States Zip Code should always have the same state, this probably indicates some state values are not valid.</span></span>  
  
#### <a name="functional-dependency-violations-pane"></a><span data-ttu-id="6ef28-204">Riquadro Violazioni dipendenza funzionale</span><span class="sxs-lookup"><span data-stu-id="6ef28-204">Functional Dependency Violations pane</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6ef28-205">Una percentuale elevata di valori non corretti nei dati può provocare risultati imprevisti da un profilo Dipendenza funzionale.</span><span class="sxs-lookup"><span data-stu-id="6ef28-205">A high percentage of erroneous values in the data could lead to unexpected results from a Functional Dependency profile.</span></span> <span data-ttu-id="6ef28-206">Ad esempio, il 90% delle righe contiene il valore di stato "WI" per il valore di codice postale ZIP "98052".</span><span class="sxs-lookup"><span data-stu-id="6ef28-206">For example, 90% of the rows have a State value of "WI" for a Postal Code value of "98052."</span></span> <span data-ttu-id="6ef28-207">Il profilo segnala le righe che contengono il valore di stato "WA" corretto come violazioni.</span><span class="sxs-lookup"><span data-stu-id="6ef28-207">The profile reports rows that contain the correct state value of "WA" as violations.</span></span>  
  
 **\<determinant column name>**  
 <span data-ttu-id="6ef28-208">Visualizza il valore della colonna determinante o della combinazione di colonne determinanti in questa istanza di una violazione della dipendenza funzionale.</span><span class="sxs-lookup"><span data-stu-id="6ef28-208">Displays the value of the determinant column or combination of columns in this instance of a functional dependency violation.</span></span>  
  
 **\<dependent column name>**  
 <span data-ttu-id="6ef28-209">Visualizza il valore della colonna dipendente in questa istanza di una violazione della dipendenza funzionale.</span><span class="sxs-lookup"><span data-stu-id="6ef28-209">Displays the value of the dependent column in this instance of a functional dependency violation.</span></span>  
  
 <span data-ttu-id="6ef28-210">**Conteggio del supporto**</span><span class="sxs-lookup"><span data-stu-id="6ef28-210">**Support Count**</span></span>  
 <span data-ttu-id="6ef28-211">Visualizza il numero di righe in cui il valore della colonna determinante determina la colonna dipendente.</span><span class="sxs-lookup"><span data-stu-id="6ef28-211">Displays the number of rows in which the determinant column value determines the dependent column.</span></span>  
  
 <span data-ttu-id="6ef28-212">**Conteggio violazioni**</span><span class="sxs-lookup"><span data-stu-id="6ef28-212">**Violation Count**</span></span>  
 <span data-ttu-id="6ef28-213">Visualizza il numero di righe in cui il valore della colonna determinante non determina la colonna dipendente.</span><span class="sxs-lookup"><span data-stu-id="6ef28-213">Displays the number of rows in which the determinant column value does not determine the dependent column.</span></span> <span data-ttu-id="6ef28-214">Si tratta delle righe in cui i valori dipendenti corrispondono ai valori indicati nella colonna **\<dependent column name>** .</span><span class="sxs-lookup"><span data-stu-id="6ef28-214">(These are the rows where the dependent value is the value shown in the **\<dependent column name>** column.)</span></span>  
  
 <span data-ttu-id="6ef28-215">**Percentuale del supporto**</span><span class="sxs-lookup"><span data-stu-id="6ef28-215">**Support Percentage**</span></span>  
 <span data-ttu-id="6ef28-216">Visualizza la percentuale di righe in cui la colonna determinante determina la colonna dipendente.</span><span class="sxs-lookup"><span data-stu-id="6ef28-216">Displays the percentage of rows in which the determinant column determines the dependent column.</span></span>  
  
### <a name="profile-type--value-inclusion-profile"></a><span data-ttu-id="6ef28-217">Tipo di profilo: profilo Inclusione valore</span><span class="sxs-lookup"><span data-stu-id="6ef28-217">Profile Type = Value Inclusion Profile</span></span>  
  
#### <a name="value-inclusion-profile-pane"></a><span data-ttu-id="6ef28-218">Riquadro Profilo Inclusione valore</span><span class="sxs-lookup"><span data-stu-id="6ef28-218">Value Inclusion Profile pane</span></span>  
 <span data-ttu-id="6ef28-219">**Colonne lato subset**</span><span class="sxs-lookup"><span data-stu-id="6ef28-219">**Subset Side Columns**</span></span>  
 <span data-ttu-id="6ef28-220">Visualizza la colonna o la combinazione di colonne analizzate per determinare se sono incluse nelle colonne del superset.</span><span class="sxs-lookup"><span data-stu-id="6ef28-220">Displays the column or combination of columns that were profiled to determine whether they are in the superset columns.</span></span>  
  
 <span data-ttu-id="6ef28-221">**Colonne lato superset**</span><span class="sxs-lookup"><span data-stu-id="6ef28-221">**Superset Side Columns**</span></span>  
 <span data-ttu-id="6ef28-222">Visualizza la colonna o la combinazione di colonne analizzate per determinare se includono i valori delle colonne del subset.</span><span class="sxs-lookup"><span data-stu-id="6ef28-222">Displays the column or combination of columns that were profiled to determine whether they include the values in the subset columns.</span></span>  
  
 <span data-ttu-id="6ef28-223">**Attendibilità inclusione**</span><span class="sxs-lookup"><span data-stu-id="6ef28-223">**Inclusion Strength**</span></span>  
 <span data-ttu-id="6ef28-224">Visualizza il livello di attendibilità (come percentuale) della sovrapposizione tra colonne.</span><span class="sxs-lookup"><span data-stu-id="6ef28-224">Displays the strength (as a percentage) of the overlap between columns.</span></span> <span data-ttu-id="6ef28-225">Un livello di attendibilità inferiore al 100% indica che vi sono casi in cui il valore del subset non viene rilevato tra i valori del superset.</span><span class="sxs-lookup"><span data-stu-id="6ef28-225">A key strength of less than 100% indicates that there are cases where the subset value is not found among the superset values.</span></span>  
  
#### <a name="inclusion-violations-pane"></a><span data-ttu-id="6ef28-226">Riquadro Violazioni inclusione</span><span class="sxs-lookup"><span data-stu-id="6ef28-226">Inclusion Violations pane</span></span>  
 <span data-ttu-id="6ef28-227">**\<column1>\<column2> così via.**</span><span class="sxs-lookup"><span data-stu-id="6ef28-227">**\<column1>, \<column2>, etc.**</span></span>  
 <span data-ttu-id="6ef28-228">Visualizza i valori nella colonna o colonne del subset che non sono disponibili nella colonna o colonne del superset.</span><span class="sxs-lookup"><span data-stu-id="6ef28-228">Displays the values in the subset column or columns that were not found in the superset column or columns.</span></span>  
  
 <span data-ttu-id="6ef28-229">**Numero**</span><span class="sxs-lookup"><span data-stu-id="6ef28-229">**Count**</span></span>  
 <span data-ttu-id="6ef28-230">Visualizza il numero di righe in cui la colonna specificata ha il valore indicato nella prima colonna.</span><span class="sxs-lookup"><span data-stu-id="6ef28-230">Displays the number of rows in which the specified column has the value shown in the first column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ef28-231">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ef28-231">See Also</span></span>  
 <span data-ttu-id="6ef28-232">[Visualizzatore profilo dati](control-flow/data-profile-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="6ef28-232">[Data Profile Viewer](control-flow/data-profile-viewer.md) </span></span>  
 [<span data-ttu-id="6ef28-233">Attività Profiling dati e visualizzatore</span><span class="sxs-lookup"><span data-stu-id="6ef28-233">Data Profiling Task and Viewer</span></span>](control-flow/data-profiling-task-and-viewer.md)  
  
  
