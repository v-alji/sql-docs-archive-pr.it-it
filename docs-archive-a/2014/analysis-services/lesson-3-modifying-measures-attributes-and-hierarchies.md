---
title: 'Lezione 3: modifica di misure, attributi e gerarchie | Microsoft Docs'
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 17d243cb-9bfb-43d7-8e6f-4d601fd62150
author: minewiskan
ms.author: owend
ms.openlocfilehash: c410136540a0ba85d50fbabc8b2d3c52be1823f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630133"
---
# <a name="lesson-3-modifying-measures-attributes-and-hierarchies"></a><span data-ttu-id="5b768-102">Lezione 3: Modifica di misure, attributi e gerarchie</span><span class="sxs-lookup"><span data-stu-id="5b768-102">Lesson 3: Modifying Measures, Attributes and Hierarchies</span></span>
  <span data-ttu-id="5b768-103">Dopo aver definito il cubo iniziale, è possibile rendere il cubo maggiormente utile e semplice.</span><span class="sxs-lookup"><span data-stu-id="5b768-103">After defining your initial cube, you are ready to improve the usefulness and friendliness of the cube.</span></span> <span data-ttu-id="5b768-104">A tale scopo, aggiungere le gerarchie che supportano la navigazione e l'aggregazione a vari livelli, applicare formati a una misura specifica e definire calcoli e relazioni.</span><span class="sxs-lookup"><span data-stu-id="5b768-104">You can do this by adding hierarchies that support navigation and aggregation at various levels, by applying formats to specific measure, and by defining calculations and relationships.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5b768-105">I progetti completati per tutte le lezioni in questa esercitazione sono disponibili online.</span><span class="sxs-lookup"><span data-stu-id="5b768-105">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="5b768-106">È possibile passare a qualsiasi lezione utilizzando il progetto completato della lezione precedente come punto iniziale.</span><span class="sxs-lookup"><span data-stu-id="5b768-106">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="5b768-107">[Fare clic qui](https://go.microsoft.com/fwlink/?LinkID=221866) per scaricare i progetti di esempio usati in questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="5b768-107">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 <span data-ttu-id="5b768-108">In questa lezione sono incluse le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="5b768-108">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="5b768-109">Modifica delle misure</span><span class="sxs-lookup"><span data-stu-id="5b768-109">Modifying Measures</span></span>](lesson-3-1-modifying-measures.md)  
 <span data-ttu-id="5b768-110">In questa attività vengono impostate le proprietà di formattazione per le misure di valuta e di percentuale nel cubo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial.</span><span class="sxs-lookup"><span data-stu-id="5b768-110">In this task, you specify formatting properties for the currency and percentage measures in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>  
  
 [<span data-ttu-id="5b768-111">Modifica della dimensione Customer</span><span class="sxs-lookup"><span data-stu-id="5b768-111">Modifying the Customer Dimension</span></span>](lesson-3-2-modifying-the-customer-dimension.md)  
 <span data-ttu-id="5b768-112">In questa attività verranno illustrate le procedure per definire le gerarchie utente, creare calcoli denominati, modificare gli attributi in modo che vengano utilizzati calcoli denominati e raggruppare gli attributi e le gerarchie utente in cartelle di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="5b768-112">In this task, you define a user hierarchy, create named calculations, modify attributes to use named calculations, and group attributes and user hierarchies into display folders.</span></span>  
  
 [<span data-ttu-id="5b768-113">Modifica della dimensione Product</span><span class="sxs-lookup"><span data-stu-id="5b768-113">Modifying the Product Dimension</span></span>](lesson-3-3-modifying-the-product-dimension.md)  
 <span data-ttu-id="5b768-114">In questa attività verranno illustrate le procedure per definire una gerarchia utente e il nome del membro Totale, creare calcoli denominati e specificare le cartelle di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="5b768-114">In this task, you define a user hierarchy, create named calculations, define the All member name, and define display folders.</span></span>  
  
 [<span data-ttu-id="5b768-115">Modifica della dimensione Date</span><span class="sxs-lookup"><span data-stu-id="5b768-115">Modifying the Date Dimension</span></span>](lesson-3-4-modifying-the-date-dimension.md)  
 <span data-ttu-id="5b768-116">In questa attività verranno illustrate le procedure per definire una gerarchia utente, modificare i nomi dei membri degli attributi e utilizzare chiavi composte per specificare membri degli attributi univoci.</span><span class="sxs-lookup"><span data-stu-id="5b768-116">In this task, you define a user hierarchy, modify attribute member names, and use composite keys to specify unique attribute members.</span></span>  
  
 [<span data-ttu-id="5b768-117">Esplorazione di un cubo distribuito</span><span class="sxs-lookup"><span data-stu-id="5b768-117">Browsing the Deployed Cube</span></span>](lesson-3-5-browsing-the-deployed-cube.md)  
 <span data-ttu-id="5b768-118">In questa attività verranno illustrate le procedure per esplorare i dati dei cubi tramite l'apposita finestra in Progettazione cubi.</span><span class="sxs-lookup"><span data-stu-id="5b768-118">In this task, you browse cube data by using the browser in Cube Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b768-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b768-119">See Also</span></span>  
 <span data-ttu-id="5b768-120">[Scenario di Analysis Services Tutorial](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="5b768-120">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 [<span data-ttu-id="5b768-121">Modellazione multidimensionale &#40;esercitazione di AdventureWorks&#41;</span><span class="sxs-lookup"><span data-stu-id="5b768-121">Multidimensional Modeling &#40;Adventure Works Tutorial&#41;</span></span>](multidimensional-modeling-adventure-works-tutorial.md)  
  
  
