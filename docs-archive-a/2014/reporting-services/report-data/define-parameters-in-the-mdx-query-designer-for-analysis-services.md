---
title: Definire i parametri in Progettazione query MDX per Analysis Services (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- parameters [Reporting Services], MDX
- Multidimensional Expressions [Reporting Services]
- Data Mining Prediction [Reporting Services]
- MDX [Reporting Services], defining parameters
- DMX [Reporting Services]
ms.assetid: 4ad1e5bc-f510-4752-b4f6-589e55317a90
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6b2b05fc0122eb25a7a0799f7b47b1b99486a28c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726568"
---
# <a name="define-parameters-in-the-mdx-query-designer-for-analysis-services-report-builder-and-ssrs"></a><span data-ttu-id="64ec3-102">Definizione dei parametri in Progettazione query MDX per Analysis Services (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="64ec3-102">Define Parameters in the MDX Query Designer for Analysis Services (Report Builder and SSRS)</span></span>
  <span data-ttu-id="64ec3-103">Per parametrizzare una query MDX per un'origine dati di [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] , è necessario aggiungere un parametro di query alla query.</span><span class="sxs-lookup"><span data-stu-id="64ec3-103">To parameterize an MDX query for an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source, you must add a query parameter to the query.</span></span> <span data-ttu-id="64ec3-104">In Progettazione query MDX, è possibile aggiungere un parametro di query sia in modalità progettazione sia in modalità query specificando un filtro.</span><span class="sxs-lookup"><span data-stu-id="64ec3-104">In the MDX query designer, you can add a query parameter in both Design mode and Query mode by specifying a filter.</span></span> <span data-ttu-id="64ec3-105">Dopo avere definito la query tramite un parametro di query, in Reporting Services vengono creati automaticamente un parametro di report e un set di dati per l'elenco dei valori validi.</span><span class="sxs-lookup"><span data-stu-id="64ec3-105">After you define the query with a query parameter, Reporting Services automatically creates a report parameter and a dataset to provide the list of valid values.</span></span> <span data-ttu-id="64ec3-106">In questo modo un utente può specificare un valore che viene passato direttamente alla query.</span><span class="sxs-lookup"><span data-stu-id="64ec3-106">This enables a user to specify a value that is passed directly to the query.</span></span>

> [!NOTE]
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]

### <a name="to-define-a-query-parameter-in-mdx-in-design-mode"></a><span data-ttu-id="64ec3-107">Per definire un parametro di query MDX in modalità progettazione</span><span class="sxs-lookup"><span data-stu-id="64ec3-107">To define a query parameter in MDX in Design mode</span></span>

1.  <span data-ttu-id="64ec3-108">Nel riquadro Dati report fare clic con il pulsante destro del mouse su un set di dati creato da un tipo di origine dati di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] e quindi scegliere **Query**.</span><span class="sxs-lookup"><span data-stu-id="64ec3-108">In the Report Data pane, right-click on a dataset created from a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source type, and then click **Query**.</span></span> <span data-ttu-id="64ec3-109">La finestra Progettazione query MDX verrà aperta in modalità progettazione.</span><span class="sxs-lookup"><span data-stu-id="64ec3-109">The MDX query designer opens in Design mode.</span></span>

2.  <span data-ttu-id="64ec3-110">Trascinare una dimensione nell'area filtro e rilasciarla nella prima cella della colonna **Dimensione** .</span><span class="sxs-lookup"><span data-stu-id="64ec3-110">Drag a dimension to the filter area and drop it on the first cell in the **Dimension** column.</span></span>

3.  <span data-ttu-id="64ec3-111">Selezionare un valore nell'elenco a discesa della colonna **Gerarchia** .</span><span class="sxs-lookup"><span data-stu-id="64ec3-111">In the **Hierarchy** column, choose a value from the drop-down list.</span></span>

4.  <span data-ttu-id="64ec3-112">Selezionare un operatore nell'elenco a discesa della colonna **Operatore** .</span><span class="sxs-lookup"><span data-stu-id="64ec3-112">In the **Operator** column, choose an operator for the drop-down list.</span></span>

5.  <span data-ttu-id="64ec3-113">Selezionare valori singoli nell'elenco a discesa della colonna **Espressione filtro** oppure fare clic sul membro **Totale** per selezionare tutti i valori.</span><span class="sxs-lookup"><span data-stu-id="64ec3-113">In the **Filter Expression** column, select individual values from the drop-down list, or click the **All** member to choose all values.</span></span>

6.  <span data-ttu-id="64ec3-114">Selezionare la casella di controllo nella colonna **Parametri** per creare un parametro del report.</span><span class="sxs-lookup"><span data-stu-id="64ec3-114">In the **Parameters** column, select the check box to create a report parameter.</span></span>

7.  <span data-ttu-id="64ec3-115">Fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="64ec3-115">Click **Run**.</span></span>

     <span data-ttu-id="64ec3-116">Dopo avere eseguito la query, fare clic su **Progettazione** nella barra degli strumenti per passare alla modalità query e visualizzare la query MDX creata.</span><span class="sxs-lookup"><span data-stu-id="64ec3-116">After you run the query, click **Design** on the toolbar to toggle to Query mode to view the MDX query that was created.</span></span> <span data-ttu-id="64ec3-117">Non modificare il testo della query in modalità query se si desidera continuare a sviluppare la query in modalità progettazione.</span><span class="sxs-lookup"><span data-stu-id="64ec3-117">Do not change the query text in Query mode if you want to continue to use Design mode to develop the query.</span></span> <span data-ttu-id="64ec3-118">Fare clic su **Progettazione** per passare di nuovo alla modalità progettazione.</span><span class="sxs-lookup"><span data-stu-id="64ec3-118">Click **Design** to toggle back to Design mode.</span></span>

8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]

     <span data-ttu-id="64ec3-119">Nel riquadro dei dati del report espandere il nodo Parametri per visualizzare il parametro del report creato automaticamente per il filtro.</span><span class="sxs-lookup"><span data-stu-id="64ec3-119">In the Report Data pane, expand the Parameters node to display the report parameter that was automatically created for the filter.</span></span>

     <span data-ttu-id="64ec3-120">Per visualizzare il set di dati dei valori disponibili per il parametro del report, fare clic con il pulsante destro del mouse su un'area vuota nel riquadro Dati report e selezionare **Mostra set di dati nascosti**.</span><span class="sxs-lookup"><span data-stu-id="64ec3-120">To view the dataset that provides available values for the report parameter, right-click any blank area in the Report Data pane, and then click **Show Hidden Datasets**.</span></span> <span data-ttu-id="64ec3-121">Nel riquadro dei dati del report verranno visualizzati tutti i set di dati contenuti nel report.</span><span class="sxs-lookup"><span data-stu-id="64ec3-121">The Report Data pane displays all datasets in the report.</span></span>

### <a name="to-define-a-query-parameter-in-mdx-in-query-mode"></a><span data-ttu-id="64ec3-122">Per definire un parametro di query MDX in modalità query</span><span class="sxs-lookup"><span data-stu-id="64ec3-122">To define a query parameter in MDX in Query mode</span></span>

1.  <span data-ttu-id="64ec3-123">Nel riquadro Dati report fare clic con il pulsante destro del mouse su un set di dati creato da un tipo di origine dati di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] e quindi scegliere **Query**.</span><span class="sxs-lookup"><span data-stu-id="64ec3-123">In the Report Data pane, right-click on a dataset created from a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source type, and then click **Query**.</span></span> <span data-ttu-id="64ec3-124">La finestra Progettazione query MDX verrà aperta in modalità progettazione.</span><span class="sxs-lookup"><span data-stu-id="64ec3-124">The MDX query designer opens in Design mode.</span></span>

2.  <span data-ttu-id="64ec3-125">Fare clic su **Progettazione** nella barra degli strumenti per passare alla modalità query.</span><span class="sxs-lookup"><span data-stu-id="64ec3-125">On the toolbar, click **Design** to toggle to Query mode.</span></span>

3.  <span data-ttu-id="64ec3-126">Nella barra degli strumenti della progettazione query MDX fare clic su **Parametri query** (![icona della finestra di dialogo Parametri query](../../analysis-services/media/iconqueryparameter.gif "Icona della finestra di dialogo Parametri query")).</span><span class="sxs-lookup"><span data-stu-id="64ec3-126">On the MDX query designer toolbar, click **Query Parameters** (![Icon for the Query Parameters dialog box](../../analysis-services/media/iconqueryparameter.gif "Icon for the Query Parameters dialog box")).</span></span> <span data-ttu-id="64ec3-127">Verrà visualizzata la finestra di dialogo Parametri query.</span><span class="sxs-lookup"><span data-stu-id="64ec3-127">The Query Parameters dialog box opens.</span></span>

4.  <span data-ttu-id="64ec3-128">Nella colonna **parametro** fare clic su **\<Enter Parameter>** , quindi digitare il nome di un parametro.</span><span class="sxs-lookup"><span data-stu-id="64ec3-128">In the **Parameter** column, click **\<Enter Parameter>**, and then type the name of a parameter.</span></span>

5.  <span data-ttu-id="64ec3-129">Selezionare un valore nell'elenco a discesa della colonna **Dimensione** .</span><span class="sxs-lookup"><span data-stu-id="64ec3-129">In the **Dimension** column, choose a value from the drop-down list.</span></span>

6.  <span data-ttu-id="64ec3-130">Selezionare un valore nell'elenco a discesa della colonna **Gerarchia** .</span><span class="sxs-lookup"><span data-stu-id="64ec3-130">In the **Hierarchy** column, choose a value from the drop-down list.</span></span>

7.  <span data-ttu-id="64ec3-131">Selezionare la casella di controllo nella colonna **Più valori** per creare un parametro multivalore.</span><span class="sxs-lookup"><span data-stu-id="64ec3-131">In the **Multiple values** column, select the check box to create a multivalue parameter.</span></span>

8.  <span data-ttu-id="64ec3-132">Nell'elenco a discesa della colonna **Predefinito** selezionare uno o più valori a seconda della selezione eseguita nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="64ec3-132">In the **Default** column, from the drop-down list, select a single value or multiple values depending on your choice in step 5.</span></span>

9. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]

10. <span data-ttu-id="64ec3-133">Nella barra degli strumenti Progettazione query fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="64ec3-133">On the query designer toolbar, click **Run**.</span></span>

11. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]

     <span data-ttu-id="64ec3-134">Nel riquadro dei dati del report espandere il nodo Parametri per visualizzare il parametro del report creato automaticamente per il filtro.</span><span class="sxs-lookup"><span data-stu-id="64ec3-134">In the Report Data pane, expand the Parameters node to display the report parameter that was automatically created for the filter.</span></span>

     <span data-ttu-id="64ec3-135">Per visualizzare il set di dati dei valori disponibili per il parametro del report, fare clic con il pulsante destro del mouse su un'area vuota nel riquadro Dati report e selezionare **Mostra set di dati nascosti**.</span><span class="sxs-lookup"><span data-stu-id="64ec3-135">To view the dataset that provides available values for the report parameter, right-click any blank area in the Report Data pane, and then click **Show Hidden Datasets**.</span></span> <span data-ttu-id="64ec3-136">Nel riquadro dei dati del report verranno visualizzati tutti i set di dati contenuti nel report.</span><span class="sxs-lookup"><span data-stu-id="64ec3-136">The Report Data pane displays all datasets in the report.</span></span>

## <a name="see-also"></a><span data-ttu-id="64ec3-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64ec3-137">See Also</span></span>
 <span data-ttu-id="64ec3-138">[Tipo di connessione Analysis Services per mdx &#40;SSRS&#41;](analysis-services-connection-type-for-mdx-ssrs.md) [Analysis Services interfaccia utente di progettazione query MDX](analysis-services-mdx-query-designer-user-interface.md)</span><span class="sxs-lookup"><span data-stu-id="64ec3-138">[Analysis Services Connection Type for MDX &#40;SSRS&#41;](analysis-services-connection-type-for-mdx-ssrs.md) [Analysis Services MDX Query Designer User Interface](analysis-services-mdx-query-designer-user-interface.md)</span></span>


