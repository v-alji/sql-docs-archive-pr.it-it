---
title: Utilizzare Preparazione aggiornamento per preparare gli aggiornamenti | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor [SQL Server]
- upgrading SQL Server, Upgrade Advisor
- upgrading SQL Server, preparing to upgrade
- SQL Server Upgrade Advisor
- analyzing installations for upgrading [SQL Server]
ms.assetid: d85b0833-ddeb-42e3-9397-97ea60d521b7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: e53d895cb19a172d0810ae9d6c2bda3406732da1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715939"
---
# <a name="use-upgrade-advisor-to-prepare-for-upgrades"></a><span data-ttu-id="c507c-102">Utilizzare Preparazione aggiornamento per preparare gli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="c507c-102">Use Upgrade Advisor to Prepare for Upgrades</span></span>
  <span data-ttu-id="c507c-103">Preparazione aggiornamento a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] semplifica le attività di preparazione per l'aggiornamento a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c507c-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Upgrade Advisor helps you prepare for upgrades to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="c507c-104">Preparazione aggiornamento consente di analizzare i componenti installati dalle versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e di generare un report contenente i problemi da correggere prima o dopo l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="c507c-104">Upgrade Advisor analyzes installed components from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and then generates a report that identifies issues to fix either before or after you upgrade.</span></span>  
  
## <a name="how-upgrade-advisor-works"></a><span data-ttu-id="c507c-105">Funzionamento di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="c507c-105">How Upgrade Advisor Works</span></span>  
 <span data-ttu-id="c507c-106">Quando si esegue Preparazione aggiornamento, ne viene visualizzata l'home page,</span><span class="sxs-lookup"><span data-stu-id="c507c-106">When you run Upgrade Advisor, the Upgrade Advisor Home page appears.</span></span> <span data-ttu-id="c507c-107">da cui è possibile eseguire gli strumenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c507c-107">From the Home page, you can run the following tools:</span></span>  
  
-   <span data-ttu-id="c507c-108">Analisi guidata di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="c507c-108">Upgrade Advisor Analysis Wizard</span></span>  
  
-   <span data-ttu-id="c507c-109">Visualizzatore report di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="c507c-109">Upgrade Advisor Report Viewer</span></span>  
  
-   <span data-ttu-id="c507c-110">Guida di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="c507c-110">Upgrade Advisor Help</span></span>  
  
 <span data-ttu-id="c507c-111">La prima volta che si utilizza Preparazione aggiornamento, eseguire l'Analisi guidata di Preparazione aggiornamento per analizzare i componenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c507c-111">The first time that you use Upgrade Advisor, run the Upgrade Advisor Analysis Wizard to analyze [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components.</span></span> <span data-ttu-id="c507c-112">Al termine dell'analisi, visualizzare i report risultanti nel Visualizzatore report di Preparazione aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="c507c-112">When the wizard finishes the analysis, view the resulting reports in the Upgrade Advisor Report Viewer.</span></span> <span data-ttu-id="c507c-113">In ogni report sono inclusi collegamenti a informazioni della Guida di Preparazione aggiornamento che consentono di correggere o ridurre gli effetti dei problemi noti.</span><span class="sxs-lookup"><span data-stu-id="c507c-113">Each report provides links to information in Upgrade Advisor Help that will help you fix or reduce the effect of the known issues.</span></span>  
  
## <a name="upgrade-advisor-analysis"></a><span data-ttu-id="c507c-114">Analisi di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="c507c-114">Upgrade Advisor Analysis</span></span>  
 <span data-ttu-id="c507c-115">Preparazione aggiornamento analizza i seguenti componenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="c507c-115">Upgrade Advisor analyzes the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components:</span></span>  
  
-   [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
-   [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
-   [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]  
  
 <span data-ttu-id="c507c-116">Nell'analisi vengono esaminati gli oggetti a cui è possibile accedere, quali script, stored procedure, trigger e file di traccia.</span><span class="sxs-lookup"><span data-stu-id="c507c-116">The analysis examines objects that can be accessed, such as scripts, stored procedures, triggers, and trace files.</span></span> <span data-ttu-id="c507c-117">Preparazione aggiornamento non è in grado di analizzare applicazioni desktop o stored procedure crittografate.</span><span class="sxs-lookup"><span data-stu-id="c507c-117">Upgrade Advisor cannot analyze desktop applications or encrypted stored procedures.</span></span>  
  
 <span data-ttu-id="c507c-118">L'output è nel formato di un report XML.</span><span class="sxs-lookup"><span data-stu-id="c507c-118">Output is in the form of an XML report.</span></span> <span data-ttu-id="c507c-119">Per visualizzare il report XML, utilizzare il Visualizzatore report di Preparazione aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="c507c-119">View the XML report by using the Upgrade Advisor report viewer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c507c-120">I report potrebbero contenere l'indicazione di altri problemi di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="c507c-120">Reports might contain an "other upgrade issues" item.</span></span> <span data-ttu-id="c507c-121">non rilevati da Preparazione aggiornamento ma che potrebbero esistere sul server o nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="c507c-121">This item links to a list of issues that are not detected by Upgrade Advisor, but might exist on your server or in your applications.</span></span> <span data-ttu-id="c507c-122">Esaminare l'elenco dei problemi non rilevabili e determinare se sia necessario apportare modifiche al server o alle applicazioni a causa di tali problemi.</span><span class="sxs-lookup"><span data-stu-id="c507c-122">You should review the list of undetectable issues and determine whether you must change your server or applications because of the undetectable issues.</span></span>  
  
## <a name="how-to-install-and-run-upgrade-advisor"></a><span data-ttu-id="c507c-123">Come installare e aggiornare Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="c507c-123">How to Install and Run Upgrade Advisor</span></span>  
 <span data-ttu-id="c507c-124">Il percorso di installazione di Preparazione aggiornamento a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dipende dagli elementi analizzati.</span><span class="sxs-lookup"><span data-stu-id="c507c-124">The location where you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Upgrade Advisor depends on what you will be analyzing.</span></span> <span data-ttu-id="c507c-125">Preparazione aggiornamento supporta l'analisi remota di tutti i componenti supportati, ad eccezione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c507c-125">Upgrade Advisor supports remote analysis of all supported components except [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="c507c-126">Se non si esegue l'analisi di istanze di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], è possibile installare Preparazione aggiornamento in qualsiasi computer in grado di connettersi all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e che soddisfa i prerequisiti di Preparazione aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="c507c-126">If you are not scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can install Upgrade Advisor on any computer that can connect to your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and that meets the Upgrade Advisor prerequisites.</span></span> <span data-ttu-id="c507c-127">Per altre informazioni, vedere [Aggiornamenti di versione ed edizione supportati](../../database-engine/install-windows/supported-version-and-edition-upgrades.md).</span><span class="sxs-lookup"><span data-stu-id="c507c-127">For more information, see [Supported Version and Edition Upgrades](../../database-engine/install-windows/supported-version-and-edition-upgrades.md).</span></span> <span data-ttu-id="c507c-128">Se si prevede di analizzare le istanze di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], è necessario installare Preparazione aggiornamento nel server di report.</span><span class="sxs-lookup"><span data-stu-id="c507c-128">If you are scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must install Upgrade Advisor on the report server.</span></span>  
  
 <span data-ttu-id="c507c-129">Preparazione aggiornamento è disponibile in un feature pack.</span><span class="sxs-lookup"><span data-stu-id="c507c-129">Upgrade Advisor is available in a feature pack.</span></span>  
  
 <span data-ttu-id="c507c-130">Di seguito vengono indicati i prerequisiti per l'installazione e l'esecuzione di Preparazione aggiornamento:</span><span class="sxs-lookup"><span data-stu-id="c507c-130">Prerequisites for installing and running Upgrade Advisor are as follows:</span></span>  
  
-   [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] <span data-ttu-id="c507c-131">SP2, Windows 7 SP1 e [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1.</span><span class="sxs-lookup"><span data-stu-id="c507c-131">SP2, Windows 7 SP1, and [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1.</span></span>  
  
-   <span data-ttu-id="c507c-132">Windows Installer a partire dalla versione 4.5.</span><span class="sxs-lookup"><span data-stu-id="c507c-132">Windows Installer beginning with version 4.5.</span></span> <span data-ttu-id="c507c-133">È possibile installare Windows Installer dal [sito Web di Windows Installer](https://www.microsoft.com/download/details.aspx?id=8483).</span><span class="sxs-lookup"><span data-stu-id="c507c-133">You can install Windows Installer from the [Windows Installer Web site](https://www.microsoft.com/download/details.aspx?id=8483).</span></span>  
  
-   <span data-ttu-id="c507c-134">Microsoft .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="c507c-134">Microsoft .NET Framework 4.</span></span> <span data-ttu-id="c507c-135">.NET Framework 4 è disponibile sul [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] supporto del prodotto e dalla pagina di [download di .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=209895).</span><span class="sxs-lookup"><span data-stu-id="c507c-135">.NET Framework 4 is available on the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] product media, and from the [.NET Framework 4 download page](https://go.microsoft.com/fwlink/?LinkId=209895).</span></span>  
  
    -   <span data-ttu-id="c507c-136">Per eseguire l'installazione di .NET Framework 4 dai supporti di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], individuare la radice dell'unità disco.</span><span class="sxs-lookup"><span data-stu-id="c507c-136">To install the .NET Framework 4 from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] media, locate the root of the disk drive.</span></span> <span data-ttu-id="c507c-137">Fare quindi doppio clic sulla cartella \redist, sulla cartella DotNetFrameworks ed eseguire dotNetFx40_Full_x86_x64.exe (sia per i sistemi operativi a 32 bit che per quelli a 64 bit).</span><span class="sxs-lookup"><span data-stu-id="c507c-137">Then, double-click the \redist folder, double-click the DotNetFrameworks folder, and run dotNetFx40_Full_x86_x64.exe (for 32-bit operating systems or for 64-bit operating systems).</span></span>  
  
 <span data-ttu-id="c507c-138">Per installare Preparazione aggiornamento dal Web, fare clic sul pulsante di download presente nella pagina di download.</span><span class="sxs-lookup"><span data-stu-id="c507c-138">To install Upgrade Advisor from the Web, click the download button on the download page.</span></span> <span data-ttu-id="c507c-139">È quindi possibile eseguire l'installazione immediatamente oppure salvare il file SQLUA.msi per eseguirlo successivamente.</span><span class="sxs-lookup"><span data-stu-id="c507c-139">You can then run installation immediately, or save the SQLUA.msi file to run later.</span></span> <span data-ttu-id="c507c-140">Se l'installazione viene eseguita dal disco del prodotto, eseguire SQLUA.msi direttamente da tale disco.</span><span class="sxs-lookup"><span data-stu-id="c507c-140">If you are installing from the product disc, run SQLUA.msi directly from the product disk.</span></span>  
  
 <span data-ttu-id="c507c-141">Dopo aver installato Preparazione aggiornamento, è possibile aprirlo dal menu **Start** :</span><span class="sxs-lookup"><span data-stu-id="c507c-141">After you install Upgrade Advisor, you can open it from the **Start** menu:</span></span>  
  
-   <span data-ttu-id="c507c-142">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)] , quindi fare clic su \*\* [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Preparazione aggiornamento\*\*.</span><span class="sxs-lookup"><span data-stu-id="c507c-142">Click **Start**, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], and then click **[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor**.</span></span>  
  
 <span data-ttu-id="c507c-143">Per ulteriori informazioni, vedere la documentazione inclusa nel download di Preparazione aggiornamento e le note sulla versione di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c507c-143">For more information, see the Upgrade Advisor documentation included in the Upgrade Advisor download and the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Release Notes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c507c-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c507c-144">See Also</span></span>  
 <span data-ttu-id="c507c-145">[Usare più versioni e istanze di SQL Server](../../../2014/sql-server/install/work-with-multiple-versions-and-instances-of-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c507c-145">[Work with Multiple Versions and Instances of SQL Server](../../../2014/sql-server/install/work-with-multiple-versions-and-instances-of-sql-server.md) </span></span>  
 <span data-ttu-id="c507c-146">[Aggiornamenti di versione ed edizione supportati](../../database-engine/install-windows/supported-version-and-edition-upgrades.md) </span><span class="sxs-lookup"><span data-stu-id="c507c-146">[Supported Version and Edition Upgrades](../../database-engine/install-windows/supported-version-and-edition-upgrades.md) </span></span>  
 [<span data-ttu-id="c507c-147">Compatibilità con le versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="c507c-147">Backward Compatibility</span></span>](../../../2014/getting-started/backward-compatibility.md)  
  
  
