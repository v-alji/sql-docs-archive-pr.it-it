---
title: Server Integration Services (SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], managing
- managing packages [Integration Services]
ms.assetid: 6d667bba-7c25-492a-8f4d-70ebaca28f40
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a0da83cdac269499dfbde7a6387a4af4690c83ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629990"
---
# <a name="integration-services-ssis-server"></a><span data-ttu-id="25608-102">Server Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="25608-102">Integration Services (SSIS) Server</span></span>
  <span data-ttu-id="25608-103">Dopo aver progettato e testato i pacchetti in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], è possibile distribuire i progetti contenenti i pacchetti nel server [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25608-103">After you design and test packages in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], you can deploy the projects that contain the packages to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
 <span data-ttu-id="25608-104">Il server [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] è un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] in cui viene ospitato il database di `SSISDB`.</span><span class="sxs-lookup"><span data-stu-id="25608-104">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server is an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the `SSISDB` database.</span></span> <span data-ttu-id="25608-105">Nel database vengono archiviati gli oggetti seguenti: pacchetti, progetti, parametri, autorizzazioni, proprietà del server e cronologia operativa.</span><span class="sxs-lookup"><span data-stu-id="25608-105">The database stores the following objects: packages, projects, parameters, permissions, server properties, and operational history.</span></span>  
  
 <span data-ttu-id="25608-106">Tramite il database `SSISDB` vengono esposte le informazioni sull'oggetto nelle viste pubbliche su cui è possibile eseguire query.</span><span class="sxs-lookup"><span data-stu-id="25608-106">The `SSISDB` database exposes the object information in public views that you can query.</span></span> <span data-ttu-id="25608-107">Nel database sono inoltre disponibili stored procedure che è possibile chiamare per gestire gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="25608-107">The database also provides stored procedures that you can call to manage the objects.</span></span>  
  
 <span data-ttu-id="25608-108">Prima di poter distribuire i progetti nel server [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], è necessario creare il catalogo `SSISDB`.</span><span class="sxs-lookup"><span data-stu-id="25608-108">Before you can deploy the projects to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server, you need to create the `SSISDB` catalog.</span></span>  
  
 <span data-ttu-id="25608-109">Per una panoramica della funzionalità del catalogo SSISDB, vedere [Catalogo SSISDB](ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="25608-109">For an overview of the SSISDB catalog functionality, see [SSIS Catalog](ssis-catalog.md).</span></span>  
  
## <a name="high-availability"></a><span data-ttu-id="25608-110">Disponibilità elevata</span><span class="sxs-lookup"><span data-stu-id="25608-110">High Availability</span></span>  
 <span data-ttu-id="25608-111">Analogamente ad altri database utente, il database `SSISDB` supporta il mirroring del database e la replica.</span><span class="sxs-lookup"><span data-stu-id="25608-111">Like other user databases, the `SSISDB` database does support database mirroring and replication.</span></span> <span data-ttu-id="25608-112">Per altre informazioni sul mirroring e la replica, vedere [Mirroring del database &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="25608-112">For more information about mirroring and replication, see [Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md).</span></span>  
  
 <span data-ttu-id="25608-113">È inoltre possibile fornire la disponibilità elevata di SSISDB e i relativi contenuti utilizzando i gruppi di disponibilità SSIS e AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="25608-113">You can also provide high-availability of SSISDB and its contents by making use of SSIS and AlwaysOn Availability Groups.</span></span> <span data-ttu-id="25608-114">Per ulteriori informazioni, vedere il post sul blog di Matt Masson relativo a [SSIS con AlwaysOn](https://go.microsoft.com/fwlink/?LinkId=255873)sul sito Web blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="25608-114">For more information, see this blog post by Matt Masson, [SSIS with AlwaysOn](https://go.microsoft.com/fwlink/?LinkId=255873), at blogs.msdn.com.</span></span>  
  
##  <a name="integration-services-server-in-sql-server-management-studio"></a><a name="ssms"></a><span data-ttu-id="25608-115">Server Integration Services in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="25608-115">Integration Services Server in SQL Server Management Studio</span></span>  
 <span data-ttu-id="25608-116">Quando si stabilisce la connessione a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] in cui è ospitato il database `SSISDB`, gli oggetti seguenti sono visibili in Esplora oggetti:</span><span class="sxs-lookup"><span data-stu-id="25608-116">When you connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the `SSISDB` database, you see the following objects in Object Explorer:</span></span>  
  
-   <span data-ttu-id="25608-117">**Database SSISDB**</span><span class="sxs-lookup"><span data-stu-id="25608-117">**SSISDB Database**</span></span>  
  
     <span data-ttu-id="25608-118">Il `SSISDB` database viene visualizzato nel nodo **database** in Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="25608-118">The `SSISDB` database appears under the **Databases** node in Object Explore.</span></span> <span data-ttu-id="25608-119">È possibile eseguire una query sulle viste e chiamare le stored procedure tramite cui vengono gestiti il server [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] e gli oggetti archiviati nel server.</span><span class="sxs-lookup"><span data-stu-id="25608-119">You can query the views and call the stored procedures that manage the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server and the objects that are stored on the server.</span></span>  
  
-   <span data-ttu-id="25608-120">**Cataloghi di Integration Services**</span><span class="sxs-lookup"><span data-stu-id="25608-120">**Integration Services Catalogs**</span></span>  
  
     <span data-ttu-id="25608-121">Nel nodo **Cataloghi di Integration Services** sono presenti cartelle per i progetti e gli ambienti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25608-121">Under the **Integration Services Catalogs** node there are folders for [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] projects and environments.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="25608-122">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="25608-122">Related Tasks</span></span>  
  
-   [<span data-ttu-id="25608-123">Creare il catalogo SSIS</span><span class="sxs-lookup"><span data-stu-id="25608-123">Create the SSIS Catalog</span></span>](../create-the-ssis-catalog.md)  
  
-   [<span data-ttu-id="25608-124">Visualizzare l'elenco di pacchetti nel server Integration Services</span><span class="sxs-lookup"><span data-stu-id="25608-124">View the List of Packages on the Integration Services Server</span></span>](view-the-list-of-packages-on-the-integration-services-server.md)  
  
-   [<span data-ttu-id="25608-125">Distribuire progetti nel server Integration Services</span><span class="sxs-lookup"><span data-stu-id="25608-125">Deploy Projects to Integration Services Server</span></span>](../deploy-projects-to-integration-services-server.md)  
  
-   [<span data-ttu-id="25608-126">Eseguire un pacchetto sul server SSIS mediante SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="25608-126">Run a Package on the SSIS Server Using SQL Server Management Studio</span></span>](../run-a-package-on-the-ssis-server-using-sql-server-management-studio.md)  
  
## <a name="related-content"></a><span data-ttu-id="25608-127">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="25608-127">Related Content</span></span>  
 <span data-ttu-id="25608-128">Intervento sul blog relativo a [SSIS con AlwaysOn](https://go.microsoft.com/fwlink/?LinkId=255873)sul sito Web blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="25608-128">Blog entry, [SSIS with AlwaysOn](https://go.microsoft.com/fwlink/?LinkId=255873), at blogs.msdn.com.</span></span>  
  
  
