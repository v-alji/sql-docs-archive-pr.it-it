---
title: Creare e gestire indicatori KPI (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.kpi.f1
ms.assetid: c96026c2-4394-4c3c-986b-4c95a4421900
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8e9d7ef77939efe407ed6ab0d725a6d788c58b49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626916"
---
# <a name="create-and-manage-kpis-ssas-tabular"></a><span data-ttu-id="084ad-102">Creare e gestire indicatori KPI (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="084ad-102">Create and Manage KPIs (SSAS Tabular)</span></span>
  <span data-ttu-id="084ad-103">In questo argomento viene descritto come creare, modificare o eliminare un indicatore di prestazioni chiave (KPI) in un modello tabulare.</span><span class="sxs-lookup"><span data-stu-id="084ad-103">This topic describes how to create, edit, or delete a KPI (Key Performance Indicator) in a tabular model.</span></span> <span data-ttu-id="084ad-104">Per creare un indicatore KPI, selezionare una misura che restituisca il valore di base dell'indicatore KPI.</span><span class="sxs-lookup"><span data-stu-id="084ad-104">To create a KPI, you select a measure that evaluates to the KPI's Base value.</span></span> <span data-ttu-id="084ad-105">Successivamente, utilizzare la finestra di dialogo Indicatore di prestazioni chiave per selezionare una seconda misura o un valore assoluto tramite cui venga restituito un valore di destinazione.</span><span class="sxs-lookup"><span data-stu-id="084ad-105">You then use the Key Performance Indicator dialog box to select a second measure or an absolute value that evaluates to a target value.</span></span> <span data-ttu-id="084ad-106">È quindi possibile definire le soglie dello stato tramite cui si misurano le prestazioni tra le misure di base e di destinazione.</span><span class="sxs-lookup"><span data-stu-id="084ad-106">You can then define status thresholds that measure the performance between the Base and Target measures.</span></span>  
  
 <span data-ttu-id="084ad-107">In questo argomento sono incluse le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="084ad-107">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="084ad-108">Per creare un indicatore KPI</span><span class="sxs-lookup"><span data-stu-id="084ad-108">To create a KPI</span></span>](#bkmk_create_KPI)  
  
-   [<span data-ttu-id="084ad-109">Per modificare un indicatore KPI</span><span class="sxs-lookup"><span data-stu-id="084ad-109">To edit a KPI</span></span>](#bkmk_edit_KPI)  
  
-   [<span data-ttu-id="084ad-110">Per eliminare un indicatore KPI e la misura di base</span><span class="sxs-lookup"><span data-stu-id="084ad-110">To delete a KPI and the base measure</span></span>](#bkmk_delete)  
  
-   [<span data-ttu-id="084ad-111">Per eliminare un indicatore KPI e mantenere la misura base</span><span class="sxs-lookup"><span data-stu-id="084ad-111">To delete a KPI, but keep the base measure</span></span>](#bkmk_delete_KPI)  
  
## <a name="tasks"></a><span data-ttu-id="084ad-112">Attività</span><span class="sxs-lookup"><span data-stu-id="084ad-112">Tasks</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="084ad-113">Prima di creare un indicatore KPI, è innanzitutto necessario creare una misura di base che consenta la restituzione di un valore.</span><span class="sxs-lookup"><span data-stu-id="084ad-113">Before creating a KPI, you must first create a Base measure that evaluates to value.</span></span> <span data-ttu-id="084ad-114">Estendere quindi la misura di base a un indicatore KPI.</span><span class="sxs-lookup"><span data-stu-id="084ad-114">You then extend the Base measure to a KPI.</span></span> <span data-ttu-id="084ad-115">La procedura per creare misure è descritta in un altro argomento, [Creare e gestire misure &#40;SSAS tabulare&#41;](measures-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="084ad-115">How to create measures are described in another topic, [Create and Manage Measures &#40;SSAS Tabular&#41;](measures-ssas-tabular.md).</span></span> <span data-ttu-id="084ad-116">Un indicatore KPI richiede inoltre un valore di destinazione,</span><span class="sxs-lookup"><span data-stu-id="084ad-116">A KPI also requires a target value.</span></span> <span data-ttu-id="084ad-117">che può essere il valore di un'altra misura predefinita o un valore assoluto.</span><span class="sxs-lookup"><span data-stu-id="084ad-117">This value can be from another pre-defined measure or an absolute value.</span></span> <span data-ttu-id="084ad-118">Dopo aver esteso una misura di base a un indicatore KPI, sarà possibile selezionare il valore di destinazione e definire le soglie dello stato nella finestra di dialogo Indicatore di prestazioni chiave.</span><span class="sxs-lookup"><span data-stu-id="084ad-118">Once you have extended a Base measure to a KPI, you can then select the target value and define status thresholds in the Key Performance Indicator dialog box.</span></span>  
  
###  <a name="to-create-a-kpi"></a><a name="bkmk_create_KPI"></a> <span data-ttu-id="084ad-119">Per creare un indicatore KPI</span><span class="sxs-lookup"><span data-stu-id="084ad-119">To create a KPI</span></span>  
  
1.  <span data-ttu-id="084ad-120">Nella griglia delle misure fare clic con il pulsante destro del mouse sulla misura che verrà usata come misura di base (valore), quindi scegliere **Crea KPI**.</span><span class="sxs-lookup"><span data-stu-id="084ad-120">In the measure grid, right-click the measure that will serve as the Base measure (value), and then click **Create KPI**.</span></span>  
  
2.  <span data-ttu-id="084ad-121">In **Definisci valore di destinazione** della finestra di dialogo **Indicatore di prestazioni chiave**selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="084ad-121">In the **Key Performance Indicator** dialog box, in **Define target value**, select from one of the following:</span></span>  
  
     <span data-ttu-id="084ad-122">Selezionare **Misura**, quindi una misura di destinazione dalla casella di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="084ad-122">Select **Measure**, and then select a target measure from the listbox.</span></span>  
  
     <span data-ttu-id="084ad-123">Selezionare **Valore assoluto**, quindi digitare un valore numerico.</span><span class="sxs-lookup"><span data-stu-id="084ad-123">Select **Absolute value**, and then type a numerical value.</span></span>  
  
3.  <span data-ttu-id="084ad-124">In **Definisci soglie stato**scegliere e trascinare i valori soglia minimo e massimo.</span><span class="sxs-lookup"><span data-stu-id="084ad-124">In **Define status thresholds**, click and slide the low and high threshold values.</span></span>  
  
4.  <span data-ttu-id="084ad-125">In **Seleziona stile icona**fare clic su un tipo di immagine.</span><span class="sxs-lookup"><span data-stu-id="084ad-125">In **Select icon style**, click an image type.</span></span>  
  
5.  <span data-ttu-id="084ad-126">Fare clic su **Descrizioni**, quindi digitare le descrizioni per l'indicatore KPI, il valore, lo stato e la destinazione.</span><span class="sxs-lookup"><span data-stu-id="084ad-126">Click on **Descriptions**, and then type descriptions for KPI, Value, Status, and Target.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="084ad-127">È possibile utilizzare la funzionalità Analizza in Excel per testare l'indicatore KPI.</span><span class="sxs-lookup"><span data-stu-id="084ad-127">You can use the Analyze in Excel feature to test your KPI.</span></span> <span data-ttu-id="084ad-128">Per altre informazioni, vedere la sezione [Analizzare in Excel &#40;SSAS tabulare&#41;](analyze-in-excel-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="084ad-128">For more information, see [Analyze in Excel &#40;SSAS Tabular&#41;](analyze-in-excel-ssas-tabular.md).</span></span>  
  
###  <a name="to-edit-a-kpi"></a><a name="bkmk_edit_KPI"></a> <span data-ttu-id="084ad-129">Per modificare un indicatore KPI</span><span class="sxs-lookup"><span data-stu-id="084ad-129">To edit a KPI</span></span>  
  
-   <span data-ttu-id="084ad-130">Nella griglia delle misure fare clic con il pulsante destro del mouse sulla misura che viene usata come misura di base (valore) dell'indicatore KPI, quindi scegliere **Modifica impostazioni KPI**.</span><span class="sxs-lookup"><span data-stu-id="084ad-130">In the measure grid, right-click the measure that serves as the Base measure (value) of the KPI, and then click **Edit KPI Settings**.</span></span>  
  
###  <a name="to-delete-a-kpi-and-the-base-measure"></a><a name="bkmk_delete"></a> <span data-ttu-id="084ad-131">Per eliminare un indicatore KPI e la misura base</span><span class="sxs-lookup"><span data-stu-id="084ad-131">To delete a KPI and the base measure</span></span>  
  
-   <span data-ttu-id="084ad-132">Nella griglia delle misure fare clic con il pulsante destro del mouse sulla misura che viene usata come misura di base (valore) dell'indicatore KPI, quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="084ad-132">In the measure grid, right-click the measure that serves as the Base measure (value) of the KPI, and then click **Delete**.</span></span>  
  
###  <a name="to-delete-a-kpi-but-keep-the-base-measure"></a><a name="bkmk_delete_KPI"></a><span data-ttu-id="084ad-133">Per eliminare un indicatore KPI, mantenendo però la misura di base</span><span class="sxs-lookup"><span data-stu-id="084ad-133">To delete a KPI, but keep the base measure</span></span>  
  
-   <span data-ttu-id="084ad-134">Nella griglia delle misure fare clic con il pulsante destro del mouse sulla misura che viene usata come misura di base (valore) dell'indicatore KPI, quindi scegliere **Elimina KPI**.</span><span class="sxs-lookup"><span data-stu-id="084ad-134">In the measure grid, right-click the measure that serves as the Base measure (value) of the KPI, and then click **Delete KPI**.</span></span>  
  
## <a name="alt-shortcuts"></a><span data-ttu-id="084ad-135">Tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="084ad-135">ALT Shortcuts</span></span>  
  
|<span data-ttu-id="084ad-136">Sezione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="084ad-136">UI section</span></span>|<span data-ttu-id="084ad-137">Comando tramite tasto</span><span class="sxs-lookup"><span data-stu-id="084ad-137">Key command</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="084ad-138">Misura di base KPI</span><span class="sxs-lookup"><span data-stu-id="084ad-138">KPI base measure</span></span>|<span data-ttu-id="084ad-139">ALT+B</span><span class="sxs-lookup"><span data-stu-id="084ad-139">ALT+B</span></span>|  
|<span data-ttu-id="084ad-140">Stato KPI</span><span class="sxs-lookup"><span data-stu-id="084ad-140">KPI Status</span></span>|<span data-ttu-id="084ad-141">ALT+S</span><span class="sxs-lookup"><span data-stu-id="084ad-141">ALT+S</span></span>|  
|<span data-ttu-id="084ad-142">Measure</span><span class="sxs-lookup"><span data-stu-id="084ad-142">Measure</span></span>|<span data-ttu-id="084ad-143">ALT+M</span><span class="sxs-lookup"><span data-stu-id="084ad-143">ALT+M</span></span>|  
|<span data-ttu-id="084ad-144">Valore assoluto</span><span class="sxs-lookup"><span data-stu-id="084ad-144">Absolute value</span></span>|<span data-ttu-id="084ad-145">ALT + A</span><span class="sxs-lookup"><span data-stu-id="084ad-145">ALT+A</span></span>|  
|<span data-ttu-id="084ad-146">Definisci soglie stato</span><span class="sxs-lookup"><span data-stu-id="084ad-146">Define status thresholds</span></span>|<span data-ttu-id="084ad-147">ALT+U</span><span class="sxs-lookup"><span data-stu-id="084ad-147">ALT+U</span></span>|  
|<span data-ttu-id="084ad-148">Seleziona stile icona</span><span class="sxs-lookup"><span data-stu-id="084ad-148">Select icon style</span></span>|<span data-ttu-id="084ad-149">ALT+I</span><span class="sxs-lookup"><span data-stu-id="084ad-149">ALT+I</span></span>|  
|<span data-ttu-id="084ad-150">Tendenza</span><span class="sxs-lookup"><span data-stu-id="084ad-150">Trend</span></span>|<span data-ttu-id="084ad-151">ALT+T</span><span class="sxs-lookup"><span data-stu-id="084ad-151">ALT+T</span></span>|  
|<span data-ttu-id="084ad-152">Descrizioni</span><span class="sxs-lookup"><span data-stu-id="084ad-152">Descriptions</span></span>|<span data-ttu-id="084ad-153">ALT+D</span><span class="sxs-lookup"><span data-stu-id="084ad-153">ALT+D</span></span>|  
|<span data-ttu-id="084ad-154">Tendenza</span><span class="sxs-lookup"><span data-stu-id="084ad-154">Trend</span></span>|<span data-ttu-id="084ad-155">ALT+T</span><span class="sxs-lookup"><span data-stu-id="084ad-155">ALT+T</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="084ad-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="084ad-156">See Also</span></span>  
 <span data-ttu-id="084ad-157">[Indicatori KPI &#40;&#41;tabulare SSAS](kpis-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="084ad-157">[KPIs &#40;SSAS Tabular&#41;](kpis-ssas-tabular.md) </span></span>  
 <span data-ttu-id="084ad-158">[Misure &#40;SSAS tabulare&#41;](measures-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="084ad-158">[Measures &#40;SSAS Tabular&#41;](measures-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="084ad-159">Creare e gestire misure &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="084ad-159">Create and Manage Measures &#40;SSAS Tabular&#41;</span></span>](create-and-manage-measures-ssas-tabular.md)  
  
  
