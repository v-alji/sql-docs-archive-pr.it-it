---
title: "Attività 6: verificare che l'attributo basato su dominio venga creato utilizzando Gestione dati master | Microsoft Docs"
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 6e90517a-910c-4c33-8f11-92ac3cff4fdc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ea26202ca9e607058b1e385957be3ea3d04038b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623639"
---
# <a name="task-6-verify-that-the-domain-based-attribute-is-created-using-master-data-manager"></a><span data-ttu-id="59e1c-102">Attività 6: Verifica della creazione dell'attributo basato su dominio tramite Gestione dati master</span><span class="sxs-lookup"><span data-stu-id="59e1c-102">Task 6: Verify that the Domain-Based Attribute is Created using Master Data Manager</span></span>
  <span data-ttu-id="59e1c-103">In questa attività si verifica che l'entità **State** venga creata in **MDS** e che l'attributo **State** dell'entità **Supplier** sia un attributo basato su dominio che dipende dall'entità **State** tramite **Gestione dati master**.</span><span class="sxs-lookup"><span data-stu-id="59e1c-103">In this task, you verify that the **State** entity is created in **MDS** and the **State** attribute of the **Supplier** entity is a domain-based attribute that depends on the **State** entity by using **Master Data Manager**.</span></span>

1.  <span data-ttu-id="59e1c-104">Passare all'applicazione Web **Gestione dati master**.</span><span class="sxs-lookup"><span data-stu-id="59e1c-104">Switch to the **Master Data Manger** web application.</span></span>

2.  <span data-ttu-id="59e1c-105">Fare clic su **SQL Server 2012 Master Data Services** in alto per tornare alla home page.</span><span class="sxs-lookup"><span data-stu-id="59e1c-105">Click **SQL Server 2012 Master Data Services** at the top to get to the home page.</span></span>

3.  <span data-ttu-id="59e1c-106">Assicurarsi che il modello **Suppliers** sia selezionato e fare clic su **Esplora risorse**.</span><span class="sxs-lookup"><span data-stu-id="59e1c-106">Ensure that **Suppliers** model is selected and click **Explorer**.</span></span> <span data-ttu-id="59e1c-107">Se **Esplora risorse** è già aperto è possibile aggiornare la pagina.</span><span class="sxs-lookup"><span data-stu-id="59e1c-107">You could refresh the page if you already had **Explorer** open.</span></span>

4.  <span data-ttu-id="59e1c-108">Passando il puntatore su **Entità** nella barra dei menu, si noti che ora sono presenti due entità: **Supplier** e **State**.</span><span class="sxs-lookup"><span data-stu-id="59e1c-108">Hover your mouse over **Entities** on the menu bar and notice that now there are two entities: **Supplier** and **State**.</span></span>

     <span data-ttu-id="59e1c-109">![Menu Entità con Stato e fornitore](../../2014/tutorials/media/et-verifythatthedbaiscreatedusingmdm-01.jpg "Menu Entità con Stato e fornitore")</span><span class="sxs-lookup"><span data-stu-id="59e1c-109">![Entities Menu with State and Supplier](../../2014/tutorials/media/et-verifythatthedbaiscreatedusingmdm-01.jpg "Entities Menu with State and Supplier")</span></span>

5.  <span data-ttu-id="59e1c-110">Fare clic su **State** se l'entità non è già aperta.</span><span class="sxs-lookup"><span data-stu-id="59e1c-110">Click **State** if the entity is not open already.</span></span>

6.  <span data-ttu-id="59e1c-111">Selezionare **GA** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="59e1c-111">Select **GA** from the list.</span></span>

7.  <span data-ttu-id="59e1c-112">Nel riquadro **Dettagli** a destra modificare il **Nome** in **Georgia** nel **riquadro destro** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="59e1c-112">In the **Details** pane to the right, change the **Name** to **Georgia** in the **right pane**, and click **OK**.</span></span>

8.  <span data-ttu-id="59e1c-113">Ripetere i passaggi precedenti per gli altri stati.</span><span class="sxs-lookup"><span data-stu-id="59e1c-113">Repeat the previous steps for other states.</span></span>

    |<span data-ttu-id="59e1c-114">Codice</span><span class="sxs-lookup"><span data-stu-id="59e1c-114">Code</span></span>|<span data-ttu-id="59e1c-115">Nome</span><span class="sxs-lookup"><span data-stu-id="59e1c-115">Name</span></span>|
    |----------|----------|
    |<span data-ttu-id="59e1c-116">CA</span><span class="sxs-lookup"><span data-stu-id="59e1c-116">CA</span></span>|<span data-ttu-id="59e1c-117">California</span><span class="sxs-lookup"><span data-stu-id="59e1c-117">California</span></span>|
    |<span data-ttu-id="59e1c-118">CO</span><span class="sxs-lookup"><span data-stu-id="59e1c-118">CO</span></span>|<span data-ttu-id="59e1c-119">Colorado</span><span class="sxs-lookup"><span data-stu-id="59e1c-119">Colorado</span></span>|
    |<span data-ttu-id="59e1c-120">IL</span><span class="sxs-lookup"><span data-stu-id="59e1c-120">IL</span></span>|<span data-ttu-id="59e1c-121">Illinois</span><span class="sxs-lookup"><span data-stu-id="59e1c-121">Illinois</span></span>|
    |<span data-ttu-id="59e1c-122">DC</span><span class="sxs-lookup"><span data-stu-id="59e1c-122">DC</span></span>|<span data-ttu-id="59e1c-123">District of Columbia</span><span class="sxs-lookup"><span data-stu-id="59e1c-123">District of Columbia</span></span>|
    |<span data-ttu-id="59e1c-124">FL</span><span class="sxs-lookup"><span data-stu-id="59e1c-124">FL</span></span>|<span data-ttu-id="59e1c-125">Florida</span><span class="sxs-lookup"><span data-stu-id="59e1c-125">Florida</span></span>|
    |<span data-ttu-id="59e1c-126">AL</span><span class="sxs-lookup"><span data-stu-id="59e1c-126">AL</span></span>|<span data-ttu-id="59e1c-127">Alabama</span><span class="sxs-lookup"><span data-stu-id="59e1c-127">Alabama</span></span>|
    |<span data-ttu-id="59e1c-128">KY</span><span class="sxs-lookup"><span data-stu-id="59e1c-128">KY</span></span>|<span data-ttu-id="59e1c-129">Kentucky</span><span class="sxs-lookup"><span data-stu-id="59e1c-129">Kentucky</span></span>|
    |<span data-ttu-id="59e1c-130">MA</span><span class="sxs-lookup"><span data-stu-id="59e1c-130">MA</span></span>|<span data-ttu-id="59e1c-131">Massachusetts</span><span class="sxs-lookup"><span data-stu-id="59e1c-131">Massachusetts</span></span>|
    |<span data-ttu-id="59e1c-132">AZ</span><span class="sxs-lookup"><span data-stu-id="59e1c-132">AZ</span></span>|<span data-ttu-id="59e1c-133">Arizona</span><span class="sxs-lookup"><span data-stu-id="59e1c-133">Arizona</span></span>|
    |<span data-ttu-id="59e1c-134">MI</span><span class="sxs-lookup"><span data-stu-id="59e1c-134">MI</span></span>|<span data-ttu-id="59e1c-135">Michigan</span><span class="sxs-lookup"><span data-stu-id="59e1c-135">Michigan</span></span>|
    |<span data-ttu-id="59e1c-136">MN</span><span class="sxs-lookup"><span data-stu-id="59e1c-136">MN</span></span>|<span data-ttu-id="59e1c-137">Minnesota</span><span class="sxs-lookup"><span data-stu-id="59e1c-137">Minnesota</span></span>|
    |<span data-ttu-id="59e1c-138">NJ</span><span class="sxs-lookup"><span data-stu-id="59e1c-138">NJ</span></span>|<span data-ttu-id="59e1c-139">New Jersey</span><span class="sxs-lookup"><span data-stu-id="59e1c-139">New Jersey</span></span>|
    |<span data-ttu-id="59e1c-140">NV</span><span class="sxs-lookup"><span data-stu-id="59e1c-140">NV</span></span>|<span data-ttu-id="59e1c-141">Nevada</span><span class="sxs-lookup"><span data-stu-id="59e1c-141">Nevada</span></span>|
    |<span data-ttu-id="59e1c-142">NY</span><span class="sxs-lookup"><span data-stu-id="59e1c-142">NY</span></span>|<span data-ttu-id="59e1c-143">New York</span><span class="sxs-lookup"><span data-stu-id="59e1c-143">New York</span></span>|
    |<span data-ttu-id="59e1c-144">OH</span><span class="sxs-lookup"><span data-stu-id="59e1c-144">OH</span></span>|<span data-ttu-id="59e1c-145">Ohio</span><span class="sxs-lookup"><span data-stu-id="59e1c-145">Ohio</span></span>|
    |<span data-ttu-id="59e1c-146">OK</span><span class="sxs-lookup"><span data-stu-id="59e1c-146">OK</span></span>|<span data-ttu-id="59e1c-147">Oklahoma</span><span class="sxs-lookup"><span data-stu-id="59e1c-147">Oklahoma</span></span>|
    |<span data-ttu-id="59e1c-148">OR</span><span class="sxs-lookup"><span data-stu-id="59e1c-148">OR</span></span>|<span data-ttu-id="59e1c-149">Oregon</span><span class="sxs-lookup"><span data-stu-id="59e1c-149">Oregon</span></span>|
    |<span data-ttu-id="59e1c-150">PA</span><span class="sxs-lookup"><span data-stu-id="59e1c-150">PA</span></span>|<span data-ttu-id="59e1c-151">Pennsylvania</span><span class="sxs-lookup"><span data-stu-id="59e1c-151">Pennsylvania</span></span>|
    |<span data-ttu-id="59e1c-152">SC</span><span class="sxs-lookup"><span data-stu-id="59e1c-152">SC</span></span>|<span data-ttu-id="59e1c-153">South Carolina</span><span class="sxs-lookup"><span data-stu-id="59e1c-153">South Carolina</span></span>|
    |<span data-ttu-id="59e1c-154">KS</span><span class="sxs-lookup"><span data-stu-id="59e1c-154">KS</span></span>|<span data-ttu-id="59e1c-155">Kansas</span><span class="sxs-lookup"><span data-stu-id="59e1c-155">Kansas</span></span>|
    |<span data-ttu-id="59e1c-156">TN</span><span class="sxs-lookup"><span data-stu-id="59e1c-156">TN</span></span>|<span data-ttu-id="59e1c-157">Tennessee</span><span class="sxs-lookup"><span data-stu-id="59e1c-157">Tennessee</span></span>|
    |<span data-ttu-id="59e1c-158">TX</span><span class="sxs-lookup"><span data-stu-id="59e1c-158">TX</span></span>|<span data-ttu-id="59e1c-159">Texas</span><span class="sxs-lookup"><span data-stu-id="59e1c-159">Texas</span></span>|
    |<span data-ttu-id="59e1c-160">UT</span><span class="sxs-lookup"><span data-stu-id="59e1c-160">UT</span></span>|<span data-ttu-id="59e1c-161">Utah</span><span class="sxs-lookup"><span data-stu-id="59e1c-161">Utah</span></span>|
    |<span data-ttu-id="59e1c-162">VA</span><span class="sxs-lookup"><span data-stu-id="59e1c-162">VA</span></span>|<span data-ttu-id="59e1c-163">Virginia</span><span class="sxs-lookup"><span data-stu-id="59e1c-163">Virginia</span></span>|
    |<span data-ttu-id="59e1c-164">WA</span><span class="sxs-lookup"><span data-stu-id="59e1c-164">WA</span></span>|<span data-ttu-id="59e1c-165">Washington</span><span class="sxs-lookup"><span data-stu-id="59e1c-165">Washington</span></span>|
    |<span data-ttu-id="59e1c-166">WI</span><span class="sxs-lookup"><span data-stu-id="59e1c-166">WI</span></span>|<span data-ttu-id="59e1c-167">Wisconsin</span><span class="sxs-lookup"><span data-stu-id="59e1c-167">Wisconsin</span></span>|
    |<span data-ttu-id="59e1c-168">HI</span><span class="sxs-lookup"><span data-stu-id="59e1c-168">HI</span></span>|<span data-ttu-id="59e1c-169">Hawaii</span><span class="sxs-lookup"><span data-stu-id="59e1c-169">Hawaii</span></span>|
    |<span data-ttu-id="59e1c-170">MD</span><span class="sxs-lookup"><span data-stu-id="59e1c-170">MD</span></span>|<span data-ttu-id="59e1c-171">Maryland</span><span class="sxs-lookup"><span data-stu-id="59e1c-171">Maryland</span></span>|
    |<span data-ttu-id="59e1c-172">CT</span><span class="sxs-lookup"><span data-stu-id="59e1c-172">CT</span></span>|<span data-ttu-id="59e1c-173">Connecticut</span><span class="sxs-lookup"><span data-stu-id="59e1c-173">Connecticut</span></span>|

9. <span data-ttu-id="59e1c-174">Selezionare una delle voci degli stati e fare clic su **Visualizza transazioni** nella barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="59e1c-174">Select any of the state entries and click **View Transactions** from the Toolbar.</span></span> <span data-ttu-id="59e1c-175">La transazione per l'aggiornamento appena effettuato viene visualizzata nell'elenco di transazioni.</span><span class="sxs-lookup"><span data-stu-id="59e1c-175">You should see the transaction for the update you just made is in the list of transactions.</span></span>

10. <span data-ttu-id="59e1c-176">Passare il puntatore sul menu **Entità** e fare clic su **Supplier**.</span><span class="sxs-lookup"><span data-stu-id="59e1c-176">Hover the mouse over **Entities** menu and click **Supplier**.</span></span>

11. <span data-ttu-id="59e1c-177">A questo punto si noti che un valore per il campo **Stato** può essere modificato nel riquadro **Dettagli** tramite l'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="59e1c-177">Now, notice that a value for the **State** field can be changed in the **Details** pane by using the drop-down list.</span></span> <span data-ttu-id="59e1c-178">È anche possibile osservare che, nell'elenco a sinistra e nell'elenco a discesa nel riquadro **Dettagli**, viene prima visualizzato il codice e poi il nome tra parentesi graffe.</span><span class="sxs-lookup"><span data-stu-id="59e1c-178">You can also see that, in the list to the left and in the drop-down list in the **Details** pane, code is displayed first and then the name in curly braces.</span></span> <span data-ttu-id="59e1c-179">È possibile modificare anche qualsiasi altro valore nel riquadro **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="59e1c-179">You can also change any other value in the **Details** pane.</span></span>

     <span data-ttu-id="59e1c-180">![Attributo stato con codici e nomi aggiornati](../../2014/tutorials/media/et-verifythatthedbaiscreatedusingmdm-02.jpg "Attributo stato con codici e nomi aggiornati")</span><span class="sxs-lookup"><span data-stu-id="59e1c-180">![State Attribute with Updated Code and Names](../../2014/tutorials/media/et-verifythatthedbaiscreatedusingmdm-02.jpg "State Attribute with Updated Code and Names")</span></span>

## <a name="next-step"></a><span data-ttu-id="59e1c-181">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="59e1c-181">Next Step</span></span>
 [<span data-ttu-id="59e1c-182">Attività 7: Visualizzazione degli aggiornamenti eseguiti tramite Gestione dati master in Excel</span><span class="sxs-lookup"><span data-stu-id="59e1c-182">Task 7: Viewing Updates Made using Master Data Manager in Excel</span></span>](../../2014/tutorials/task-7-viewing-updates-made-using-master-data-manager-in-excel.md)


