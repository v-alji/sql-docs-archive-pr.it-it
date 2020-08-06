---
title: Esplorazione del cubo distribuito | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 849c6109-1453-4fe4-a892-c49a982cfadb
author: minewiskan
ms.author: owend
ms.openlocfilehash: b876c8b2876aaf4ad28b0f4ea3fb8bab32cd787b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630136"
---
# <a name="browsing-the-deployed-cube"></a><span data-ttu-id="949f3-102">Esplorazione di un cubo distribuito</span><span class="sxs-lookup"><span data-stu-id="949f3-102">Browsing the Deployed Cube</span></span>
  <span data-ttu-id="949f3-103">Nell'attività seguente si esplorerà il cubo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial.</span><span class="sxs-lookup"><span data-stu-id="949f3-103">In the following task, you browse the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span> <span data-ttu-id="949f3-104">Poiché l'analisi confronta la misura in più dimensioni, verrà utilizzata una tabella pivot di Excel per esplorare i dati.</span><span class="sxs-lookup"><span data-stu-id="949f3-104">Because our analysis compares measure across multiple dimensions, you will use an Excel PivotTable to browse your data.</span></span> <span data-ttu-id="949f3-105">L'utilizzo di una tabella pivot consente di posizionare cliente, data e informazioni sul prodotto su diversi assi in modo da potere visualizzare come cambia Internet Sales quando viene visualizzato in periodi di tempo, dati demografici del cliente e linee di prodotti specifici.</span><span class="sxs-lookup"><span data-stu-id="949f3-105">Using a PivotTable lets you place customer, date, and product information on different axes so that you can see how Internet Sales change when viewed across specific time periods, customer demographics, and product lines.</span></span>  
  
### <a name="to-browse-the-deployed-cube"></a><span data-ttu-id="949f3-106">Per esplorare il cubo distribuito</span><span class="sxs-lookup"><span data-stu-id="949f3-106">To browse the deployed cube</span></span>  
  
1.  <span data-ttu-id="949f3-107">Per passare a Progettazione cubi in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] , fare doppio clic sul cubo \*\* [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] tutorial\*\* nella cartella **cubi** della Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="949f3-107">To switch to Cube Designer in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], double-click the **[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial** cube in the **Cubes** folder of the Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="949f3-108">Aprire la scheda **Esplorazione** , quindi fare clic sul pulsante **Riconnetti** nella barra degli strumenti della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="949f3-108">Open the **Browser** tab, and then click the **Reconnect** button on the toolbar of the designer.</span></span>  
  
3.  <span data-ttu-id="949f3-109">Fare clic sull'icona Excel per avviare Excel utilizzando il database dell'area di lavoro come origine dati.</span><span class="sxs-lookup"><span data-stu-id="949f3-109">Click the Excel icon to launch Excel using the workspace database as the data source.</span></span> <span data-ttu-id="949f3-110">Quando viene richiesto di abilitare le connessioni, fare clic su **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="949f3-110">When prompted to enable connections, click **Enable**.</span></span>  
  
4.  <span data-ttu-id="949f3-111">Nell'elenco di campi della tabella pivot espandere **Internet Sales**, quindi trascinare la misura **Sales Amount** nell'area **Valori** .</span><span class="sxs-lookup"><span data-stu-id="949f3-111">In the PivotTable Field List, expand **Internet Sales**, and then drag the **Sales Amount** measure to the **Values** area.</span></span>  
  
5.  <span data-ttu-id="949f3-112">Nell'elenco di campi della tabella pivot espandere **Product**.</span><span class="sxs-lookup"><span data-stu-id="949f3-112">In the PivotTable Field List, expand **Product**.</span></span>  
  
6.  <span data-ttu-id="949f3-113">Trascinare la gerarchia utente **Product Model Lines** nell'area **Colonne** .</span><span class="sxs-lookup"><span data-stu-id="949f3-113">Drag the **Product Model Lines** user hierarchy to the **Columns** area.</span></span>  
  
7.  <span data-ttu-id="949f3-114">Nell'elenco di campi della tabella pivot espandere **Customer**e **Location**, quindi trascinare la gerarchia **Customer Geography** dalla cartella di visualizzazione Location della dimensione Customer all'area **Righe** .</span><span class="sxs-lookup"><span data-stu-id="949f3-114">In the PivotTable Field List, expand **Customer**, expand **Location**, and then drag the **Customer Geography** hierarchy from the Location display folder in the Customer dimension to the **Rows** area.</span></span>  
  
8.  <span data-ttu-id="949f3-115">Nell'elenco di campi della tabella pivot espandere **Order Date**, quindi trascinare la gerarchia **Order Date.Calendar Date** nell'area **Filtro report** .</span><span class="sxs-lookup"><span data-stu-id="949f3-115">In the PivotTable Field List, expand **Order Date**, and then drag the **Order Date.Calendar Date** hierarchy to the **Report Filter** area.</span></span>  
  
9. <span data-ttu-id="949f3-116">Fare clic sulla freccia a destra del filtro **Order Date.Calendar Date** nel riquadro Dati, deselezionare la casella di controllo relativa al livello **(Totale)** , espandere **2006**, **H1 CY 2006**e **Q1 CY 2006**, selezionare la casella di controllo relativa a **February 2006**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="949f3-116">Click the arrow to the right of the **Order Date.Calendar Date** filter in the data pane, clear the check box for the **(All)** level, expand **2006**, expand **H1 CY 2006**, expand **Q1 CY 2006**, select the check box for **February 2006**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="949f3-117">Verranno visualizzate le vendite realizzate nel mese di febbraio 2006 tramite Internet in base alla regione e alla linea di prodotti, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="949f3-117">Internet sales by region and product line for the month of February, 2006 appear as shown in the following image.</span></span>  
  
     <span data-ttu-id="949f3-118">![Vendite Internet per regione e linea di prodotti](../../2014/tutorials/media/l3-cube-browser-finish.gif "Vendite Internet per regione e linea di prodotti")</span><span class="sxs-lookup"><span data-stu-id="949f3-118">![Internet sales by region and product line](../../2014/tutorials/media/l3-cube-browser-finish.gif "Internet sales by region and product line")</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="949f3-119">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="949f3-119">Next Lesson</span></span>  
 [<span data-ttu-id="949f3-120">Lezione 4: Definizione delle proprietà avanzate di attributi e dimensioni</span><span class="sxs-lookup"><span data-stu-id="949f3-120">Lesson 4: Defining Advanced Attribute and Dimension Properties</span></span>](lesson-4-defining-advanced-attribute-and-dimension-properties.md)  
  
  
