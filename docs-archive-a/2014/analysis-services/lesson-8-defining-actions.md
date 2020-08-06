---
title: 'Lezione 8: definizione di azioni | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 15459396-83c9-48a0-b10a-99ae38768c79
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4d4daaed3f1992478b309529fc15e2e903a27920
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722007"
---
# <a name="lesson-8-defining-actions"></a><span data-ttu-id="0045e-102">Lezione 8: Definizione di azioni</span><span class="sxs-lookup"><span data-stu-id="0045e-102">Lesson 8: Defining Actions</span></span>
  <span data-ttu-id="0045e-103">In questa lezione verranno descritte le procedure per definire le azioni del progetto di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0045e-103">In this lesson, you will learn to define actions in your [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="0045e-104">Un'azione è semplicemente un'istruzione MDX (Multidimensional Expressions) archiviata in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , che può essere incorporata in applicazioni client e avviata da un utente.</span><span class="sxs-lookup"><span data-stu-id="0045e-104">An action is just a Multidimensional Expressions (MDX) statement that is stored in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and which can be incorporated into client applications and started by a user.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0045e-105">I progetti completati per tutte le lezioni in questa esercitazione sono disponibili online.</span><span class="sxs-lookup"><span data-stu-id="0045e-105">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="0045e-106">È possibile passare a qualsiasi lezione utilizzando il progetto completato della lezione precedente come punto iniziale.</span><span class="sxs-lookup"><span data-stu-id="0045e-106">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="0045e-107">[Fare clic qui](https://go.microsoft.com/fwlink/?LinkID=221866) per scaricare i progetti di esempio usati in questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="0045e-107">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="0045e-108">supporta i tipi di azioni descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="0045e-108">supports the types of actions that are described in the following table.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0045e-109">CommandLine</span><span class="sxs-lookup"><span data-stu-id="0045e-109">CommandLine</span></span>|<span data-ttu-id="0045e-110">Esegue un comando al prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="0045e-110">Executes a command at the command prompt</span></span>|  
|<span data-ttu-id="0045e-111">Set di dati</span><span class="sxs-lookup"><span data-stu-id="0045e-111">Dataset</span></span>|<span data-ttu-id="0045e-112">Restituisce un set di dati a un'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="0045e-112">Returns a dataset to a client application.</span></span>|  
|<span data-ttu-id="0045e-113">Drill-through</span><span class="sxs-lookup"><span data-stu-id="0045e-113">Drillthrough</span></span>|<span data-ttu-id="0045e-114">Restituisce un'istruzione drill-through come un'espressione che viene eseguita dal client per restituire un set di righe</span><span class="sxs-lookup"><span data-stu-id="0045e-114">Returns a drillthrough statement as an expression, which the client executes to return a rowset</span></span>|  
|<span data-ttu-id="0045e-115">Html</span><span class="sxs-lookup"><span data-stu-id="0045e-115">Html</span></span>|<span data-ttu-id="0045e-116">Esegue uno script HTML in un browser Internet</span><span class="sxs-lookup"><span data-stu-id="0045e-116">Executes an HTML script in an Internet browser</span></span>|  
|<span data-ttu-id="0045e-117">Proprietario</span><span class="sxs-lookup"><span data-stu-id="0045e-117">Proprietary</span></span>|<span data-ttu-id="0045e-118">Esegue un'operazione utilizzando un'interfaccia diversa da quelle elencate in questa tabella.</span><span class="sxs-lookup"><span data-stu-id="0045e-118">Performs an operation by using an interface other than those listed in this table.</span></span>|  
|<span data-ttu-id="0045e-119">Report</span><span class="sxs-lookup"><span data-stu-id="0045e-119">Report</span></span>|<span data-ttu-id="0045e-120">Invia una richiesta con parametri basata sull'URL a un server di report e restituisce un report a un'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="0045e-120">Submits a parameterized URL-based request to a report server and returns a report to a client application.</span></span>|  
|<span data-ttu-id="0045e-121">Set di righe</span><span class="sxs-lookup"><span data-stu-id="0045e-121">Rowset</span></span>|<span data-ttu-id="0045e-122">Restituisce un set di righe a un'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="0045e-122">Returns a rowset to a client application.</span></span>|  
|<span data-ttu-id="0045e-123">Istruzione</span><span class="sxs-lookup"><span data-stu-id="0045e-123">Statement</span></span>|<span data-ttu-id="0045e-124">Esegue un comando OLE DB.</span><span class="sxs-lookup"><span data-stu-id="0045e-124">Runs an OLE DB command.</span></span>|  
|<span data-ttu-id="0045e-125">URL</span><span class="sxs-lookup"><span data-stu-id="0045e-125">URL</span></span>|<span data-ttu-id="0045e-126">Visualizza una pagina Web dinamica in un browser Internet</span><span class="sxs-lookup"><span data-stu-id="0045e-126">Displays a dynamic Web page in an Internet browser.</span></span>|  
  
 <span data-ttu-id="0045e-127">Le azioni consentono agli utenti di avviare un'applicazione o di eseguire altre procedure nell'ambito di un elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="0045e-127">Actions let users start an application or perform other steps within the context of a selected item.</span></span> <span data-ttu-id="0045e-128">Per altre informazioni, vedere [Azioni &#40;Analysis Services - Dati multidimensionali&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md), [Azioni nei modelli multidimensionali](multidimensional-models/actions-in-multidimensional-models.md)</span><span class="sxs-lookup"><span data-stu-id="0045e-128">For more information, see [Actions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md), [Actions in Multidimensional Models](multidimensional-models/actions-in-multidimensional-models.md)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0045e-129">Per ulteriori esempi di azioni, vedere quelli disponibili nella scheda Modelli nel riquadro Strumenti di calcolo oppure nel data warehouse di esempio [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW.</span><span class="sxs-lookup"><span data-stu-id="0045e-129">For examples of actions, see the action examples on the Templates tab in the Calculation Tools pane or in the examples in the [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW sample data warehouse.</span></span> <span data-ttu-id="0045e-130">Per altre informazioni sull'installazione di questo database, vedere [Installare dati di esempio e progetti per l'esercitazione di modellazione multidimensionale di Analysis Services](install-sample-data-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="0045e-130">For more information about installing this database, see [Install Sample Data and Projects for the Analysis Services Multidimensional Modeling Tutorial](install-sample-data-and-projects.md).</span></span>  
  
 <span data-ttu-id="0045e-131">Questa lezione include gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0045e-131">This lesson includes the following task:</span></span>  
  
 [<span data-ttu-id="0045e-132">Definizione e utilizzo di un'azione drill-through</span><span class="sxs-lookup"><span data-stu-id="0045e-132">Defining and Using a Drillthrough Action</span></span>](lesson-8-1-defining-and-using-a-drillthrough-action.md)  
 <span data-ttu-id="0045e-133">In questa procedura viene definita, utilizzata e utilizzerà e quindi modificata un'azione drill-through tramite la relazione di tipo Fatti citata precedentemente in questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="0045e-133">In this task, you define, use, and then modify a drillthrough action through the fact dimension relationship that you defined earlier in this tutorial.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="0045e-134">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="0045e-134">Next Lesson</span></span>  
 [<span data-ttu-id="0045e-135">Lezione 9: Definizione di prospettive e traduzioni</span><span class="sxs-lookup"><span data-stu-id="0045e-135">Lesson 9: Defining Perspectives and Translations</span></span>](lesson-9-defining-perspectives-and-translations.md)  
  
## <a name="see-also"></a><span data-ttu-id="0045e-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0045e-136">See Also</span></span>  
 <span data-ttu-id="0045e-137">[Scenario di Analysis Services Tutorial](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="0045e-137">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="0045e-138">[Esercitazione di modellazione multidimensionale &#40;Adventure Works&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="0045e-138">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 <span data-ttu-id="0045e-139">[Azioni &#40;Analysis Services Dati multidimensionali&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="0045e-139">[Actions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="0045e-140">Azioni nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="0045e-140">Actions in Multidimensional Models</span></span>](multidimensional-models/actions-in-multidimensional-models.md)  
  
  
