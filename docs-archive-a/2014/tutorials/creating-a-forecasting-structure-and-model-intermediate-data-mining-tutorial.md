---
title: Creazione di una struttura e di un modello di previsione (Esercitazione intermedia sul data mining) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 5f55cbf6-0db4-4cb4-a0f5-e27441873d4f
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d77b15a9a8efe9a9c6faec49a2274ee182706992
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711208"
---
# <a name="creating-a-forecasting-structure-and-model-intermediate-data-mining-tutorial"></a><span data-ttu-id="a10d5-102">Creazione di una struttura e di un modello di previsione (Esercitazione intermedia sul data mining)</span><span class="sxs-lookup"><span data-stu-id="a10d5-102">Creating a Forecasting Structure and Model (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="a10d5-103">Verrà ora utilizzata la Creazione guidata modello di data mining per creare una nuova struttura di data mining e un nuovo modello di data mining basati sulla vista origine dati appena creata.</span><span class="sxs-lookup"><span data-stu-id="a10d5-103">Next, you will use the Data Mining Wizard to create a new mining structure and mining model based on the data source view that you just created.</span></span> <span data-ttu-id="a10d5-104">In questa attività si specificherà che il modello di data mining deve utilizzare l'algoritmo [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series.</span><span class="sxs-lookup"><span data-stu-id="a10d5-104">In this task you will specify that the mining model should use the [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series algorithm.</span></span>  
  
### <a name="to-create-a-forecasting-mining-structure"></a><span data-ttu-id="a10d5-105">Per creare una struttura di data mining per la previsione</span><span class="sxs-lookup"><span data-stu-id="a10d5-105">To create a forecasting mining structure</span></span>  
  
1.  <span data-ttu-id="a10d5-106">In Esplora soluzioni in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] fare clic con il pulsante destro del mouse su **strutture di data mining** e scegliere **nuova struttura di data mining**</span><span class="sxs-lookup"><span data-stu-id="a10d5-106">In Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], right-click **Mining Structures** and select **New Mining Structure**.</span></span>  
  
2.  <span data-ttu-id="a10d5-107">Nella pagina iniziale **Creazione guidata modello di data mining** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a10d5-107">On the **Welcome to the Data Mining Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="a10d5-108">Nella pagina **Selezione metodo di definizione** verificare che sia selezionato **da database relazionale o data warehouse esistente** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a10d5-108">On the **Select the Definition Method** page, verify that **From existing relational database or data warehouse** is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="a10d5-109">Nella pagina **Crea la struttura di data mining** in **cui data mining tecnica si desidera utilizzare?** selezionare **Microsoft Time Series**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a10d5-109">On the **Create the Data Mining Structure** page, under **Which data mining technique do you want to use?**, select **Microsoft Time Series**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="a10d5-110">Nella pagina **Selezione vista origine dati** , in **viste origine dati disponibili**, selezionare **SalesByRegion**.</span><span class="sxs-lookup"><span data-stu-id="a10d5-110">On the **Select Data Source View** page, under **Available data source views**, select **SalesByRegion**.</span></span>  
  
6.  <span data-ttu-id="a10d5-111">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a10d5-111">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="a10d5-112">Nella pagina **impostazione tipi di tabelle** assicurarsi che la casella di controllo nella colonna **case** per la tabella vTimeSeries sia selezionata, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a10d5-112">On the **Specify Table Types** page, ensure that the check box in the **Case** column for the vTimeSeries table is selected, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="a10d5-113">Nella pagina **impostazione dati di training** selezionare le caselle di controllo nella colonna **chiave** per le colonne ModelRegion e ReportingDate.</span><span class="sxs-lookup"><span data-stu-id="a10d5-113">On the **Specify the Training Data** page, select the check boxes in the **Key** column for the ModelRegion and ReportingDate columns.</span></span>  
  
     <span data-ttu-id="a10d5-114">La colonna ReportingDate dovrebbe essere selezionata per impostazione predefinita, poiché è stata specificata come chiave primaria logica quando è stata creata la vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="a10d5-114">ReportingDate should be selected by default, because you specified this column as the logical primary key when you created the data source view.</span></span> <span data-ttu-id="a10d5-115">Aggiungendo ModelRegion come seconda chiave, si indica all'algoritmo di creare una serie temporale distinta per ogni combinazione di modello e area geografica elencata in questo campo.</span><span class="sxs-lookup"><span data-stu-id="a10d5-115">By adding ModelRegion as a second key, you are telling the algorithm to create a separate time series for each combination of model and region listed in this field.</span></span>  
  
9. <span data-ttu-id="a10d5-116">Selezionare le caselle di controllo nelle colonne **input** e **stimabile** per la quantità, colonna, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a10d5-116">Select the check boxes in the **Input** and **Predictable** columns for the Quantity, column, and then click **Next**.</span></span>  
  
     <span data-ttu-id="a10d5-117">Selezionando **stimabile**, si indica che si desidera creare previsioni sui dati in questa colonna.</span><span class="sxs-lookup"><span data-stu-id="a10d5-117">By selecting **Predictable**, you indicate that you want to create forecasts on the data in this column.</span></span> <span data-ttu-id="a10d5-118">Tuttavia, poiché si desidera basare le previsioni sui dati passati, è inoltre necessario aggiungere la colonna come input.</span><span class="sxs-lookup"><span data-stu-id="a10d5-118">However, because you want to base the forecasts on past data, you must also add the column as an input.</span></span>  
  
10. <span data-ttu-id="a10d5-119">Nella pagina **specificare il tipo di dati e il contenuto delle colonne**, rivedere le selezioni.</span><span class="sxs-lookup"><span data-stu-id="a10d5-119">On the page **Specify Columns' Content and Data Type**, review the selections.</span></span>  
  
     <span data-ttu-id="a10d5-120">La colonna ModelRegion viene designata come colonna **chiave** e la colonna ReportingDate viene automaticamente designata come colonna **chiave temporale** .</span><span class="sxs-lookup"><span data-stu-id="a10d5-120">The ModelRegion column is designated as a **Key** column and the ReportingDate column is automatically designated as a **Key Time** column.</span></span> <span data-ttu-id="a10d5-121">È consentito un solo tipo per ogni tipo di chiave.</span><span class="sxs-lookup"><span data-stu-id="a10d5-121">You can have only one of each type of key.</span></span>  
  
11. <span data-ttu-id="a10d5-122">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a10d5-122">Click **Next**.</span></span>  
  
12. <span data-ttu-id="a10d5-123">Nella pagina **Completamento procedura guidata** Digitare per **Nome struttura di data mining** `Forecasting` .</span><span class="sxs-lookup"><span data-stu-id="a10d5-123">On the **Completing the Wizard** page, for **Mining structure name**, type `Forecasting`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a10d5-124">L'opzione di drill-through non è disponibile per i modelli Time Series.</span><span class="sxs-lookup"><span data-stu-id="a10d5-124">The option to enable drillthrough is not available for time series models.</span></span>  
  
13. <span data-ttu-id="a10d5-125">In **nome modello di data mining**Digitare `Forecasting` , quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="a10d5-125">In **Mining model name**, type `Forecasting`, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="a10d5-126">Progettazione modelli di data mining viene aperto per visualizzare la `Forecasting` struttura di data mining appena creata.</span><span class="sxs-lookup"><span data-stu-id="a10d5-126">Data Mining Designer opens to display the `Forecasting` mining structure that you just created.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="a10d5-127">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="a10d5-127">Next Task in Lesson</span></span>  
 [<span data-ttu-id="a10d5-128">Modifica della struttura di previsione &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="a10d5-128">Modifying the Forecasting Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/modifying-the-forecasting-structure-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="a10d5-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a10d5-129">See Also</span></span>  
 <span data-ttu-id="a10d5-130">[Progettazione modelli di data mining](../../2014/analysis-services/data-mining/data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="a10d5-130">[Data Mining Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span></span>  
 [<span data-ttu-id="a10d5-131">Algoritmo Microsoft Time Series</span><span class="sxs-lookup"><span data-stu-id="a10d5-131">Microsoft Time Series Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md)  
  
  
