---
title: Aggiungere, modificare o eliminare un parametro di report (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d44a8e0a-10cf-4502-9391-09743ffc9bad
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 231cd51d7ed0a481f004b39a2e8819df3fc33748
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628473"
---
# <a name="add-change-or-delete-a-report-parameter-report-builder-and-ssrs"></a><span data-ttu-id="b996c-102">Aggiungere, modificare o eliminare un parametro di report (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="b996c-102">Add, Change, or Delete a Report Parameter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b996c-103">Un parametro di report consente di scegliere i dati del report, connettere report correlati e variare la presentazione del report.</span><span class="sxs-lookup"><span data-stu-id="b996c-103">A report parameter provides a way to choose report data, connect related reports together, and vary the report presentation.</span></span> <span data-ttu-id="b996c-104">È possibile specificare un valore predefinito e un elenco di valori disponibili per consentire all'utente di modificare la selezione.</span><span class="sxs-lookup"><span data-stu-id="b996c-104">You can provide a default value and a list of available values, and the user can change the selection.</span></span>  
  
 <span data-ttu-id="b996c-105">Dopo aver pubblicato un report, è possibile modificare i valori predefiniti, i valori disponibili e altre proprietà relative a un parametro di report sul server di report.</span><span class="sxs-lookup"><span data-stu-id="b996c-105">After you publish a report, you can change the default values, the available values, and other properties for a report parameter on the report server.</span></span> <span data-ttu-id="b996c-106">Per fornire più set di valori predefiniti del parametro, è possibile creare report collegati.</span><span class="sxs-lookup"><span data-stu-id="b996c-106">You can provide multiple sets of default parameter values by creating linked reports.</span></span> <span data-ttu-id="b996c-107">Per ulteriori informazioni, vedere "Impostazione delle proprietà dei parametri per un report pubblicato" nella documentazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] inclusa nella [documentazione online di SQL Server](https://go.microsoft.com/fwlink/?linkid=120955).</span><span class="sxs-lookup"><span data-stu-id="b996c-107">For more information, see "Setting Parameter Properties for a Published Report" in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] documentation in [SQL Server Books Online](https://go.microsoft.com/fwlink/?linkid=120955).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-or-edit-a-report-parameter"></a><span data-ttu-id="b996c-108">Per aggiungere o modificare un parametro di report</span><span class="sxs-lookup"><span data-stu-id="b996c-108">To add or edit a report parameter</span></span>  
  
1.  <span data-ttu-id="b996c-109">Nel riquadro **Dati report** fare clic con il pulsante destro del mouse sul nodo **Parametri** e scegliere **Aggiungi parametro**.</span><span class="sxs-lookup"><span data-stu-id="b996c-109">In the **Report Data** pane, right-click the **Parameters** node and click **Add Parameter**.</span></span> <span data-ttu-id="b996c-110">Verrà visualizzata la finestra di dialogo **Proprietà parametri report** .</span><span class="sxs-lookup"><span data-stu-id="b996c-110">The **Report Parameter Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="b996c-111">In **Nome**digitare il nome del parametro o accettare il nome predefinito.</span><span class="sxs-lookup"><span data-stu-id="b996c-111">In **Name**, type the name of the parameter or accept the default name.</span></span>  
  
3.  <span data-ttu-id="b996c-112">Nella casella **Messaggio di richiesta**digitare il testo da visualizzare accanto alla casella di testo del parametro quando l'utente esegue il report.</span><span class="sxs-lookup"><span data-stu-id="b996c-112">In **Prompt**, type the text that appears next to the parameter text box when the user runs the report.</span></span>  
  
4.  <span data-ttu-id="b996c-113">Nella casella **Tipo di dati**selezionare il tipo di dati per il valore del parametro.</span><span class="sxs-lookup"><span data-stu-id="b996c-113">In **Data type**, select the data type for the parameter value.</span></span>  
  
5.  <span data-ttu-id="b996c-114">Se il parametro può contenere un valore vuoto, selezionare **Consenti nessun valore**.</span><span class="sxs-lookup"><span data-stu-id="b996c-114">If the parameter can contain a blank value, select **Allow blank value**.</span></span>  
  
6.  <span data-ttu-id="b996c-115">Se il parametro può contenere un valore Null, selezionare **Consenti valore Null**.</span><span class="sxs-lookup"><span data-stu-id="b996c-115">If the parameter can contain a null value, select **Allow null value**.</span></span>  
  
7.  <span data-ttu-id="b996c-116">Per consentire agli utenti la selezione di più valori per il parametro, selezionare **Consenti più valori**.</span><span class="sxs-lookup"><span data-stu-id="b996c-116">To allow a user to select more than one value for the parameter, select **Allow multiple values**.</span></span>  
  
8.  <span data-ttu-id="b996c-117">Impostare l'opzione di visibilità.</span><span class="sxs-lookup"><span data-stu-id="b996c-117">Set the visibility option.</span></span>  
  
    -   <span data-ttu-id="b996c-118">Per visualizzare il parametro sulla barra degli strumenti all'inizio del report, selezionare **Visibile**.</span><span class="sxs-lookup"><span data-stu-id="b996c-118">To show the parameter on the toolbar at the top of the report, select **Visible**.</span></span>  
  
    -   <span data-ttu-id="b996c-119">Per nascondere il parametro in modo da non visualizzarlo sulla barra degli strumenti, selezionare **Nascosto**.</span><span class="sxs-lookup"><span data-stu-id="b996c-119">To hide the parameter so that it does not display on the toolbar, select **Hidden**.</span></span>  
  
    -   <span data-ttu-id="b996c-120">Per nascondere il parametro e proteggerlo da eventuali modifiche sul server di report in seguito alla relativa pubblicazione, selezionare **Interno**.</span><span class="sxs-lookup"><span data-stu-id="b996c-120">To hide the parameter and protect it from being modified on the report server after the report is published, select **Internal**.</span></span> <span data-ttu-id="b996c-121">Il parametro di report potrà essere visualizzato solo nella relativa definizione.</span><span class="sxs-lookup"><span data-stu-id="b996c-121">The report parameter can then only be viewed in the report definition.</span></span> <span data-ttu-id="b996c-122">Per questa opzione è necessario impostare un valore predefinito o consentire l'immissione di un valore Null per il parametro.</span><span class="sxs-lookup"><span data-stu-id="b996c-122">For this option, you must set a default value or allow the parameter to accept a null value.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-report-parameter"></a><span data-ttu-id="b996c-123">Per eliminare un parametro di report</span><span class="sxs-lookup"><span data-stu-id="b996c-123">To delete a report parameter</span></span>  
  
1.  <span data-ttu-id="b996c-124">Nel riquadro **dei dati del report** espandere il nodo **parametri** .</span><span class="sxs-lookup"><span data-stu-id="b996c-124">In the **Report Data** pane, expand the **Parameters** node.</span></span>  
  
2.  <span data-ttu-id="b996c-125">Fare clic con il pulsante destro del mouse sul parametro di report, quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="b996c-125">Right-click the report parameter and click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b996c-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b996c-126">See Also</span></span>  
 <span data-ttu-id="b996c-127">[Aggiunta, modifica o eliminazione dei valori disponibili per un parametro di report &#40;Generatore report e SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md) </span><span class="sxs-lookup"><span data-stu-id="b996c-127">[Add, Change, or Delete Available Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md) </span></span>  
 <span data-ttu-id="b996c-128">[Aggiungere, modificare o eliminare valori predefiniti per un parametro di report &#40;Generatore report e SSRS&#41;](add-change-or-delete-default-values-for-a-report-parameter.md) </span><span class="sxs-lookup"><span data-stu-id="b996c-128">[Add, Change, or Delete Default Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-default-values-for-a-report-parameter.md) </span></span>  
 <span data-ttu-id="b996c-129">[Modificare l'ordine di un parametro di report &#40;Generatore report e SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b996c-129">[Change the Order of a Report Parameter &#40;Report Builder and SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b996c-130">[Parametri del report &#40;Generatore report e Progettazione report&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="b996c-130">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="b996c-131">[Guida Generatore report per finestre di dialogo, riquadri e procedure guidate](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="b996c-131">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="b996c-132">[Aggiungere parametri di propagazione a un report &#40;Generatore report e SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b996c-132">[Add Cascading Parameters to a Report &#40;Report Builder and SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b996c-133">[Esercitazione: aggiungere un parametro al report &#40;Generatore report&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="b996c-133">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 <span data-ttu-id="b996c-134">[Esercitazioni &#40;Generatore report&#41;](../report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="b996c-134">[Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md) </span></span>  
 <span data-ttu-id="b996c-135">[Aggiungere filtri del set di dati, aree dati e gruppi &#40;Generatore report e SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="b996c-135">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="b996c-136">[Riferimenti alla raccolta Parameters &#40;Generatore report e SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="b996c-136">[Parameters Collection References &#40;Report Builder and SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md) </span></span>  
 [<span data-ttu-id="b996c-137">Aggiunta di un parametro multivalore a un report</span><span class="sxs-lookup"><span data-stu-id="b996c-137">Add a multi-value parameter to a Report</span></span>](add-a-multi-value-parameter-to-a-report.md)  
  
  
