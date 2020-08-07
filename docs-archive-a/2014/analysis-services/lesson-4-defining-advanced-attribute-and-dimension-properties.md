---
title: 'Lezione 4: definizione di attributi avanzati e proprietà della dimensione | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0e86b9be-e47d-4bb4-87eb-136ff3a61aef
author: minewiskan
ms.author: owend
ms.openlocfilehash: deb2d9c40ad5024f6cc4ba6e9148df41a168c6e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718869"
---
# <a name="lesson-4-defining-advanced-attribute-and-dimension-properties"></a><span data-ttu-id="0ba02-102">Lezione 4: Definizione delle proprietà avanzate di attributi e dimensioni</span><span class="sxs-lookup"><span data-stu-id="0ba02-102">Lesson 4: Defining Advanced Attribute and Dimension Properties</span></span>
  <span data-ttu-id="0ba02-103">In questa lezione verranno illustrate le procedure per l'utilizzo di alcune proprietà avanzate degli attributi, delle gerarchie degli attribuiti e delle proprietà delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="0ba02-103">In this lesson, you will learn how to use some of the advanced properties of attributes, attribute hierarchies, and dimension properties.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ba02-104">Questa lezione è basata su una versione migliorata del progetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial completato nelle prime tre lezioni di questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="0ba02-104">This lesson is based on an enhanced version of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project that you completed in the first three lessons of this tutorial.</span></span> <span data-ttu-id="0ba02-105">Nella prima attività di questa lezione viene descritto dove individuare il progetto di esempio appropriato da utilizzare per questa lezione e vengono illustrate le differenze tra questo progetto e il progetto creato nelle prime tre lezioni.</span><span class="sxs-lookup"><span data-stu-id="0ba02-105">The first task in this lesson describes where to locate the appropriate sample project to use for the lesson, and the difference between this project and the project that you created in the first three lessons.</span></span>  
  
 <span data-ttu-id="0ba02-106">In questa lezione sono incluse le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="0ba02-106">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="0ba02-107">Utilizzo di una versione modificata del progetto Analysis Services Tutorial</span><span class="sxs-lookup"><span data-stu-id="0ba02-107">Using a Modified Version of the Analysis Services Tutorial Project</span></span>](lesson-4-1-using-a-modified-version-of-the-analysis-services-tutorial-project.md)  
 <span data-ttu-id="0ba02-108">In questa attività vengono illustrate le procedure per aprire, controllare e distribuire una versione modificata del progetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial, con più gruppi di misure e dimensioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="0ba02-108">In this task, you open, review, and deploy a modified version of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, which has multiple measure groups and additional dimensions.</span></span>  
  
 [<span data-ttu-id="0ba02-109">Definizione delle proprietà degli attributi padre in una gerarchia padre-figlio</span><span class="sxs-lookup"><span data-stu-id="0ba02-109">Defining Parent Attribute Properties in a Parent-Child Hierarchy</span></span>](lesson-4-2-defining-parent-attribute-properties-in-a-parent-child-hierarchy.md)  
 <span data-ttu-id="0ba02-110">In questa attività vengono illustrate le procedure per definire i nomi dei livelli in una dimensione padre-figlio e per specificare se i dati correlati ai membri padre vengono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="0ba02-110">In this task, you define level names in a parent-child dimension and specify whether data related to parent members is displayed.</span></span> <span data-ttu-id="0ba02-111">Per ulteriori informazioni, vedere [gerarchia padre-figlio](multidimensional-models/parent-child-dimension.md) e [attributi nelle gerarchie padre-figlio](multidimensional-models/parent-child-dimension-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="0ba02-111">For more information, see [Parent-Child Hierarchy](multidimensional-models/parent-child-dimension.md) and [Attributes in Parent-Child Hierarchies](multidimensional-models/parent-child-dimension-attributes.md).</span></span>  
  
 [<span data-ttu-id="0ba02-112">Raggruppamento automatico dei membri degli attributi</span><span class="sxs-lookup"><span data-stu-id="0ba02-112">Automatically Grouping Attribute Members</span></span>](lesson-4-3-automatically-grouping-attribute-members.md)  
 <span data-ttu-id="0ba02-113">In questa attività vengono illustrate le procedure per creare automaticamente gruppi di membri dell'attributo in base alla distribuzione dei membri all'interno della gerarchia dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="0ba02-113">In this task, you automatically create groupings of attribute members based on the distribution of the members within the attribute hierarchy.</span></span> <span data-ttu-id="0ba02-114">Per altre informazioni, vedere [Raggruppare membri di attributo &#40;discretizzazione&#41;](multidimensional-models/attribute-properties-group-attribute-members.md).</span><span class="sxs-lookup"><span data-stu-id="0ba02-114">For more information, see [Group Attribute Members &#40;Discretization&#41;](multidimensional-models/attribute-properties-group-attribute-members.md).</span></span>  
  
 [<span data-ttu-id="0ba02-115">Come nascondere e disabilitare le gerarchie degli attributi</span><span class="sxs-lookup"><span data-stu-id="0ba02-115">Hiding and Disabling Attribute Hierarchies</span></span>](lesson-4-4-hiding-and-disabling-attribute-hierarchies.md)  
 <span data-ttu-id="0ba02-116">In questa attività vengono illustrate le procedure per disabilitare o nascondere le gerarchie degli attributi.</span><span class="sxs-lookup"><span data-stu-id="0ba02-116">In this task, you learn how and when to disable or hide attribute hierarchies.</span></span>  
  
 [<span data-ttu-id="0ba02-117">Ordinamento dei membri dell'attributo in base a un attributo secondario</span><span class="sxs-lookup"><span data-stu-id="0ba02-117">Sorting Attribute Members Based on a Secondary Attribute</span></span>](lesson-4-5-sorting-attribute-members-based-on-a-secondary-attribute.md)  
 <span data-ttu-id="0ba02-118">In questa attività vengono illustrate le procedure per ordinare i membri della dimensione in base a un attributo secondario in modo da ottenere il tipo di ordinamento desiderato.</span><span class="sxs-lookup"><span data-stu-id="0ba02-118">In this task, you learn how to sort dimension members based on a secondary attribute, to achieve the sort order that you want.</span></span>  
  
 [<span data-ttu-id="0ba02-119">Impostazione delle relazioni tra gli attributi in una gerarchia definita dall'utente</span><span class="sxs-lookup"><span data-stu-id="0ba02-119">Specifying Attribute Relationships Between Attributes in a User-Defined Hierarchy</span></span>](4-6-specifying-attribute-relationships-in-user-defined-hierarchy.md)  
 <span data-ttu-id="0ba02-120">In questa attività vengono illustrate le procedure per definire le proprietà del membro per gli attributi e per specificarne le relazioni di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="0ba02-120">In this task, you learn how to define member properties for attributes and to specify aggregation relationships between them.</span></span> <span data-ttu-id="0ba02-121">Per altre informazioni, vedere [Definire relazioni tra attributi](multidimensional-models/attribute-relationships-define.md) e [Proprietà delle gerarchie definite dall'utente](multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md).</span><span class="sxs-lookup"><span data-stu-id="0ba02-121">For more information, see [Define Attribute Relationships](multidimensional-models/attribute-relationships-define.md) and [User Hierarchy Properties](multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md).</span></span>  
  
 [<span data-ttu-id="0ba02-122">Definizione delle proprietà UnknownMember e NullProcessing</span><span class="sxs-lookup"><span data-stu-id="0ba02-122">Defining the Unknown Member and Null Processing Properties</span></span>](lesson-4-7-defining-the-unknown-member-and-null-processing-properties.md)  
 <span data-ttu-id="0ba02-123">In questa attività vengono configurate le proprietà UnknownMember e UnknownMemberName per gestire le condizioni di errore determinate dai membri Null della dimensione.</span><span class="sxs-lookup"><span data-stu-id="0ba02-123">In this task, you configure the UnknownMember and UnknownMemberName properties to handle error conditions caused by null dimension members.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="0ba02-124">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="0ba02-124">Next Lesson</span></span>  
 [<span data-ttu-id="0ba02-125">Lezione 5: Definizione delle relazioni tra dimensioni e gruppi di misure</span><span class="sxs-lookup"><span data-stu-id="0ba02-125">Lesson 5: Defining Relationships Between Dimensions and Measure Groups</span></span>](lesson-5-defining-relationships-between-dimensions-and-measure-groups.md)  
  
## <a name="see-also"></a><span data-ttu-id="0ba02-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ba02-126">See Also</span></span>  
 <span data-ttu-id="0ba02-127">[Scenario di Analysis Services Tutorial](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="0ba02-127">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="0ba02-128">[Esercitazione di modellazione multidimensionale &#40;Adventure Works&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="0ba02-128">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 [<span data-ttu-id="0ba02-129">Dimensioni nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="0ba02-129">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
