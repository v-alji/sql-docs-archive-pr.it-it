---
title: Creazione di una vista origine dati (esercitazione di base sul data mining) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c1e68a88-0f82-415d-becc-78d180d4f845
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 4582845c905ef95601cbff2c810633f0cc901e3e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626992"
---
# <a name="creating-a-data-source-view-basic-data-mining-tutorial"></a><span data-ttu-id="fa511-102">Creazione di una vista origine dati (Esercitazione di base sul data mining)</span><span class="sxs-lookup"><span data-stu-id="fa511-102">Creating a Data Source View (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="fa511-103">Una vista origine dati si basa su un'origine dati e definisce un subset dei dati che è possibile utilizzare nelle strutture di data mining.</span><span class="sxs-lookup"><span data-stu-id="fa511-103">A data source view is built on a data source and defines a subset of the data, which you can then use in your mining structures.</span></span> <span data-ttu-id="fa511-104">È inoltre possibile utilizzare la vista origine dati per aggiungere colonne, creare aggregazioni e colonne calcolate nonché aggiungere viste denominate.</span><span class="sxs-lookup"><span data-stu-id="fa511-104">You can also use the data source view to add columns, create calculated columns and aggregates, and add named views.</span></span> <span data-ttu-id="fa511-105">Le viste origine dati consentono di selezionare i dati correlati al progetto, stabilire relazioni tra tabelle e modificare la struttura dei dati senza modificare l'origine dati originale.</span><span class="sxs-lookup"><span data-stu-id="fa511-105">By using data source views, you can select the data that relates to your project, establish relationships between tables, and modify the structure of the data, without modifying the original data source.</span></span> <span data-ttu-id="fa511-106">Per altre informazioni, vedere [Viste origine dati in modelli multidimensionali](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models).</span><span class="sxs-lookup"><span data-stu-id="fa511-106">For more information, see [Data Source Views in Multidimensional Models](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models).</span></span>  
  
### <a name="to-create-a-data-source-view"></a><span data-ttu-id="fa511-107">Per creare una vista origine dati</span><span class="sxs-lookup"><span data-stu-id="fa511-107">To create a data source view</span></span>  
  
1.  <span data-ttu-id="fa511-108">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **viste origine dati**e scegliere **nuova vista origine dati**.</span><span class="sxs-lookup"><span data-stu-id="fa511-108">In **Solution Explorer**, right-click **Data Source Views**, and select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="fa511-109">Nella pagina **Creazione guidata vista origine dati** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fa511-109">On the **Welcome to the Data Source View Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="fa511-110">Nella pagina **Selezione origine dati** , in **origini dati relazionali**, selezionare l'origine dati Adventure Works DW 2012 creata nell'ultima attività.</span><span class="sxs-lookup"><span data-stu-id="fa511-110">On the **Select a Data Source** page, under **Relational data sources**, select the Adventure Works DW 2012 data source that you created in the last task.</span></span> <span data-ttu-id="fa511-111">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fa511-111">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fa511-112">Se si desidera creare un'origine dati, fare clic con il pulsante destro del mouse su **origini dati** e scegliere **nuova origine dati** per avviare la creazione guidata origine dati.</span><span class="sxs-lookup"><span data-stu-id="fa511-112">If you want to create a data source, right-click **Data Sources** and then click **New Data Source** to start the Data Source Wizard.</span></span>  
  
4.  <span data-ttu-id="fa511-113">Nella pagina **Selezione tabelle e viste** selezionare gli oggetti seguenti, quindi fare clic sulla freccia destra per includerli nella nuova vista origine dati:</span><span class="sxs-lookup"><span data-stu-id="fa511-113">On the **Select Tables and Views** page, select the following objects, and then click the right arrow to include them in the new data source view:</span></span>  
  
    -   <span data-ttu-id="fa511-114">**ProspectiveBuyer (dbo)** -tabella dei potenziali acquirenti di biciclette</span><span class="sxs-lookup"><span data-stu-id="fa511-114">**ProspectiveBuyer (dbo)** - table of prospective bike buyers</span></span>  
  
    -   <span data-ttu-id="fa511-115">**vTargetMail (dbo)** -visualizzazione dei dati cronologici sugli acquirenti di biciclette precedenti</span><span class="sxs-lookup"><span data-stu-id="fa511-115">**vTargetMail (dbo)** - view of historical data about past bike buyers</span></span>  
  
5.  <span data-ttu-id="fa511-116">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fa511-116">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="fa511-117">Per impostazione predefinita, nella pagina **Completamento procedura guidata** la vista origine dati è denominata Adventure Works DW 2012.</span><span class="sxs-lookup"><span data-stu-id="fa511-117">On the **Completing the Wizard** page, by default the data source view is named Adventure Works DW 2012.</span></span> <span data-ttu-id="fa511-118">Modificare il nome in `Targeted Mailing` , quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="fa511-118">Change the name to `Targeted Mailing`, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="fa511-119">La nuova vista origine dati verrà visualizzata nella scheda **Targeted mailing. dsv [Design]** .</span><span class="sxs-lookup"><span data-stu-id="fa511-119">The new data source view opens in the **Targeted Mailing.dsv [Design]** tab.</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="fa511-120">Attività precedente della lezione</span><span class="sxs-lookup"><span data-stu-id="fa511-120">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="fa511-121">Creazione di un'origine dati &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="fa511-121">Creating a Data Source &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="fa511-122">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="fa511-122">Next Lesson</span></span>  
 [<span data-ttu-id="fa511-123">Lezione 2: creazione di una struttura di mailing diretto &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="fa511-123">Lesson 2: Building a Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="fa511-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa511-124">See Also</span></span>  
 [<span data-ttu-id="fa511-125">Definizione di una vista origine dati &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="fa511-125">Defining a Data Source View &#40;Analysis Services&#41;</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/defining-a-data-source-view-analysis-services)  
  
  
