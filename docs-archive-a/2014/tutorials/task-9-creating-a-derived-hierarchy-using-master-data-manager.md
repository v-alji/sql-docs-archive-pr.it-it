---
title: 'Attività 9: creazione di una gerarchia derivata utilizzando Gestione dati master | Microsoft Docs'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 3bd2ec05-933f-4947-b1fe-c9226961eb7d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 5c85750e4556722c6e6a5edbccb4a3c82c119a74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726359"
---
# <a name="task-9-creating-a-derived-hierarchy-using-master-data-manager"></a><span data-ttu-id="7d503-102">Attività 9: Creazione di una gerarchia derivata tramite Gestione dati master</span><span class="sxs-lookup"><span data-stu-id="7d503-102">Task 9: Creating a Derived Hierarchy using Master Data Manager</span></span>
  <span data-ttu-id="7d503-103">In questa attività viene creata una gerarchia derivata mediante Gestione dati master.</span><span class="sxs-lookup"><span data-stu-id="7d503-103">In this task, you create a derived hierarchy by using Master Data Manager.</span></span> <span data-ttu-id="7d503-104">Questa gerarchia derivata è derivata dalle relazioni tra attributi basati su dominio tra le entità **Supplier** e **state** .</span><span class="sxs-lookup"><span data-stu-id="7d503-104">This derived hierarchy is derived from the domain-based attribute relationships between the **Supplier** and **State** entities.</span></span>  
  
1.  <span data-ttu-id="7d503-105">Passare alla pagina principale di **Gestione dati master** facendo clic **SQL Server Master Data Services 2012** nella parte superiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="7d503-105">Switch to the main page of **Master Data Manager** by clicking **SQL Server 2012 Master Data Services** at the top of the page.</span></span>  
  
2.  <span data-ttu-id="7d503-106">Fare clic su **Amministrazione sistema** nella sezione **attività amministrative** .</span><span class="sxs-lookup"><span data-stu-id="7d503-106">Click **System Administration** in the **Administrative Tasks** section.</span></span>  
  
3.  <span data-ttu-id="7d503-107">Posizionare il mouse su **Gestisci** sulla barra dei menu e fare clic su **gerarchie derivate**.</span><span class="sxs-lookup"><span data-stu-id="7d503-107">Hover the mouse over **Manage** on the menu bar, and click **Derived Hierarchies**.</span></span>  
  
     <span data-ttu-id="7d503-108">![Menu Gestisci - Gerarchie derivate selezionate](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-01.jpg "Menu Gestisci - Gerarchie derivate selezionate")</span><span class="sxs-lookup"><span data-stu-id="7d503-108">![Manage Menu - Derived Hierarchies Selected](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-01.jpg "Manage Menu - Derived Hierarchies Selected")</span></span>  
  
4.  <span data-ttu-id="7d503-109">Sulla barra degli strumenti fare clic sul pulsante **Aggiungi gerarchia derivata (+)** .</span><span class="sxs-lookup"><span data-stu-id="7d503-109">Click **Add Derived Hierarchy (+)** button on the toolbar.</span></span>  
  
     <span data-ttu-id="7d503-110">![Pulsante Aggiungi gerarchia derivata](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-02.jpg "Pulsante Aggiungi gerarchia derivata")</span><span class="sxs-lookup"><span data-stu-id="7d503-110">![Add Derived Hierarchy Button](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-02.jpg "Add Derived Hierarchy Button")</span></span>  
  
5.  <span data-ttu-id="7d503-111">Digitare **SuppliersInState** per il **nome della gerarchia derivata**.</span><span class="sxs-lookup"><span data-stu-id="7d503-111">Type **SuppliersInState** for the **Derived hierarchy name**.</span></span>  
  
6.  <span data-ttu-id="7d503-112">Fare clic sul pulsante **Salva** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="7d503-112">Click **Save** button on the toolbar.</span></span>  
  
     <span data-ttu-id="7d503-113">![Pulsante Salva gerarchia derivata](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-03.jpg "Pulsante Salva gerarchia derivata")</span><span class="sxs-lookup"><span data-stu-id="7d503-113">![Save Derived Hierarchy Button](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-03.jpg "Save Derived Hierarchy Button")</span></span>  
  
7.  <span data-ttu-id="7d503-114">Trascinare **Supplier** da **livelli disponibili: SuppliersInState** a **livelli correnti: SuppliersInState**.</span><span class="sxs-lookup"><span data-stu-id="7d503-114">Drag **Supplier** from **Available Levels: SuppliersInState** to **Current Levels: SuppliersInState**.</span></span>  
  
     <span data-ttu-id="7d503-115">![Entità e gerarchie disponibili a livello corrente](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-04.jpg "Entità e gerarchie disponibili a livello corrente")</span><span class="sxs-lookup"><span data-stu-id="7d503-115">![Avialble Entities and Hierarchies to Current Level](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-04.jpg "Avialble Entities and Hierarchies to Current Level")</span></span>  
  
8.  <span data-ttu-id="7d503-116">Trascinare **lo stato** da **livelli disponibili: SuppliersInState** a **livelli correnti: SuppliersInState**.</span><span class="sxs-lookup"><span data-stu-id="7d503-116">Drag **State** from **Available Levels: SuppliersInState** to **Current Levels: SuppliersInState**.</span></span> <span data-ttu-id="7d503-117">La schermata deve avere **livelli correnti** , come illustrato nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="7d503-117">The screen should have **Current Levels** as shown in the following picture.</span></span>  
  
     <span data-ttu-id="7d503-118">![Livelli correnti e anteprima della gerarchia derivata](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-05.jpg "Livelli correnti e anteprima della gerarchia derivata")</span><span class="sxs-lookup"><span data-stu-id="7d503-118">![Current Levels and Preview of Derived Hierarchy](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-05.jpg "Current Levels and Preview of Derived Hierarchy")</span></span>  
  
9. <span data-ttu-id="7d503-119">Nella finestra di **Anteprima** , espandere **NY {New York}** . verrà visualizzato un fornitore in tale stato, come illustrato nell'immagine precedente.</span><span class="sxs-lookup"><span data-stu-id="7d503-119">In the **Preview** window, expand **NY { New York}** and you should see one supplier in that state as shown in the preceding image.</span></span>  
  
10. <span data-ttu-id="7d503-120">Passare alla pagina principale di **Gestione dati master** facendo clic **SQL Server Master Data Services 2012** nella parte superiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="7d503-120">Switch to the main page of **Master Data Manager** by clicking **SQL Server 2012 Master Data Services** at the top of the page.</span></span>  
  
11. <span data-ttu-id="7d503-121">Fare clic su **Esplora**.</span><span class="sxs-lookup"><span data-stu-id="7d503-121">Click **Explorer**.</span></span>  
  
12. <span data-ttu-id="7d503-122">Posizionare il puntatore del mouse su **gerarchie** e fare clic su **derivato: SuppliersInState**.</span><span class="sxs-lookup"><span data-stu-id="7d503-122">Hover the mouse over **Hierarchies** and click **Derived:SuppliersInState**.</span></span>  
  
     <span data-ttu-id="7d503-123">![Gerarchie - Menu Derived:SuppliersInState](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-06.jpg "Gerarchie - Menu Derived:SuppliersInState")</span><span class="sxs-lookup"><span data-stu-id="7d503-123">![Hierarchies - Derived:SuppliersInState Menu](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-06.jpg "Hierarchies - Derived:SuppliersInState Menu")</span></span>  
  
13. <span data-ttu-id="7d503-124">Fare clic su un nodo di **stato** nella **visualizzazione albero** per visualizzare i fornitori in tale stato nel riquadro di destra.</span><span class="sxs-lookup"><span data-stu-id="7d503-124">Click on any **state** node in the **tree view** and you should see the suppliers in that state in the right pane.</span></span>  
  
     <span data-ttu-id="7d503-125">![Gerarchia derivata in Esplora](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-07.jpg "Gerarchia derivata in Esplora")</span><span class="sxs-lookup"><span data-stu-id="7d503-125">![Derived Hierarchy in Explorer](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-07.jpg "Derived Hierarchy in Explorer")</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="7d503-126">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="7d503-126">Next Step</span></span>  
 [<span data-ttu-id="7d503-127">Lezione 5: Automazione della pulizia e della corrispondenza tramite SSIS</span><span class="sxs-lookup"><span data-stu-id="7d503-127">Lesson 5: Automating the Cleansing and Matching using SSIS</span></span>](../../2014/tutorials/lesson-5-automating-the-cleansing-and-matching-using-ssis.md)  
  
  
