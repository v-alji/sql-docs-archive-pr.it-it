---
title: Eseguire passaggi di Windows PowerShell in SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: f25f7549-c9b3-4618-85f2-c9a08adbe0e3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8c100e2eaf1f9b706087bd991fbc268540c29a46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627850"
---
# <a name="run-windows-powershell-steps-in-sql-server-agent"></a><span data-ttu-id="e8a85-102">Esecuzione di passaggi di Windows PowerShell in SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="e8a85-102">Run Windows PowerShell Steps in SQL Server Agent</span></span>
  <span data-ttu-id="e8a85-103">Utilizzare SQL Server Agent per eseguire script di SQL Server PowerShell a orari pianificati.</span><span class="sxs-lookup"><span data-stu-id="e8a85-103">Use SQL Server Agent to run SQL Server PowerShell scripts at schedule times.</span></span>  
  
1.  <span data-ttu-id="e8a85-104">**Prima di iniziare:**  [Limitazioni e restrizioni](#LimitationsRestrictions)</span><span class="sxs-lookup"><span data-stu-id="e8a85-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions)</span></span>  
  
2.  <span data-ttu-id="e8a85-105">**Per eseguire PowerShell da SQL Server Agent tramite:**  [passaggio del processo di PowerShell](#PShellJob), [passaggio del processo del prompt dei comandi](#CmdExecJob)</span><span class="sxs-lookup"><span data-stu-id="e8a85-105">**To run PowerShell from SQL Server Agent, using:**  [PowerShell Job Step](#PShellJob), [Command Prompt Job Step](#CmdExecJob)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="e8a85-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e8a85-106">Before You Begin</span></span>  
 <span data-ttu-id="e8a85-107">Sono disponibili molti tipi di passaggi del processo di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="e8a85-107">There are several types of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent job steps.</span></span> <span data-ttu-id="e8a85-108">Ogni tipo è associato a un sottosistema che implementa un ambiente specifico, ad esempio un agente di replica o un ambiente del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="e8a85-108">Each type is associated with a subsystem that implements a specific environment, such as a replication agent or command prompt environment.</span></span> <span data-ttu-id="e8a85-109">È possibile codificare gli script di Windows PowerShell, quindi utilizzare [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent per includere gli script nei processi eseguiti in base a orari pianificati o in risposta a eventi di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e8a85-109">You can code Windows PowerShell scripts, and then use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent to include the scripts in jobs that run at scheduled times or in response to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] events.</span></span> <span data-ttu-id="e8a85-110">È possibile eseguire gli script di Windows PowerShell con un passaggio del processo del prompt dei comandi o di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e8a85-110">Windows PowerShell scripts can be run using either a command prompt job step or a PowerShell job step.</span></span>  
  
1.  <span data-ttu-id="e8a85-111">Utilizzare un passaggio del processo di PowerShell per fare in modo che il sottosistema [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent esegua l'utilità `sqlps`, che avvia PowerShell 2.0 e importa il modulo `sqlps`.</span><span class="sxs-lookup"><span data-stu-id="e8a85-111">Use a PowerShell job step to have the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent subsystem run the `sqlps` utility, which launches PowerShell 2.0 and imports the `sqlps` module.</span></span>  
  
2.  <span data-ttu-id="e8a85-112">Utilizzare un passaggio del processo del prompt dei comandi per eseguire PowerShell.exe e specificare uno script che importa il modulo `sqlps`.</span><span class="sxs-lookup"><span data-stu-id="e8a85-112">Use a command prompt job step to run PowerShell.exe, and specify a script that imports the `sqlps` module.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="e8a85-113">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="e8a85-113">Limitations and Restrictions</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="e8a85-114">Ogni passaggio del processo di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent che esegue PowerShell con il modulo `sqlps` avvia un processo che utilizza all'incirca 20 MB di memoria.</span><span class="sxs-lookup"><span data-stu-id="e8a85-114">Each [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent job step that runs PowerShell with the `sqlps` module launches a process which consumes approximately 20 MB of memory.</span></span> <span data-ttu-id="e8a85-115">L'esecuzione simultanea di numerosi passaggi del processo di Windows PowerShell può avere un impatto negativo sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="e8a85-115">Running large numbers of concurrent Windows PowerShell job steps can adversely impact performance.</span></span>  
  
##  <a name="create-a-powershell-job-step"></a><a name="PShellJob"></a><span data-ttu-id="e8a85-116">Creazione di un passaggio del processo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8a85-116">Create a PowerShell Job Step</span></span>  
 <span data-ttu-id="e8a85-117">**Per creare un passaggio del processo di PowerShell**</span><span class="sxs-lookup"><span data-stu-id="e8a85-117">**To create a PowerShell job step**</span></span>  
  
1.  <span data-ttu-id="e8a85-118">Espandere **SQL Server Agent**, creare un nuovo processo oppure fare clic con il pulsante destro del mouse su un processo esistente e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="e8a85-118">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="e8a85-119">Per ulteriori informazioni sulla creazione di un processo, vedere [Creazione di processi](../ssms/agent/create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="e8a85-119">For more information about creating a job, see [Creating Jobs](../ssms/agent/create-jobs.md).</span></span>  
  
2.  <span data-ttu-id="e8a85-120">Nella finestra di dialogo **Proprietà processo** fare clic sulla pagina **Passaggi** e quindi su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e8a85-120">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
3.  <span data-ttu-id="e8a85-121">Nella finestra di dialogo **Nuovo passaggio di processo** digitare il nome del passaggio del processo nella casella **Nome passaggio**.</span><span class="sxs-lookup"><span data-stu-id="e8a85-121">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
4.  <span data-ttu-id="e8a85-122">Scegliere **PowerShell** dall'elenco **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="e8a85-122">In the **Type** list, click **PowerShell**.</span></span>  
  
5.  <span data-ttu-id="e8a85-123">Nell'elenco **Esegui come** selezionare l'account proxy con le credenziali che verranno utilizzate dal processo.</span><span class="sxs-lookup"><span data-stu-id="e8a85-123">In the **Run as** list, select the proxy account with the credentials that the job will use.</span></span>  
  
6.  <span data-ttu-id="e8a85-124">Nella casella **Comando** immettere la sintassi dello script di PowerShell che verrà eseguito per il passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="e8a85-124">In the **Command** box, enter the PowerShell script syntax that will be executed for the job step.</span></span> <span data-ttu-id="e8a85-125">In alternativa, è possibile fare clic su **Apri** e selezionare un file contenente la sintassi dello script.</span><span class="sxs-lookup"><span data-stu-id="e8a85-125">Alternately, click **Open** and select a file containing the script syntax.</span></span>  
  
7.  <span data-ttu-id="e8a85-126">Fare clic sulla pagina **Avanzate** per impostare le opzioni seguenti relative al passaggio di processo: l'azione da eseguire in caso di esito positivo o negativo del passaggio, il numero di tentativi di esecuzione del passaggio che devono essere effettuati da [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent e gli intervalli tra tentativi successivi.</span><span class="sxs-lookup"><span data-stu-id="e8a85-126">Click the **Advanced** page to set the following job step options: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should try to execute the job step, and how often retry attempts should be made.</span></span>  
  
##  <a name="create-a-command-prompt-job-step"></a><a name="CmdExecJob"></a><span data-ttu-id="e8a85-127">Creazione di un passaggio del processo del prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="e8a85-127">Create a Command Prompt Job Step</span></span>  
 <span data-ttu-id="e8a85-128">**Per creare un passaggio del processo di CmdExec**</span><span class="sxs-lookup"><span data-stu-id="e8a85-128">**To create a CmdExec job step**</span></span>  
  
1.  <span data-ttu-id="e8a85-129">Espandere **SQL Server Agent**, creare un nuovo processo oppure fare clic con il pulsante destro del mouse su un processo esistente e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="e8a85-129">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="e8a85-130">Per ulteriori informazioni sulla creazione di un processo, vedere [Creazione di processi](../ssms/agent/create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="e8a85-130">For more information about creating a job, see [Creating Jobs](../ssms/agent/create-jobs.md).</span></span>  
  
2.  <span data-ttu-id="e8a85-131">Nella finestra di dialogo **Proprietà processo** fare clic sulla pagina **Passaggi** e quindi su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e8a85-131">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
3.  <span data-ttu-id="e8a85-132">Nella finestra di dialogo **Nuovo passaggio di processo** digitare il nome del passaggio del processo nella casella **Nome passaggio**.</span><span class="sxs-lookup"><span data-stu-id="e8a85-132">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
4.  <span data-ttu-id="e8a85-133">Nell'elenco **Tipo** selezionare **Sistema operativo (CmdExec)**.</span><span class="sxs-lookup"><span data-stu-id="e8a85-133">In the **Type** list, choose **Operating system (CmdExec)**.</span></span>  
  
5.  <span data-ttu-id="e8a85-134">Nell'elenco **Esegui come** selezionare l'account proxy con le credenziali che verranno utilizzate dal processo.</span><span class="sxs-lookup"><span data-stu-id="e8a85-134">In **Run as** list, select the proxy account with the credentials that the job will use.</span></span> <span data-ttu-id="e8a85-135">Per impostazione predefinita, questi passaggi di processo vengono eseguiti nel contesto dell'account di servizio SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="e8a85-135">By default, CmdExec job steps run under the context of the SQL Server Agent service account.</span></span>  
  
6.  <span data-ttu-id="e8a85-136">Nella casella **Elabora codice di uscita di un comando eseguito correttamente** digitare un valore compreso tra 0 e 999999.</span><span class="sxs-lookup"><span data-stu-id="e8a85-136">In the **Process exit code of a successful command** box, enter a value from 0 to 999999.</span></span>  
  
7.  <span data-ttu-id="e8a85-137">Nella casella **Comando** , immettere powershell.exe con parametri che specificano lo script di PowerShell da eseguire.</span><span class="sxs-lookup"><span data-stu-id="e8a85-137">In the **Command** box, enter powershell.exe with parameters specifying the PowerShell script to be run.</span></span>  
  
8.  <span data-ttu-id="e8a85-138">Fare clic sulla pagina **Avanzate** per impostare le opzioni relative ai passaggi di processo, ad esempio l'operazione da eseguire se il passaggio di processo ha esito positivo o negativo, il numero di tentativi che devono essere eseguiti da [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent per l'esecuzione del passaggio di processo e il file in cui [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent può scrivere l'output del passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="e8a85-138">Click the **Advanced** page to set job step options, such as: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should try to execute the job step, and the file where [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent can write the job step output.</span></span> <span data-ttu-id="e8a85-139">L'output del passaggio di processo può essere scritto in un file di sistema unicamente dai membri del ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="e8a85-139">Only members of the **sysadmin** fixed server role can write job step output to an operating system file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8a85-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8a85-140">See Also</span></span>  
 [<span data-ttu-id="e8a85-141">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8a85-141">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
  
  
