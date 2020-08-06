---
title: 'Passaggio 2: Aggiunta e configurazione del contenitore Ciclo Foreach | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 88a973cc-0f23-4ecf-adb6-5b06279c2df6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: de5e8875c43edda618ccef4839c88c3b84a003cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624823"
---
# <a name="step-2-adding-and-configuring-the-foreach-loop-container"></a><span data-ttu-id="43d01-102">Passaggio 2: Aggiunta e configurazione del contenitore Ciclo Foreach</span><span class="sxs-lookup"><span data-stu-id="43d01-102">Step 2: Adding and Configuring the Foreach Loop Container</span></span>
  <span data-ttu-id="43d01-103">In questa attività verrà aggiunta la capacità di creare un ciclo in una cartella di file flat e applicare la stessa trasformazione del flusso di dati utilizzata nella lezione 1 a ognuno di questi file flat.</span><span class="sxs-lookup"><span data-stu-id="43d01-103">In this task, you will add the ability to loop through a folder of flat files and apply the same data flow transformation used in Lesson 1 to each of those flat files.</span></span> <span data-ttu-id="43d01-104">Ciò si ottiene tramite l'aggiunta e la configurazione di un contenitore Ciclo Foreach al flusso di controllo.</span><span class="sxs-lookup"><span data-stu-id="43d01-104">You do this by adding and configuring a Foreach Loop container to the control flow.</span></span>  
  
 <span data-ttu-id="43d01-105">Il contenitore Ciclo Foreach che si aggiunge deve essere in grado di collegarsi a ogni file flat della cartella.</span><span class="sxs-lookup"><span data-stu-id="43d01-105">The Foreach Loop container that you add must be able to connect to each flat file in the folder.</span></span> <span data-ttu-id="43d01-106">Dal momento che tutti i file della cartella hanno lo stesso formato, il contenitore Ciclo Foreach può utilizzare la stessa gestione connessione file flat per la connessione a tali file.</span><span class="sxs-lookup"><span data-stu-id="43d01-106">Because all the files in the folder have the same format, the Foreach Loop container can use the same Flat File connection manager to connect to each of these files.</span></span> <span data-ttu-id="43d01-107">La gestione connessione file flat utilizzata dal contenitore è la stessa creata nella lezione 1.</span><span class="sxs-lookup"><span data-stu-id="43d01-107">The Flat File connection manager that the container will use is the same Flat File connection manager that you created in Lesson 1.</span></span>  
  
 <span data-ttu-id="43d01-108">Al momento, la gestione connessione file flat della lezione 1 si connette a un solo file flat specifico.</span><span class="sxs-lookup"><span data-stu-id="43d01-108">Currently, the Flat File connection manager from Lesson 1 connects to only one, specific flat file.</span></span> <span data-ttu-id="43d01-109">Per ottenere la connessione in modo iterativo a ogni file flat della cartella, sarà necessario configurare il contenitore Ciclo Foreach e la gestione connessione file flat come segue:</span><span class="sxs-lookup"><span data-stu-id="43d01-109">To iteratively connect to each flat file in the folder, you will have to configure both the Foreach Loop container and the Flat File connection manager as follows:</span></span>  
  
-   <span data-ttu-id="43d01-110">**Contenitore Ciclo Foreach:** sul valore enumerato del contenitore verrà eseguito il mapping a una variabile di pacchetto definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="43d01-110">**Foreach Loop container:** You will map the enumerated value of the container to a user-defined package variable.</span></span> <span data-ttu-id="43d01-111">Il contenitore utilizzerà poi questa variabile definita dall'utente per modificare in modo dinamico la proprietà `ConnectionString` della gestione connessione file flat e connettersi in modo iterativo a ogni file flat della cartella.</span><span class="sxs-lookup"><span data-stu-id="43d01-111">The container will then use this user-defined variable to dynamically modify the `ConnectionString` property of the Flat File connection manager and iteratively connect to each flat file in the folder.</span></span>  
  
-   <span data-ttu-id="43d01-112">**Gestione connessione file flat:** La gestione connessione creata nella lezione 1 sarà modificata utilizzando una variabile definita dall'utente per popolare la proprietà della gestione connessione `ConnectionString` .</span><span class="sxs-lookup"><span data-stu-id="43d01-112">**Flat File connection manager:** You will modify the connection manager that was created in Lesson 1 by using a user-defined variable to populate the connection manager's `ConnectionString` property.</span></span>  
  
 <span data-ttu-id="43d01-113">Le procedure di questa attività mostrano come creare e modificare il contenitore Ciclo Foreach per utilizzare una variabile di pacchetto definita dall'utente ed aggiungere l'attività flusso di dati al ciclo.</span><span class="sxs-lookup"><span data-stu-id="43d01-113">The procedures in this task show you how to create and modify the Foreach Loop container to use a user-defined package variable and to add the data flow task to the loop.</span></span> <span data-ttu-id="43d01-114">Si imparerà a modificare la gestione connessione file flat per utilizzare una variabile definita dall'utente nella successiva attività.</span><span class="sxs-lookup"><span data-stu-id="43d01-114">You will learn how to modify the Flat File connection manager to use a user-defined variable in the next task.</span></span>  
  
 <span data-ttu-id="43d01-115">Dopo aver apportato tali modifiche al pacchetto, quando questo viene eseguito, il contenitore Ciclo Foreach si ripete attraverso la raccolta di dati nella cartella Sample Data.</span><span class="sxs-lookup"><span data-stu-id="43d01-115">After you have made these modifications to the package, when the package is run, the Foreach Loop Container will iterate through the collection of files in the Sample Data folder.</span></span> <span data-ttu-id="43d01-116">Ogni volta che viene individuato un file che corrisponde ai criteri, il contenitore Ciclo Foreach popola la variabile definita dall'utente con il nome file, esegue il mapping della variabile definita dall'utente alla proprietà `ConnectionString` della gestione connessione file flat SampleCurrency Data e quindi esegue il flusso di dati su tale file.</span><span class="sxs-lookup"><span data-stu-id="43d01-116">Each time a file is found that matches the criteria, the Foreach Loop Container will populate the user-defined variable with the file name, map the user-defined variable to the `ConnectionString` property of the Sample Currency Data Flat File connection manager, and then run the data flow against that file.</span></span> <span data-ttu-id="43d01-117">Di conseguenza, in ogni iterazione del Ciclo Foreach, l'attività Flusso di dati consuma un file flat diverso.</span><span class="sxs-lookup"><span data-stu-id="43d01-117">Therefore, in each iteration of the Foreach Loop the Data Flow task will consume a different flat file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="43d01-118">Dal momento che [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] separa il flusso di controllo dal flusso dei dati, i cicli aggiunti al flusso di controllo non richiedono la modifica del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="43d01-118">Because [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] separates control flow from data flow, any looping that you add to the control flow will not require modification to the data flow.</span></span> <span data-ttu-id="43d01-119">Di conseguenza, non è necessario modificare il flusso di dati creato nella lezione 1.</span><span class="sxs-lookup"><span data-stu-id="43d01-119">Therefore, the data flow that you created in Lesson 1 does not have to be changed.</span></span>  
  
### <a name="to-add-a-foreach-loop-container"></a><span data-ttu-id="43d01-120">Per aggiungere un contenitore Ciclo Foreach</span><span class="sxs-lookup"><span data-stu-id="43d01-120">To add a Foreach Loop container</span></span>  
  
1.  <span data-ttu-id="43d01-121">In **SQL Server Data Tools**fare clic sulla scheda **Flusso di controllo** .</span><span class="sxs-lookup"><span data-stu-id="43d01-121">In **SQL Server Data Tools**, click the **Control Flow** tab.</span></span>  
  
2.  <span data-ttu-id="43d01-122">Nella **Casella degli strumenti SSIS**espandere **Contenitori**, quindi trascinare **Contenitore Ciclo Foreach** sulla superficie di progettazione della scheda **Flusso di controllo** .</span><span class="sxs-lookup"><span data-stu-id="43d01-122">In the **SSIS Toolbox**, expand **Containers**, and then drag a **Foreach Loop Container** onto the design surface of the **Control Flow** tab.</span></span>  
  
3.  <span data-ttu-id="43d01-123">Fare clic con il pulsante destro del mouse sul **Contenitore Ciclo Foreach** appena aggiunto e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="43d01-123">Right-click the newly added **Foreach Loop Container** and select **Edit**.</span></span>  
  
4.  <span data-ttu-id="43d01-124">Nella finestra di dialogo **Editor ciclo foreach** , nella pagina **generale** , in **nome**immettere `Foreach File in Folder` .</span><span class="sxs-lookup"><span data-stu-id="43d01-124">In the **Foreach Loop Editor** dialog box, on the **General** page, for **Name**, enter `Foreach File in Folder`.</span></span> <span data-ttu-id="43d01-125">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="43d01-125">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="43d01-126">Fare clic con il pulsante destro del mouse sul contenitore ciclo foreach, scegliere **Proprietà**e nella finestra Proprietà verificare che la `LocaleID` proprietà sia impostata su **inglese (Stati Uniti)**.</span><span class="sxs-lookup"><span data-stu-id="43d01-126">Right-click the Foreach Loop container, click **Properties**, and in the Properties window, verify that the `LocaleID` property is set to **English (United States)**.</span></span>  
  
### <a name="to-configure-the-enumerator-for-the-foreach-loop-container"></a><span data-ttu-id="43d01-127">Per configurare l'enumeratore per il contenitore Ciclo Foreach</span><span class="sxs-lookup"><span data-stu-id="43d01-127">To configure the enumerator for the Foreach Loop container</span></span>  
  
1.  <span data-ttu-id="43d01-128">Fare doppio clic su Foreach File in Folder per riaprire l'**Editor ciclo Foreach**.</span><span class="sxs-lookup"><span data-stu-id="43d01-128">Double-click Foreach File in Folder to reopen the **Foreach Loop Editor**.</span></span>  
  
2.  <span data-ttu-id="43d01-129">Fare clic su **Raccolta**.</span><span class="sxs-lookup"><span data-stu-id="43d01-129">Click **Collection**.</span></span>  
  
3.  <span data-ttu-id="43d01-130">Nella pagina **Raccolta** selezionare **Enumeratore Foreach File**.</span><span class="sxs-lookup"><span data-stu-id="43d01-130">On the **Collection** page, select **Foreach File Enumerator**.</span></span>  
  
4.  <span data-ttu-id="43d01-131">Nel gruppo **Configurazione enumeratore** fare clic su **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="43d01-131">In the **Enumerator configuration** group, click **Browse**.</span></span>  
  
5.  <span data-ttu-id="43d01-132">Nella finestra di dialogo **Sfoglia per cartelle** individuare nel computer la cartella contenente i file Currency_\*.txt.</span><span class="sxs-lookup"><span data-stu-id="43d01-132">In the **Browse for Folder** dialog box, locate the folder on your machine that contains the Currency_\*.txt files.</span></span>  
  
     <span data-ttu-id="43d01-133">Questi dati di esempio sono inclusi nei pacchetti di lezioni di [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="43d01-133">This sample data is included with the [!INCLUDE[ssIS](../includes/ssis-md.md)] lesson packages.</span></span> <span data-ttu-id="43d01-134">Per scaricare i dati di esempio e i pacchetti di lezioni, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="43d01-134">To download the sample data and the lesson packages, do the following.</span></span>  
  
    1.  <span data-ttu-id="43d01-135">Passare alla pagina relativa agli [esempi di prodotti di Integration Services](https://go.microsoft.com/fwlink/?LinkId=275027)</span><span class="sxs-lookup"><span data-stu-id="43d01-135">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="43d01-136">Fare clic sulla scheda **Downloads** .</span><span class="sxs-lookup"><span data-stu-id="43d01-136">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="43d01-137">Fare clic sul collegamento ipertestuale " https://msftisprodsamples.codeplex.com/downloads/get/578097 " SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span><span class="sxs-lookup"><span data-stu-id="43d01-137">Click the  HYPERLINK "https://msftisprodsamples.codeplex.com/downloads/get/578097" SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
6.  <span data-ttu-id="43d01-138">Nella casella **File** digitare **Currency_\*.txt**.</span><span class="sxs-lookup"><span data-stu-id="43d01-138">In the **Files** box, type **Currency_\*.txt**.</span></span>  
  
### <a name="to-map-the-enumerator-to-a-user-defined-variable"></a><span data-ttu-id="43d01-139">Per eseguire il mapping dell'enumeratore a una variabile definita dall'utente</span><span class="sxs-lookup"><span data-stu-id="43d01-139">To map the enumerator to a user-defined variable</span></span>  
  
1.  <span data-ttu-id="43d01-140">Fare clic su **Mapping variabili**.</span><span class="sxs-lookup"><span data-stu-id="43d01-140">Click **Variable Mappings**.</span></span>  
  
2.  <span data-ttu-id="43d01-141">Nella colonna **variabile** della pagina **Mapping variabili** fare clic sulla cella vuota e selezionare **\<New Variable...>** .</span><span class="sxs-lookup"><span data-stu-id="43d01-141">On the **Variable Mappings** page, in the **Variable** column, click the empty cell and select **\<New Variable...>**.</span></span>  
  
3.  <span data-ttu-id="43d01-142">Nella finestra di dialogo **Aggiungi variabile** Digitare per **nome** `varFileName` .</span><span class="sxs-lookup"><span data-stu-id="43d01-142">In the **Add Variable** dialog box, for **Name**, type `varFileName`.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="43d01-143">Per i nomi delle variabili viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="43d01-143">Variable names are case sensitive.</span></span>  
  
4.  <span data-ttu-id="43d01-144">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="43d01-144">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="43d01-145">Fare di nuovo clic su **OK** per chiudere la finestra di dialogo **Editor ciclo Foreach** .</span><span class="sxs-lookup"><span data-stu-id="43d01-145">Click **OK** again to exit the **Foreach Loop Editor** dialog box.</span></span>  
  
### <a name="to-add-the-data-flow-task-to-the-loop"></a><span data-ttu-id="43d01-146">Per aggiungere le attività flusso di dati al ciclo</span><span class="sxs-lookup"><span data-stu-id="43d01-146">To add the data flow task to the loop</span></span>  
  
-   <span data-ttu-id="43d01-147">Trascinare l'attività **Estrai** dati di valuta di esempio flusso di dati nel contenitore ciclo foreach ora rinominata `Foreach File in Folder` .</span><span class="sxs-lookup"><span data-stu-id="43d01-147">Drag the **Extract Sample Currency Data** data flow task onto the Foreach Loop container now renamed `Foreach File in Folder`.</span></span>  
  
## <a name="next-lesson-task"></a><span data-ttu-id="43d01-148">Attività della lezione successiva</span><span class="sxs-lookup"><span data-stu-id="43d01-148">Next Lesson Task</span></span>  
 [<span data-ttu-id="43d01-149">Passaggio 3: Modifica della gestione connessione file flat</span><span class="sxs-lookup"><span data-stu-id="43d01-149">Step 3: Modifying the Flat File Connection Manager</span></span>](lesson-2-3-modifying-the-flat-file-connection-manager.md)  
  
## <a name="see-also"></a><span data-ttu-id="43d01-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43d01-150">See Also</span></span>  
 <span data-ttu-id="43d01-151">[Configurare un contenitore ciclo foreach](control-flow/foreach-loop-container.md) </span><span class="sxs-lookup"><span data-stu-id="43d01-151">[Configure a Foreach Loop Container](control-flow/foreach-loop-container.md) </span></span>  
 [<span data-ttu-id="43d01-152">Usare variabili nei pacchetti</span><span class="sxs-lookup"><span data-stu-id="43d01-152">Use Variables in Packages</span></span>](use-variables-in-packages.md)  
  
