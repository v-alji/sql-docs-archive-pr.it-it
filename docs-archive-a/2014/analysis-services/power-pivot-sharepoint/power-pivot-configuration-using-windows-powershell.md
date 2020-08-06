---
title: Configurazione di PowerPivot con Windows PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 4d83e53e-04f1-417d-9039-d9e81ae0483d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 83b42da3e676a291bb021c02ee52e9a810207397
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636410"
---
# <a name="powerpivot-configuration-using-windows-powershell"></a><span data-ttu-id="01849-102">Configurazione di PowerPivot tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="01849-102">PowerPivot Configuration using Windows PowerShell</span></span>
  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="01849-103">include i cmdlet di Windows PowerShell che è possibile usare per configurare un'installazione di [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="01849-103">includes Windows PowerShell cmdlets that you can use to configure an installation of [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)].</span></span> <span data-ttu-id="01849-104">Per configurazione completamente un'installazione con PowerShell, è necessario utilizzare cmdlet sia di SharePoint che di PowerPivot per SharePoint.</span><span class="sxs-lookup"><span data-stu-id="01849-104">To fully configure an installation with PowerShell requires the use of both SharePoint cmdlets and PowerPivot for SharePoint cmdlets.</span></span> <span data-ttu-id="01849-105">La maggior parte della configurazione può essere completata usando uno degli strumenti di [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="01849-105">A majority of configuration can be completed using one of the [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] tools.</span></span> <span data-ttu-id="01849-106">Per ulteriori informazioni sugli strumenti, vedere [strumenti di configurazione di PowerPivot](power-pivot-configuration-tools.md).</span><span class="sxs-lookup"><span data-stu-id="01849-106">For more information on the tools, see [PowerPivot Configuration Tools](power-pivot-configuration-tools.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="01849-107">Per una farm di SharePoint 2010, prima di poter configurare PowerPivot per SharePoint o una farm di SharePoint in cui viene utilizzato un server di database [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] è necessario che SharePoint 2010 SP1 sia installato.</span><span class="sxs-lookup"><span data-stu-id="01849-107">For a SharePoint 2010 farm, SharePoint 2010 SP1 must be installed before you can configure either PowerPivot for SharePoint, or a SharePoint farm that uses a [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] database server.</span></span> <span data-ttu-id="01849-108">Se il Service Pack non è ancora stato installato, eseguire questa operazione prima di iniziare a configurare il server.</span><span class="sxs-lookup"><span data-stu-id="01849-108">If you have not yet installed the service pack, install it before you begin configuring the server.</span></span>  
  
## <a name="benefits-of-configuring-powerpivot-for-sharepoint-using-powershell"></a><span data-ttu-id="01849-109">Vantaggi della configurazione di PowerPivot per SharePoint utilizzando PowerShell</span><span class="sxs-lookup"><span data-stu-id="01849-109">Benefits of Configuring PowerPivot for SharePoint Using PowerShell</span></span>  
 <span data-ttu-id="01849-110">È possibile compilare i file di script di Windows PowerShell (con estensione ps1) per rendere automatiche le attività di configurazione.</span><span class="sxs-lookup"><span data-stu-id="01849-110">You can build Windows PowerShell script (.ps1) files to automate configuration tasks.</span></span> <span data-ttu-id="01849-111">Si consiglia di adottare questo approccio se sono necessari passaggi di installazione e configurazione controllati da script eseguibili in qualsiasi server.</span><span class="sxs-lookup"><span data-stu-id="01849-111">This approach is recommended if you require scripted installation and configuration steps that you can run on any server.</span></span> <span data-ttu-id="01849-112">Uno script di questo tipo può essere necessario come parte di un piano di ripristino di emergenza per ricompilare un server in caso di errore hardware.</span><span class="sxs-lookup"><span data-stu-id="01849-112">You might require such a script as part of a disaster recovery plan for rebuilding a server in the event of a hardware failure.</span></span>  
  
## <a name="view-a-list-of-the-powerpivot-cmdlets-on-a-server"></a><span data-ttu-id="01849-113">Visualizzare un elenco di cmdlet PowerPivot in un server</span><span class="sxs-lookup"><span data-stu-id="01849-113">View a list of the PowerPivot Cmdlets on a Server</span></span>  
 <span data-ttu-id="01849-114">Per visualizzare il contenuto ed esempi dei [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] cmdlet, vedere informazioni di [riferimento su PowerShell per PowerPivot per SharePoint](/sql/analysis-services/powershell/powershell-reference-for-power-pivot-for-sharepoint).</span><span class="sxs-lookup"><span data-stu-id="01849-114">To see content and examples of the [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] cmdlets, see [PowerShell Reference for PowerPivot for SharePoint](/sql/analysis-services/powershell/powershell-reference-for-power-pivot-for-sharepoint).</span></span>  
  
 <span data-ttu-id="01849-115">Per utilizzare PowerShell per visualizzare un elenco di cmdlet di PowerPivot:</span><span class="sxs-lookup"><span data-stu-id="01849-115">To use PowerShell to view a list of the PowerPivot cmdlets:</span></span>  
  
1.  <span data-ttu-id="01849-116">Aprire una shell di gestione di SharePoint usando l'opzione **Esegui come amministratore** .</span><span class="sxs-lookup"><span data-stu-id="01849-116">Open SharePoint Management Shell using the **Run as Administrator** option.</span></span>  
  
2.  <span data-ttu-id="01849-117">Immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="01849-117">Enter the following command:</span></span>  
  
    ```powershell
    Get-Help *powerpivot*  
    ```  
  
     <span data-ttu-id="01849-118">Dovrebbe venire visualizzato un elenco di cmdlet nel cui nome è incluso PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="01849-118">You should see a list of cmdlets that include PowerPivot in the cmdlet name.</span></span> <span data-ttu-id="01849-119">Ad esempio, `Get-PowerPivotServiceApplication`.</span><span class="sxs-lookup"><span data-stu-id="01849-119">For example `Get-PowerPivotServiceApplication`.</span></span> <span data-ttu-id="01849-120">Il numero di cmdlet disponibili dipende dalla versione di Analysis Services in uso.</span><span class="sxs-lookup"><span data-stu-id="01849-120">The number of cmdlets available depends on the version of Analysis Services you are using.</span></span>  
  
    -   <span data-ttu-id="01849-121">10 cmdlet con il server SQL Server 2012 SP1 Analysis Services configurato nella modalità SharePoint e SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="01849-121">10 cmdlets with SQL Server 2012 SP1 Analysis Services server configured in SharePoint mode, and SharePoint 2013.</span></span> <span data-ttu-id="01849-122">La versione 2012 SP1 utilizza una nuova architettura che consente l'esecuzione di Analysis Server all'esterno della farm di SharePoint e richiede meno cmdlet di Windows PowerShell di gestione.</span><span class="sxs-lookup"><span data-stu-id="01849-122">The 2012 SP1 version utilizes a new architecture that allows the Analysis Server to run outside the SharePoint farm and requires fewer management Windows PowerShell cmdlets.</span></span>  
  
    -   <span data-ttu-id="01849-123">17 cmdlet con il server SQL Server 2012 SP1 Analysis Services configurato nella modalità SharePoint e SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="01849-123">17 cmdlets with SQL Server 2012 Analysis Services server configured in SharePoint mode, and SharePoint 2010.</span></span>  
  
     <span data-ttu-id="01849-124">Se nell'elenco non viene restituito alcun comando o se viene visualizzato un messaggio di errore simile a " `get-help could not find *powerpivot* in a help file in this session.` ", vedere la sezione successiva in questo argomento per istruzioni sull'abilitazione dei cmdlet PowerPivot nel server.</span><span class="sxs-lookup"><span data-stu-id="01849-124">If no commands are returned in the list or you see an error message similar to "`get-help could not find *powerpivot* in a help file in this session.`", see the next section in this topic for instructions on how to enable the PowerPivot cmdlets on the server.</span></span>  
  
     <span data-ttu-id="01849-125">Per tutti i cmdlet è disponibile la Guida.</span><span class="sxs-lookup"><span data-stu-id="01849-125">All cmdlets have online help.</span></span> <span data-ttu-id="01849-126">Nell'esempio seguente viene illustrato come visualizzare la Guida per il cmdlet `New-PowerPivotServiceApplication`:</span><span class="sxs-lookup"><span data-stu-id="01849-126">The following example shows how to view the online help for the `New-PowerPivotServiceApplication` cmdlet:</span></span>  
  
    ```powershell
    Get-Help new-powerpivotserviceapplication -Full  
    ```  
  
     <span data-ttu-id="01849-127">In alternativa, per visualizzare solo gli esempi, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="01849-127">Alternatively, to view just the examples, use the following syntax:</span></span>  
  
    ```powershell
    Get-Help new-powerpivotserviceapplication -Example  
    ```  
  
## <a name="enable-powerpivot-cmdlets-on-a-server"></a><span data-ttu-id="01849-128">Abilitare i cmdlet di PowerPivot in un server</span><span class="sxs-lookup"><span data-stu-id="01849-128">Enable PowerPivot Cmdlets on a Server</span></span>  
 <span data-ttu-id="01849-129">I cmdlet di PowerPivot sono disponibili dopo l'installazione di PowerPivot per SharePoint e la distribuzione della soluzione della farm.</span><span class="sxs-lookup"><span data-stu-id="01849-129">PowerPivot cmdlets are available after you install PowerPivot for SharePoint and deploy the farm solution.</span></span> <span data-ttu-id="01849-130">Le soluzioni vengono distribuite quando si esegue lo strumento di configurazione PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="01849-130">The solutions are deployed when you ran the PowerPivot Configuration tool.</span></span> <span data-ttu-id="01849-131">Attenersi a questi passaggi per abilitare l'utilizzo dei cmdlet:</span><span class="sxs-lookup"><span data-stu-id="01849-131">Follow these steps to enable the use of cmdlets:</span></span>  
  
1.  <span data-ttu-id="01849-132">Aprire una shell di gestione di SharePoint usando l'opzione **Esegui come amministratore** .</span><span class="sxs-lookup"><span data-stu-id="01849-132">Open SharePoint Management Shell using the **Run as Administrator** option.</span></span>  
  
2.  <span data-ttu-id="01849-133">Eseguire il primo cmdlet:</span><span class="sxs-lookup"><span data-stu-id="01849-133">Run the first cmdlet:</span></span>  
  
    ```powershell
    Add-SPSolution -LiteralPath "C:\Program Files\Microsoft SQL Server\110\Tools\PowerPivotTools\ConfigurationTool\Resources\PowerPivotFarm.wsp"  
    ```  
  
     <span data-ttu-id="01849-134">Il cmdlet restituisce il nome e l'ID della soluzione e Deployed=False.</span><span class="sxs-lookup"><span data-stu-id="01849-134">The cmdlet returns the name of the solution, its solution ID, and Deployed=False.</span></span> <span data-ttu-id="01849-135">Nel passaggio successivo la soluzione viene distribuita.</span><span class="sxs-lookup"><span data-stu-id="01849-135">In the next step, you deploy the solution.</span></span>  
  
3.  <span data-ttu-id="01849-136">Eseguire il secondo cmdlet per distribuire la soluzione:</span><span class="sxs-lookup"><span data-stu-id="01849-136">Run the second cmdlet to deploy the solution:</span></span>  
  
    ```powershell
    Install-SPSolution -Identity PowerPivotFarm.wsp -GACDeployment -Force  
    ```  
  
4.  <span data-ttu-id="01849-137">Chiudere la finestra.</span><span class="sxs-lookup"><span data-stu-id="01849-137">Close the window.</span></span> <span data-ttu-id="01849-138">Riaprirla usando nuovamente l'opzione **Esegui come amministratore** .</span><span class="sxs-lookup"><span data-stu-id="01849-138">Reopen it, again using the **Run as Administrator** option.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="01849-139">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="01849-139">Related Content</span></span>  
 [<span data-ttu-id="01849-140">Amministrazione e configurazione del server PowerPivot in Amministrazione centrale</span><span class="sxs-lookup"><span data-stu-id="01849-140">PowerPivot Server Administration and Configuration in Central Administration</span></span>](power-pivot-server-administration-and-configuration-in-central-administration.md)  
  
 [<span data-ttu-id="01849-141">PowerPivot Configuration Tools</span><span class="sxs-lookup"><span data-stu-id="01849-141">PowerPivot Configuration Tools</span></span>](power-pivot-configuration-tools.md)  
  
 [<span data-ttu-id="01849-142">Riferimento a PowerShell per PowerPivot per SharePoint</span><span class="sxs-lookup"><span data-stu-id="01849-142">PowerShell Reference for PowerPivot for SharePoint</span></span>](/sql/analysis-services/powershell/powershell-reference-for-power-pivot-for-sharepoint)  
