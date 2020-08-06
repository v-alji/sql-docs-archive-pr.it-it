---
title: Usare PowerShell per modificare ed elencare i proprietari delle sottoscrizioni Reporting Services ed eseguire una sottoscrizione | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0fa6cb36-68fc-4fb8-b1dc-ae4f12bf6ff0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b274dc190d8830a2cf7b55110f15267a00c581e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629172"
---
# <a name="use-powershell-to-change-and-list-reporting-services-subscription-owners-and-run-a-subscription"></a><span data-ttu-id="9deff-102">Usare PowerShell per modificare ed elencare i proprietari di sottoscrizioni di Reporting Services ed eseguire una sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="9deff-102">Use PowerShell to Change and List Reporting Services Subscription Owners and Run a Subscription</span></span>
  <span data-ttu-id="9deff-103">A partire da [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)][!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] è possibile trasferire a livello di programmazione la proprietà di una sottoscrizione [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] da un utente a un altro.</span><span class="sxs-lookup"><span data-stu-id="9deff-103">Starting with [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)][!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] you can programmatically transfer the ownership of a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] subscription from one user to another.</span></span> <span data-ttu-id="9deff-104">In questo argomento sono disponibili alcuni script di Windows PowerShell che possono essere usati per modificare o semplicemente elencare la proprietà delle sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="9deff-104">This topic provides several Windows PowerShell scripts you can use to change or simply list subscription ownership.</span></span> <span data-ttu-id="9deff-105">Ogni esempio include sintassi di esempio per la modalità nativa e la modalità SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9deff-105">Each sample includes sample syntax for both Native mode and SharePoint mode.</span></span> <span data-ttu-id="9deff-106">Dopo la modifica del proprietario, la sottoscrizione sarà eseguita nel contesto di protezione del nuovo proprietario e nel campo User!UserID nel report sarà visualizzato il valore relativo al nuovo proprietario.</span><span class="sxs-lookup"><span data-stu-id="9deff-106">After you change the subscription owner, the subscription will then execute in the security context of the new owner, and the User!UserID field in the report will display the value of new owner.</span></span> <span data-ttu-id="9deff-107">Per altre informazioni sul modello a oggetti chiamato dagli esempi di PowerShell, vedere <xref:ReportService2010.ReportingService2010.ChangeSubscriptionOwner%2A></span><span class="sxs-lookup"><span data-stu-id="9deff-107">For more information on the object model the PowerShell samples call, see <xref:ReportService2010.ReportingService2010.ChangeSubscriptionOwner%2A></span></span>

 <span data-ttu-id="9deff-108">![Contenuto correlato di PowerShell](../media/rs-powershellicon.jpg "Contenuto correlato di PowerShell")</span><span class="sxs-lookup"><span data-stu-id="9deff-108">![PowerShell related content](../media/rs-powershellicon.jpg "PowerShell related content")</span></span>

||
|-|
|<span data-ttu-id="9deff-109">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Modalità nativa &#124; [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] modalità SharePoint</span><span class="sxs-lookup"><span data-stu-id="9deff-109">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Native mode &#124; [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>|

 <span data-ttu-id="9deff-110">**Contenuto dell'argomento:**</span><span class="sxs-lookup"><span data-stu-id="9deff-110">**In this topic:**</span></span>

-   [<span data-ttu-id="9deff-111">Come usare gli script</span><span class="sxs-lookup"><span data-stu-id="9deff-111">How to use the scripts</span></span>](#bkmk_how_to)

-   [<span data-ttu-id="9deff-112">Script: elencare la proprietà di tutte le sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="9deff-112">Script: List the ownership of all subscriptions</span></span>](#bkmk_list_ownership_all)

-   [<span data-ttu-id="9deff-113">Script: elencare tutte le sottoscrizioni di proprietà di un utente specifico</span><span class="sxs-lookup"><span data-stu-id="9deff-113">Script: List all subscriptions owned by a specific user</span></span>](#bkmk_list_all_one_user)

-   [<span data-ttu-id="9deff-114">Script: modificare la proprietà per tutte le sottoscrizioni appartenenti a un utente specifico</span><span class="sxs-lookup"><span data-stu-id="9deff-114">Script: Change ownership for all subscriptions owned by a specific user</span></span>](#bkmk_change_all)

-   [<span data-ttu-id="9deff-115">Script: elencare tutte le sottoscrizioni associate a un report specifico</span><span class="sxs-lookup"><span data-stu-id="9deff-115">Script: List all subscriptions associated with a specific report</span></span>](#bkmk_list_for_1_report)

-   [<span data-ttu-id="9deff-116">Script: cambiare la proprietà di una sottoscrizione specifica</span><span class="sxs-lookup"><span data-stu-id="9deff-116">Script: Change ownership of a specific subscription</span></span>](#bkmk_change_all_1_subscription)

-   [<span data-ttu-id="9deff-117">Script: eseguire (attivare) una singola sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="9deff-117">Script: Run (fire) a single subscription</span></span>](#bkmk_run_1_subscription)

##  <a name="how-to-use-the-scripts"></a><a name="bkmk_how_to"></a> <span data-ttu-id="9deff-118">Come usare gli script</span><span class="sxs-lookup"><span data-stu-id="9deff-118">How to use the scripts</span></span>

### <a name="permissions"></a><span data-ttu-id="9deff-119">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="9deff-119">Permissions</span></span>
 <span data-ttu-id="9deff-120">In questa sezione sono riepilogati i livelli di autorizzazione necessari per usare ogni metodo della modalità nativa e della modalità SharePoint di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9deff-120">This section summarizes the permission levels required to use each of the methods for both Native and SharePoint mode [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="9deff-121">Gli script in questo argomento usano i metodi seguenti di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="9deff-121">The scripts in this topic use the following [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] methods:</span></span>

-   [<span data-ttu-id="9deff-122">Metodo ReportingService2010.ListSubscriptions</span><span class="sxs-lookup"><span data-stu-id="9deff-122">ReportingService2010.ListSubscriptions Method</span></span>](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.listsubscriptions.aspx)

-   [<span data-ttu-id="9deff-123">Metodo ReportingService2010.ChangeSubscriptionOwner</span><span class="sxs-lookup"><span data-stu-id="9deff-123">ReportingService2010.ChangeSubscriptionOwner Method</span></span>](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.changesubscriptionowner.aspx)

-   [<span data-ttu-id="9deff-124">ReportingService2010.ListChildren</span><span class="sxs-lookup"><span data-stu-id="9deff-124">ReportingService2010.ListChildren</span></span>](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.listchildren.aspx)

-   <span data-ttu-id="9deff-125">Il metodo [ReportingService2010.FireEvent](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.fireevent.aspx) è usato solo nell'ultimo script per attivare l'esecuzione di una sottoscrizione specifica.</span><span class="sxs-lookup"><span data-stu-id="9deff-125">The method [ReportingService2010.FireEvent](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.fireevent.aspx) is only used in the last script to trigger a specific subscription to run.</span></span> <span data-ttu-id="9deff-126">Se non si prevede di usare tale sottoscrizione, è possibile ignorare i requisiti relativi alle autorizzazioni per il metodo FireEvent.</span><span class="sxs-lookup"><span data-stu-id="9deff-126">If you do not plan to use that script you can ignore the permission requirements for the FireEvent method.</span></span>

 <span data-ttu-id="9deff-127">**Modalità nativa:**</span><span class="sxs-lookup"><span data-stu-id="9deff-127">**Native mode:**</span></span>

-   <span data-ttu-id="9deff-128">Elencare le sottoscrizioni: (HYPERLINK " https://technet.microsoft.com/library/microsoft.reportingservices.interfaces.reportoperation.aspx " ReadSubscription nel report e l'utente è il proprietario della sottoscrizione) o ReadAnySubscription</span><span class="sxs-lookup"><span data-stu-id="9deff-128">List Subscriptions: ( HYPERLINK "https://technet.microsoft.com/library/microsoft.reportingservices.interfaces.reportoperation.aspx" ReadSubscription on the report AND the user is the subscription owner) OR ReadAnySubscription</span></span>

-   <span data-ttu-id="9deff-129">Modifica sottoscrizioni: l'utente deve essere membro del gruppo BUILTIN\Administrators</span><span class="sxs-lookup"><span data-stu-id="9deff-129">Change Subscriptions: The user must be a member of the BUILTIN\Administrators group</span></span>

-   <span data-ttu-id="9deff-130">Elenco figli: ReadProperties su Item</span><span class="sxs-lookup"><span data-stu-id="9deff-130">List Children: ReadProperties on Item</span></span>

-   <span data-ttu-id="9deff-131">Evento di attivazione: GenerateEvents (System)</span><span class="sxs-lookup"><span data-stu-id="9deff-131">Fire Event: GenerateEvents (System)</span></span>

 <span data-ttu-id="9deff-132">**Modalità SharePoint:**</span><span class="sxs-lookup"><span data-stu-id="9deff-132">**SharePoint mode:**</span></span>

-   <span data-ttu-id="9deff-133">Elencare le sottoscrizioni: ManageAlerts o (HYPERLINK " https://technet.microsoft.com/library/microsoft.sharepoint.spbasepermissions.aspx " CreateAlerts nel report e l'utente è il proprietario della sottoscrizione e la sottoscrizione è una sottoscrizione temporizzata).</span><span class="sxs-lookup"><span data-stu-id="9deff-133">List Subscriptions: ManageAlerts OR ( HYPERLINK "https://technet.microsoft.com/library/microsoft.sharepoint.spbasepermissions.aspx" CreateAlerts on the report AND the user is the subscription owner and the subscription is a timed subscription).</span></span>

-   <span data-ttu-id="9deff-134">Modifica sottoscrizioni: ManageWeb</span><span class="sxs-lookup"><span data-stu-id="9deff-134">Change Subscriptions: ManageWeb</span></span>

-   <span data-ttu-id="9deff-135">Elenco figli: ViewListItems</span><span class="sxs-lookup"><span data-stu-id="9deff-135">List Children: ViewListItems</span></span>

-   <span data-ttu-id="9deff-136">Evento di attivazione: ManageWeb</span><span class="sxs-lookup"><span data-stu-id="9deff-136">Fire Event: ManageWeb</span></span>

 <span data-ttu-id="9deff-137">Per altre informazioni, vedere [Confrontare ruoli e attività di Reporting Services con autorizzazioni e gruppi di SharePoint](../reporting-services-roles-tasks-vs-sharepoint-groups-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9deff-137">For more information, see [Compare Roles and Tasks in Reporting Services to SharePoint Groups and Permissions](../reporting-services-roles-tasks-vs-sharepoint-groups-permissions.md).</span></span>

### <a name="script-usage"></a><span data-ttu-id="9deff-138">Uso degli script</span><span class="sxs-lookup"><span data-stu-id="9deff-138">Script usage</span></span>
 <span data-ttu-id="9deff-139">**Creare file script (con estensione ps1)**</span><span class="sxs-lookup"><span data-stu-id="9deff-139">**Create Script files (.ps1)**</span></span>

1.  <span data-ttu-id="9deff-140">Creare una cartella con nome **c:\scripts**.</span><span class="sxs-lookup"><span data-stu-id="9deff-140">Create a folder named **c:\scripts**.</span></span> <span data-ttu-id="9deff-141">Se si sceglie una cartella diversa, modificare il nome della cartella usato nelle istruzioni di esempio della sintassi da riga di comando.</span><span class="sxs-lookup"><span data-stu-id="9deff-141">If you choose a different folder then modify the folder name used in the example command line syntax statements.</span></span>

2.  <span data-ttu-id="9deff-142">Creare un file di testo per ogni script e salvare i file nella cartella c:\scripts.</span><span class="sxs-lookup"><span data-stu-id="9deff-142">Create a text file for each script and save the files to the c:\scripts folder.</span></span> <span data-ttu-id="9deff-143">Quando si creano i file con estensione ps1, usare il nome di ogni esempio di sintassi da riga di comando.</span><span class="sxs-lookup"><span data-stu-id="9deff-143">When you create the .ps1 files, use the name from each example command line syntax.</span></span>

3.  <span data-ttu-id="9deff-144">Aprire un prompt dei comandi con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="9deff-144">Open a command prompt with administrative privileges.</span></span>

4.  <span data-ttu-id="9deff-145">Eseguire ogni file script, usando l'esempio di sintassi da riga di comando disponibile in ogni esempio.</span><span class="sxs-lookup"><span data-stu-id="9deff-145">Run each script file, using the sample command line syntax provided with each example.</span></span>

 <span data-ttu-id="9deff-146">**Ambienti testati**</span><span class="sxs-lookup"><span data-stu-id="9deff-146">**Tested environments**</span></span>

 <span data-ttu-id="9deff-147">Gli script in questo argomento sono stati testati in PowerShell versione 3 e con le versioni seguenti di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="9deff-147">The scripts in this topic were tested on PowerShell version 3 and with the following versions of [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]:</span></span>

-   [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]

-   [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]

-   [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)]

##  <a name="script-list-the-ownership-of-all-subscriptions"></a><a name="bkmk_list_ownership_all"></a> <span data-ttu-id="9deff-148">Script: elencare la proprietà di tutte le sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="9deff-148">Script: List the ownership of all subscriptions</span></span>
 <span data-ttu-id="9deff-149">Questo script permette di elencare tutte le sottoscrizioni in un sito.</span><span class="sxs-lookup"><span data-stu-id="9deff-149">This script lists all of the subscriptions on a site.</span></span> <span data-ttu-id="9deff-150">È possibile usare questo script per testare la connessione o verificare il percorso del report e l'ID di sottoscrizione da usare in altri script.</span><span class="sxs-lookup"><span data-stu-id="9deff-150">You can use this script to test your connection or to verify the report path and subscription id for use in the other scripts.</span></span> <span data-ttu-id="9deff-151">Questo script è utile anche per la semplice verifica delle sottoscrizioni esistenti e dei relativi proprietari.</span><span class="sxs-lookup"><span data-stu-id="9deff-151">This is also a useful script to simply audit what subscriptions exist and who owns them.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="9deff-152">Sintassi in modalità nativa</span><span class="sxs-lookup"><span data-stu-id="9deff-152">Native mode syntax</span></span>

```cmd
powershell c:\scripts\ListAll_SSRS_Subscriptions.ps1 "[server]/reportserver" "/"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="9deff-153">Sintassi della modalità SharePoint</span><span class="sxs-lookup"><span data-stu-id="9deff-153">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\ListAll_SSRS_Subscriptions.ps1 "[server]/_vti_bin/reportserver" "http://[server]"
```

### <a name="script"></a><span data-ttu-id="9deff-154">Script</span><span class="sxs-lookup"><span data-stu-id="9deff-154">Script</span></span>

```powershell
# Parameters
#    server   - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)

Param(
    [string]$server,
    [string]$site
   )

$rs2010 += New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
$subscriptions += $rs2010.ListSubscriptions($site); # use "/" for default native mode site

Write-Host " "
Write-Host "----- $server's Subscriptions: "
$subscriptions | select Path, report, Description, Owner, SubscriptionID, lastexecuted, Status
```

> [!TIP]
>  <span data-ttu-id="9deff-155">Per verificare gli URL del sito in modalità SharePoint, usare il cmdlet **Get-SPSite**di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9deff-155">To verify site URLS in SharePoint mode, use the SharePoint cmdlet **Get-SPSite**.</span></span> <span data-ttu-id="9deff-156">Per altre informazioni, vedere [Get-SPSite](https://technet.microsoft.com/library/ff607950\(v=office.15\).aspx).</span><span class="sxs-lookup"><span data-stu-id="9deff-156">For more information, see [Get-SPSite](https://technet.microsoft.com/library/ff607950\(v=office.15\).aspx).</span></span>

##  <a name="script-list-all-subscriptions-owned-by-a-specific-user"></a><a name="bkmk_list_all_one_user"></a> <span data-ttu-id="9deff-157">Script: elencare tutte le sottoscrizioni di proprietà di un utente specifico</span><span class="sxs-lookup"><span data-stu-id="9deff-157">Script: List all subscriptions owned by a specific user</span></span>
 <span data-ttu-id="9deff-158">Questo script permette di elencare tutte le sottoscrizioni di proprietà di un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="9deff-158">This script lists all of the subscriptions owned by a specific user.</span></span> <span data-ttu-id="9deff-159">È possibile usare questo script per testare la connessione o verificare il percorso del report e l'ID di sottoscrizione da usare in altri script.</span><span class="sxs-lookup"><span data-stu-id="9deff-159">You can use this script to test your connection or to verify the report path and subscription id for use in the other scripts.</span></span> <span data-ttu-id="9deff-160">Questo script è utile se un utente abbandona l'organizzazione e si vuole verificare le sottoscrizioni appartenenti a tale utente, in modo da potere modificare il proprietario o eliminare la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="9deff-160">This script is useful when someone in your organization leaves and you want to verify what subscriptions they owned so you can change the owner or delete the subscription.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="9deff-161">Sintassi in modalità nativa</span><span class="sxs-lookup"><span data-stu-id="9deff-161">Native mode syntax</span></span>

```cmd
powershell c:\scripts\ListAll_SSRS_Subscriptions4User.ps1 "[Domain]\[user]" "[server]/reportserver" "/"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="9deff-162">Sintassi della modalità SharePoint</span><span class="sxs-lookup"><span data-stu-id="9deff-162">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\ListAll_SSRS_Subscriptions4User.ps1 "[Domain]\[user]"  "[server]/_vti_bin/reportserver" "http://[server]"
```

### <a name="script"></a><span data-ttu-id="9deff-163">Script</span><span class="sxs-lookup"><span data-stu-id="9deff-163">Script</span></span>

```powershell
# Parameters:
#    currentOwner - DOMAIN\USER that owns the subscriptions you wish to change
#    server        - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)
#    site        - use "/" for default native mode site
Param(
    [string]$currentOwner,
    [string]$server,
    [string]$site
)

$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
$subscriptions += $rs2010.ListSubscriptions($site);

Write-Host " "
Write-Host " "
Write-Host "----- $currentOwner's Subscriptions: "
$subscriptions | select Path, report, Description, Owner, SubscriptionID, lastexecuted,Status | where {$_.owner -eq $currentOwner}
```

##  <a name="script-change-ownership-for-all-subscriptions-owned-by-a-specific-user"></a><a name="bkmk_change_all"></a> <span data-ttu-id="9deff-164">Script: modificare la proprietà per tutte le sottoscrizioni appartenenti a un utente specifico</span><span class="sxs-lookup"><span data-stu-id="9deff-164">Script: Change ownership for all subscriptions owned by a specific user</span></span>
 <span data-ttu-id="9deff-165">Questo script permette di cambiare la proprietà per tutte le sottoscrizioni appartenenti a un utente specifico, impostando il parametro relativo al nuovo proprietario.</span><span class="sxs-lookup"><span data-stu-id="9deff-165">This script changes the ownership for all subscriptions owned by a specific user to the new owner parameter.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="9deff-166">Sintassi in modalità nativa</span><span class="sxs-lookup"><span data-stu-id="9deff-166">Native mode syntax</span></span>

```cmd
powershell c:\scripts\ChangeALL_SSRS_SubscriptionOwner.ps1 "[Domain]\current owner]" "[Domain]\[new owner]" "[server]/reportserver"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="9deff-167">Sintassi della modalità SharePoint</span><span class="sxs-lookup"><span data-stu-id="9deff-167">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\ChangeALL_SSRS_SubscriptionOwner.ps1 "[Domain]\{current owner]" "[Domain]\[new owner]" "[server]/_vti_bin/reportserver"
```

### <a name="script"></a><span data-ttu-id="9deff-168">Script</span><span class="sxs-lookup"><span data-stu-id="9deff-168">Script</span></span>

```powershell
# Parameters:
#    currentOwner - DOMAIN\USER that owns the subscriptions you wish to change
#    newOwner      - DOMAIN\USER that will own the subscriptions you wish to change
#    server        - server and instance name (e.g. myserver/reportserver, myserver/reportserver_db2, myserver/_vti_bin/reportserver)

Param(
    [string]$currentOwner,
    [string]$newOwner,
    [string]$server
)

$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
$items = $rs2010.ListChildren("/", $true);

$subscriptions = @();

ForEach ($item in $items)
{
    if ($item.TypeName -eq "Report")
    {
        $curRepSubs = $rs2010.ListSubscriptions($item.Path);
        ForEach ($curRepSub in $curRepSubs)
        {
            if ($curRepSub.Owner -eq $currentOwner)
            {
                $subscriptions += $curRepSub;
            }
        }
    }
}

Write-Host " "
Write-Host " "
Write-Host -foregroundcolor "green" "-----  $currentOwner's Subscriptions changing ownership to $newOwner : "
$subscriptions | select SubscriptionID, Owner, Path, Description,  Status  | format-table -AutoSize

ForEach ($sub in $subscriptions)
{
    $rs2010.ChangeSubscriptionOwner($sub.SubscriptionID, $newOwner);
}

$subs2 = @();

ForEach ($item in $items)
{
    if ($item.TypeName -eq "Report")
    {
        $subs2 += $rs2010.ListSubscriptions($item.Path);
    }
}
```

##  <a name="script-list-all-subscriptions-associated-with-a-specific-report"></a><a name="bkmk_list_for_1_report"></a> <span data-ttu-id="9deff-169">Script: elencare tutte le sottoscrizioni associate a un report specifico</span><span class="sxs-lookup"><span data-stu-id="9deff-169">Script: List all subscriptions associated with a specific report</span></span>
 <span data-ttu-id="9deff-170">Questo script permette di elencare tutte le sottoscrizioni associate a un report specifico.</span><span class="sxs-lookup"><span data-stu-id="9deff-170">This script lists all of the subscriptions associated with a specific report.</span></span> <span data-ttu-id="9deff-171">La sintassi del percorso del report è diversa in modalità SharePoint, che necessita di un URL completo.</span><span class="sxs-lookup"><span data-stu-id="9deff-171">The report path syntax is different SharePoint mode which requires a full URL.</span></span> <span data-ttu-id="9deff-172">Nell'esempio di sintassi il nome usato per il report è "title only", che include uno spazio e quindi deve essere racchiuso da virgolette semplici.</span><span class="sxs-lookup"><span data-stu-id="9deff-172">In the syntax examples, the report name used is "title only", which contains a space and therefore requires the single quotes around the report name.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="9deff-173">Sintassi in modalità nativa</span><span class="sxs-lookup"><span data-stu-id="9deff-173">Native mode syntax</span></span>

```cmd
powershell c:\scripts\List_SSRS_One_Reports_Subscriptions.ps1 "[server]/reportserver" "'/reports/title only'" "/"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="9deff-174">Sintassi della modalità SharePoint</span><span class="sxs-lookup"><span data-stu-id="9deff-174">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\List_SSRS_One_Reports_Subscriptions.ps1 "[server]/_vti_bin/reportserver"  "'http://[server]/shared documents/title only.rdl'" "http://[server]"
```

### <a name="script"></a><span data-ttu-id="9deff-175">Script</span><span class="sxs-lookup"><span data-stu-id="9deff-175">Script</span></span>

```powershell
# Parameters:
#    server      - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)
#    reportpath  - path to report in the report server, including report name e.g. /reports/test report >> pass in  "'/reports/title only'"
#    site        - use "/" for default native mode site
Param
(
      [string]$server,
      [string]$reportpath,
      [string]$site
)

$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
$subscriptions += $rs2010.ListSubscriptions($site);

Write-Host " "
Write-Host " "
Write-Host "----- $reportpath 's Subscriptions: "
$subscriptions | select Path, report, Description, Owner, SubscriptionID, lastexecuted,Status | where {$_.path -eq $reportpath}
```

##  <a name="script-change-ownership-of-a-specific-subscription"></a><a name="bkmk_change_all_1_subscription"></a> <span data-ttu-id="9deff-176">Script: cambiare la proprietà di una sottoscrizione specifica</span><span class="sxs-lookup"><span data-stu-id="9deff-176">Script: Change ownership of a specific subscription</span></span>
 <span data-ttu-id="9deff-177">Questo script permette di cambiare la proprietà di una sottoscrizione specifica.</span><span class="sxs-lookup"><span data-stu-id="9deff-177">This script changes the ownership for a specific subscription.</span></span> <span data-ttu-id="9deff-178">La sottoscrizione è identificata dal valore SubscriptionID passato nello script.</span><span class="sxs-lookup"><span data-stu-id="9deff-178">The subscription is identified by the SubscriptionID that you pass into the script.</span></span> <span data-ttu-id="9deff-179">È possibile usare uno degli script per elencare le sottoscrizioni per determinare il valore SubscriptionID corretto.</span><span class="sxs-lookup"><span data-stu-id="9deff-179">You can use one of the list subscription scripts to determine the correct SubscriptionID.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="9deff-180">Sintassi in modalità nativa</span><span class="sxs-lookup"><span data-stu-id="9deff-180">Native mode syntax</span></span>

```cmd
powershell c:\scripts\Change_SSRS_Owner_One_Subscription.ps1 "[Domain]\[new owner]" "[server]/reportserver" "/" "ac5637a1-9982-4d89-9d69-a72a9c3b3150"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="9deff-181">Sintassi della modalità SharePoint</span><span class="sxs-lookup"><span data-stu-id="9deff-181">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\Change_SSRS_Owner_One_Subscription.ps1 "[Domain]\[new owner]" "[server]/_vti_bin/reportserver" "http://[server]" "9660674b-f020-453f-b1e3-d9ba37624519"
```

### <a name="script"></a><span data-ttu-id="9deff-182">Script</span><span class="sxs-lookup"><span data-stu-id="9deff-182">Script</span></span>

```powershell
# Parameters:
#    newOwner       - DOMAIN\USER that will own the subscriptions you wish to change
#    server         - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)
#    site        - use "/" for default native mode site
#    subscriptionID - guid for the single subscription to change

Param(
    [string]$newOwner,
    [string]$server,
    [string]$site,
    [string]$subscriptionid
   )
$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential;

$subscription += $rs2010.ListSubscriptions($site) | where {$_.SubscriptionID -eq $subscriptionid};

Write-Host " "
Write-Host "----- $subscriptionid's Subscription properties: "
$subscription | select Path, report, Description, SubscriptionID, Owner, Status

$rs2010.ChangeSubscriptionOwner($subscription.SubscriptionID, $newOwner)

#refresh the list
$subscription = $rs2010.ListSubscriptions($site) | where {$_.SubscriptionID -eq $subscriptionid}; # use "/" for default native mode site
Write-Host "----- $subscriptionid's Subscription properties: "
$subscription | select Path, report, Description, SubscriptionID, Owner, Status
```

##  <a name="script-run-fire-a-single-subscription"></a><a name="bkmk_run_1_subscription"></a> <span data-ttu-id="9deff-183">Script: eseguire (attivare) una singola sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="9deff-183">Script: Run (fire) a single subscription</span></span>
 <span data-ttu-id="9deff-184">Questo script eseguirà una sottoscrizione specifica usando il metodo FireEvent.</span><span class="sxs-lookup"><span data-stu-id="9deff-184">This script will run a specific subscription using the FireEvent method.</span></span> <span data-ttu-id="9deff-185">Lo script eseguirà immediatamente la sottoscrizione, indipendentemente dalla pianificazione configurata per la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="9deff-185">The script will immediately run the subscription regardless of the schedule configured for the subscription.</span></span> <span data-ttu-id="9deff-186">EventType è verificato rispetto al set noto degli eventi definiti nel file di configurazione del server di report **rsreportserver.config** . Lo script usa il tipo di evento seguente per le sottoscrizioni standard:</span><span class="sxs-lookup"><span data-stu-id="9deff-186">The EventType is matched against the known set of events that are defined in the report server configuration file **rsreportserver.config** The script uses the following event type for standard subscriptions:</span></span>

 `<Event>`

 `<Type>TimedSubscription</Type>`

 `</Event>`

 <span data-ttu-id="9deff-187">Per altre informazioni sul file di configurazione, vedere [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="9deff-187">For more information on the configuration file, see [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span></span>

 <span data-ttu-id="9deff-188">Lo script include logica di ritardo di tipo "`Start-Sleep -s 6`". Dopo l'attivazione dell'evento è quindi disponibile tempo per rendere disponibile lo stato aggiornato con il metodo ListSubscription.</span><span class="sxs-lookup"><span data-stu-id="9deff-188">The script includes delay logic "`Start-Sleep -s 6`" so there is time after the event fires, for the updated status to be available with the ListSubscription method.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="9deff-189">Sintassi in modalità nativa</span><span class="sxs-lookup"><span data-stu-id="9deff-189">Native mode syntax</span></span>

```cmd
powershell c:\scripts\FireSubscription.ps1 "[server]/reportserver" $null "70366e82-2d3c-4edd-a216-b97e51e26de9"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="9deff-190">Sintassi della modalità SharePoint</span><span class="sxs-lookup"><span data-stu-id="9deff-190">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\FireSubscription.ps1 "[server]/_vti_bin/reportserver" "http://[server]" "c3425c72-580d-423e-805a-41cf9799fd25"
```

### <a name="script"></a><span data-ttu-id="9deff-191">Script</span><span class="sxs-lookup"><span data-stu-id="9deff-191">Script</span></span>

```powershell
# Parameters
#    server         - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)
#    site           - use $null for a native mode server
#    subscriptionid - subscription guid

Param(
  [string]$server,
  [string]$site,
  [string]$subscriptionid
  )

$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
#event type is case sensative to what is in the rsreportserver.config
$rs2010.FireEvent("TimedSubscription",$subscriptionid,$site)

Write-Host " "
Write-Host "----- Subscription ($subscriptionid) status: "
#get list of subscriptions and filter to the specific ID to see the Status and LastExecuted
Start-Sleep -s 6 # slight delay in processing so ListSubscription returns the updated Status and LastExecuted
$subscriptions = $rs2010.ListSubscriptions($site); 
$subscriptions | select Status, Path, report, Description, Owner, SubscriptionID, EventType, lastexecuted | where {$_.SubscriptionID -eq $subscriptionid}
```

## <a name="see-also"></a><span data-ttu-id="9deff-192">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9deff-192">See Also</span></span>
 <span data-ttu-id="9deff-193"><xref:ReportService2010.ReportingService2010.ListSubscriptions%2A> <xref:ReportService2010.ReportingService2010.ChangeSubscriptionOwner%2A></span><span class="sxs-lookup"><span data-stu-id="9deff-193"><xref:ReportService2010.ReportingService2010.ListSubscriptions%2A> <xref:ReportService2010.ReportingService2010.ChangeSubscriptionOwner%2A></span></span> 
 <xref:ReportService2010.ReportingService2010.ListChildren%2A> 
 <xref:ReportService2010.ReportingService2010.FireEvent%2A>
