---
title: 'Esercitazione: Replica di dati tra server con connessione continua Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- tutorials [SQL Server replication]
- replication [SQL Server], tutorials
- wizards [SQL Server replication]
ms.assetid: 7b18a04a-2c3d-4efe-a0bc-c3f92be72fd0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 415cac62112c1c1d2aa6c42ec189c2614ec03923
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637740"
---
# <a name="tutorial-replicating-data-between-continuously-connected-servers"></a><span data-ttu-id="4747e-102">Esercitazione: Replica di dati tra server con connessione continua</span><span class="sxs-lookup"><span data-stu-id="4747e-102">Tutorial: Replicating Data Between Continuously Connected Servers</span></span>
  <span data-ttu-id="4747e-103">La replica è una buona soluzione al problema legato al trasferimento dei dati tra server con connessione continua.</span><span class="sxs-lookup"><span data-stu-id="4747e-103">Replication is a good solution to the problem of moving data between continuously connected servers.</span></span> <span data-ttu-id="4747e-104">Le procedure guidate relative alla replica consentono di eseguire in modo semplificato i passaggi necessari per configurare e amministrare una topologia di replica.</span><span class="sxs-lookup"><span data-stu-id="4747e-104">Using replication's wizards, you can easily configure and administer a replication topology.</span></span> <span data-ttu-id="4747e-105">In questa esercitazione viene descritto come configurare una topologia di replica per server con connessione continua.</span><span class="sxs-lookup"><span data-stu-id="4747e-105">This tutorial shows you how to configure a replication topology for continuously connected servers.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="4747e-106">Lezioni dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="4747e-106">What You Will Learn</span></span>  
 <span data-ttu-id="4747e-107">In questa esercitazione viene descritto come pubblicare dati da un database all'altro mediante la replica transazionale.</span><span class="sxs-lookup"><span data-stu-id="4747e-107">This tutorial will show you how to publish data from one database to another using transactional replication.</span></span> <span data-ttu-id="4747e-108">Nella prima lezione verranno descritte le procedure per la creazione di una pubblicazione in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4747e-108">The first lesson shows how to use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to create a publication.</span></span> <span data-ttu-id="4747e-109">Nelle lezioni seguenti verranno descritte le procedure per creare e convalidare una sottoscrizione e per misurare la latenza.</span><span class="sxs-lookup"><span data-stu-id="4747e-109">Later lessons show how to create and validate a subscription and how to measure latency.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4747e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4747e-110">Requirements</span></span>  
 <span data-ttu-id="4747e-111">Questa esercitazione è destinata agli utenti esperti nelle operazioni di database di base ma con una limitata conoscenza della replica.</span><span class="sxs-lookup"><span data-stu-id="4747e-111">This tutorial is intended for users who are familiar with basic database operations, but who have limited experience with replication.</span></span> <span data-ttu-id="4747e-112">Per eseguire questa esercitazione è necessario avere completato l'esercitazione precedente [Preparazione del server per la replica](tutorial-preparing-the-server-for-replication.md).</span><span class="sxs-lookup"><span data-stu-id="4747e-112">This tutorial requires that you have completed the previous tutorial, [Preparing the Server for Replication](tutorial-preparing-the-server-for-replication.md).</span></span>  
  
 <span data-ttu-id="4747e-113">Per utilizzare l'esercitazione è necessario che nel sistema siano installati i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4747e-113">To use this tutorial, your system must have the following components:</span></span>  
  
-   <span data-ttu-id="4747e-114">Nel server di pubblicazione (origine):</span><span class="sxs-lookup"><span data-stu-id="4747e-114">At the Publisher server (source):</span></span>  
  
    -   <span data-ttu-id="4747e-115">Qualsiasi edizione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ad eccezione di Express ([!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]) o [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4747e-115">Any edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], except Express ([!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]) or [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> <span data-ttu-id="4747e-116">Questa edizioni non possono fungere da server di pubblicazione per la replica.</span><span class="sxs-lookup"><span data-stu-id="4747e-116">These editions cannot be replication Publishers.</span></span>  
  
    -   [!INCLUDE[ssSampleDBUserInputNonLocal](../../includes/sssampledbuserinputnonlocal-md.md)] <span data-ttu-id="4747e-117">database di esempio.</span><span class="sxs-lookup"><span data-stu-id="4747e-117">sample database.</span></span> <span data-ttu-id="4747e-118">Per una maggiore sicurezza, i database di esempio non vengono installati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4747e-118">To enhance security, the sample databases are not installed by default.</span></span>  
  
-   <span data-ttu-id="4747e-119">Sottoscrittore (destinazione):</span><span class="sxs-lookup"><span data-stu-id="4747e-119">Subscriber server (destination):</span></span>  
  
    -   <span data-ttu-id="4747e-120">Qualsiasi edizione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ad eccezione di [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4747e-120">Any edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], except [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> [!INCLUDE[ssEW](../../includes/ssew-md.md)] <span data-ttu-id="4747e-121">non può essere un Sottoscrittore nella replica transazionale.</span><span class="sxs-lookup"><span data-stu-id="4747e-121">cannot be a Subscriber in transactional replication.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4747e-122">Per impostazione predefinita la replica non è installata in [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4747e-122">Replication is not installed on [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] by default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4747e-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] è necessario connettersi al server di pubblicazione e al Sottoscrittore utilizzando un account di accesso membro del ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="4747e-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you must connect to the Publisher and Subscriber using a login that is a member of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="4747e-124">**Tempo stimato per il completamento di questa esercitazione: 30 minuti.**</span><span class="sxs-lookup"><span data-stu-id="4747e-124">**Estimated time to complete this tutorial: 30 minutes.**</span></span>  
  
## <a name="lessons-in-this-tutorial"></a><span data-ttu-id="4747e-125">Lezioni dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="4747e-125">Lessons in This Tutorial</span></span>  
  
-   [<span data-ttu-id="4747e-126">Lezione 1: Pubblicazione dei dati tramite la replica transazionale</span><span class="sxs-lookup"><span data-stu-id="4747e-126">Lesson 1: Publishing Data Using Transactional Replication</span></span>](lesson-1-publishing-data-using-transactional-replication.md)  
  
-   [<span data-ttu-id="4747e-127">Lezione 2: Creazione di una sottoscrizione per una pubblicazione transazionale</span><span class="sxs-lookup"><span data-stu-id="4747e-127">Lesson 2: Creating a Subscription to the Transactional Publication</span></span>](lesson-2-creating-a-subscription-to-the-transactional-publication.md)  
  
-   [<span data-ttu-id="4747e-128">Lezione 3: Convalida della sottoscrizione e misurazione della latenza</span><span class="sxs-lookup"><span data-stu-id="4747e-128">Lesson 3: Validating the Subscription and Measuring Latency</span></span>](lesson-3-validating-the-subscription-and-measuring-latency.md)  
  
 [<span data-ttu-id="4747e-129">Avviare l'esercitazione</span><span class="sxs-lookup"><span data-stu-id="4747e-129">Start the Tutorial</span></span>](transactional/transactional-replication.md)  
  
## <a name="see-also"></a><span data-ttu-id="4747e-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4747e-130">See Also</span></span>  
 [<span data-ttu-id="4747e-131">Concetti di base relativi alla programmazione della replica</span><span class="sxs-lookup"><span data-stu-id="4747e-131">Replication Programming Concepts</span></span>](concepts/replication-programming-concepts.md)  
  
  
