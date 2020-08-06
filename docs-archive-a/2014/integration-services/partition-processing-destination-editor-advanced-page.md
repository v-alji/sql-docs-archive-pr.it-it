---
title: Editor destinazione elaborazione partizione (pagina Avanzate) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.partprocessingtransformation.advanced.f1
helpviewer_keywords:
- Partition Processing Destination Editor
ms.assetid: 2039ee0f-069d-479d-90b2-2a12481b1162
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 12845ecd644eabd949ea37fbb18ba6cc9cf342f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624803"
---
# <a name="partition-processing-destination-editor-advanced-page"></a><span data-ttu-id="fb13d-102">Editor destinazione elaborazione partizione (pagina Avanzate)</span><span class="sxs-lookup"><span data-stu-id="fb13d-102">Partition Processing Destination Editor (Advanced Page)</span></span>
  <span data-ttu-id="fb13d-103">Utilizzare la pagina **Avanzate** della finestra di dialogo **Editor destinazione elaborazione partizione** per configurare la gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="fb13d-103">Use the **Advanced** page of the **Partition Processing Destination Editor** dialog box to configure error handling.</span></span>  
  
 <span data-ttu-id="fb13d-104">Per ulteriori informazioni sulla destinazione elaborazione partizione, vedere [Partition Processing Destination](data-flow/partition-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="fb13d-104">To learn more about the Partition Processing destination, see [Partition Processing Destination](data-flow/partition-processing-destination.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fb13d-105">Le attività qui descritte non si applicano ai modelli tabulari di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="fb13d-105">Tasks described here do not apply to Analysis Services tabular models.</span></span>  <span data-ttu-id="fb13d-106">Non è possibile eseguire il mapping di colonne di input a colonne di partizione per i modelli tabulari.</span><span class="sxs-lookup"><span data-stu-id="fb13d-106">You cannot map input columns to partition columns for tabular models.</span></span> <span data-ttu-id="fb13d-107">È possibile utilizzare invece l'attività Esegui DDL Analysis Services [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) per elaborare la partizione.</span><span class="sxs-lookup"><span data-stu-id="fb13d-107">You can instead use the Analysis Services Execute DDL task [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) to process the partition.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fb13d-108">Opzioni</span><span class="sxs-lookup"><span data-stu-id="fb13d-108">Options</span></span>  
 <span data-ttu-id="fb13d-109">**Usare la configurazione degli errori predefinita.**</span><span class="sxs-lookup"><span data-stu-id="fb13d-109">**Use default error configuration.**</span></span>  
 <span data-ttu-id="fb13d-110">Consente di specificare se utilizzare la gestione degli errori predefinita di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb13d-110">Specify whether to use the default [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] error handling.</span></span> <span data-ttu-id="fb13d-111">Per impostazione predefinita, questo valore è `True`.</span><span class="sxs-lookup"><span data-stu-id="fb13d-111">By default, this value is `True`.</span></span>  
  
 <span data-ttu-id="fb13d-112">**Azione per errore chiave**</span><span class="sxs-lookup"><span data-stu-id="fb13d-112">**Key error action**</span></span>  
 <span data-ttu-id="fb13d-113">Consente di specificare la modalità di gestione dei record che hanno valori di chiave non validi.</span><span class="sxs-lookup"><span data-stu-id="fb13d-113">Specify how to handle records that have unacceptable key values.</span></span>  
  
|<span data-ttu-id="fb13d-114">Valore</span><span class="sxs-lookup"><span data-stu-id="fb13d-114">Value</span></span>|<span data-ttu-id="fb13d-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fb13d-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fb13d-116">**ConvertToUnknown**</span><span class="sxs-lookup"><span data-stu-id="fb13d-116">**ConvertToUnknown**</span></span>|<span data-ttu-id="fb13d-117">Consente di convertire il valore di chiave non valido nel valore Sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="fb13d-117">Convert the unacceptable key value to the Unknown value.</span></span>|  
|<span data-ttu-id="fb13d-118">**DiscardRecord**</span><span class="sxs-lookup"><span data-stu-id="fb13d-118">**DiscardRecord**</span></span>|<span data-ttu-id="fb13d-119">Consente di scartare il record.</span><span class="sxs-lookup"><span data-stu-id="fb13d-119">Discard the record.</span></span>|  
  
 <span data-ttu-id="fb13d-120">**Ignora errori**</span><span class="sxs-lookup"><span data-stu-id="fb13d-120">**Ignore errors**</span></span>  
 <span data-ttu-id="fb13d-121">Consente di specificare che gli errori devono essere ignorati.</span><span class="sxs-lookup"><span data-stu-id="fb13d-121">Specify that errors should be ignored.</span></span>  
  
 <span data-ttu-id="fb13d-122">**Arresta in caso di errore**</span><span class="sxs-lookup"><span data-stu-id="fb13d-122">**Stop on error**</span></span>  
 <span data-ttu-id="fb13d-123">Consente di specificare che l'elaborazione deve essere arrestata al verificarsi di un errore.</span><span class="sxs-lookup"><span data-stu-id="fb13d-123">Specify that processing should stop when an error occurs.</span></span>  
  
 <span data-ttu-id="fb13d-124">**Numero di errori**</span><span class="sxs-lookup"><span data-stu-id="fb13d-124">**Number of errors**</span></span>  
 <span data-ttu-id="fb13d-125">Consente di specificare la soglia di errore alla quale l'elaborazione deve arrestarsi quando è stata selezionata l'opzione **Arresta in caso di errore**.</span><span class="sxs-lookup"><span data-stu-id="fb13d-125">Specify the error threshold at which processing should stop, if you have selected **Stop on error**.</span></span>  
  
 <span data-ttu-id="fb13d-126">**Azione in caso di errore**</span><span class="sxs-lookup"><span data-stu-id="fb13d-126">**On error action**</span></span>  
 <span data-ttu-id="fb13d-127">Consente di specificare l'azione che deve essere intrapresa al raggiungimento della soglia di errore quando è stata selezionata l'opzione **Arresta in caso di errore**.</span><span class="sxs-lookup"><span data-stu-id="fb13d-127">Specify the action to take when the error threshold is reached, if you have selected **Stop on error**.</span></span>  
  
|<span data-ttu-id="fb13d-128">Valore</span><span class="sxs-lookup"><span data-stu-id="fb13d-128">Value</span></span>|<span data-ttu-id="fb13d-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fb13d-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fb13d-130">**StopProcessing**</span><span class="sxs-lookup"><span data-stu-id="fb13d-130">**StopProcessing**</span></span>|<span data-ttu-id="fb13d-131">Consente di arrestare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fb13d-131">Stop processing.</span></span>|  
|<span data-ttu-id="fb13d-132">**StopLogging**</span><span class="sxs-lookup"><span data-stu-id="fb13d-132">**StopLogging**</span></span>|<span data-ttu-id="fb13d-133">Consente di arrestare la registrazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="fb13d-133">Stop logging errors.</span></span>|  
  
 <span data-ttu-id="fb13d-134">**Chiave non trovata**</span><span class="sxs-lookup"><span data-stu-id="fb13d-134">**Key not found**</span></span>  
 <span data-ttu-id="fb13d-135">Consente di specificare l'azione che deve essere intrapresa per un errore di chiave non trovata.</span><span class="sxs-lookup"><span data-stu-id="fb13d-135">Specify the action to take for a key not found error.</span></span> <span data-ttu-id="fb13d-136">Il valore predefinito è **ReportAndContinue**.</span><span class="sxs-lookup"><span data-stu-id="fb13d-136">By default, this value is **ReportAndContinue**.</span></span>  
  
|<span data-ttu-id="fb13d-137">Valore</span><span class="sxs-lookup"><span data-stu-id="fb13d-137">Value</span></span>|<span data-ttu-id="fb13d-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fb13d-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fb13d-139">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="fb13d-139">**IgnoreError**</span></span>|<span data-ttu-id="fb13d-140">Consente di ignorare l'errore e continuare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fb13d-140">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="fb13d-141">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="fb13d-141">**ReportAndContinue**</span></span>|<span data-ttu-id="fb13d-142">Consente di segnalare l'errore e continuare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fb13d-142">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="fb13d-143">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="fb13d-143">**ReportAndStop**</span></span>|<span data-ttu-id="fb13d-144">Consente di segnalare l'errore e arrestare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fb13d-144">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="fb13d-145">**Chiave duplicata**</span><span class="sxs-lookup"><span data-stu-id="fb13d-145">**Duplicate key**</span></span>  
 <span data-ttu-id="fb13d-146">Consente di specificare l'azione che deve essere intrapresa per un errore di chiave duplicata.</span><span class="sxs-lookup"><span data-stu-id="fb13d-146">Specify the action to take for a duplicate key error.</span></span> <span data-ttu-id="fb13d-147">Il valore predefinito è **IgnoreError**.</span><span class="sxs-lookup"><span data-stu-id="fb13d-147">By default, this value is **IgnoreError**.</span></span>  
  
|<span data-ttu-id="fb13d-148">Valore</span><span class="sxs-lookup"><span data-stu-id="fb13d-148">Value</span></span>|<span data-ttu-id="fb13d-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fb13d-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fb13d-150">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="fb13d-150">**IgnoreError**</span></span>|<span data-ttu-id="fb13d-151">Consente di ignorare l'errore e continuare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fb13d-151">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="fb13d-152">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="fb13d-152">**ReportAndContinue**</span></span>|<span data-ttu-id="fb13d-153">Consente di segnalare l'errore e continuare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fb13d-153">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="fb13d-154">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="fb13d-154">**ReportAndStop**</span></span>|<span data-ttu-id="fb13d-155">Consente di segnalare l'errore e arrestare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fb13d-155">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="fb13d-156">**Chiave Null convertita in sconosciuta**</span><span class="sxs-lookup"><span data-stu-id="fb13d-156">**Null key converted to unknown**</span></span>  
 <span data-ttu-id="fb13d-157">Consente di specificare l'azione che deve essere intrapresa quando una chiave Null è stata convertita nel valore Sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="fb13d-157">Specify the action to take when a null key has been converted to the Unknown value.</span></span> <span data-ttu-id="fb13d-158">Il valore predefinito è **IgnoreError**.</span><span class="sxs-lookup"><span data-stu-id="fb13d-158">By default, this value is **IgnoreError**.</span></span>  
  
|<span data-ttu-id="fb13d-159">Valore</span><span class="sxs-lookup"><span data-stu-id="fb13d-159">Value</span></span>|<span data-ttu-id="fb13d-160">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fb13d-160">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fb13d-161">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="fb13d-161">**IgnoreError**</span></span>|<span data-ttu-id="fb13d-162">Consente di ignorare l'errore e continuare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fb13d-162">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="fb13d-163">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="fb13d-163">**ReportAndContinue**</span></span>|<span data-ttu-id="fb13d-164">Consente di segnalare l'errore e continuare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fb13d-164">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="fb13d-165">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="fb13d-165">**ReportAndStop**</span></span>|<span data-ttu-id="fb13d-166">Consente di segnalare l'errore e arrestare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fb13d-166">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="fb13d-167">**Chiave Null non consentita**</span><span class="sxs-lookup"><span data-stu-id="fb13d-167">**Null key not allowed**</span></span>  
 <span data-ttu-id="fb13d-168">Consente di specificare l'azione che deve essere intrapresa quando viene incontrata una chiave Null e le chiavi Null non sono consentite.</span><span class="sxs-lookup"><span data-stu-id="fb13d-168">Specify the action to take when null keys are not allowed and a null key is encountered.</span></span> <span data-ttu-id="fb13d-169">Il valore predefinito è **ReportAndContinue**.</span><span class="sxs-lookup"><span data-stu-id="fb13d-169">By default, this value is **ReportAndContinue**.</span></span>  
  
|<span data-ttu-id="fb13d-170">Valore</span><span class="sxs-lookup"><span data-stu-id="fb13d-170">Value</span></span>|<span data-ttu-id="fb13d-171">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fb13d-171">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fb13d-172">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="fb13d-172">**IgnoreError**</span></span>|<span data-ttu-id="fb13d-173">Consente di ignorare l'errore e continuare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fb13d-173">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="fb13d-174">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="fb13d-174">**ReportAndContinue**</span></span>|<span data-ttu-id="fb13d-175">Consente di segnalare l'errore e continuare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fb13d-175">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="fb13d-176">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="fb13d-176">**ReportAndStop**</span></span>|<span data-ttu-id="fb13d-177">Consente di segnalare l'errore e arrestare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fb13d-177">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="fb13d-178">**Percorso log degli errori**</span><span class="sxs-lookup"><span data-stu-id="fb13d-178">**Error log path**</span></span>  
 <span data-ttu-id="fb13d-179">Consente di digitare il percorso del log degli errori o di selezionare una destinazione usando il pulsante Sfoglia **(...)** .</span><span class="sxs-lookup"><span data-stu-id="fb13d-179">Type the path for the error log, or select a destination by using the browse **(...)** button.</span></span>  
  
 <span data-ttu-id="fb13d-180">**Sfoglia (...)**</span><span class="sxs-lookup"><span data-stu-id="fb13d-180">**Browse (...)**</span></span>  
 <span data-ttu-id="fb13d-181">Consente di selezionare il percorso del log degli errori.</span><span class="sxs-lookup"><span data-stu-id="fb13d-181">Select a path for the error log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb13d-182">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb13d-182">See Also</span></span>  
 <span data-ttu-id="fb13d-183">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="fb13d-183">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="fb13d-184">Editor destinazione elaborazione partizione &#40;pagina Mapping&#41;</span><span class="sxs-lookup"><span data-stu-id="fb13d-184">Partition Processing Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/partition-processing-destination-editor-mappings-page.md)  
  
  
