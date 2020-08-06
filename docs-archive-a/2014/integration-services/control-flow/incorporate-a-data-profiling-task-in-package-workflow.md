---
title: Incorporare un'attività Profiling dati nel flusso di lavoro del pacchetto | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling task [Integration Services], using output in workflow
ms.assetid: 39a51586-6977-4c45-b80b-0157a54ad510
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cd3544586ac99f66b961f7961e4f4af4d9e4a4c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627335"
---
# <a name="incorporate-a-data-profiling-task-in-package-workflow"></a><span data-ttu-id="6b90d-102">Incorporamento di un'attività Profiling dati nel flusso di lavoro del pacchetto</span><span class="sxs-lookup"><span data-stu-id="6b90d-102">Incorporate a Data Profiling Task in Package Workflow</span></span>
  <span data-ttu-id="6b90d-103">Il profiling dati e la pulizia non sono attività potenziali per un processo automatizzato nelle fasi iniziali.</span><span class="sxs-lookup"><span data-stu-id="6b90d-103">Data profiling and cleanup are not candidates for an automated process in their early stages.</span></span> <span data-ttu-id="6b90d-104">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] l'output dell'attività Profiling dati richiede in genere un'analisi visiva e una valutazione umana per determinare se le violazioni segnalate sono significative o eccessive.</span><span class="sxs-lookup"><span data-stu-id="6b90d-104">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], the output of the Data Profiling task usually requires visual analysis and human judgment to determine whether reported violations are meaningful or excessive.</span></span> <span data-ttu-id="6b90d-105">Anche dopo il riconoscimento di problemi di qualità dei dati, è comunque necessario definire con attenzione un piano ben studiato per tentare di individuare l'approccio migliore per la pulizia.</span><span class="sxs-lookup"><span data-stu-id="6b90d-105">Even after recognizing data quality problems, there still has to be a carefully thought-out plan that addresses the best approach for cleanup.</span></span>  
  
 <span data-ttu-id="6b90d-106">Tuttavia, una volta stabiliti i criteri per la qualità dei dati, è possibile automatizzare operazioni periodiche di analisi e pulizia dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="6b90d-106">However, after criteria for data quality have been established, you might want to automate a periodic analysis and cleanup of the data source.</span></span> <span data-ttu-id="6b90d-107">Considerare gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="6b90d-107">Consider these scenarios:</span></span>  
  
-   <span data-ttu-id="6b90d-108">**Controllo della qualità dei dati prima di un caricamento incrementale**.</span><span class="sxs-lookup"><span data-stu-id="6b90d-108">**Checking data quality before an incremental load**.</span></span> <span data-ttu-id="6b90d-109">Utilizzare l'attività Profiling dati per calcolare il profilo Rapporto di valori Null nella colonna dei nuovi dati destinati alla colonna CustomerName di una tabella Customers.</span><span class="sxs-lookup"><span data-stu-id="6b90d-109">Use the Data Profiling task to compute the Column Null Ratio Profile of new data intended for the CustomerName column in a Customers table.</span></span> <span data-ttu-id="6b90d-110">Se la percentuale di valori Null è maggiore del 20%, inviare un messaggio di posta elettronica contenente l'output del profilo all'operatore e terminare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6b90d-110">If the percentage of null values is greater than 20%, send an e-mail message that contains the profile output to the operator and end the package.</span></span> <span data-ttu-id="6b90d-111">In caso contrario, continuare il caricamento incrementale.</span><span class="sxs-lookup"><span data-stu-id="6b90d-111">Otherwise, continue the incremental load.</span></span>  
  
-   <span data-ttu-id="6b90d-112">**Automazione della pulizia quando vengono soddisfatte le condizioni specificate**.</span><span class="sxs-lookup"><span data-stu-id="6b90d-112">**Automating cleanup when the specified conditions are met**.</span></span> <span data-ttu-id="6b90d-113">Utilizzare l'attività Profiling dati per calcolare il profilo Inclusione valore della colonna State rispetto a una tabella di ricerca di stati e quello della colonna ZIP Code/Postal Code rispetto a una tabella di ricerca di CAP.</span><span class="sxs-lookup"><span data-stu-id="6b90d-113">Use the Data Profiling task to compute the Value Inclusion Profile of the State column against a lookup table of states, and of the ZIP Code/Postal Code column against a lookup table of zip codes.</span></span> <span data-ttu-id="6b90d-114">Se l'attendibilità dell'inclusione dei valori di stato è minore dell'80%, ma quella dei valori di ZIP Code/Postal Code è maggiore del 99%, emergono due indicazioni.</span><span class="sxs-lookup"><span data-stu-id="6b90d-114">If the inclusion strength of the state values is less than 80%, but the inclusion strength of the ZIP Code/Postal Code values is greater than 99%, this indicates two things.</span></span> <span data-ttu-id="6b90d-115">Innanzitutto, i dati relativi allo stato sono errati.</span><span class="sxs-lookup"><span data-stu-id="6b90d-115">First, the state data is bad.</span></span> <span data-ttu-id="6b90d-116">In secondo luogo, i dati relativi a ZIP Code/Postal Code sono corretti.</span><span class="sxs-lookup"><span data-stu-id="6b90d-116">Second, the ZIP Code/Postal Code data is good.</span></span> <span data-ttu-id="6b90d-117">Avviare un'attività Flusso di dati per pulire i dati dello stato eseguendo una ricerca del valore dello stato corretto dal valore corrente di Zip Code/Postal Code.</span><span class="sxs-lookup"><span data-stu-id="6b90d-117">Launch a Data Flow task that cleans up the state data by performing a lookup of the correct state value from the current Zip Code/Postal Code value.</span></span>  
  
 <span data-ttu-id="6b90d-118">Dopo aver ottenuto un flusso di lavoro in cui è possibile incorporare l'attività Flusso di dati, è necessario identificare i passaggi richiesti per aggiungere questa attività.</span><span class="sxs-lookup"><span data-stu-id="6b90d-118">After you have a workflow into which you can incorporate the Data Flow task, you have to understand the steps that are required to add this task.</span></span> <span data-ttu-id="6b90d-119">Nella sezione seguente viene descritto il processo generale di incorporazione dell'attività Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="6b90d-119">The next section describes the general process of incorporating the Data Flow task.</span></span> <span data-ttu-id="6b90d-120">Nelle due sezioni finali viene descritto come connettere l'attività Flusso di dati direttamente a un'origine dati o ai dati trasformati dal flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="6b90d-120">The final two sections describe how to connect the Data Flow task either directly to a data source or to transformed data from the Data Flow.</span></span>  
  
## <a name="defining-a-general-workflow-for-the-data-flow-task"></a><span data-ttu-id="6b90d-121">Definizione di un flusso di lavoro generale per l'attività Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="6b90d-121">Defining a General Workflow for the Data Flow Task</span></span>  
 <span data-ttu-id="6b90d-122">Nella procedura seguente viene definito l'approccio generale per l'utilizzo dell'output dell'attività Profiling dati nel flusso di lavoro di un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6b90d-122">The following procedure outlines the general approach for using the output of the Data Profiling task in the workflow of a package.</span></span>  
  
#### <a name="to-use-the-output-of-the-data-profiling-task-programmatically-in-a-package"></a><span data-ttu-id="6b90d-123">Per utilizzare l'output dell'attività Profiling dati a livello di codice in un pacchetto</span><span class="sxs-lookup"><span data-stu-id="6b90d-123">To use the output of the Data Profiling task programmatically in a package</span></span>  
  
1.  <span data-ttu-id="6b90d-124">Aggiungere e configurare l'attività Profiling dati in un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6b90d-124">Add and configure the Data Profiling task in a package.</span></span>  
  
2.  <span data-ttu-id="6b90d-125">Configurare le variabili del pacchetto che conterranno i valori che si desidera recuperare dai risultati del profilo.</span><span class="sxs-lookup"><span data-stu-id="6b90d-125">Configure package variables to hold the values that you want to retrieve from the profile results.</span></span>  
  
3.  <span data-ttu-id="6b90d-126">Aggiungere e configurare un'attività Script.</span><span class="sxs-lookup"><span data-stu-id="6b90d-126">Add and configure a Script task.</span></span> <span data-ttu-id="6b90d-127">Connettere l'attività Script all'attività Profiling dati.</span><span class="sxs-lookup"><span data-stu-id="6b90d-127">Connect the Script task to the Data Profiling task.</span></span> <span data-ttu-id="6b90d-128">Nell'attività Script scrivere codice che legge i valori desiderati dal file di output dell'attività Profiling dati e popola le variabili del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6b90d-128">In the Script task, write code that reads the desired values from the output file of the Data Profiling task and populates the package variables.</span></span>  
  
4.  <span data-ttu-id="6b90d-129">Nei vincoli di precedenza che connettono l'attività Script ai rami a valle nel flusso di lavoro, scrivere espressioni che utilizzano i valori delle variabili per indirizzare il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6b90d-129">In the precedence constraints that connect the Script task to downstream branches in the workflow, write expressions that use the values of the variables to direct the workflow.</span></span>  
  
 <span data-ttu-id="6b90d-130">Quando si incorpora l'attività Profiling dati nel flusso di lavoro di un pacchetto, tenere presenti queste due caratteristiche dell'attività:</span><span class="sxs-lookup"><span data-stu-id="6b90d-130">When incorporating the Data Profiling task into the workflow of a package, keep these two features of the task in mind:</span></span>  
  
-   <span data-ttu-id="6b90d-131">**Output dell'attività**.</span><span class="sxs-lookup"><span data-stu-id="6b90d-131">**Task output**.</span></span> <span data-ttu-id="6b90d-132">L'output dell'attività Profiling dati viene scritto in un file o in una variabile del pacchetto in formato XML in base allo schema DataProfile.xsd.</span><span class="sxs-lookup"><span data-stu-id="6b90d-132">The Data Profiling task writes its output to a file or a package variable in XML format according to the DataProfile.xsd schema.</span></span> <span data-ttu-id="6b90d-133">Pertanto, è necessario eseguire una query sull'output XML se si desidera utilizzare i risultati del profilo nel flusso di lavoro condizionale di un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6b90d-133">Therefore, you have to query the XML output if you want to use the profile results in the conditional workflow of a package.</span></span> <span data-ttu-id="6b90d-134">A tale scopo, è possibile utilizzare il linguaggio di query Xpath.</span><span class="sxs-lookup"><span data-stu-id="6b90d-134">You can easily use the Xpath query language to query this XML output.</span></span> <span data-ttu-id="6b90d-135">Per esaminare la struttura di questo output XML, è possibile aprire un file di output di esempio o lo schema stesso.</span><span class="sxs-lookup"><span data-stu-id="6b90d-135">To study the structure of this XML output, you can open a sample output file or the schema itself.</span></span> <span data-ttu-id="6b90d-136">Per aprire il file di output o lo schema, è possibile usare [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], un altro editor XML o un editor di testo, ad esempio il Blocco note.</span><span class="sxs-lookup"><span data-stu-id="6b90d-136">To open the output file or schema, you can use [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], another XML editor, or a text editor, such as Notepad.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6b90d-137">Alcuni risultati del profilo visualizzati nel Visualizzatore profilo dati sono valori calcolati che non si trovano direttamente nell'output.</span><span class="sxs-lookup"><span data-stu-id="6b90d-137">Some of the profile results that are displayed in the Data Profile Viewer are calculated values that are not directly found in the output.</span></span> <span data-ttu-id="6b90d-138">Ad esempio, l'output del profilo Rapporto di valori Null nella colonna contiene il numero complessivo di righe e il numero di righe che contengono valori Null.</span><span class="sxs-lookup"><span data-stu-id="6b90d-138">For example, the output of the Column Null Ratio Profile contains the total number of rows and the number of rows that contain null values.</span></span> <span data-ttu-id="6b90d-139">È necessario eseguire una query su questi due valori, quindi calcolare la percentuale di righe che contengono valori Null per ottenere il rapporto di valori Null nella colonna.</span><span class="sxs-lookup"><span data-stu-id="6b90d-139">You have to query these two values, and then calculate the percentage of rows that contain null values, to obtain the column null ratio.</span></span>  
  
-   <span data-ttu-id="6b90d-140">**Input dell'attività**.</span><span class="sxs-lookup"><span data-stu-id="6b90d-140">**Task input**.</span></span> <span data-ttu-id="6b90d-141">L'input dell'attività Profiling dati viene letto da tabelle di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6b90d-141">The Data Profiling task reads its input from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables.</span></span> <span data-ttu-id="6b90d-142">Pertanto, è necessario salvare i dati presenti in memoria in tabelle di staging se si desidera eseguire il profiling di dati già caricati e trasformati nel flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="6b90d-142">Therefore, you have to save data that is in memory to staging tables if you want to profile data that has already been loaded and transformed in the data flow.</span></span>  
  
 <span data-ttu-id="6b90d-143">Nelle sezioni seguenti questo flusso di lavoro generale viene applicato al profiling di dati provenienti direttamente da un'origine dati esterna o trasformati dall'attività Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="6b90d-143">The following sections apply this general workflow to profiling data that comes directly from an external data source or that comes transformed from the Data Flow task.</span></span> <span data-ttu-id="6b90d-144">Viene inoltre illustrato come gestire i requisiti di input e di output dell'attività Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="6b90d-144">These sections also show how to handle the input and output requirements of the Data Flow task.</span></span>  
  
## <a name="connecting-the-data-profiling-task-directly-to-an-external-data-source"></a><span data-ttu-id="6b90d-145">Connessione diretta dell'attività Profiling dati a un'origine dati esterna</span><span class="sxs-lookup"><span data-stu-id="6b90d-145">Connecting the Data Profiling Task Directly to an External Data Source</span></span>  
 <span data-ttu-id="6b90d-146">L'attività Profiling dati consente di eseguire il profiling di dati provenienti direttamente da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="6b90d-146">The Data Profiling task can profile data that comes directly from a data source.</span></span>  <span data-ttu-id="6b90d-147">Per illustrare questa funzionalità, nell'esempio seguente viene utilizzata l'attività Profiling dati per calcolare un profilo Rapporto di valori Null nella colonna per le colonne della tabella Person.Address nel database [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6b90d-147">To illustrate this capability, the following example uses the Data Profiling task to compute a Column Null Ratio Profile on the columns of the Person.Address table in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="6b90d-148">Viene quindi utilizzata un'attività Script per recuperare i risultati dal file di output e popolare le variabili del pacchetto che è possibile utilizzare per indirizzare il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6b90d-148">Then, this example uses a Script task to retrieve the results from the output file and populate package variables that can be used to direct workflow.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6b90d-149">Per questo semplice esempio è stata selezionata la colonna AddressLine2, in quanto contiene una percentuale elevata di valori Null.</span><span class="sxs-lookup"><span data-stu-id="6b90d-149">The AddressLine2 column was selected for this simple example because this column contains a high percentage of null values.</span></span>  
  
 <span data-ttu-id="6b90d-150">L'esempio è costituito dai passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="6b90d-150">This example consists of the following steps:</span></span>  
  
-   <span data-ttu-id="6b90d-151">Configurazione delle gestioni connessioni che eseguono la connessione all'origine dati esterna e al file di output che conterrà i risultati del profilo.</span><span class="sxs-lookup"><span data-stu-id="6b90d-151">Configuring the connection managers that connect to the external data source and to the output file that will contain the profile results.</span></span>  
  
-   <span data-ttu-id="6b90d-152">Configurazione delle variabili del pacchetto che conterranno i valori necessari per l'attività Profiling dati.</span><span class="sxs-lookup"><span data-stu-id="6b90d-152">Configuring the package variables that will hold the values needed by the Data Profiling task.</span></span>  
  
-   <span data-ttu-id="6b90d-153">Configurazione dell'attività Profiling dati per calcolare il profilo Rapporto di valori Null nella colonna.</span><span class="sxs-lookup"><span data-stu-id="6b90d-153">Configuring the Data Profiling task to compute the Column Null Ratio Profile.</span></span>  
  
-   <span data-ttu-id="6b90d-154">Configurazione dell'attività Script per gestire l'output XML dell'attività Profiling dati.</span><span class="sxs-lookup"><span data-stu-id="6b90d-154">Configuring the Script task to work the XML output from the Data Profiling task.</span></span>  
  
-   <span data-ttu-id="6b90d-155">Configurazione dei vincoli di precedenza che controlleranno quali rami a valle nel flusso di lavoro vengono eseguiti in base ai risultati dell'attività Profiling dati.</span><span class="sxs-lookup"><span data-stu-id="6b90d-155">Configuring the precedence constraints that will control which downstream branches in the workflow are run based on the results of the Data Profiling task.</span></span>  
  
### <a name="configure-the-connection-managers"></a><span data-ttu-id="6b90d-156">Configurare le gestioni connessioni</span><span class="sxs-lookup"><span data-stu-id="6b90d-156">Configure the Connection Managers</span></span>  
 <span data-ttu-id="6b90d-157">Per questo esempio, sono disponibili due gestioni connessioni:</span><span class="sxs-lookup"><span data-stu-id="6b90d-157">For this example, there are two connection managers:</span></span>  
  
-   <span data-ttu-id="6b90d-158">Una gestione connessione [!INCLUDE[vstecado](../../includes/vstecado-md.md)] che stabilisce la connessione al database [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6b90d-158">An [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that connects to the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span>  
  
-   <span data-ttu-id="6b90d-159">Una gestione connessione file che crea il file di output che conterrà i risultati dell'attività Profiling dati.</span><span class="sxs-lookup"><span data-stu-id="6b90d-159">A File connection manager that creates the output file that will hold the results of the Data Profiling task.</span></span>  
  
##### <a name="to-configure-the-connection-managers"></a><span data-ttu-id="6b90d-160">Per configurare le gestioni connessioni</span><span class="sxs-lookup"><span data-stu-id="6b90d-160">To configure the connection managers</span></span>  
  
1.  <span data-ttu-id="6b90d-161">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]creare un nuovo pacchetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6b90d-161">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span>  
  
2.  <span data-ttu-id="6b90d-162">Aggiungere una gestione connessione [!INCLUDE[vstecado](../../includes/vstecado-md.md)] al pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6b90d-162">Add an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager to the package.</span></span> <span data-ttu-id="6b90d-163">Configurare questa gestione connessione per l'uso del provider di dati .NET per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) e per la connessione a un'istanza disponibile del database [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6b90d-163">Configure this connection manager to use the NET Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) and to connect to an available instance of the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span>  
  
     <span data-ttu-id="6b90d-164">Per impostazione predefinita, il nome della gestione connessione è \<server name>.AdventureWorks1.</span><span class="sxs-lookup"><span data-stu-id="6b90d-164">By default, the connection manager has the following name: \<server name>.AdventureWorks1.</span></span>  
  
3.  <span data-ttu-id="6b90d-165">Aggiungere una gestione connessione file al pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6b90d-165">Add a File connection manager to the package.</span></span> <span data-ttu-id="6b90d-166">Configurare questa gestione connessione per la creazione del file di output per l'attività Profiling dati.</span><span class="sxs-lookup"><span data-stu-id="6b90d-166">Configure this connection manager to create the output file for the Data Profiling task.</span></span>  
  
     <span data-ttu-id="6b90d-167">In questo esempio viene utilizzato il nome file DataProfile1.xml.</span><span class="sxs-lookup"><span data-stu-id="6b90d-167">This example uses the file name, DataProfile1.xml.</span></span> <span data-ttu-id="6b90d-168">Per impostazione predefinita, la gestione connessione e il file hanno lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="6b90d-168">By default, the connection manager has the same name as the file.</span></span>  
  
### <a name="configure-the-package-variables"></a><span data-ttu-id="6b90d-169">Configurare le variabili del pacchetto</span><span class="sxs-lookup"><span data-stu-id="6b90d-169">Configure the Package Variables</span></span>  
 <span data-ttu-id="6b90d-170">In questo esempio vengono utilizzate due variabili del pacchetto:</span><span class="sxs-lookup"><span data-stu-id="6b90d-170">This example uses two package variables:</span></span>  
  
-   <span data-ttu-id="6b90d-171">La variabile ProfileConnectionName passa il nome della gestione connessione file all'attività Script.</span><span class="sxs-lookup"><span data-stu-id="6b90d-171">The ProfileConnectionName variable passes the name of the File connection manager to the Script task.</span></span>  
  
-   <span data-ttu-id="6b90d-172">La variabile AddressLine2NullRatio passa il rapporto di valori Null calcolato per questa colonna dall'attività Script al pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6b90d-172">The AddressLine2NullRatio variable passes the calculated null ratio for this column out of the Script task to the package.</span></span>  
  
##### <a name="to-configure-the-package-variables-that-will-hold-profile-results"></a><span data-ttu-id="6b90d-173">Per configurare le variabili del pacchetto che conterranno i risultati del profilo</span><span class="sxs-lookup"><span data-stu-id="6b90d-173">To configure the package variables that will hold profile results</span></span>  
  
-   <span data-ttu-id="6b90d-174">Nella finestra **Variabili** aggiungere e configurare le due variabili del pacchetto seguenti:</span><span class="sxs-lookup"><span data-stu-id="6b90d-174">In the **Variables** window, add and configure the following two package variables:</span></span>  
  
    -   <span data-ttu-id="6b90d-175">Immettere il nome, `ProfileConnectionName` , per una delle variabili e impostare il tipo di questa variabile su **String**.</span><span class="sxs-lookup"><span data-stu-id="6b90d-175">Enter the name, `ProfileConnectionName`, for one of the variables and set the type of this variable to **String**.</span></span>  
  
    -   <span data-ttu-id="6b90d-176">Immettere il nome, `AddressLine2NullRatio` , per l'altra variabile e impostare il tipo di questa variabile su **Double**.</span><span class="sxs-lookup"><span data-stu-id="6b90d-176">Enter the name, `AddressLine2NullRatio`, for the other variable and set the type of this variable to **Double**.</span></span>  
  
### <a name="configure-the-data-profiling-task"></a><span data-ttu-id="6b90d-177">Configurare l'attività Profiling dati</span><span class="sxs-lookup"><span data-stu-id="6b90d-177">Configure the Data Profiling Task</span></span>  
 <span data-ttu-id="6b90d-178">L'attività Profiling dati deve essere configurata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="6b90d-178">The Data Profiling task has to be configured in the following way:</span></span>  
  
-   <span data-ttu-id="6b90d-179">Per utilizzare come input i dati forniti dalla gestione connessione [!INCLUDE[vstecado](../../includes/vstecado-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6b90d-179">To use the data that the [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager supplies as input.</span></span>  
  
-   <span data-ttu-id="6b90d-180">Per eseguire un profilo Rapporto di valori Null nella colonna sui dati di input.</span><span class="sxs-lookup"><span data-stu-id="6b90d-180">To perform a Column Null Ratio profile on the input data.</span></span>  
  
-   <span data-ttu-id="6b90d-181">Per salvare i risultati del profilo nel file associato alla gestione connessione file.</span><span class="sxs-lookup"><span data-stu-id="6b90d-181">To save the profile results to the file that is associated with the File connection manager.</span></span>  
  
##### <a name="to-configure-the-data-profiling-task"></a><span data-ttu-id="6b90d-182">Per configurare l'attività Profiling dati</span><span class="sxs-lookup"><span data-stu-id="6b90d-182">To configure the Data Profiling task</span></span>  
  
1.  <span data-ttu-id="6b90d-183">Aggiungere un'attività Profiling dati al flusso di controllo.</span><span class="sxs-lookup"><span data-stu-id="6b90d-183">To the Control Flow, add a Data Profiling task.</span></span>  
  
2.  <span data-ttu-id="6b90d-184">Aprire **Editor attività Profiling dati** per configurare l'attività.</span><span class="sxs-lookup"><span data-stu-id="6b90d-184">Open the **Data Profiling Task Editor** to configure the task.</span></span>  
  
3.  <span data-ttu-id="6b90d-185">Nella pagina **Generale** dell'editor, per **Destinazione**, selezionare il nome della gestione connessione file configurata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="6b90d-185">On the **General** page of the editor, for **Destination**, select the name of the File connection manager that you have previously configured.</span></span>  
  
4.  <span data-ttu-id="6b90d-186">Nella pagina **Richieste profilo** dell'editor creare un nuovo profilo Rapporto di valori Null nella colonna.</span><span class="sxs-lookup"><span data-stu-id="6b90d-186">On the **Profile Requests** page of the editor, create a new Column Null Ratio Profile.</span></span>  
  
5.  <span data-ttu-id="6b90d-187">Nel riquadro **Proprietà richiesta** , per **ConnectionManager**, selezionare la gestione connessione [!INCLUDE[vstecado](../../includes/vstecado-md.md)] configurata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="6b90d-187">In the **Request properties** pane, for **ConnectionManager**, select the [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that you have previously configured.</span></span> <span data-ttu-id="6b90d-188">Quindi, per **TableOrView**, selezionare Person.Address.</span><span class="sxs-lookup"><span data-stu-id="6b90d-188">Then, for **TableOrView**, select Person.Address.</span></span>  
  
6.  <span data-ttu-id="6b90d-189">Chiudere l'editor attività Profiling dati.</span><span class="sxs-lookup"><span data-stu-id="6b90d-189">Close the Data Profiling Task Editor.</span></span>  
  
### <a name="configure-the-script-task"></a><span data-ttu-id="6b90d-190">Configurare l'attività Script</span><span class="sxs-lookup"><span data-stu-id="6b90d-190">Configure the Script Task</span></span>  
 <span data-ttu-id="6b90d-191">L'attività Script deve essere configurata per recuperare i risultati dal file di output e popolare le variabili del pacchetto configurate in precedenza.</span><span class="sxs-lookup"><span data-stu-id="6b90d-191">The Script task has to be configured to retrieve the results from the output file and populate the package variables that were previously configured.</span></span>  
  
##### <a name="to-configure-the-script-task"></a><span data-ttu-id="6b90d-192">Per configurare l'attività Script</span><span class="sxs-lookup"><span data-stu-id="6b90d-192">To configure the Script task</span></span>  
  
1.  <span data-ttu-id="6b90d-193">Aggiungere un'attività Script al flusso di controllo.</span><span class="sxs-lookup"><span data-stu-id="6b90d-193">To the Control Flow, add a Script task.</span></span>  
  
2.  <span data-ttu-id="6b90d-194">Connettere l'attività Script all'attività Profiling dati.</span><span class="sxs-lookup"><span data-stu-id="6b90d-194">Connect the Script task to the Data Profiling task.</span></span>  
  
3.  <span data-ttu-id="6b90d-195">Aprire **Editor attività Script** per configurare l'attività.</span><span class="sxs-lookup"><span data-stu-id="6b90d-195">Open the **Script Task Editor** to configure the task.</span></span>  
  
4.  <span data-ttu-id="6b90d-196">Nella pagina **Script** selezionare il linguaggio di programmazione preferito.</span><span class="sxs-lookup"><span data-stu-id="6b90d-196">On the **Script** page, select your preferred programming language.</span></span> <span data-ttu-id="6b90d-197">Quindi, rendere disponibili le due variabili del pacchetto per lo script:</span><span class="sxs-lookup"><span data-stu-id="6b90d-197">Then, make the two package variables available to the script:</span></span>  
  
    1.  <span data-ttu-id="6b90d-198">Per `ReadOnlyVariables` , selezionare `ProfileConnectionName` .</span><span class="sxs-lookup"><span data-stu-id="6b90d-198">For `ReadOnlyVariables`, select `ProfileConnectionName`.</span></span>  
  
    2.  <span data-ttu-id="6b90d-199">Per **ReadWriteVariables**selezionare `AddressLine2NullRatio` .</span><span class="sxs-lookup"><span data-stu-id="6b90d-199">For **ReadWriteVariables**, select `AddressLine2NullRatio`.</span></span>  
  
5.  <span data-ttu-id="6b90d-200">Selezionare **Modifica script** per aprire l'ambiente di sviluppo dello script.</span><span class="sxs-lookup"><span data-stu-id="6b90d-200">Select **Edit Script** to open the script development environment.</span></span>  
  
6.  <span data-ttu-id="6b90d-201">Aggiungere un riferimento allo spazio dei nomi System.Xml.</span><span class="sxs-lookup"><span data-stu-id="6b90d-201">Add a reference to the System.Xml namespace.</span></span>  
  
7.  <span data-ttu-id="6b90d-202">Immettere il codice di esempio che corrisponde al linguaggio di programmazione in uso:</span><span class="sxs-lookup"><span data-stu-id="6b90d-202">Enter the sample code that corresponds to your programming language:</span></span>  
  
    ```vb  
    Imports System  
    Imports Microsoft.SqlServer.Dts.Runtime  
    Imports System.Xml  
  
    Public Class ScriptMain  
  
      Private FILENAME As String = "C:\ TEMP\DataProfile1.xml"  
      Private PROFILE_NAMESPACE_URI As String = "https://schemas.microsoft.com/DataDebugger/"  
      Private NULLCOUNT_XPATH As String = _  
        "/default:DataProfile/default:DataProfileOutput/default:Profiles" & _  
        "/default:ColumnNullRatioProfile[default:Column[@Name='AddressLine2']]/default:NullCount/text()"  
      Private TABLE_XPATH As String = _  
        "/default:DataProfile/default:DataProfileOutput/default:Profiles" & _  
        "/default:ColumnNullRatioProfile[default:Column[@Name='AddressLine2']]/default:Table"  
  
      Public Sub Main()  
  
        Dim profileConnectionName As String  
        Dim profilePath As String  
        Dim profileOutput As New XmlDocument  
        Dim profileNSM As XmlNamespaceManager  
        Dim nullCountNode As XmlNode  
        Dim nullCount As Integer  
        Dim tableNode As XmlNode  
        Dim rowCount As Integer  
        Dim nullRatio As Double  
  
        ' Open output file.  
        profileConnectionName = Dts.Variables("ProfileConnectionName").Value.ToString()  
        profilePath = Dts.Connections(profileConnectionName).ConnectionString  
        profileOutput.Load(profilePath)  
        profileNSM = New XmlNamespaceManager(profileOutput.NameTable)  
        profileNSM.AddNamespace("default", PROFILE_NAMESPACE_URI)  
  
        ' Get null count for column.  
        nullCountNode = profileOutput.SelectSingleNode(NULLCOUNT_XPATH, profileNSM)  
        nullCount = CType(nullCountNode.Value, Integer)  
  
        ' Get row count for table.  
        tableNode = profileOutput.SelectSingleNode(TABLE_XPATH, profileNSM)  
        rowCount = CType(tableNode.Attributes("RowCount").Value, Integer)  
  
        ' Compute and return null ratio.  
        nullRatio = nullCount / rowCount  
        Dts.Variables("AddressLine2NullRatio").Value = nullRatio  
  
        Dts.TaskResult = Dts.Results.Success  
  
      End Sub  
  
    End Class  
    ```  
  
    ```csharp  
    using System;  
    using Microsoft.SqlServer.Dts.Runtime;  
    using System.Xml;  
  
    public class ScriptMain  
    {  
  
      private string FILENAME = "C:\\ TEMP\\DataProfile1.xml";  
      private string PROFILE_NAMESPACE_URI = "https://schemas.microsoft.com/DataDebugger/";  
      private string NULLCOUNT_XPATH = "/default:DataProfile/default:DataProfileOutput/default:Profiles" + "/default:ColumnNullRatioProfile[default:Column[@Name='AddressLine2']]/default:NullCount/text()";  
      private string TABLE_XPATH = "/default:DataProfile/default:DataProfileOutput/default:Profiles" + "/default:ColumnNullRatioProfile[default:Column[@Name='AddressLine2']]/default:Table";  
  
      public void Main()  
      {  
  
        string profileConnectionName;  
        string profilePath;  
        XmlDocument profileOutput = new XmlDocument();  
        XmlNamespaceManager profileNSM;  
        XmlNode nullCountNode;  
        int nullCount;  
        XmlNode tableNode;  
        int rowCount;  
        double nullRatio;  
  
        // Open output file.  
        profileConnectionName = Dts.Variables["ProfileConnectionName"].Value.ToString();  
        profilePath = Dts.Connections[profileConnectionName].ConnectionString;  
        profileOutput.Load(profilePath);  
        profileNSM = new XmlNamespaceManager(profileOutput.NameTable);  
        profileNSM.AddNamespace("default", PROFILE_NAMESPACE_URI);  
  
        // Get null count for column.  
        nullCountNode = profileOutput.SelectSingleNode(NULLCOUNT_XPATH, profileNSM);  
        nullCount = (int)nullCountNode.Value;  
  
        // Get row count for table.  
        tableNode = profileOutput.SelectSingleNode(TABLE_XPATH, profileNSM);  
        rowCount = (int)tableNode.Attributes["RowCount"].Value;  
  
        // Compute and return null ratio.  
        nullRatio = nullCount / rowCount;  
        Dts.Variables["AddressLine2NullRatio"].Value = nullRatio;  
  
        Dts.TaskResult = Dts.Results.Success;  
  
      }  
  
    }  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="6b90d-203">Nel codice di esempio di questa procedura viene illustrato come caricare l'output dell'attività Profiling dati da un file.</span><span class="sxs-lookup"><span data-stu-id="6b90d-203">The sample code shown in this procedure demonstrates how to load the output of the Data Profiling task from a file.</span></span> <span data-ttu-id="6b90d-204">Per caricare invece l'output dell'attività Profiling dati da una variabile del pacchetto, vedere il codice di esempio alternativo riportato dopo questa procedura.</span><span class="sxs-lookup"><span data-stu-id="6b90d-204">To load the output of the Data Profiling task from a package variable instead, see the alternative sample code that follows this procedure.</span></span>  
  
8.  <span data-ttu-id="6b90d-205">Chiudere l'ambiente di sviluppo dello script, quindi l'editor attività Script.</span><span class="sxs-lookup"><span data-stu-id="6b90d-205">Close the script development environment, and then close the Script Task Editor.</span></span>  
  
#### <a name="alternative-code-reading-the-profile-output-from-a-variable"></a><span data-ttu-id="6b90d-206">Codice alternativo: lettura dell'output del profilo da una variabile</span><span class="sxs-lookup"><span data-stu-id="6b90d-206">Alternative Code-Reading the Profile Output from a Variable</span></span>  
 <span data-ttu-id="6b90d-207">La procedura riportata in precedenza indica come caricare l'output dell'attività Profiling dati da un file.</span><span class="sxs-lookup"><span data-stu-id="6b90d-207">The previous procedure shows how to load the output of the Data Profiling task from a file.</span></span> <span data-ttu-id="6b90d-208">Un metodo alternativo consiste nel caricare questo output da una variabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6b90d-208">However, an alternative method would be to load this output from a package variable.</span></span> <span data-ttu-id="6b90d-209">A tale scopo, è necessario apportare le modifiche seguenti al codice di esempio:</span><span class="sxs-lookup"><span data-stu-id="6b90d-209">To load the output from a variable, you have to make the following changes to the sample code:</span></span>  
  
-   <span data-ttu-id="6b90d-210">Chiamare il metodo `LoadXml` della classe `XmlDocument` anziché il metodo `Load`.</span><span class="sxs-lookup"><span data-stu-id="6b90d-210">Call the `LoadXml` method of the `XmlDocument` class instead of the `Load` method.</span></span>  
  
-   <span data-ttu-id="6b90d-211">Nell'editor attività Script aggiungere il nome della variabile del pacchetto che contiene l'output del profilo all'elenco `ReadOnlyVariables` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="6b90d-211">In the Script Task Editor, add the name of the package variable that contains the profile output to the task's `ReadOnlyVariables` list.</span></span>  
  
-   <span data-ttu-id="6b90d-212">Passare il valore stringa della variabile al metodo `LoadXML` come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="6b90d-212">Pass the string value of the variable to the `LoadXML` method, as shown in the following code example.</span></span> <span data-ttu-id="6b90d-213">In questo esempio viene utilizzato "ProfileOutput" come nome della variabile del pacchetto che contiene l'output del profilo.</span><span class="sxs-lookup"><span data-stu-id="6b90d-213">(This example uses "ProfileOutput" as the name of the package variable that contains the profile output.)</span></span>  
  
    ```vb  
    Dim outputString As String  
    outputString = Dts.Variables("ProfileOutput").Value.ToString()  
    ...  
    profileOutput.LoadXml(outputString)  
    ```  
  
    ```csharp  
    string outputString;  
    outputString = Dts.Variables["ProfileOutput"].Value.ToString();  
    ...  
    profileOutput.LoadXml(outputString);  
    ```  
  
### <a name="configure-the-precedence-constraints"></a><span data-ttu-id="6b90d-214">Configurare i vincoli di precedenza</span><span class="sxs-lookup"><span data-stu-id="6b90d-214">Configure the Precedence Constraints</span></span>  
 <span data-ttu-id="6b90d-215">I vincoli di precedenza devono essere configurati per controllare quali rami a valle nel flusso di lavoro vengono eseguiti in base ai risultati dell'attività Profiling dati.</span><span class="sxs-lookup"><span data-stu-id="6b90d-215">The precedence constraints have to be configured to control which downstream branches in the workflow are run based on the results of the Data Profiling task.</span></span>  
  
##### <a name="to-configure-the-precedence-constraints"></a><span data-ttu-id="6b90d-216">Per configurare i vincoli di precedenza</span><span class="sxs-lookup"><span data-stu-id="6b90d-216">To configure the precedence constraints</span></span>  
  
-   <span data-ttu-id="6b90d-217">Nei vincoli di precedenza che connettono l'attività Script ai rami a valle nel flusso di lavoro, scrivere espressioni che utilizzano i valori delle variabili per indirizzare il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6b90d-217">In the precedence constraints that connect the Script task to downstream branches in the workflow, write expressions that use the values of the variables to direct the workflow.</span></span>  
  
     <span data-ttu-id="6b90d-218">Ad esempio, è possibile impostare **Operazione valutazione** del vincolo di precedenza su **Espressione e vincolo**.</span><span class="sxs-lookup"><span data-stu-id="6b90d-218">For example, you might set the **Evaluation operation** of the precedence constraint to **Expression and Constraint**.</span></span> <span data-ttu-id="6b90d-219">È quindi possibile utilizzare `@AddressLine2NullRatio < .90` come valore dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="6b90d-219">Then, you might use `@AddressLine2NullRatio < .90` as the value of the expression.</span></span> <span data-ttu-id="6b90d-220">In questo modo il flusso di lavoro segue il percorso selezionato quando le attività precedenti vengono completate e quando la percentuale di valori Null nella colonna selezionata è minore del 90%.</span><span class="sxs-lookup"><span data-stu-id="6b90d-220">This causes the workflow to follow the selected path when the previous tasks succeed, and when the percentage of null values in the selected column is less than 90%.</span></span>  
  
## <a name="connecting-the-data-profiling-task-to-transformed-data-from-the-data-flow"></a><span data-ttu-id="6b90d-221">Connessione dell'attività Profiling dati ai dati trasformati dal flusso di dati</span><span class="sxs-lookup"><span data-stu-id="6b90d-221">Connecting the Data Profiling Task to Transformed Data from the Data Flow</span></span>  
 <span data-ttu-id="6b90d-222">Anziché direttamente da un'origine dati, è possibile eseguire il profiling dei dati che sono già stati caricati e trasformanti nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6b90d-222">Instead of profiling data directly from a data source, you can profile data that has already been loaded and transformed in the data flow.</span></span> <span data-ttu-id="6b90d-223">L'attività Profiling dati funziona, tuttavia, solo per dati persistenti, non per dati in memoria.</span><span class="sxs-lookup"><span data-stu-id="6b90d-223">However, the Data Profiling task works only against persisted data, not against in-memory data.</span></span> <span data-ttu-id="6b90d-224">Pertanto, è necessario utilizzare dapprima un componente di destinazione per salvare i dati trasformati in una tabella di staging.</span><span class="sxs-lookup"><span data-stu-id="6b90d-224">Therefore, you must first use a destination component to save the transformed data to a staging table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6b90d-225">Quando si configura l'attività Profiling dati, è necessario selezionare tabelle e colonne esistenti.</span><span class="sxs-lookup"><span data-stu-id="6b90d-225">When you configure the Data Profiling task, you have to select existing tables and columns.</span></span> <span data-ttu-id="6b90d-226">Pertanto, è necessario creare la tabella di staging in fase di progettazione prima di poter configurare l'attività.</span><span class="sxs-lookup"><span data-stu-id="6b90d-226">Therefore, you must create the staging table at design time before you can configure the task.</span></span> <span data-ttu-id="6b90d-227">In altri termini, questo scenario non consente l'utilizzo di una tabella temporanea creata in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6b90d-227">In other words, this scenario does not allow you to use a temporary table that is created at run time.</span></span>  
  
 <span data-ttu-id="6b90d-228">Dopo aver salvato i dati in una tabella di staging, è possibile effettuare le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6b90d-228">After saving the data to a staging table, you can do the following actions:</span></span>  
  
-   <span data-ttu-id="6b90d-229">Utilizzare l'attività Profiling dati per eseguire il profiling dei dati.</span><span class="sxs-lookup"><span data-stu-id="6b90d-229">Use the Data Profiling task to profile the data.</span></span>  
  
-   <span data-ttu-id="6b90d-230">Utilizzare un'attività Script per leggere i risultati come descritto in precedenza in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="6b90d-230">Use a Script task to read the results as described earlier in this topic.</span></span>  
  
-   <span data-ttu-id="6b90d-231">Utilizzare questi risultati per indirizzare il flusso di lavoro successivo del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6b90d-231">Use those results to direct the subsequent workflow of the package.</span></span>  
  
 <span data-ttu-id="6b90d-232">Nella procedura seguente viene fornito l'approccio generale per l'utilizzo dell'attività Profiling dati per eseguire il profiling di dati trasformati dal flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="6b90d-232">The following procedure provides the general approach for using the Data Profiling task to profile data that has been transformed by the data flow.</span></span> <span data-ttu-id="6b90d-233">Molti passaggi sono simili a quelli descritti in precedenza per il profiling dei dati provenienti direttamente da un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="6b90d-233">Many of these steps are similar to the ones described earlier for profiling data that comes directly from an external data source.</span></span> <span data-ttu-id="6b90d-234">Può essere necessario rivedere questi passaggi precedenti per ulteriori informazioni su come configurare i vari componenti.</span><span class="sxs-lookup"><span data-stu-id="6b90d-234">You might want to review those earlier steps for more information about how to configure the various components.</span></span>  
  
#### <a name="to-use-the-data-profiling-task-in-the-data-flow"></a><span data-ttu-id="6b90d-235">Per utilizzare l'attività Profiling dati nel flusso di dati</span><span class="sxs-lookup"><span data-stu-id="6b90d-235">To use the Data Profiling task in the data flow</span></span>  
  
1.  <span data-ttu-id="6b90d-236">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]creare un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6b90d-236">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], create a package.</span></span>  
  
2.  <span data-ttu-id="6b90d-237">Nel flusso di dati aggiungere, configurare e connettere le origini e le trasformazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="6b90d-237">In the Data Flow, add, configure, and connect the appropriate sources and transformations.</span></span>  
  
3.  <span data-ttu-id="6b90d-238">Nel flusso di dati aggiungere, configurare e connettere un componente di destinazione che salva i dati trasformati in una tabella di staging.</span><span class="sxs-lookup"><span data-stu-id="6b90d-238">In the Data Flow, add, configure, and connect a destination component that saves the transformed data to a staging table.</span></span>  
  
4.  <span data-ttu-id="6b90d-239">Nel flusso di controllo aggiungere e configurare un'attività Profiling dati che calcola i profili desiderati rispetto ai dati trasformati nella tabella di staging.</span><span class="sxs-lookup"><span data-stu-id="6b90d-239">In the Control Flow, add and configure a Data Profiling task that computes the desired profiles against the transformed data in the staging table.</span></span> <span data-ttu-id="6b90d-240">Connettere l'attività Profiling dati all'attività Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="6b90d-240">Connect the Data Profiling task to the Data Flow task.</span></span>  
  
5.  <span data-ttu-id="6b90d-241">Configurare le variabili del pacchetto che conterranno i valori che si desidera recuperare dai risultati del profilo.</span><span class="sxs-lookup"><span data-stu-id="6b90d-241">Configure package variables to hold the values that you want to retrieve from the profile results.</span></span>  
  
6.  <span data-ttu-id="6b90d-242">Aggiungere e configurare un'attività Script.</span><span class="sxs-lookup"><span data-stu-id="6b90d-242">Add and configure a Script task.</span></span> <span data-ttu-id="6b90d-243">Connettere l'attività Script all'attività Profiling dati.</span><span class="sxs-lookup"><span data-stu-id="6b90d-243">Connect the Script task to the Data Profiling task.</span></span> <span data-ttu-id="6b90d-244">Nell'attività Script scrivere codice che legge i valori desiderati dall'output dell'attività Profiling dati e popola le variabili del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6b90d-244">In the Script task, write code that reads the desired values from the output of the Data Profiling task and populates the package variables.</span></span>  
  
7.  <span data-ttu-id="6b90d-245">Nei vincoli di precedenza che connettono l'attività Script ai rami a valle nel flusso di lavoro, scrivere espressioni che utilizzano i valori delle variabili per indirizzare il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6b90d-245">In the precedence constraints that connect the Script task to downstream branches in the workflow, write expressions that use the values of the variables to direct the workflow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b90d-246">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b90d-246">See Also</span></span>  
 <span data-ttu-id="6b90d-247">[Impostazione dell'attività Profiling dati](data-profiling-task.md) </span><span class="sxs-lookup"><span data-stu-id="6b90d-247">[Setup of the Data Profiling Task](data-profiling-task.md) </span></span>  
 [<span data-ttu-id="6b90d-248">Visualizzatore profilo dati</span><span class="sxs-lookup"><span data-stu-id="6b90d-248">Data Profile Viewer</span></span>](data-profile-viewer.md)  
  
  
