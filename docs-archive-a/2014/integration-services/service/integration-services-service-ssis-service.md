---
title: Servizio Integration Services (servizio SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services service, about Integration Services service
- SQL Server Integration Services service
- service [Integration Services],about Integration Services service
- service [Integration Services]
- SQL Server Integration Services, service
ms.assetid: 2c785b3b-4a0c-4df7-b5cd-23756dc87842
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 04b24f0f0d54009c50654904d606a208504f229c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726071"
---
# <a name="integration-services-service-ssis-service"></a><span data-ttu-id="83767-102">Servizio Integration Services (servizio SSIS)</span><span class="sxs-lookup"><span data-stu-id="83767-102">Integration Services Service (SSIS Service)</span></span>
  <span data-ttu-id="83767-103">Negli argomenti contenuti in questa sezione viene illustrato il servizio [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , un servizio Windows per la gestione dei pacchetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83767-103">The topics in this section discuss the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="83767-104">Questo servizio non è necessario per creare, salvare ed eseguire i pacchetti di Integration Services.</span><span class="sxs-lookup"><span data-stu-id="83767-104">This service is not required to create, save, and run Integration Services packages.</span></span> [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] <span data-ttu-id="83767-105">supporta il servizio [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] per la compatibilità con le versioni precedenti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83767-105">supports the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="83767-106">A partire da [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] archivia gli oggetti, le impostazioni e i dati operativi nel `SSISDB` database per i progetti distribuiti nel [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server usando il modello di distribuzione del progetto.</span><span class="sxs-lookup"><span data-stu-id="83767-106">Starting in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] stores objects, settings, and operational data in the `SSISDB` database for projects that you've deployed to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server using the project deployment model.</span></span> <span data-ttu-id="83767-107">Nel server [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , che è un'istanza del motore di database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , è ospitato il database.</span><span class="sxs-lookup"><span data-stu-id="83767-107">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server, which is an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Database Engine, hosts the database.</span></span> <span data-ttu-id="83767-108">Per altre informazioni sul database, vedere [Catalogo SSIS](../catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="83767-108">For more information about the database, see [SSIS Catalog](../catalog/ssis-catalog.md).</span></span> <span data-ttu-id="83767-109">Per altre informazioni sulla distribuzione di progetti nel server [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , vedere [Distribuire progetti nel server Integration Services](../deploy-projects-to-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="83767-109">For more information about deploying projects to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server, see [Deploy Projects to Integration Services Server](../deploy-projects-to-integration-services-server.md).</span></span>  
  
## <a name="management-capabilities"></a><span data-ttu-id="83767-110">Funzionalità di gestione</span><span class="sxs-lookup"><span data-stu-id="83767-110">Management Capabilities</span></span>  
 <span data-ttu-id="83767-111">Il servizio [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] è un servizio Windows per la gestione di pacchetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83767-111">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is a Windows service for managing [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="83767-112">Il servizio [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] è disponibile solo in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83767-112">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is available only in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="83767-113">Il servizio [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] consente di eseguire le attività di gestione seguenti:</span><span class="sxs-lookup"><span data-stu-id="83767-113">Running the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service provides the following management capabilities:</span></span>  
  
-   <span data-ttu-id="83767-114">Avvio di pacchetti locali o archiviati in una posizione remota</span><span class="sxs-lookup"><span data-stu-id="83767-114">Starting remote and locally stored packages</span></span>  
  
-   <span data-ttu-id="83767-115">Arresto di pacchetti eseguiti localmente o in modalità remota</span><span class="sxs-lookup"><span data-stu-id="83767-115">Stopping remote and locally running packages</span></span>  
  
-   <span data-ttu-id="83767-116">Monitoraggio di pacchetti eseguiti localmente o in modalità remota</span><span class="sxs-lookup"><span data-stu-id="83767-116">Monitoring remote and locally running packages</span></span>  
  
-   <span data-ttu-id="83767-117">Importazione ed esportazione di pacchetti</span><span class="sxs-lookup"><span data-stu-id="83767-117">Importing and exporting packages</span></span>  
  
-   <span data-ttu-id="83767-118">Gestione dell'archiviazione di pacchetti</span><span class="sxs-lookup"><span data-stu-id="83767-118">Managing package storage</span></span>  
  
-   <span data-ttu-id="83767-119">Personalizzazione delle cartelle di archiviazione</span><span class="sxs-lookup"><span data-stu-id="83767-119">Customizing storage folders</span></span>  
  
-   <span data-ttu-id="83767-120">Arresto dei pacchetti in esecuzione quando il servizio viene arrestato</span><span class="sxs-lookup"><span data-stu-id="83767-120">Stopping running packages when the service is stopped</span></span>  
  
-   <span data-ttu-id="83767-121">Visualizzazione del registro eventi di Windows</span><span class="sxs-lookup"><span data-stu-id="83767-121">Viewing the Windows Event log</span></span>  
  
-   <span data-ttu-id="83767-122">Connessione a più server [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83767-122">Connecting to multiple [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] servers</span></span>  
  
## <a name="startup-type-for-integration-services-service"></a><span data-ttu-id="83767-123">Tipo di avvio per il servizio Integration Services</span><span class="sxs-lookup"><span data-stu-id="83767-123">Startup Type for Integration Services Service</span></span>  
 <span data-ttu-id="83767-124">Il servizio [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] viene installato quando si installa il componente [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83767-124">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is installed when you install the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] component of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="83767-125">Per impostazione predefinita, il servizio [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] viene avviato in base al tipo di avvio automatico.</span><span class="sxs-lookup"><span data-stu-id="83767-125">By default, the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is started and the startup type of the service is set to automatic.</span></span> <span data-ttu-id="83767-126">È necessario che sia in esecuzione se si desidera eseguire il monitoraggio dei pacchetti archiviati nell'archivio pacchetti [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83767-126">The service must be running to monitor the packages that are stored in the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Store.</span></span> <span data-ttu-id="83767-127">L'archivio pacchetti [!INCLUDE[ssIS](../../includes/ssis-md.md)] può essere il database msdb di un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o le cartelle designate del file system.</span><span class="sxs-lookup"><span data-stu-id="83767-127">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Store can be either the msdb database in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or the designated folders in the file system.</span></span>  
  
 <span data-ttu-id="83767-128">Il servizio [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] non è necessario se si desidera semplicemente progettare ed eseguire pacchetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83767-128">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is not required if you only want to design and execute [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="83767-129">È invece necessario per elencare e monitorare i pacchetti tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83767-129">However, the service is required to list and monitor packages using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="83767-130">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="83767-130">Related Tasks</span></span>  
  
-   [<span data-ttu-id="83767-131">Impostare le proprietà del servizio Integration Services</span><span class="sxs-lookup"><span data-stu-id="83767-131">Set the Properties of the Integration Services Service</span></span>](../set-the-properties-of-the-integration-services-service.md)  
  
-   [<span data-ttu-id="83767-132">Visualizzare eventi per il servizio Integration Services</span><span class="sxs-lookup"><span data-stu-id="83767-132">View Events for the Integration Services Service</span></span>](../view-events-for-the-integration-services-service.md)  
  
  
