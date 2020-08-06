---
title: 'Elenco di controllo: usare PowerShell per verificare PowerPivot per SharePoint | Microsoft Docs'
ms.custom: ''
ms.date: 07/20/2020
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 73a13f05-3450-411f-95f9-4b6167cc7607
author: minewiskan
ms.author: owend
ms.openlocfilehash: 001b3fae82851b9ec08b0383bb3db9e6d011ae32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713639"
---
# <a name="checklist-use-powershell-to-verify-powerpivot-for-sharepoint"></a><span data-ttu-id="c20d2-102">Elenco di controllo: utilizzare PowerShell per verificare PowerPivot per SharePoint</span><span class="sxs-lookup"><span data-stu-id="c20d2-102">CheckList: Use PowerShell to Verify PowerPivot for SharePoint</span></span>
  <span data-ttu-id="c20d2-103">Senza il superamento della prova di verifica con cui viene confermata l'operatività dei servizi e dei dati in uso, non vengono completate né le installazioni di [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] né le operazioni di recupero.</span><span class="sxs-lookup"><span data-stu-id="c20d2-103">No [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] installation or recovery operation is complete without a solid verification test pass that confirms your services and data are operational.</span></span> <span data-ttu-id="c20d2-104">In questo articolo viene illustrata la modalità di esecuzione di queste procedure tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c20d2-104">In this article, we show you how to perform these steps using Windows PowerShell.</span></span> <span data-ttu-id="c20d2-105">Ogni passaggio è inserito nella relativa sezione in modo da poter accedere direttamente ad attività specifiche.</span><span class="sxs-lookup"><span data-stu-id="c20d2-105">We put each step into its own section so that you can go straight to specific tasks.</span></span> <span data-ttu-id="c20d2-106">Ad esempio, eseguire lo script nella sezione [Database](#bkmk_databases) di questo argomento per verificare il nome dell'applicazione di servizio e i database del contenuto, se si desidera programmarli per la manutenzione o il backup.</span><span class="sxs-lookup"><span data-stu-id="c20d2-106">For example, run the script in the [Databases](#bkmk_databases) section of this topic to verify the name of the service application and content databases if you want to schedule them for maintenance or backup.</span></span>

|||
|-|-|
|<span data-ttu-id="c20d2-107">![Contenuto correlato di PowerShell](../../../reporting-services/media/rs-powershellicon.jpg "Contenuto correlato di PowerShell")</span><span class="sxs-lookup"><span data-stu-id="c20d2-107">![PowerShell related content](../../../reporting-services/media/rs-powershellicon.jpg "PowerShell related content")</span></span>|<span data-ttu-id="c20d2-108">Alla fine dell'argomento è disponibile uno script completo di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c20d2-108">A full PowerShell script is included at the bottom of the topic.</span></span> <span data-ttu-id="c20d2-109">Utilizzare questo script come punto di partenza per compilarne uno personalizzato per il controllo della distribuzione completa di [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c20d2-109">Use the full script as a starting point to build a custom script for auditing your full [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] deployment.</span></span>|

||
|-|
|<span data-ttu-id="c20d2-110">**[!INCLUDE[applies](../../../includes/applies-md.md)]** SharePoint 2013 &#124; SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="c20d2-110">**[!INCLUDE[applies](../../../includes/applies-md.md)]**  SharePoint 2013 &#124; SharePoint 2010</span></span>|

 <span data-ttu-id="c20d2-111">**In questo argomento**: le voci con le lettere nel sommario seguente corrispondono alle aree del diagramma.</span><span class="sxs-lookup"><span data-stu-id="c20d2-111">**In this topic**: The lettered items in the following the TOC correspond to areas of the diagram.</span></span> <span data-ttu-id="c20d2-112">Nel diagramma vengono illustrate le operazioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="c20d2-112">The diagram illustrates the</span></span>

|||
|-|-|
|[<span data-ttu-id="c20d2-113">Preparazione dell'ambiente di PowerShell</span><span class="sxs-lookup"><span data-stu-id="c20d2-113">Prepare your PowerShell environment</span></span>](#bkmk_prerequisites)<br /><br /> [<span data-ttu-id="c20d2-114">Sintomi e azioni consigliate</span><span class="sxs-lookup"><span data-stu-id="c20d2-114">Symptoms and Recommended Actions</span></span>](#bkmk_symptoms)<br /><br /> <span data-ttu-id="c20d2-115">**(A)** [Servizio Windows Analysis Services](#bkmk_windows_service)</span><span class="sxs-lookup"><span data-stu-id="c20d2-115">**(A)** [Analysis Services Windows Service](#bkmk_windows_service)</span></span><br /><br /> <span data-ttu-id="c20d2-116">**(B)** [PowerPivotSystemService e PowerPivotEngineService](#bkmk_engine_and_system_service)</span><span class="sxs-lookup"><span data-stu-id="c20d2-116">**(B)** [PowerPivotSystemService and PowerPivotEngineService](#bkmk_engine_and_system_service)</span></span><br /><br /> <span data-ttu-id="c20d2-117">**(C)** [Proxy e applicazioni di servizio PowerPivot](#bkmk_powerpivot_service_application)</span><span class="sxs-lookup"><span data-stu-id="c20d2-117">**(C)** [PowerPivot Service Application(s) and proxies](#bkmk_powerpivot_service_application)</span></span><br /><br /> <span data-ttu-id="c20d2-118">**(D)** [Database](#bkmk_databases)</span><span class="sxs-lookup"><span data-stu-id="c20d2-118">**(D)** [Databases](#bkmk_databases)</span></span><br /><br /> [<span data-ttu-id="c20d2-119">Funzionalità di SharePoint</span><span class="sxs-lookup"><span data-stu-id="c20d2-119">SharePoint Features</span></span>](#bkmk_features)<br /><br /> [<span data-ttu-id="c20d2-120">Processi timer</span><span class="sxs-lookup"><span data-stu-id="c20d2-120">Timer Jobs</span></span>](#bkmk_timer_jobs)<br /><br /> [<span data-ttu-id="c20d2-121">Regole di integrità</span><span class="sxs-lookup"><span data-stu-id="c20d2-121">Health Rules</span></span>](#bkmk_health_rules)<br /><br /> <span data-ttu-id="c20d2-122">**(E)** [Log di Servizio di registrazione unificato e di Windows](#bkmk_logs)</span><span class="sxs-lookup"><span data-stu-id="c20d2-122">**(E)** [Windows and ULS Logs](#bkmk_logs)</span></span><br /><br /> [<span data-ttu-id="c20d2-123">Provider MSOLAP</span><span class="sxs-lookup"><span data-stu-id="c20d2-123">MSOLAP Provider</span></span>](#bkmk_msolap)<br /><br /> [<span data-ttu-id="c20d2-124">Libreria client ADOMD.Net</span><span class="sxs-lookup"><span data-stu-id="c20d2-124">ADOMD.Net client Library</span></span>](#bkmk_adomd)<br /><br /> [<span data-ttu-id="c20d2-125">Regole di raccolta dati di integrità</span><span class="sxs-lookup"><span data-stu-id="c20d2-125">Health Data Collection Rules</span></span>](#bkmk_health_collection)<br /><br /> [<span data-ttu-id="c20d2-126">Soluzioni</span><span class="sxs-lookup"><span data-stu-id="c20d2-126">Solutions</span></span>](#bkmk_solutions)<br /><br /> [<span data-ttu-id="c20d2-127">Passaggi di verifica manuali</span><span class="sxs-lookup"><span data-stu-id="c20d2-127">Manual Verification Steps</span></span>](#bkmk_manual)<br /><br /> [<span data-ttu-id="c20d2-128">Altre risorse</span><span class="sxs-lookup"><span data-stu-id="c20d2-128">More Resources</span></span>](#bkmk_more_resources)<br /><br /> [<span data-ttu-id="c20d2-129">Script completo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="c20d2-129">Full PowerShell Script</span></span>](#bkmk_full_script)|<span data-ttu-id="c20d2-130">![verifica di powershell di powerpivot](../../../sql-server/install/media/ssas-powershell-component-verification.png "verifica di powershell di powerpivot")</span><span class="sxs-lookup"><span data-stu-id="c20d2-130">![powershell verification of powerpivot](../../../sql-server/install/media/ssas-powershell-component-verification.png "powershell verification of powerpivot")</span></span>|

##  <a name="prepare-your-powershell-environment"></a><a name="bkmk_prerequisites"></a><span data-ttu-id="c20d2-131">Preparare l'ambiente di PowerShell</span><span class="sxs-lookup"><span data-stu-id="c20d2-131">Prepare your PowerShell environment</span></span>
 <span data-ttu-id="c20d2-132">Con i passaggi descritti in questa sezione viene preparato l'ambiente di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c20d2-132">The steps in this section prepare your PowerShell environment.</span></span> <span data-ttu-id="c20d2-133">I passaggi possono non essere necessari, a seconda dell'ambiente di scripting attualmente configurato.</span><span class="sxs-lookup"><span data-stu-id="c20d2-133">The steps may not be required, depending on how your scripting environment is currently configured.</span></span>

 <span data-ttu-id="c20d2-134">**Autorizzazioni di PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c20d2-134">**PowerShell Permissions**</span></span>

 <span data-ttu-id="c20d2-135">Aprire una finestra di Powershell o PowerShell ISE (Integrated Scripting Environment) con **privilegi amministrativi**.</span><span class="sxs-lookup"><span data-stu-id="c20d2-135">Open a Powershell window or the PowerShell ISE (Integrated Scripting Environment) with **administrative privileges**.</span></span> <span data-ttu-id="c20d2-136">Se non si dispone di questi privilegi quando si eseguono i comandi, verrà visualizzato un messaggio di errore simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c20d2-136">If you do not have administrative privileges when you run commands, you will see an error message similar to the following:</span></span>

 <span data-ttu-id="c20d2-137">Get-SPLogEvent: è necessario disporre di **privilegi amministrativi** per il computer per eseguire questo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c20d2-137">Get-SPLogEvent : You need to have Machine **administrator privileges** to run this cmdlet.</span></span>

 <span data-ttu-id="c20d2-138">**Modulo di SharePoint e [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="c20d2-138">**SharePoint and [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)]** Module</span></span>

 <span data-ttu-id="c20d2-139">Se viene visualizzato un messaggio di errore analogo a quello riportato di seguito quando si eseguono i cmdlet correlati a SharePoint, eseguire il comando Add-PSSnapin:</span><span class="sxs-lookup"><span data-stu-id="c20d2-139">If you see an error message similar to the following when you run SharePoint related cmdlets, run the Add-PSSnapin command:</span></span>

 <span data-ttu-id="c20d2-140">Termine 'Get-PowerPivotSystemService' **non riconosciuto come nome di cmdlet**, funzione, programma eseguibile o file script.</span><span class="sxs-lookup"><span data-stu-id="c20d2-140">The term 'Get-PowerPivotSystemService' **is not recognized as the name of a cmdlet**, function, script file, or operable program.</span></span> <span data-ttu-id="c20d2-141">Verificare l'ortografia del nome, che il percorso sia incluso e corretto, quindi riprovare.</span><span class="sxs-lookup"><span data-stu-id="c20d2-141">Check the spelling of the name, or if a path was included, verify that the path is correct and try again.</span></span>

```
Add-PSSnapin Microsoft.Sharepoint.Powershell -EA 0
```

 <span data-ttu-id="c20d2-142">**Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c20d2-142">**Windows PowerShell**</span></span>

 <span data-ttu-id="c20d2-143">Per ulteriori informazioni su PowerShell ISE, vedere [Introduzione a Windows PowerShell ISE](https://technet.microsoft.com/library/dd315244.aspx) e [Utilizzare Windows PowerShell per amministrare SharePoint 2013](https://technet.microsoft.com/library/ee806878\(v=office.15\).aspx).</span><span class="sxs-lookup"><span data-stu-id="c20d2-143">For more information on the PowerShell ISE, see [Introducing the Windows PowerShell ISE](https://technet.microsoft.com/library/dd315244.aspx) and [Use Windows PowerShell to administer SharePoint 2013](https://technet.microsoft.com/library/ee806878\(v=office.15\).aspx).</span></span>

|||
|-|-|
|<span data-ttu-id="c20d2-144">![powerpivot nel set di applicazioni generali sharepoint](../../../sql-server/install/media/ssas-powerpivot-logo.png "powerpivot nel set di applicazioni generali sharepoint")</span><span class="sxs-lookup"><span data-stu-id="c20d2-144">![powerpivot in sharepoint general application set](../../../sql-server/install/media/ssas-powerpivot-logo.png "powerpivot in sharepoint general application set")</span></span>|<span data-ttu-id="c20d2-145">È possibile verificare facoltativamente la maggior parte dei componenti in Amministrazione centrale utilizzando il dashboard di gestione [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c20d2-145">You can optionally verify a majority of the components in Central Administration, using the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] management dashboard.</span></span> <span data-ttu-id="c20d2-146">Per aprire il dashboard in Amministrazione centrale, fare clic su **Impostazioni generali applicazione**, quindi scegliere **Dashboard di gestione** in **PowerPivot**.</span><span class="sxs-lookup"><span data-stu-id="c20d2-146">To open the dashboard in Central Administration, click **General Application Settings**, and then click **Management Dashboard** in the **PowerPivot**.</span></span> <span data-ttu-id="c20d2-147">Per ulteriori informazioni sul dashboard, vedere [PowerPivot Management Dashboard and Usage Data](../../power-pivot-sharepoint/power-pivot-management-dashboard-and-usage-data.md).</span><span class="sxs-lookup"><span data-stu-id="c20d2-147">For more information on the dashboard, see [PowerPivot Management Dashboard and Usage Data](../../power-pivot-sharepoint/power-pivot-management-dashboard-and-usage-data.md).</span></span>|

##  <a name="symptoms-and-recommended-actions"></a><a name="bkmk_symptoms"></a><span data-ttu-id="c20d2-148">Sintomi e azioni consigliate</span><span class="sxs-lookup"><span data-stu-id="c20d2-148">Symptoms and Recommended Actions</span></span>
 <span data-ttu-id="c20d2-149">Nella tabella seguente è riportato un elenco di sintomi o problemi e la sezione suggerita di questo argomento da consultare per consentire la risoluzione del problema.</span><span class="sxs-lookup"><span data-stu-id="c20d2-149">The following table is a list of symptoms or issues and the suggested section of this topic to consult to help you resolve the issue.</span></span>

|<span data-ttu-id="c20d2-150">Sintomo</span><span class="sxs-lookup"><span data-stu-id="c20d2-150">Symptom</span></span>|<span data-ttu-id="c20d2-151">Sezione di riferimento</span><span class="sxs-lookup"><span data-stu-id="c20d2-151">See section</span></span>|
|-------------|-----------------|
|<span data-ttu-id="c20d2-152">Aggiornamento dati non in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="c20d2-152">Data refresh is not running</span></span>|<span data-ttu-id="c20d2-153">Vedere la sezione [Timer Jobs](#bkmk_timer_jobs) e verificare che **Processo timer di aggiornamento dati PowerPivot** sia online.</span><span class="sxs-lookup"><span data-stu-id="c20d2-153">See the section [Timer Jobs](#bkmk_timer_jobs) and verify the **Online PowerPivot Data Refresh Timer Job** is online.</span></span>|
|<span data-ttu-id="c20d2-154">Dati del dashboard di gestione obsoleti</span><span class="sxs-lookup"><span data-stu-id="c20d2-154">Management dashboard data is old</span></span>|<span data-ttu-id="c20d2-155">Vedere la sezione [Processi timer](#bkmk_timer_jobs) e verificare che **Processo timer di elaborazione dashboard di gestione dati PowerPivot** sia online.</span><span class="sxs-lookup"><span data-stu-id="c20d2-155">See the section [Timer Jobs](#bkmk_timer_jobs) and verify the **Management Dashboard Processing Timer Job** is online.</span></span>|
|<span data-ttu-id="c20d2-156">Alcune parti del dashboard di gestione</span><span class="sxs-lookup"><span data-stu-id="c20d2-156">Some portions of the Management Dashboard</span></span>|<span data-ttu-id="c20d2-157">Se si installa PowerPivot per SharePoint in una farm che dispone della topologia di Amministrazione centrale, senza Excel Services o PowerPivot per SharePoint, è necessario scaricare e installare la libreria client Microsoft ADOMD.NET se si desidera l'accesso completo ai report incorporati nel dashboard di gestione PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="c20d2-157">If you install PowerPivot for SharePoint into a farm that has the topology of Central Administration, without Excel Services or PowerPivot for SharePoint, you must download and install the Microsoft ADOMD.NET client library if you want full access to the built-in reports in the PowerPivot management dashboard.</span></span> <span data-ttu-id="c20d2-158">Alcuni report nel dashboard utilizzano ADOMD.NET per accedere a dati interni relativi all'integrità del server e all'elaborazione query di PowerPivot nella farm.</span><span class="sxs-lookup"><span data-stu-id="c20d2-158">Some reports in the dashboard use ADOMD.NET to access internal data that provides reporting data on PowerPivot query processing and server health in the farm.</span></span> <span data-ttu-id="c20d2-159">Vedere la sezione [Libreria client ADOMD.NET](#bkmk_adomd) e l'argomento [Installare ADOMD.NET in server front-end Web in cui viene eseguita Amministrazione centrale](../../../sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="c20d2-159">See the section [ADOMD.Net client Library](#bkmk_adomd) and the topic [Install ADOMD.NET on Web Front-End Servers Running Central Administration](../../../sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md).</span></span>|
|\<future content>||

##  <a name="analysis-services-windows-service"></a><a name="bkmk_windows_service"></a><span data-ttu-id="c20d2-160">Servizio Analysis Services Windows</span><span class="sxs-lookup"><span data-stu-id="c20d2-160">Analysis Services Windows Service</span></span>
 <span data-ttu-id="c20d2-161">Con lo script in questa sezione viene verificata l'istanza di [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in modalità SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c20d2-161">The script in this section verifies the instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in SharePoint mode.</span></span> <span data-ttu-id="c20d2-162">Verificare che il servizio sia **in esecuzione**.</span><span class="sxs-lookup"><span data-stu-id="c20d2-162">Verify the service is **running**.</span></span>

```powershell
Get-Service | Select name, displayname, status | Where {$_.Name -eq "msolap`$powerpivot"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name              DisplayName                                Status
----              -----------                                ------
MSOLAP$POWERPIVOT SQL Server Analysis Services (POWERPIVOT) Running
```

##  <a name="powerpivotsystemservice-and-powerpivotengineservice"></a><a name="bkmk_engine_and_system_service"></a><span data-ttu-id="c20d2-163">PowerPivotSystemService e PowerPivotEngineService</span><span class="sxs-lookup"><span data-stu-id="c20d2-163">PowerPivotSystemService and PowerPivotEngineService</span></span>
 <span data-ttu-id="c20d2-164">Con gli script in questa sezione si verificano i servizi di sistema [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c20d2-164">The scripts in this section verify the [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] system services.</span></span> <span data-ttu-id="c20d2-165">Sono disponibili un servizio di sistema per una distribuzione di SharePoint 2013 e due servizi per una distribuzione di SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="c20d2-165">There is one system service for a SharePoint 2013 deployment and two services for a SharePoint 2010 deployment.</span></span>

 <span data-ttu-id="c20d2-166">**PowerPivotSystemService**</span><span class="sxs-lookup"><span data-stu-id="c20d2-166">**PowerPivotSystemService**</span></span>

 <span data-ttu-id="c20d2-167">Verificare che lo stato sia **online**.</span><span class="sxs-lookup"><span data-stu-id="c20d2-167">Verify the Status is **Online**.</span></span>

```powershell
Get-PowerPivotSystemService | Select typename, status, applications, farm | Format-Table -Property * -AutoSize | Out-Default
```

```Output
TypeName                                  Status Applications                             Farm
--------                                  ------ ------------                             ----
SQL Server PowerPivot Service Application Online {Default PowerPivot Service Application} SPFarm Name=SharePoint_Config_77d8ab0744a34e8aa27c806a2b8c760c
```

 <span data-ttu-id="c20d2-168">**PowerPivotEngineService**</span><span class="sxs-lookup"><span data-stu-id="c20d2-168">**PowerPivotEngineService**</span></span>

> [!NOTE]
>  <span data-ttu-id="c20d2-169">**Ignorare questo script se** si utilizza SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="c20d2-169">**Skip this script if** you are using SharePoint 2013.</span></span> <span data-ttu-id="c20d2-170">PowerPivotEngineService non fa parte di una distribuzione di SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="c20d2-170">The PowerPivotEngineService is not part of a SharePoint 2013 deployment.</span></span> <span data-ttu-id="c20d2-171">Se si esegue il cmdlet Get-PowerPivot**Engine**Service in SharePoint 2013, verrà visualizzato un messaggio di errore simile a quello riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="c20d2-171">If you run the Get-PowerPivot**Engine**Service cmdlet on SharePoint 2013, you will see an error message similar to the following.</span></span> <span data-ttu-id="c20d2-172">Questo messaggio viene restituito anche se è stato eseguito il comando Add-PSSnapin descritto nella sezione relativa ai prerequisiti di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="c20d2-172">This error message is returned even if you have run the Add-PSSnapin command described in the prerequisites section of this topic.</span></span>
> 
>  <span data-ttu-id="c20d2-173">Termine 'Get-PowerPivotEngineService' non è riconosciuto come nome di un cmdlet</span><span class="sxs-lookup"><span data-stu-id="c20d2-173">The term 'Get-PowerPivotEngineService' is not recognized as the name of a cmdlet</span></span>

 <span data-ttu-id="c20d2-174">In una distribuzione di SharePoint 2010 verificare che lo stato sia **Online**.</span><span class="sxs-lookup"><span data-stu-id="c20d2-174">In a SharePoint 2010 deployment, verify the status is **Online**.</span></span>

```powershell
Get-PowerPivotEngineService | Select typename, status, name, instances, farm | Format-Table -Property * -AutoSize | Out-Default
```

```Output
TypeName  : SQL Server Analysis Services
Status    : Online
Name      : MSOLAP$POWERPIVOT
Instances : {POWERPIVOT}
Farm      : SPFarm Name=SharePoint_Config
```

##  <a name="powerpivot-service-applications-and-proxies"></a><a name="bkmk_powerpivot_service_application"></a><span data-ttu-id="c20d2-175">Proxy e applicazioni di servizio PowerPivot</span><span class="sxs-lookup"><span data-stu-id="c20d2-175">PowerPivot Service Application(s) and proxies</span></span>
 <span data-ttu-id="c20d2-176">Verificare che lo stato sia **Online**.</span><span class="sxs-lookup"><span data-stu-id="c20d2-176">Verify the status is **Online**.</span></span> <span data-ttu-id="c20d2-177">Tramite l'applicazione Excel Services non viene utilizzato un database dell'applicazione di servizio e pertanto il cmdlet non restituisce un nome di database.</span><span class="sxs-lookup"><span data-stu-id="c20d2-177">The Excel Services Application does not use a service application database and therefore the cmdlet does not return a database name.</span></span> <span data-ttu-id="c20d2-178">Si prenda nota del database utilizzato dall'applicazione di servizio [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] in modo da poter verificare che sia online nella sezione del database più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="c20d2-178">Note the database used by the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] service application so you can verify the database is online in the database section later in this topic.</span></span>

 <span data-ttu-id="c20d2-179">**Applicazioni di servizio PowerPivot ed Excel**</span><span class="sxs-lookup"><span data-stu-id="c20d2-179">**PowerPivot and Excel Service Application(s)**</span></span>

 <span data-ttu-id="c20d2-180">Per una distribuzione di SharePoint 2010, verificare che lo stato sia **Online**.</span><span class="sxs-lookup"><span data-stu-id="c20d2-180">For a SharePoint 2010 deployment, verify the status is **Online**.</span></span>

```powershell
Get-PowerPivotServiceApplication | Select typename,name, status, unattendedaccount, applicationpool, farm, database
Get-SPExcelServiceApplication | Select typename, DisplayName, status
```

```Output
TypeName          : PowerPivot Service Application
Name              : PowerPivotServiceApplication1
Status            : Online
UnattendedAccount : PowerPivotUnattendedAccount
ApplicationPool   : SPIisWebServiceApplicationPool Name=sqlbi_serviceapp
Farm              : SPFarm Name=SharePoint_Config
Database          : GeminiServiceDatabase Name=PowerPivotServiceApplication1_19648f3f2c944e27acdc6c20aab8487a

TypeName    : Excel Services Application Web Service Application
DisplayName : Excel Services Application
Status      : Online
```

 <span data-ttu-id="c20d2-181">**Pool di applicazioni del servizio**</span><span class="sxs-lookup"><span data-stu-id="c20d2-181">**Service Application Pool**</span></span>

> [!NOTE]
>  <span data-ttu-id="c20d2-182">Nell'esempio di codice seguente viene restituita innanzitutto la proprietà applicationpool dell'applicazione di servizio [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] predefinita.</span><span class="sxs-lookup"><span data-stu-id="c20d2-182">The following code sample first returns the applicationpool property of the default [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] service application.</span></span> <span data-ttu-id="c20d2-183">Il nome viene analizzato dalla stringa e viene utilizzato per ottenere lo stato dell'oggetto pool di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="c20d2-183">The name is parsed from the string and used to get the status of the application pool object.</span></span>
> 
>  <span data-ttu-id="c20d2-184">Verificare che lo stato sia **online**.</span><span class="sxs-lookup"><span data-stu-id="c20d2-184">Verify the Status is **Online**.</span></span> <span data-ttu-id="c20d2-185">Se lo stato non è online o viene visualizzato "errore http" quando si Esplora il [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] sito, verificare che le credenziali di identità nei pool di applicazioni IIS siano ancora corrette.</span><span class="sxs-lookup"><span data-stu-id="c20d2-185">If the status is not Online or you see "http error" when you browse the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] site, verify the identity credentials in the IIS application pools are still correct.</span></span> <span data-ttu-id="c20d2-186">Il nome del pool IIS è il valore della proprietà ID restituita dal comando Get-SPServiceApplicationPool.</span><span class="sxs-lookup"><span data-stu-id="c20d2-186">The IIS pool name will is the value of the ID property returned by the Get-SPServiceApplicationPool command.</span></span>

```powershell
$poolname = [string](Get-PowerPivotServiceApplication | Select -Property applicationpool)
$position = $poolname.lastindexof("=")
$poolname = $poolname.substring($position+1)
$poolname = $poolname.substring(0,$poolname.length-1)

Get-SPServiceApplicationPool | Select name, status, processaccountname, id | Where {$_.Name -eq $poolname} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name                           Status ProcessAccountName Id
----                           ------ ------------------ ------- 
SharePoint Web Services System Online DOMAIN\account     89b50ec3-49e3-4de7-881a-2cec4b8b73ea
```

 ![Nota](../../../reporting-services/media/rs-fyinote.png "nota") Il pool di applicazioni può anche essere verificato nella pagina Amministrazione centrale **Gestisci applicazioni di servizio**. <span data-ttu-id="c20d2-188">Fare clic sul nome dell'applicazione di servizio, quindi su **Proprietà** sulla barra multifunzione.</span><span class="sxs-lookup"><span data-stu-id="c20d2-188">Click the name of the service application and then click **properties** in the ribbon.</span></span>

 <span data-ttu-id="c20d2-189">**Proxy delle applicazioni di servizio PowerPivot ed Excel**</span><span class="sxs-lookup"><span data-stu-id="c20d2-189">**PowerPivot and Excel Service Application proxies**</span></span>

 <span data-ttu-id="c20d2-190">Verificare che lo stato sia **online**.</span><span class="sxs-lookup"><span data-stu-id="c20d2-190">Verify the Status is **Online**.</span></span>

```powershell
Get-SPServiceApplicationProxy | Select typename, status, unattendedaccount, displayname | Where {$_.TypeName -Like "*powerpivot*" -Or $_.TypeName -Like "*excel services*"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
TypeName                                                 Status UnattendedAccount           DisplayName
--------                                                 ------ -----------------           -----------
PowerPivot Service Application Proxy                     Online PowerPivotUnattendedAccount PowerPivotServiceApplication1
Excel Services Application Web Service Application Proxy Online                             Excel Services Application
```

##  <a name="databases"></a><a name="bkmk_databases"></a> <span data-ttu-id="c20d2-191">Database</span><span class="sxs-lookup"><span data-stu-id="c20d2-191">Databases</span></span>
 <span data-ttu-id="c20d2-192">Con lo script seguente viene restituito lo stato dei database dell'applicazione di servizio e di tutti i database del contenuto.</span><span class="sxs-lookup"><span data-stu-id="c20d2-192">The following script returns the status of the service application databases and all content databases.</span></span> <span data-ttu-id="c20d2-193">Verificare che lo stato sia **Online**.</span><span class="sxs-lookup"><span data-stu-id="c20d2-193">Verify the status is **Online**.</span></span>

```powershell
Get-SPDatabase | Select name, status, server, typename | Where {$_.TypeName -eq "content database" -Or $_.TypeName -Like "*Gemini*"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name                                                                       Status Server                  TypeName 
----                                                                       ------ ------                  -------- 
DefaultPowerPivotServiceApplicationDB-38422181-2b68-4ab2-b2bb-9c00c39e5a5e Online SPServer Name=TESTSERVER Microsoft.AnalysisServices.SPAddin.GeminiServiceDatabase
DefaultWebApplicationDB-f0db1a8e-4c22-408c-b9b9-153bd74b0312               Online TESTSERVER\POWERPIVOT    Content Database 
SharePoint_Admin_3cadf0b098bf49e0bb15abd487f5c684                          Online TESTSERVER\POWERPIVOT    Content Database
```

##  <a name="sharepoint-features"></a><a name="bkmk_features"></a><span data-ttu-id="c20d2-194">Funzionalità di SharePoint</span><span class="sxs-lookup"><span data-stu-id="c20d2-194">SharePoint Features</span></span>
 <span data-ttu-id="c20d2-195">Verificare che le funzionalità del sito, del Web e della farm siano online.</span><span class="sxs-lookup"><span data-stu-id="c20d2-195">Verify the site, web, and farm features are online.</span></span>

```powershell
Get-SPFeature | Select displayname, status, scope, farm | Where {$_.displayName -Like "*powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
DisplayName     Status Scope Farm                         
-----------     ------ ----- ----                         
PowerPivotSite  Online  Site SPFarm Name=SharePoint_Config
PowerPivotAdmin Online   Web SPFarm Name=SharePoint_Config
PowerPivot      Online  Farm SPFarm Name=SharePoint_Config
```

##  <a name="timer-jobs"></a><a name="bkmk_timer_jobs"></a><span data-ttu-id="c20d2-196">Processi timer</span><span class="sxs-lookup"><span data-stu-id="c20d2-196">Timer Jobs</span></span>
 <span data-ttu-id="c20d2-197">Verificare che i processi timer siano **Online**.</span><span class="sxs-lookup"><span data-stu-id="c20d2-197">Verify the Time Jobs are **Online**.</span></span> <span data-ttu-id="c20d2-198">EngineService di [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] non è installato in SharePoint 2013, pertanto tramite lo script non verranno elencati i processi timer di EngineService in una distribuzione di SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="c20d2-198">The [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] EngineService is not installed on SharePoint 2013, therefore the script will not list EngineService timer jobs in a SharePoint 2013 deployment.</span></span>

```powershell
Get-SPTimerJob | Where {$_.service -Like "*power*" -Or $_.service -Like "*mid*"} | Select status, displayname, LastRunTime, service | Format-Table -Property * -AutoSize | Out-Default
```

```Output
      Status DisplayName                                                                          LastRunTime          Service                             
------ -----------                                                                          -----------          -------                             
Online Health Analysis Job (Daily, SQL Server Analysis Services, All Servers)               4/9/2014 12:00:01 AM EngineService Name=MSOLAP$POWERPIVOT
Online Health Analysis Job (Hourly, SQL Server Analysis Services, All Servers)              4/9/2014 1:00:01 PM  EngineService Name=MSOLAP$POWERPIVOT
Online Health Analysis Job (Weekly, SQL Server Analysis Services, All Servers)              4/6/2014 12:00:10 AM EngineService Name=MSOLAP$POWERPIVOT
Online PowerPivot Management Dashboard Processing Timer Job                                 4/8/2014 3:45:38 AM  MidTierService
Online PowerPivot Health Statistics Collector Timer Job                                     4/9/2014 1:00:12 PM  MidTierService
Online PowerPivot Data Refresh Timer Job                                                    4/9/2014 1:09:36 PM  MidTierService
Online Health Analysis Job (Daily, SQL Server PowerPivot Service Application, All Servers)  4/9/2014 12:00:00 AM MidTierService
Online Health Analysis Job (Daily, SQL Server PowerPivot Service Application, Any Server)   4/9/2014 12:00:00 AM MidTierService
Online Health Analysis Job (Weekly, SQL Server PowerPivot Service Application, All Servers) 4/6/2014 12:00:03 AM MidTierService
Online Health Analysis Job (Weekly, SQL Server PowerPivot Service Application, Any Server)  4/6/2014 12:00:03 AM MidTierService
Online PowerPivot Setup Extension Timer Job                                                 4/1/2014 1:40:31 AM  MidTierService
```

##  <a name="health-rules"></a><a name="bkmk_health_rules"></a><span data-ttu-id="c20d2-199">Regole di integrità</span><span class="sxs-lookup"><span data-stu-id="c20d2-199">Health Rules</span></span>
 <span data-ttu-id="c20d2-200">Sono presenti meno regole in una distribuzione di SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="c20d2-200">There are fewer rules in a SharePoint 2013 deployment.</span></span> <span data-ttu-id="c20d2-201">Per un elenco completo delle regole per ogni ambiente di SharePoint e una spiegazione di come usare le regole, vedere [regole di integrità di PowerPivot-Configure](../../power-pivot-sharepoint/configure-power-pivot-health-rules.md).</span><span class="sxs-lookup"><span data-stu-id="c20d2-201">For a full list of rules for each SharePoint environment and an explanation of how to use the rules, see [PowerPivot Health Rules - Configure](../../power-pivot-sharepoint/configure-power-pivot-health-rules.md).</span></span>

```powershell
Get-SPHealthAnalysisRule | Select name, enabled, summary | Where {$_.summary -Like "*power*"}  | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name                          Enabled Summary
----                          ------- -------         
SecondaryLogonHealthRule         True PowerPivot:  Secondary Logon service (seclogon) is disabled
DataRefreshTimerJobHealthRule    True PowerPivot: The PowerPivot Data Refresh timer job is disabled.
ASUsageLoadHealthRule            True PowerPivot: The ratio of load events to connections is too high.
ASMiniDumpHealthRule             True PowerPivot: One or more minidump files were found in the Logs directory, indicating a program crash
ASUsageCubeRule                  True PowerPivot: Usage data is not getting updated at the expected frequency.
ASADOMDNETHealthRule             True PowerPivot: ADOMD.NET is not installed on a standalone WFE that is configured for central admin
MidTierAcctReadPermissionRule    True PowerPivot: MidTier process account should have 'Full Read' permission on all associated SPWebApplications.
```

##  <a name="windows-and-uls-logs"></a><a name="bkmk_logs"></a><span data-ttu-id="c20d2-202">Log di Windows e ULS</span><span class="sxs-lookup"><span data-stu-id="c20d2-202">Windows and ULS Logs</span></span>
 <span data-ttu-id="c20d2-203">**Registro eventi di Windows**</span><span class="sxs-lookup"><span data-stu-id="c20d2-203">**Windows event log**</span></span>

 <span data-ttu-id="c20d2-204">Tramite il comando seguente verrà ricercato il registro eventi di Windows per eventi correlati all'istanza di [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in modalità SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c20d2-204">The following command will search the windows event log for events related to the instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in SharePoint mode.</span></span> <span data-ttu-id="c20d2-205">Per informazioni sulla disabilitazione degli eventi o sulla modifica del livello di evento, vedere [configurare e visualizzare i file di log di SharePoint e la registrazione diagnostica &#40;PowerPivot per SharePoint&#41;](../../power-pivot-sharepoint/configure-and-view-sharepoint-and-diagnostic-logging.md).</span><span class="sxs-lookup"><span data-stu-id="c20d2-205">For information on disabling events or changing the event level, see [Configure and View SharePoint Log Files  and Diagnostic Logging &#40;PowerPivot for SharePoint&#41;](../../power-pivot-sharepoint/configure-and-view-sharepoint-and-diagnostic-logging.md).</span></span>

 <span data-ttu-id="c20d2-206">**Nome servizio:** MSOLAP$POWERPIVOT</span><span class="sxs-lookup"><span data-stu-id="c20d2-206">**Service Name:** MSOLAP$POWERPIVOT</span></span>

 <span data-ttu-id="c20d2-207">**Nome visualizzato nei servizi Windows** : SQL Server Analysis Services (POWERPIVOT)</span><span class="sxs-lookup"><span data-stu-id="c20d2-207">**Display name in Windows Services:** SQL Server Analysis Services (POWERPIVOT)</span></span>

```powershell
Get-EventLog "application" | Where-Object {$_.source -Like "msolap`$powerpivot*"}  | Select timegenerated, entrytype , source, message | Format-Table -property * -AutoSize | Out-Default
```

```Output
TimeGenerated           EntryType Source            Message
-------------           --------- ------            -------
4/16/2014 1:45:19 PM  Information MSOLAP$POWERPIVOT Software usage metrics are disabled.
4/16/2014 1:45:19 PM  Information MSOLAP$POWERPIVOT Service started. Microsoft SQL Server Analysis Services 64 Bit Evaluation (x64) RTM 12.0.1997.5.
4/16/2014 1:45:18 PM  Information MSOLAP$POWERPIVOT The flight recorder was started.
4/14/2014 6:45:37 PM  Information MSOLAP$POWERPIVOT Software usage metrics are disabled.
```

 <span data-ttu-id="c20d2-208">**Log di Servizio di registrazione unificato di SharePoint, ultime 48 ore**</span><span class="sxs-lookup"><span data-stu-id="c20d2-208">**SharePoint ULS Log, last 48 hours**</span></span>

 <span data-ttu-id="c20d2-209">Tramite il comando seguente verranno restituiti i messaggi di [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] dal log di Servizio di registrazione unificato creati nelle ultime 48 ore.</span><span class="sxs-lookup"><span data-stu-id="c20d2-209">The following command will return [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] messages from the ULS log that were created in the last 48 hours.</span></span> <span data-ttu-id="c20d2-210">Modificare il parametro addhours in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="c20d2-210">Adjust the addhours parameter for your need.</span></span>

```powershell
Get-SPLogEvent -StartTime(Get-Date).AddHours(-48) | Where-Object {$_.Area -eq "powerpivot service" -and $_.level -eq "high"} | Select timestamp, area, category, eventid,level, message | Format-Table -Property * -AutoSize | Out-Default
```

 <span data-ttu-id="c20d2-211">Con la variazione seguente del comando vengono restituiti solo gli eventi del log per la categoria di **aggiornamento dati** .</span><span class="sxs-lookup"><span data-stu-id="c20d2-211">The following variation of the command only returns log events for the **data refresh** category.</span></span>

```powershell
Get-SPLogEvent -starttime(Get-Date).addhours(-48) | Where-Object {$_.category -eq "data refresh" -and $_.level -eq "high"} | Select timestamp, area, category, eventid, level, correlation, message
```

```Output
Timestamp   : 4/14/2014 7:15:01 PM
Area        : PowerPivot Service
Category    : Data Refresh
EventID     : 43
Level       : High
Correlation : 5755879c-7cab-e097-8f80-f27895d44a77
Message     : The following error occurred when working with the service application, Default PowerPivot Service Application. Skipping the service application..

Timestamp   : 4/14/2014 7:15:02 PM
Area        : PowerPivot Service
Category    : Data Refresh
EventID     : 99
Level       : High
Correlation : 5755879c-7cab-e097-8f80-f27895d44a77
Message     : EXCEPTION: System.TimeoutException: The request channel timed out while waiting for a reply after 00:00:47.0625313. Increase the timeout value passed to 
              the call to Request or increase the SendTimeout value on the Binding. The time allotted to this operation may have been a portion of a longer timeout. 
              ---> System.TimeoutException: The HTTP request to 'http://localhost:32843/SecurityTokenServiceApplication/securitytoken.svc/actas' has exceeded the 
              allotted timeout of 00:00:54.5930000. The time allotted to this operation may have been a portion of a longer timeout. ---> System.Net.WebException: The 
              operation has timed out     at System.Net.HttpWebRequest.GetResponse()     at 
              System.ServiceModel.Channels.HttpChannelFactory`1.HttpRequestChannel.HttpChannelRequest.WaitForReply(TimeSpan timeout...
```

##  <a name="msolap-provider"></a><a name="bkmk_msolap"></a><span data-ttu-id="c20d2-212">Provider MSOLAP</span><span class="sxs-lookup"><span data-stu-id="c20d2-212">MSOLAP Provider</span></span>
 <span data-ttu-id="c20d2-213">Verificare che si tratti del provider MSOLAP.</span><span class="sxs-lookup"><span data-stu-id="c20d2-213">Verify the provider MSOLAP provider.</span></span> [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]<span data-ttu-id="c20d2-214">e [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)] [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] richiedono MSOLAP. 5.</span><span class="sxs-lookup"><span data-stu-id="c20d2-214">and [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)] [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] require MSOLAP.5.</span></span>

```powershell
$excelApp = Get-SPExcelServiceApplication
Get-SPExcelDataProvider -ExcelServiceApplication $excelApp | Select providerid, providertype, description | Where {$_.providerid -like "msolap*" } | Format-Table -Property * -AutoSize | Out-Default
```

```Output
ProviderId ProviderType Description
---------- ------------ -----------
MSOLAP     Oledb        Microsoft OLE DB Provider for OLAP Services     
MSOLAP.3   Oledb        Microsoft OLE DB Provider for OLAP Services 9.0 
MSOLAP.4   Oledb        Microsoft OLE DB Provider for OLAP Services 10.0
MSOLAP.5   Oledb        Microsoft OLE DB Provider for OLAP Services 11.0
```

 <span data-ttu-id="c20d2-215">Per altre informazioni, vedere [Installazione del provider OLE DB di Analysis Services nei server di SharePoint](../../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md) e [Aggiungere MSOLAP.5 come provider di dati attendibile in Excel Services](https://technet.microsoft.com/library/hh758436.aspx).</span><span class="sxs-lookup"><span data-stu-id="c20d2-215">For more information, see [Install the Analysis Services OLE DB Provider on SharePoint Servers](../../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md) and [Add MSOLAP.5 as a Trusted Data Provider in Excel Services](https://technet.microsoft.com/library/hh758436.aspx).</span></span>

##  <a name="adomdnet-client-library"></a><a name="bkmk_adomd"></a><span data-ttu-id="c20d2-216">Libreria client ADOMD.Net</span><span class="sxs-lookup"><span data-stu-id="c20d2-216">ADOMD.Net client Library</span></span>

```powershell
Get-WMIObject -Class win32_product | Where-Object {$_.name -Like "*ado*"} | Select name, version, vendor | Format-Table -Property * -AutoSize | out-default
```

```Output
name                                                  version      vendor
----                                                  -------      ------
Microsoft SQL Server 2008 Analysis Services ADOMD.NET 10.1.2531.0  Microsoft Corporation
Microsoft SQL Server 2005 Analysis Services ADOMD.NET 9.00.1399.06 Microsoft Corporation
```

 <span data-ttu-id="c20d2-217">Per altre informazioni, vedere [Installare ADOMD.NET in server front-end Web in cui viene eseguita Amministrazione centrale](../../../sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="c20d2-217">For more information, see [Install ADOMD.NET on Web Front-End Servers Running Central Administration](../../../sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md).</span></span>

##  <a name="health-data-collection-rules"></a><a name="bkmk_health_collection"></a><span data-ttu-id="c20d2-218">Regole di raccolta dati di integrità</span><span class="sxs-lookup"><span data-stu-id="c20d2-218">Health Data Collection Rules</span></span>
 <span data-ttu-id="c20d2-219">Verificare che lo **Stato** sia online e **Abilitato** sia True.</span><span class="sxs-lookup"><span data-stu-id="c20d2-219">Verify the **Status** is Online and **Enabled** is True.</span></span>

```powershell
Get-SPUsageDefinition | Select name, status, enabled, tablename, DaysToKeepDetailedData | Where {$_.name -Like "powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name                         Status Enabled TableName                   DaysToKeepDetailedData
----                         ------ ------- ---------                   ----------------------
PowerPivot Connections       OnlineTrue AnalysisServicesConnections  14
PowerPivot Load Data Usage   Online    True AnalysisServicesLoads                           14
PowerPivot Query Usage       Online    True AnalysisServicesRequests                        14
PowerPivot Unload Data Usage Online    True AnalysisServicesUnloads                         14
```

 <span data-ttu-id="c20d2-220">Per altre informazioni, vedere [PowerPivot Usage Data Collection](../../power-pivot-sharepoint/power-pivot-usage-data-collection.md).</span><span class="sxs-lookup"><span data-stu-id="c20d2-220">For more information, see [PowerPivot Usage Data Collection](../../power-pivot-sharepoint/power-pivot-usage-data-collection.md).</span></span>

##  <a name="solutions"></a><a name="bkmk_solutions"></a><span data-ttu-id="c20d2-221">Soluzioni</span><span class="sxs-lookup"><span data-stu-id="c20d2-221">Solutions</span></span>
 <span data-ttu-id="c20d2-222">Se gli altri componenti sono online, è possibile ignorare la verifica delle soluzioni.</span><span class="sxs-lookup"><span data-stu-id="c20d2-222">If the other components are online then you can skip verifying the solutions.</span></span> <span data-ttu-id="c20d2-223">Se tuttavia mancano le regole di integrità, verificare l'esistenza e la visualizzazione delle due soluzioni. Verificare che le due soluzioni PowerPivot siano **Online** e **Distribuita**.</span><span class="sxs-lookup"><span data-stu-id="c20d2-223">If however the Health rules are missing, verify the two solutions exist and showed Verify the two PowerPivot solutions are **Online** and **Deployed**.</span></span>

```powershell
Get-SPSolution | Select name, status, deployed, DeploymentState, DeployedServers | Where {$_.Name -Like "*powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default
```

<span data-ttu-id="c20d2-224">SharePoint 2013:</span><span class="sxs-lookup"><span data-stu-id="c20d2-224">SharePoint 2013:</span></span>

```Output
Name                                 Status Deployed        DeploymentState DeployedServers
----                                 ------ --------        --------------- ---------------
powerpivotfarm14solution.wsp         Online     True         GlobalDeployed {UETESTA00}
powerpivotfarmsolution.wsp           Online     True         GlobalDeployed {UETESTA00}
powerpivotwebapplicationsolution.wsp Online     True WebApplicationDeployed {UETESTA00}
```

<span data-ttu-id="c20d2-225">SharePoint 2010:</span><span class="sxs-lookup"><span data-stu-id="c20d2-225">SharePoint 2010:</span></span>

```Output
Name                 Status Deployed        DeploymentState DeployedServers 
----                 ------ --------        --------------- --------------- 
powerpivotfarm.wsp   Online     True         GlobalDeployed {uesql11spoint2}
powerpivotwebapp.wsp Online     True WebApplicationDeployed {uesql11spoint2}
```

 <span data-ttu-id="c20d2-226">Per altre informazioni sulla distribuzione delle soluzioni SharePoint, vedere [Distribuire pacchetti delle soluzioni (SharePoint Server 2010)](https://technet.microsoft.com/library/cc262995\(v=office.14\).aspx).</span><span class="sxs-lookup"><span data-stu-id="c20d2-226">For more information on how to deploy SharePoint solutions, see [Deploy solution packages (SharePoint Server 2010)](https://technet.microsoft.com/library/cc262995\(v=office.14\).aspx).</span></span>

##  <a name="manual-verification-steps"></a><a name="bkmk_manual"></a><span data-ttu-id="c20d2-227">Passaggi di verifica manuali</span><span class="sxs-lookup"><span data-stu-id="c20d2-227">Manual Verification Steps</span></span>
 <span data-ttu-id="c20d2-228">In questa sezione vengono descritti i passaggi di verifica che non possono essere completati con i cmdlet di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c20d2-228">This section describes verification steps that cannot be completed with PowerShell cmdlets.</span></span>

 <span data-ttu-id="c20d2-229">**Aggiornamento dati pianificato:** configurare la pianificazione dell'aggiornamento di una cartella di lavoro su **Aggiorna anche appena possibile**.</span><span class="sxs-lookup"><span data-stu-id="c20d2-229">**Scheduled Data Refresh:** Configure the refresh schedule a workbook to **Also refresh as soon as possible**.</span></span>  <span data-ttu-id="c20d2-230">Per ulteriori informazioni, vedere la sezione "verifica dell'aggiornamento dati" in [pianificare l'aggiornamento dei dati e le origini dati che non supportano l'autenticazione di Windows &#40;PowerPivot per SharePoint&#41;](../../power-pivot-sharepoint/schedule-data-refresh-and-data-sources-no-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="c20d2-230">For more information, see the "Verify Data Refresh" section of [Schedule Data Refresh and Data Sources That Do Not Support Windows Authentication &#40;PowerPivot for SharePoint&#41;](../../power-pivot-sharepoint/schedule-data-refresh-and-data-sources-no-windows-authentication.md).</span></span>

##  <a name="more-resources"></a><a name="bkmk_more_resources"></a><span data-ttu-id="c20d2-231">Altre risorse</span><span class="sxs-lookup"><span data-stu-id="c20d2-231">More Resources</span></span>
 <span data-ttu-id="c20d2-232">[Web Server (IIS) Administration Cmdlets in Windows PowerShell](https://technet.microsoft.com/library/ee790599.aspx)(Cmdlet di amministrazione di server Web IIS in Windows PowerShell).</span><span class="sxs-lookup"><span data-stu-id="c20d2-232">[Web Server (IIS) Administration Cmdlets in Windows PowerShell](https://technet.microsoft.com/library/ee790599.aspx).</span></span>

 <span data-ttu-id="c20d2-233">[PowerShell per controllare i servizi, i siti di IIS e il pool di applicazioni in SharePoint](https://gallery.technet.microsoft.com/office/PowerShell-to-check-a6ed72a0).</span><span class="sxs-lookup"><span data-stu-id="c20d2-233">[PowerShell to check services, IIS sites and Application Pool status in SharePoint](https://gallery.technet.microsoft.com/office/PowerShell-to-check-a6ed72a0).</span></span>

 <span data-ttu-id="c20d2-234">[Informazioni di riferimento su Windows PowerShell per SharePoint 2013](https://technet.microsoft.com/library/ee890108\(v=office.15\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c20d2-234">[Windows PowerShell for SharePoint 2013 reference](https://technet.microsoft.com/library/ee890108\(v=office.15\).aspx)</span></span>

 <span data-ttu-id="c20d2-235">[Informazioni di riferimento su Windows PowerShell per SharePoint Foundation 2010](https://technet.microsoft.com/library/ee890105\(v=office.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c20d2-235">[Windows PowerShell for SharePoint Foundation 2010 reference](https://technet.microsoft.com/library/ee890105\(v=office.14\).aspx)</span></span>

 <span data-ttu-id="c20d2-236">[Gestire Excel Services con Windows PowerShell (SharePoint Server 2010)](https://technet.microsoft.com/library/ff191201\(v=office.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c20d2-236">[Manage Excel Services with Windows PowerShell (SharePoint Server 2010)](https://technet.microsoft.com/library/ff191201\(v=office.14\).aspx)</span></span>

 [<span data-ttu-id="c20d2-237">Visualizzare e leggere i file di log del programma di installazione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="c20d2-237">View and Read SQL Server Setup Log Files</span></span>](../../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md)

 [<span data-ttu-id="c20d2-238">Utilizzare il cmdlet Get-EvenLog</span><span class="sxs-lookup"><span data-stu-id="c20d2-238">Use the Get-EvenLog cmdlet</span></span>](https://technet.microsoft.com/library/ee176846.aspx)

##  <a name="full-powershell-script"></a><a name="bkmk_full_script"></a><span data-ttu-id="c20d2-239">Script completo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="c20d2-239">Full PowerShell Script</span></span>
 <span data-ttu-id="c20d2-240">Nello script seguente sono contenuti tutti i comandi delle sezioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="c20d2-240">The Following script contains all of the commands from the previous sections.</span></span> <span data-ttu-id="c20d2-241">Tramite lo script vengono eseguiti i comandi nello stesso ordine di presentazione in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="c20d2-241">The script runs the commands in the same order as they are presented in this topic.</span></span> <span data-ttu-id="c20d2-242">Nello script sono contenute alcune variazioni facoltative dei comandi riportati in questo argomento nel caso sia necessario il filtro aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="c20d2-242">The script contains some optional variations of the commands noted in this topic in case you need additional filtering.</span></span> <span data-ttu-id="c20d2-243">Le variazioni sono disabilitate con un indicatore di commento (#).</span><span class="sxs-lookup"><span data-stu-id="c20d2-243">The variations are disabled with a comment character (#).</span></span> <span data-ttu-id="c20d2-244">Nello script sono inoltre incluse alcune istruzioni per verificare la modalità SharePoint di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c20d2-244">The script also includes some statements for verifying [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span> <span data-ttu-id="c20d2-245">Le istruzioni di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] sono disabilitate con un indicatore di commento (#).</span><span class="sxs-lookup"><span data-stu-id="c20d2-245">The [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] statements are disabled with a comment character (#).</span></span>

```powershell
# This script audits services related to PowerPivot for SharePoint
$starttime = Get-Date
write-host -foregroundcolor DarkGray StartTime $starttime

Write-Host  "Import the SharePoint PowerShell snappin"
Add-PSSnapin Microsoft.Sharepoint.Powershell -EA 0

Write-Host -ForegroundColor Green "Analysis Services Windows Service"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-Service | Select name, displayname, status | Where {$_.Name -eq "msolap`$powerpivot"} | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "PowerPivotEngineService and PowerPivotSystemService"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"

Get-PowerPivotSystemService | Select typename, status, applications, farm | Format-Table -property * -AutoSize | Out-Default
# If needed, you can run the following to compare job definitions specific to the service against the results of the timer job definition section
#Get-PowerPivotSystemService | select -ExpandProperty jobdefinitions | select displayname, schedule, service | format-table -property * -autosize | out-default

Get-PowerPivotEngineService | Select typename, status, name, instances, farm | Format-Table -property * -AutoSize | Out-Default
# If needed, you can run the following to compare job definitions specific to the service against the results of the timer job definition section
#Get-PowerPivotEngineService | select -ExpandProperty jobdefinitions | select displayname, schedule, service | format-table -property * -autosize | out-default

#Write-Host -ForegroundColor Green "Service Instances - optional if you want to associate services with the server"
#Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
#Get-SPServiceInstance | select typename, status, server, service, instance | where {$_.TypeName -like "*powerpivot*" -or $_.TypeName -like "*excel*" -or $_.TypeName -like "*Analysis Services*"} | format-table -property * -autosize | out-default
#Get-PowerPivotEngineServiceInstance  | select typename, ASServername, status, server, service, instance
#Get-PowerPivotSystemServiceInstance  | select typename, ASSServerName, status, server, service, instance

Write-Host -ForegroundColor Green "PowerPivot And Excel Service Applications"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-PowerPivotServiceApplication | Select typename,name, status, unattendedaccount, applicationpool, farm, database
Get-SPExcelServiceApplication | Select typename,  DisplayName, status

#Write-Host ""
Write-Host -ForegroundColor Green "PowerPivot Service Application pool"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
# the following assumes there is only 1 PowerPivot Service Application, and returns that application's pool name.  if you have more than one, use the 2nd version
$poolname = [string](Get-PowerPivotServiceApplication | Select -Property applicationpool)
$position = $poolname.lastindexof("=")
$poolname = $poolname.substring($position+1)
$poolname = $poolname.substring(0,$poolname.length-1)
Get-SPServiceApplicationPool | Select name, status, processaccountname, id | Where {$_.Name -eq $poolname} | Format-Table -Property * -AutoSize | Out-Default

#Write-Host ""
Write-Host -ForegroundColor Green "PowerPivot and Excel Service Application Proxy"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPServiceApplicationProxy |  Select typename, status, unattendedaccount, displayname | Where {$_.TypeName -like "*powerpivot*" -or $_.TypeName -like "*excel services*"} | Format-Table -Property * -AutoSize | Out-Default
#Get-SPServiceApplicationProxy |  select typename, status, unattendedaccount, displayname | where {$_.TypeName -like "*powerpivot*" -or $_.TypeName -like "*Reporting Services*" -or $_.TypeName -like "*excel services*"} | format-table -property * -autosize | out-default

Write-Host -ForegroundColor Green "DATABASES"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPDatabase | Select name, status, server, typename | Where {$_.TypeName -eq "content database" -or $_.TypeName -like "*Gemini*"} | Format-Table -Property * -AutoSize | Out-Default
#Get-SPDatabase | select name, status, server, typename | where {$_.TypeName -eq "content database" -or $_.TypeName -like "*Gemini*" -or $_.TypeName -like "*ReportingServices*"}

Write-Host -ForegroundColor Green "features"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPFeature | Select displayname, status, scope, farm | Where {$_.displayName -like "*powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default
#Get-SPFeature | select displayname, status, scope, farm | where {$_.displayName -like "*powerpivot*" -or $_.displayName -like "*ReportServer*"}  | format-table -property * -autosize | out-default

Write-Host -ForegroundColor Green "Timer Jobs (Job Definitions) -- list is the same as seen in the 'Review timer job definitions' section of the management dashboard"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPTimerJob | Where {$_.service -like "*power*" -or $_.service -like "*mid*"} | Select status, displayname, LastRunTime, service | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "health rules"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPHealthAnalysisRule | Select name, enabled, summary | Where {$_.summary -Like "*power*"}  | Format-Table -Property * -AutoSize | Out-Default

$time = Get-Date
Write-Host -ForegroundColor DarkGray StartTime $starttime
Write-Host -ForegroundColor DarkGray EndTime $time

Write-Host -ForegroundColor Green "Windows Event Log data MSSQL$POWERPIVOT and "
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-EventLog "application" | Where-Object {$_.source -like "msolap`$powerpivot*"}  | Select timegenerated, entrytype , source, message | Format-Table -Property * -autosize | Out-Default
#The following is the same command but with the Inforamtion events filtered out.
#Get-EventLog "application" | Where-Object {$_.source -like "msolap`$powerpivot*" -and ($_.entrytype -match "error" -or $_.entrytype -match "critical" -or $_.entrytype -match "warning")}  |select timegenerated, entrytype , source, message | format-table -property * -autosize | out-default

#Write-Host ""
Write-Host -ForegroundColor Green "ULS Log data"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPLogEvent -StartTime(Get-Date).AddHours(-48) | Where-Object {$_.Area -eq "powerpivot service" -and $_.level -eq "high"} | Select timestamp, area, category, eventid, level, correlation, message | Format-Table -Property * -AutoSize | Out-Default
#the following example filters for the category 'data refresh'
#Get-SPLogEvent -starttime(get-date).addhours(-48) | Where-Object {$_.category -eq "data refresh" -and $_.level -eq "high"} | select timestamp, area, category, eventid, level, correlation, message

$time = Get-Date
Write-Host -ForegroundColor DarkGray StartTime $starttime
Write-Host -ForegroundColor DarkGray EndTime $time

Write-Host -ForegroundColor Green "MSOLAP data provider for Excel Servivces, service application"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
$excelApp = Get-SPExcelServiceApplication
Get-SPExcelDataProvider -ExcelServiceApplication $excelApp | Select providerid, providertype, description | Where {$_.providerid -like "msolap*" } | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "ADOMD.net client library"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-WMIObject -Class win32_product | Where-Object {$_.name -like "*ado*"} | Select name, version, vendor | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "Usage Data Rules"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPUsageDefinition | Select name, status, enabled, tablename, DaysToKeepDetailedData | Where {$_.name -like "powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "Solutions"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPSolution | Select name, status, deployed, DeploymentState, DeployedServers | Where {$_.Name -like "*powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default

$time = Get-Date
Write-Host -ForegroundColor DarkGray StartTime $starttime
Write-Host -ForegroundColor DarkGray EndTime $time
```
