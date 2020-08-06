---
title: Aggiungere un parametro multivalore a un report | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 12ad0e77-4c28-4bbb-ab11-473ae89ec9f1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5269293b6a21f3b1d82eb6835efbd275e3be9620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712759"
---
# <a name="add-a-multi-value-parameter-to-a-report"></a><span data-ttu-id="25941-102">Aggiunta di un parametro multivalore a un report</span><span class="sxs-lookup"><span data-stu-id="25941-102">Add a multi-value parameter to a Report</span></span>
  <span data-ttu-id="25941-103">È possibile aggiungere un parametro a un report che consente all'utente di selezionare più valori per il parametro.</span><span class="sxs-lookup"><span data-stu-id="25941-103">You can add a parameter to a report that allows the user to select more than one value for the parameter.</span></span>  
  
 <span data-ttu-id="25941-104">È possibile passare più valori di parametro al report nell'URL del report.</span><span class="sxs-lookup"><span data-stu-id="25941-104">You can pass multiple parameter values to the report within the report URL.</span></span> <span data-ttu-id="25941-105">Per un esempio di URL in cui è incluso un parametro multivalore, vedere [Passare un parametro del report in un URL](../pass-a-report-parameter-within-a-url.md).</span><span class="sxs-lookup"><span data-stu-id="25941-105">For a URL example includes a multi-value parameter, see [Pass a Report Parameter Within a URL](../pass-a-report-parameter-within-a-url.md).</span></span>  
  
 <span data-ttu-id="25941-106">Per informazioni su come passare più valori di parametro a una stored procedure, vedere [Working With Multi-Select Parameters for SSRS Reports](https://go.microsoft.com/fwlink/?LinkId=321529) (Utilizzo di parametri a selezione multipla per report SSRS) nel sito Web mssqltips.com.</span><span class="sxs-lookup"><span data-stu-id="25941-106">For information on how to pass multiple parameter values to a stored procedure, see [Working With Multi-Select Parameters for SSRS Reports](https://go.microsoft.com/fwlink/?LinkId=321529) on mssqltips.com.</span></span>  
  
### <a name="to-add-a-multi-value-parameter"></a><span data-ttu-id="25941-107">Per aggiungere un parametro multivalore</span><span class="sxs-lookup"><span data-stu-id="25941-107">To add a multi-value parameter</span></span>  
  
1.  <span data-ttu-id="25941-108">In Generatore report aprire il report a cui si desidera aggiungere il parametro multivalore.</span><span class="sxs-lookup"><span data-stu-id="25941-108">In Report Builder, open the report that you want to add the multi-value parameter to.</span></span>  
  
2.  <span data-ttu-id="25941-109">Fare clic con il pulsante destro del mouse sul set di dati del report e quindi scegliere **Proprietà set di dati**.</span><span class="sxs-lookup"><span data-stu-id="25941-109">Right-click the report dataset, and then click **Dataset Properties**</span></span>  
  
3.  <span data-ttu-id="25941-110">Aggiungere una variabile alla query del set di dati modificando il testo della query nella casella **Query** o aggiungendo un filtro mediante la finestra Progettazione query.</span><span class="sxs-lookup"><span data-stu-id="25941-110">Add a variable to the dataset query by either editing the query text in the **Query** box, or by adding a filter by using the query designer.</span></span> <span data-ttu-id="25941-111">Per altre informazioni, vedere [Compilare una query in Progettazione query relazionale &#40;Generatore report e SSRS&#41;](../report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="25941-111">For more information, see [Build a Query in the Relational Query Designer &#40;Report Builder and SSRS&#41;](../report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="25941-112">Il testo della query non deve includere l'istruzione DECLARE per la variabile di query.</span><span class="sxs-lookup"><span data-stu-id="25941-112">The query text must not include the DECLARE statement for the query variable.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="25941-113">Il testo per la variabile di query deve includere l'operatore `IN`, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="25941-113">The text for the query variable must include the `IN` operator, as shown in the following example.</span></span>  
  
    ```  
    WHERE  
      Production.ProductInventory.ProductID IN (@ProductID)  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="25941-114">Se non si includono le parentesi attorno alla variabile come illustrato in precedenza, il rendering del report non viene eseguito e viene visualizzato l'errore "dichiarare la variabile scalare".</span><span class="sxs-lookup"><span data-stu-id="25941-114">If you don't include the parentheses around the variable as shown above, the report fails to render and the "must declare the scalar variable" error is displayed.</span></span>  
  
     <span data-ttu-id="25941-115">Un parametro del set di dati per un set di dati incorporato o un set di dati condiviso viene creato automaticamente per la variabile di query.</span><span class="sxs-lookup"><span data-stu-id="25941-115">A dataset parameter for an embedded dataset or a shared dataset is created automatically for the query variable.</span></span> <span data-ttu-id="25941-116">Un parametro del report viene creato automaticamente per il parametro del set di dati.</span><span class="sxs-lookup"><span data-stu-id="25941-116">A report parameter is created automatically for the dataset parameter.</span></span>  
  
4.  <span data-ttu-id="25941-117">Nel riquadro **Dati report** espandere il nodo **Parametri** , fare clic con il pulsante destro del mouse sul parametro del report che è stato creato automaticamente per il parametro del set di dati e quindi scegliere **Proprietà parametri**.</span><span class="sxs-lookup"><span data-stu-id="25941-117">In the **Report Data** pane, expand the **Parameters** node, right-click the report parameter that was automatically created for the dataset parameter, and then click **Parameter Properties**.</span></span>  
  
5.  <span data-ttu-id="25941-118">Nella scheda **Generale** selezionare **Consenti più valori** per consentire a un utente di selezionare più valori per il parametro.</span><span class="sxs-lookup"><span data-stu-id="25941-118">In the **General** tab, select **Allow multiple values** to allow a user to select more than one value for the parameter.</span></span>  
  
6.  <span data-ttu-id="25941-119">Facoltativamente, nella scheda dei valori **Disponibile** specificare un elenco di valori disponibili da visualizzare all'utente.</span><span class="sxs-lookup"><span data-stu-id="25941-119">(Optionally) In the **Available** values tab, specify a list of available values to display to the user.</span></span>  
  
     <span data-ttu-id="25941-120">Tale elenco limita le scelte dell'utente ai soli valori validi per il parametro.</span><span class="sxs-lookup"><span data-stu-id="25941-120">An available values list limits the choices a user can make to only valid values for the parameter.</span></span> <span data-ttu-id="25941-121">Per più valori, la funzionalità **Seleziona tutto** è disponibile all'inizio dell'elenco, in modo che l'utente possa selezionare o deselezionare tutti i valori con un solo clic.</span><span class="sxs-lookup"><span data-stu-id="25941-121">For multiple values, the top of list begins with a **Select All** feature so the user can select or clear all values with a single click.</span></span> <span data-ttu-id="25941-122">Se si sceglie di ottenere i valori disponibili per il parametro del report da una query del set di dati, assicurarsi di selezionare un set di dati che non contenga la variabile di query associata allo stesso parametro del report.</span><span class="sxs-lookup"><span data-stu-id="25941-122">If you choose to get the available values for the report parameter from a dataset query, be sure to select a dataset that does not contain the query variable that is associated with the same report parameter.</span></span>  
  
     <span data-ttu-id="25941-123">Per altre informazioni, vedere [Aggiungere, modificare o eliminare valori disponibili per un parametro di report &#40;Generatore report e SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span><span class="sxs-lookup"><span data-stu-id="25941-123">For more information, see [Add, Change, or Delete Available Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span></span>  
  
### <a name="to-add-a-multi-value-parameter"></a><span data-ttu-id="25941-124">Per aggiungere un parametro multivalore</span><span class="sxs-lookup"><span data-stu-id="25941-124">To add a multi-value parameter</span></span>  
  
1.  <span data-ttu-id="25941-125">In Generatore report aprire il report a cui si desidera aggiungere il parametro multivalore.</span><span class="sxs-lookup"><span data-stu-id="25941-125">In Report Builder, open the report that you want to add the multi-value parameter to.</span></span>  
  
2.  <span data-ttu-id="25941-126">Fare clic con il pulsante destro del mouse sul set di dati del report e quindi scegliere **Proprietà set di dati**.</span><span class="sxs-lookup"><span data-stu-id="25941-126">Right-click the report dataset, and then click **Dataset Properties**</span></span>  
  
3.  <span data-ttu-id="25941-127">Aggiungere una variabile alla query del set di dati modificando il testo della query nella casella **Query** o aggiungendo un filtro mediante la finestra Progettazione query.</span><span class="sxs-lookup"><span data-stu-id="25941-127">Add a variable to the dataset query by either editing the query text in the **Query** box, or by adding a filter by using the query designer.</span></span> <span data-ttu-id="25941-128">Per altre informazioni, vedere [Compilare una query in Progettazione query relazionale &#40;Generatore report e SSRS&#41;](../report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="25941-128">For more information, see [Build a Query in the Relational Query Designer &#40;Report Builder and SSRS&#41;](../report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="25941-129">Il testo della query non deve includere l'istruzione DECLARE per la variabile di query.</span><span class="sxs-lookup"><span data-stu-id="25941-129">The query text must not include the DECLARE statement for the query variable.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="25941-130">Il testo per la variabile di query deve includere l'operatore `IN`, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="25941-130">The text for the query variable must include the `IN` operator, as shown in the following example.</span></span>  
  
    ```  
    WHERE  
      Production.ProductInventory.ProductID IN (@ProductID)  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="25941-131">Se non si includono le parentesi attorno alla variabile come illustrato in precedenza, il rendering del report non viene eseguito e viene visualizzato l'errore "dichiarare la variabile scalare".</span><span class="sxs-lookup"><span data-stu-id="25941-131">If you don't include the parentheses around the variable as shown above, the report fails to render and the "must declare the scalar variable" error is displayed.</span></span>  
  
     <span data-ttu-id="25941-132">Un parametro del set di dati per un set di dati incorporato o un set di dati condiviso viene creato automaticamente per la variabile di query.</span><span class="sxs-lookup"><span data-stu-id="25941-132">A dataset parameter for an embedded dataset or a shared dataset is created automatically for the query variable.</span></span> <span data-ttu-id="25941-133">Un parametro del report viene creato automaticamente per il parametro del set di dati.</span><span class="sxs-lookup"><span data-stu-id="25941-133">A report parameter is created automatically for the dataset parameter.</span></span>  
  
4.  <span data-ttu-id="25941-134">Nel riquadro **Dati report** espandere il nodo **Parametri** , fare clic con il pulsante destro del mouse sul parametro del report che è stato creato automaticamente per il parametro del set di dati e quindi scegliere **Proprietà parametri**.</span><span class="sxs-lookup"><span data-stu-id="25941-134">In the **Report Data** pane, expand the **Parameters** node, right-click the report parameter that was automatically created for the dataset parameter, and then click **Parameter Properties**.</span></span>  
  
5.  <span data-ttu-id="25941-135">Nella scheda **Generale** selezionare **Consenti più valori** per consentire a un utente di selezionare più valori per il parametro.</span><span class="sxs-lookup"><span data-stu-id="25941-135">In the **General** tab, select **Allow multiple values** to allow a user to select more than one value for the parameter.</span></span>  
  
6.  <span data-ttu-id="25941-136">Facoltativamente, nella scheda dei valori **Disponibile** specificare un elenco di valori disponibili da visualizzare all'utente.</span><span class="sxs-lookup"><span data-stu-id="25941-136">(Optionally) In the **Available** values tab, specify a list of available values to display to the user.</span></span>  
  
     <span data-ttu-id="25941-137">Tale elenco limita le scelte dell'utente ai soli valori validi per il parametro.</span><span class="sxs-lookup"><span data-stu-id="25941-137">An available values list limits the choices a user can make to only valid values for the parameter.</span></span> <span data-ttu-id="25941-138">Per più valori, la funzionalità **Seleziona tutto** è disponibile all'inizio dell'elenco, in modo che l'utente possa selezionare o deselezionare tutti i valori con un solo clic.</span><span class="sxs-lookup"><span data-stu-id="25941-138">For multiple values, the top of list begins with a **Select All** feature so the user can select or clear all values with a single click.</span></span> <span data-ttu-id="25941-139">Se si sceglie di ottenere i valori disponibili per il parametro del report da una query del set di dati, assicurarsi di selezionare un set di dati che non contenga la variabile di query associata allo stesso parametro del report.</span><span class="sxs-lookup"><span data-stu-id="25941-139">If you choose to get the available values for the report parameter from a dataset query, be sure to select a dataset that does not contain the query variable that is associated with the same report parameter.</span></span>  
  
     <span data-ttu-id="25941-140">Per altre informazioni, vedere [Aggiungere, modificare o eliminare valori disponibili per un parametro di report &#40;Generatore report e SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span><span class="sxs-lookup"><span data-stu-id="25941-140">For more information, see [Add, Change, or Delete Available Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25941-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25941-141">See Also</span></span>  
 <span data-ttu-id="25941-142">[Aggiungere parametri di propagazione a un report &#40;Generatore report e SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="25941-142">[Add Cascading Parameters to a Report &#40;Report Builder and SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="25941-143">Aggiungere, modificare o eliminare un parametro di report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="25941-143">Add, Change, or Delete a Report Parameter &#40;Report Builder and SSRS&#41;</span></span>](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md)  
  
  
