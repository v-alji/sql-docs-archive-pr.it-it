---
title: Creare e gestire misure (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: edc1a4b2-96d3-4f34-bb70-6cacec79e819
author: minewiskan
ms.author: owend
ms.openlocfilehash: da507bf48b285a1414ffb85ba79da50508a2ae2d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626915"
---
# <a name="create-and-manage-measures-ssas-tabular"></a><span data-ttu-id="1669b-102">Creare e gestire misure (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="1669b-102">Create and Manage Measures (SSAS Tabular)</span></span>
  <span data-ttu-id="1669b-103">Una misura è una formula creata per l'utilizzo in un report o in una tabella pivot o grafico pivot.</span><span class="sxs-lookup"><span data-stu-id="1669b-103">A measure is a formula that is created for use in a report or Excel PivotTable (or PivotChart).</span></span> <span data-ttu-id="1669b-104">Le misure possono essere basate sulle funzioni di aggregazione standard, ad esempio COUNT o SUM. In alternativa, è possibile definire formule personalizzate tramite DAX.</span><span class="sxs-lookup"><span data-stu-id="1669b-104">Measures can be based on standard aggregation functions, such as COUNT or SUM, or you can define your own formula by using DAX.</span></span> <span data-ttu-id="1669b-105">Nelle attività di questo argomento viene descritto come creare e gestire misure utilizzando la griglia delle misure di una tabella.</span><span class="sxs-lookup"><span data-stu-id="1669b-105">The tasks in this topic describe how to create and manage measures by using a table's measure grid.</span></span>  
  
 <span data-ttu-id="1669b-106">In questo argomento sono incluse le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="1669b-106">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="1669b-107">Per creare una misura tramite una formula di aggregazione standard</span><span class="sxs-lookup"><span data-stu-id="1669b-107">To create a measure using a standard aggregation formula</span></span>](#bkmk_create_stand)  
  
-   [<span data-ttu-id="1669b-108">Per creare una misura tramite una formula personalizzata</span><span class="sxs-lookup"><span data-stu-id="1669b-108">To create a measure using a custom formula</span></span>](#bkmk_create_custom)  
  
-   [<span data-ttu-id="1669b-109">Per modificare le proprietà di una misura</span><span class="sxs-lookup"><span data-stu-id="1669b-109">To edit measure properties</span></span>](#bkmk_edit)  
  
-   [<span data-ttu-id="1669b-110">Per rinominare una misura</span><span class="sxs-lookup"><span data-stu-id="1669b-110">To rename a measure</span></span>](#bkmk_rename)  
  
-   [<span data-ttu-id="1669b-111">Per eliminare una misura</span><span class="sxs-lookup"><span data-stu-id="1669b-111">To delete a measure</span></span>](#bkmk_delete)  
  
## <a name="tasks"></a><span data-ttu-id="1669b-112">Attività</span><span class="sxs-lookup"><span data-stu-id="1669b-112">Tasks</span></span>  
 <span data-ttu-id="1669b-113">Per creare e gestire misure, sarà necessario utilizzare la griglia delle misure di una tabella.</span><span class="sxs-lookup"><span data-stu-id="1669b-113">To create and manage measures, you will use a table's measure grid.</span></span> <span data-ttu-id="1669b-114">La griglia delle misure per una tabella può essere visualizzata solo in Vista dati di Progettazione modelli.</span><span class="sxs-lookup"><span data-stu-id="1669b-114">You can view the measure grid for a table in the model designer in Data View only.</span></span> <span data-ttu-id="1669b-115">Non è possibile creare misure o visualizzare la griglia delle misure in Vista diagramma; tuttavia, in tale vista è possibile visualizzare misure esistenti.</span><span class="sxs-lookup"><span data-stu-id="1669b-115">You cannot create measures or view the measure grid when in Diagram View; however, you can view existing measures in Diagram View.</span></span> <span data-ttu-id="1669b-116">Per visualizzare la griglia delle misure per una tabella, fare clic sul menu **Tabella** , quindi su **Mostra griglia delle misure**.</span><span class="sxs-lookup"><span data-stu-id="1669b-116">To show the measure grid for a table, click the **Table** menu, and then click **Show Measure Grid**.</span></span>  
  
###  <a name="to-create-a-measure-using-a-standard-aggregation-formula"></a><a name="bkmk_create_stand"></a><span data-ttu-id="1669b-117">Per creare una misura utilizzando una formula di aggregazione standard</span><span class="sxs-lookup"><span data-stu-id="1669b-117">To create a measure using a standard aggregation formula</span></span>  
  
-   <span data-ttu-id="1669b-118">Fare clic sulla colonna per la quale si desidera creare la misura, selezionare il menu **Colonna** , scegliere **Somma automatica**, quindi fare clic su un tipo di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="1669b-118">Click on the column for which you want to create the measure, then click the **Column** menu, then point to **AutoSum**, and then click an aggregation type.</span></span>  
  
     <span data-ttu-id="1669b-119">La misura verrà creata automaticamente con un nome predefinito, seguito dalla formula nella prima cella nella griglia delle misure direttamente sotto la colonna.</span><span class="sxs-lookup"><span data-stu-id="1669b-119">The measure will be created automatically with a default name, followed by the formula in the first cell in the measure grid directly beneath the column.</span></span>  
  
###  <a name="to-create-a-measure-using-a-custom-formula"></a><a name="bkmk_create_custom"></a> <span data-ttu-id="1669b-120">Per creare una misura tramite una formula personalizzata</span><span class="sxs-lookup"><span data-stu-id="1669b-120">To create a measure using a custom formula</span></span>  
  
-   <span data-ttu-id="1669b-121">Nella griglia delle misure, sotto la colonna per la quale si desidera creare la misura, fare clic su una cella, quindi nella barra della formula digitare un nome, seguito da due punti (:), da un segno di uguale (=) e dalla formula.</span><span class="sxs-lookup"><span data-stu-id="1669b-121">In the measure grid, beneath the column for which you want to create the measure, click a cell, then in the formula bar, type a name, followed by a colon (:), followed by an equals sign (=), followed by the formula.</span></span> <span data-ttu-id="1669b-122">Premere INVIO per accettare la formula.</span><span class="sxs-lookup"><span data-stu-id="1669b-122">Press ENTER to accept the formula.</span></span>  
  
###  <a name="to-edit-measure-properties"></a><a name="bkmk_edit"></a><span data-ttu-id="1669b-123">Per modificare le proprietà di una misura</span><span class="sxs-lookup"><span data-stu-id="1669b-123">To edit measure properties</span></span>  
  
-   <span data-ttu-id="1669b-124">Nella griglia delle misure fare clic su una misura, quindi nella finestra **Proprietà** digitare o selezionare un altro valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="1669b-124">In the measure grid, click a measure, and then In the **Properties** window, type or select a different property value.</span></span>  
  
###  <a name="to-rename-a-measure"></a><a name="bkmk_rename"></a><span data-ttu-id="1669b-125">Per rinominare una misura</span><span class="sxs-lookup"><span data-stu-id="1669b-125">To rename a measure</span></span>  
  
-   <span data-ttu-id="1669b-126">Nella griglia delle misure fare clic su una misura e, in **Nome misura** della finestra **Proprietà**digitare un nuovo nome, quindi fare clic su INVIO.</span><span class="sxs-lookup"><span data-stu-id="1669b-126">In the measure grid, click on a measure, and then In the **Properties** window, in **Measure Name**, type a new name, and then click ENTER.</span></span>  
  
     <span data-ttu-id="1669b-127">Inoltre, è possibile rinominare una misura nella barra della formula.</span><span class="sxs-lookup"><span data-stu-id="1669b-127">You can also rename a measure in the formula bar.</span></span> <span data-ttu-id="1669b-128">Il nome della misura precede la formula, seguito da due punti (:).</span><span class="sxs-lookup"><span data-stu-id="1669b-128">The measure name precedes the formula, followed by a colon.</span></span>  
  
###  <a name="to-delete-a-measure"></a><a name="bkmk_delete"></a><span data-ttu-id="1669b-129">Per eliminare una misura</span><span class="sxs-lookup"><span data-stu-id="1669b-129">To delete a measure</span></span>  
  
-   <span data-ttu-id="1669b-130">Nella griglia delle misure fare clic con il pulsante destro del mouse su una misura, quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="1669b-130">In the measure grid, right-click a measure, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1669b-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1669b-131">See Also</span></span>  
 <span data-ttu-id="1669b-132">[Misure &#40;SSAS tabulare&#41;](measures-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="1669b-132">[Measures &#40;SSAS Tabular&#41;](measures-ssas-tabular.md) </span></span>  
 <span data-ttu-id="1669b-133">[Indicatori KPI &#40;&#41;tabulare SSAS](kpis-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="1669b-133">[KPIs &#40;SSAS Tabular&#41;](kpis-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="1669b-134">Colonne calcolate &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="1669b-134">Calculated Columns &#40;SSAS Tabular&#41;</span></span>](ssas-calculated-columns.md)  
  
  
