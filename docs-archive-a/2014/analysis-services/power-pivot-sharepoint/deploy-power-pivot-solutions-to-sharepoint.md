---
title: Distribuire soluzioni PowerPivot in SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f202a2b7-34e0-43aa-90d5-c9a085a37c32
author: minewiskan
ms.author: owend
ms.openlocfilehash: 043647988598f932b70cc06e6bb5492d66864372
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635223"
---
# <a name="deploy-powerpivot-solutions-to-sharepoint"></a><span data-ttu-id="fe298-102">Distribuire soluzioni PowerPivot in SharePoint</span><span class="sxs-lookup"><span data-stu-id="fe298-102">Deploy PowerPivot Solutions to SharePoint</span></span>
  <span data-ttu-id="fe298-103">Utilizzare le seguenti istruzioni per distribuire manualmente due pacchetti di soluzioni che consentono di aggiungere funzionalità di PowerPivot a un ambiente SharePoint Server 2010.</span><span class="sxs-lookup"><span data-stu-id="fe298-103">Use the following instructions to manually deploy two solution packages that add PowerPivot features to a SharePoint Server 2010 environment.</span></span> <span data-ttu-id="fe298-104">La distribuzione delle soluzioni è un passaggio obbligatorio per la configurazione di PowerPivot per SharePoint in un server SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="fe298-104">Deploying the solutions is a required step for configuring PowerPivot for SharePoint on a SharePoint 2010 server.</span></span> <span data-ttu-id="fe298-105">Per visualizzare l'elenco completo dei passaggi necessari, vedere [amministrazione e configurazione del server PowerPivot in Amministrazione centrale](power-pivot-server-administration-and-configuration-in-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="fe298-105">To view the complete list of required steps, see [PowerPivot Server Administration and Configuration in Central Administration](power-pivot-server-administration-and-configuration-in-central-administration.md).</span></span>  
  
 <span data-ttu-id="fe298-106">In alternativa, per distribuire le soluzioni è possibile utilizzare lo strumento di configurazione PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="fe298-106">Alternatively, you can use the PowerPivot Configuration Tool to deploy the solutions.</span></span> <span data-ttu-id="fe298-107">L'utilizzo dello strumento di configurazione è più facile e più efficiente per installazione di un unico server, ma è possibile utilizzare Amministrazione centrale e PowerShell se si preferisce utilizzare uno strumento familiare o se si configurano più funzionalità contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="fe298-107">Using the configuration tool is easier and more efficient for a single server installation, but you might want to use Central Administration and PowerShell if you prefer using a familiar tool or if you are configuring multiple features at the same time.</span></span> <span data-ttu-id="fe298-108">Per ulteriori informazioni sull'utilizzo dello strumento di configurazione di, vedere [strumenti di configurazione di PowerPivot](power-pivot-configuration-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fe298-108">For more information about using the configuration tool, see [PowerPivot Configuration Tools](power-pivot-configuration-tools.md).</span></span>  
  
 <span data-ttu-id="fe298-109">Prima della distribuzione delle soluzioni è necessario installare PowerPivot per SharePoint tramite il supporto di installazione di SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="fe298-109">Before deploying the solutions, you must first install PowerPivot for SharePoint using the SQL Server 2012 installation media.</span></span> <span data-ttu-id="fe298-110">I pacchetti di soluzioni che si desidera distribuire verranno installati dal programma di installazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fe298-110">SQL Server Setup installs the solution packages that you are about to deploy.</span></span>  
  
 <span data-ttu-id="fe298-111">In questo argomento sono incluse le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fe298-111">This topic contains the following sections:</span></span>  
  
 [<span data-ttu-id="fe298-112">Prerequisito: verificare che l'applicazione Web utilizzi l'autenticazione in modalità classica</span><span class="sxs-lookup"><span data-stu-id="fe298-112">Prerequisite: Verify the Web Application uses Classic Mode Authentication</span></span>](#bkmk_classic)  
  
 [<span data-ttu-id="fe298-113">Passaggio 1: distribuire la soluzione farm</span><span class="sxs-lookup"><span data-stu-id="fe298-113">Step 1: Deploy the Farm Solution</span></span>](#bkmk_farm)  
  
 [<span data-ttu-id="fe298-114">Passaggio 2: distribuire la soluzione applicazione Web PowerPivot in Amministrazione centrale</span><span class="sxs-lookup"><span data-stu-id="fe298-114">Step 2: Deploy the PowerPivot Web Application Solution to Central Administration</span></span>](#deployCA)  
  
 [<span data-ttu-id="fe298-115">Passaggio 3: distribuire la soluzione applicazione Web PowerPivot ad altre applicazioni Web</span><span class="sxs-lookup"><span data-stu-id="fe298-115">Step 3: Deploy the PowerPivot Web Application Solution to Other Web Applications</span></span>](#deployUI)  
  
 [<span data-ttu-id="fe298-116">Ridistribuire o ritirare la soluzione</span><span class="sxs-lookup"><span data-stu-id="fe298-116">Redeploy or retract the Solution</span></span>](#retract)  
  
 [<span data-ttu-id="fe298-117">Informazioni sulle soluzioni PowerPivot</span><span class="sxs-lookup"><span data-stu-id="fe298-117">About the PowerPivot Solutions</span></span>](#intro)  
  
##  <a name="prerequisite-verify-the-web-application-uses-classic-mode-authentication"></a><a name="bkmk_classic"></a> <span data-ttu-id="fe298-118">Prerequisito: verificare che l'applicazione Web utilizzi l'autenticazione in modalità classica</span><span class="sxs-lookup"><span data-stu-id="fe298-118">Prerequisite: Verify the Web Application uses Classic Mode Authentication</span></span>  
 <span data-ttu-id="fe298-119">PowerPivot per SharePoint è supportato solo per le applicazioni Web che utilizzano l'autenticazione in modalità classica di Windows.</span><span class="sxs-lookup"><span data-stu-id="fe298-119">PowerPivot for SharePoint is only supported for web applications that use Windows-classic mode authentication.</span></span> <span data-ttu-id="fe298-120">Per verificare se l'applicazione usa la modalità classica, eseguire il cmdlet di PowerShell seguente dalla **Shell di gestione di sharepoint 2010**, sostituendo `http://<top-level site name>` con il nome del sito di SharePoint:</span><span class="sxs-lookup"><span data-stu-id="fe298-120">To check whether the application uses Classic mode, run the following PowerShell cmdlet from the **SharePoint 2010 Management Shell**, replacing `http://<top-level site name>` with the name of your SharePoint site:</span></span>  
  
```powershell
Get-SPWebApplication http://<top-level site name> | Format-List UseClaimsAuthentication  
```  
  
 <span data-ttu-id="fe298-121">Il valore restituito dovrebbe essere **false**.</span><span class="sxs-lookup"><span data-stu-id="fe298-121">The return value should be **false**.</span></span> <span data-ttu-id="fe298-122">Se è **true**, non è possibile accedere ai dati PowerPivot con questa applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="fe298-122">If it is **true**, you cannot access PowerPivot data with this web application.</span></span>  
  
##  <a name="step-1-deploy-the-farm-solution"></a><a name="bkmk_farm"></a> <span data-ttu-id="fe298-123">Passaggio 1: distribuire la soluzione farm</span><span class="sxs-lookup"><span data-stu-id="fe298-123">Step 1: Deploy the Farm Solution</span></span>  
 <span data-ttu-id="fe298-124">In questa sezione viene illustrato come distribuire le soluzioni utilizzando PowerShell, ma è anche possibile utilizzare lo strumento di configurazione PowerPivot per completare questa attività.</span><span class="sxs-lookup"><span data-stu-id="fe298-124">This section shows you how to deploy solutions using PowerShell, but you can also use the PowerPivot Configuration Tool to complete this task.</span></span> <span data-ttu-id="fe298-125">Per ulteriori informazioni, vedere [configurare o ripristinare PowerPivot per SharePoint 2010 &#40;strumento di configurazione PowerPivot&#41;](../configure-repair-powerpivot-sharepoint-2010.md).</span><span class="sxs-lookup"><span data-stu-id="fe298-125">For more information, see [Configure or Repair PowerPivot for SharePoint 2010 &#40;PowerPivot Configuration Tool&#41;](../configure-repair-powerpivot-sharepoint-2010.md).</span></span>  
  
 <span data-ttu-id="fe298-126">È necessario eseguire questa attività una sola volta dopo l'installazione di PowerPivot per SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fe298-126">This task only needs to be performed once, after you install PowerPivot for SharePoint.</span></span>  
  
1.  <span data-ttu-id="fe298-127">In un server che dispone di un'installazione di PowerPivot per SharePoint aprire una shell di gestione di SharePoint 2010 utilizzando l'opzione **Esegui come amministratore** .</span><span class="sxs-lookup"><span data-stu-id="fe298-127">On a server that has an installation of PowerPivot for SharePoint, open a SharePoint 2010 Management Shell using the **Run as Administrator** option.</span></span>  
  
2.  <span data-ttu-id="fe298-128">Eseguire il seguente cmdlet per aggiungere la soluzione farm.</span><span class="sxs-lookup"><span data-stu-id="fe298-128">Run the following cmdlet to add the farm solution.</span></span>  
  
    ```powershell
    Add-SPSolution -LiteralPath "C:\Program Files\Microsoft SQL Server\110\Tools\PowerPivotTools\ConfigurationTool\Resources\PowerPivotFarm.wsp"  
    ```  
  
     <span data-ttu-id="fe298-129">Il cmdlet restituisce il nome e l'ID della soluzione e Deployed=False.</span><span class="sxs-lookup"><span data-stu-id="fe298-129">The cmdlet returns the name of the solution, its solution ID, and Deployed=False.</span></span> <span data-ttu-id="fe298-130">Nel passaggio successivo la soluzione verrà distribuita.</span><span class="sxs-lookup"><span data-stu-id="fe298-130">In the next step, you will deploy the solution.</span></span>  
  
3.  <span data-ttu-id="fe298-131">Eseguire il successivo cmdlet per distribuire la soluzione farm:</span><span class="sxs-lookup"><span data-stu-id="fe298-131">Run the next cmdlet to deploy the farm solution:</span></span>  
  
    ```powershell
    Install-SPSolution -Identity PowerPivotFarm.wsp -GACDeployment -Force  
    ```  
  
##  <a name="step-2-deploy-the-powerpivot-web-application-solution-to-central-administration"></a><a name="deployCA"></a><span data-ttu-id="fe298-132">Passaggio 2: distribuire la soluzione applicazione Web PowerPivot in Amministrazione centrale</span><span class="sxs-lookup"><span data-stu-id="fe298-132">Step 2: Deploy the PowerPivot Web Application Solution to Central Administration</span></span>  
 <span data-ttu-id="fe298-133">Dopo la distribuzione della soluzione farm, è necessario distribuire la soluzione applicazione Web in Amministrazione centrale.</span><span class="sxs-lookup"><span data-stu-id="fe298-133">After you deploy the farm solution, you must deploy the Web application solution to Central Administration.</span></span> <span data-ttu-id="fe298-134">Tramite questo passaggio viene aggiunto il dashboard di gestione PowerPivot in Amministrazione centrale.</span><span class="sxs-lookup"><span data-stu-id="fe298-134">This step adds the PowerPivot Management Dashboard to Central Administration.</span></span>  
  
1.  <span data-ttu-id="fe298-135">Aprire una shell di gestione di SharePoint 2010 utilizzando l'opzione **Esegui come amministratore** .</span><span class="sxs-lookup"><span data-stu-id="fe298-135">Open a SharePoint 2010 Management Shell using the **Run as Administrator** option.</span></span>  
  
2.  <span data-ttu-id="fe298-136">Eseguire il seguente cmdlet per creare un riferimento ad Amministrazione centrale:</span><span class="sxs-lookup"><span data-stu-id="fe298-136">Run the following cmdlet to create a reference to Central Administration:</span></span>  
  
    ```powershell
    $centralAdmin = $(Get-SPWebApplication -IncludeCentralAdministration | Where { $_.IsAdministrationWebApplication -eq $TRUE})  
    ```  
  
3.  <span data-ttu-id="fe298-137">Eseguire il seguente cmdlet per aggiungere la soluzione farm.</span><span class="sxs-lookup"><span data-stu-id="fe298-137">Run the following cmdlet to add the farm solution.</span></span>  
  
    ```powershell
    Add-SPSolution -LiteralPath "C:\Program Files\Microsoft SQL Server\110\Tools\PowerPivotTools\ConfigurationTool\Resources\PowerPivotWebApp.wsp"  
    ```  
  
     <span data-ttu-id="fe298-138">Il cmdlet restituisce il nome e l'ID della soluzione e Deployed=False.</span><span class="sxs-lookup"><span data-stu-id="fe298-138">The cmdlet returns the name of the solution, its solution ID, and Deployed=False.</span></span> <span data-ttu-id="fe298-139">Nel passaggio successivo la soluzione verrà distribuita.</span><span class="sxs-lookup"><span data-stu-id="fe298-139">In the next step, you will deploy the solution.</span></span>  
  
4.  <span data-ttu-id="fe298-140">Eseguire il successivo cmdlet per installare la soluzione applicazione Web in Amministrazione centrale.</span><span class="sxs-lookup"><span data-stu-id="fe298-140">Run the next cmdlet to install the web application solution to Central Administration.</span></span>  
  
    ```powershell
    Install-SPSolution -Identity PowerPivotWebApp.wsp -GACDeployment -Force -WebApplication $centralAdmin  
    ```  
  
 <span data-ttu-id="fe298-141">Dopo la distribuzione della soluzione applicazione Web in Amministrazione centrale, sarà possibile utilizzare questo strumento per completare tutti i passaggi di configurazione rimanenti.</span><span class="sxs-lookup"><span data-stu-id="fe298-141">Now that the web application solution is deployed to Central Administration, you can use Central Administration to complete all remaining configuration steps.</span></span>  
  
##  <a name="step-3-deploy-the-powerpivot-web-application-solution-to-other-web-applications"></a><a name="deployUI"></a><span data-ttu-id="fe298-142">Passaggio 3: distribuire la soluzione applicazione Web PowerPivot ad altre applicazioni Web</span><span class="sxs-lookup"><span data-stu-id="fe298-142">Step 3: Deploy the PowerPivot Web Application Solution to Other Web Applications</span></span>  
 <span data-ttu-id="fe298-143">Nell'attività precedente si è distribuito Powerpivotwebapp.wsp in Amministrazione centrale.</span><span class="sxs-lookup"><span data-stu-id="fe298-143">In the previous task, you deployed Powerpivotwebapp.wsp to Central Administration.</span></span> <span data-ttu-id="fe298-144">In questa sezione si provvederà alla distribuzione di powerpivotwebapp.wsp in un'applicazione Web esistente che supporta l'accesso ai dati PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="fe298-144">In this section, you deploy the powerpivotwebapp.wsp on each existing web application that supports PowerPivot data access.</span></span> <span data-ttu-id="fe298-145">Se in seguito si aggiungono altre applicazioni Web, assicurarsi di ripetere questo passaggio anche per tali applicazioni.</span><span class="sxs-lookup"><span data-stu-id="fe298-145">If you add more web applications later, be sure to repeat this step for those additional web applications.</span></span>  
  
1.  <span data-ttu-id="fe298-146">In Impostazioni sistema di Amministrazione centrale fare clic su **Gestisci soluzioni farm**.</span><span class="sxs-lookup"><span data-stu-id="fe298-146">In Central Administration, in System Settings, click **Manage farm solutions**.</span></span>  
  
2.  <span data-ttu-id="fe298-147">Fare clic su **powerpivotwebapp. wsp**.</span><span class="sxs-lookup"><span data-stu-id="fe298-147">Click **powerpivotwebapp.wsp**.</span></span>  
  
3.  <span data-ttu-id="fe298-148">Fare clic su **Distribuisci soluzione**.</span><span class="sxs-lookup"><span data-stu-id="fe298-148">Click **Deploy Solution**.</span></span>  
  
4.  <span data-ttu-id="fe298-149">In **Distribuisci in?** selezionare l'applicazione Web di SharePoint per cui si desidera aggiungere il supporto della funzionalità PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="fe298-149">In **Deploy To?**, select the SharePoint web application for which you want to add PowerPivot feature support.</span></span>  
  
5.  <span data-ttu-id="fe298-150">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="fe298-150">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="fe298-151">Ripetere l'operazione per le altre applicazioni Web SharePoint che supporteranno l'accesso ai dati PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="fe298-151">Repeat for other SharePoint web applications that will also support PowerPivot data access.</span></span>  
  
##  <a name="redeploy-or-retract-the-solution"></a><a name="retract"></a> <span data-ttu-id="fe298-152">Ridistribuire o ritirare la soluzione</span><span class="sxs-lookup"><span data-stu-id="fe298-152">Redeploy or retract the Solution</span></span>  
 <span data-ttu-id="fe298-153">Sebbene Amministrazione centrale SharePoint consenta il ritiro della soluzione, non è necessario ritirare il file powerpivotwebapp.wsp a meno che si stia sistematicamente eseguendo la risoluzione dei problemi relativi a un'installazione o alla distribuzione di una patch.</span><span class="sxs-lookup"><span data-stu-id="fe298-153">Although SharePoint Central Administration provides solution retraction, you do not need to retract the powerpivotwebapp.wsp file unless you are systematically troubleshooting an installation or patch deployment problem.</span></span>  
  
1.  <span data-ttu-id="fe298-154">In Impostazioni sistema di Amministrazione centrale SharePoint 2010 fare clic su **Gestisci soluzioni farm**.</span><span class="sxs-lookup"><span data-stu-id="fe298-154">In SharePoint 2010 Central Administration, in System Settings, click **Manage farm solutions**.</span></span>  
  
2.  <span data-ttu-id="fe298-155">Fare clic su **Powerpivotwebapp.wsp**.</span><span class="sxs-lookup"><span data-stu-id="fe298-155">Click **Powerpivotwebapp.wsp**.</span></span>  
  
3.  <span data-ttu-id="fe298-156">Fare clic su **Ritira soluzione**.</span><span class="sxs-lookup"><span data-stu-id="fe298-156">Click **Retract Solution**.</span></span>  
  
 <span data-ttu-id="fe298-157">Se si verificano problemi di distribuzione del server che si riportano alla soluzione farm, è possibile ridistribuirla eseguendo l'opzione **Ripristina** nello strumento di configurazione PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="fe298-157">If you encounter server deployment issues that you trace back to the farm solution, you can redeploy it by running the **Repair** option in the PowerPivot Configuration Tool.</span></span> <span data-ttu-id="fe298-158">Le operazioni di ripristino tramite lo strumento sono preferibili perché richiedono meno passaggi da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="fe298-158">Repair operations via the tool is preferred because it requires fewer steps on your part.</span></span> <span data-ttu-id="fe298-159">Per ulteriori informazioni, vedere [configurare o ripristinare PowerPivot per SharePoint 2010 &#40;strumento di configurazione PowerPivot&#41;](../configure-repair-powerpivot-sharepoint-2010.md).</span><span class="sxs-lookup"><span data-stu-id="fe298-159">For more information, see [Configure or Repair PowerPivot for SharePoint 2010 &#40;PowerPivot Configuration Tool&#41;](../configure-repair-powerpivot-sharepoint-2010.md).</span></span>  
  
 <span data-ttu-id="fe298-160">Se si desidera ridistribuire ancora tutte le soluzioni, assicurarsi di effettuare le operazioni in questo ordine:</span><span class="sxs-lookup"><span data-stu-id="fe298-160">If you still want to re-deploy all solutions, be sure to do so in this order:</span></span>  
  
1.  <span data-ttu-id="fe298-161">Ritirare la soluzione dell'applicazione Web PowerPivot da tutte le applicazioni Web SharePoint in cui viene utilizzata.</span><span class="sxs-lookup"><span data-stu-id="fe298-161">Retract the PowerPivot Web application solution from all SharePoint web applications that use it.</span></span>  
  
2.  <span data-ttu-id="fe298-162">Ritirare la soluzione farm PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="fe298-162">Retract the PowerPivot farm solution.</span></span>  
  
3.  <span data-ttu-id="fe298-163">Ridistribuire la soluzione farm PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="fe298-163">Redeploy the PowerPivot farm solution.</span></span>  
  
4.  <span data-ttu-id="fe298-164">Ridistribuire la soluzione dell'applicazione Web PowerPivot in tutte le applicazioni Web SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fe298-164">Redeploy the PowerPivot Web application solution to all SharePoint web applications.</span></span>  
  
##  <a name="about-the-powerpivot-solutions"></a><a name="intro"></a><span data-ttu-id="fe298-165">Informazioni sulle soluzioni PowerPivot</span><span class="sxs-lookup"><span data-stu-id="fe298-165">About the PowerPivot Solutions</span></span>  
 <span data-ttu-id="fe298-166">In PowerPivot per SharePoint vengono utilizzati due pacchetti di soluzioni per distribuire le relative pagine dell'applicazione e file di programma nella farm e in singole applicazioni Web.</span><span class="sxs-lookup"><span data-stu-id="fe298-166">PowerPivot for SharePoint uses two solution packages to deploy its application pages and program files to the farm and to individual web applications.</span></span>  
  
-   <span data-ttu-id="fe298-167">La soluzione farm è globale.</span><span class="sxs-lookup"><span data-stu-id="fe298-167">The farm solution is global.</span></span> <span data-ttu-id="fe298-168">Viene distribuita una volta e quindi diventa automaticamente disponibile in qualsiasi nuovo server PowerPivot per SharePoint che verrà aggiunto alla farm.</span><span class="sxs-lookup"><span data-stu-id="fe298-168">It is deployed once and then becomes automatically available to any new PowerPivot for SharePoint servers that you add to the farm later.</span></span>  
  
-   <span data-ttu-id="fe298-169">La soluzione dell'applicazione Web è specifica dell'applicazione e deve essere distribuita a ogni applicazione Web nella farm, inclusa l'applicazione Web Amministrazione centrale.</span><span class="sxs-lookup"><span data-stu-id="fe298-169">The web application solution is application-specific and must be deployed to each web application in the farm, including the Central Administration web application.</span></span>  
  
 <span data-ttu-id="fe298-170">Ogni soluzione viene distribuita in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="fe298-170">Each solution is deployed differently.</span></span>  <span data-ttu-id="fe298-171">La soluzione della farm viene distribuita una volta, dopo l'installazione della prima istanza di PowerPivot per SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fe298-171">The farm solution is deployed once, after the first PowerPivot for SharePoint instance is installed.</span></span> <span data-ttu-id="fe298-172">Per distribuire la soluzione farm, utilizzare lo strumento di configurazione PowerPivot o i cmdlet PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fe298-172">To deploy the farm solution, you use the PowerPivot Configuration Tool or PowerShell cmdlets.</span></span>  
  
 <span data-ttu-id="fe298-173">La soluzione applicazione Web viene inizialmente distribuita ad Amministrazione centrale, seguita dalle distribuzioni successive della soluzione a qualsiasi applicazione Web aggiuntiva che supporterà le richieste di dati PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="fe298-173">The web application solution is initially deployed to Central Administration, followed by subsequent solution deployments to any additional web applications that will support requests for PowerPivot data.</span></span> <span data-ttu-id="fe298-174">Per distribuire la soluzione applicazione Web in Amministrazione centrale, è necessario utilizzare lo strumento di configurazione PowerPivot o il cmdlet PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fe298-174">To deploy the web application solution to Central Administration, you must use the PowerPivot Configuration Tool or PowerShell cmdlet.</span></span> <span data-ttu-id="fe298-175">Per tutte le altre applicazioni Web, è possibile distribuire la soluzione applicazione Web manualmente utilizzando Amministrazione centrale o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fe298-175">For all other web applications, you can deploy the web application solution manually using Central Administration or PowerShell.</span></span>  
  
|<span data-ttu-id="fe298-176">Soluzione</span><span class="sxs-lookup"><span data-stu-id="fe298-176">Solution</span></span>|<span data-ttu-id="fe298-177">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fe298-177">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="fe298-178">Powerpivotfarm.wsp</span><span class="sxs-lookup"><span data-stu-id="fe298-178">Powerpivotfarm.wsp</span></span>|<span data-ttu-id="fe298-179">Consente di aggiungere il file Microsoft.AnalysisServices.SharePoint.Integration.dll all'assembly globale.</span><span class="sxs-lookup"><span data-stu-id="fe298-179">Adds Microsoft.AnalysisServices.SharePoint.Integration.dll to the global assembly.</span></span><br /><br /> <span data-ttu-id="fe298-180">Consente di aggiungere il file Microsoft.AnalysisServices.ChannelTransport.dll all'assembly globale.</span><span class="sxs-lookup"><span data-stu-id="fe298-180">Adds Microsoft.AnalysisServices.ChannelTransport.dll to the global assembly.</span></span><br /><br /> <span data-ttu-id="fe298-181">Consente di installare funzionalità e file di risorse nonché di registrare i tipi di contenuto.</span><span class="sxs-lookup"><span data-stu-id="fe298-181">Installs features and resources files, and registers content types.</span></span><br /><br /> <span data-ttu-id="fe298-182">Aggiunge modelli di raccolta per Raccolta PowerPivot e le raccolte di feed di dati.</span><span class="sxs-lookup"><span data-stu-id="fe298-182">Adds library templates for PowerPivot Gallery and Data Feed libraries.</span></span><br /><br /> <span data-ttu-id="fe298-183">Aggiunge pagine dell'applicazione per la configurazione dell'applicazione di servizio, il dashboard di gestione di PowerPivot, l'aggiornamento dati e la raccolta PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="fe298-183">Adds application pages for service application configuration, PowerPivot Management Dashboard, data refresh, and PowerPivot Gallery.</span></span>|  
|<span data-ttu-id="fe298-184">powerpivotwebapp.wsp</span><span class="sxs-lookup"><span data-stu-id="fe298-184">Powerpivotwebapp.wsp</span></span>|<span data-ttu-id="fe298-185">Aggiunge i file di risorse Microsoft.AnalysisServices.SharePoint.Integration.dll alla cartella delle estensioni per il server Web nel server Web front-end.</span><span class="sxs-lookup"><span data-stu-id="fe298-185">Adds Microsoft.AnalysisServices.SharePoint.Integration.dll resources files to the web server extensions folder on the Web front-end.</span></span><br /><br /> <span data-ttu-id="fe298-186">Aggiunge il servizio Web PowerPivot al server Web-front end.</span><span class="sxs-lookup"><span data-stu-id="fe298-186">Adds PowerPivot Web service to the Web-front end.</span></span><br /><br /> <span data-ttu-id="fe298-187">Aggiunge la generazione di immagini di anteprima per Raccolta PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="fe298-187">Adds thumbnail image generation for PowerPivot Gallery.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fe298-188">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe298-188">See Also</span></span>  
 <span data-ttu-id="fe298-189">[PowerPivot per SharePoint di aggiornamento](../../database-engine/install-windows/upgrade-power-pivot-for-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="fe298-189">[Upgrade PowerPivot for SharePoint](../../database-engine/install-windows/upgrade-power-pivot-for-sharepoint.md) </span></span>  
 <span data-ttu-id="fe298-190">[Amministrazione e configurazione del server PowerPivot in Amministrazione centrale](power-pivot-server-administration-and-configuration-in-central-administration.md) </span><span class="sxs-lookup"><span data-stu-id="fe298-190">[PowerPivot Server Administration and Configuration in Central Administration](power-pivot-server-administration-and-configuration-in-central-administration.md) </span></span>  
 [<span data-ttu-id="fe298-191">Configurazione di PowerPivot tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe298-191">PowerPivot Configuration using Windows PowerShell</span></span>](power-pivot-configuration-using-windows-powershell.md)  
