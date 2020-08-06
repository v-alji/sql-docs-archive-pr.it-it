---
title: Tocchi del flusso di dati | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 2d847adf-4b3d-4949-a195-ef43de275077
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 053b34add45354d0df71fa73a72f8786cc706d15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713356"
---
# <a name="data-flow-taps"></a><span data-ttu-id="104ae-102">Scelte del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="104ae-102">Data Flow Taps</span></span>
  <span data-ttu-id="104ae-103">In [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] è stata introdotta una nuova funzionalità con cui è possibile aggiungere una scelta dei dati in un percorso del flusso di dati di un pacchetto in fase di esecuzione e indirizzare l'output della scelta dei dati a un file esterno.</span><span class="sxs-lookup"><span data-stu-id="104ae-103">[!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] introduces a new feature that allows you to add a data tap on a data flow path of a package at runtime and direct the output from the data tap to an external file.</span></span> <span data-ttu-id="104ae-104">Per utilizzare questa funzionalità, è necessario distribuire il progetto SSIS utilizzando il modello di distribuzione del progetto in un server SSIS.</span><span class="sxs-lookup"><span data-stu-id="104ae-104">To use this feature, you must deploy your SSIS project using the project deployment model to an SSIS Server.</span></span> <span data-ttu-id="104ae-105">Al termine della distribuzione del pacchetto nel server, è necessario eseguire script T-SQL nel database SSISDB per aggiungere le scelte dei dati prima dell'esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="104ae-105">After you deploy the package to the server, you need to execute T-SQL scripts against the SSISDB database to add data taps before executing the package.</span></span> <span data-ttu-id="104ae-106">Di seguito è riportato uno scenario di esempio:</span><span class="sxs-lookup"><span data-stu-id="104ae-106">Here is a sample scenario:</span></span>  
  
1.  <span data-ttu-id="104ae-107">Creare un'istanza di esecuzione di un pacchetto usando la stored procedure [catalog.create_execution &#40;database SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="104ae-107">Create an execution instance of a package by using the [catalog.create_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database) stored procedure.</span></span>  
  
2.  <span data-ttu-id="104ae-108">Aggiungere una scelta dei dati usando la stored procedure [catalog.add_data_tap](/sql/integration-services/system-stored-procedures/catalog-add-data-tap) o [catalog.add_data_tap_by_guid](/sql/integration-services/system-stored-procedures/catalog-add-data-tap-by-guid) .</span><span class="sxs-lookup"><span data-stu-id="104ae-108">Add a data tap by using either [catalog.add_data_tap](/sql/integration-services/system-stored-procedures/catalog-add-data-tap) or [catalog.add_data_tap_by_guid](/sql/integration-services/system-stored-procedures/catalog-add-data-tap-by-guid) stored procedure.</span></span>  
  
3.  <span data-ttu-id="104ae-109">Avviare l'istanza di esecuzione del pacchetto usando [catalog.start_execution &#40;databse SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="104ae-109">Start the execution instance of the package by using the [catalog.start_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database).</span></span>  
  
 <span data-ttu-id="104ae-110">Di seguito è riportato uno script SQL di esempio tramite cui vengono eseguiti i passaggi descritti nello scenario sopra indicato:</span><span class="sxs-lookup"><span data-stu-id="104ae-110">Here is a sample SQL script that performs the steps described in the above scenario:</span></span>  
  
```  
  
Declare @execid bigint  
EXEC [SSISDB].[catalog].[create_execution] @folder_name=N'ETL Folder', @project_name=N'ETL Project', @package_name=N'Package.dtsx', @execution_id=@execid OUTPUT  
EXEC [SSISDB].[catalog].add_data_tap @execution_id = @execid, @task_package_path = '\Package\Data Flow Task', @dataflow_path_id_string = 'Paths[Flat File Source.Flat File Source Output]', @data_filename = 'output.txt'  
EXEC [SSISDB].[catalog].[start_execution] @execid  
  
```  
  
 <span data-ttu-id="104ae-111">I parametri del nome della cartella, del nome del progetto e del nome del pacchetto della stored procedure create_execution corrispondono ai nomi della cartella, del progetto e del pacchetto nel catalogo di Integration Services.</span><span class="sxs-lookup"><span data-stu-id="104ae-111">The folder name, project name, and package name parameters of the create_execution stored procedure correspond to the folder, project, and package names in the Integration Services catalog.</span></span> <span data-ttu-id="104ae-112">È possibile ottenere i nomi della cartella, del progetto e del pacchetto da utilizzare nella chiamata a create_execution da SQL Server Management Studio come illustrato nella figura riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="104ae-112">You can get the folder, project, and package names to use in the create_execution call from the SQL Server Management Studio as shown in the following image.</span></span> <span data-ttu-id="104ae-113">Se non viene visualizzato il progetto SSIS in questo punto, non può ancora essere distribuito nel server SSIS.</span><span class="sxs-lookup"><span data-stu-id="104ae-113">If you do not see your SSIS project here, you may not have deployed the project to SSIS server yet.</span></span> <span data-ttu-id="104ae-114">Fare clic con il pulsante destro del mouse sul progetto SSIS in Visual Studio e scegliere Distribuisci per distribuire il progetto nel server SSIS previsto.</span><span class="sxs-lookup"><span data-stu-id="104ae-114">Right-click on SSIS project in Visual Studio and click Deploy to deploy the project to the expected SSIS server.</span></span>  
  
 <span data-ttu-id="104ae-115">Anziché digitare le istruzioni SQL, è possibile generare lo script di esecuzione del pacchetto effettuando i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="104ae-115">Instead of typing the SQL statements, you can generate the execute package script by performing the following steps:</span></span>  
  
1.  <span data-ttu-id="104ae-116">Fare clic con il pulsante destro del mouse su **Package.dtsx** , quindi scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="104ae-116">Right-click **Package.dtsx** and click **Execute**.</span></span>  
  
2.  <span data-ttu-id="104ae-117">Fare clic sul pulsante della barra degli strumenti **Script** per generare lo script.</span><span class="sxs-lookup"><span data-stu-id="104ae-117">Click **Script** toolbar button to generate the script.</span></span>  
  
3.  <span data-ttu-id="104ae-118">A questo punto, aggiungere l'istruzione add_data_tap prima della chiamata a start_execution.</span><span class="sxs-lookup"><span data-stu-id="104ae-118">Now, add the add_data_tap statement before the start_execution call.</span></span>  
  
 <span data-ttu-id="104ae-119">Il parametro task_package_path della stored procedure add_data_tap corrisponde alla proprietà PackagePath dell'attività Flusso di dati in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="104ae-119">The task_package_path parameter of add_data_tap stored procedure corresponds to the PackagePath property of the data flow task in Visual Studio.</span></span> <span data-ttu-id="104ae-120">In Visual Studio fare clic con il pulsante destro del mouse su **Attività Flusso di dati**e scegliere **Proprietà** per avviare la relativa finestra.</span><span class="sxs-lookup"><span data-stu-id="104ae-120">In Visual Studio, right-click the **Data Flow Task**, and click **Properties** to launch the Properties window.</span></span>  <span data-ttu-id="104ae-121">Prendere nota del valore della proprietà **PackagePath** per usarlo come valore per il parametro task_package_path per la chiamata della stored procedure add_data_tap.</span><span class="sxs-lookup"><span data-stu-id="104ae-121">Note the value of the **PackagePath** property to use it as a value for the task_package_path parameter for add_data_tap stored procedure call.</span></span>  
  
 <span data-ttu-id="104ae-122">Il parametro dataflow_path_id_string della stored procedure add_data_tap corrisponde alla proprietà IdentificationString del percorso del flusso di dati a cui si desidera aggiungere una scelta dei dati.</span><span class="sxs-lookup"><span data-stu-id="104ae-122">The dataflow_path_id_string  parameter of add_data_tap stored procedure corresponds to the IdentificationString property of the data flow path to which you want to add a data tap.</span></span> <span data-ttu-id="104ae-123">Per ottenere dataflow_path_id_string, fare clic sul percorso del flusso di dati (la freccia tra le attività nel flusso di dati) e prendere nota del valore della proprietà **IdentificationString** nella finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="104ae-123">To get the dataflow_path_id_string, click the data flow path (arrow between tasks in the data flow), and note the value of the **IdentificationString** property in the Properties window.</span></span>  
  
 <span data-ttu-id="104ae-124">Quando si esegue lo script, il file di output viene archiviato in \<Program Files>\Microsoft SQL Server\110\DTS\DataDumps.</span><span class="sxs-lookup"><span data-stu-id="104ae-124">When you execute the script, the output file is stored in \<Program Files>\Microsoft SQL Server\110\DTS\DataDumps.</span></span> <span data-ttu-id="104ae-125">Se esiste già un file con il nome, viene creato un nuovo file con un suffisso, ad esempio output[1].txt.</span><span class="sxs-lookup"><span data-stu-id="104ae-125">If a file with the name already exists, a new file with a suffix (for example: output[1].txt)  is created.</span></span>  
  
 <span data-ttu-id="104ae-126">Come accennato in precedenza, è inoltre possibile usare la stored procedure [catalog.add_data_tap_by_guid](/sql/integration-services/system-stored-procedures/catalog-add-data-tap-by-guid)anziché la stored procedure add_data_tap.</span><span class="sxs-lookup"><span data-stu-id="104ae-126">As mentioned earlier, you can also use [catalog.add_data_tap_by_guid](/sql/integration-services/system-stored-procedures/catalog-add-data-tap-by-guid)stored procedure instead of using add_data_tap stored procedure.</span></span> <span data-ttu-id="104ae-127">Questa stored procedure accetta l'ID dell'attività Flusso di dati come parametro anziché task_package_path.</span><span class="sxs-lookup"><span data-stu-id="104ae-127">This stored procedure takes the ID of data flow task as a parameter instead of task_package_path.</span></span> <span data-ttu-id="104ae-128">È possibile ottenere l'ID dell'attività Flusso di dati dalla finestra delle proprietà di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="104ae-128">You can get the ID of data flow task from the properties window in Visual Studio.</span></span>  
  
## <a name="removing-a-data-tap"></a><span data-ttu-id="104ae-129">Rimozione di una scelta dei dati</span><span class="sxs-lookup"><span data-stu-id="104ae-129">Removing a data tap</span></span>  
 <span data-ttu-id="104ae-130">È possibile rimuovere una scelta dei dati prima di avviare l'esecuzione usando la stored procedure [catalog.remove_data_tap](/sql/integration-services/system-stored-procedures/catalog-remove-data-tap) .</span><span class="sxs-lookup"><span data-stu-id="104ae-130">You can remove a data tap before starting the execution by using the [catalog.remove_data_tap](/sql/integration-services/system-stored-procedures/catalog-remove-data-tap) stored procedure.</span></span> <span data-ttu-id="104ae-131">Questa stored procedure accetta l'ID della scelta dei dati come parametro, che è possibile ottenere come output della stored procedure add_data_tap.</span><span class="sxs-lookup"><span data-stu-id="104ae-131">This stored procedure takes the ID of data tap as a parameter, which you can get as an output of the add_data_tap stored procedure.</span></span>  
  
```  
  
DECLARE @tap_id bigint  
EXEC [SSISDB].[catalog].add_data_tap @execution_id = @execid, @task_package_path = '\Package\Data Flow Task', @dataflow_path_id_string = 'Paths[Flat File Source.Flat File Source Output]', @data_filename = 'output.txt' @data_tap_id=@tap_id OUTPUT  
EXEC [SSISDB].[catalog].remove_data_tap @tap_id  
  
```  
  
## <a name="listing-all-data-taps"></a><span data-ttu-id="104ae-132">Elenco di tutte le scelte dei dati</span><span class="sxs-lookup"><span data-stu-id="104ae-132">Listing all data taps</span></span>  
 <span data-ttu-id="104ae-133">È inoltre possibile elencare tutte le scelte dei dati tramite la vista catalog.execution_data_taps.</span><span class="sxs-lookup"><span data-stu-id="104ae-133">You can also list all the data taps by using the catalog.execution_data_taps view.</span></span> <span data-ttu-id="104ae-134">Nell'esempio seguente vengono estratte le scelte dei dati per un'istanza di esecuzione specifica (ID: 54).</span><span class="sxs-lookup"><span data-stu-id="104ae-134">The following example extracts data taps for a specification execution instance (ID: 54).</span></span>  
  
```  
select * from [SSISDB].[catalog].execution_data_taps where execution_id=@execid  
```  
  
## <a name="performance-consideration"></a><span data-ttu-id="104ae-135">Considerazione sulle prestazioni</span><span class="sxs-lookup"><span data-stu-id="104ae-135">Performance consideration</span></span>  
 <span data-ttu-id="104ae-136">L'abilitazione del livello di registrazione dettagliata e l'aggiunta di scelte dei dati determinano un aumento delle operazioni di I/O eseguite dalla soluzione di integrazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="104ae-136">Enabling verbose logging level and adding data taps increase the I/O operations performed by your data integration solution.</span></span> <span data-ttu-id="104ae-137">Pertanto, è consigliabile aggiungere le scelte dei dati solo ai fini della risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="104ae-137">Hence, we recommend that you add data taps only for troubleshooting purposes</span></span>  
  
## <a name="video"></a><span data-ttu-id="104ae-138">Video</span><span class="sxs-lookup"><span data-stu-id="104ae-138">Video</span></span>  
 <span data-ttu-id="104ae-139">In questo [video su TechNet](https://technet.microsoft.com/sqlserver/dn600163) viene illustrato come aggiungere o usare le scelte dei dati nel catalogo di SQL Server 2012 SSISDB che facilita il debug dei pacchetti a livello di codice e l'acquisizione dei risultati parziali in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="104ae-139">This [video on TechNet](https://technet.microsoft.com/sqlserver/dn600163) demonstrates how to add/use data taps in SQL Server 2012 SSISDB catalog that help with debugging packages programmatically and capturing the partial results at the runtime.</span></span> <span data-ttu-id="104ae-140">Inoltre vengono illustrate la modalità per elencare/rimuovere queste scelte dei dati e le procedure consigliate per l'utilizzo delle scelte dei dati nei pacchetti SSIS.</span><span class="sxs-lookup"><span data-stu-id="104ae-140">It also discusses how to list/ remove these data taps and best practices for using data taps in SSIS packages.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="104ae-141">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="104ae-141">Related Tasks</span></span>  
 [<span data-ttu-id="104ae-142">Debug di un flusso di dati</span><span class="sxs-lookup"><span data-stu-id="104ae-142">Debugging Data Flow</span></span>](troubleshooting/debugging-data-flow.md)  
  
 [<span data-ttu-id="104ae-143">Strumenti per la risoluzione dei problemi relativi all'esecuzione dei pacchetti</span><span class="sxs-lookup"><span data-stu-id="104ae-143">Troubleshooting Tools for Package Execution</span></span>](troubleshooting/troubleshooting-tools-for-package-execution.md)  
  
  
