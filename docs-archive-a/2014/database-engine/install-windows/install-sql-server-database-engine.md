---
title: Informazioni sul motore di database SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server], installing
ms.assetid: d0876e7f-aa52-4dd7-bd5c-029e2ffded5f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 93e3d7a749fe6be47cc84d43509a6f378476b2ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716584"
---
# <a name="about-the-sql-server-database-engine"></a><span data-ttu-id="72c48-102">Informazioni sul Motore di database di SQL Server</span><span class="sxs-lookup"><span data-stu-id="72c48-102">About the SQL Server Database Engine</span></span>
  <span data-ttu-id="72c48-103">Il componente [!INCLUDE[ssDE](../../includes/ssde-md.md)] di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rappresenta il servizio principale per l'archiviazione, l'elaborazione e la protezione dei dati.</span><span class="sxs-lookup"><span data-stu-id="72c48-103">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] component of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is the core service for storing, processing, and securing data.</span></span> <span data-ttu-id="72c48-104">Grazie all'accesso controllato e all'elaborazione rapida delle transazioni, il [!INCLUDE[ssDE](../../includes/ssde-md.md)] è in grado di soddisfare i requisiti delle applicazioni che richiedono un maggiore utilizzo di dati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="72c48-104">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] provides controlled access and rapid transaction processing to meet the requirements of the most demanding data consuming applications in your enterprise.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="72c48-105">supporta fino a 50 istanze del [!INCLUDE[ssDE](../../includes/ssde-md.md)] in un singolo computer.</span><span class="sxs-lookup"><span data-stu-id="72c48-105">supports up to 50 instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on a single computer.</span></span> <span data-ttu-id="72c48-106">Per creare un'installazione tipica di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vedere [installare SQL Server 2014 dall'installazione guidata &#40;&#41;di ](install-sql-server-from-the-installation-wizard-setup.md)installazione.</span><span class="sxs-lookup"><span data-stu-id="72c48-106">To create a typical [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation, see [Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](install-sql-server-from-the-installation-wizard-setup.md).</span></span>  
  
 <span data-ttu-id="72c48-107">**Importante** Per le installazioni locali, è necessario eseguire il programma di installazione come amministratore.</span><span class="sxs-lookup"><span data-stu-id="72c48-107">**Important** For local installations, you must run Setup as an administrator.</span></span> <span data-ttu-id="72c48-108">Se si installa [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da una condivisione remota, è necessario utilizzare un account di dominio con autorizzazioni di lettura ed esecuzione relative a tale condivisione.</span><span class="sxs-lookup"><span data-stu-id="72c48-108">If you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a remote share, you must use a domain account that has read and execute permissions on the remote share.</span></span>  
  
 <span data-ttu-id="72c48-109">Quando si seleziona **Motore di database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** nella pagina Componenti da installare dell'Installazione guidata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vengono installate le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="72c48-109">The following features are installed when you select **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Database Engine** on the Components to Install page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard:</span></span>  
  
-   [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
-   <span data-ttu-id="72c48-110">Replica - componente facoltativo</span><span class="sxs-lookup"><span data-stu-id="72c48-110">Replication - is an optional component</span></span>  
  
-   <span data-ttu-id="72c48-111">Ricerca full-text - componente facoltativo</span><span class="sxs-lookup"><span data-stu-id="72c48-111">Full-Text Search - is an optional component</span></span>  
  
-   <span data-ttu-id="72c48-112">Data Quality Services - componente facoltativo</span><span class="sxs-lookup"><span data-stu-id="72c48-112">Data Quality Services - is an optional component</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="72c48-113">In questa versione, la selezione della casella di controllo **Data Quality Services** nell'installazione non comporta l'installazione del server Data Quality Services (DQS).</span><span class="sxs-lookup"><span data-stu-id="72c48-113">In this release, selecting the **Data Quality Services** check box in setup does not install the Data Quality Services (DQS) server.</span></span> <span data-ttu-id="72c48-114">Sarà necessario eseguire dei passaggi aggiuntivi postinstallazione per installare server DQS.</span><span class="sxs-lookup"><span data-stu-id="72c48-114">You will have to perform additional steps post installation to install DQS server.</span></span> <span data-ttu-id="72c48-115">Per altre informazioni, vedere [Installare Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md).</span><span class="sxs-lookup"><span data-stu-id="72c48-115">For more information, see [Install Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md).</span></span>  
  
 <span data-ttu-id="72c48-116">Le funzionalità aggiuntive seguenti rappresentano opzioni disponibili per molti scenari utente tipici:</span><span class="sxs-lookup"><span data-stu-id="72c48-116">The following additional features are options for many typical user scenarios:</span></span>  
  
-   <span data-ttu-id="72c48-117">Client Data Quality</span><span class="sxs-lookup"><span data-stu-id="72c48-117">Data Quality Client</span></span>  
  
-   [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]  
  
-   <span data-ttu-id="72c48-118">Componenti di connettività</span><span class="sxs-lookup"><span data-stu-id="72c48-118">Connectivity components</span></span>  
  
-   <span data-ttu-id="72c48-119">Modelli di programmazione</span><span class="sxs-lookup"><span data-stu-id="72c48-119">Programming models</span></span>  
  
-   <span data-ttu-id="72c48-120">Strumenti di gestione</span><span class="sxs-lookup"><span data-stu-id="72c48-120">Management tools</span></span>  
  
-   [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]  
  
-   <span data-ttu-id="72c48-121">Componenti della documentazione</span><span class="sxs-lookup"><span data-stu-id="72c48-121">Documentation components</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="72c48-122">Per impostazione predefinita, i database di esempio e il codice di esempio non vengono installati come parte dell'installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="72c48-122">By default, sample databases and sample code are not installed as part of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup.</span></span> <span data-ttu-id="72c48-123">Per installare i database di esempio e il codice di esempio, vedere il sito Web [CodePlex](https://go.microsoft.com/fwlink/?LinkId=87843).</span><span class="sxs-lookup"><span data-stu-id="72c48-123">To install sample databases and sample code, see the [CodePlex Web site](https://go.microsoft.com/fwlink/?LinkId=87843).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72c48-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72c48-124">See Also</span></span>  
 <span data-ttu-id="72c48-125">[Funzionalità supportate dalle edizioni di SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span><span class="sxs-lookup"><span data-stu-id="72c48-125">[Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span></span>  
 <span data-ttu-id="72c48-126">[Edizioni e componenti di SQL Server 2014](../../sql-server/editions-and-components-of-sql-server-2016.md) </span><span class="sxs-lookup"><span data-stu-id="72c48-126">[Editions and Components of SQL Server 2014](../../sql-server/editions-and-components-of-sql-server-2016.md) </span></span>  
 <span data-ttu-id="72c48-127">[Pianificazione di un'installazione di SQL Server](../../sql-server/install/planning-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="72c48-127">[Planning a SQL Server Installation](../../sql-server/install/planning-a-sql-server-installation.md) </span></span>  
 <span data-ttu-id="72c48-128">[Soluzioni a disponibilità elevata &#40;SQL Server&#41;](../../sql-server/failover-clusters/high-availability-solutions-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="72c48-128">[High Availability Solutions &#40;SQL Server&#41;](../../sql-server/failover-clusters/high-availability-solutions-sql-server.md) </span></span>  
 [<span data-ttu-id="72c48-129">Eseguire l'aggiornamento a SQL Server 2014 usando l'installazione guidata &#40;&#41;</span><span class="sxs-lookup"><span data-stu-id="72c48-129">Upgrade to SQL Server 2014 Using the Installation Wizard &#40;Setup&#41;</span></span>](upgrade-sql-server-using-the-installation-wizard-setup.md)  
  
  
