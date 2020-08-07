---
title: Registrare lo stato del processo nel registro applicazioni di Windows | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- status information [SQL Server], jobs
- SQL Server Agent jobs, status
- writing job status to log
- jobs [SQL Server Agent], status
- logs [SQL Server], jobs
ms.assetid: 3b813702-8f61-40ec-bf3b-ce9deb7e68be
author: stevestein
ms.author: sstein
ms.openlocfilehash: 67bdd7948d1722e49976d5e48b571c684431cd1c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719361"
---
# <a name="write-the-job-status-to-the-windows-application-log"></a><span data-ttu-id="cfb78-102">Registrare lo stato del processo nel registro applicazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="cfb78-102">Write the Job Status to the Windows Application Log</span></span>
  <span data-ttu-id="cfb78-103">In questo argomento viene descritto come configurare [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] per scrivere lo stato del processo nel registro eventi applicazioni di Windows utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] o SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="cfb78-103">This topic describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to write job status to the Windows application event log by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="cfb78-104">Tramite le risposte ai processi gli amministratori del database vengono informati in merito al completamento e alla frequenza di esecuzione dei processi.</span><span class="sxs-lookup"><span data-stu-id="cfb78-104">Job responses ensure that database administrators know when jobs complete and how frequently they run.</span></span> <span data-ttu-id="cfb78-105">Le risposte ai processi tipiche includono:</span><span class="sxs-lookup"><span data-stu-id="cfb78-105">Typical job responses include:</span></span>  
  
-   <span data-ttu-id="cfb78-106">Notifica all'operatore tramite posta elettronica, trasmissione di messaggi su cercapersone o messaggi **Net Send** .</span><span class="sxs-lookup"><span data-stu-id="cfb78-106">Notifying the operator by using e-mail, electronic paging, or a **net send** message.</span></span> <span data-ttu-id="cfb78-107">Usare uno di questi metodi di risposta al processo se l'operatore dovrà eseguire operazioni basate sull'esito.</span><span class="sxs-lookup"><span data-stu-id="cfb78-107">Use one of these job responses if the operator must perform a follow-up action.</span></span> <span data-ttu-id="cfb78-108">Ad esempio, se un processo di backup viene completato, l'operatore dovrà ricevere una notifica per rimuovere il nastro di backup e riporlo in un luogo sicuro.</span><span class="sxs-lookup"><span data-stu-id="cfb78-108">For example, if a backup job completes successfully, the operator must be notified to remove the backup tape and store it in a safe location.</span></span>  
  
-   <span data-ttu-id="cfb78-109">Scrittura di un messaggio di evento nel registro delle applicazioni di Windows.</span><span class="sxs-lookup"><span data-stu-id="cfb78-109">Writing an event message to the Windows application log.</span></span> <span data-ttu-id="cfb78-110">Questa risposta può essere usata esclusivamente per i processi non riusciti.</span><span class="sxs-lookup"><span data-stu-id="cfb78-110">You can use this response only for failed jobs.</span></span>  
  
-   <span data-ttu-id="cfb78-111">Eliminazione automatica del processo.</span><span class="sxs-lookup"><span data-stu-id="cfb78-111">Automatically deleting the job.</span></span> <span data-ttu-id="cfb78-112">Usare la risposta soltanto se si è certi che non sarà necessario rieseguire il processo.</span><span class="sxs-lookup"><span data-stu-id="cfb78-112">Use this job response if you are certain that you do not need to rerun this job.</span></span>  
  
 <span data-ttu-id="cfb78-113">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="cfb78-113">**In This Topic**</span></span>  
  
-   <span data-ttu-id="cfb78-114">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="cfb78-114">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="cfb78-115">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="cfb78-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="cfb78-116">**Per scrivere lo stato del processo nel registro applicazioni di Windows usando:**</span><span class="sxs-lookup"><span data-stu-id="cfb78-116">**To write the job status to the Windows application log, using:**</span></span>  
  
     [<span data-ttu-id="cfb78-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cfb78-117">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="cfb78-118">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="cfb78-118">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cfb78-119">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="cfb78-119">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cfb78-120">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="cfb78-120">Security</span></span>  
 <span data-ttu-id="cfb78-121">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="cfb78-121">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="cfb78-122">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cfb78-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-write-job-status-to-the-windows-application-log"></a><span data-ttu-id="cfb78-123">Per registrare lo stato del processo nel registro applicazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="cfb78-123">To write job status to the Windows application log</span></span>  
  
1.  <span data-ttu-id="cfb78-124">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="cfb78-124">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="cfb78-125">Espandere **SQL Server Agent**, espandere **Processi**, fare clic con il pulsante destro del mouse sul processo da modificare e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="cfb78-125">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="cfb78-126">Scegliere la pagina **Notifiche** .</span><span class="sxs-lookup"><span data-stu-id="cfb78-126">Select the **Notifications** page.</span></span>  
  
4.  <span data-ttu-id="cfb78-127">Selezionare l'opzione **Scrivi nel registro eventi delle applicazioni di Windows**e quindi scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cfb78-127">Check **Write to Windows application event log**, and choose one of the following:</span></span>  
  
    -   <span data-ttu-id="cfb78-128">Fare clic su**In caso di esito positivo processo**per registrare lo stato del processo quando questo viene completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="cfb78-128">Click**When the job succeeds**to log the job status when the job completes successfully.</span></span>  
  
    -   <span data-ttu-id="cfb78-129">Fare clic su**In caso di esito negativo processo**per registrare lo stato del processo quando questo non viene completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="cfb78-129">Click**When the job fails**to log the job status when the job completes unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="cfb78-130">Fare clic su**Al termine del processo** per registrare lo stato del processo indipendentemente dal suo completamento.</span><span class="sxs-lookup"><span data-stu-id="cfb78-130">Click**When the job completes** to log the job status regardless of completion status.</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="cfb78-131">Utilizzo di SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="cfb78-131">Using SQL Server Management Objects</span></span>  

### <a name="to-write-job-status-to-the-windows-application-log"></a><span data-ttu-id="cfb78-132">Per registrare lo stato del processo nel registro applicazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="cfb78-132">To write job status to the Windows application log</span></span>
  
 <span data-ttu-id="cfb78-133">Chiamare la proprietà `EventLogLevel` della classe `Job` tramite un linguaggio di programmazione come Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cfb78-133">Call the `EventLogLevel` property of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
  
 <span data-ttu-id="cfb78-134">Nell'esempio di codice seguente il processo viene impostato per generare una voce nel registro eventi del sistema operativo al termine dell'esecuzione del processo.</span><span class="sxs-lookup"><span data-stu-id="cfb78-134">The following code example sets the job to generate an operating system event log entry when the job execution finishes.</span></span>  
  
```powershell
$srv = new-object Microsoft.SqlServer.Management.Smo.Server("(local)")  
$jb = new-object Microsoft.SqlServer.Management.Smo.Agent.Job($srv.JobServer, "Test Job")  
$jb.EventLogLevel = [Microsoft.SqlServer.Management.Smo.Agent.CompletionAction]::Always  
```  
