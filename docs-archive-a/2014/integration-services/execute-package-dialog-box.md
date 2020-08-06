---
title: Finestra di dialogo Esegui pacchetto | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.ispackageexecute.f1
- sql12.ssis.ssms.executepackage.f1
ms.assetid: 4f7a806d-4867-4d1f-bc65-b00c1caee7b6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1b60381054c781cd59f0a9d434710663b72d616c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629504"
---
# <a name="execute-package-dialog-box"></a><span data-ttu-id="ae4d5-102">Execute Package Dialog Box</span><span class="sxs-lookup"><span data-stu-id="ae4d5-102">Execute Package Dialog Box</span></span>
  <span data-ttu-id="ae4d5-103">Usare la finestra di dialogo **Esegui pacchetto** per eseguire un pacchetto archiviato nel server [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ae4d5-103">Use the **Execute Package** dialog box to run a package that is stored on the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span>  
  
 <span data-ttu-id="ae4d5-104">È possibile che in un pacchetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] siano contenuti i parametri con i valori archiviati nelle variabili di ambiente.</span><span class="sxs-lookup"><span data-stu-id="ae4d5-104">An [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package may contain parameters that values stored in environment variables.</span></span> <span data-ttu-id="ae4d5-105">Prima di eseguire tale pacchetto, è necessario specificare l'ambiente che sarà utilizzato per fornire i valori della variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="ae4d5-105">Before executing such a package, you must specify which environment will be used to provide the environment variable values.</span></span> <span data-ttu-id="ae4d5-106">Un progetto può contenere più ambienti, ma solo un ambiente può essere utilizzato per l'associazione di valori della variabile di ambiente al momento dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ae4d5-106">A project may contain multiple environments, but only one environment can be used for binding environment variable values at the time of execution.</span></span> <span data-ttu-id="ae4d5-107">Se nel pacchetto non viene utilizzata alcuna variabile di ambiente, non sarà necessario alcun ambiente.</span><span class="sxs-lookup"><span data-stu-id="ae4d5-107">If no environment variables are used in the package, an environment is not required.</span></span>  
  
 <span data-ttu-id="ae4d5-108">Per saperne di più</span><span class="sxs-lookup"><span data-stu-id="ae4d5-108">What do you want to do?</span></span>  
  
-   [<span data-ttu-id="ae4d5-109">Aprire la finestra di dialogo Esegui pacchetto</span><span class="sxs-lookup"><span data-stu-id="ae4d5-109">Open the Execute Package dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="ae4d5-110">Impostare le opzioni nella pagina Generale</span><span class="sxs-lookup"><span data-stu-id="ae4d5-110">Set the Options on the General page</span></span>](#general)  
  
-   [<span data-ttu-id="ae4d5-111">Impostare le opzioni nella scheda Parametri</span><span class="sxs-lookup"><span data-stu-id="ae4d5-111">Set the Options on the Parameters tab</span></span>](#parameters)  
  
-   [<span data-ttu-id="ae4d5-112">Impostare le opzioni nella scheda Gestioni connessioni</span><span class="sxs-lookup"><span data-stu-id="ae4d5-112">Set the Options on the Connection Managers tab</span></span>](#connection)  
  
-   [<span data-ttu-id="ae4d5-113">Impostare le opzioni nella scheda Avanzate</span><span class="sxs-lookup"><span data-stu-id="ae4d5-113">Set the Options on the Advanced tab</span></span>](#advanced)  
  
-   [<span data-ttu-id="ae4d5-114">Creazione di script per le opzioni contenute nella finestra di dialogo Esegui pacchetto</span><span class="sxs-lookup"><span data-stu-id="ae4d5-114">Scripting the Options in the Execute Package Dialog Box</span></span>](#script)  
  
##  <a name="open-the-execute-package-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="ae4d5-115">Aprire la finestra di dialogo Esegui pacchetto</span><span class="sxs-lookup"><span data-stu-id="ae4d5-115">Open the Execute Package dialog box</span></span>  
  
1.  <span data-ttu-id="ae4d5-116">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]connettersi al server [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ae4d5-116">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="ae4d5-117">Verrà eseguita la connessione all'istanza del [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] in cui è ospitato il database SSISDB.</span><span class="sxs-lookup"><span data-stu-id="ae4d5-117">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="ae4d5-118">In Esplora oggetti espandere l'albero per visualizzare il nodo dei **cataloghi di Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="ae4d5-118">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="ae4d5-119">Espandere il nodo **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="ae4d5-119">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="ae4d5-120">Espandere la cartella contenente il pacchetto che si desidera eseguire.</span><span class="sxs-lookup"><span data-stu-id="ae4d5-120">Expand the folder that contains the package you want to run.</span></span>  
  
5.  <span data-ttu-id="ae4d5-121">Fare clic con il pulsante destro del mouse sul pacchetto, quindi scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="ae4d5-121">Right-click the package, and then click **Execute**.</span></span>  
  
##  <a name="set-the-options-on-the-general-page"></a><a name="general"></a> <span data-ttu-id="ae4d5-122">Impostare le opzioni nella pagina Generale</span><span class="sxs-lookup"><span data-stu-id="ae4d5-122">Set the Options on the General page</span></span>  
 <span data-ttu-id="ae4d5-123">Selezionare **Ambiente** per specificare l'ambiente che viene applicato quando si esegue il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ae4d5-123">Select **Environment** to specify the environment that is applied with the package is run.</span></span>  
  
##  <a name="set-the-options-on-the-parameters-tab"></a><a name="parameters"></a> <span data-ttu-id="ae4d5-124">Impostare le opzioni nella scheda Parametri</span><span class="sxs-lookup"><span data-stu-id="ae4d5-124">Set the Options on the Parameters tab</span></span>  
 <span data-ttu-id="ae4d5-125">Usare la scheda **Parametri** per modificare i valori dei parametri usati quando si esegue il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ae4d5-125">Use the **Parameters** tab to modify the parameter values that are used when the package runs.</span></span>  
  
##  <a name="set-the-options-on-the-connection-managers-tab"></a><a name="connection"></a> <span data-ttu-id="ae4d5-126">Impostare le opzioni nella scheda Gestioni connessioni</span><span class="sxs-lookup"><span data-stu-id="ae4d5-126">Set the Options on the Connection Managers tab</span></span>  
 <span data-ttu-id="ae4d5-127">Utilizzare la scheda Gestione connessioni per impostare le proprietà della gestione connessione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ae4d5-127">Use the Connection Managers tab to set the properties of the package connection manager(s).</span></span>  
  
##  <a name="set-the-options-on-the-advanced-tab"></a><a name="advanced"></a> <span data-ttu-id="ae4d5-128">Impostare le opzioni nella scheda Avanzate</span><span class="sxs-lookup"><span data-stu-id="ae4d5-128">Set the Options on the Advanced tab</span></span>  
 <span data-ttu-id="ae4d5-129">Utilizzare la scheda Avanzate per gestire le proprietà e le altre impostazioni del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ae4d5-129">Use the Advanced tab to manage properties and other package settings.</span></span>  
  
 <span data-ttu-id="ae4d5-130">**Aggiungi**, **Modifica**, **Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="ae4d5-130">**Add**, **Edit**, **Remove**</span></span>  
 <span data-ttu-id="ae4d5-131">Selezionare queste opzioni per aggiungere, modificare o rimuovere una proprietà.</span><span class="sxs-lookup"><span data-stu-id="ae4d5-131">Click to add, edit, or remove a property.</span></span>  
  
 <span data-ttu-id="ae4d5-132">**Livello di registrazione**</span><span class="sxs-lookup"><span data-stu-id="ae4d5-132">**Logging level**</span></span>  
 <span data-ttu-id="ae4d5-133">Consente di selezionare il livello di registrazione per l'esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ae4d5-133">Select the logging level for the package execution.</span></span> <span data-ttu-id="ae4d5-134">Per altre informazioni, vedere [catalog.start_execution &#40;database SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="ae4d5-134">For more information, see [catalog.set_execution_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database).</span></span>  
  
 <span data-ttu-id="ae4d5-135">**Dump su errori**</span><span class="sxs-lookup"><span data-stu-id="ae4d5-135">**Dump on errors**</span></span>  
 <span data-ttu-id="ae4d5-136">Specificare se creare un file di dump quando si verifica un errore durante l'esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ae4d5-136">Specify whether a dump file is created when errors occur during the package execution.</span></span> <span data-ttu-id="ae4d5-137">Per altre informazioni, vedere [Generazione di file di dump per l'esecuzione del pacchetto](troubleshooting/generating-dump-files-for-package-execution.md).</span><span class="sxs-lookup"><span data-stu-id="ae4d5-137">For more information, see [Generating Dump Files for Package Execution](troubleshooting/generating-dump-files-for-package-execution.md).</span></span>  
  
 <span data-ttu-id="ae4d5-138">**Runtime a 32 bit**</span><span class="sxs-lookup"><span data-stu-id="ae4d5-138">**32-bit runtime**</span></span>  
 <span data-ttu-id="ae4d5-139">Specificare che il pacchetto verrà eseguito in un sistema a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="ae4d5-139">Specify that the package will execute on a 32-bit system.</span></span>  
  
##  <a name="scripting-the-options-in-the-execute-package-dialog-box"></a><a name="script"></a> <span data-ttu-id="ae4d5-140">Creazione di script per le opzioni contenute nella finestra di dialogo Esegui pacchetto</span><span class="sxs-lookup"><span data-stu-id="ae4d5-140">Scripting the Options in the Execute Package Dialog Box</span></span>  
 <span data-ttu-id="ae4d5-141">Mentre si è nella finestra di dialogo **Esegui pacchetto** , è inoltre possibile usare il pulsante **Script** nella barra degli strumenti per scrivere automaticamente codice [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ae4d5-141">While you are in the **Execute Package** dialog box, you can also use the **Script** button on the toolbar to write [!INCLUDE[tsql](../includes/tsql-md.md)] code for you.</span></span> <span data-ttu-id="ae4d5-142">Lo script generato chiama le stored procedure [catalog.start_execution &#40;database SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database) con le stesse opzioni selezionate nella finestra di dialogo **Esegui pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="ae4d5-142">The generated script calls the stored procedures [catalog.start_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database) with the same options that you have selected in the **Execute Package** dialog box.</span></span> <span data-ttu-id="ae4d5-143">Lo script verrà visualizzato in una nuova finestra dello script di [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae4d5-143">The script appears in a new script window in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
  
