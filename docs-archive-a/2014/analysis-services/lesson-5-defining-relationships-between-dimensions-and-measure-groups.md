---
title: 'Lezione 5: definizione delle relazioni tra dimensioni e gruppi di misure | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 31aeb271-47a1-433b-a8a5-120bcb4584d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6dbdf20e64e3cd8adc751b69122a380d7b3b3648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627498"
---
# <a name="lesson-5-defining-relationships-between-dimensions-and-measure-groups"></a><span data-ttu-id="cec9c-102">Lezione 5: Definizione delle relazioni tra dimensioni e gruppi di misure</span><span class="sxs-lookup"><span data-stu-id="cec9c-102">Lesson 5: Defining Relationships Between Dimensions and Measure Groups</span></span>
  <span data-ttu-id="cec9c-103">Nelle lezioni precedenti di questa esercitazione è stato spiegato che le dimensioni del database aggiunte a un cubo possono essere utilizzate come base per una o più dimensioni del cubo.</span><span class="sxs-lookup"><span data-stu-id="cec9c-103">In the previous lessons in this tutorial, you learned that database dimensions added to a cube can be used as the basis for one or more cube dimensions.</span></span> <span data-ttu-id="cec9c-104">In questa lezione verranno illustrate le procedure per definire tipi diversi di relazioni tra dimensioni e gruppi di misure del cubo, nonché per specificare le proprietà di tali relazioni.</span><span class="sxs-lookup"><span data-stu-id="cec9c-104">In this lesson, you learn to define different types of relationships between cube dimensions and measure groups, and to specify the properties of these relationships.</span></span>  
  
 <span data-ttu-id="cec9c-105">Per altre informazioni, vedere [Relazioni tra dimensioni](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="cec9c-105">For more information, see [Dimension Relationships](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cec9c-106">I progetti completati per tutte le lezioni in questa esercitazione sono disponibili online.</span><span class="sxs-lookup"><span data-stu-id="cec9c-106">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="cec9c-107">È possibile passare a qualsiasi lezione utilizzando il progetto completato della lezione precedente come punto iniziale.</span><span class="sxs-lookup"><span data-stu-id="cec9c-107">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="cec9c-108">[Fare clic qui](https://go.microsoft.com/fwlink/?LinkID=221866) per scaricare i progetti di esempio usati in questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="cec9c-108">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 <span data-ttu-id="cec9c-109">In questa lezione sono incluse le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="cec9c-109">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="cec9c-110">Definizione di una relazione di tipo Riferimento</span><span class="sxs-lookup"><span data-stu-id="cec9c-110">Defining a Referenced Relationship</span></span>](lesson-5-1-defining-a-referenced-relationship.md)  
 <span data-ttu-id="cec9c-111">In questa attività viene illustrato come collegare indirettamente una dimensione a una tabella dei fatti tramite una dimensione collegata direttamente tramite una relazione tra chiave primaria e chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="cec9c-111">In this task, you learn to link a dimension to a fact table indirectly through a dimension that is linked directly through a primary key-foreign key relationship.</span></span>  
  
 [<span data-ttu-id="cec9c-112">Definizione di una relazione di tipo Fatti</span><span class="sxs-lookup"><span data-stu-id="cec9c-112">Defining a Fact Relationship</span></span>](lesson-5-2-defining-a-fact-relationship.md)  
 <span data-ttu-id="cec9c-113">In questa attività verranno illustrate le procedure per definire una dimensione basata sui dati di una tabella dei fatti nonché per definire la relazione della dimensione come una relazione di tipo Fatti.</span><span class="sxs-lookup"><span data-stu-id="cec9c-113">In this task, you learn to define a dimension based on data in the fact table, and to define the dimension relationship as a fact relationship.</span></span>  
  
 [<span data-ttu-id="cec9c-114">Definizione di una relazione molti-a-molti</span><span class="sxs-lookup"><span data-stu-id="cec9c-114">Defining a Many-to-Many Relationship</span></span>](lesson-5-3-defining-a-many-to-many-relationship.md)  
 <span data-ttu-id="cec9c-115">In questa attività verranno illustrate le procedure per mettere in relazione un fatto a più membri delle dimensioni tramite una relazione molti-a-molti tra le tabelle delle dimensioni e dei fatti.</span><span class="sxs-lookup"><span data-stu-id="cec9c-115">In this task, you learn to relate a fact to multiple dimension members through the definition of a many-to-many relationship between dimension tables and fact tables.</span></span>  
  
 [<span data-ttu-id="cec9c-116">Definizione della granularità della dimensione in un gruppo di misure</span><span class="sxs-lookup"><span data-stu-id="cec9c-116">Defining Dimension Granularity within a Measure Group</span></span>](lesson-5-4-defining-dimension-granularity-within-a-measure-group.md)  
 <span data-ttu-id="cec9c-117">In questa attività verranno illustrate le procedure per modificare la granularità di una dimensione per un gruppo di misure specifico.</span><span class="sxs-lookup"><span data-stu-id="cec9c-117">In this task, you learn to modify the granularity of a dimension for a specific measure group.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="cec9c-118">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="cec9c-118">Next Lesson</span></span>  
 [<span data-ttu-id="cec9c-119">Lezione 6: Definizione di calcoli</span><span class="sxs-lookup"><span data-stu-id="cec9c-119">Lesson 6: Defining Calculations</span></span>](lesson-6-defining-calculations.md)  
  
## <a name="see-also"></a><span data-ttu-id="cec9c-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cec9c-120">See Also</span></span>  
 <span data-ttu-id="cec9c-121">[Scenario di Analysis Services Tutorial](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="cec9c-121">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="cec9c-122">[Esercitazione di modellazione multidimensionale &#40;Adventure Works&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="cec9c-122">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 [<span data-ttu-id="cec9c-123">Relazioni tra dimensioni</span><span class="sxs-lookup"><span data-stu-id="cec9c-123">Dimension Relationships</span></span>](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md)  
  
  
