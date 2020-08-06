---
title: Distribuire ed eseguire pacchetti SSIS tramite stored procedure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 60914b0c-1f65-45f8-8132-0ca331749fcc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1570207dca6e944b54c553a1d83256d8f4fa3244
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724007"
---
# <a name="deploy-and-execute-ssis-packages-using-stored-procedures"></a><span data-ttu-id="20956-102">Distribuire ed eseguire pacchetti SSIS utilizzando le stored procedure</span><span class="sxs-lookup"><span data-stu-id="20956-102">Deploy and Execute SSIS Packages using Stored Procedures</span></span>
  <span data-ttu-id="20956-103">Quando un progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] viene configurato in modo da utilizzare il relativo modello di distribuzione, è possibile utilizzare le stored procedure nel catalogo di [!INCLUDE[ssIS](../includes/ssis-md.md)] per distribuire il progetto ed eseguire i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="20956-103">When you configure an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to use the project deployment model, you can use stored procedures in the [!INCLUDE[ssIS](../includes/ssis-md.md)] catalog to deploy the project and execute the packages.</span></span> <span data-ttu-id="20956-104">Per informazioni sui modelli di distribuzione di progetti, vedere [Distribuzione di progetti e pacchetti](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="20956-104">For information about the project deployment model, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="20956-105">Per distribuire il progetto ed eseguire i pacchetti, è inoltre possibile utilizzare [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] o [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="20956-105">You can also use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to deploy the project and execute the packages.</span></span> <span data-ttu-id="20956-106">Per altre informazioni, vedere gli argomenti nella sezione **Vedere anche** .</span><span class="sxs-lookup"><span data-stu-id="20956-106">For more information, see the topics in the **See Also** section.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="20956-107">Ad eccezione di catalog.deploy_project, è possibile generare facilmente le istruzioni Transact-SQL per le stored procedure elencate nella procedura descritta di seguito effettuando le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="20956-107">You can easily generate the Transact-SQL statements for the stored procedures listed in the procedure below, with the exception of catalog.deploy_project, by doing the following:</span></span>  
> 
>  1.  <span data-ttu-id="20956-108">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]espandere il nodo **Cataloghi di Integration Services** in Esplora oggetti e selezionare il pacchetto che si desidera eseguire.</span><span class="sxs-lookup"><span data-stu-id="20956-108">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], expand the **Integration Services Catalogs** node in Object Explorer and navigate to the package you want to execute.</span></span>  
> 2.  <span data-ttu-id="20956-109">Fare clic con il pulsante destro del mouse sul pacchetto, quindi scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="20956-109">Right-click the package, and then click **Execute**.</span></span>  
> 3.  <span data-ttu-id="20956-110">In base alle esigenze, impostare i valori dei parametri, le proprietà di gestione connessione e le opzioni nella scheda **Avanzate** , ad esempio il livello di registrazione.</span><span class="sxs-lookup"><span data-stu-id="20956-110">As needed, set parameters values, connection manager properties, and options in the **Advanced** tab such as the logging level.</span></span>  
> 
>      <span data-ttu-id="20956-111">Per altre informazioni sui livelli di registrazione, vedere [Abilitare la registrazione per l'esecuzione di pacchetti nel server SSIS](../../2014/integration-services/enable-logging-for-package-execution-on-the-ssis-server.md).</span><span class="sxs-lookup"><span data-stu-id="20956-111">For more information about logging levels, see [Enable Logging for Package Execution on the SSIS Server](../../2014/integration-services/enable-logging-for-package-execution-on-the-ssis-server.md).</span></span>  
> 4.  <span data-ttu-id="20956-112">Prima di fare clic su **OK** per eseguire il pacchetto, scegliere **Script**.</span><span class="sxs-lookup"><span data-stu-id="20956-112">Before clicking **OK** to execute the package, click **Script**.</span></span> <span data-ttu-id="20956-113">Transact-SQL viene visualizzato in una finestra dell'editor di query in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20956-113">The Transact-SQL appears in a Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="to-deploy-and-execute-a-package-using-stored-procedures"></a><span data-ttu-id="20956-114">Per distribuire ed eseguire un pacchetto utilizzando le stored procedure</span><span class="sxs-lookup"><span data-stu-id="20956-114">To deploy and execute a package using stored procedures</span></span>  
  
1.  <span data-ttu-id="20956-115">Chiamare [catalog.deploy_project &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-deploy-project-ssisdb-database) per distribuire il progetto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che contiene il pacchetto sul server [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20956-115">Call [catalog.deploy_project &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-deploy-project-ssisdb-database) to deploy the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="20956-116">Per recuperare il contenuto binario del [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] file di distribuzione del progetto, per il parametro \* \@ project_stream\* usare un'istruzione SELECT con la funzione OPENROWSET e il provider bulk per set di righe.</span><span class="sxs-lookup"><span data-stu-id="20956-116">To retrieve the binary contents of the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project deployment file, for the *\@project_stream* parameter, use a SELECT statement with the OPENROWSET function and the BULK rowset provider.</span></span> <span data-ttu-id="20956-117">Questo provider consente di leggere i dati da un file.</span><span class="sxs-lookup"><span data-stu-id="20956-117">The BULK rowset provider enables you to read data from a file.</span></span> <span data-ttu-id="20956-118">Tramite l'argomento SINGLE_BLOB per il provider BULK per set di righe, il contenuto del file di dati viene restituito come un set di righe a riga e colonna singole di tipo varbinary(max).</span><span class="sxs-lookup"><span data-stu-id="20956-118">The SINGLE_BLOB argument for the BULK rowset provider returns the contents of the data file as a single-row, single-column rowset of type varbinary(max).</span></span> <span data-ttu-id="20956-119">Per altre informazioni, vedere [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="20956-119">For more information, see [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
     <span data-ttu-id="20956-120">Nell'esempio seguente, il progetto SSISPackages_ProjectDeployment viene distribuito nella cartella di pacchetti SSIS nel server [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="20956-120">In the following example, the SSISPackages_ProjectDeployment project is deployed to the SSIS Packages folder on the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="20956-121">I dati binari vengono letti dal file di progetto (SSISPackage_ProjectDeployment. ispac) e vengono archiviati nel parametro \* \@ ProjectBinary\* di tipo varbinary (max).</span><span class="sxs-lookup"><span data-stu-id="20956-121">The binary data is read from the project file (SSISPackage_ProjectDeployment.ispac) and is stored in the *\@ProjectBinary* parameter of type varbinary(max).</span></span> <span data-ttu-id="20956-122">Il valore del parametro \* \@ ProjectBinary\* viene assegnato al parametro \* \@ project_stream\* .</span><span class="sxs-lookup"><span data-stu-id="20956-122">The *\@ProjectBinary* parameter value is assigned to the *\@project_stream* parameter.</span></span>  
  
    ```  
    DECLARE @ProjectBinary as varbinary(max)  
    DECLARE @operation_id as bigint  
    Set @ProjectBinary = (SELECT * FROM OPENROWSET(BULK 'C:\MyProjects\ SSISPackage_ProjectDeployment.ispac', SINGLE_BLOB) as BinaryData)  
  
    Exec catalog.deploy_project @folder_name = 'SSIS Packages', @project_name = 'DeployViaStoredProc_SSIS', @Project_Stream = @ProjectBinary, @operation_id = @operation_id out  
  
    ```  
  
2.  <span data-ttu-id="20956-123">Chiamare [catalog.create_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database) per creare un'istanza di esecuzione del pacchetto e chiamare facoltativamente [catalog.set_execution_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database) per impostare i valori del parametro di runtime.</span><span class="sxs-lookup"><span data-stu-id="20956-123">Call [catalog.create_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database) to create an instance of the package execution, and optionally call [catalog.set_execution_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database) to set runtime parameter values.</span></span>  
  
     <span data-ttu-id="20956-124">Nell'esempio seguente, tramite catalog.create_execution viene creata un'istanza di esecuzione per package.dtsx che è contenuto nel progetto SSISPackage_ProjectDeployment.</span><span class="sxs-lookup"><span data-stu-id="20956-124">In the following example, catalog.create_execution creates an instance of execution for package.dtsx that is contained in the SSISPackage_ProjectDeployment project.</span></span> <span data-ttu-id="20956-125">Il progetto si trova nella cartella di pacchetti SSIS.</span><span class="sxs-lookup"><span data-stu-id="20956-125">The project is located in the SSIS Packages folder.</span></span> <span data-ttu-id="20956-126">Il valore di execution_id restituito dalla stored procedure viene utilizzato per la chiamata a catalog.set_execution_parameter_value.</span><span class="sxs-lookup"><span data-stu-id="20956-126">The execution_id returned by the stored procedure is used in the call to catalog.set_execution_parameter_value.</span></span> <span data-ttu-id="20956-127">Tramite questa seconda stored procedure il parametro LOGGING_LEVEL viene impostato su 3 (registrazione dettagliata) e un parametro del pacchetto denominato Parameter1 viene impostato su un valore 1.</span><span class="sxs-lookup"><span data-stu-id="20956-127">This second stored procedure sets the LOGGING_LEVEL parameter to 3 (verbose logging) and sets a package parameter named Parameter1 to a value of 1.</span></span>  
  
     <span data-ttu-id="20956-128">Per i parametri come LOGGING_LEVEL, il valore di object_type è 50.</span><span class="sxs-lookup"><span data-stu-id="20956-128">For parameters such as LOGGING_LEVEL the object_type value is 50.</span></span> <span data-ttu-id="20956-129">Per i parametri del pacchetto, il valore di object_type è 30.</span><span class="sxs-lookup"><span data-stu-id="20956-129">For package parameters the object_type value is 30.</span></span>  
  
    ```  
    Declare @execution_id bigint  
    EXEC [SSISDB].[catalog].[create_execution] @package_name=N'Package.dtsx', @execution_id=@execution_id OUTPUT, @folder_name=N'SSIS Packages', @project_name=N'SSISPackage_ProjectDeployment', @use32bitruntime=False, @reference_id=1  
  
    Select @execution_id  
    DECLARE @var0 smallint = 3  
    EXEC [SSISDB].[catalog].[set_execution_parameter_value] @execution_id,  @object_type=50, @parameter_name=N'LOGGING_LEVEL', @parameter_value=@var0  
  
    DECLARE @var1 int = 1  
    EXEC [SSISDB].[catalog].[set_execution_parameter_value] @execution_id,  @object_type=30, @parameter_name=N'Parameter1', @parameter_value=@var1  
  
    GO  
  
    ```  
  
3.  <span data-ttu-id="20956-130">Chiamare [catalog.start_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database) per eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="20956-130">Call [catalog.start_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database) to execute the package.</span></span>  
  
     <span data-ttu-id="20956-131">Nell'esempio seguente, una chiamata a catalog.start_execution viene aggiunta a Transact-SQL per avviare l'esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="20956-131">In the following example, a call to catalog.start_execution is added to the Transact-SQL to start the package execution.</span></span> <span data-ttu-id="20956-132">Viene utilizzato il valore di execution_id restituito dalla stored procedure catalog.create_execution.</span><span class="sxs-lookup"><span data-stu-id="20956-132">The execution_id returned by the catalog.create_execution stored procedure is used.</span></span>  
  
    ```  
    Declare @execution_id bigint  
    EXEC [SSISDB].[catalog].[create_execution] @package_name=N'Package.dtsx', @execution_id=@execution_id OUTPUT, @folder_name=N'SSIS Packages', @project_name=N'SSISPackage_ProjectDeployment', @use32bitruntime=False, @reference_id=1  
  
    Select @execution_id  
    DECLARE @var0 smallint = 3  
    EXEC [SSISDB].[catalog].[set_execution_parameter_value] @execution_id,  @object_type=50, @parameter_name=N'LOGGING_LEVEL', @parameter_value=@var0  
  
    DECLARE @var1 int = 1  
    EXEC [SSISDB].[catalog].[set_execution_parameter_value] @execution_id,  @object_type=30, @parameter_name=N'Parameter1', @parameter_value=@var1  
  
    EXEC [SSISDB].[catalog].[start_execution] @execution_id  
    GO  
  
    ```  
  
## <a name="to-deploy-a-project-from-server-to-server-using-stored-procedures"></a><span data-ttu-id="20956-133">Per distribuire un progetto da un server in un altro mediante stored procedure</span><span class="sxs-lookup"><span data-stu-id="20956-133">To deploy a project from server to server using stored procedures</span></span>  
 <span data-ttu-id="20956-134">È possibile distribuire un progetto da server a server tramite le stored procedure [catalog.get_project &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-get-project-ssisdb-database) e [catalog.deploy_project &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-deploy-project-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="20956-134">You can deploy a project from server to server by using the [catalog.get_project &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-get-project-ssisdb-database) and [catalog.deploy_project &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-deploy-project-ssisdb-database) stored procedures.</span></span>  
  
 <span data-ttu-id="20956-135">Prima di eseguire le stored procedure, è necessario effettuare le operazioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="20956-135">You need to do the following before running the stored procedures.</span></span>  
  
-   <span data-ttu-id="20956-136">Creare un oggetto server collegato.</span><span class="sxs-lookup"><span data-stu-id="20956-136">Create a linked server object.</span></span> <span data-ttu-id="20956-137">Per altre informazioni, vedere [Creare server collegati &#40;Motore di database di SQL Server&#41;](../database-engine/sql-server-database-engine-overview.md).</span><span class="sxs-lookup"><span data-stu-id="20956-137">For more information, see [Create Linked Servers &#40;SQL Server Database Engine&#41;](../database-engine/sql-server-database-engine-overview.md).</span></span>  
  
     <span data-ttu-id="20956-138">Nella pagina **Opzioni server** della finestra di dialogo **Proprietà server collegato** impostare **RPC** e **RPC Out** su **True**.</span><span class="sxs-lookup"><span data-stu-id="20956-138">On the **Server Options** page of the **Linked Server Properties** dialog box, set **RPC** and **RPC Out** to **True**.</span></span> <span data-ttu-id="20956-139">Impostare anche **Abilita innalzamento di livello delle transazioni distribuite per RPC** su **False**.</span><span class="sxs-lookup"><span data-stu-id="20956-139">Also, set **Enable Promotion of Distributed Transactions for RPC** to **False**.</span></span>  
  
-   <span data-ttu-id="20956-140">Abilitare i parametri dinamici per il provider selezionato per il server collegato espandendo il nodo **Provider** in **Server collegati** in Esplora oggetti, facendo clic con il pulsante destro del mouse sul provider e selezionando **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="20956-140">Enable dynamic parameters for the provider you selected for the linked server, by expanding the **Providers** node under **Linked Servers** in Object Explorer, right-clicking the provider, and then clicking **Properties**.</span></span> <span data-ttu-id="20956-141">Selezionare **Abilita** accanto a **Parametro dinamico**.</span><span class="sxs-lookup"><span data-stu-id="20956-141">Select **Enable** next to **Dynamic parameter.**</span></span>  
  
-   <span data-ttu-id="20956-142">Verificare che Distributed Transaction Coordinator (DTC) venga avviato in entrambi i server.</span><span class="sxs-lookup"><span data-stu-id="20956-142">Confirm that the Distributed Transaction Coordinator (DTC) is started on both servers.</span></span>  
  
 <span data-ttu-id="20956-143">Chiamare catalog.get_project per restituire i dati binari per il progetto, quindi chiamare catalog.deploy_project.</span><span class="sxs-lookup"><span data-stu-id="20956-143">Call catalog.get_project to return the binary for the project, and then call catalog.deploy_project.</span></span> <span data-ttu-id="20956-144">Il valore restituito da catalog.get_project viene inserito in una variabile di tabella di tipo varbinary(max).</span><span class="sxs-lookup"><span data-stu-id="20956-144">The value returned by catalog.get_project is inserted into a table variable of type varbinary(max).</span></span> <span data-ttu-id="20956-145">Tramite il server collegato non possono essere restituiti risultati di tipo varbinary(max).</span><span class="sxs-lookup"><span data-stu-id="20956-145">The linked server can't return results that are varbinary(max).</span></span>  
  
 <span data-ttu-id="20956-146">Nell'esempio seguente, tramite catalog.get_project viene restituito un file binario per il progetto SSISPackages nel server collegato.</span><span class="sxs-lookup"><span data-stu-id="20956-146">In the following example, catalog.get_project returns a binary for the SSISPackages project on the linked server.</span></span> <span data-ttu-id="20956-147">Tramite catalog.deploy_project il progetto viene distribuito nella cartella denominata DestFolder nel server locale.</span><span class="sxs-lookup"><span data-stu-id="20956-147">The catalog.deploy_project deploys the project to the local server, to the folder named DestFolder.</span></span>  
  
```  
declare @resultsTableVar table (  
project_binary varbinary(max)  
)  
  
INSERT @resultsTableVar (project_binary)  
EXECUTE [MyLinkedServer].[SSISDB].[catalog].[get_project] 'Packages', 'SSISPackages'  
  
declare @project_binary varbinary(max)  
select @project_binary = project_binary from @resultsTableVar  
  
exec [SSISDB].[CATALOG].[deploy_project] 'DestFolder', 'SSISPackages', @project_binary  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="20956-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20956-148">See Also</span></span>  
 <span data-ttu-id="20956-149">[Distribuire progetti nel server Integration Services](../../2014/integration-services/deploy-projects-to-integration-services-server.md) </span><span class="sxs-lookup"><span data-stu-id="20956-149">[Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md) </span></span>  
 <span data-ttu-id="20956-150">[Eseguire un pacchetto in SQL Server Data Tools](../../2014/integration-services/run-a-package-in-sql-server-data-tools.md) </span><span class="sxs-lookup"><span data-stu-id="20956-150">[Run a Package in SQL Server Data Tools](../../2014/integration-services/run-a-package-in-sql-server-data-tools.md) </span></span>  
 [<span data-ttu-id="20956-151">Eseguire un pacchetto sul server SSIS mediante SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="20956-151">Run a Package on the SSIS Server Using SQL Server Management Studio</span></span>](run-a-package-on-the-ssis-server-using-sql-server-management-studio.md)  
  
  
