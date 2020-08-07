---
title: Definizione ed esplorazione delle prospettive | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 766004b9-6578-4914-a445-6f44843a5fb0
author: minewiskan
ms.author: owend
ms.openlocfilehash: c9658098180618c2d5d6d6d9e00e7a7e4a6c4231
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718858"
---
# <a name="defining-and-browsing-perspectives"></a><span data-ttu-id="c5d45-102">Definizione ed esplorazione delle prospettive</span><span class="sxs-lookup"><span data-stu-id="c5d45-102">Defining and Browsing Perspectives</span></span>
  <span data-ttu-id="c5d45-103">Una prospettiva può semplificare la visualizzazione di un cubo a scopi specifici.</span><span class="sxs-lookup"><span data-stu-id="c5d45-103">A perspective can simplify the view of a cube for specific purposes.</span></span> <span data-ttu-id="c5d45-104">Per impostazione predefinita, gli utenti possono vedere tutti gli elementi di un cubo per i quali dispongono di autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="c5d45-104">By default, users can see all of the elements in a cube to which they have permissions.</span></span> <span data-ttu-id="c5d45-105">Quando si visualizza un intero cubo di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , viene visualizzata la prospettiva predefinita del cubo.</span><span class="sxs-lookup"><span data-stu-id="c5d45-105">What users are viewing when they view an entire [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube is the default perspective for the cube.</span></span> <span data-ttu-id="c5d45-106">La navigazione all'interno di una visualizzazione dell'intero cubo può essere molto complessa per gli utenti, soprattutto per coloro che devono solo interagire con una piccola parte del cubo per soddisfare i requisiti di Business Intelligence e di report.</span><span class="sxs-lookup"><span data-stu-id="c5d45-106">A view of the whole cube can be very complex for users to navigate, especially for users who only need to interact with a small part of the cube to satisfy their business intelligence and reporting requirements.</span></span>  
  
 <span data-ttu-id="c5d45-107">Per ridurre la complessità apparente di un cubo è possibile creare subset visualizzabili del cubo, denominati *prospettive*, che visualizzano agli utenti solo una parte dei gruppi di misure, delle misure, delle dimensioni, degli attributi, delle gerarchie, degli indicatori di prestazioni chiave (KPI), delle azioni e dei membri calcolati del cubo.</span><span class="sxs-lookup"><span data-stu-id="c5d45-107">To reduce the apparent complexity of a cube, you can create viewable subsets of the cube, called *perspectives*, which show users only a part of the measure groups, measures, dimensions, attributes, hierarchies, Key Performance Indicators (KPIs), actions, and calculated members in the cube.</span></span> <span data-ttu-id="c5d45-108">Ciò può risultare particolarmente utile per utilizzare applicazioni client scritte per una versione precedente di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5d45-108">This can be particularly useful for working with client applications that were written for a previous release of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="c5d45-109">Tali applicazioni non supportano cartelle di visualizzazione o prospettive, tuttavia una prospettiva è ad esempio presente nei client precedenti sotto forma di cubo.</span><span class="sxs-lookup"><span data-stu-id="c5d45-109">These clients have no concept of display folders or perspectives, for example, but a perspective appears to older clients as if it were a cube.</span></span> <span data-ttu-id="c5d45-110">Per altre informazioni, vedere [Prospettive](multidimensional-models-olap-logical-cube-objects/perspectives.md)e [Prospettive nei modelli multidimensionali](multidimensional-models/perspectives-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="c5d45-110">For more information, see [Perspectives](multidimensional-models-olap-logical-cube-objects/perspectives.md), and [Perspectives in Multidimensional Models](multidimensional-models/perspectives-in-multidimensional-models.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c5d45-111">Una prospettiva non è un meccanismo di sicurezza, ma uno strumento per semplificare il lavoro all'utente.</span><span class="sxs-lookup"><span data-stu-id="c5d45-111">A perspective is not a security mechanism, but instead is a tool for providing a better user experience.</span></span> <span data-ttu-id="c5d45-112">Tutta la sicurezza di una prospettiva viene ereditata dal cubo sottostante.</span><span class="sxs-lookup"><span data-stu-id="c5d45-112">All security for a perspective is inherited from the underlying cube.</span></span>  
  
 <span data-ttu-id="c5d45-113">Nelle procedure descritte in questo argomento vengono definite diverse prospettive e successivamente il cubo verrà esplorato tramite ognuna di tali prospettive.</span><span class="sxs-lookup"><span data-stu-id="c5d45-113">In the tasks in this topic, you will define several different perspectives and then browse the cube through each of these new perspectives.</span></span>  
  
## <a name="defining-an-internet-sales-perspective"></a><span data-ttu-id="c5d45-114">Definizione di una prospettiva Internet Sales</span><span class="sxs-lookup"><span data-stu-id="c5d45-114">Defining an Internet Sales Perspective</span></span>  
  
1.  <span data-ttu-id="c5d45-115">Aprire Progettazione cubi per il cubo di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial, quindi fare clic sulla scheda **Prospettive** .</span><span class="sxs-lookup"><span data-stu-id="c5d45-115">Open Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **Perspectives** tab.</span></span>  
  
     <span data-ttu-id="c5d45-116">Tutti gli oggetti e i relativi tipi verranno visualizzati nel riquadro **Prospettive** , come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="c5d45-116">All the objects and their object types appear in the **Perspectives** pane, as shown in the following image.</span></span>  
  
     <span data-ttu-id="c5d45-117">![Riquadro Prospettive di Progettazione cubi](../../2014/tutorials/media/l9-perspectives-1.gif "Riquadro Prospettive di Progettazione cubi")</span><span class="sxs-lookup"><span data-stu-id="c5d45-117">![Perspectives pane of Cube Designer](../../2014/tutorials/media/l9-perspectives-1.gif "Perspectives pane of Cube Designer")</span></span>  
  
2.  <span data-ttu-id="c5d45-118">Fare clic sul pulsante **Nuova prospettiva** sulla barra degli strumenti della scheda **Prospettive** .</span><span class="sxs-lookup"><span data-stu-id="c5d45-118">On the toolbar of the **Perspectives** tab, click the **New Perspective** button.</span></span>  
  
     <span data-ttu-id="c5d45-119">Verrà visualizzata una nuova prospettiva nella colonna **Nome prospettiva** , con il nome predefinito **Prospettiva**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="c5d45-119">A new perspective appears in the **Perspective Name** column with a default name of **Perspective**, as shown in the following image.</span></span> <span data-ttu-id="c5d45-120">Si noti che è selezionata la casella di controllo corrispondente a ogni oggetto. Finché non si deseleziona la casella di controllo di un oggetto, questa prospettiva è identica alla prospettiva predefinita del cubo.</span><span class="sxs-lookup"><span data-stu-id="c5d45-120">Notice that the check box for every object is selected; until you clear the check box for an object, this perspective is identical to the default perspective of this cube.</span></span>  
  
     <span data-ttu-id="c5d45-121">![Nuova prospettiva nella colonna Nome prospettiva](../../2014/tutorials/media/l9-perspectives-2.gif "Nuova prospettiva nella colonna Nome prospettiva")</span><span class="sxs-lookup"><span data-stu-id="c5d45-121">![New perspective in Perspective Name column](../../2014/tutorials/media/l9-perspectives-2.gif "New perspective in Perspective Name column")</span></span>  
  
3.  <span data-ttu-id="c5d45-122">Modificare il nome della prospettiva in `Internet Sales` .</span><span class="sxs-lookup"><span data-stu-id="c5d45-122">Change the perspective name to `Internet Sales`.</span></span>  
  
4.  <span data-ttu-id="c5d45-123">Nella riga successiva impostare DefaultMeasure su **Internet Sales-Sales Amount**.</span><span class="sxs-lookup"><span data-stu-id="c5d45-123">On the next row, set the DefaultMeasure to **Internet Sales-Sales Amount**.</span></span>  
  
     <span data-ttu-id="c5d45-124">Quando gli utenti esplorano il cubo utilizzando questa prospettiva, questa sarà la misura che visualizzeranno gli utenti, a meno che non ne venga specificata una diversa.</span><span class="sxs-lookup"><span data-stu-id="c5d45-124">When users browse the cube by using this perspective, this will be the measure that the users see unless they specify some other measure.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c5d45-125">È inoltre possibile impostare la misura predefinita per tutto il cubo di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial nella finestra Proprietà della scheda **Struttura cubo** per il cubo.</span><span class="sxs-lookup"><span data-stu-id="c5d45-125">You can also set the default measure for the whole [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube in the Properties window on the **Cube Structure** tab for the cube.</span></span>  
  
5.  <span data-ttu-id="c5d45-126">Deselezionare le caselle di controllo corrispondenti agli oggetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5d45-126">Clear the check box for the following objects:</span></span>  
  
    -   <span data-ttu-id="c5d45-127">`Reseller Sales`gruppo di misure</span><span class="sxs-lookup"><span data-stu-id="c5d45-127">`Reseller Sales` measure group</span></span>  
  
    -   <span data-ttu-id="c5d45-128">Gruppo di misure**Sales Quotas**</span><span class="sxs-lookup"><span data-stu-id="c5d45-128">**Sales Quotas** measure group</span></span>  
  
    -   <span data-ttu-id="c5d45-129">Gruppo di misure**Sales Quotas 1**</span><span class="sxs-lookup"><span data-stu-id="c5d45-129">**Sales Quotas 1** measure group</span></span>  
  
    -   <span data-ttu-id="c5d45-130">Dimensione del cubo**Reseller**</span><span class="sxs-lookup"><span data-stu-id="c5d45-130">**Reseller** cube dimension</span></span>  
  
    -   <span data-ttu-id="c5d45-131">Dimensione del cubo**Reseller Geography**</span><span class="sxs-lookup"><span data-stu-id="c5d45-131">**Reseller Geography** cube dimension</span></span>  
  
    -   <span data-ttu-id="c5d45-132">Dimensione del cubo**Sales Territory**</span><span class="sxs-lookup"><span data-stu-id="c5d45-132">**Sales Territory** cube dimension</span></span>  
  
    -   <span data-ttu-id="c5d45-133">Dimensione del cubo**Employee**</span><span class="sxs-lookup"><span data-stu-id="c5d45-133">**Employee** cube dimension</span></span>  
  
    -   <span data-ttu-id="c5d45-134">Dimensione del cubo**Promotion**</span><span class="sxs-lookup"><span data-stu-id="c5d45-134">**Promotion** cube dimension</span></span>  
  
    -   <span data-ttu-id="c5d45-135"> di**Reseller Revenue**</span><span class="sxs-lookup"><span data-stu-id="c5d45-135">**Reseller Revenue** KPI</span></span>  
  
    -   <span data-ttu-id="c5d45-136">Set denominato**Large Resellers**</span><span class="sxs-lookup"><span data-stu-id="c5d45-136">**Large Resellers** named set</span></span>  
  
    -   <span data-ttu-id="c5d45-137">Membro calcolato**Total Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="c5d45-137">**Total Sales Amount** calculated member</span></span>  
  
    -   <span data-ttu-id="c5d45-138">Membro calcolato**Total Product Cost**</span><span class="sxs-lookup"><span data-stu-id="c5d45-138">**Total Product Cost** calculated member</span></span>  
  
    -   <span data-ttu-id="c5d45-139">Membro calcolato**Reseller GPM**</span><span class="sxs-lookup"><span data-stu-id="c5d45-139">**Reseller GPM** calculated member</span></span>  
  
    -   <span data-ttu-id="c5d45-140">Membro calcolato**Total GPM**</span><span class="sxs-lookup"><span data-stu-id="c5d45-140">**Total GPM** calculated member</span></span>  
  
    -   <span data-ttu-id="c5d45-141">Membro calcolato**Reseller Sales Ratio to All Products**</span><span class="sxs-lookup"><span data-stu-id="c5d45-141">**Reseller Sales Ratio to All Products** calculated member</span></span>  
  
    -   <span data-ttu-id="c5d45-142">Membro calcolato**Total Sales Ratio to All Products**</span><span class="sxs-lookup"><span data-stu-id="c5d45-142">**Total Sales Ratio to All Products** calculated member</span></span>  
  
     <span data-ttu-id="c5d45-143">Questi oggetti non riguardano le vendite Internet.</span><span class="sxs-lookup"><span data-stu-id="c5d45-143">These objects do not relate to Internet sales.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c5d45-144">All'interno di ogni dimensione è inoltre possibile selezionare i singoli attributi e le singole gerarchie definite dall'utente che si desidera visualizzare in una prospettiva.</span><span class="sxs-lookup"><span data-stu-id="c5d45-144">Within each dimension, you can also individually select the user-defined hierarchies and attributes that you want to appear in a perspective.</span></span>  
  
## <a name="defining-a-reseller-sales-perspective"></a><span data-ttu-id="c5d45-145">Definizione di una prospettiva Reseller Sales</span><span class="sxs-lookup"><span data-stu-id="c5d45-145">Defining a Reseller Sales Perspective</span></span>  
  
1.  <span data-ttu-id="c5d45-146">Fare clic sul pulsante **Nuova prospettiva** sulla barra degli strumenti della scheda **Prospettive** .</span><span class="sxs-lookup"><span data-stu-id="c5d45-146">On the toolbar of the **Perspectives** tab, click the **New Perspective** button.</span></span>  
  
2.  <span data-ttu-id="c5d45-147">Modificare il nome della nuova prospettiva in `Reseller Sales` .</span><span class="sxs-lookup"><span data-stu-id="c5d45-147">Change the name of the new perspective to `Reseller Sales`.</span></span>  
  
3.  <span data-ttu-id="c5d45-148">Impostare **Reseller Sales-Sales Amount** come misura predefinita.</span><span class="sxs-lookup"><span data-stu-id="c5d45-148">Set **Reseller Sales-Sales Amount** as the default measure.</span></span>  
  
     <span data-ttu-id="c5d45-149">Quando gli utenti esplorano il cubo utilizzando questa prospettiva, questa misura sarà la misura visualizzata agli utenti, a meno che non ne venga specificata una diversa.</span><span class="sxs-lookup"><span data-stu-id="c5d45-149">When users browse the cube by using this perspective, this measure will be the measure that the users will see unless they specify some other measure.</span></span>  
  
4.  <span data-ttu-id="c5d45-150">Deselezionare le caselle di controllo corrispondenti agli oggetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5d45-150">Clear the check box for the following objects:</span></span>  
  
    -   <span data-ttu-id="c5d45-151">`Internet Sales`gruppo di misure</span><span class="sxs-lookup"><span data-stu-id="c5d45-151">`Internet Sales` measure group</span></span>  
  
    -   <span data-ttu-id="c5d45-152">Gruppo di misure**Internet Sales Reason**</span><span class="sxs-lookup"><span data-stu-id="c5d45-152">**Internet Sales Reason** measure group</span></span>  
  
    -   <span data-ttu-id="c5d45-153">Dimensione del cubo**Customer**</span><span class="sxs-lookup"><span data-stu-id="c5d45-153">**Customer** cube dimension</span></span>  
  
    -   <span data-ttu-id="c5d45-154">Dimensione del cubo**Internet Sales Order Details**</span><span class="sxs-lookup"><span data-stu-id="c5d45-154">**Internet Sales Order Details** cube dimension</span></span>  
  
    -   <span data-ttu-id="c5d45-155">Dimensione del cubo**Sales Reason**</span><span class="sxs-lookup"><span data-stu-id="c5d45-155">**Sales Reason** cube dimension</span></span>  
  
    -   <span data-ttu-id="c5d45-156">Azione drill-through**Internet Sales Details Drillthrough Action**</span><span class="sxs-lookup"><span data-stu-id="c5d45-156">**Internet Sales Details Drillthrough Action** drillthrough action</span></span>  
  
    -   <span data-ttu-id="c5d45-157">Membro calcolato**Total Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="c5d45-157">**Total Sales Amount** calculated member</span></span>  
  
    -   <span data-ttu-id="c5d45-158">Membro calcolato**Total Product Cost**</span><span class="sxs-lookup"><span data-stu-id="c5d45-158">**Total Product Cost** calculated member</span></span>  
  
    -   <span data-ttu-id="c5d45-159">Membro calcolato**Internet GPM**</span><span class="sxs-lookup"><span data-stu-id="c5d45-159">**Internet GPM** calculated member</span></span>  
  
    -   <span data-ttu-id="c5d45-160">Membro calcolato**Total GPM**</span><span class="sxs-lookup"><span data-stu-id="c5d45-160">**Total GPM** calculated member</span></span>  
  
    -   <span data-ttu-id="c5d45-161">Membro calcolato**Internet Sales Ratio to All Products**</span><span class="sxs-lookup"><span data-stu-id="c5d45-161">**Internet Sales Ratio to All Products** calculated member</span></span>  
  
    -   <span data-ttu-id="c5d45-162">Membro calcolato**Total Sales Ratio to All Products**</span><span class="sxs-lookup"><span data-stu-id="c5d45-162">**Total Sales Ratio to All Products** calculated member</span></span>  
  
     <span data-ttu-id="c5d45-163">Questi oggetti non riguardano le vendite rivenditore.</span><span class="sxs-lookup"><span data-stu-id="c5d45-163">These objects do not relate to resellers sales.</span></span>  
  
## <a name="defining-a-sales-summary-perspective"></a><span data-ttu-id="c5d45-164">Definizione di una prospettiva Sales Summary</span><span class="sxs-lookup"><span data-stu-id="c5d45-164">Defining a Sales Summary Perspective</span></span>  
  
1.  <span data-ttu-id="c5d45-165">Fare clic sul pulsante **Nuova prospettiva** sulla barra degli strumenti della scheda **Prospettive** .</span><span class="sxs-lookup"><span data-stu-id="c5d45-165">On the toolbar of the **Perspectives** tab, click the **New Perspective** button.</span></span>  
  
2.  <span data-ttu-id="c5d45-166">Modificare il nome della nuova prospettiva in `Sales Summary` .</span><span class="sxs-lookup"><span data-stu-id="c5d45-166">Change the name of the new perspective to `Sales Summary`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c5d45-167">Non è possibile specificare una misura calcolata come misura predefinita.</span><span class="sxs-lookup"><span data-stu-id="c5d45-167">You cannot specify a calculated measure as the default measure.</span></span>  
  
3.  <span data-ttu-id="c5d45-168">Deselezionare le caselle di controllo corrispondenti agli oggetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5d45-168">Clear the check box for the following objects:</span></span>  
  
    -   <span data-ttu-id="c5d45-169">`Internet Sales`gruppo di misure</span><span class="sxs-lookup"><span data-stu-id="c5d45-169">`Internet Sales` measure group</span></span>  
  
    -   <span data-ttu-id="c5d45-170">`Reseller Sales`gruppo di misure</span><span class="sxs-lookup"><span data-stu-id="c5d45-170">`Reseller Sales` measure group</span></span>  
  
    -   <span data-ttu-id="c5d45-171">Gruppo di misure**Internet Sales Reason**</span><span class="sxs-lookup"><span data-stu-id="c5d45-171">**Internet Sales Reason** measure group</span></span>  
  
    -   <span data-ttu-id="c5d45-172">Gruppo di misure**Sales Quotas**</span><span class="sxs-lookup"><span data-stu-id="c5d45-172">**Sales Quotas** measure group</span></span>  
  
    -   <span data-ttu-id="c5d45-173">Gruppo di misure**Sales Quotas1**</span><span class="sxs-lookup"><span data-stu-id="c5d45-173">**Sales Quotas1** measure group</span></span>  
  
    -   <span data-ttu-id="c5d45-174">Dimensione del cubo**Internet Sales Order Details**</span><span class="sxs-lookup"><span data-stu-id="c5d45-174">**Internet Sales Order Details** cube dimension</span></span>  
  
    -   <span data-ttu-id="c5d45-175">Dimensione del cubo**Sales Reason**</span><span class="sxs-lookup"><span data-stu-id="c5d45-175">**Sales Reason** cube dimension</span></span>  
  
    -   <span data-ttu-id="c5d45-176">Azione drill-through**Internet Sales Details Drillthrough Action**</span><span class="sxs-lookup"><span data-stu-id="c5d45-176">**Internet Sales Details Drillthrough Action** drillthrough action</span></span>  
  
4.  <span data-ttu-id="c5d45-177">Selezionare le caselle di controllo corrispondenti agli oggetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5d45-177">Select the check box for the following objects:</span></span>  
  
    -   <span data-ttu-id="c5d45-178">Misura**Internet Sales Count**</span><span class="sxs-lookup"><span data-stu-id="c5d45-178">**Internet Sales Count** measure</span></span>  
  
    -   <span data-ttu-id="c5d45-179">Misura**Reseller Sales Count**</span><span class="sxs-lookup"><span data-stu-id="c5d45-179">**Reseller Sales Count** measure</span></span>  
  
## <a name="browsing-the-cube-through-each-perspective"></a><span data-ttu-id="c5d45-180">Esplorazione del cubo tramite ogni prospettiva</span><span class="sxs-lookup"><span data-stu-id="c5d45-180">Browsing the Cube Through Each Perspective</span></span>  
  
1.  <span data-ttu-id="c5d45-181">Scegliere **Distribuisci Analysis Services Tutorial** dal menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="c5d45-181">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="c5d45-182">Dopo aver completato la distribuzione, passare alla scheda **Esplorazione** , quindi fare clic sul pulsante **Riconnetti** .</span><span class="sxs-lookup"><span data-stu-id="c5d45-182">When deployment has successfully completed, switch to the **Browser** tab, and then click the **Reconnect** button.</span></span>  
  
3.  <span data-ttu-id="c5d45-183">Avviare Excel.</span><span class="sxs-lookup"><span data-stu-id="c5d45-183">Start Excel.</span></span>  
  
4.  <span data-ttu-id="c5d45-184">Analizza in Excel richiede di scegliere quale prospettiva utilizzare per la visualizzazione del modello in Excel, come illustrato nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="c5d45-184">Analyze in Excel prompts you to choose which perspective to use when browsing the model in Excel, as shown in the following image.</span></span>  
  
     <span data-ttu-id="c5d45-185">![Oggetti per la prospettiva Internet Sales](../../2014/tutorials/media/l9-perspectives-3.gif "Oggetti per la prospettiva Internet Sales")</span><span class="sxs-lookup"><span data-stu-id="c5d45-185">![Objects for the Internet Sales perspective](../../2014/tutorials/media/l9-perspectives-3.gif "Objects for the Internet Sales perspective")</span></span>  
  
5.  <span data-ttu-id="c5d45-186">In alternativa, è possibile avviare Excel dal menu Start di Windows, definire una connessione al database Analysis Services Tutorial su localhost e scegliere una prospettiva nella procedura guidata Connessione dati, come illustrato nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="c5d45-186">Alternatively, you can start Excel from the Windows Start menu, define a connection to the Analysis Services Tutorial database on localhost, and choose a perspective in the Data Connection wizard, as shown in the following image.</span></span>  
  
     <span data-ttu-id="c5d45-187">![Connessione dati guidata in Excel](../../2014/tutorials/media/l9-perspectives-3b.gif "Connessione dati guidata in Excel")</span><span class="sxs-lookup"><span data-stu-id="c5d45-187">![Data Connection wizard in Excel](../../2014/tutorials/media/l9-perspectives-3b.gif "Data Connection wizard in Excel")</span></span>  
  
6.  <span data-ttu-id="c5d45-188">Selezionare `Internet Sales` nell'elenco **prospettiva** , quindi rivedere le misure e le dimensioni nel riquadro metadati.</span><span class="sxs-lookup"><span data-stu-id="c5d45-188">Select `Internet Sales` in the **Perspective** list and then review the measures and dimensions in the metadata pane.</span></span>  
  
     <span data-ttu-id="c5d45-189">Si noti che vengono visualizzati solo gli oggetti specificati per la prospettiva Internet Sales.</span><span class="sxs-lookup"><span data-stu-id="c5d45-189">Notice that only those objects that are specified for the Internet Sales perspective appear.</span></span>  
  
7.  <span data-ttu-id="c5d45-190">Nel riquadro dei metadati espandere **Misure**.</span><span class="sxs-lookup"><span data-stu-id="c5d45-190">In the metadata pane, expand **Measures**.</span></span>  
  
     <span data-ttu-id="c5d45-191">Si noti che `Internet Sales` viene visualizzato solo il gruppo di misure, insieme ai membri calcolati **Internet GPM** e **Internet Sales Ratio per tutti i prodotti** .</span><span class="sxs-lookup"><span data-stu-id="c5d45-191">Notice that only the `Internet Sales` measure group appears, together with the **Internet GPM** and **Internet Sales Ratio to All Products** calculated members.</span></span>  
  
8.  <span data-ttu-id="c5d45-192">Nel modello selezionare di nuovo Excel.</span><span class="sxs-lookup"><span data-stu-id="c5d45-192">In the model, select Excel again.</span></span> <span data-ttu-id="c5d45-193">Selezionare `Sales Summary`.</span><span class="sxs-lookup"><span data-stu-id="c5d45-193">Select `Sales Summary`.</span></span>  
  
     <span data-ttu-id="c5d45-194">Si noti che in ognuno di questi gruppi di misure viene visualizzata un'unica misura, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="c5d45-194">Notice that in each of these measure groups, only a single measure appears, as shown in the following image.</span></span>  
  
     <span data-ttu-id="c5d45-195">![Misure Internet Sales e Reseller Sales](../../2014/tutorials/media/l9-perspectives-4.gif "Misure Internet Sales e Reseller Sales")</span><span class="sxs-lookup"><span data-stu-id="c5d45-195">![Internet Sales and Reseller Sales measures](../../2014/tutorials/media/l9-perspectives-4.gif "Internet Sales and Reseller Sales measures")</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="c5d45-196">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="c5d45-196">Next Task in Lesson</span></span>  
 [<span data-ttu-id="c5d45-197">Definizione ed esplorazione delle traduzioni</span><span class="sxs-lookup"><span data-stu-id="c5d45-197">Defining and Browsing Translations</span></span>](lesson-9-2-defining-and-browsing-translations.md)  
  
## <a name="see-also"></a><span data-ttu-id="c5d45-198">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5d45-198">See Also</span></span>  
 <span data-ttu-id="c5d45-199">[Prospettive](multidimensional-models-olap-logical-cube-objects/perspectives.md) </span><span class="sxs-lookup"><span data-stu-id="c5d45-199">[Perspectives](multidimensional-models-olap-logical-cube-objects/perspectives.md) </span></span>  
 [<span data-ttu-id="c5d45-200">Prospettive nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="c5d45-200">Perspectives in Multidimensional Models</span></span>](multidimensional-models/perspectives-in-multidimensional-models.md)  
  
  
