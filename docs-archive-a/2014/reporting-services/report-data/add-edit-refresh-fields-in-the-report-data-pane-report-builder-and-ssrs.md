---
title: Aggiungere, modificare, aggiornare i campi nel riquadro Dati report (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2e36f0fe-8100-4513-b169-14d611646f81
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2a20880b84383fc5d9f96c5611419a08facb9ac2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623842"
---
# <a name="add-edit-refresh-fields-in-the-report-data-pane-report-builder-and-ssrs"></a><span data-ttu-id="ca45b-102">Aggiunta, modifica e aggiornamento di campi nel riquadro dei dati del report (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="ca45b-102">Add, Edit, Refresh Fields in the Report Data Pane (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ca45b-103">I campi del set di dati costituiscono la raccolta predefinita di nomi di campo che rappresentano i dati che vengono restituiti quando viene eseguita una query del set di dati in un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="ca45b-103">Dataset fields are the built-in collection of field names that represent the data that is returned when a dataset query runs on an external data source.</span></span>  
  
 <span data-ttu-id="ca45b-104">Per un set di dati incorporato, i campi del set di dati sono i campi creati dopo che è stata completata la compilazione di una query, è stato chiuso il riquadro Progettazione query e sono stati calcolati i campi creati.</span><span class="sxs-lookup"><span data-stu-id="ca45b-104">For an embedded dataset, the dataset fields are the fields that are created after you finish building a query and close the Query Designer pane, and calculated fields that you create.</span></span>  
  
 <span data-ttu-id="ca45b-105">Per un set di dati condiviso, i campi del set di dati sono i campi della definizione del set di dati condiviso quando viene aggiunta al report in uso.</span><span class="sxs-lookup"><span data-stu-id="ca45b-105">For a shared dataset, the dataset fields are the fields from the shared dataset definition when you added it to your report.</span></span> <span data-ttu-id="ca45b-106">Anche se la query del set di dati condiviso sul server di report viene utilizzata sempre durante l'esecuzione del report, l'elenco di campi del set di dati nel report è statico.</span><span class="sxs-lookup"><span data-stu-id="ca45b-106">Although the query from the shared dataset on the report server is always used when you run the report, the list of dataset fields in the report is static.</span></span>  
  
 <span data-ttu-id="ca45b-107">Utilizzare **Aggiorna campi** per aggiornare l'elenco di campi nel report affinché corrisponda all'elenco corrente di campi della query del set di dati condiviso.</span><span class="sxs-lookup"><span data-stu-id="ca45b-107">Use **Refresh Fields** to update the list of fields in the report to match the current list of fields from the shared dataset query.</span></span> <span data-ttu-id="ca45b-108">L'aggiornamento dell'elenco di campi non influisce sui campi calcolati definiti nel report in uso.</span><span class="sxs-lookup"><span data-stu-id="ca45b-108">Refreshing the field list does not affect the calculated fields that you define in your report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-query-field"></a><span data-ttu-id="ca45b-109">Per aggiungere un campo di query</span><span class="sxs-lookup"><span data-stu-id="ca45b-109">To add a query field</span></span>  
  
1.  <span data-ttu-id="ca45b-110">Nel riquadro Dati report fare clic con il pulsante destro del mouse sul set di dati, quindi scegliere **Aggiungi campo query**.</span><span class="sxs-lookup"><span data-stu-id="ca45b-110">In the Report Data pane, right-click the dataset, and then click **Add Query Field**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ca45b-111">Se non è possibile visualizzare il riquadro Dati report, scegliere **Dati report** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="ca45b-111">If you cannot see the Report Data pane, from the **View** menu, click **Report Data**.</span></span>  
  
2.  <span data-ttu-id="ca45b-112">Nella pagina **Campi** della finestra di dialogo **Proprietà set di dati** fare clic su **Aggiungi**, quindi scegliere **Campo query**.</span><span class="sxs-lookup"><span data-stu-id="ca45b-112">In the **Fields** page of the **Dataset Properties** dialog box, click **Add**, and then click **Query Field**.</span></span> <span data-ttu-id="ca45b-113">Verrà aggiunta una nuova riga nella parte inferiore della griglia.</span><span class="sxs-lookup"><span data-stu-id="ca45b-113">A new row is added to the bottom of the grid.</span></span>  
  
3.  <span data-ttu-id="ca45b-114">Nella casella di testo **Nome campo** digitare il nome per il campo.</span><span class="sxs-lookup"><span data-stu-id="ca45b-114">In the **Field Name** text box, type the name for the field.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ca45b-115">I nomi devono essere univoci nell'ambito del set di dati.</span><span class="sxs-lookup"><span data-stu-id="ca45b-115">Names must be unique in the dataset.</span></span>  
  
4.  <span data-ttu-id="ca45b-116">Nella casella di testo **Origine campo** digitare il nome di un campo esistente nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="ca45b-116">In the **Field Source** text box, type the name of an existing field on the data source.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-add-a-calculated-field"></a><span data-ttu-id="ca45b-117">Per aggiungere un campo calcolato</span><span class="sxs-lookup"><span data-stu-id="ca45b-117">To add a calculated field</span></span>  
  
1.  <span data-ttu-id="ca45b-118">Nel riquadro Dati report fare clic con il pulsante destro del mouse sul set di dati, quindi scegliere **Aggiungi campo calcolato**.</span><span class="sxs-lookup"><span data-stu-id="ca45b-118">In the Report Data pane, right-click the dataset, and then click **Add Calculated Field**.</span></span>  
  
2.  <span data-ttu-id="ca45b-119">Nella pagina **Campi** della finestra di dialogo **Proprietà set di dati** fare clic su **Aggiungi**, quindi scegliere **Campo calcolato**.</span><span class="sxs-lookup"><span data-stu-id="ca45b-119">In the **Fields** page of the **Dataset Properties** dialog box, click **Add**, and then click **Calculated Field**.</span></span> <span data-ttu-id="ca45b-120">Verrà aggiunta una nuova riga nella parte inferiore della griglia.</span><span class="sxs-lookup"><span data-stu-id="ca45b-120">A new row is added to the bottom of the grid.</span></span>  
  
3.  <span data-ttu-id="ca45b-121">Nella casella di testo **Nome campo** digitare il nome per il campo.</span><span class="sxs-lookup"><span data-stu-id="ca45b-121">In the **Field Name** text bo, type the name for the field.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ca45b-122">I nomi devono essere univoci nell'ambito del set di dati.</span><span class="sxs-lookup"><span data-stu-id="ca45b-122">Names must be unique in the dataset.</span></span>  
  
4.  <span data-ttu-id="ca45b-123">Nella casella di testo **Origine campo** digitare l'espressione per il campo.</span><span class="sxs-lookup"><span data-stu-id="ca45b-123">In the **Field Source** text box, type the expression for the field.</span></span> <span data-ttu-id="ca45b-124">Fare clic sul pulsante Espressione (**fx**) per compilare un'espressione.</span><span class="sxs-lookup"><span data-stu-id="ca45b-124">Click the expression (**fx**) button to build an expression.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ca45b-125">L'espressione per un campo calcolato non può contenere funzioni di aggregazione o riferimenti a elementi del report.</span><span class="sxs-lookup"><span data-stu-id="ca45b-125">The expression for a calculated field cannot contain aggregates or references to report items.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-edit-a-query-field-or-a-dataset-field"></a><span data-ttu-id="ca45b-126">Per modificare un campo di query o un campo del set di dati</span><span class="sxs-lookup"><span data-stu-id="ca45b-126">To edit a query field or a dataset field</span></span>  
  
1.  <span data-ttu-id="ca45b-127">Nel riquadro Dati report fare clic con il pulsante destro del mouse sul campo, quindi scegliere **Proprietà campo**.</span><span class="sxs-lookup"><span data-stu-id="ca45b-127">In the Report Data pane, right-click the field, and then click **Field Properties**.</span></span>  
  
2.  <span data-ttu-id="ca45b-128">Nella pagina **Campi** della finestra di dialogo **Proprietà set di dati** fare clic su un campo esistente per selezionare la riga.</span><span class="sxs-lookup"><span data-stu-id="ca45b-128">In the **Fields** page of the **Dataset Properties** dialog box, click an existing field to select the row.</span></span>  
  
3.  <span data-ttu-id="ca45b-129">Modificare il nome o il valore del campo.</span><span class="sxs-lookup"><span data-stu-id="ca45b-129">Change the name of the field or the value of the field.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-query-field-or-a-calculated-field"></a><span data-ttu-id="ca45b-130">Per eliminare un campo di query o un campo calcolato</span><span class="sxs-lookup"><span data-stu-id="ca45b-130">To delete a query field or a calculated field</span></span>  
  
1.  <span data-ttu-id="ca45b-131">Nel riquadro dei dati del report espandere il set di dati per visualizzare la raccolta di campi.</span><span class="sxs-lookup"><span data-stu-id="ca45b-131">In the Report Data pane, expand the dataset to display the field collection.</span></span>  
  
2.  <span data-ttu-id="ca45b-132">Fare clic con il pulsante destro del mouse sul campo che si desidera rimuovere, quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="ca45b-132">Right-click the field you want to remove, and then click **Delete**.</span></span>  
  
### <a name="to-refresh-the-field-collection-in-the-report-data-pane-for-a-shared-dataset"></a><span data-ttu-id="ca45b-133">Per aggiornare la raccolta di campi nel riquadro dei dati del report per il set di dati</span><span class="sxs-lookup"><span data-stu-id="ca45b-133">To refresh the field collection in the Report Data Pane for a shared dataset</span></span>  
  
1.  <span data-ttu-id="ca45b-134">Nel riquadro dei dati del report fare clic con il pulsante destro del mouse sul set di dati e quindi scegliere **Query**.</span><span class="sxs-lookup"><span data-stu-id="ca45b-134">In the Report Data pane, right-click the dataset, and then click **Query**.</span></span>  
  
2.  <span data-ttu-id="ca45b-135">Fare clic su **Aggiorna campi**.</span><span class="sxs-lookup"><span data-stu-id="ca45b-135">Click **Refresh Fields**.</span></span>  
  
     <span data-ttu-id="ca45b-136">Sul server di report viene eseguita la query del set di dati condiviso che restituisce la raccolta campi corrente.</span><span class="sxs-lookup"><span data-stu-id="ca45b-136">On the report server, the shared dataset query runs and returns the current field collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca45b-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca45b-137">See Also</span></span>  
 <span data-ttu-id="ca45b-138">[Raccolta di campi del set di dati &#40;Generatore report e SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ca45b-138">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ca45b-139">[Aggiungere dati a un report &#40;Generatore report e SSRS&#41;](report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ca45b-139">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="ca45b-140">[Set di dati condivisi e incorporati del report &#40;Generatore report e SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ca45b-140">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ca45b-141">[Strumenti di progettazione query in Reporting Services](../reporting-services-query-designers.md) </span><span class="sxs-lookup"><span data-stu-id="ca45b-141">[Reporting Services Query Designers](../reporting-services-query-designers.md) </span></span>  
 [<span data-ttu-id="ca45b-142">Finestre di progettazione query &#40;Generatore report&#41;</span><span class="sxs-lookup"><span data-stu-id="ca45b-142">Query Designers &#40;Report Builder&#41;</span></span>](../query-designers-report-builder.md)  
  
  
