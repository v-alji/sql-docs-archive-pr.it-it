---
title: Guida a Developer&#39;s (replica) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
helpviewer_keywords:
- developer's guide [SQL Server replication]
- programming [SQL Server replication]
- replication [SQL Server], development
ms.assetid: 7ee134ae-1cab-4a35-8017-8ac6d8fc64b6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d9651aec1f02d19ea3494abf242f75049a4f33f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721391"
---
# <a name="developer39s-guide-replication"></a><span data-ttu-id="305c9-102">Guida a Developer&#39;s (replica)</span><span class="sxs-lookup"><span data-stu-id="305c9-102">Developer&#39;s Guide (Replication)</span></span>
  <span data-ttu-id="305c9-103">La possibilità da configurare, gestire e monitorare a livello di codice una topologia di replica consente di semplificare le attività di replica ripetute e di migliorare l'esperienza utente per le applicazioni basate sulla replica.</span><span class="sxs-lookup"><span data-stu-id="305c9-103">The ability to programmatically configure, maintain, and monitor a replication topology enables you to both simplify repeated replication tasks and improve the user experience for your replication-based applications.</span></span> <span data-ttu-id="305c9-104">Mediante la programmazione della replica, è possibile offrire funzionalità di replica personalizzate agli utenti finali, senza che sia necessario conoscere le stored procedure di replica e i file eseguibili degli agenti di replica o utilizzare l'interfaccia di replica implementata da [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="305c9-104">By programming replication, your end-users can be provided with customized replication functionalities without having to be familiar with replication stored procedures and replication agent executables or having to using the replication user interface implemented by [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="305c9-105">Di seguito vengono descritti gli scenari in cui le applicazioni possono trarre vantaggio dall'accesso a livello di codice ai servizi di replica:</span><span class="sxs-lookup"><span data-stu-id="305c9-105">The following are scenarios in which your applications might benefit from programmatic access to replication services:</span></span>  
  
-   <span data-ttu-id="305c9-106">Aggiunta di funzionalità di replica a un'applicazione dell'utente finale esistente, ad esempio la sincronizzazione di una sottoscrizione pull quando l'utente fa clic su un pulsante.</span><span class="sxs-lookup"><span data-stu-id="305c9-106">Adding replication functionalities to an existing end-user application, such as synchronizing a pull subscription when the user clicks a button.</span></span>   
-   <span data-ttu-id="305c9-107">Creazione di un'interfaccia utente basata sul web per l'amministrazione remota della replica.</span><span class="sxs-lookup"><span data-stu-id="305c9-107">Creating a Web-based user interface for remotely administering replication.</span></span>    
-   <span data-ttu-id="305c9-108">Creazione di un'interfaccia utente personalizzata che esponga solo un subset delle funzionalità di amministrazione e che possa essere utilizzata per l'amministrazione remota di più topologie di replica da un solo percorso o che combini funzionalità di amministrazione e di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="305c9-108">Creating a custom user interface that exposes only a subset of administration functionality, can be used to remotely administer multiple replication topologies from a single location, or that combine administration and synchronization functionalities.</span></span>    
-   <span data-ttu-id="305c9-109">Miglioramento di uno strumento di monitoraggio esistente mediante l'aggiunta di funzionalità di controllo dello stato di una pubblicazione o di una sottoscrizione o presso il server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="305c9-109">Improving an existing monitoring tool by adding the ability to monitor the status of a publication, subscription, or at the Distributor.</span></span>    
-   <span data-ttu-id="305c9-110">Creazione di un'applicazione personalizzata per amministrare o sincronizzare sottoscrizioni di un server di pubblicazione Oracle.</span><span class="sxs-lookup"><span data-stu-id="305c9-110">Creating a custom application to administer or synchronize subscriptions to an Oracle publisher.</span></span>    
-   <span data-ttu-id="305c9-111">Scrittura di regole business personalizzate da eseguire alla sincronizzazione di una sottoscrizione di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="305c9-111">Writing customized business rules that are executed when a merge subscription is synchronized.</span></span>    
-   <span data-ttu-id="305c9-112">Generazione di script [!INCLUDE[tsql](../../../includes/tsql-md.md)] che possono essere eseguiti ripetutamente durante la configurazione di nuovi sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="305c9-112">Generating [!INCLUDE[tsql](../../../includes/tsql-md.md)] scripts that can be run repeated when configuring new Subscribers.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="305c9-113">consente di controllare a livello di codice gli agenti di replica e di amministrare e monitorare a livello di codice una topologia di replica.</span><span class="sxs-lookup"><span data-stu-id="305c9-113">enables you to programmatically control replication agents and to programmatically administer and monitor a replication topology.</span></span> <span data-ttu-id="305c9-114">Per altre informazioni sulla programmazione della replica, vedere [Concetti di base relativi alla programmazione della replica](replication-programming-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="305c9-114">To learn more about programming replication, see [Replication Programming Concepts](replication-programming-concepts.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="305c9-115">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="305c9-115">In This Section</span></span>  
 [<span data-ttu-id="305c9-116">Concetti di base relativi alla programmazione della replica</span><span class="sxs-lookup"><span data-stu-id="305c9-116">Replication Programming Concepts</span></span>](replication-programming-concepts.md)  
 <span data-ttu-id="305c9-117">Descrive i passaggi di pianificazione per lo sviluppo di un'applicazione che utilizza la replica.</span><span class="sxs-lookup"><span data-stu-id="305c9-117">Describes the planning steps to develop an application that uses replication.</span></span>  
  
 [<span data-ttu-id="305c9-118">Replication System Stored Procedures Concepts</span><span class="sxs-lookup"><span data-stu-id="305c9-118">Replication System Stored Procedures Concepts</span></span>](replication-system-stored-procedures-concepts.md)  
 <span data-ttu-id="305c9-119">Descrive come è possibile utilizzare stored procedure di sistema per fornire l'accesso a livello di codice in una topologia di replica.</span><span class="sxs-lookup"><span data-stu-id="305c9-119">Describes how system stored procedures can be used to proivide programmatic access in a replication topology.</span></span>  
  
 [<span data-ttu-id="305c9-120">Concetti di base relativi a RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="305c9-120">Replication Management Objects Concepts</span></span>](replication-management-objects-concepts.md)  
 <span data-ttu-id="305c9-121">Illustra i concetti di base per l'utilizzo di RMO (Replication Management Objects),</span><span class="sxs-lookup"><span data-stu-id="305c9-121">Explains the concepts for using Replication Management Objects (RMO).</span></span> <span data-ttu-id="305c9-122">ovvero un assembly di codice gestito che incapsula le funzionalità di replica per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="305c9-122">This is a managed code assembly that encapsulates replication functionalities for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="305c9-123">Replication Agent Executables Concepts</span><span class="sxs-lookup"><span data-stu-id="305c9-123">Replication Agent Executables Concepts</span></span>](replication-agent-executables-concepts.md)  
 <span data-ttu-id="305c9-124">Descrive l'utilizzo di file eseguibili dell'agente di replica.</span><span class="sxs-lookup"><span data-stu-id="305c9-124">Describes the use of Replication Agent Executable files.</span></span>  

  
  
