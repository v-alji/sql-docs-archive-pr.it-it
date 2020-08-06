---
title: Script e PowerShell con Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- scripts [Reporting Services]
- Reporting Services, scripting
- scripting [Reporting Services]
ms.assetid: 1ac2646d-ed5a-4436-b18f-2150c33f3d87
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a7a8dc805351897c11202467ed8bcb0373ef77c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629722"
---
# <a name="scripting-and-powershell-with-reporting-services"></a><span data-ttu-id="cd4ea-102">Script e PowerShell con Reporting Services</span><span class="sxs-lookup"><span data-stu-id="cd4ea-102">Scripting and PowerShell with Reporting Services</span></span>
  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="cd4ea-103">supporta un'ampia gamma di scenari di sviluppo e gestione tramite script, tra cui l'utilità della riga di comando rs.exe, i cmdlet PowerShell per server di report in modalità SharePoint, sfruttando il modello a oggetti [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] da PowerShell per la modalità nativa e SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cd4ea-103">supports a wide range of development and management scenarios through script, including the rs.exe command line utility, PowerShell cmdlets for SharePoint mode report servers, and leveraging the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] object model from PowerShell for both Native and SharePoint mode.</span></span>

-   <span data-ttu-id="cd4ea-104">Gli amministratori possono scrivere script in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] per automatizzare le procedure di distribuzione e gestione dell'installazione di un server di report.</span><span class="sxs-lookup"><span data-stu-id="cd4ea-104">Administrators can write script in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] to automate how they deploy and manage a report server installation.</span></span> <span data-ttu-id="cd4ea-105">Gli amministratori possono anche generare ed eseguire script [!INCLUDE[tsql](../../includes/tsql-md.md)] che consentono di creare, configurare e aggiornare un database del server di report.</span><span class="sxs-lookup"><span data-stu-id="cd4ea-105">Administrators can also generate and run [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts that create, configure, and update a report server database.</span></span> <span data-ttu-id="cd4ea-106">Gli amministratori possono anche usare le funzionalità script di registrazione e riproduzione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] per automatizzare le attività di manutenzione di routine.</span><span class="sxs-lookup"><span data-stu-id="cd4ea-106">Administrators can also use the record and playback script features in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to automate routine maintenance tasks.</span></span>

-   <span data-ttu-id="cd4ea-107">Gli sviluppatori possono creare applicazioni personalizzate che includono script.</span><span class="sxs-lookup"><span data-stu-id="cd4ea-107">Developers can create custom applications that include script.</span></span> <span data-ttu-id="cd4ea-108">È possibile eseguire uno script che effettua chiamate al servizio Web ReportServer.</span><span class="sxs-lookup"><span data-stu-id="cd4ea-108">You can run script that makes calls to the Report Server Web service.</span></span> <span data-ttu-id="cd4ea-109">Nello script è possibile scrivere quasi tutte le operazioni che si possono scrivere in codice gestito.</span><span class="sxs-lookup"><span data-stu-id="cd4ea-109">Almost any operation that you can write in managed code can also be written in script.</span></span>

-   [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="cd4ea-110">supporta lo script .NET [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] come linguaggio di script che può essere elaborato dall'utilità RS.exe, un host di script che viene eseguito nel server di report.</span><span class="sxs-lookup"><span data-stu-id="cd4ea-110">supports [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET script as the script language that can be processed by the RS.exe utility, a script host that runs on the report server.</span></span>

## <a name="reporting-services-sharepoint-mode-powershell-cmdlets-and-samples"></a><span data-ttu-id="cd4ea-111">Cmdlet ed esempi di PowerShell in modalità SharePoint di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="cd4ea-111">Reporting Services SharePoint mode PowerShell cmdlets and samples</span></span>
 <span data-ttu-id="cd4ea-112">![Contenuto correlato di PowerShell](../media/rs-powershellicon.jpg "Contenuto correlato di PowerShell")</span><span class="sxs-lookup"><span data-stu-id="cd4ea-112">![PowerShell related content](../media/rs-powershellicon.jpg "PowerShell related content")</span></span>

 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="cd4ea-113">include i cmdlet [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] per l'amministrazione del server di report.</span><span class="sxs-lookup"><span data-stu-id="cd4ea-113">SharePoint mode includes [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] cmdlets for report server administration.</span></span>

-   <span data-ttu-id="cd4ea-114">[PowerShell cmdlets for Reporting Services SharePoint Mode](../powershell-cmdlets-for-reporting-services-sharepoint-mode.md) Sono inclusi gli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cd4ea-114">[PowerShell cmdlets for Reporting Services SharePoint Mode](../powershell-cmdlets-for-reporting-services-sharepoint-mode.md) Includes the following examples:</span></span>

    -   <span data-ttu-id="cd4ea-115">Creare un proxy e un'applicazione di servizio</span><span class="sxs-lookup"><span data-stu-id="cd4ea-115">Create a service application and proxy</span></span>

    -   <span data-ttu-id="cd4ea-116">Rivedere e aggiornare un'estensione per il recapito</span><span class="sxs-lookup"><span data-stu-id="cd4ea-116">Review and update a delivery extension</span></span>

    -   <span data-ttu-id="cd4ea-117">Ottenere e impostare le proprietà del database dell'applicazione Reporting Service, ad esempio timeout database</span><span class="sxs-lookup"><span data-stu-id="cd4ea-117">Get and set Properties of the Reporting Service Application Database, for example database timeout</span></span>

    -   <span data-ttu-id="cd4ea-118">Elencare le estensioni per i dati</span><span class="sxs-lookup"><span data-stu-id="cd4ea-118">List Data Extensions</span></span>

## <a name="reporting-services-object-model-and-powershell-samples"></a><span data-ttu-id="cd4ea-119">Modello a oggetti di Reporting Services ed esempi di Powershell</span><span class="sxs-lookup"><span data-stu-id="cd4ea-119">Reporting Services Object model and Powershell samples</span></span>
 <span data-ttu-id="cd4ea-120">![Contenuto correlato di PowerShell](../media/rs-powershellicon.jpg "Contenuto correlato di PowerShell")</span><span class="sxs-lookup"><span data-stu-id="cd4ea-120">![PowerShell related content](../media/rs-powershellicon.jpg "PowerShell related content")</span></span>

 <span data-ttu-id="cd4ea-121">Le chiamate del modello a oggetti principale di PowerShell valide in generale per la modalità SharePoint e nativa, ad esempio l'attività di migrazione, l'attività di sottoscrizione ed esempi più correlati per le sottoscrizioni, funzionano in SQL15.</span><span class="sxs-lookup"><span data-stu-id="cd4ea-121">PowerShell calling the core object model and for the most part valid for SharePoint and native mode, for example the migration work, subscription work, and more related samples for subscriptions work in SQL15.</span></span>

-   <span data-ttu-id="cd4ea-122">[Usare PowerShell per modificare ed elencare i proprietari di sottoscrizioni di Reporting Services ed eseguire una sottoscrizione](../subscriptions/manage-subscription-owners-and-run-subscription-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="cd4ea-122">[Use PowerShell to Change and List Reporting Services Subscription Owners and Run a Subscription](../subscriptions/manage-subscription-owners-and-run-subscription-powershell.md).</span></span>

-   <span data-ttu-id="cd4ea-123">[Usare PowerShell per creare una VM di Azure con un server di report in modalità nativa](https://msdn.microsoft.com/library/azure/dn449661.aspx).</span><span class="sxs-lookup"><span data-stu-id="cd4ea-123">[Use PowerShell to Create an Azure VM With a Native Mode Report Server](https://msdn.microsoft.com/library/azure/dn449661.aspx).</span></span>

-   <span data-ttu-id="cd4ea-124">Vedere la sezione "Accedere alle classi WMI utilizzando PowerShell" in [Accedere al provider WMI per Reporting Services](access-the-reporting-services-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="cd4ea-124">See the section "Access the WMI classes using PowerShell" in [Access the Reporting Services WMI Provider](access-the-reporting-services-wmi-provider.md).</span></span>

-   <span data-ttu-id="cd4ea-125">[Come amministrare SSRS con gli script di PowerShell](https://www.sqlshack.com/how-to-administer-sql-server-reporting-services-ssrs-subscriptions-using-powershell/)</span><span class="sxs-lookup"><span data-stu-id="cd4ea-125">[How to Administer SSRS using PowerShell](https://www.sqlshack.com/how-to-administer-sql-server-reporting-services-ssrs-subscriptions-using-powershell/).scriptin</span></span>

## <a name="rsexe-scripting-samples"></a><span data-ttu-id="cd4ea-126">Esempi di script RS.exe</span><span class="sxs-lookup"><span data-stu-id="cd4ea-126">RS.exe scripting samples</span></span>

-   <span data-ttu-id="cd4ea-127">[Esempio Reporting Services Script rs.exe per eseguire la migrazione del contenuto tra server di report](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="cd4ea-127">[Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span></span>

-   <span data-ttu-id="cd4ea-128">Per altri esempi di script, applicazioni ed estensioni, vedere gli [esempi di prodotti di Reporting Services di SQL Server](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="cd4ea-128">For additional script, application, and extension examples, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>

## <a name="see-also"></a><span data-ttu-id="cd4ea-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd4ea-129">See Also</span></span>
 <span data-ttu-id="cd4ea-130">[RS.exe utility &#40;SSRS&#41;](rs-exe-utility-ssrs.md) [script di distribuzione e attività amministrative](script-deployment-and-administrative-tasks.md) [con l'utilità rs.exe e il servizio Web](script-with-the-rs-exe-utility-and-the-web-service.md)</span><span class="sxs-lookup"><span data-stu-id="cd4ea-130">[RS.exe Utility &#40;SSRS&#41;](rs-exe-utility-ssrs.md) [Script Deployment and Administrative Tasks](script-deployment-and-administrative-tasks.md) [Script with the rs.exe Utility and the Web Service](script-with-the-rs-exe-utility-and-the-web-service.md)</span></span>


