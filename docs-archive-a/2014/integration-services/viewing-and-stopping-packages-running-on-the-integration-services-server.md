---
title: Visualizzazione e arresto dei pacchetti in esecuzione nel server Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], managing
- managing running packages [Integration Services]
- packages [Integration Services], running
- running package [Integration Services], managing
ms.assetid: 11bf44e6-f6b0-475f-b816-40e914dbac80
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6e63839d4ab5d8d50f7d86eea05c8d58107d6799
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636778"
---
# <a name="viewing-and-stopping-packages-running-on-the-integration-services-server"></a><span data-ttu-id="787b2-102">Visualizzazione e arresto dell'esecuzione dei pacchetti nel server Integration Services</span><span class="sxs-lookup"><span data-stu-id="787b2-102">Viewing and Stopping Packages Running on the Integration Services Server</span></span>
  <span data-ttu-id="787b2-103">Nel database di `SSISDB` la cronologia di esecuzione viene archiviata in tabelle interne che non sono visibili agli utenti.</span><span class="sxs-lookup"><span data-stu-id="787b2-103">The `SSISDB` database stores execution history in internal tables that are not visible to users.</span></span> <span data-ttu-id="787b2-104">Tuttavia, nel database vengono esposte le informazioni necessarie tramite viste pubbliche su cui è possibile eseguire una query.</span><span class="sxs-lookup"><span data-stu-id="787b2-104">However it exposes the information that you need through public views that you can query.</span></span> <span data-ttu-id="787b2-105">Inoltre, sono disponibili stored procedure che è possibile chiamare per eseguire attività comuni correlate ai pacchetti.</span><span class="sxs-lookup"><span data-stu-id="787b2-105">It also provides stored procedures that you can call to perform common tasks related to packages.</span></span>  
  
 <span data-ttu-id="787b2-106">In genere, gli oggetti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] vengono gestiti nel server in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="787b2-106">Typically you manage [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] objects on the server in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="787b2-107">Tuttavia, è anche possibile eseguire query sulle viste del database e chiamare direttamente le stored procedure oppure scrivere codice personalizzato con cui chiamare l'API gestita.</span><span class="sxs-lookup"><span data-stu-id="787b2-107">However you can also query the database views and call the stored procedures directly, or write custom code that calls the managed API.</span></span> [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="787b2-108">e l'API gestita eseguono query sulle viste e chiamano le stored procedure per eseguire molte delle relative attività.</span><span class="sxs-lookup"><span data-stu-id="787b2-108">and the managed API query the views and call the stored procedures to perform many of their tasks.</span></span> <span data-ttu-id="787b2-109">È ad esempio possibile visualizzare l'elenco di pacchetti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] attualmente in esecuzione nel server e, se necessario richiederne l'arresto.</span><span class="sxs-lookup"><span data-stu-id="787b2-109">For example, you can view the list of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages that are currently running on the server, and request packages to stop if you have to.</span></span>  
  
## <a name="viewing-the-list-of-running-packages"></a><span data-ttu-id="787b2-110">Visualizzazione dell'elenco di pacchetti in esecuzione</span><span class="sxs-lookup"><span data-stu-id="787b2-110">Viewing the List of Running Packages</span></span>  
 <span data-ttu-id="787b2-111">È possibile visualizzare l'elenco di pacchetti attualmente in esecuzione nel server nella finestra di dialogo **Operazioni attive** .</span><span class="sxs-lookup"><span data-stu-id="787b2-111">You can view the list of packages that are currently running on the server in the **Active Operations** dialog box.</span></span> <span data-ttu-id="787b2-112">Per altre informazioni, vedere [Active Operations Dialog Box](../../2014/integration-services/active-operations-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="787b2-112">For more information, see [Active Operations Dialog Box](../../2014/integration-services/active-operations-dialog-box.md).</span></span>  
  
 <span data-ttu-id="787b2-113">Per informazioni su altri metodi utilizzabili per visualizzare l'elenco di pacchetti in esecuzione, vedere gli argomenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="787b2-113">For information about the other methods that you can use to view the list of running packages, see the following topics.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="787b2-114">accesso</span><span class="sxs-lookup"><span data-stu-id="787b2-114">access</span></span>  
 <span data-ttu-id="787b2-115">Per visualizzare l'elenco di pacchetti in esecuzione nel server, eseguire una query sulla vista [catalog.executions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database) per i pacchetti con stato 2.</span><span class="sxs-lookup"><span data-stu-id="787b2-115">To view the list of packages that are running on the server, query the view, [catalog.executions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database) for packages that have a status of 2.</span></span>  
  
 <span data-ttu-id="787b2-116">Accesso a livello di codice tramite l'API gestita</span><span class="sxs-lookup"><span data-stu-id="787b2-116">Programmatic access through the managed API</span></span>  
 <span data-ttu-id="787b2-117">Vedere lo spazio dei nomi <xref:Microsoft.SqlServer.Management.IntegrationServices> e le relative classi.</span><span class="sxs-lookup"><span data-stu-id="787b2-117">See the <xref:Microsoft.SqlServer.Management.IntegrationServices> namespace and its classes.</span></span>  
  
## <a name="stopping-a-running-package"></a><span data-ttu-id="787b2-118">Arresto di un pacchetto in esecuzione</span><span class="sxs-lookup"><span data-stu-id="787b2-118">Stopping a Running Package</span></span>  
 <span data-ttu-id="787b2-119">È possibile richiedere l'arresto di un pacchetto in esecuzione nella finestra di dialogo **Operazioni attive** .</span><span class="sxs-lookup"><span data-stu-id="787b2-119">You can request a running package to stop in the **Active Operations** dialog box.</span></span> <span data-ttu-id="787b2-120">Per altre informazioni, vedere [Active Operations Dialog Box](../../2014/integration-services/active-operations-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="787b2-120">For more information, see [Active Operations Dialog Box](../../2014/integration-services/active-operations-dialog-box.md).</span></span>  
  
 <span data-ttu-id="787b2-121">Per informazioni su altri metodi utilizzabili per arrestare un pacchetto in esecuzione, vedere gli argomenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="787b2-121">For information about the other methods that you can use to stop a running package, see the following topics.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="787b2-122">accesso</span><span class="sxs-lookup"><span data-stu-id="787b2-122">access</span></span>  
 <span data-ttu-id="787b2-123">Per arrestare un pacchetto in esecuzione nel server, chiamare la stored procedure [catalog.stop_operation &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-stop-operation-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="787b2-123">To stop a package that is running on the server, call the stored procedure, [catalog.stop_operation &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-stop-operation-ssisdb-database).</span></span>  
  
 <span data-ttu-id="787b2-124">Accesso a livello di codice tramite l'API gestita</span><span class="sxs-lookup"><span data-stu-id="787b2-124">Programmatic access through the managed API</span></span>  
 <span data-ttu-id="787b2-125">Vedere lo spazio dei nomi <xref:Microsoft.SqlServer.Management.IntegrationServices> e le relative classi.</span><span class="sxs-lookup"><span data-stu-id="787b2-125">See the <xref:Microsoft.SqlServer.Management.IntegrationServices> namespace and its classes.</span></span>  
  
## <a name="viewing-the-history-of-packages-that-have-run"></a><span data-ttu-id="787b2-126">Visualizzazione della cronologia dei pacchetti eseguiti</span><span class="sxs-lookup"><span data-stu-id="787b2-126">Viewing the History of Packages That Have Run</span></span>  
 <span data-ttu-id="787b2-127">Per visualizzare la cronologia di pacchetti eseguiti in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], usare il report **Tutte le esecuzioni** .</span><span class="sxs-lookup"><span data-stu-id="787b2-127">To view the history of packages that have run in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], use the **All Executions** report.</span></span> <span data-ttu-id="787b2-128">Per altre informazioni sul report **Tutte le esecuzioni** e gli altri report standard, vedere [Visualizzare i report per il server Integration Services](../../2014/integration-services/reports-for-the-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="787b2-128">For more information on the **All Executions** report and other standard reports, see [Reports for the Integration Services Server](../../2014/integration-services/reports-for-the-integration-services-server.md).</span></span>  
  
 <span data-ttu-id="787b2-129">Per informazioni su altri metodi utilizzabili per visualizzare la cronologia di pacchetti in esecuzione, vedere gli argomenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="787b2-129">For information about the other methods that you can use to view the history of running packages, see the following topics.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="787b2-130">accesso</span><span class="sxs-lookup"><span data-stu-id="787b2-130">access</span></span>  
 <span data-ttu-id="787b2-131">Per visualizzare le informazioni sui pacchetti eseguiti, eseguire una query sulla vista [catalog.executions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="787b2-131">To view information about packages that have run, query the view, [catalog.executions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database).</span></span>  
  
 <span data-ttu-id="787b2-132">Accesso a livello di codice tramite l'API gestita</span><span class="sxs-lookup"><span data-stu-id="787b2-132">Programmatic access through the managed API</span></span>  
 <span data-ttu-id="787b2-133">Vedere lo spazio dei nomi <xref:Microsoft.SqlServer.Management.IntegrationServices> e le relative classi.</span><span class="sxs-lookup"><span data-stu-id="787b2-133">See the <xref:Microsoft.SqlServer.Management.IntegrationServices> namespace and its classes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="787b2-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="787b2-134">See Also</span></span>  
 <span data-ttu-id="787b2-135">[Esecuzione di progetti e pacchetti](packages/run-integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="787b2-135">[Execution of Projects and Packages](packages/run-integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="787b2-136">Report per la risoluzione dei problemi relativi all'esecuzione dei pacchetti</span><span class="sxs-lookup"><span data-stu-id="787b2-136">Troubleshooting Reports for Package Execution</span></span>](troubleshooting/troubleshooting-reports-for-package-execution.md)  
  
  
