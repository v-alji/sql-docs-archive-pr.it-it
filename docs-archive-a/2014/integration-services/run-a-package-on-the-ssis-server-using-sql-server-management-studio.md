---
title: Eseguire un pacchetto nel server SSIS utilizzando SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 56dc1bf8-99d4-41dc-bdc4-f64f1ccfd688
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d17009988dea54621d4fd7ef542cf452bfe95c6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713239"
---
# <a name="run-a-package-on-the-ssis-server-using-sql-server-management-studio"></a><span data-ttu-id="a3d6f-102">Eseguire un pacchetto sul server SSIS mediante SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a3d6f-102">Run a Package on the SSIS Server Using SQL Server Management Studio</span></span>
  <span data-ttu-id="a3d6f-103">Dopo aver distribuito il progetto nel server [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , è possibile eseguire il pacchetto nel server.</span><span class="sxs-lookup"><span data-stu-id="a3d6f-103">After you deploy your project to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server, you can run the package on the server.</span></span>  
  
 <span data-ttu-id="a3d6f-104">È possibile utilizzare i report relativi alle operazioni per visualizzare informazioni sui pacchetti eseguiti, o che sono attualmente in esecuzione, nel server.</span><span class="sxs-lookup"><span data-stu-id="a3d6f-104">You can use operations reports to view information about packages that have run, or are currently running, on the server.</span></span> <span data-ttu-id="a3d6f-105">Per altre informazioni, vedere [report per il server Integration Services](../../2014/integration-services/reports-for-the-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="a3d6f-105">For more information, see [Reports for the Integration Services Server](../../2014/integration-services/reports-for-the-integration-services-server.md).</span></span>  
  
### <a name="to-run-a-package-on-the-server-using-sql-server-management-studio"></a><span data-ttu-id="a3d6f-106">Per eseguire un pacchetto nel server mediante SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a3d6f-106">To run a package on the server using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="a3d6f-107">Aprire [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] e connettersi all'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] in cui è contenuto il catalogo di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a3d6f-107">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that contains the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] catalog.</span></span>  
  
2.  <span data-ttu-id="a3d6f-108">In Esplora oggetti espandere il nodo **Cataloghi di Integration Services** , il nodo **SSISDB** e navigare al pacchetto contenuto nel progetto distribuito.</span><span class="sxs-lookup"><span data-stu-id="a3d6f-108">In Object Explorer, expand the **Integration Services Catalogs** node, expand the **SSISDB** node, and navigate to the package contained in the project you deployed.</span></span>  
  
3.  <span data-ttu-id="a3d6f-109">Fare clic con il pulsante destro del mouse sul nome del pacchetto e selezionare **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="a3d6f-109">Right-click the package name and select **Execute**.</span></span>  
  
4.  <span data-ttu-id="a3d6f-110">Configurare l'esecuzione del pacchetto usando le impostazioni sulle schede **Parametri**, **Gestioni connessioni**e **Avanzate** nella finestra di dialogo **Esegui pacchetto** .</span><span class="sxs-lookup"><span data-stu-id="a3d6f-110">Configure the package execution by using the settings on the **Parameters**, **Connection Managers**, and **Advanced** tabs in the **Execute Package** dialog box.</span></span>  
  
5.  <span data-ttu-id="a3d6f-111">Fare clic su **OK** per eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="a3d6f-111">Click **OK** to run the package.</span></span>  
  
     <span data-ttu-id="a3d6f-112">-oppure-</span><span class="sxs-lookup"><span data-stu-id="a3d6f-112">-or-</span></span>  
  
     <span data-ttu-id="a3d6f-113">Utilizzare le stored procedure per eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="a3d6f-113">Use stored procedures to run the package.</span></span> <span data-ttu-id="a3d6f-114">Fare clic su **Script** per generare l'istruzione Transact-SQL tramite cui viene creata e avviata un'istanza dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a3d6f-114">Click **Script** to generate the Transact-SQL statement that creates an instance of the execution and starts an instance of the execution.</span></span> <span data-ttu-id="a3d6f-115">Nell'istruzione è inclusa una chiamata alle stored procedure catalog.create_execution, catalog.set_execution_parameter_value e catalog.start_execution.</span><span class="sxs-lookup"><span data-stu-id="a3d6f-115">The statement includes a call to the catalog.create_execution, catalog.set_execution_parameter_value, and catalog.start_execution stored procedures.</span></span> <span data-ttu-id="a3d6f-116">Per altre informazioni su queste stored procedure, vedere [catalog.create_execution &#40;database SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database), [catalog.set_execution_parameter_value &#40;database SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database) e [catalog.start_execution &#40;database SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="a3d6f-116">For more information about these stored procedures, see [catalog.create_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database), [catalog.set_execution_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database), and [catalog.start_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database).</span></span>  
  
  
