---
title: Aggiungere, modificare o eliminare valori predefiniti per un parametro di report (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10460"
- sql12.rtp.rptdesigner.reportparameters.defaultvalues.f1
- "10072"
ms.assetid: 6a87e069-b3a9-47b6-bcec-afcdd8aff65f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1d50fdbbe42a656ef839785c0968b36c8c829e11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628467"
---
# <a name="add-change-or-delete-default-values-for-a-report-parameter-report-builder-and-ssrs"></a><span data-ttu-id="d8060-102">Aggiungere, modificare o eliminare valori predefiniti per un parametro di report (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="d8060-102">Add, Change, or Delete Default Values for a Report Parameter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d8060-103">Dopo aver creato un parametro del report, è possibile specificare un elenco di valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="d8060-103">After you create a report parameter, you can provide a list of default values.</span></span> <span data-ttu-id="d8060-104">Se tutti i parametri dispongono di un valore predefinito valido, il report viene eseguito automaticamente la prima volta che viene visualizzato o ne viene visualizzata l'anteprima.</span><span class="sxs-lookup"><span data-stu-id="d8060-104">If all parameters have a valid default value, the report runs automatically when you first view or preview it.</span></span>  
  
 <span data-ttu-id="d8060-105">I parametri di report possono rappresentare un valore singolo o più valori.</span><span class="sxs-lookup"><span data-stu-id="d8060-105">Report parameters can represent one value or multiple values.</span></span> <span data-ttu-id="d8060-106">Per i valori singoli, è possibile fornire un valore letterale o un'espressione,</span><span class="sxs-lookup"><span data-stu-id="d8060-106">For single values, you can provide a literal or expression.</span></span> <span data-ttu-id="d8060-107">mentre per più valori è possibile fornire un elenco statico di valori o un elenco da un set di dati del report.</span><span class="sxs-lookup"><span data-stu-id="d8060-107">For multiple values, you can provide a static list or a list from a report dataset.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="d8060-108">Dopo aver pubblicato un report, è possibile eseguire l'override dei valori predefiniti definiti nel report nello strumento di creazione di report, impostando i valori delle proprietà del parametro nel server di report.</span><span class="sxs-lookup"><span data-stu-id="d8060-108">After you publish a report, you can override the default values that you define in the report in the report authoring tool, by setting parameter property values on the report server.</span></span> <span data-ttu-id="d8060-109">Inoltre, per fornire più set di valori predefiniti del parametro, è possibile creare report collegati.</span><span class="sxs-lookup"><span data-stu-id="d8060-109">You can also provide multiple sets of default parameter values by creating linked reports.</span></span> <span data-ttu-id="d8060-110">Per altre informazioni, vedere  [Parametri report &#40;Generatore report e Progettazione report&#41;](report-parameters-report-builder-and-report-designer.md)</span><span class="sxs-lookup"><span data-stu-id="d8060-110">For more information, see  [Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md)</span></span>  
  
### <a name="to-add-or-change-the-default-values-for-a-report-parameter"></a><span data-ttu-id="d8060-111">Per aggiungere o modificare i valori predefiniti per un parametro di report</span><span class="sxs-lookup"><span data-stu-id="d8060-111">To add or change the default values for a report parameter</span></span>  
  
1.  <span data-ttu-id="d8060-112">Nel riquadro dei dati del espandere il nodo **Parametri** .</span><span class="sxs-lookup"><span data-stu-id="d8060-112">In the Report Data pane, expand the **Parameters** node.</span></span> <span data-ttu-id="d8060-113">Fare clic sul con il pulsante destro del mouse sul parametro, quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="d8060-113">Right-click the parameter and click **Edit**.</span></span> <span data-ttu-id="d8060-114">Verrà visualizzata la finestra di dialogo **Proprietà parametri report** .</span><span class="sxs-lookup"><span data-stu-id="d8060-114">The **Report Parameter Properties** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d8060-115">Se il riquadro dei dati del report non è visualizzato, scegliere **Dati report** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="d8060-115">If the Report Data pane is not visible, click **View** and then click **Report Data**.</span></span>  
  
2.  <span data-ttu-id="d8060-116">Fare clic su **Valori predefiniti**.</span><span class="sxs-lookup"><span data-stu-id="d8060-116">Click **Default Values**.</span></span>  
  
3.  <span data-ttu-id="d8060-117">Selezionare un'opzione predefinita:</span><span class="sxs-lookup"><span data-stu-id="d8060-117">Select a default option:</span></span>  
  
    -   <span data-ttu-id="d8060-118">Per fornire manualmente un valore o un elenco di valori, fare clic su **Imposta valori**.</span><span class="sxs-lookup"><span data-stu-id="d8060-118">To manually provide a value or list of values, click **Specify values**.</span></span> <span data-ttu-id="d8060-119">Fare clic su **Aggiungi** , quindi immettere il valore nella casella di testo **Valore** .</span><span class="sxs-lookup"><span data-stu-id="d8060-119">Click **Add** and then enter the value in the **Value** text box.</span></span> <span data-ttu-id="d8060-120">È possibile scrivere un'espressione per un valore.</span><span class="sxs-lookup"><span data-stu-id="d8060-120">You can write an expression for a value.</span></span> <span data-ttu-id="d8060-121">Il tipo di dati deve corrispondere al tipo di dati del parametro.</span><span class="sxs-lookup"><span data-stu-id="d8060-121">The data type must match the data type of the parameter.</span></span> <span data-ttu-id="d8060-122">Non è possibile utilizzare i nomi di campi in un'espressione per un parametro.</span><span class="sxs-lookup"><span data-stu-id="d8060-122">Field names cannot be used in an expression for a parameter.</span></span>  
  
         <span data-ttu-id="d8060-123">Per i parametri multivalore, ripetere questo passaggio per il numero desiderato di valori.</span><span class="sxs-lookup"><span data-stu-id="d8060-123">For multivalue parameters, repeat this step for as many values as you want to provide.</span></span> <span data-ttu-id="d8060-124">Gli elementi vengono visualizzati nell'elenco a discesa in base all'ordine in cui appaiono nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="d8060-124">The order of items you see in this list determines the order that the user sees them in the drop-down list.</span></span> <span data-ttu-id="d8060-125">Per modificare l'ordine di un elemento nell'elenco, fare clic su una casella di testo **Valore** per selezionare l'elemento, quindi usare i pulsanti freccia per spostare l'elemento verso l'alto o verso il basso nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="d8060-125">To change the order of an item in the list, click the **Value** text box to select the item, and then use the up and down arrow buttons to move the item higher or lower in the list.</span></span>  
  
    -   <span data-ttu-id="d8060-126">Per fornire il nome di un set di dati che recupera i valori, fare clic su **Ottieni valori da una query**.</span><span class="sxs-lookup"><span data-stu-id="d8060-126">To provide the name of an existing dataset that retrieves the values, click **Get values from a query**.</span></span> <span data-ttu-id="d8060-127">In **Set di dati**scegliere il nome del set di dati.</span><span class="sxs-lookup"><span data-stu-id="d8060-127">In **Dataset**, choose the name of the dataset.</span></span>  
  
         <span data-ttu-id="d8060-128">In **Campo valori**scegliere il nome del campo in cui sono disponibili i valori del parametro.</span><span class="sxs-lookup"><span data-stu-id="d8060-128">In **Value field**, choose the name of the field that provides parameter values.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-remove-the-default-values-for-a-report-parameter"></a><span data-ttu-id="d8060-129">Per rimuovere i valori predefiniti per un parametro di report</span><span class="sxs-lookup"><span data-stu-id="d8060-129">To remove the default values for a report parameter</span></span>  
  
1.  <span data-ttu-id="d8060-130">Nel riquadro dei dati del espandere il nodo **Parametri** .</span><span class="sxs-lookup"><span data-stu-id="d8060-130">In the Report Data pane, expand the **Parameters** node.</span></span> <span data-ttu-id="d8060-131">Fare clic sul con il pulsante destro del mouse sul parametro, quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="d8060-131">Right-click the parameter and click **Edit**.</span></span> <span data-ttu-id="d8060-132">Verrà visualizzata la finestra di dialogo **Proprietà parametri report** .</span><span class="sxs-lookup"><span data-stu-id="d8060-132">The **Report Parameter Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="d8060-133">Fare clic su **Valori predefiniti**.</span><span class="sxs-lookup"><span data-stu-id="d8060-133">Click **Default Values**.</span></span>  
  
3.  <span data-ttu-id="d8060-134">In **Selezionare una delle seguenti opzioni**fare clic su **Nessun valore predefinito**.</span><span class="sxs-lookup"><span data-stu-id="d8060-134">In **Select from one of the following options**, click **No default value**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d8060-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8060-135">See Also</span></span>  
 <span data-ttu-id="d8060-136">[Parametri report &#40;Generatore report e Progettazione report&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="d8060-136">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="d8060-137">[Aggiunta di parametri di propagazione a un report &#40;Generatore report e SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d8060-137">[Add Cascading Parameters to a Report &#40;Report Builder and SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d8060-138">[Esercitazione: Aggiungere un parametro al report &#40;Generatore report&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="d8060-138">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 <span data-ttu-id="d8060-139">[Aggiungere filtri per set di dati, aree dati e gruppi &#40;Generatore report e SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="d8060-139">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="d8060-140">[Riferimenti alla raccolta dei parametri &#40;Generatore report e SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="d8060-140">[Parameters Collection References &#40;Report Builder and SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md) </span></span>  
 <span data-ttu-id="d8060-141">[Modificare l'ordine di un parametro del report &#40;Generatore report e SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d8060-141">[Change the Order of a Report Parameter &#40;Report Builder and SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d8060-142">[Aggiungere, modificare o eliminare un parametro di report &#40;Generatore report e SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d8060-142">[Add, Change, or Delete a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="d8060-143">Espressioni &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d8060-143">Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)  
  
  
