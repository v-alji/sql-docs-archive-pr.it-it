---
title: Usare il provider PowerShell per eventi estesi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- PowerShell [SQL Server], xevent
- extended events [SQL Server], PowerShell
- PowerShell [SQL Server], extended events
ms.assetid: 0b10016f-a479-4444-a484-46cb4677cf64
author: rothja
ms.author: jroth
ms.openlocfilehash: a9efbd389545dcde8285a38b06f41580fb65de6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629826"
---
# <a name="use-the-powershell-provider-for-extended-events"></a><span data-ttu-id="4e6f2-102">Utilizzare il provider PowerShell per eventi estesi</span><span class="sxs-lookup"><span data-stu-id="4e6f2-102">Use the PowerShell Provider for Extended Events</span></span>
  <span data-ttu-id="4e6f2-103">È possibile gestire eventi estesi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tramite il provider PowerShell per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4e6f2-103">You can manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Extended Events by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell provider.</span></span> <span data-ttu-id="4e6f2-104">La sottocartella XEvent è disponibile all'interno dell'unità SQLSERVER.</span><span class="sxs-lookup"><span data-stu-id="4e6f2-104">The XEvent subfolder is available under the SQLSERVER drive.</span></span> <span data-ttu-id="4e6f2-105">È possibile accedere alla cartella utilizzando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4e6f2-105">You can access the folder by using either of the following methods:</span></span>  
  
-   <span data-ttu-id="4e6f2-106">Al prompt dei comandi digitare `sqlps` e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="4e6f2-106">At a command prompt, type `sqlps`, and then press ENTER.</span></span> <span data-ttu-id="4e6f2-107">Digitare `cd xevent` e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="4e6f2-107">Type `cd xevent`, and then press ENTER.</span></span> <span data-ttu-id="4e6f2-108">Da qui è possibile usare il **CD** e i `dir` comandi (oppure i cmdlet **set-location** e **Get-ChildItem** ) per passare al nome del server e al nome dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="4e6f2-108">From there, you can use the **cd** and `dir` commands (or **Set-Location** and **Get-Childitem** cmdlets) to navigate to the server name and instance name.</span></span>  
  
-   <span data-ttu-id="4e6f2-109">In Esplora oggetti espandere il nome dell'istanza, espandere **Gestione**, fare clic con il pulsante destro del mouse su **Eventi estesi**, quindi scegliere **Avvia PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4e6f2-109">In Object Explorer, expand the instance name, expand **Management**, right-click **Extended Events**, and then click **Start PowerShell**.</span></span> <span data-ttu-id="4e6f2-110">Verrà avviato PowerShell nel percorso seguente:</span><span class="sxs-lookup"><span data-stu-id="4e6f2-110">This starts PowerShell in the following path:</span></span>  
  
     <span data-ttu-id="4e6f2-111">PS SqlServer: \ XEvent \\ *nomeserver* \\ *NomeIstanza*></span><span class="sxs-lookup"><span data-stu-id="4e6f2-111">PS SQLSERVER:\XEvent\\*ServerName*\\*InstanceName*></span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4e6f2-112">È possibile avviare PowerShell da qualsiasi nodo all'interno di **Eventi estesi**.</span><span class="sxs-lookup"><span data-stu-id="4e6f2-112">You can start PowerShell from any node under **Extended Events**.</span></span> <span data-ttu-id="4e6f2-113">È possibile, ad esempio, fare clic con il pulsante destro del mouse su **Sessioni**e quindi scegliere **Avvia PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4e6f2-113">For example, you can right-click **Sessions**, and then click **Start PowerShell**.</span></span> <span data-ttu-id="4e6f2-114">Verrà avviato PowerShell a un livello più interno, nella cartella Sessioni.</span><span class="sxs-lookup"><span data-stu-id="4e6f2-114">This starts PowerShell one level deeper, at the Sessions folder.</span></span>  
  
 <span data-ttu-id="4e6f2-115">È possibile esplorare l'albero delle cartelle XEvent per visualizzare sessioni di eventi estesi esistenti e i relativi eventi, database di destinazione e predicati associati.</span><span class="sxs-lookup"><span data-stu-id="4e6f2-115">You can browse the XEvent folder tree to view existing Extended Events sessions and their associated events, targets and predicates.</span></span> <span data-ttu-id="4e6f2-116">Ad esempio, dal percorso PS SqlServer: \ XEvent \\ *nomeserver* \\ *NomeIstanza*> digitare, `cd sessions` premere INVIO, digitare `dir` e quindi premere INVIO. è possibile visualizzare l'elenco delle sessioni archiviate in tale istanza.</span><span class="sxs-lookup"><span data-stu-id="4e6f2-116">For example, from the PS SQLSERVER:\XEvent\\*ServerName*\\*InstanceName*> path, if you type `cd sessions`, press ENTER, type `dir`, and then press ENTER, you can see the list of sessions that are stored on that instance.</span></span> <span data-ttu-id="4e6f2-117">È inoltre possibile visualizzare se la sessione è in esecuzione, e in tal caso per quanto tempo, e se la sessione è configurata per l'avvio all'avvio dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="4e6f2-117">You can also view whether the session is running (and if this is the case, for how long), and whether the session is configured to start when the instance starts.</span></span>  
  
 <span data-ttu-id="4e6f2-118">Per visualizzare gli eventi, i relativi predicati e i database di destinazione associati a una sessione, è possibile passare alla directory con il nome della sessione e quindi visualizzare la cartella degli eventi o dei database di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4e6f2-118">To view the events, their predictates, and the targets that are associated with a session, you can change directories to the session name, and then view either the events or targets folder.</span></span> <span data-ttu-id="4e6f2-119">Ad esempio, per visualizzare gli eventi e i relativi predicati associati alla sessione di integrità del sistema predefinita, dal percorso PS SqlServer: \ XEvent \\ *ServerName* \\ *NomeIstanza*\Sessions> digitare `cd system_health\events,` premi invio, digitare `dir` e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="4e6f2-119">For example, to view the events and their predicates that are associated with the default system health session, from the PS SQLSERVER:\XEvent\\*ServerName*\\*InstanceName*\Sessions> path, type `cd system_health\events,` press ENTER, type `dir`, and then press ENTER.</span></span>  
  
 <span data-ttu-id="4e6f2-120">Il provider PowerShell per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è uno strumento potente che consente di creare, modificare e gestire sessioni di eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="4e6f2-120">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell provider is a powerful tool that you can use to create, alter, and manage Extended Events sessions.</span></span> <span data-ttu-id="4e6f2-121">Nella sezione seguente vengono forniti alcuni esempi di base dell'utilizzo di script di PowerShell con eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="4e6f2-121">The following section provides some basic examples of using PowerShell scripts with Extended Events.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="4e6f2-122">Esempi</span><span class="sxs-lookup"><span data-stu-id="4e6f2-122">Examples</span></span>  
 <span data-ttu-id="4e6f2-123">Negli esempi seguenti notare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="4e6f2-123">In the following examples, note the following:</span></span>  
  
-   <span data-ttu-id="4e6f2-124">Gli script devono essere eseguiti dal prompt PS SQLSERVER: \\> (disponibile digitando `sqlps` al prompt dei comandi).</span><span class="sxs-lookup"><span data-stu-id="4e6f2-124">The scripts must be run from the PS SQLSERVER:\\> prompt (available by typing `sqlps` at a command prompt).</span></span>  
  
-   <span data-ttu-id="4e6f2-125">Gli script utilizzano l'istanza predefinita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e6f2-125">The scripts use the default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="4e6f2-126">È necessario salvare gli script con estensione ps1.</span><span class="sxs-lookup"><span data-stu-id="4e6f2-126">The scripts must be saved with a .ps1 extension.</span></span>  
  
-   <span data-ttu-id="4e6f2-127">I criteri di esecuzione di PowerShell devono consentire l'esecuzione dello script.</span><span class="sxs-lookup"><span data-stu-id="4e6f2-127">The PowerShell execution policy must allow the script to run.</span></span> <span data-ttu-id="4e6f2-128">Per impostare i criteri di esecuzione, usare il cmdlet **Set-Executionpolicy**</span><span class="sxs-lookup"><span data-stu-id="4e6f2-128">To set the execution policy, use the **Set-Executionpolicy** cmdlet.</span></span> <span data-ttu-id="4e6f2-129">(per altre informazioni, digitare `get-help set-executionpolicy -detailed`, quindi premere INVIO).</span><span class="sxs-lookup"><span data-stu-id="4e6f2-129">(For more information, type `get-help set-executionpolicy -detailed`, and then press ENTER.)</span></span>  
  
 <span data-ttu-id="4e6f2-130">Nello script seguente viene creata una nuova sessione denominata 'TestSession'.</span><span class="sxs-lookup"><span data-stu-id="4e6f2-130">The following script creates a new session that is named 'TestSession'.</span></span>  
  
```powershell
#Script for creating a session.  
cd XEvent  
$h = hostname  
cd $h  
  
#Use the default instance.  
$store = dir | where {$_.DisplayName -ieq 'default'}  
$session = New-Object Microsoft.SqlServer.Management.XEvent.Session -ArgumentList $store, "TestSession"  
$event = $session.AddEvent("sqlserver.file_written")  
$event.AddAction("package0.callstack")  
$session.Create()  
```  
  
 <span data-ttu-id="4e6f2-131">Nello script seguente viene aggiunta la destinazione del buffer circolare alla sessione creata nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="4e6f2-131">The following script adds the ring buffer target to the session that was created in the previous example.</span></span> <span data-ttu-id="4e6f2-132">In questo esempio si illustra l'utilizzo del metodo `Alter`.</span><span class="sxs-lookup"><span data-stu-id="4e6f2-132">(This example shows the use of the `Alter` method.</span></span> <span data-ttu-id="4e6f2-133">Tenere presente che è possibile aggiungere la destinazione quando si crea la sessione per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="4e6f2-133">Be aware that you can add the target when you first create the session.)</span></span>  
  
```powershell
#Script to alter a session.  
cd XEvent  
$h = hostname  
cd $h  
cd DEFAULT\Sessions  
  
#Used to find the specified session.  
$session = dir | where {$_.Name -eq 'TestSession'}  
  
#Add the ring buffer target and call the Alter method.  
$session.AddTarget("package0.ring_buffer")  
$session.Alter()  
```  
  
 <span data-ttu-id="4e6f2-134">Nello script seguente viene creata una nuova sessione in cui è utilizzata un'espressione di predicato.</span><span class="sxs-lookup"><span data-stu-id="4e6f2-134">The following script creates a new session that uses a predicate expression.</span></span> <span data-ttu-id="4e6f2-135">In questo caso la sessione raccoglie informazioni per il momento in cui verrà scritto il file c:\temp.log tramite l'evento sqlserver.file_written.</span><span class="sxs-lookup"><span data-stu-id="4e6f2-135">In this case, the session collects information for when the c:\temp.log file is written to (through the sqlserver.file_written event).</span></span>  
  
```powershell
#Script for creating a session.  
cd XEvent  
$h = hostname  
cd $h  
  
#Use the default instance.  
$store = dir | where {$_.DisplayName -ieq 'default'}  
$session = New-Object Microsoft.SqlServer.Management.XEvent.Session -ArgumentList $store, "TestSession2"  
$event = $session.AddEvent("sqlserver.file_written")  
  
#Construct a predicate "equal_i_unicode_string(path, N'c:\temp.log')".  
$column = $store.SqlServerPackage.EventInfoSet["file_written"].DataEventColumnInfoSet["path"]  
$operand = new-object Microsoft.SqlServer.Management.XEvent.PredOperand -argumentlist $column  
$value = new-object Microsoft.SqlServer.Management.XEvent.PredValue -argumentlist "c:\temp.log"  
$compare = $store.Package0Package.PredCompareInfoSet["equal_i_unicode_string"]  
$predicate = new-object Microsoft.SqlServer.Management.XEvent.PredFunctionExpr -ArgumentList $compare, $operand, $value  
$event.SetPredicate($predicate)  
$session.Create()  
```  
  
## <a name="security"></a><span data-ttu-id="4e6f2-136">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4e6f2-136">Security</span></span>  
 <span data-ttu-id="4e6f2-137">Per creare, modificare o eliminare una sessione di eventi estesi, è necessario disporre dell'autorizzazione ALTER ANY EVENT SESSION.</span><span class="sxs-lookup"><span data-stu-id="4e6f2-137">To create, alter, or drop an Extended Events session, you must have the ALTER ANY EVENT SESSION permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e6f2-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e6f2-138">See Also</span></span>  
 <span data-ttu-id="4e6f2-139">[SQL Server PowerShell](../../powershell/sql-server-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="4e6f2-139">[SQL Server PowerShell](../../powershell/sql-server-powershell.md) </span></span>  
 <span data-ttu-id="4e6f2-140">[Usare la sessione di system_health](use-the-ssms-xe-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="4e6f2-140">[Use the system_health Session](use-the-ssms-xe-profiler.md) </span></span>  
 [<span data-ttu-id="4e6f2-141">Strumenti degli eventi estesi</span><span class="sxs-lookup"><span data-stu-id="4e6f2-141">Extended Events Tools</span></span>](extended-events-tools.md)  
