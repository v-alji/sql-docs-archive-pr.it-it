---
title: 'Passaggio 2: Abilitazione e impostazione delle configurazioni dei pacchetti | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 005218ab-8dd5-48e9-a185-6bc60cd43a7a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a804efcd84ebe563a13f61443fe19096788ca809
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626142"
---
# <a name="step-2-enabling-and-configuring-package-configurations"></a><span data-ttu-id="0a9b5-102">Passaggio 2: Abilitazione e impostazione delle configurazioni dei pacchetti</span><span class="sxs-lookup"><span data-stu-id="0a9b5-102">Step 2: Enabling and Configuring Package Configurations</span></span>
  <span data-ttu-id="0a9b5-103">In questa attività si convertirà il progetto nel modello di distribuzione del pacchetto e si abiliteranno le configurazioni di pacchetto utilizzando la Configurazione guidata pacchetto.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-103">In this task, you will convert the project to the Package Deployment Model and enable package configurations using the Package Configuration Wizard.</span></span> <span data-ttu-id="0a9b5-104">Questa procedura guidata consente di generare un file di configurazione XML contenente le impostazioni di configurazione per la proprietà `Directory` del contenitore Ciclo Foreach.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-104">You will use this wizard to generate an XML configuration file that contains configuration settings for the `Directory` property of the Foreach Loop container.</span></span> <span data-ttu-id="0a9b5-105">Il valore della proprietà Directory è specificato da una variabile a livello di pacchetto che è possibile aggiornare in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-105">The value of the Directory property is supplied by a new package-level variable that you can update at run time.</span></span> <span data-ttu-id="0a9b5-106">Verrà inoltre popolata una cartella di dati di esempio da utilizzare durante il test.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-106">Additionally, you will populate a new sample data folder to use during testing.</span></span>  
  
### <a name="to-create-a-new-package-level-variable-mapped-to-the-directory-property"></a><span data-ttu-id="0a9b5-107">Per creare una nuova variabile a livello di pacchetto associata alla proprietà Directory</span><span class="sxs-lookup"><span data-stu-id="0a9b5-107">To create a new package-level variable mapped to the Directory property</span></span>  
  
1.  <span data-ttu-id="0a9b5-108">Fare clic sullo sfondo della scheda **Flusso di controllo** in Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0a9b5-108">Click the background of the **Control Flow** tab in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="0a9b5-109">In questo modo viene impostato l'ambito del pacchetto per la variabile che verrà creata.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-109">This sets the scope for the variable you will create to the package.</span></span>  
  
2.  <span data-ttu-id="0a9b5-110">Scegliere [!INCLUDE[ssIS](../includes/ssis-md.md)] Variabili **dal menu**.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-110">On the [!INCLUDE[ssIS](../includes/ssis-md.md)] menu, select **Variables**.</span></span>  
  
3.  <span data-ttu-id="0a9b5-111">Nella finestra **Variabili** fare clic sull'icona Aggiungi variabile.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-111">In the **Variables** window, click the Add Variable icon.</span></span>  
  
4.  <span data-ttu-id="0a9b5-112">Nella casella **Nome** digitare **varFolderName**.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-112">In the **Name** box, type **varFolderName**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="0a9b5-113">Per i nomi delle variabili viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-113">Variable names are case sensitive.</span></span>  
  
5.  <span data-ttu-id="0a9b5-114">Verificare che nella casella **ambito** sia visualizzato il nome del pacchetto, Lesson 5.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-114">Verify that the **Scope** box shows the name of the package, Lesson 5.</span></span>  
  
6.  <span data-ttu-id="0a9b5-115">Impostare su **String** il valore della casella `varFolderName` Tipo di dati **della variabile**.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-115">Set the value of the **Data Type** box of the `varFolderName` variable to **String**.</span></span>  
  
7.  <span data-ttu-id="0a9b5-116">Tornare alla scheda **Flusso di controllo** e fare doppio clic sul contenitore **Foreach File in Folder** .</span><span class="sxs-lookup"><span data-stu-id="0a9b5-116">Return to the **Control Flow** tab and double-click the **Foreach File in Folder** container.</span></span>  
  
8.  <span data-ttu-id="0a9b5-117">Nella pagina **Raccolta** di **Editor ciclo Foreach** fare clic su **Espressioni** e quindi sul pulsante con i puntini di sospensione **(...)**.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-117">On the **Collection** page of the **Foreach Loop Editor**, click **Expressions**, and then click the ellipsis button **(...)**.</span></span>  
  
9. <span data-ttu-id="0a9b5-118">Nell' **Editor espressioni di proprietà**fare clic nell'elenco **Proprietà** e selezionare `Directory` .</span><span class="sxs-lookup"><span data-stu-id="0a9b5-118">In the **Property Expressions Editor**, click in the **Property** list, and select `Directory`.</span></span>  
  
10. <span data-ttu-id="0a9b5-119">Nella casella **espressione** fare clic sul pulsante con i puntini di sospensione **(...)**.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-119">In the **Expression** box, click the ellipsis button **(...)**.</span></span>  
  
11. <span data-ttu-id="0a9b5-120">In **Generatore di espressioni**espandere la cartella Variabili e trascinare la variabile **User::varFolderName** nella casella **Espressione** .</span><span class="sxs-lookup"><span data-stu-id="0a9b5-120">In the **Expression Builder**, expand the Variables folder, and drag the variable **User::varFolderName** to the **Expression** box.</span></span>  
  
12. <span data-ttu-id="0a9b5-121">Fare clic su **OK** per chiudere **Generatore di espressioni**.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-121">Click **OK** to exit the **Expression Builder**.</span></span>  
  
13. <span data-ttu-id="0a9b5-122">Fare clic su **OK** per chiudere **Editor espressioni di proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-122">Click **OK** to exit the **Property Expressions Editor**.</span></span>  
  
14. <span data-ttu-id="0a9b5-123">Fare clic su **OK** per uscire da **Editor ciclo Foreach**.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-123">Click **OK** to exit the **Foreach Loop Editor**.</span></span>  
  
### <a name="to-enable-package-configurations"></a><span data-ttu-id="0a9b5-124">Per abilitare le configurazioni dei pacchetti</span><span class="sxs-lookup"><span data-stu-id="0a9b5-124">To enable package configurations</span></span>  
  
1.  <span data-ttu-id="0a9b5-125">Scegliere **Converti nel modello di distribuzione del pacchetto**dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-125">On the **Project Menu**, click **Convert to Package Deployment Model**.</span></span>  
  
2.  <span data-ttu-id="0a9b5-126">Fare clic su **OK** nella richiesta di avviso e, una volta completata la conversione, scegliere **OK** nella finestra di dialogo **Converti nel modello di distribuzione del pacchetto** .</span><span class="sxs-lookup"><span data-stu-id="0a9b5-126">Click **OK** on the warning prompt and, once the conversion is complete, click **OK** on the **Convert to Package Deployment Model** dialog.</span></span>  
  
3.  <span data-ttu-id="0a9b5-127">Fare clic sullo sfondo della scheda **Flusso di controllo** in Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0a9b5-127">Click the background of the **Control Flow** tab in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
4.  <span data-ttu-id="0a9b5-128">Scegliere **Configurazioni pacchetto** dal menu **SSIS**.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-128">On the **SSIS** menu, click **Package Configurations**.</span></span>  
  
5.  <span data-ttu-id="0a9b5-129">Nella finestra di dialogo **Libreria configurazioni pacchetto** selezionare **Abilita configurazioni pacchetto**e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-129">In the **Package Configurations Organizer** dialog box, select **Enable Package Configurations**, and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="0a9b5-130">Nella pagina iniziale di Configurazione guidata pacchetto fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-130">On the welcome page of the Package Configuration Wizard, click **Next**.</span></span>  
  
7.  <span data-ttu-id="0a9b5-131">Nella pagina **Selezione tipo di configurazione** verificare che l'opzione **Tipo configurazione** sia impostata su **File di configurazione XML**.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-131">On the **Select Configuration Type** page, verify that the **Configuration type** is set to **XML configuration file**.</span></span>  
  
8.  <span data-ttu-id="0a9b5-132">Nella pagina **Selezione tipo di configurazione** fare clic su **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-132">On the **Select Configuration Type** page, click **Browse**.</span></span>  
  
9. <span data-ttu-id="0a9b5-133">Per impostazione predefinita, nella finestra di dialogo **Selezionare il percorso del file di configurazione** verrà visualizzata la cartella del progetto.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-133">By default, the **Select Configuration File Location** dialog box will open to the project folder.</span></span>  
  
10. <span data-ttu-id="0a9b5-134">Nella finestra di dialogo **Selezionare il percorso del file di configurazione** digitare **SSISTutorial** nel campo **Nome file**e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-134">In the **Select Configuration File Location** dialog box, for **File name** type **SSISTutorial**, and then click **Save**.</span></span>  
  
11. <span data-ttu-id="0a9b5-135">Nella pagina **Selezione tipo di configurazione** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-135">On the **Select Configuration Type** page, click **Next.**</span></span>  
  
12. <span data-ttu-id="0a9b5-136">Nel riquadro **oggetti** della pagina **Selezione proprietà da esportare** espandere **variabili**, espandere **VarFolderName**, espandere **Proprietà**, quindi selezionare **valore**.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-136">On the **Select Properties to Export** page, in the **Objects** pane, expand **Variables**, expand **varFolderName**, expand **Properties**, and then select **Value**.</span></span>  
  
13. <span data-ttu-id="0a9b5-137">Nella pagina **Selezione proprietà da esportare** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-137">On the **Select Properties to Export** page, click **Next**.</span></span>  
  
14. <span data-ttu-id="0a9b5-138">Nella pagina **Completamento procedura guidata** digitare un nome per la configurazione, ad esempio **SSIS Tutorial Directory configuration**.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-138">On the **Completing the Wizard** page, type a configuration name for the configuration, such as **SSIS Tutorial Directory configuration**.</span></span> <span data-ttu-id="0a9b5-139">Si tratta del nome della configurazione visualizzato nella finestra di dialogo **Libreria configurazioni pacchetto** .</span><span class="sxs-lookup"><span data-stu-id="0a9b5-139">This is the configuration name that is displayed in the **Package Configuration Organizer** dialog box.</span></span>  
  
15. <span data-ttu-id="0a9b5-140">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-140">Click **Finish**.</span></span>  
  
16. <span data-ttu-id="0a9b5-141">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-141">Click **Close**.</span></span>  
  
17. <span data-ttu-id="0a9b5-142">La procedura guidata crea un file di configurazione denominato SSISTutorial. dtsConfig che contiene le impostazioni di configurazione per `value` della variabile che a sua volta imposta la `Directory` proprietà dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-142">The wizard creates a configuration file, named SSISTutorial.dtsConfig, that contains configuration settings for the `value` of the variable that in turn sets the `Directory` property of the enumerator.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0a9b5-143">In un file di configurazione in genere sono incluse informazioni complesse sulle proprietà del pacchetto; tuttavia per questa esercitazione le uniche informazioni di configurazione saranno</span><span class="sxs-lookup"><span data-stu-id="0a9b5-143">A configuration file typically contains complex information about the package properties, but for this tutorial the only configuration information should be</span></span>  
    > <span data-ttu-id="0a9b5-144"><Configuration ConfiguredType="Property"</span><span class="sxs-lookup"><span data-stu-id="0a9b5-144"><Configuration ConfiguredType="Property"</span></span>  
    > <span data-ttu-id="0a9b5-145">Path = "\Pacchetto.variabili [user:: varFolderName]. Properties [valore] "ValueType =" stringa "\></span><span class="sxs-lookup"><span data-stu-id="0a9b5-145">Path="\Package.Variables[User::varFolderName].Properties[Value]" ValueType="String"\></span></span>  
    >  \<ConfiguredValue>\</ConfiguredValue>  
    > <span data-ttu-id="0a9b5-146">\</Configuration>.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-146">\</Configuration>.</span></span>  
  
### <a name="to-create-and-populate-a-new-sample-data-folder"></a><span data-ttu-id="0a9b5-147">Per creare e popolare una nuova cartella di dati di esempio</span><span class="sxs-lookup"><span data-stu-id="0a9b5-147">To create and populate a new sample data folder</span></span>  
  
1.  <span data-ttu-id="0a9b5-148">In Esplora risorse, al livello radice dell'unità (ad esempio, C: \\ ), creare una nuova cartella denominata `New Sample Data` .</span><span class="sxs-lookup"><span data-stu-id="0a9b5-148">In Windows Explorer, at the root level of your drive (for example, C:\\), create a new folder named `New Sample Data`.</span></span>  
  
2.  <span data-ttu-id="0a9b5-149">Individuare i file di esempio nel computer e copiare tre dei file nella cartella.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-149">Locate the sample files on your computer and copy three of the files from the folder.</span></span>  
  
3.  <span data-ttu-id="0a9b5-150">`New Sample Data`Incollare i file copiati nella cartella.</span><span class="sxs-lookup"><span data-stu-id="0a9b5-150">In the `New Sample Data` folder, paste the copied files.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="0a9b5-151">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="0a9b5-151">Next Task in Lesson</span></span>  
 [<span data-ttu-id="0a9b5-152">Passaggio 3: Modifica del valore di configurazione della proprietà Directory</span><span class="sxs-lookup"><span data-stu-id="0a9b5-152">Step 3: Modifying the Directory Property Configuration Value</span></span>](lesson-5-3-modifying-the-directory-property-configuration-value.md)  
  
  
