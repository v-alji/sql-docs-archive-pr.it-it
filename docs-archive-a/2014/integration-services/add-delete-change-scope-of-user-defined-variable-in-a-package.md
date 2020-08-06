---
title: Aggiungere, eliminare e modificare l'ambito di una variabile definita dall'utente in un pacchetto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- variables [Integration Services], adding
ms.assetid: cbf40c7f-3c8a-48cd-aefa-8b37faf8b40e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1a7e5980fc7f730c69ef886e4e80760cfbdc9e4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627958"
---
# <a name="add-delete-change-scope-of-user-defined-variable-in-a-package"></a><span data-ttu-id="b4cb7-102">Aggiungere, eliminare o modificare l'ambito di una variabile definita dall'utente in un pacchetto</span><span class="sxs-lookup"><span data-stu-id="b4cb7-102">Add, Delete, Change Scope of User-Defined Variable in a Package</span></span>
  <span data-ttu-id="b4cb7-103">In queste procedure viene descritto come aggiungere, eliminare e modificare l'ambito di una variabile definita dall'utente in un pacchetto tramite la finestra **Variabili** .</span><span class="sxs-lookup"><span data-stu-id="b4cb7-103">These procedures describe how to add, delete, and change the scope of a user-defined variable in a package by using the **Variables** window.</span></span>  
  
 <span data-ttu-id="b4cb7-104">Per altre informazioni sull'ambito delle variabili, vedere [Variabili di Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="b4cb7-104">For more information about variable scope, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
 <span data-ttu-id="b4cb7-105">In [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] vengono anche fornite variabili di sistema che rendono le informazioni di sistema disponibili durante l'esecuzione e che sono utilizzabili in contenitori come pacchetti e gestori di eventi.</span><span class="sxs-lookup"><span data-stu-id="b4cb7-105">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] also provides system variables that make system information available at run time and can be used in containers such as packages and event handlers.</span></span> <span data-ttu-id="b4cb7-106">Le variabili di sistema non possono essere eliminate.</span><span class="sxs-lookup"><span data-stu-id="b4cb7-106">You cannot delete system variables.</span></span>  
  
### <a name="to-add-a-variable"></a><span data-ttu-id="b4cb7-107">Per aggiungere una variabile</span><span class="sxs-lookup"><span data-stu-id="b4cb7-107">To add a variable</span></span>  
  
1.  <span data-ttu-id="b4cb7-108">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il pacchetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="b4cb7-108">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package you want to work with.</span></span>  
  
2.  <span data-ttu-id="b4cb7-109">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="b4cb7-109">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="b4cb7-110">In Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] eseguire una delle operazioni seguenti per definire l'ambito della variabile:</span><span class="sxs-lookup"><span data-stu-id="b4cb7-110">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, to define the scope of the variable, do one of the following:</span></span>  
  
    -   <span data-ttu-id="b4cb7-111">Per impostare il pacchetto come ambito, fare clic in un punto qualsiasi dell'area di progettazione della scheda **Flusso di controllo** .</span><span class="sxs-lookup"><span data-stu-id="b4cb7-111">To set the scope to the package, click anywhere on the design surface of the **Control Flow** tab.</span></span>  
  
    -   <span data-ttu-id="b4cb7-112">Per impostare un gestore dell'evento come ambito, selezionare un file eseguibile e un gestore dell'evento nell'area di progettazione della scheda **Gestore evento** .</span><span class="sxs-lookup"><span data-stu-id="b4cb7-112">To set the scope to an event handler, select an executable and an event handler on the design surface of the **Event Handler** tab.</span></span>  
  
    -   <span data-ttu-id="b4cb7-113">Per impostare un'attività o un contenitore come ambito, nell'area di progettazione della scheda **Flusso di controllo** o **Gestore evento** fare clic su un'attività o un contenitore.</span><span class="sxs-lookup"><span data-stu-id="b4cb7-113">To set the scope to a task or container, on the design surface of the **Control Flow** tab or the **Event Handler** tab, click a task or container.</span></span>  
  
4.  <span data-ttu-id="b4cb7-114">Scegliere **Variabili** dal menu **SSIS**.</span><span class="sxs-lookup"><span data-stu-id="b4cb7-114">On the **SSIS** menu, click **Variables**.</span></span> <span data-ttu-id="b4cb7-115">Facoltativamente, è possibile visualizzare la finestra **Variabili** eseguendo il mapping del comando View.Variables a una combinazione di tasti scelta dall'utente nella pagina **Tastiera** della finestra di dialogo **Opzioni** .</span><span class="sxs-lookup"><span data-stu-id="b4cb7-115">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
5.  <span data-ttu-id="b4cb7-116">Nella finestra **variabili** fare clic sull'icona **Aggiungi variabile** .</span><span class="sxs-lookup"><span data-stu-id="b4cb7-116">In the **Variables** window, click the **Add Variable** icon.</span></span> <span data-ttu-id="b4cb7-117">La nuova variabile verrà aggiunta all'elenco.</span><span class="sxs-lookup"><span data-stu-id="b4cb7-117">The new variable is added to the list.</span></span>  
  
6.  <span data-ttu-id="b4cb7-118">Facoltativamente, fare clic sull'icona **Opzioni griglia** , selezionare le colonne aggiuntive da visualizzare nella finestra di dialogo **Variables Grid Options** (Opzioni griglia variabili) e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4cb7-118">Optionally, click the **Grid Options** icon, select additional columns to show in the **Variables Grid Options** dialog box, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="b4cb7-119">Facoltativamente, impostare le proprietà delle variabili.</span><span class="sxs-lookup"><span data-stu-id="b4cb7-119">Optionally, set the variable properties.</span></span> <span data-ttu-id="b4cb7-120">Per altre informazioni, vedere [Impostazione delle proprietà di una variabile definita dall'utente](../../2014/integration-services/set-the-properties-of-a-user-defined-variable.md).</span><span class="sxs-lookup"><span data-stu-id="b4cb7-120">For more information, see [Set the Properties of a User-Defined Variable](../../2014/integration-services/set-the-properties-of-a-user-defined-variable.md).</span></span>  
  
8.  <span data-ttu-id="b4cb7-121">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="b4cb7-121">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-delete-a-variable"></a><span data-ttu-id="b4cb7-122">Per eliminare una variabile</span><span class="sxs-lookup"><span data-stu-id="b4cb7-122">To delete a variable</span></span>  
  
1.  <span data-ttu-id="b4cb7-123">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="b4cb7-123">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="b4cb7-124">In Esplora soluzioni fare clic con il pulsante destro del mouse sul pacchetto in modo da aprirlo.</span><span class="sxs-lookup"><span data-stu-id="b4cb7-124">In Solution Explorer, right-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="b4cb7-125">Scegliere **Variabili** dal menu **SSIS**.</span><span class="sxs-lookup"><span data-stu-id="b4cb7-125">On the **SSIS** menu, click **Variables**.</span></span> <span data-ttu-id="b4cb7-126">Facoltativamente, è possibile visualizzare la finestra **Variabili** eseguendo il mapping del comando View.Variables a una combinazione di tasti scelta dall'utente nella pagina **Tastiera** della finestra di dialogo **Opzioni** .</span><span class="sxs-lookup"><span data-stu-id="b4cb7-126">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
4.  <span data-ttu-id="b4cb7-127">Selezionare la variabile che si desidera eliminare e quindi fare clic su **Elimina variabile**.</span><span class="sxs-lookup"><span data-stu-id="b4cb7-127">Select the variable to delete, and then click **Delete Variable**.</span></span>  
  
     <span data-ttu-id="b4cb7-128">Se la variabile non viene visualizzata nella finestra variabili, fare clic su **Opzioni griglia** , quindi selezionare **Mostra variabili di tutti gli ambiti**.</span><span class="sxs-lookup"><span data-stu-id="b4cb7-128">If you don't see the variable in the Variables window, click **Grid Options** and then select **Show variables of all scopes**.</span></span>  
  
5.  <span data-ttu-id="b4cb7-129">Se viene visualizzata la finestra di dialogo **Conferma eliminazione variabili** , fare clic su **Sì** per confermare.</span><span class="sxs-lookup"><span data-stu-id="b4cb7-129">If the **Confirm Deletion of Variables** dialog box opens, click **Yes** to confirm.</span></span>  
  
6.  <span data-ttu-id="b4cb7-130">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="b4cb7-130">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-change-the-scope-of-a-variable"></a><span data-ttu-id="b4cb7-131">Per modificare l'ambito di una variabile</span><span class="sxs-lookup"><span data-stu-id="b4cb7-131">To change the scope of a variable</span></span>  
  
1.  <span data-ttu-id="b4cb7-132">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="b4cb7-132">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="b4cb7-133">In Esplora soluzioni fare clic con il pulsante destro del mouse sul pacchetto in modo da aprirlo.</span><span class="sxs-lookup"><span data-stu-id="b4cb7-133">In Solution Explorer, right-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="b4cb7-134">Scegliere **Variabili** dal menu **SSIS**.</span><span class="sxs-lookup"><span data-stu-id="b4cb7-134">On the **SSIS** menu, click **Variables**.</span></span> <span data-ttu-id="b4cb7-135">Facoltativamente, è possibile visualizzare la finestra **Variabili** eseguendo il mapping del comando View.Variables a una combinazione di tasti scelta dall'utente nella pagina **Tastiera** della finestra di dialogo **Opzioni** .</span><span class="sxs-lookup"><span data-stu-id="b4cb7-135">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
4.  <span data-ttu-id="b4cb7-136">Selezionare la variabile e quindi fare clic su **Sposta variabile**.</span><span class="sxs-lookup"><span data-stu-id="b4cb7-136">Select the variable and then click **Move Variable**.</span></span>  
  
     <span data-ttu-id="b4cb7-137">Se la variabile non viene visualizzata nella finestra variabili, fare clic su **Opzioni griglia** , quindi selezionare **Mostra variabili di tutti gli ambiti**.</span><span class="sxs-lookup"><span data-stu-id="b4cb7-137">If you don't see the variable in the Variables window, click **Grid Options** and then select **Show variables of all scopes**.</span></span>  
  
5.  <span data-ttu-id="b4cb7-138">Nella finestra di dialogo **Seleziona nuovo ambito** selezionare il pacchetto oppure un contenitore, un'attività o un gestore eventi del pacchetto per modificare l'ambito della variabile.</span><span class="sxs-lookup"><span data-stu-id="b4cb7-138">In the **Select New Scope** dialog box, select the package or a container, task, or event handler in the package, to change the variable scope.</span></span>  
  
6.  <span data-ttu-id="b4cb7-139">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="b4cb7-139">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4cb7-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4cb7-140">See Also</span></span>  
 <span data-ttu-id="b4cb7-141">[Variabili di Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="b4cb7-141">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="b4cb7-142">[Usare variabili nei pacchetti](../../2014/integration-services/use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="b4cb7-142">[Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md) </span></span>  
 <span data-ttu-id="b4cb7-143">[Impostare le proprietà di una variabile definita dall'utente](../../2014/integration-services/set-the-properties-of-a-user-defined-variable.md) </span><span class="sxs-lookup"><span data-stu-id="b4cb7-143">[Set the Properties of a User-Defined Variable](../../2014/integration-services/set-the-properties-of-a-user-defined-variable.md) </span></span>  
 [<span data-ttu-id="b4cb7-144">Usare i valori di variabili e parametri in un pacchetto figlio</span><span class="sxs-lookup"><span data-stu-id="b4cb7-144">Use the Values of Variables and Parameters in a Child Package</span></span>](../../2014/integration-services/use-the-values-of-variables-and-parameters-in-a-child-package.md)  
  
  
