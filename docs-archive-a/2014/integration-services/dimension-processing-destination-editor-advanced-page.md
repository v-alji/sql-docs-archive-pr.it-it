---
title: Editor destinazione elaborazione dimensione (pagina Avanzate) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dimprocessingtransformation.advanced.f1
helpviewer_keywords:
- Dimension Processing Destination Editor
ms.assetid: 2b30835a-2680-4d98-89a4-4f17e29e3818
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5be80cbbfb6871594d7481ccc0f9444d014885e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636812"
---
# <a name="dimension-processing-destination-editor-advanced-page"></a><span data-ttu-id="fbf92-102">Editor destinazione elaborazione dimensione (pagina Avanzate)</span><span class="sxs-lookup"><span data-stu-id="fbf92-102">Dimension Processing Destination Editor (Advanced Page)</span></span>
  <span data-ttu-id="fbf92-103">Usare la pagina **Avanzate** della finestra di dialogo **Editor destinazione elaborazione dimensione** per configurare la gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="fbf92-103">Use the **Advanced** page of the **Dimension Processing Destination Editor** dialog box to configure error handling.</span></span>  
  
 <span data-ttu-id="fbf92-104">Per ulteriori informazioni sulla destinazione elaborazione dimensione, vedere [Dimension Processing Destination](data-flow/dimension-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="fbf92-104">To learn more about the Dimension Processing destination, see [Dimension Processing Destination](data-flow/dimension-processing-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="fbf92-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="fbf92-105">Options</span></span>  
 <span data-ttu-id="fbf92-106">**Usare la configurazione degli errori predefinita.**</span><span class="sxs-lookup"><span data-stu-id="fbf92-106">**Use default error configuration.**</span></span>  
 <span data-ttu-id="fbf92-107">Consente di specificare se utilizzare la gestione degli errori predefinita di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fbf92-107">Specify whether to use the default [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] error handling.</span></span> <span data-ttu-id="fbf92-108">Per impostazione predefinita, questo valore è `True`.</span><span class="sxs-lookup"><span data-stu-id="fbf92-108">By default, this value is `True`.</span></span>  
  
 <span data-ttu-id="fbf92-109">**Azione per errore chiave**</span><span class="sxs-lookup"><span data-stu-id="fbf92-109">**Key error action**</span></span>  
 <span data-ttu-id="fbf92-110">Consente di specificare la modalità di gestione dei record che hanno valori di chiave non validi.</span><span class="sxs-lookup"><span data-stu-id="fbf92-110">Specify how to handle records that have unacceptable key values.</span></span>  
  
|<span data-ttu-id="fbf92-111">Valore</span><span class="sxs-lookup"><span data-stu-id="fbf92-111">Value</span></span>|<span data-ttu-id="fbf92-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fbf92-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fbf92-113">**ConvertToUnknown**</span><span class="sxs-lookup"><span data-stu-id="fbf92-113">**ConvertToUnknown**</span></span>|<span data-ttu-id="fbf92-114">Consente di convertire il valore di chiave non valido nel valore `UnknownMember`.</span><span class="sxs-lookup"><span data-stu-id="fbf92-114">Convert the unacceptable key value to the `UnknownMember` value.</span></span>|  
|<span data-ttu-id="fbf92-115">**DiscardRecord**</span><span class="sxs-lookup"><span data-stu-id="fbf92-115">**DiscardRecord**</span></span>|<span data-ttu-id="fbf92-116">Consente di scartare il record.</span><span class="sxs-lookup"><span data-stu-id="fbf92-116">Discard the record.</span></span>|  
  
 <span data-ttu-id="fbf92-117">**Ignora errori**</span><span class="sxs-lookup"><span data-stu-id="fbf92-117">**Ignore errors**</span></span>  
 <span data-ttu-id="fbf92-118">Consente di specificare che gli errori devono essere ignorati.</span><span class="sxs-lookup"><span data-stu-id="fbf92-118">Specify that errors should be ignored.</span></span>  
  
 <span data-ttu-id="fbf92-119">**Arresta in caso di errore**</span><span class="sxs-lookup"><span data-stu-id="fbf92-119">**Stop on error**</span></span>  
 <span data-ttu-id="fbf92-120">Consente di specificare che l'elaborazione deve essere arrestata al verificarsi di un errore.</span><span class="sxs-lookup"><span data-stu-id="fbf92-120">Specify that processing should stop when an error occurs.</span></span>  
  
 <span data-ttu-id="fbf92-121">**Numero di errori**</span><span class="sxs-lookup"><span data-stu-id="fbf92-121">**Number of errors**</span></span>  
 <span data-ttu-id="fbf92-122">Consente di specificare la soglia di errore alla quale l'elaborazione deve arrestarsi quando è stata selezionata l'opzione **Arresta in caso di errore**.</span><span class="sxs-lookup"><span data-stu-id="fbf92-122">Specify the error threshold at which processing should stop, if you have selected **Stop on errors**.</span></span>  
  
 <span data-ttu-id="fbf92-123">**Azione in caso di errore**</span><span class="sxs-lookup"><span data-stu-id="fbf92-123">**On error action**</span></span>  
 <span data-ttu-id="fbf92-124">Consente di specificare l'azione che deve essere intrapresa al raggiungimento della soglia di errore quando è stata selezionata l'opzione **Arresta in caso di errore**.</span><span class="sxs-lookup"><span data-stu-id="fbf92-124">Specify the action to take when the error threshold is reached, if you have selected **Stop on errors**.</span></span>  
  
|<span data-ttu-id="fbf92-125">Valore</span><span class="sxs-lookup"><span data-stu-id="fbf92-125">Value</span></span>|<span data-ttu-id="fbf92-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fbf92-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fbf92-127">**StopProcessing**</span><span class="sxs-lookup"><span data-stu-id="fbf92-127">**StopProcessing**</span></span>|<span data-ttu-id="fbf92-128">Consente di arrestare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fbf92-128">Stop processing.</span></span>|  
|<span data-ttu-id="fbf92-129">**StopLogging**</span><span class="sxs-lookup"><span data-stu-id="fbf92-129">**StopLogging**</span></span>|<span data-ttu-id="fbf92-130">Consente di arrestare la registrazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="fbf92-130">Stop logging errors.</span></span>|  
  
 <span data-ttu-id="fbf92-131">**Chiave non trovata**</span><span class="sxs-lookup"><span data-stu-id="fbf92-131">**Key not found**</span></span>  
 <span data-ttu-id="fbf92-132">Consente di specificare l'azione che deve essere intrapresa per un errore di chiave non trovata.</span><span class="sxs-lookup"><span data-stu-id="fbf92-132">Specify the action to take for a key not found error.</span></span> <span data-ttu-id="fbf92-133">Il valore predefinito è **ReportAndContinue**.</span><span class="sxs-lookup"><span data-stu-id="fbf92-133">By default, this value is **ReportAndContinue**.</span></span>  
  
|<span data-ttu-id="fbf92-134">Valore</span><span class="sxs-lookup"><span data-stu-id="fbf92-134">Value</span></span>|<span data-ttu-id="fbf92-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fbf92-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fbf92-136">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="fbf92-136">**IgnoreError**</span></span>|<span data-ttu-id="fbf92-137">Consente di ignorare l'errore e continuare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fbf92-137">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="fbf92-138">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="fbf92-138">**ReportAndContinue**</span></span>|<span data-ttu-id="fbf92-139">Consente di segnalare l'errore e continuare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fbf92-139">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="fbf92-140">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="fbf92-140">**ReportAndStop**</span></span>|<span data-ttu-id="fbf92-141">Consente di segnalare l'errore e arrestare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fbf92-141">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="fbf92-142">**Chiave duplicata**</span><span class="sxs-lookup"><span data-stu-id="fbf92-142">**Duplicate key**</span></span>  
 <span data-ttu-id="fbf92-143">Consente di specificare l'azione che deve essere intrapresa per un errore di chiave duplicata.</span><span class="sxs-lookup"><span data-stu-id="fbf92-143">Specify the action to take for a duplicate key error.</span></span> <span data-ttu-id="fbf92-144">Il valore predefinito è **IgnoreError**.</span><span class="sxs-lookup"><span data-stu-id="fbf92-144">By default, this value is **IgnoreError**.</span></span>  
  
|<span data-ttu-id="fbf92-145">Valore</span><span class="sxs-lookup"><span data-stu-id="fbf92-145">Value</span></span>|<span data-ttu-id="fbf92-146">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fbf92-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fbf92-147">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="fbf92-147">**IgnoreError**</span></span>|<span data-ttu-id="fbf92-148">Consente di ignorare l'errore e continuare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fbf92-148">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="fbf92-149">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="fbf92-149">**ReportAndContinue**</span></span>|<span data-ttu-id="fbf92-150">Consente di segnalare l'errore e continuare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fbf92-150">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="fbf92-151">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="fbf92-151">**ReportAndStop**</span></span>|<span data-ttu-id="fbf92-152">Consente di segnalare l'errore e arrestare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fbf92-152">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="fbf92-153">**Chiave Null convertita in sconosciuta**</span><span class="sxs-lookup"><span data-stu-id="fbf92-153">**Null key converted to unknown**</span></span>  
 <span data-ttu-id="fbf92-154">Consente di specificare l'azione che deve essere intrapresa quando una chiave Null è stata convertita nel valore `UnknownMember`.</span><span class="sxs-lookup"><span data-stu-id="fbf92-154">Specify the action to take when a null key has been converted to the `UnknownMember` value.</span></span> <span data-ttu-id="fbf92-155">Il valore predefinito è **IgnoreError**.</span><span class="sxs-lookup"><span data-stu-id="fbf92-155">By default, this value is **IgnoreError**.</span></span>  
  
|<span data-ttu-id="fbf92-156">Valore</span><span class="sxs-lookup"><span data-stu-id="fbf92-156">Value</span></span>|<span data-ttu-id="fbf92-157">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fbf92-157">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fbf92-158">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="fbf92-158">**IgnoreError**</span></span>|<span data-ttu-id="fbf92-159">Consente di ignorare l'errore e continuare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fbf92-159">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="fbf92-160">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="fbf92-160">**ReportAndContinue**</span></span>|<span data-ttu-id="fbf92-161">Consente di segnalare l'errore e continuare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fbf92-161">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="fbf92-162">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="fbf92-162">**ReportAndStop**</span></span>|<span data-ttu-id="fbf92-163">Consente di segnalare l'errore e arrestare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fbf92-163">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="fbf92-164">**Chiave Null non consentita**</span><span class="sxs-lookup"><span data-stu-id="fbf92-164">**Null key not allowed**</span></span>  
 <span data-ttu-id="fbf92-165">Consente di specificare l'azione che deve essere intrapresa quando viene incontrata una chiave Null e le chiavi Null non sono consentite.</span><span class="sxs-lookup"><span data-stu-id="fbf92-165">Specify the action to take when null keys are not allowed and a null key is encountered.</span></span> <span data-ttu-id="fbf92-166">Il valore predefinito è **ReportAndContinue**.</span><span class="sxs-lookup"><span data-stu-id="fbf92-166">By default, this value is **ReportAndContinue**.</span></span>  
  
|<span data-ttu-id="fbf92-167">Valore</span><span class="sxs-lookup"><span data-stu-id="fbf92-167">Value</span></span>|<span data-ttu-id="fbf92-168">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fbf92-168">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fbf92-169">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="fbf92-169">**IgnoreError**</span></span>|<span data-ttu-id="fbf92-170">Consente di ignorare l'errore e continuare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fbf92-170">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="fbf92-171">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="fbf92-171">**ReportAndContinue**</span></span>|<span data-ttu-id="fbf92-172">Consente di segnalare l'errore e continuare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fbf92-172">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="fbf92-173">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="fbf92-173">**ReportAndStop**</span></span>|<span data-ttu-id="fbf92-174">Consente di segnalare l'errore e arrestare l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fbf92-174">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="fbf92-175">**Percorso log degli errori**</span><span class="sxs-lookup"><span data-stu-id="fbf92-175">**Error log path**</span></span>  
 <span data-ttu-id="fbf92-176">Consente di digitare il percorso del log degli errori o di selezionare una destinazione con il pulsante **Sfoglia (...)**.</span><span class="sxs-lookup"><span data-stu-id="fbf92-176">Type the path of the error log, or click the **browse(...)** button to select a destination.</span></span>  
  
 <span data-ttu-id="fbf92-177">**Sfoglia (...)**</span><span class="sxs-lookup"><span data-stu-id="fbf92-177">**Browse (...)**</span></span>  
 <span data-ttu-id="fbf92-178">Consente di selezionare il percorso del log degli errori.</span><span class="sxs-lookup"><span data-stu-id="fbf92-178">Select a path for the error log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbf92-179">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbf92-179">See Also</span></span>  
 <span data-ttu-id="fbf92-180">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="fbf92-180">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="fbf92-181">[Editor destinazione elaborazione dimensione &#40;pagina Gestione connessione&#41;](../../2014/integration-services/dimension-processing-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="fbf92-181">[Dimension Processing Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/dimension-processing-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="fbf92-182">Editor destinazione elaborazione dimensione &#40;pagina Mapping&#41;</span><span class="sxs-lookup"><span data-stu-id="fbf92-182">Dimension Processing Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/dimension-processing-destination-editor-mappings-page.md)  
  
  
