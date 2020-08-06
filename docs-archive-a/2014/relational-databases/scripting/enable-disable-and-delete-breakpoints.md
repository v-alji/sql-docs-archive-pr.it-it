---
title: Abilitazione, disabilitazione ed eliminazione di punti di interruzione
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 357b5874-273f-43a9-8e30-83872bdea5dc
author: rothja
ms.author: jroth
ms.openlocfilehash: 17e83c6488b9d9026fb78e5fb8f50e22533fa61e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637235"
---
# <a name="enable-disable-and-delete-breakpoints"></a><span data-ttu-id="66f25-102">Abilitazione, disabilitazione ed eliminazione di punti di interruzione</span><span class="sxs-lookup"><span data-stu-id="66f25-102">Enable, Disable, and Delete Breakpoints</span></span>
  <span data-ttu-id="66f25-103">Per visualizzare e gestire tutti i punti di interruzione impostati, è possibile utilizzare la finestra **Punti di interruzione** .</span><span class="sxs-lookup"><span data-stu-id="66f25-103">To view and manage all the open breakpoints, you can use the **Breakpoints** window.</span></span> <span data-ttu-id="66f25-104">Utilizzare questa finestra per visualizzare informazioni sui punti di interruzione e per effettuare azioni quali l'eliminazione, la disabilitazione o l'abilitazione di punti di interruzione.</span><span class="sxs-lookup"><span data-stu-id="66f25-104">Use the window to view breakpoint information and to take actions such as deleting, disabling, or enabling breakpoints.</span></span>  
  
## <a name="the-breakpoints-window"></a><span data-ttu-id="66f25-105">Finestra Punti di interruzione</span><span class="sxs-lookup"><span data-stu-id="66f25-105">The Breakpoints Window</span></span>  
 <span data-ttu-id="66f25-106">Nella finestra **Punti di interruzione** vengono elencate informazioni quali la riga di codice sulla quale è impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="66f25-106">The **Breakpoints** window lists information such as which line of code the breakpoint is located on.</span></span> <span data-ttu-id="66f25-107">Nella finestra **Punti di interruzione** è inoltre possibile eliminare, disabilitare e abilitare punti di interruzione.</span><span class="sxs-lookup"><span data-stu-id="66f25-107">In the **Breakpoints** window, you can also delete, disable, and enable breakpoints.</span></span> <span data-ttu-id="66f25-108">Per ulteriori informazioni sulla finestra **Punti di interruzione** , vedere [Punti di interruzione Window](transact-sql-debugger-breakpoints-window.md).</span><span class="sxs-lookup"><span data-stu-id="66f25-108">For more information about the **Breakpoints** window, see [Breakpoints Window](transact-sql-debugger-breakpoints-window.md)</span></span>  
  
 <span data-ttu-id="66f25-109">La disabilitazione di un punto di interruzione previene la sospensione dell'esecuzione, tuttavia il punto di interruzione rimane presente qualora si desideri riattivarlo in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="66f25-109">Disabling a breakpoint prevents it from pausing execution, but leaves the definition in place in case you want to enable the breakpoint later.</span></span> <span data-ttu-id="66f25-110">L'eliminazione di un punto di interruzione ne comporta la rimozione permanente.</span><span class="sxs-lookup"><span data-stu-id="66f25-110">Deleting a breakpoint removes it permanently.</span></span> <span data-ttu-id="66f25-111">È necessario attivare o disattivare un nuovo punto di interruzione per mettere in pausa esecuzione sull'istruzione.</span><span class="sxs-lookup"><span data-stu-id="66f25-111">You must toggle a new breakpoint to pause execution on the statement.</span></span>  
  
## <a name="to-open-the-breakpoints-window"></a><span data-ttu-id="66f25-112">Per aprire la finestra Punti di interruzione</span><span class="sxs-lookup"><span data-stu-id="66f25-112">To Open the Breakpoints Window</span></span>  
 <span data-ttu-id="66f25-113">**To open the Breakpoints window**</span><span class="sxs-lookup"><span data-stu-id="66f25-113">**To open the Breakpoints window**</span></span>  
  
 <span data-ttu-id="66f25-114">È possibile aprire la finestra **Punti di interruzione** in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="66f25-114">You can open the **Breakpoints** window in one of the following ways:</span></span>  
  
-   <span data-ttu-id="66f25-115">Scegliere **Finestre** dal menu **Debug**, quindi fare clic su **Punti di interruzione**.</span><span class="sxs-lookup"><span data-stu-id="66f25-115">On the **Debug** menu, click **Windows**, and then click **Breakpoints**.</span></span>  
  
-   <span data-ttu-id="66f25-116">Nella barra degli strumenti **Debug** fare clic sul pulsante **Punti di interruzione** .</span><span class="sxs-lookup"><span data-stu-id="66f25-116">On the **Debug** toolbar, click the **Breakpoints** button.</span></span>  
  
-   <span data-ttu-id="66f25-117">Premere CTRL+ALT+B.</span><span class="sxs-lookup"><span data-stu-id="66f25-117">Press CTRL+ALT+B.</span></span>  
  
## <a name="to-disable-a-single-breakpoint"></a><span data-ttu-id="66f25-118">Per disabilitare un solo punto di interruzione</span><span class="sxs-lookup"><span data-stu-id="66f25-118">To Disable a Single Breakpoint</span></span>  
 <span data-ttu-id="66f25-119">**To disable a single breakpoint**</span><span class="sxs-lookup"><span data-stu-id="66f25-119">**To disable a single breakpoint**</span></span>  
  
 <span data-ttu-id="66f25-120">È possibile disabilitare un singolo punto di interruzione in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="66f25-120">You can disable a single breakpoint in one of the following ways:</span></span>  
  
-   <span data-ttu-id="66f25-121">Nella finestra dell'editor di query, fare clic con il pulsante destro del mouse sul punto di interruzione, quindi fare clic su **Disabilita punto di interruzione**.</span><span class="sxs-lookup"><span data-stu-id="66f25-121">In the Query Editor window, right-click the breakpoint, and then click **Disable Breakpoint**.</span></span>  
  
-   <span data-ttu-id="66f25-122">Nella finestra Punti di interruzione, deselezionare la casella di controllo a sinistra del punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="66f25-122">In the Breakpoints window, clear the check box to the left of the breakpoint.</span></span>  
  
## <a name="to-disable-all-breakpoints"></a><span data-ttu-id="66f25-123">Per disabilitare tutti i punti di interruzione</span><span class="sxs-lookup"><span data-stu-id="66f25-123">To Disable All Breakpoints</span></span>  
 <span data-ttu-id="66f25-124">**To disable all breakpoints**</span><span class="sxs-lookup"><span data-stu-id="66f25-124">**To disable all breakpoints**</span></span>  
  
 <span data-ttu-id="66f25-125">È possibile disabilitare tutti i punti di interruzione in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="66f25-125">You can disable all breakpoints in one of the following ways:</span></span>  
  
-   <span data-ttu-id="66f25-126">Scegliere **Disabilita tutti i punti di interruzione** dal menu **Debug**.</span><span class="sxs-lookup"><span data-stu-id="66f25-126">On the **Debug** menu, click **Disable All Breakpoints**.</span></span>  
  
-   <span data-ttu-id="66f25-127">Nella barra degli strumenti della finestra **Punti di interruzione** , fare clic sul pulsante **Disabilita tutti i punti di interruzione** .</span><span class="sxs-lookup"><span data-stu-id="66f25-127">On the toolbar of the **Breakpoints** window, click the **Disable All Breakpoints** button.</span></span>  
  
## <a name="to-enable-a-single-breakpoint"></a><span data-ttu-id="66f25-128">Per abilitare un solo punto di interruzione</span><span class="sxs-lookup"><span data-stu-id="66f25-128">To Enable a Single Breakpoint</span></span>  
 <span data-ttu-id="66f25-129">**To enable a single breakpoint**</span><span class="sxs-lookup"><span data-stu-id="66f25-129">**To enable a single breakpoint**</span></span>  
  
 <span data-ttu-id="66f25-130">È possibile abilitare un singolo punto di interruzione in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="66f25-130">You can enable a single breakpoint in one of the following ways:</span></span>  
  
-   <span data-ttu-id="66f25-131">Nella finestra dell'editor di query, fare clic con il pulsante destro del mouse sul punto di interruzione, quindi fare clic su **Abilita punto di interruzione**.</span><span class="sxs-lookup"><span data-stu-id="66f25-131">In the Query Editor window, right-click the breakpoint, and then click **Enable Breakpoint**.</span></span>  
  
-   <span data-ttu-id="66f25-132">Nella finestra Punti di interruzione, selezionare la casella di controllo a sinistra del punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="66f25-132">In the Breakpoints window, click the box to the left of the breakpoint.</span></span>  
  
## <a name="to-enable-all-breakpoints"></a><span data-ttu-id="66f25-133">Per abilitare tutti i punti di interruzione</span><span class="sxs-lookup"><span data-stu-id="66f25-133">To Enable All Breakpoints</span></span>  
 <span data-ttu-id="66f25-134">**To enable all breakpoints**</span><span class="sxs-lookup"><span data-stu-id="66f25-134">**To enable all breakpoints**</span></span>  
  
 <span data-ttu-id="66f25-135">È possibile abilitare tutti i punti di interruzione in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="66f25-135">You can enable all breakpoints in one of the following ways:</span></span>  
  
-   <span data-ttu-id="66f25-136">Scegliere **Abilita tutti i punti di interruzione** dal menu **Debug**.</span><span class="sxs-lookup"><span data-stu-id="66f25-136">On the **Debug** menu, click **Enable All Breakpoints**.</span></span>  
  
-   <span data-ttu-id="66f25-137">Nella barra degli strumenti della finestra **Punti di interruzione** , fare clic sul pulsante **Abilita tutti i punti di interruzione** .</span><span class="sxs-lookup"><span data-stu-id="66f25-137">On the toolbar of the **Breakpoints** window, click the **Enable All Breakpoints** button.</span></span>  
  
## <a name="to-delete-a-single-breakpoint"></a><span data-ttu-id="66f25-138">Per eliminare un solo punto di interruzione</span><span class="sxs-lookup"><span data-stu-id="66f25-138">To Delete a Single Breakpoint</span></span>  
 <span data-ttu-id="66f25-139">**To delete a single breakpoint**</span><span class="sxs-lookup"><span data-stu-id="66f25-139">**To delete a single breakpoint**</span></span>  
  
 <span data-ttu-id="66f25-140">È possibile eliminare un singolo punto di interruzione in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="66f25-140">You can delete a single breakpoint in one of the following ways:</span></span>  
  
-   <span data-ttu-id="66f25-141">Nella finestra dell'editor di query, fare clic con il pulsante destro del mouse sul punto di interruzione, quindi fare clic su **Elimina punto di interruzione**.</span><span class="sxs-lookup"><span data-stu-id="66f25-141">In the Query Editor window, right-click the breakpoint, and then click **Delete Breakpoint**.</span></span>  
  
-   <span data-ttu-id="66f25-142">Nella finestra Punti di interruzione fare clic con il pulsante destro del mouse su un punto di interruzione e scegliere **Elimina** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="66f25-142">In the Breakpoints window, right-click the breakpoint, and then click **Delete** on the shortcut menu.</span></span>  
  
-   <span data-ttu-id="66f25-143">Nella finestra Punti di interruzione, selezionare il punto di interruzione, quindi premere CANC.</span><span class="sxs-lookup"><span data-stu-id="66f25-143">In the Breakpoints window, select the breakpoint, and then press DELETE.</span></span>  
  
## <a name="to-delete-all-breakpoints"></a><span data-ttu-id="66f25-144">Per eliminare tutti i punti di interruzione</span><span class="sxs-lookup"><span data-stu-id="66f25-144">To Delete All Breakpoints</span></span>  
 <span data-ttu-id="66f25-145">**To delete all breakpoints**</span><span class="sxs-lookup"><span data-stu-id="66f25-145">**To delete all breakpoints**</span></span>  
  
 <span data-ttu-id="66f25-146">È possibile eliminare tutti i punti di interruzione in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="66f25-146">You can delete all breakpoints in one of the following ways:</span></span>  
  
-   <span data-ttu-id="66f25-147">Scegliere **Elimina tutti i punti di interruzione** dal menu **Debug**.</span><span class="sxs-lookup"><span data-stu-id="66f25-147">On the **Debug** menu, cllick **Delete All Breakpoints**.</span></span>  
  
-   <span data-ttu-id="66f25-148">Sulla barra degli strumenti della finestra **Punti di interruzione** fare clic sul pulsante **Elimina tutti i punti di interruzione** .</span><span class="sxs-lookup"><span data-stu-id="66f25-148">On the toolbar of the **Breakpoints** window, click the **Delete All Breakpoints** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66f25-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66f25-149">See Also</span></span>  
 [<span data-ttu-id="66f25-150">Attivare/disattivare un punto di interruzione</span><span class="sxs-lookup"><span data-stu-id="66f25-150">Toggle a Breakpoint</span></span>](../spatial/point.md)  
  
  
