---
title: Requisiti hardware e software per Reporting Services in modalità SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 01/09/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ed91877d-4f74-4266-a932-b824b4810c99
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: a4fc19b2871d7d5731649c61a8d5231d7e3479dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637061"
---
# <a name="hardware-and-software-requirements-for-reporting-services-in-sharepoint-mode"></a><span data-ttu-id="486cb-102">Requisiti hardware e software per Reporting Services in modalità SharePoint</span><span class="sxs-lookup"><span data-stu-id="486cb-102">Hardware and Software Requirements for Reporting Services in SharePoint Mode</span></span>

  <span data-ttu-id="486cb-103">In questo argomento vengono descritti i prerequisiti, i requisiti hardware e le considerazioni sull'installazione per l' [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] esecuzione in modalità SharePoint.</span><span class="sxs-lookup"><span data-stu-id="486cb-103">This topic describes prerequisites, hardware requirements, and installation considerations for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] running in SharePoint mode.</span></span> <span data-ttu-id="486cb-104">Dal momento la modalità SharePoint di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] richiede un server SharePoint, la maggior parte dei requisiti sono basati sull'ambiente SharePoint.</span><span class="sxs-lookup"><span data-stu-id="486cb-104">Because [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode requires a SharePoint server, most of the requirements are based on the SharePoint environment.</span></span> <span data-ttu-id="486cb-105">Per i server di report in modalità nativa è consigliabile soddisfare i requisiti hardware e software minimi per l'esecuzione di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="486cb-105">For native mode report servers, your hardware should meet minimum hardware and software requirements for running [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="486cb-106">Per ulteriori informazioni, vedere [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="486cb-106">For more information, see [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span></span>  
  
-   [<span data-ttu-id="486cb-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="486cb-107">Prerequisites</span></span>](#bkmk_prereq)  
  
-   [<span data-ttu-id="486cb-108">Requisiti del database del server di report</span><span class="sxs-lookup"><span data-stu-id="486cb-108">Report Server Database Requirements</span></span>](#bkmk_report_server_database)  
  
-   [<span data-ttu-id="486cb-109">Requisiti per Power View</span><span class="sxs-lookup"><span data-stu-id="486cb-109">Power View Requirements</span></span>](#bkmk_powerview)  
  
-   [<span data-ttu-id="486cb-110">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="486cb-110">More Information</span></span>](#bkmk_more_information)  
  
##  <a name="prerequisites"></a><a name="bkmk_prereq"></a> <span data-ttu-id="486cb-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="486cb-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="486cb-112">Per le installazioni locali, l'account connesso durante l'installazione di SharePoint e [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] deve essere un membro del gruppo di amministratori del sistema operativo locale.</span><span class="sxs-lookup"><span data-stu-id="486cb-112">For local installations, the account logged in during installation of SharePoint and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] needs to be a member of the administrators group in the local operating system.</span></span> <span data-ttu-id="486cb-113">L'account di configurazione non deve essere un membro del gruppo di amministratori della farm di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="486cb-113">The setup account does not need to be a member of the SharePoint farm administrators group.</span></span>  
  
     <span data-ttu-id="486cb-114">Per ulteriori informazioni, vedere [Autorizzazioni e impostazioni di sicurezza per gli account in SharePoint Server 2013](https://technet.microsoft.com/library/cc678863.aspx).</span><span class="sxs-lookup"><span data-stu-id="486cb-114">For more information, see [Account permissions and security settings in SharePoint 2013](https://technet.microsoft.com/library/cc678863.aspx).</span></span>  
  
-   <span data-ttu-id="486cb-115">Per [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in esecuzione in modalità SharePoint è richiesto il server SharePoint.</span><span class="sxs-lookup"><span data-stu-id="486cb-115">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] running in SharePoint mode requires SharePoint Server.</span></span> <span data-ttu-id="486cb-116">Per ulteriori informazioni sui requisiti e sulle configurazioni di SharePoint, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="486cb-116">For more information about SharePoint requirements and configurations, see the following:</span></span>  
  
    -   <span data-ttu-id="486cb-117">[Requisiti hardware e software (SharePoint 2013)](https://go.microsoft.com/fwlink/p/?LinkId=256365) (https://go.microsoft.com/fwlink/p/?LinkId=256365)</span><span class="sxs-lookup"><span data-stu-id="486cb-117">[Hardware and software requirements (SharePoint 2013)](https://go.microsoft.com/fwlink/p/?LinkId=256365) (https://go.microsoft.com/fwlink/p/?LinkId=256365)</span></span>  
  
    -   [<span data-ttu-id="486cb-118">Gestione e ridimensionamento delle capacità per SharePoint Server 2013</span><span class="sxs-lookup"><span data-stu-id="486cb-118">Capacity management and sizing for SharePoint Server 2013</span></span>](https://technet.microsoft.com/library/cc261700.aspx)  
  
    -   [<span data-ttu-id="486cb-119">Requisiti software per Business Intelligence (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="486cb-119">Software requirements for business intelligence (SharePoint 2013)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=256367)  
  
    -   <span data-ttu-id="486cb-120">[Requisiti hardware e software (SharePoint Server 2010)](https://technet.microsoft.com/library/cc262485\(v=office.14\))</span><span class="sxs-lookup"><span data-stu-id="486cb-120">[Hardware and software requirements (SharePoint Server 2010)](https://technet.microsoft.com/library/cc262485\(v=office.14\))</span></span>  
  
    -   <span data-ttu-id="486cb-121">[Gestione e ridimensionamento delle capacità per SharePoint Server 2010](https://technet.microsoft.com/library/cc261700.aspx\(v=office.14\))</span><span class="sxs-lookup"><span data-stu-id="486cb-121">[Capacity management and sizing for SharePoint Server 2010](https://technet.microsoft.com/library/cc261700.aspx\(v=office.14\))</span></span>  
  
-   <span data-ttu-id="486cb-122">Se si desidera aggiornare l'installazione esistente di SharePoint per [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] con [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], vedere [Upgrade and Migrate Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="486cb-122">If you want to upgrade or update existing [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint installation with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], see [Upgrade and Migrate Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md).</span></span>  
  
-   <span data-ttu-id="486cb-123">Verificare che il servizio **SharePoint 2013 Administration** venga avviato in Server Manager di Windows.</span><span class="sxs-lookup"><span data-stu-id="486cb-123">Verify the **SharePoint 2013 Administration** service is started in Windows Server Manager.</span></span>  
  
###  <a name="report-server-database-requirements"></a><a name="bkmk_report_server_database"></a> <span data-ttu-id="486cb-124">Requisiti del database del server di report</span><span class="sxs-lookup"><span data-stu-id="486cb-124">Report Server Database Requirements</span></span>  
  
-   <span data-ttu-id="486cb-125">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e nei prodotti e nelle tecnologie SharePoint vengono utilizzati database relazionali di SQL Server per archiviare i dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="486cb-125">Both [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and SharePoint products and technologies use SQL Server relational databases to store application data.</span></span>  
  
-   [!INCLUDE[ssRSCurrent](../../includes/ssrscurrent-md.md)] <span data-ttu-id="486cb-126">richiede un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] di un'edizione di SQL Server compatibile.</span><span class="sxs-lookup"><span data-stu-id="486cb-126">requires an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] of a compatible SQL Server edition.</span></span> <span data-ttu-id="486cb-127">Per ulteriori informazioni sui requisiti hardware e software, vedere [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="486cb-127">For more information on hardware and software requirements, see [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span></span>  
  
-   <span data-ttu-id="486cb-128">Nei prodotti SharePoint può essere utilizzata un'istanza del database esistente.</span><span class="sxs-lookup"><span data-stu-id="486cb-128">SharePoint products can use an existing database instance.</span></span> <span data-ttu-id="486cb-129">Se non è installata alcuna istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] , tramite il programma di installazione dei prodotti SharePoint viene installato SQL Server Express Edition per i database dell'applicazione SharePoint.</span><span class="sxs-lookup"><span data-stu-id="486cb-129">If an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] is not installed, the SharePoint Products Setup program installs SQL Server Express Edition for the SharePoint application databases.</span></span>  
  
-   <span data-ttu-id="486cb-130">L'istanza del server di report non può utilizzare SQL Server Express Edition per il proprio database.</span><span class="sxs-lookup"><span data-stu-id="486cb-130">The report server instance cannot use the SQL Server Express Edition for its database.</span></span> <span data-ttu-id="486cb-131">Tuttavia, l'istanza di SQL Server Express Edition installata mediante il prodotto SharePoint può esistere in modalità side-by-side con altre eventuali edizioni del motore di database.</span><span class="sxs-lookup"><span data-stu-id="486cb-131">However, the SQL Server Express Edition instance installed by the SharePoint product can exist side-by-side with other Database Engine editions.</span></span>  
  
##  <a name="sscrescent-requirements"></a><a name="bkmk_powerview"></a><span data-ttu-id="486cb-132">[!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)]Requisiti di</span><span class="sxs-lookup"><span data-stu-id="486cb-132">[!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] Requirements</span></span>

 <span data-ttu-id="486cb-133">Esaminare la [documentazione di Power View](https://office.microsoft.com/excel-help/power-view-explore-visualize-and-present-your-data-HA102835634.aspx) più aggiornata su Office.Microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="486cb-133">Review the most up-to-date [Power View documentation](https://office.microsoft.com/excel-help/power-view-explore-visualize-and-present-your-data-HA102835634.aspx) on Office.Microsoft.com.</span></span> [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] <span data-ttu-id="486cb-134">è ora una funzionalità di Microsoft Excel 2013 ed è incluso nel componente aggiuntivo di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Reporting Services per Microsoft SharePoint Server 2010 e 2013 Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="486cb-134">is a feature of Microsoft Excel 2013, and is part of the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Reporting Services add-in for Microsoft SharePoint Server 2010 and 2013 Enterprise Editions.</span></span>  
  
##  <a name="more-information"></a><a name="bkmk_more_information"></a> <span data-ttu-id="486cb-135">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="486cb-135">More Information</span></span>

 <span data-ttu-id="486cb-136">Per informazioni sulle modifiche di SharePoint, vedere [modifiche da sharepoint 2010 a sharepoint 2013](https://technet.microsoft.com/library/ff607742\(office.15\).aspx) ( https://technet.microsoft.com/library/ff607742(office.15).aspx) .</span><span class="sxs-lookup"><span data-stu-id="486cb-136">For information on SharePoint changes, see [Changes from SharePoint 2010 to SharePoint 2013](https://technet.microsoft.com/library/ff607742\(office.15\).aspx) (https://technet.microsoft.com/library/ff607742(office.15).aspx).</span></span>  
  
 <span data-ttu-id="486cb-137">[Note sulla versione di SQL Server 2014](https://go.microsoft.com/fwlink/?LinkID=296445).</span><span class="sxs-lookup"><span data-stu-id="486cb-137">[SQL Server 2014 Release Notes](https://go.microsoft.com/fwlink/?LinkID=296445).</span></span>  
  
