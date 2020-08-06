---
title: Concetti di base relativi ai file eseguibili dell'agente di replica | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
helpviewer_keywords:
- programming interfaces [SQL Server replication]
- programming [SQL Server replication], agents
- replication [SQL Server], agents and profiles
- agents [SQL Server replication], executables
- command prompt [SQL Server replication]
ms.assetid: cba476df-d4ea-44c9-bb86-81488971e328
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 73f9fe0d1a98fa1afc813cd113dcced685b4f98a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725535"
---
# <a name="replication-agent-executables-concepts"></a><span data-ttu-id="a45fe-102">Concetti di base relativi ai file eseguibili dell'agente di replica</span><span class="sxs-lookup"><span data-stu-id="a45fe-102">Replication Agent Executables Concepts</span></span>
  <span data-ttu-id="a45fe-103">Gli agenti di replica possono essere controllati a livello di codice nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a45fe-103">Replication agents can be controlled programmatically in the following ways:</span></span>  
  
-   <span data-ttu-id="a45fe-104">Utilizzo delle interfacce di programmazione gestite dell'agente nello spazio dei nomi <xref:Microsoft.SqlServer.Replication>.</span><span class="sxs-lookup"><span data-stu-id="a45fe-104">Using the managed agent programming interfaces in the <xref:Microsoft.SqlServer.Replication> Namespace.</span></span>  
  
-   <span data-ttu-id="a45fe-105">Richiamo dei file eseguibili dell'agente dal prompt dei comandi con un set di parametri fornito.</span><span class="sxs-lookup"><span data-stu-id="a45fe-105">Invoking agent executable files from the command prompt with a supplied set of parameters.</span></span>  
  
 <span data-ttu-id="a45fe-106">Il richiamo diretto degli agenti di replica dal prompt dei comandi consente l'accesso a livello di codice agli agenti da script della riga di comando inclusi in file batch.</span><span class="sxs-lookup"><span data-stu-id="a45fe-106">Directly invoking replication agents from the command prompt enables agents to be programmatically accessed from command-line scripting in batch files.</span></span> <span data-ttu-id="a45fe-107">Quando viene richiamato dal prompt dei comandi, l'agente viene eseguito con l'account di sicurezza di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] dell'utente che ha richiamato l'agente o avviato il file batch.</span><span class="sxs-lookup"><span data-stu-id="a45fe-107">When an agent is invoked from the command prompt, it runs under the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows security account of the user that invoked the agent or started the batch file.</span></span>  
  
 <span data-ttu-id="a45fe-108">Le istanze degli agenti di replica seguenti possono essere eseguite utilizzando file eseguibili.</span><span class="sxs-lookup"><span data-stu-id="a45fe-108">Instances of the following replication agents can be run using executable files.</span></span>  
  
-   [<span data-ttu-id="a45fe-109">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="a45fe-109">Replication Distribution Agent</span></span>](../agents/replication-distribution-agent.md)  
  
-   [<span data-ttu-id="a45fe-110">Agente lettura log repliche</span><span class="sxs-lookup"><span data-stu-id="a45fe-110">Replication Log Reader Agent</span></span>](../agents/replication-log-reader-agent.md)  
  
-   [<span data-ttu-id="a45fe-111">Replication Merge Agent</span><span class="sxs-lookup"><span data-stu-id="a45fe-111">Replication Merge Agent</span></span>](../agents/replication-merge-agent.md)  
  
-   [<span data-ttu-id="a45fe-112">Agente di lettura coda repliche</span><span class="sxs-lookup"><span data-stu-id="a45fe-112">Replication Queue Reader Agent</span></span>](../agents/replication-queue-reader-agent.md)  
  
-   [<span data-ttu-id="a45fe-113">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="a45fe-113">Replication Snapshot Agent</span></span>](../agents/replication-snapshot-agent.md)  
  
 <span data-ttu-id="a45fe-114">Quando si richiamano gli agenti di replica, è possibile utilizzare profili di prestazioni per passare automaticamente un set di parametri definito al file eseguibile dell'agente.</span><span class="sxs-lookup"><span data-stu-id="a45fe-114">When invoking replication agents, you can use performance profiles to automatically pass a defined set of parameters to the agent executable.</span></span> <span data-ttu-id="a45fe-115">Per altre informazioni, vedere [Replication Agent Profiles](../agents/replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a45fe-115">For more information, see [Replication Agent Profiles](../agents/replication-agent-profiles.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="a45fe-116">Esempi</span><span class="sxs-lookup"><span data-stu-id="a45fe-116">Examples</span></span>  
 <span data-ttu-id="a45fe-117">Negli esempi seguenti viene illustrato come richiamare gli agenti di replica dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="a45fe-117">The following examples show how to invoke replication agents from the command prompt.</span></span> <span data-ttu-id="a45fe-118">Gli agenti di replica possono inoltre essere richiamati utilizzando RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="a45fe-118">Replication agents can also be invoked using Replication Management Objects (RMO).</span></span> <span data-ttu-id="a45fe-119">Per altre informazioni, vedere [Sincronizzare le sottoscrizioni &#40;replica&#41;](../synchronize-data.md).</span><span class="sxs-lookup"><span data-stu-id="a45fe-119">For more information, see [Synchronize Subscriptions &#40;Replication&#41;](../synchronize-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a45fe-120">Le interruzioni di riga presenti negli esempi sono state aggiunte per facilitare la lettura.</span><span class="sxs-lookup"><span data-stu-id="a45fe-120">Line breaks in these examples were added to improve readability.</span></span> <span data-ttu-id="a45fe-121">I comandi in un file batch devono essere inseriti in un'unica riga.</span><span class="sxs-lookup"><span data-stu-id="a45fe-121">In a batch file, commands must be made in a single line.</span></span>  
  
### <a name="running-the-snapshot-agent"></a><span data-ttu-id="a45fe-122">Esecuzione dell'agente snapshot</span><span class="sxs-lookup"><span data-stu-id="a45fe-122">Running the Snapshot Agent</span></span>  
 <span data-ttu-id="a45fe-123">Questo file batch di esempio richiama l'agente snapshot dal prompt dei comandi per generare uno snapshot per la pubblicazione **AdvWorksSalesOrdersMerge**.</span><span class="sxs-lookup"><span data-stu-id="a45fe-123">This example batch file invokes the Snapshot Agent from the command prompt to generate a snapshot for the **AdvWorksSalesOrdersMerge** publication.</span></span>  
  
```  
REM -- Declare variables  
SET Publisher=%InstanceName%;  
SET PublicationDB=AdventureWorks2012;   
SET Publication=AdvWorksSalesOrdersMerge;   
  
REM --Start the Snapshot Agent to generate the snapshot for AdvWorksSalesOrdersMerge.  
"C:\Program Files\Microsoft SQL Server\120\COM\SNAPSHOT.EXE" -Publication %Publication%   
-Publisher %Publisher% -Distributor %Publisher% -PublisherDB %PublicationDB%   
-ReplicationType 2 -OutputVerboseLevel 1 -DistributorSecurityMode 1 ;  
  
```  
  
### <a name="running-the-distribution-agent"></a><span data-ttu-id="a45fe-124">Esecuzione dell'agente di distribuzione</span><span class="sxs-lookup"><span data-stu-id="a45fe-124">Running the Distribution Agent</span></span>  
 <span data-ttu-id="a45fe-125">Questo file batch di esempio richiama l'agente di distribuzione dal prompt dei comandi per replicare continuamente le modifiche dalla pubblicazione **AdvWorksProductTran** in un server di sottoscrizione push.</span><span class="sxs-lookup"><span data-stu-id="a45fe-125">This example batch file invokes the Distribution Agent from the command prompt to continuously replicate changes from the **AdvWorksProductTran** publication to a push subscriber.</span></span>  
  
```  
REM -- Declare the variables.  
SET Publisher=%instancename%;  
SET Subscriber=%instancename%;  
SET PublicationDB=AdventureWorks2012;  
SET SubscriptionDB=AdventureWorks2012Replica;   
SET Publication=AdvWorksProductsTran;  
  
REM -- Start the Distribution Agent with four subscription streams.  
REM -- The following command must be supplied without line breaks.  
"C:\Program Files\Microsoft SQL Server\120\COM\DISTRIB.EXE" -Subscriber %Subscriber%   
-SubscriberDB %SubscriptionDB% -SubscriberSecurityMode 1 -Publication %Publication%   
-Publisher %Publisher% -PublisherDB %PublicationDB% -Distributor %Publisher%   
-DistributorSecurityMode 1 -Continuous -SubscriptionType 0 -SubscriptionStreams 4 ;  
  
```  
  
### <a name="running-the-merge-agent"></a><span data-ttu-id="a45fe-126">Esecuzione dell'agente di merge</span><span class="sxs-lookup"><span data-stu-id="a45fe-126">Running the Merge Agent</span></span>  
 <span data-ttu-id="a45fe-127">Questo file batch di esempio richiama l'agente di merge dal prompt dei comandi per sincronizzare una sottoscrizione pull con la pubblicazione **AdvWorksSalesOrdersMerge**.</span><span class="sxs-lookup"><span data-stu-id="a45fe-127">This example batch file invokes the Merge Agent from the command prompt to synchronize a pull subscription to the **AdvWorksSalesOrdersMerge** publication.</span></span>  
  
```  
REM -- Declare the variables.  
SET Publisher=%instancename%;  
SET Subscriber=%instancename%;  
SET PublicationDB=AdventureWorks2012;  
SET SubscriptionDB=AdventureWorks2012Replica;   
SET Publication=AdvWorksSalesOrdersMerge;  
  
REM --Start the Merge Agent with concurrent upload and download processes.  
REM -- The following command must be supplied without line breaks.  
"C:\Program Files\Microsoft SQL Server\120\COM\REPLMERG.EXE" -Publication %Publication%    
-Publisher %Publisher%  -Subscriber  %Subscriber%  -Distributor %Publisher%    
-PublisherDB %PublicationDB%  -SubscriberDB %SubscriptionDB% -PublisherSecurityMode 1    
-OutputVerboseLevel 2  -SubscriberSecurityMode 1  -SubscriptionType 1 -DistributorSecurityMode 1    
-Validate 3  -ParallelUploadDownload 1 ;  
  
```  
  
  
