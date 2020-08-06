---
title: Installare PowerPivot dal prompt dei comandi | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 7f1f2b28-c9f5-49ad-934b-02f2fa6b9328
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 54f30142cdc2e39b3ec565d4f965fdad675405e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637036"
---
# <a name="install-powerpivot-from-the-command-prompt"></a><span data-ttu-id="ff736-102">Installazione di PowerPivot dal prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="ff736-102">Install PowerPivot from the Command Prompt</span></span>
  <span data-ttu-id="ff736-103">È possibile eseguire il programma di installazione dalla riga di comando per installare SQL Server PowerPivot per SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ff736-103">You can run Setup from the command line to install SQL Server PowerPivot for SharePoint.</span></span> <span data-ttu-id="ff736-104">È necessario includere il parametro `/ROLE` nel comando ed escludere il parametro `/FEATURES`.</span><span class="sxs-lookup"><span data-stu-id="ff736-104">You must include the `/ROLE` parameter in your command and exclude the `/FEATURES` parameter.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ff736-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ff736-105">Prerequisites</span></span>  
 <span data-ttu-id="ff736-106">SharePoint Server 2010 Enterprise Edition con Service Pack 1 (SP1) deve essere installato.</span><span class="sxs-lookup"><span data-stu-id="ff736-106">SharePoint Server 2010 enterprise edition with Service Pack 1 (SP1) must be installed.</span></span>  
  
 <span data-ttu-id="ff736-107">È necessario utilizzare account di dominio per eseguire il provisioning di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="ff736-107">You must use domain accounts to provision Analysis Services.</span></span>  
  
 <span data-ttu-id="ff736-108">Il computer deve essere unito in join allo stesso dominio della farm di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ff736-108">The computer must be joined to the same domain as the SharePoint farm.</span></span>  
  
##  <a name="role-based-installation-options"></a><a name="Commands"></a><span data-ttu-id="ff736-109">Opzioni di installazione basate su/ROLE</span><span class="sxs-lookup"><span data-stu-id="ff736-109">/ROLE based installation options</span></span>  
 <span data-ttu-id="ff736-110">Per le distribuzioni PowerPivot per SharePoint, viene utilizzato il parametro `/ROLE` anziché `/FEATURES`.</span><span class="sxs-lookup"><span data-stu-id="ff736-110">For PowerPivot for SharePoint deployments, the `/ROLE` parameter is used in place of the `/FEATURES` parameter.</span></span> <span data-ttu-id="ff736-111">I valori validi includono:</span><span class="sxs-lookup"><span data-stu-id="ff736-111">Valid values include:</span></span>  
  
-   `SPI_AS_ExistingFarm`  
  
-   `SPI_AS_NewFarm`  
  
 <span data-ttu-id="ff736-112">Con entrambi i ruoli è possibile installare i file di distribuzione, configurazione e applicazione che consentono l'esecuzione di PowerPivot per SharePoint in una farm di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ff736-112">Both roles install application, configuration, and deployment files that enable a PowerPivot for SharePoint to run in a SharePoint farm.</span></span> <span data-ttu-id="ff736-113">Se si specifica uno dei due ruoli, vengono verificati i requisiti hardware e software necessari per l'integrazione con SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ff736-113">Specifying either role will cause Setup to check for hardware and software requirements necessary for SharePoint integration.</span></span>  
  
 <span data-ttu-id="ff736-114">Con l'opzione Farm esistente si suppone l'esistenza di una farm di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ff736-114">The existing farm option assumes that a SharePoint farm is already in place.</span></span> <span data-ttu-id="ff736-115">La nuova opzione Farm presuppone che venga creata una nuova farm. supporta l'aggiunta di un'istanza di motore di database nella sintassi della riga di comando, in modo che sia possibile utilizzare l'istanza di motore di database come server di database della farm.</span><span class="sxs-lookup"><span data-stu-id="ff736-115">The new farm option assumes that you will create a new farm; it supports the addition of a Database Engine instance in the command line syntax so that you can use the Database Engine instance as the farm's database server.</span></span>  
  
 <span data-ttu-id="ff736-116">A differenza delle versioni precedenti, tutte le attività di configurazione del server vengono eseguite successivamente all'installazione.</span><span class="sxs-lookup"><span data-stu-id="ff736-116">In contrast with the previous releases, all server configuration tasks are performed as post-installation tasks.</span></span> <span data-ttu-id="ff736-117">In caso di automazione delle procedure di installazione e configurazione, è possibile utilizzare PowerShell per configurare il server.</span><span class="sxs-lookup"><span data-stu-id="ff736-117">If you are automating installation and configuration steps, you can use PowerShell to configure the server.</span></span> <span data-ttu-id="ff736-118">Per ulteriori informazioni, vedere [configurazione di PowerPivot mediante Windows PowerShell](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-configuration-using-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="ff736-118">For more information, see [PowerPivot Configuration using Windows PowerShell](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-configuration-using-windows-powershell).</span></span>  
  
## <a name="example-commands"></a><span data-ttu-id="ff736-119">Comando di esempio</span><span class="sxs-lookup"><span data-stu-id="ff736-119">Example Commands</span></span>  
 <span data-ttu-id="ff736-120">Negli esempi seguenti viene illustrato l'utilizzo di ogni opzione.</span><span class="sxs-lookup"><span data-stu-id="ff736-120">The following examples illustrate the usage of each option.</span></span> <span data-ttu-id="ff736-121">Nell'esempio 1 viene illustrato `SPI_AS_ExistingFarm` .</span><span class="sxs-lookup"><span data-stu-id="ff736-121">Example 1 shows `SPI_AS_ExistingFarm`.</span></span>  
  
```cmd
Setup.exe /q /IAcceptSQLServerLicenseTerms /ACTION=install /ROLE=SPI_AS_ExistingFarm /INSTANCENAME=PowerPivot /INDICATEPROGRESS/ASSVCACCOUNT=<DomainName\UserName> /ASSVCPASSWORD=<StrongPassword> /ASSYSADMINACCOUNTS=<DomainName\UserName>   
```  
  
 <span data-ttu-id="ff736-122">Nell'esempio 2 viene illustrata l'opzione `SPI_AS_NewFarm`.</span><span class="sxs-lookup"><span data-stu-id="ff736-122">Example 2 shows `SPI_AS_NewFarm`.</span></span> <span data-ttu-id="ff736-123">Si noti che sono inclusi i parametri per eseguire il provisioning del Motore di database.</span><span class="sxs-lookup"><span data-stu-id="ff736-123">Notice that it includes parameters for provisioning the Database Engine.</span></span>  
  
```cmd
Setup.exe /q /IAcceptSQLServerLicenseTerms /ACTION=install /ROLE=SPI_AS_NewFarm /INSTANCENAME=PowerPivot /INDICATEPROGRESS/SQLSVCACCOUNT=<DomainName\UserName> /SQLSVCPASSWORD=<StrongPassword> /SQLSYSADMINACCOUNTS=<DomainName\UserName> /AGTSVCACCOUNT=<DomainName\UserName> /AGTSVCPASSWORD=<StrongPassword> /ASSVCACCOUNT=<DomainName\UserName> /ASSVCPASSWORD=<StrongPassword> /ASSYSADMINACCOUNTS=<DomainName\UserName>   
```  
  
##  <a name="modifying-the-command-syntax"></a><a name="Join"></a><span data-ttu-id="ff736-124">Modifica della sintassi del comando</span><span class="sxs-lookup"><span data-stu-id="ff736-124">Modifying the command syntax</span></span>  
 <span data-ttu-id="ff736-125">Utilizzare i passaggi seguenti per modificare la sintassi del comando di esempio.</span><span class="sxs-lookup"><span data-stu-id="ff736-125">Use the following steps to modify the example command syntax.</span></span>  
  
1.  <span data-ttu-id="ff736-126">Copiare il comando seguente in Blocco note:</span><span class="sxs-lookup"><span data-stu-id="ff736-126">Copy the following command into Notepad:</span></span>  
  
    ```cmd
    Setup.exe /q /IAcceptSQLServerLicenseTerms /ACTION=install /ROLE=SPI_AS_ExistingFarm /INSTANCENAME=PowerPivot /INDICATEPROGRESS/ASSVCACCOUNT=<DomainName\UserName> /ASSVCPASSWORD=<StrongPassword> /ASSYSADMINACCOUNTS=<DomainName\UserName>   
    ```  
  
     <span data-ttu-id="ff736-127">Il parametro `/q` consente di eseguire il programma di installazione in modalità non interattiva senza l'ausilio dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="ff736-127">The `/q` parameter runs Setup in quiet mode, which suppresses the user interface.</span></span>  
  
     <span data-ttu-id="ff736-128">È necessario specificare `/IAcceptSQLServerLicenseTerms` quando si specifica il parametro `/q` o `/qs` per le installazioni automatiche.</span><span class="sxs-lookup"><span data-stu-id="ff736-128">The `/IAcceptSQLServerLicenseTerms` is required when the `/q` or `/qs` parameter is specified for un-attended installations.</span></span>  
  
     <span data-ttu-id="ff736-129">Il parametro `/action` indica al programma di installazione di eseguire un'installazione.</span><span class="sxs-lookup"><span data-stu-id="ff736-129">The `/action` parameter instructs Setup to perform an installation.</span></span>  
  
     <span data-ttu-id="ff736-130">Il parametro `/role` indica al programma di installazione di installare il programma Analysis Services e i file di configurazione necessari per PowerPivot per SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ff736-130">The `/role` parameter instructs Setup to install the Analysis Services program and configuration files required for PowerPivot for SharePoint.</span></span> <span data-ttu-id="ff736-131">Questo ruolo consente inoltre di rilevare e utilizzare le informazioni di connettività della farm esistente per accedere al database di configurazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ff736-131">This role also detects and uses the existing farm connectivity information to access the SharePoint configuration database.</span></span> <span data-ttu-id="ff736-132">Questo parametro è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ff736-132">This parameter is required.</span></span> <span data-ttu-id="ff736-133">Utilizzarlo invece del parametro `/features` per specificare i componenti da installare.</span><span class="sxs-lookup"><span data-stu-id="ff736-133">Use it instead of the `/features` parameter to specify the components to install.</span></span>  
  
     <span data-ttu-id="ff736-134">Il parametro `/instancename` specifica 'PowerPivot' come un'istanza denominata.</span><span class="sxs-lookup"><span data-stu-id="ff736-134">The `/instancename` parameter specifies 'PowerPivot' as a named instance.</span></span> <span data-ttu-id="ff736-135">Questo valore è specificato a livello di codice e non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="ff736-135">This value is hard-coded and cannot be changed.</span></span> <span data-ttu-id="ff736-136">Viene specificato nel comando per scopi didattici per sapere in che modo è stato installato il servizio.</span><span class="sxs-lookup"><span data-stu-id="ff736-136">It is specified in the command for educational purposes so that you know how the service is installed.</span></span>  
  
     <span data-ttu-id="ff736-137">Il parametro `/indicateprogress` consente di monitorare lo stato di avanzamento nella finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="ff736-137">The `/indicateprogress` parameter allows you to monitor progress in the command prompt window.</span></span>  
  
2.  <span data-ttu-id="ff736-138">Il parametro `PID` viene omesso dal comando, di conseguenza viene installata la copia di valutazione.</span><span class="sxs-lookup"><span data-stu-id="ff736-138">The `PID` parameter is omitted from the command, which causes the Evaluation edition to be installed.</span></span> <span data-ttu-id="ff736-139">Se si desidera installare la Enterprise Edition, aggiungere il PID al comando Setup e fornire un codice Product Key valido.</span><span class="sxs-lookup"><span data-stu-id="ff736-139">If you want to install the Enterprise edition, add the PID to your Setup command and provide a valid product key.</span></span>  
  
    ```  
    /PID=<product key for an Enterprise installation>  
    ```  
  
3.  <span data-ttu-id="ff736-140">Sostituire i segnaposto per \<domain\username> e \<StrongPassword> con account utente e password validi.</span><span class="sxs-lookup"><span data-stu-id="ff736-140">Replace the placeholders for \<domain\username> and \<StrongPassword>with valid user accounts and passwords.</span></span>  
  
     <span data-ttu-id="ff736-141">I `/assvaccount` parametri e **/ASSVCPASSWORD** vengono utilizzati per configurare l' [!INCLUDE[ssGeminiSrv](../../includes/ssgeminisrv-md.md)] istanza nel server applicazioni.</span><span class="sxs-lookup"><span data-stu-id="ff736-141">The `/assvaccount` and **/assvcpassword** parameters are used to configure the [!INCLUDE[ssGeminiSrv](../../includes/ssgeminisrv-md.md)] instance on the application server.</span></span> <span data-ttu-id="ff736-142">Sostituire questi segnaposto con informazioni sull'account valide.</span><span class="sxs-lookup"><span data-stu-id="ff736-142">Replace these placeholders with valid account information.</span></span>  
  
     <span data-ttu-id="ff736-143">Il parametro **/ASSYSADMINACCOUNTS** deve essere impostato sull'identità dell'utente che esegue SQL Server installazione.</span><span class="sxs-lookup"><span data-stu-id="ff736-143">The **/assysadminaccounts** parameter must be set to the identity of the user who is running SQL Server Setup.</span></span> <span data-ttu-id="ff736-144">È necessario specificare almeno un amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="ff736-144">You must specify at least one system administrator.</span></span> <span data-ttu-id="ff736-145">Si noti che il programma di installazione di SQL Server non concede più autorizzazioni sysadmin automatiche ai membri del gruppo Administrators predefinito.</span><span class="sxs-lookup"><span data-stu-id="ff736-145">Note that SQL Server Setup no long grants automatic sysadmin permissions to members of the built-in Administrators group.</span></span>  
  
4.  <span data-ttu-id="ff736-146">Rimuovere le interruzioni di riga.</span><span class="sxs-lookup"><span data-stu-id="ff736-146">Remove line breaks.</span></span>  
  
5.  <span data-ttu-id="ff736-147">Selezionare l'intero comando e quindi fare clic su **copia** nel menu Modifica.</span><span class="sxs-lookup"><span data-stu-id="ff736-147">Select the entire command and then click **Copy** on the Edit menu.</span></span>  
  
6.  <span data-ttu-id="ff736-148">Aprire un prompt dei comandi dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="ff736-148">Open an administrator command prompt.</span></span> <span data-ttu-id="ff736-149">A tale scopo, fare clic sul pulsante **Start**, fare clic con il pulsante destro del mouse sul prompt dei comandi e scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="ff736-149">To do this, click **Start**, right-click the command prompt, and select **Run as administrator**.</span></span>  
  
7.  <span data-ttu-id="ff736-150">Spostarsi sull'unità o sulla cartella condivisa che contiene i supporti di installazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ff736-150">Navigate to the drive or shared folder that contains the SQL Server installation media.</span></span>  
  
8.  <span data-ttu-id="ff736-151">Incollare il comando rivisto nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="ff736-151">Paste the revised command into the command line.</span></span> <span data-ttu-id="ff736-152">A tale scopo, fare clic sull'icona nell'angolo superiore sinistro della finestra del prompt dei comandi, scegliere **modifica**e quindi fare clic su **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="ff736-152">To do this, click the icon in the top left corner of the command prompt window, point to **Edit**, and then click **Paste**.</span></span>  
  
9. <span data-ttu-id="ff736-153">Premere **invio** per eseguire il comando.</span><span class="sxs-lookup"><span data-stu-id="ff736-153">Press **Enter** to run the command.</span></span> <span data-ttu-id="ff736-154">Attendere il completamento dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="ff736-154">Wait for setup to complete.</span></span> <span data-ttu-id="ff736-155">È possibile monitorare lo stato di avanzamento dell'installazione nella finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="ff736-155">You can monitor Setup's progress in the command prompt window.</span></span>  
  
10. <span data-ttu-id="ff736-156">Per verificare installazione, controllare il file summary.txt in \Programmi\SQL Server\120\Setup Bootstrap\Log.</span><span class="sxs-lookup"><span data-stu-id="ff736-156">To verify installation, check the summary.txt file at \Program Files\SQL Server\120\Setup Bootstrap\Log.</span></span> <span data-ttu-id="ff736-157">Il risultato finale deve essere "Superato" se il server viene installato senza errori.</span><span class="sxs-lookup"><span data-stu-id="ff736-157">Final result should say "Passed" if the server installed without errors.</span></span>  
  
11. <span data-ttu-id="ff736-158">Configurare il server.</span><span class="sxs-lookup"><span data-stu-id="ff736-158">Configure the server.</span></span> <span data-ttu-id="ff736-159">È necessario almeno distribuire soluzioni, creare un'applicazione di servizio e abilitare la caratteristica per ogni raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="ff736-159">At a minimum, you must deploy solutions, create a service application, and enable the feature for each site collection.</span></span> <span data-ttu-id="ff736-160">Per ulteriori informazioni, vedere [configurare o ripristinare PowerPivot per SharePoint 2010 &#40;strumento di configurazione powerpivot&#41;](../../../2014/analysis-services/configure-repair-powerpivot-sharepoint-2010.md) o [amministrazione e configurazione del server PowerPivot in Amministrazione centrale](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-server-administration-and-configuration-in-central-administration).</span><span class="sxs-lookup"><span data-stu-id="ff736-160">For more information, see [Configure or Repair PowerPivot for SharePoint 2010 &#40;PowerPivot Configuration Tool&#41;](../../../2014/analysis-services/configure-repair-powerpivot-sharepoint-2010.md) or [PowerPivot Server Administration and Configuration in Central Administration](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-server-administration-and-configuration-in-central-administration).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff736-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff736-161">See Also</span></span>  
 <span data-ttu-id="ff736-162">[Configurare gli account del servizio PowerPivot](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/configure-power-pivot-service-accounts) </span><span class="sxs-lookup"><span data-stu-id="ff736-162">[Configure PowerPivot Service Accounts](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/configure-power-pivot-service-accounts) </span></span>  
 [<span data-ttu-id="ff736-163">Installazione di PowerPivot per SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="ff736-163">PowerPivot for SharePoint 2010 Installation</span></span>](../../../2014/sql-server/install/powerpivot-for-sharepoint-2010-installation.md)  
