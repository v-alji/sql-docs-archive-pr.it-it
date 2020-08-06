---
title: Esecuzione di progetti e pacchetti | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, running
- SSIS packages, running
- packages [Integration Services], running
- SQL Server Integration Services packages, running
- executing packages [Integration Services]
- running packages [Integration Services]
- Integration Services, (See also Integration Services packages)
ms.assetid: c5fecc23-6f04-4fb2-9a29-01492ea41404
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c50dc3d7ab909aa43e8f1f0e7017290538ac6476
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629891"
---
# <a name="execution-of-projects-and-packages"></a><span data-ttu-id="4c049-102">Esecuzione di progetti e pacchetti</span><span class="sxs-lookup"><span data-stu-id="4c049-102">Execution of Projects and Packages</span></span>
  <span data-ttu-id="4c049-103">Per eseguire un pacchetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , è possibile usare vari strumenti, a seconda della posizione in cui sono archiviati tali pacchetti.</span><span class="sxs-lookup"><span data-stu-id="4c049-103">To run an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package, you can use one of several tools depending on where those packages are stored.</span></span> <span data-ttu-id="4c049-104">Gli strumenti sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="4c049-104">The tools are listed in the table below.</span></span>  
  
 <span data-ttu-id="4c049-105">Per archiviare un pacchetto nel server [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , è possibile utilizzare il modello di distribuzione del progetto per distribuire il progetto nel server.</span><span class="sxs-lookup"><span data-stu-id="4c049-105">To store a package on the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server, you use the project deployment model to deploy the project to the server.</span></span> <span data-ttu-id="4c049-106">Per informazioni, vedere [Distribuire progetti nel server Integration Services](../deploy-projects-to-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="4c049-106">For information, see [Deploy Projects to Integration Services Server](../deploy-projects-to-integration-services-server.md).</span></span>  
  
 <span data-ttu-id="4c049-107">Per archiviare un pacchetto nell'archivio pacchetti SSIS, nel database msdb o nel file system, è possibile utilizzare il modello di distribuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="4c049-107">To store a package in the SSIS Package store, the msdb database, or in the file system, you use the package deployment model.</span></span> <span data-ttu-id="4c049-108">Per ulteriori informazioni, vedere [distribuzione di pacchetti &#40;&#41;SSIS ](legacy-package-deployment-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="4c049-108">For more information, see [Package Deployment &#40;SSIS&#41;](legacy-package-deployment-ssis.md).</span></span>  
  
|<span data-ttu-id="4c049-109">Strumento</span><span class="sxs-lookup"><span data-stu-id="4c049-109">Tool</span></span>|<span data-ttu-id="4c049-110">Pacchetti archiviati nel server Integration Services</span><span class="sxs-lookup"><span data-stu-id="4c049-110">Packages that are stored on the Integration Services server</span></span>|<span data-ttu-id="4c049-111">Pacchetti archiviati nell'archivio pacchetti SSIS o nel database msdb</span><span class="sxs-lookup"><span data-stu-id="4c049-111">Packages that are stored in the SSIS Package Store or in the msdb database</span></span>|<span data-ttu-id="4c049-112">Pacchetti archiviati nel file system, all'esterno del percorso che fa parte dell'archivio pacchetti SSIS</span><span class="sxs-lookup"><span data-stu-id="4c049-112">Packages that are stored in the file system, outside of the location that is part of the SSIS Package Store</span></span>|  
|----------|-----------------------------------------------------------------|--------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="4c049-113">**SQL Server Data Tools**</span><span class="sxs-lookup"><span data-stu-id="4c049-113">**SQL Server Data Tools**</span></span>|<span data-ttu-id="4c049-114">No</span><span class="sxs-lookup"><span data-stu-id="4c049-114">No</span></span>|<span data-ttu-id="4c049-115">No</span><span class="sxs-lookup"><span data-stu-id="4c049-115">No</span></span><br /><br /> <span data-ttu-id="4c049-116">È tuttavia possibile aggiungere un pacchetto esistente a un progetto dall'archivio pacchetti di [!INCLUDE[ssIS](../../includes/ssis-md.md)] , in cui è incluso il database msdb.</span><span class="sxs-lookup"><span data-stu-id="4c049-116">However, you can add an existing package to a project from the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Store, which includes the msdb database.</span></span> <span data-ttu-id="4c049-117">L'aggiunta di un pacchetto esistente al progetto comporta la creazione di una copia locale del pacchetto nel file system.</span><span class="sxs-lookup"><span data-stu-id="4c049-117">Adding an existing package to the project in this manner makes a local copy of the package in the file system.</span></span>|<span data-ttu-id="4c049-118">Sì</span><span class="sxs-lookup"><span data-stu-id="4c049-118">Yes</span></span>|  
|<span data-ttu-id="4c049-119">**SQL Server Management Studio, quando si è connessi a un'istanza del motore di database in cui è ospitato il server Integration Services**</span><span class="sxs-lookup"><span data-stu-id="4c049-119">**SQL Server Management Studio, when you are connected to an instance of the Database Engine that hosts the Integration Services server**</span></span><br /><br /> <span data-ttu-id="4c049-120">Per altre informazioni, vedere [Finestra di dialogo Esecuzione pacchetto](../execute-package-dialog-box.md)</span><span class="sxs-lookup"><span data-stu-id="4c049-120">For more information, see [Execute Package Dialog Box](../execute-package-dialog-box.md)</span></span>|<span data-ttu-id="4c049-121">Sì</span><span class="sxs-lookup"><span data-stu-id="4c049-121">Yes</span></span>|<span data-ttu-id="4c049-122">No</span><span class="sxs-lookup"><span data-stu-id="4c049-122">No</span></span><br /><br /> <span data-ttu-id="4c049-123">È tuttavia possibile importare un pacchetto nel server da questi percorsi.</span><span class="sxs-lookup"><span data-stu-id="4c049-123">However, you can import a package to the server from these locations.</span></span>|<span data-ttu-id="4c049-124">No</span><span class="sxs-lookup"><span data-stu-id="4c049-124">No</span></span><br /><br /> <span data-ttu-id="4c049-125">È tuttavia possibile importare un pacchetto nel server dal file system.</span><span class="sxs-lookup"><span data-stu-id="4c049-125">However, you can import a package to the server from the file system.</span></span>|  
|<span data-ttu-id="4c049-126">**SQL Server Management Studio, quando è connesso al servizio Integration Services che gestisce l'archivio pacchetti SSIS**</span><span class="sxs-lookup"><span data-stu-id="4c049-126">**SQL Server Management Studio, when it is connected to the Integration Services service that manages the SSIS Package Store**</span></span>|<span data-ttu-id="4c049-127">No</span><span class="sxs-lookup"><span data-stu-id="4c049-127">No</span></span>|<span data-ttu-id="4c049-128">Sì</span><span class="sxs-lookup"><span data-stu-id="4c049-128">Yes</span></span>|<span data-ttu-id="4c049-129">No</span><span class="sxs-lookup"><span data-stu-id="4c049-129">No</span></span><br /><br /> <span data-ttu-id="4c049-130">È tuttavia possibile importare un pacchetto nell'archivio pacchetti di [!INCLUDE[ssIS](../../includes/ssis-md.md)] dal file system.</span><span class="sxs-lookup"><span data-stu-id="4c049-130">However, you can import a package to the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Store from the file system.</span></span>|  
|<span data-ttu-id="4c049-131">**dtexec**</span><span class="sxs-lookup"><span data-stu-id="4c049-131">**dtexec**</span></span><br /><br /> <span data-ttu-id="4c049-132">Per altre informazioni, vedere [dtexec Utility](dtexec-utility.md).</span><span class="sxs-lookup"><span data-stu-id="4c049-132">For more information, see [dtexec Utility](dtexec-utility.md).</span></span>|<span data-ttu-id="4c049-133">Sì</span><span class="sxs-lookup"><span data-stu-id="4c049-133">Yes</span></span>|<span data-ttu-id="4c049-134">Sì</span><span class="sxs-lookup"><span data-stu-id="4c049-134">Yes</span></span>|<span data-ttu-id="4c049-135">Sì</span><span class="sxs-lookup"><span data-stu-id="4c049-135">Yes</span></span>|  
|<span data-ttu-id="4c049-136">**dtexecui**</span><span class="sxs-lookup"><span data-stu-id="4c049-136">**dtexecui**</span></span><br /><br /> <span data-ttu-id="4c049-137">Per altre informazioni, vedere [Riferimento all’interfaccia utente dell’utilità di esecuzione pacchetti &#40;DtExecUI&#41;](execute-package-utility-dtexecui-ui-reference.md)</span><span class="sxs-lookup"><span data-stu-id="4c049-137">For more information, see [Execute Package Utility &#40;DtExecUI&#41; UI Reference](execute-package-utility-dtexecui-ui-reference.md)</span></span>|<span data-ttu-id="4c049-138">No</span><span class="sxs-lookup"><span data-stu-id="4c049-138">No</span></span>|<span data-ttu-id="4c049-139">Sì</span><span class="sxs-lookup"><span data-stu-id="4c049-139">Yes</span></span>|<span data-ttu-id="4c049-140">Sì</span><span class="sxs-lookup"><span data-stu-id="4c049-140">Yes</span></span>|  
|<span data-ttu-id="4c049-141">**SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="4c049-141">**SQL Server Agent**</span></span><br /><br /> <span data-ttu-id="4c049-142">Per pianificare un pacchetto, è possibile utilizzare un processo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="4c049-142">You use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job To schedule a package.</span></span><br /><br /> <span data-ttu-id="4c049-143">Per altre informazioni, vedere [Processi di SQL Server Agent per i pacchetti](sql-server-agent-jobs-for-packages.md).</span><span class="sxs-lookup"><span data-stu-id="4c049-143">For more information, see [SQL Server Agent Jobs for Packages](sql-server-agent-jobs-for-packages.md).</span></span>|<span data-ttu-id="4c049-144">Sì</span><span class="sxs-lookup"><span data-stu-id="4c049-144">Yes</span></span>|<span data-ttu-id="4c049-145">Sì</span><span class="sxs-lookup"><span data-stu-id="4c049-145">Yes</span></span>|<span data-ttu-id="4c049-146">Sì</span><span class="sxs-lookup"><span data-stu-id="4c049-146">Yes</span></span>|  
|<span data-ttu-id="4c049-147">**Stored procedure predefinita**</span><span class="sxs-lookup"><span data-stu-id="4c049-147">**Built-in stored procedure**</span></span><br /><br /> <span data-ttu-id="4c049-148">Per altre informazioni, vedere [catalog.start_execution &#40;database SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database)</span><span class="sxs-lookup"><span data-stu-id="4c049-148">For more information, see [catalog.start_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database)</span></span>|<span data-ttu-id="4c049-149">Sì</span><span class="sxs-lookup"><span data-stu-id="4c049-149">Yes</span></span>|<span data-ttu-id="4c049-150">No</span><span class="sxs-lookup"><span data-stu-id="4c049-150">No</span></span>|<span data-ttu-id="4c049-151">No</span><span class="sxs-lookup"><span data-stu-id="4c049-151">No</span></span>|  
|<span data-ttu-id="4c049-152">**API gestita, tramite tipi e membri dello spazio dei nomi**  <xref:Microsoft.SqlServer.Management.IntegrationServices></span><span class="sxs-lookup"><span data-stu-id="4c049-152">**Managed API, by using types and members in the** <xref:Microsoft.SqlServer.Management.IntegrationServices> namespace</span></span>|<span data-ttu-id="4c049-153">Sì</span><span class="sxs-lookup"><span data-stu-id="4c049-153">Yes</span></span>|<span data-ttu-id="4c049-154">No</span><span class="sxs-lookup"><span data-stu-id="4c049-154">No</span></span>|<span data-ttu-id="4c049-155">No</span><span class="sxs-lookup"><span data-stu-id="4c049-155">No</span></span>|  
|<span data-ttu-id="4c049-156">**API gestita, tramite tipi e membri dello spazio dei nomi**  <xref:Microsoft.SqlServer.Dts.Runtime></span><span class="sxs-lookup"><span data-stu-id="4c049-156">**Managed API, by using types and members in the** <xref:Microsoft.SqlServer.Dts.Runtime> namespace</span></span>|<span data-ttu-id="4c049-157">Non attualmente</span><span class="sxs-lookup"><span data-stu-id="4c049-157">Not currently</span></span>|<span data-ttu-id="4c049-158">Sì</span><span class="sxs-lookup"><span data-stu-id="4c049-158">Yes</span></span>|<span data-ttu-id="4c049-159">Sì</span><span class="sxs-lookup"><span data-stu-id="4c049-159">Yes</span></span>|  
  
## <a name="execution-and-logging"></a><span data-ttu-id="4c049-160">Esecuzione e registrazione</span><span class="sxs-lookup"><span data-stu-id="4c049-160">Execution and Logging</span></span>  
 <span data-ttu-id="4c049-161">È possibile abilitare la registrazione per i pacchetti di[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , nonché acquisire informazioni di run-time in file di log.</span><span class="sxs-lookup"><span data-stu-id="4c049-161">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages can be enabled for logging and you can capture run-time information in log files.</span></span> <span data-ttu-id="4c049-162">Per altre informazioni, vedere [registrazione di Integration Services &#40;SSIS&#41;](../performance/integration-services-ssis-logging.md).</span><span class="sxs-lookup"><span data-stu-id="4c049-162">For more information, see [Integration Services &#40;SSIS&#41; Logging](../performance/integration-services-ssis-logging.md).</span></span>  
  
 <span data-ttu-id="4c049-163">Per monitorare i pacchetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che vengono distribuiti ed eseguiti nel server [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , utilizzare i report delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="4c049-163">You can monitor [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages that are deployed to and run on the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server by using operation reports.</span></span> <span data-ttu-id="4c049-164">I report sono disponibili in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c049-164">The reports are available in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="4c049-165">Per altre informazioni, vedere [report per il server Integration Services](../reports-for-the-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="4c049-165">For more information, see [Reports for the Integration Services Server](../reports-for-the-integration-services-server.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="4c049-166">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="4c049-166">Related Tasks</span></span>  
  
-   [<span data-ttu-id="4c049-167">Pianificare un pacchetto tramite SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="4c049-167">Schedule a Package by using SQL Server Agent</span></span>](../schedule-a-package-by-using-sql-server-agent.md)  
  
-   [<span data-ttu-id="4c049-168">Eseguire un pacchetto in SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="4c049-168">Run a Package in SQL Server Data Tools</span></span>](../run-a-package-in-sql-server-data-tools.md)  
  
-   [<span data-ttu-id="4c049-169">Eseguire un pacchetto sul server SSIS mediante SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4c049-169">Run a Package on the SSIS Server Using SQL Server Management Studio</span></span>](../run-a-package-on-the-ssis-server-using-sql-server-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="4c049-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c049-170">See Also</span></span>  
 <span data-ttu-id="4c049-171">[Utilità dtexec](dtexec-utility.md) </span><span class="sxs-lookup"><span data-stu-id="4c049-171">[dtexec Utility](dtexec-utility.md) </span></span>  
 [<span data-ttu-id="4c049-172">Importazione/Esportazione guidata SQL Server</span><span class="sxs-lookup"><span data-stu-id="4c049-172">SQL Server Import and Export Wizard</span></span>](../import-export-data/import-and-export-data-with-the-sql-server-import-and-export-wizard.md)  
  
  