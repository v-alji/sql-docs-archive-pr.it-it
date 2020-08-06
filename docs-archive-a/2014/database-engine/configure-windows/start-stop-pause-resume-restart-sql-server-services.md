---
title: Avviare, arrestare, sospendere, riprendere, riavviare il servizio motore di database, SQL Server Agent o SQL Server Browser | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Configuration Manager, start and stop services
- stopping SQL Server Agent
- parameters [SQL Server], startup options
- SQL Server, startup options
- Database Engine [SQL Server], starting and stopping services
- pausing SQL Server
- PowerShell [SQL Server], starting and stopping services
- single-user mode [SQL Server], starting in
- SQL Server Management Studio [SQL Server], starting or stopping services
- stopping SQL Server Browser service
- starting SQL Server Agent
- default instances [SQL Server], starting and stopping
- SQL Server Agent, starting and stopping
- command prompt [SQL Server], starting and stopping SQL Server services
- continuing SQL Server
- starting SQL Server Database Engine
- net stop commands [SQL Server]
- command prompt [SQL Server], SQL Browser service
- Configuration Manager, start and stop services
- resuming SQL Server
- startup options [SQL Server]
- named instances [SQL Server], starting and stopping
- net start commands [SQL Server]
- SQL Server, starting and stopping
- stopping SQL Server
- starting SQL Server Browser service
- SQL Server Database Engine setting startup options
- administering SQL Server, starting and stopping services
- Management Studio [SQL Server], starting or stopping services
ms.assetid: 32660a02-e5a1-411a-9e57-7066ca459df6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f4b102c8fd81923d7386c8e556896e715311a07e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723027"
---
# <a name="start-stop-pause-resume-restart-the-database-engine-sql-server-agent-or-sql-server-browser-service"></a><span data-ttu-id="3cbae-102">Avviare, arrestare, sospendere, riprendere, riavviare il motore di database, SQL Server Agent o SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="3cbae-102">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>
  <span data-ttu-id="3cbae-103">In questo argomento viene illustrato come avviare, i comandi arrestare, i comandi sospendere, i comandi riprendere o riavviare [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], i comandi [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser usando Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , i comandi [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], i comandi **net** da un prompt dei comandi, i comandi [!INCLUDE[tsql](../../includes/tsql-md.md)], i comandi or PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3cbae-103">This topic describes how to start, stop, pause, resume, or restart the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], **net** commands from a command prompt, [!INCLUDE[tsql](../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
-   <span data-ttu-id="3cbae-104">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="3cbae-104">**Before you begin:**</span></span>  
  
    -   [<span data-ttu-id="3cbae-105">Descrizione dei servizi</span><span class="sxs-lookup"><span data-stu-id="3cbae-105">What are these services?</span></span>](#Services)  
  
    -   [<span data-ttu-id="3cbae-106">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="3cbae-106">Additional Information</span></span>](#MoreInformation)  
  
    -   [<span data-ttu-id="3cbae-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="3cbae-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3cbae-108">**Istruzioni relative all'utilizzo di:**</span><span class="sxs-lookup"><span data-stu-id="3cbae-108">**Instructions using:**</span></span>  
  
    -   [<span data-ttu-id="3cbae-109">Gestione configurazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="3cbae-109">SQL Server Configuration Manager</span></span>](#SSCMProcedure)  
  
    -   [<span data-ttu-id="3cbae-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3cbae-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
    -   [<span data-ttu-id="3cbae-111">Comandi net da una finestra del prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="3cbae-111">net Commands from a Command Prompt window</span></span>](#CommandPrompt)  
  
    -   [<span data-ttu-id="3cbae-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3cbae-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
    -   [<span data-ttu-id="3cbae-113">PowerShell</span><span class="sxs-lookup"><span data-stu-id="3cbae-113">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3cbae-114">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="3cbae-114">Before You Begin</span></span>  
  
###  <a name="what-is-the-ssdenoversion-service-the-ssnoversion-agent-service-and-the-ssnoversion-browser-service"></a><a name="Services"></a> <span data-ttu-id="3cbae-115">Descrizione dei servizi [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent e [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser</span><span class="sxs-lookup"><span data-stu-id="3cbae-115">What is the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] service, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service, and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service?</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3cbae-116">sono programmi eseguibili che vengono eseguiti come servizi Windows.</span><span class="sxs-lookup"><span data-stu-id="3cbae-116">components are executable programs that run as a Windows service.</span></span> <span data-ttu-id="3cbae-117">I programmi che vengono eseguiti come servizi Windows rimangono in esecuzione anche se sullo schermo del computer non viene rilevata alcuna attività.</span><span class="sxs-lookup"><span data-stu-id="3cbae-117">Programs that run as a Windows service can continue to operate without displaying any activity on the computer screen.</span></span>  
  
 <span data-ttu-id="3cbae-118">**[!INCLUDE[ssDE](../../includes/ssde-md.md)]servizio**</span><span class="sxs-lookup"><span data-stu-id="3cbae-118">**[!INCLUDE[ssDE](../../includes/ssde-md.md)] service**</span></span>  
 <span data-ttu-id="3cbae-119">Processo eseguibile dato da [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cbae-119">The executable process that is the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="3cbae-120">Il [!INCLUDE[ssDE](../../includes/ssde-md.md)] può essere l'istanza predefinita (una per computer) o una delle molte istanze denominate del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cbae-120">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] can be the default instance (limit one per computer), or can be one of many named instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="3cbae-121">Usare Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per determinare quali istanze del [!INCLUDE[ssDE](../../includes/ssde-md.md)] vengono installate nel computer.</span><span class="sxs-lookup"><span data-stu-id="3cbae-121">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to determine which instances of [!INCLUDE[ssDE](../../includes/ssde-md.md)] are installed on the computer.</span></span> <span data-ttu-id="3cbae-122">L'istanza predefinita (se installata) è indicata come \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER)\*\*.</span><span class="sxs-lookup"><span data-stu-id="3cbae-122">The default instance (if you install it) is listed as **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER)**.</span></span> <span data-ttu-id="3cbae-123">Le istanze denominate (se installate) vengono elencate come \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (<instance_name>)\*\*.</span><span class="sxs-lookup"><span data-stu-id="3cbae-123">Named instances (if you install them) are listed as **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (<instance_name>)**.</span></span> <span data-ttu-id="3cbae-124">Per impostazione predefinita, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express viene installato come \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SQLEXPRESS)\*\*.</span><span class="sxs-lookup"><span data-stu-id="3cbae-124">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express is installed as **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SQLEXPRESS)**.</span></span>  
  
 <span data-ttu-id="3cbae-125">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Servizio Agent**</span><span class="sxs-lookup"><span data-stu-id="3cbae-125">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service**</span></span>  
 <span data-ttu-id="3cbae-126">Servizio di Windows che esegue attività amministrative pianificate, ovvero processi e avvisi.</span><span class="sxs-lookup"><span data-stu-id="3cbae-126">A Windows service that executes scheduled administrative tasks, which are called jobs and alerts.</span></span> <span data-ttu-id="3cbae-127">Per altre informazioni, vedere [SQL Server Agent](../../ssms/agent/sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="3cbae-127">For more information, see [SQL Server Agent](../../ssms/agent/sql-server-agent.md).</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3cbae-128">Agent non è disponibile in ogni edizione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cbae-128">Agent is not available in every edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3cbae-129">Per un elenco delle funzionalità supportate dalle edizioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vedere [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="3cbae-129">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="3cbae-130">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Servizio browser**</span><span class="sxs-lookup"><span data-stu-id="3cbae-130">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service**</span></span>  
 <span data-ttu-id="3cbae-131">Servizio di Windows che rimane in attesa delle richieste in arrivo per le risorse di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e fornisce ai client informazioni sulle istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installate nel computer.</span><span class="sxs-lookup"><span data-stu-id="3cbae-131">A Windows service that listens for incoming requests for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources and provides clients information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span> <span data-ttu-id="3cbae-132">Viene usata una singola istanza del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser per tutte le istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installate nel computer.</span><span class="sxs-lookup"><span data-stu-id="3cbae-132">A single instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service is used for all instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installed on the computer.</span></span>  
  
###  <a name="additional-information"></a><a name="MoreInformation"></a><span data-ttu-id="3cbae-133">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="3cbae-133">Additional Information</span></span>  
  
-   <span data-ttu-id="3cbae-134">Sospendendo il servizio [!INCLUDE[ssDE](../../includes/ssde-md.md)] si impedisce a nuovi utenti di connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)], ma si consente a quelli già connessi di continuare a lavorare finché le connessioni non vengono interrotte.</span><span class="sxs-lookup"><span data-stu-id="3cbae-134">Pausing the [!INCLUDE[ssDE](../../includes/ssde-md.md)] service prevents new users from connecting to the [!INCLUDE[ssDE](../../includes/ssde-md.md)], but users who are already connected can continue to work until their connections are broken.</span></span> <span data-ttu-id="3cbae-135">Sospendere il servizio quando si desidera attendere che gli utenti completino il loro lavoro prima di arrestare il servizio.</span><span class="sxs-lookup"><span data-stu-id="3cbae-135">Use pause when you want to wait for users to complete work before you stop the service.</span></span> <span data-ttu-id="3cbae-136">In questo modo, gli utenti possono completare le transazioni in corso.</span><span class="sxs-lookup"><span data-stu-id="3cbae-136">This enables them to complete transactions that are in progress.</span></span> <span data-ttu-id="3cbae-137">Riprendi consente al [!INCLUDE[ssDE](../../includes/ssde-md.md)] di accettare nuove connessioni.</span><span class="sxs-lookup"><span data-stu-id="3cbae-137">Resume allows the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to accept new connections again.</span></span> <span data-ttu-id="3cbae-138">Non è possibile sospendere né riprendere il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="3cbae-138">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service cannot be paused or resumed.</span></span>  
  
-   <span data-ttu-id="3cbae-139">In Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] viene visualizzato lo stato corrente dei servizi tramite le icone seguenti.</span><span class="sxs-lookup"><span data-stu-id="3cbae-139">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] display the current status of services by using the following icons.</span></span>  
  
     <span data-ttu-id="3cbae-140">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="3cbae-140">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager**</span></span>  
  
    -   <span data-ttu-id="3cbae-141">Una freccia verde sull'icona accanto al nome del servizio indica che il servizio è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="3cbae-141">A green arrow on the icon next to the service name indicates that the service is started.</span></span>  
  
    -   <span data-ttu-id="3cbae-142">Un quadrato rosso sull'icona accanto al nome del servizio indica che il servizio è stato arrestato.</span><span class="sxs-lookup"><span data-stu-id="3cbae-142">A red square on the icon next to the service name indicates that the service is stopped.</span></span>  
  
    -   <span data-ttu-id="3cbae-143">Due linee blu verticali sull'icona accanto al nome del servizio indica che il servizio è stato sospeso.</span><span class="sxs-lookup"><span data-stu-id="3cbae-143">Two vertical blue lines on the icon next to the service name indicates that the service is paused.</span></span>  
  
    -   <span data-ttu-id="3cbae-144">Quando il [!INCLUDE[ssDE](../../includes/ssde-md.md)]viene riavviato, un quadrato rosso indica che il servizio è stato arrestato, dopodiché una freccia verde indicherà che il servizio è stato avviato correttamente.</span><span class="sxs-lookup"><span data-stu-id="3cbae-144">When restarting the [!INCLUDE[ssDE](../../includes/ssde-md.md)], a red square will indicate that the service stopped, and then a green arrow will indicate that he service started successfully.</span></span>  
  
     **[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**  
  
    -   <span data-ttu-id="3cbae-145">Una freccia bianca su un cerchio verde accanto al nome del servizio indica che il servizio è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="3cbae-145">A white arrow on a green circle icon next to the service name indicates that the service is started.</span></span>  
  
    -   <span data-ttu-id="3cbae-146">Un quadrato bianco su un cerchio rosso accanto al nome del servizio indica che il servizio è stato arrestato.</span><span class="sxs-lookup"><span data-stu-id="3cbae-146">A white square on a red circle icon next to the service name indicates that the service is stopped.</span></span>  
  
    -   <span data-ttu-id="3cbae-147">Due linee bianche verticali su un cerchio blu accanto al nome del servizio indica che il servizio è stato sospeso.</span><span class="sxs-lookup"><span data-stu-id="3cbae-147">Two vertical white lines on a blue circle icon next to the service name indicates that the service is paused.</span></span>  
  
-   <span data-ttu-id="3cbae-148">Se si usano Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]solo le opzioni possibili saranno disponibili.</span><span class="sxs-lookup"><span data-stu-id="3cbae-148">When using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager or [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], only options that are possible will be available.</span></span> <span data-ttu-id="3cbae-149">Ad esempio, se il servizio è già avviato, l'opzione **Avvia** non sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="3cbae-149">For example, if the service is already started, **Start** will be unavailable.</span></span>  
  
-   <span data-ttu-id="3cbae-150">Se l'esecuzione avviene su un cluster, il servizio [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] verrà gestito al meglio tramite Amministrazione cluster.</span><span class="sxs-lookup"><span data-stu-id="3cbae-150">When running on a cluster, the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] service is best managed by using Cluster Administrator.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3cbae-151">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="3cbae-151">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3cbae-152">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="3cbae-152">Permissions</span></span>  
 <span data-ttu-id="3cbae-153">Per impostazione predefinita, solo i membri del gruppo di amministratori locale possono avviare, arrestare, mettere in pausa, riprendere o riavviare un servizio.</span><span class="sxs-lookup"><span data-stu-id="3cbae-153">By default, only members of the local administrators group can start, stop, pause, resume or restart a service.</span></span> <span data-ttu-id="3cbae-154">Per concedere a utenti non amministratori la possibilità di gestire servizi, vedere [Concedere agli utenti i privilegi per gestire i servizi in Windows Server 2003](https://support.microsoft.com/kb/325349).</span><span class="sxs-lookup"><span data-stu-id="3cbae-154">To grant non-administrators the ability to manage services, see [How to grant users rights to manage services in Windows Server 2003](https://support.microsoft.com/kb/325349).</span></span> <span data-ttu-id="3cbae-155">Il processo è analogo ad altre versioni di Windows.</span><span class="sxs-lookup"><span data-stu-id="3cbae-155">(The process is similar on other versions of Windows.)</span></span>  
  
 <span data-ttu-id="3cbae-156">L'arresto [!INCLUDE[ssDE](../../includes/ssde-md.md)] di utilizzando il [!INCLUDE[tsql](../../includes/tsql-md.md)] `SHUTDOWN` comando richiede l'appartenenza al ruolo predefinito del server **sysadmin** o **serveradmin** e non è trasferibile.</span><span class="sxs-lookup"><span data-stu-id="3cbae-156">Stopping the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by using the [!INCLUDE[tsql](../../includes/tsql-md.md)]`SHUTDOWN` command requires membership in the **sysadmin** or **serveradmin** fixed server roles, and is not transferable.</span></span>  
  
##  <a name="using-ssnoversion-configuration-manager"></a><a name="SSCMProcedure"></a><span data-ttu-id="3cbae-157">Utilizzo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3cbae-157">Using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager</span></span>  
  
#### <a name="to-start-stop-pause-resume-or-restart-the-an-instance-of-the-ssdenoversion"></a><span data-ttu-id="3cbae-158">Per avviare, arrestare, sospendere, riprendere o riavviare un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cbae-158">To start, stop, pause, resume, or restart the an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]</span></span>  
  
1.  <span data-ttu-id="3cbae-159">Fare clic sul menu **Start** , scegliere **Tutti i programmi**, [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], **Strumenti di configurazione**e quindi **Gestione configurazione SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="3cbae-159">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="3cbae-160">Se viene visualizzata la finestra di dialogo **Controllo account utente** fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="3cbae-160">If the **User Account Control** dialog box appears, click **Yes**.</span></span>  
  
3.  <span data-ttu-id="3cbae-161">Nel riquadro a sinistra di Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fare clic su **Servizi di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="3cbae-161">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the left pane, click **SQL Server Services**.</span></span>  
  
4.  <span data-ttu-id="3cbae-162">Nel riquadro dei risultati fare clic con il pulsante destro del mouse su **SQL Server (MSSQLServer)** o su un'istanza denominata, quindi fare clic su **Avvia**, **Arresta**, **Sospendi**, **Riprendi**o **Riavvia**.</span><span class="sxs-lookup"><span data-stu-id="3cbae-162">In the results pane, right-click **SQL Server (MSSQLServer)** or a named instance, and then click **Start**, **Stop**, **Pause**, **Resume**, or **Restart**.</span></span>  
  
5.  <span data-ttu-id="3cbae-163">Fare clic su **OK** per chiudere Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3cbae-163">Click **OK** to close [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3cbae-164">Per avviare un'istanza di [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] con le opzioni di avvio, vedere [Configurare le opzioni di avvio del server &#40;Gestione configurazione SQL Server&#41;](scm-services-configure-server-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="3cbae-164">To start an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with startup options, see [Configure Server Startup Options &#40;SQL Server Configuration Manager&#41;](scm-services-configure-server-startup-options.md).</span></span>  
  
#### <a name="to-start-stop-pause-resume-or-restart-the-ssnoversion-browser-or-an-instance-of-the-ssnoversion-agent"></a><span data-ttu-id="3cbae-165">Per avviare, arrestare, sospendere, riprendere o riavviare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser o un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span><span class="sxs-lookup"><span data-stu-id="3cbae-165">To start, stop, pause, resume, or restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser or an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
1.  <span data-ttu-id="3cbae-166">Fare clic sul menu **Start** , scegliere **Tutti i programmi**, [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], **Strumenti di configurazione**e quindi **Gestione configurazione SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="3cbae-166">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="3cbae-167">Se viene visualizzata la finestra di dialogo **Controllo account utente** fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="3cbae-167">If the **User Account Control** dialog box appears, click **Yes**.</span></span>  
  
3.  <span data-ttu-id="3cbae-168">Nel riquadro a sinistra di Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fare clic su **Servizi di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="3cbae-168">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the left pane, click **SQL Server Services**.</span></span>  
  
4.  <span data-ttu-id="3cbae-169">Nel riquadro dei risultati fare clic con il pulsante destro del mouse su \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] browser**, \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent (MSSQLServer)** o \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent (<instance_name>)\*\* per un'istanza denominata, quindi fare clic su **Avvia**, **Interrompi**, **Sospendi**, **Riprendi**o **Riavvia**.</span><span class="sxs-lookup"><span data-stu-id="3cbae-169">In the results pane, right-click **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser**, or **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent (MSSQLServer)** or **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent (<instance_name>)** for a named instance, and then click **Start**, **Stop**, **Pause**, **Resume**, or **Restart**.</span></span>  
  
5.  <span data-ttu-id="3cbae-170">Fare clic su **OK** per chiudere Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3cbae-170">Click **OK** to close [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3cbae-171">Non è possibile sospendere Agent.</span><span class="sxs-lookup"><span data-stu-id="3cbae-171">Agent cannot be paused.</span></span>  
  
##  <a name="using-ssnoversion-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3cbae-172">Utilizzo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Studio</span><span class="sxs-lookup"><span data-stu-id="3cbae-172">Using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Studio</span></span>  
  
#### <a name="to-start-stop-pause-resume-or-restart-the-an-instance-of-the-ssdenoversion"></a><span data-ttu-id="3cbae-173">Per avviare, arrestare, sospendere, riprendere o riavviare un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cbae-173">To start, stop, pause, resume, or restart the an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]</span></span>  
  
1.  <span data-ttu-id="3cbae-174">In Esplora oggetti connettersi all'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)], fare clic con il pulsante destro del mouse sull'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] da avviare, quindi fare clic su **Avvia**, **Arresta**, **Sospendi**, **Riprendi**o **Riavvia**.</span><span class="sxs-lookup"><span data-stu-id="3cbae-174">In Object Explorer, connect to the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], right-click the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] you want to start, and then click **Start**, **Stop**, **Pause**, **Resume**, or **Restart**.</span></span>  
  
     <span data-ttu-id="3cbae-175">Oppure, in Server registrati fare clic con il pulsante destro del mouse sull'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] da avviare, selezionare **Controllo servizi**e quindi fare clic su **Avvia**, **Arresta**, **Sospendi**, **Riprendi**o **Riavvia**.</span><span class="sxs-lookup"><span data-stu-id="3cbae-175">Or, in Registered Servers, right-click the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] you want to start, point to **Service Control**, and then click **Start**, **Stop**, **Pause**, **Resume**, or **Restart**.</span></span>  
  
2.  <span data-ttu-id="3cbae-176">Se viene visualizzata la finestra di dialogo **Controllo account utente** fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="3cbae-176">If the **User Account Control** dialog box appears, click **Yes**.</span></span>  
  
3.  <span data-ttu-id="3cbae-177">Se viene richiesto di eseguire l'azione, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="3cbae-177">When prompted if you want to perform the action, click **Yes**.</span></span>  
  
#### <a name="to-start-stop-or-restart-the-an-instance-of-the-ssnoversion-agent"></a><span data-ttu-id="3cbae-178">Per avviare, arrestare o riavviare un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span><span class="sxs-lookup"><span data-stu-id="3cbae-178">To start, stop, or restart the an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
1.  <span data-ttu-id="3cbae-179">In Esplora oggetti connettersi all'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] , fare clic con il pulsante destro del mouse su \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent\*\*, quindi fare clic su **Avvia**, **Arresta**o **Riavvia**.</span><span class="sxs-lookup"><span data-stu-id="3cbae-179">In Object Explorer, connect to the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], right-click **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent**, and then click **Start**, **Stop**, or **Restart**.</span></span>  
  
2.  <span data-ttu-id="3cbae-180">Se viene visualizzata la finestra di dialogo **Controllo account utente** fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="3cbae-180">If the **User Account Control** dialog box appears, click **Yes**.</span></span>  
  
3.  <span data-ttu-id="3cbae-181">Se viene richiesto di eseguire l'azione, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="3cbae-181">When prompted if you want to perform the action, click **Yes**.</span></span>  
  
##  <a name="from-the-command-prompt-window-using-net-commands"></a><a name="CommandPrompt"></a> <span data-ttu-id="3cbae-182">Utilizzo dei comandi net dalla finestra del prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="3cbae-182">From the Command Prompt Window using net Commands</span></span>  
 <span data-ttu-id="3cbae-183">I servizi [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] possono essere avviati, arrestati o sospesi usando i comandi **net** di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="3cbae-183">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services can be started, stopped, or paused by using [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows **net** commands.</span></span>  
  
###  <a name="to-start-the-default-instance-of-the-ssde"></a><a name="dbDefault"></a> <span data-ttu-id="3cbae-184">Per avviare l'istanza predefinita del [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cbae-184">To start the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span></span>  
  
-   <span data-ttu-id="3cbae-185">Al prompt dei comandi digitare uno dei comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3cbae-185">From a command prompt, enter one of the following commands:</span></span>  
  
     <span data-ttu-id="3cbae-186">**net start "SQL Server (MSSQLSERVER)"**</span><span class="sxs-lookup"><span data-stu-id="3cbae-186">**net start "SQL Server (MSSQLSERVER)"**</span></span>  
  
     <span data-ttu-id="3cbae-187">-oppure-</span><span class="sxs-lookup"><span data-stu-id="3cbae-187">-or-</span></span>  
  
     <span data-ttu-id="3cbae-188">**net start MSSQLSERVER**</span><span class="sxs-lookup"><span data-stu-id="3cbae-188">**net start MSSQLSERVER**</span></span>  
  
###  <a name="to-start-a-named-instance-of-the-ssde"></a><a name="dbNamed"></a> <span data-ttu-id="3cbae-189">Per avviare un'istanza denominata del [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cbae-189">To start a named instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span></span>  
  
-   <span data-ttu-id="3cbae-190">Al prompt dei comandi digitare uno dei comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="3cbae-190">From a command prompt, enter one of the following commands.</span></span> <span data-ttu-id="3cbae-191">Sostituire *\<instancename>* con il nome dell'istanza da gestire.</span><span class="sxs-lookup"><span data-stu-id="3cbae-191">Replace *\<instancename>* with the name of the instance you want to manage.</span></span>  
  
     <span data-ttu-id="3cbae-192">**net start "SQL Server (** *instancename* **)"**</span><span class="sxs-lookup"><span data-stu-id="3cbae-192">**net start "SQL Server (** *instancename* **)"**</span></span>  
  
     <span data-ttu-id="3cbae-193">-oppure-</span><span class="sxs-lookup"><span data-stu-id="3cbae-193">-or-</span></span>  
  
     <span data-ttu-id="3cbae-194">**net start MSSQL$** *instancename*</span><span class="sxs-lookup"><span data-stu-id="3cbae-194">**net start MSSQL$** *instancename*</span></span>  
  
###  <a name="to-start-the-ssde-with-startup-options"></a><a name="dbStartup"></a> <span data-ttu-id="3cbae-195">Per avviare il [!INCLUDE[ssDE](../../includes/ssde-md.md)] con le opzioni di avvio</span><span class="sxs-lookup"><span data-stu-id="3cbae-195">To start the [!INCLUDE[ssDE](../../includes/ssde-md.md)] with startup options</span></span>  
  
-   <span data-ttu-id="3cbae-196">Aggiungere le opzioni di avvio alla fine dell'istruzione **net start "SQL Server (MSSQLSERVER)"** , separate da uno spazio.</span><span class="sxs-lookup"><span data-stu-id="3cbae-196">Add startup options to the end of the **net start "SQL Server (MSSQLSERVER)"** statement, separated by a space.</span></span> <span data-ttu-id="3cbae-197">Quando vengono avviate con **net start**, le opzioni di avvio usano una barra (/) anziché un trattino (-).</span><span class="sxs-lookup"><span data-stu-id="3cbae-197">When started using **net start**, startup options use a slash (/) instead of a hyphen (-).</span></span>  
  
     <span data-ttu-id="3cbae-198">**net start "SQL Server (MSSQLSERVER)" /f /m**</span><span class="sxs-lookup"><span data-stu-id="3cbae-198">**net start "SQL Server (MSSQLSERVER)" /f /m**</span></span>  
  
     <span data-ttu-id="3cbae-199">-oppure-</span><span class="sxs-lookup"><span data-stu-id="3cbae-199">-or-</span></span>  
  
     <span data-ttu-id="3cbae-200">**net start MSSQLSERVER /f /m**</span><span class="sxs-lookup"><span data-stu-id="3cbae-200">**net start MSSQLSERVER /f /m**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3cbae-201">Per altre informazioni sulle opzioni di avvio, vedere [Opzioni di avvio del servizio del motore di database](database-engine-service-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="3cbae-201">For more information about startup options, see [Database Engine Service Startup Options](database-engine-service-startup-options.md).</span></span>  
  
###  <a name="to-start-the-ssnoversion-agent-on-the-default-instance-of-ssnoversion"></a><a name="agDefault"></a> <span data-ttu-id="3cbae-202">Per avviare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sull'istanza predefinita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cbae-202">To start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent on the default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="3cbae-203">Al prompt dei comandi digitare uno dei comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3cbae-203">From a command prompt, enter one of the following commands:</span></span>  
  
     <span data-ttu-id="3cbae-204">**net start "SQL Server Agent (MSSQLSERVER)"**</span><span class="sxs-lookup"><span data-stu-id="3cbae-204">**net start "SQL Server Agent (MSSQLSERVER)"**</span></span>  
  
     <span data-ttu-id="3cbae-205">-oppure-</span><span class="sxs-lookup"><span data-stu-id="3cbae-205">-or-</span></span>  
  
     <span data-ttu-id="3cbae-206">**net start SQLSERVERAGENT**</span><span class="sxs-lookup"><span data-stu-id="3cbae-206">**net start SQLSERVERAGENT**</span></span>  
  
###  <a name="to-start-the-ssnoversion-agent-on-a-named-instance-of-ssnoversion"></a><a name="agNamed"></a> <span data-ttu-id="3cbae-207">Per avviare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent su un'istanza denominata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cbae-207">To start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent on a named instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="3cbae-208">Al prompt dei comandi digitare uno dei comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="3cbae-208">From a command prompt, enter one of the following commands.</span></span> <span data-ttu-id="3cbae-209">Sostituire *instancename* con il nome dell'istanza da gestire.</span><span class="sxs-lookup"><span data-stu-id="3cbae-209">Replace *instancename* with the name of the instance you want to manage.</span></span>  
  
     <span data-ttu-id="3cbae-210">**net start "SQL Server Agent(** *instancename* **)"**</span><span class="sxs-lookup"><span data-stu-id="3cbae-210">**net start "SQL Server Agent(** *instancename* **)"**</span></span>  
  
     <span data-ttu-id="3cbae-211">-oppure-</span><span class="sxs-lookup"><span data-stu-id="3cbae-211">-or-</span></span>  
  
     <span data-ttu-id="3cbae-212">**net start SQLAgent$** *instancename*</span><span class="sxs-lookup"><span data-stu-id="3cbae-212">**net start SQLAgent$** *instancename*</span></span>  
  
 <span data-ttu-id="3cbae-213">Per informazioni sull'esecuzione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in modalità dettagliata per la risoluzione dei problemi, vedere [Applicazione sqlagent90](../../tools/sqlagent90-application.md).</span><span class="sxs-lookup"><span data-stu-id="3cbae-213">For information about how to run [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in verbose mode for troubleshooting, see [sqlagent90 Application](../../tools/sqlagent90-application.md).</span></span>  
  
###  <a name="to-start-the-ssnoversion-browser"></a><a name="Browser"></a> <span data-ttu-id="3cbae-214">Per avviare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser</span><span class="sxs-lookup"><span data-stu-id="3cbae-214">To start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser</span></span>  
  
-   <span data-ttu-id="3cbae-215">Al prompt dei comandi digitare uno dei comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3cbae-215">From a command prompt, enter one of the following commands:</span></span>  
  
     <span data-ttu-id="3cbae-216">**net start "SQL Server Browser"**</span><span class="sxs-lookup"><span data-stu-id="3cbae-216">**net start "SQL Server Browser"**</span></span>  
  
     <span data-ttu-id="3cbae-217">-oppure-</span><span class="sxs-lookup"><span data-stu-id="3cbae-217">-or-</span></span>  
  
     <span data-ttu-id="3cbae-218">**net start SQLBrowser**</span><span class="sxs-lookup"><span data-stu-id="3cbae-218">**net start SQLBrowser**</span></span>  
  
###  <a name="to-pause-or-stop-services-from-the-command-prompt-window"></a><a name="pauseStop"></a> <span data-ttu-id="3cbae-219">Per sospendere o arrestare servizi dalla finestra del prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="3cbae-219">To pause or stop services from the Command Prompt window</span></span>  
  
-   <span data-ttu-id="3cbae-220">Per sospendere o arrestare servizi modificare i comandi nei modi seguenti.</span><span class="sxs-lookup"><span data-stu-id="3cbae-220">To pause or stop services modify the commands in the following ways.</span></span>  
  
    -   <span data-ttu-id="3cbae-221">Per sospendere un servizio, sostituire **net start** con **net pause**.</span><span class="sxs-lookup"><span data-stu-id="3cbae-221">To pause a service, replace **net start** with **net pause**.</span></span>  
  
    -   <span data-ttu-id="3cbae-222">Per arrestare un servizio, sostituire **net start** con **net stop**.</span><span class="sxs-lookup"><span data-stu-id="3cbae-222">To stop a service, replace **net start** with use **net stop**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3cbae-223">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3cbae-223">Using Transact-SQL</span></span>  
 <span data-ttu-id="3cbae-224">È possibile arrestare il [!INCLUDE[ssDE](../../includes/ssde-md.md)] tramite l'istruzione `SHUTDOWN`.</span><span class="sxs-lookup"><span data-stu-id="3cbae-224">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] can be stopped by using the `SHUTDOWN` statement.</span></span>  
  
#### <a name="to-stop-the-ssde-using-tsql"></a><span data-ttu-id="3cbae-225">Per arrestare il [!INCLUDE[ssDE](../../includes/ssde-md.md)] tramite [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cbae-225">To stop the [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
-   <span data-ttu-id="3cbae-226">Per attendere il completamento delle stored procedure e delle istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] attualmente in esecuzione e quindi arrestare [!INCLUDE[ssDE](../../includes/ssde-md.md)], eseguire l'istruzione seguente.</span><span class="sxs-lookup"><span data-stu-id="3cbae-226">To wait for currently running [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and stored procedures to finish, and then stop the [!INCLUDE[ssDE](../../includes/ssde-md.md)], execute the following statement.</span></span>  
  
    ```sql  
    SHUTDOWN;   
    ```  
  
-   <span data-ttu-id="3cbae-227">Per arrestare immediatamente il [!INCLUDE[ssDE](../../includes/ssde-md.md)], eseguire l'istruzione seguente.</span><span class="sxs-lookup"><span data-stu-id="3cbae-227">To stop the [!INCLUDE[ssDE](../../includes/ssde-md.md)] immediately, execute the following statement.</span></span>  
  
    ```sql  
    SHUTDOWN WITH NOWAIT;   
    ```  
  
 <span data-ttu-id="3cbae-228">Per ulteriori informazioni sull' `SHUTDOWN` istruzione, vedere [SHUTDOWN &#40;&#41;Transact-SQL ](/sql/t-sql/language-elements/shutdown-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3cbae-228">For more information about the `SHUTDOWN` statement, see [SHUTDOWN &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/shutdown-transact-sql).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="3cbae-229">Uso di PowerShell</span><span class="sxs-lookup"><span data-stu-id="3cbae-229">Using PowerShell</span></span>  
  
#### <a name="to-start-and-stop-ssde-services"></a><span data-ttu-id="3cbae-230">Per avviare e arrestare i servizi del [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cbae-230">To start and stop [!INCLUDE[ssDE](../../includes/ssde-md.md)] services</span></span>  
  
1.  <span data-ttu-id="3cbae-231">In una finestra del prompt dei comandi avviare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell eseguendo il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="3cbae-231">In a Command Prompt window, start [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell by executing the following command.</span></span>  
  
    ```ms-dos  
    sqlps  
    ```  
  
2.  <span data-ttu-id="3cbae-232">Al prompt dei comandi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="3cbae-232">At a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell command prompt, by executing the following command.</span></span> <span data-ttu-id="3cbae-233">Sostituire `computername` con il nome del computer.</span><span class="sxs-lookup"><span data-stu-id="3cbae-233">Replace `computername` with the name of your computer.</span></span>  
  
    ```powershell  
    # Get a reference to the ManagedComputer class.  
    CD SQLSERVER:\SQL\computername  
    $Wmi = (Get-Item .).ManagedComputer
    ```  
  
3.  <span data-ttu-id="3cbae-234">Identificare il servizio che si desidera arrestare o avviare.</span><span class="sxs-lookup"><span data-stu-id="3cbae-234">Identify the service that you want to stop or start.</span></span> <span data-ttu-id="3cbae-235">Selezionare una delle righe seguenti.</span><span class="sxs-lookup"><span data-stu-id="3cbae-235">Pick one of the following lines.</span></span> <span data-ttu-id="3cbae-236">Sostituire `instancename` con il nome dell'istanza denominata.</span><span class="sxs-lookup"><span data-stu-id="3cbae-236">Replace `instancename` with the name of the named instance.</span></span>  
  
    -   <span data-ttu-id="3cbae-237">Per ottenere un riferimento all'istanza predefinita del [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cbae-237">To get a reference to the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['MSSQLSERVER']  
        ```  
  
    -   <span data-ttu-id="3cbae-238">Per ottenere un riferimento a un'istanza denominata del [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cbae-238">To get a reference to a named instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['MSSQL$instancename']  
        ```  
  
    -   <span data-ttu-id="3cbae-239">Per ottenere un riferimento al servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sull'istanza predefinita del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cbae-239">To get a reference to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service on the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['SQLSERVERAGENT']  
        ```  
  
    -   <span data-ttu-id="3cbae-240">Per ottenere un riferimento al servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent su un'istanza denominata del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cbae-240">To get a reference to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service on a named instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['SQLAGENT$instancename']  
        ```  
  
    -   <span data-ttu-id="3cbae-241">Per ottenere un riferimento al servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser.</span><span class="sxs-lookup"><span data-stu-id="3cbae-241">To get a reference to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['SQLBROWSER']  
        ```  
  
4.  <span data-ttu-id="3cbae-242">Completare l'esempio per avviare e quindi arrestare il servizio selezionato.</span><span class="sxs-lookup"><span data-stu-id="3cbae-242">Complete the example to start and then stop the selected service.</span></span>  
  
    ```powershell  
    # Display the state of the service.  
    $DfltInstance  
    # Start the service.  
    $DfltInstance.Start();  
    # Wait until the service has time to start.  
    # Refresh the cache.  
    $DfltInstance.Refresh();   
    # Display the state of the service.  
    $DfltInstance  
    # Stop the service.  
    $DfltInstance.Stop();  
    # Wait until the service has time to stop.  
    # Refresh the cache.  
    $DfltInstance.Refresh();   
    # Display the state of the service.  
    $DfltInstance  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3cbae-243">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3cbae-243">See Also</span></span>  
 <span data-ttu-id="3cbae-244">[Avviare SQL Server con la configurazione minima](start-sql-server-with-minimal-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="3cbae-244">[Start SQL Server with Minimal Configuration](start-sql-server-with-minimal-configuration.md) </span></span>  
 [<span data-ttu-id="3cbae-245">Funzionalità supportate dalle edizioni di SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="3cbae-245">Features Supported by the Editions of SQL Server 2014</span></span>](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
