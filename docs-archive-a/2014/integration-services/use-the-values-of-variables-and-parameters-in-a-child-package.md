---
title: Usare i valori di variabili e parametri in un pacchetto figlio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- variables [Integration Services], passing between packages
- configurations [Integration Services]
- packages [Integration Services], configurations
- variables [Integration Services], adding
ms.assetid: 9b939edb-4e17-48e5-8428-855beb10049c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 28561db91e5e924d8b25f9c7be7a4a51c6c315ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635114"
---
# <a name="use-the-values-of-variables-and-parameters-in-a-child-package"></a><span data-ttu-id="4549c-102">Utilizzare i valori di variabili e parametri in un pacchetto figlio</span><span class="sxs-lookup"><span data-stu-id="4549c-102">Use the Values of Variables and Parameters in a Child Package</span></span>
  <span data-ttu-id="4549c-103">In questa procedura viene descritto come creare una configurazione di pacchetto in cui viene utilizzato il tipo di configurazione variabile padre.</span><span class="sxs-lookup"><span data-stu-id="4549c-103">This procedure describes how to create a package configuration that uses the parent variable configuration type.</span></span> <span data-ttu-id="4549c-104">Questo tipo di configurazione consente a un pacchetto figlio eseguito da un pacchetto padre di accedere a una variabile del pacchetto padre.</span><span class="sxs-lookup"><span data-stu-id="4549c-104">This configuration type enables a child package that is run from a parent package to access a variable in the parent.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4549c-105">È inoltre possibile passare valori a un pacchetto figlio configurando l'attività Esegui pacchetto per eseguire il mapping delle variabili o dei parametri del pacchetto padre o dei parametri del progetto ai parametri del pacchetto figlio.</span><span class="sxs-lookup"><span data-stu-id="4549c-105">You can also pass values to a child package by configuring the Execute Package Task to map parent package variables or parameters, or project parameters, to child package parameters.</span></span> <span data-ttu-id="4549c-106">Per altre informazioni, vedere [Attività Esegui pacchetto](control-flow/execute-package-task.md).</span><span class="sxs-lookup"><span data-stu-id="4549c-106">For more information, see [Execute Package Task](control-flow/execute-package-task.md).</span></span>  
  
 <span data-ttu-id="4549c-107">Non è necessario creare la variabile nel pacchetto padre prima di creare la configurazione di pacchetto nel pacchetto figlio.</span><span class="sxs-lookup"><span data-stu-id="4549c-107">It is not necessary to create the variable in the parent package before you create the package configuration in the child package.</span></span> <span data-ttu-id="4549c-108">La variabile può essere aggiunta al pacchetto padre in qualsiasi momento, ma nella configurazione di pacchetto è necessario utilizzare il nome esatto della variabile padre.</span><span class="sxs-lookup"><span data-stu-id="4549c-108">You can add the variable to the parent package at any time, but you must use the exact name of the parent variable in the package configuration.</span></span> <span data-ttu-id="4549c-109">Affinché sia possibile creare una configurazione che utilizza la variabile padre, tuttavia, nel pacchetto figlio deve essere presente una variabile che possa essere aggiornata dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="4549c-109">However, before you can create a parent variable configuration, there must be an existing variable in the child package that the configuration can update.</span></span> <span data-ttu-id="4549c-110">Per altre informazioni sull'aggiunta e la configurazione di variabili, vedere [Aggiungere, eliminare o modificare l'ambito di una variabile definita dall'utente in un pacchetto](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).</span><span class="sxs-lookup"><span data-stu-id="4549c-110">For more information about adding and configuring variables, see [Add, Delete, Change Scope of User-Defined Variable in a Package](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).</span></span>  
  
 <span data-ttu-id="4549c-111">Come ambito per la variabile del pacchetto padre utilizzata nella configurazione di tipo Variabile pacchetto padre è possibile impostare l'attività Esegui pacchetto, il contenitore che include l'attività o il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="4549c-111">The scope of the variable in the parent package that is used in a parent variable configuration can be set to the Execute Package task, to the container that has the task, or to the package.</span></span> <span data-ttu-id="4549c-112">Se in uno stesso pacchetto sono definite più variabili con lo stesso nome, verrà utilizzata quella con ambito più vicino all'attività Esegui pacchetto.</span><span class="sxs-lookup"><span data-stu-id="4549c-112">If multiple variables with the same name are defined in a package, the variable that is closest in scope to the Execute Package task is used.</span></span> <span data-ttu-id="4549c-113">L'ambito più vicino all'attività Esegui pacchetto è l'attività stessa.</span><span class="sxs-lookup"><span data-stu-id="4549c-113">The closest scope to the Execute Package task is the task itself.</span></span>  
  
### <a name="to-add-a-variable-to-a-parent-package"></a><span data-ttu-id="4549c-114">Per aggiungere una variabile a un pacchetto padre</span><span class="sxs-lookup"><span data-stu-id="4549c-114">To add a variable to a parent package</span></span>  
  
1.  <span data-ttu-id="4549c-115">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenente il pacchetto a cui si desidera aggiungere una variabile da passare a un pacchetto figlio.</span><span class="sxs-lookup"><span data-stu-id="4549c-115">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package to which you want to add a variable to pass to a child package.</span></span>  
  
2.  <span data-ttu-id="4549c-116">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="4549c-116">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="4549c-117">In Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] eseguire una delle operazioni seguenti per definire l'ambito della variabile:</span><span class="sxs-lookup"><span data-stu-id="4549c-117">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, to define the scope of the variable, do one of the following:</span></span>  
  
    -   <span data-ttu-id="4549c-118">Per impostare il pacchetto come ambito, fare clic in un punto qualsiasi dell'area di progettazione della scheda **Flusso di controllo** .</span><span class="sxs-lookup"><span data-stu-id="4549c-118">To set the scope to the package, click anywhere on the design surface of the **Control Flow** tab.</span></span>  
  
    -   <span data-ttu-id="4549c-119">Per impostare come ambito un contenitore padre dell'attività Esegui pacchetto, fare clic sul contenitore.</span><span class="sxs-lookup"><span data-stu-id="4549c-119">To set the scope to a parent container of the Execute Package task, click the container.</span></span>  
  
    -   <span data-ttu-id="4549c-120">Per impostare l'ambito sull'attività Esegui pacchetto, fare clic sull'attività.</span><span class="sxs-lookup"><span data-stu-id="4549c-120">To set the scope to the Execute Package task, click the task.</span></span>  
  
4.  <span data-ttu-id="4549c-121">Aggiungere e configurare una variabile.</span><span class="sxs-lookup"><span data-stu-id="4549c-121">Add and configure a variable.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4549c-122">Selezionare un tipo di dati compatibile con i dati che verranno memorizzati nella variabile.</span><span class="sxs-lookup"><span data-stu-id="4549c-122">Select a data type that is compatible with the data that the variable will store.</span></span>  
  
5.  <span data-ttu-id="4549c-123">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="4549c-123">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-add-a-variable-to-a-child-package"></a><span data-ttu-id="4549c-124">Per aggiungere una variabile a un pacchetto figlio</span><span class="sxs-lookup"><span data-stu-id="4549c-124">To add a variable to a child package</span></span>  
  
1.  <span data-ttu-id="4549c-125">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenente il pacchetto a cui si vuole aggiungere una configurazione di variabile padre.</span><span class="sxs-lookup"><span data-stu-id="4549c-125">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package to which you want to add a parent variable configuration.</span></span>  
  
2.  <span data-ttu-id="4549c-126">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="4549c-126">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="4549c-127">In Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] , per impostare il pacchetto come ambito, fare clic in un punto qualsiasi dell'area di progettazione della scheda **Flusso di controllo** .</span><span class="sxs-lookup"><span data-stu-id="4549c-127">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, to set the scope to the package, click anywhere on the design surface of the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="4549c-128">Aggiungere e configurare una variabile.</span><span class="sxs-lookup"><span data-stu-id="4549c-128">Add and configure a variable.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4549c-129">Selezionare un tipo di dati compatibile con i dati che verranno memorizzati nella variabile.</span><span class="sxs-lookup"><span data-stu-id="4549c-129">Select a data type that is compatible with the data that the variable will store.</span></span>  
  
5.  <span data-ttu-id="4549c-130">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="4549c-130">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-add-a-parent-package-configuration-to-a-child-package"></a><span data-ttu-id="4549c-131">Per aggiungere a un pacchetto figlio una configurazione di tipo Variabile pacchetto padre</span><span class="sxs-lookup"><span data-stu-id="4549c-131">To add a parent package configuration to a child package</span></span>  
  
1.  <span data-ttu-id="4549c-132">Se necessario, aprire il pacchetto figlio in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4549c-132">If it is not already open, open the child package in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="4549c-133">Fare clic in un punto qualsiasi dell'area di progettazione della scheda **Flusso di controllo** .</span><span class="sxs-lookup"><span data-stu-id="4549c-133">Click anywhere on the design surface of the **Control Flow** tab.</span></span>  
  
3.  <span data-ttu-id="4549c-134">Scegliere **Configurazioni pacchetto** dal menu **SSIS**.</span><span class="sxs-lookup"><span data-stu-id="4549c-134">On the **SSIS** menu, click **Package Configurations**.</span></span>  
  
4.  <span data-ttu-id="4549c-135">Nella finestra di dialogo **Libreria configurazioni pacchetto** selezionare **Abilita configurazioni pacchetto**e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="4549c-135">In the **Package Configuration Organizer** dialog box, select **Enable package configuration**, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="4549c-136">Nella pagina iniziale della configurazione guidata pacchetto fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="4549c-136">On the welcome page of the Package Configuration Wizard, click **Next.**</span></span>  
  
6.  <span data-ttu-id="4549c-137">Nella pagina Selezione tipo di configurazione selezionare **Variabile pacchetto padre** nell'elenco **Tipo configurazione** ed eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4549c-137">On the Select Configuration Type page, in the **Configuration type** list, select **Parent package variable** and do one of the following:</span></span>  
  
    -   <span data-ttu-id="4549c-138">Selezionare **Usa le impostazioni di configurazione specificate di seguito**e quindi specificare nella casella **Variabile padre** il nome della variabile del pacchetto padre da usare nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="4549c-138">Select **Specify configuration settings directly**, and then in the **Parent variable** box, provide the name of the variable in the parent package to use in the configuration.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="4549c-139">Per i nomi delle variabili viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="4549c-139">Variable names are case sensitive.</span></span>  
  
    -   <span data-ttu-id="4549c-140">Selezionare **Percorso della configurazione memorizzato in una variabile di ambiente** e quindi selezionare nell'elenco **Variabile di ambiente**la variabile di ambiente che contiene il nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="4549c-140">Select or **Configuration location is stored in an environment variable,** and then in the **Environment variable list**, select the environmentvariable that contains the name of the variable.</span></span>  
  
7.  <span data-ttu-id="4549c-141">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4549c-141">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="4549c-142">Nella pagina Selezione proprietà di destinazione espandere il nodo **Variabile** , espandere il nodo **Proprietà** della variabile da configurare e quindi fare clic sulla proprietà che deve essere impostata dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="4549c-142">On the Select Target Property page, expand the **Variable** node, and expand the **Properties** node of the variable to configure, and then click the property to be set by the configuration.</span></span>  
  
9. <span data-ttu-id="4549c-143">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4549c-143">Click **Next**.</span></span>  
  
10. <span data-ttu-id="4549c-144">Nella pagina Completamento procedura guidata modificare facoltativamente il nome predefinito della configurazione e verificare le informazioni relative alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="4549c-144">On the Completing the Wizard page, optionally, modify the default name of the configuration and review the configuration information.</span></span>  
  
11. <span data-ttu-id="4549c-145">Scegliere **Fine** per completare la procedura guidata e tornare alla finestra di dialogo **Libreria configurazioni pacchetto** .</span><span class="sxs-lookup"><span data-stu-id="4549c-145">Click **Finish** to complete the wizard and return to the **Package Configuration Organizer** dialog box.</span></span>  
  
12. <span data-ttu-id="4549c-146">Nella finestra di dialogo **Libreria configurazioni pacchetto** la nuova configurazione è elencata nella casella **Configurazione** .</span><span class="sxs-lookup"><span data-stu-id="4549c-146">In the **Package Configuration Organizer** dialog box, the **Configuration** box lists the new configuration.</span></span>  
  
13. <span data-ttu-id="4549c-147">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="4549c-147">Click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4549c-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4549c-148">See Also</span></span>  
 <span data-ttu-id="4549c-149">[Configurazioni di pacchetti](../../2014/integration-services/package-configurations.md) </span><span class="sxs-lookup"><span data-stu-id="4549c-149">[Package Configurations](../../2014/integration-services/package-configurations.md) </span></span>  
 <span data-ttu-id="4549c-150">[Creazione di configurazioni di pacchetto](../../2014/integration-services/create-package-configurations.md) </span><span class="sxs-lookup"><span data-stu-id="4549c-150">[Create Package Configurations](../../2014/integration-services/create-package-configurations.md) </span></span>  
 <span data-ttu-id="4549c-151">[Variabili di Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="4549c-151">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 [<span data-ttu-id="4549c-152">Usare variabili nei pacchetti</span><span class="sxs-lookup"><span data-stu-id="4549c-152">Use Variables in Packages</span></span>](../../2014/integration-services/use-variables-in-packages.md)  
  
  
