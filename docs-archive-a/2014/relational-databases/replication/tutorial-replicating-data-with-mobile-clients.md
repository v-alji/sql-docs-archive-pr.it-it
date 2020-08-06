---
title: 'Esercitazione: Replica di dati con client mobili | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: af673514-30c7-403a-9d18-d01e1a095115
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2cdf8be7cb0da11f0aa1022ba656d50c10826ad2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637738"
---
# <a name="tutorial-replicating-data-with-mobile-clients"></a><span data-ttu-id="54baa-102">Esercitazione: Replica di dati con client mobili</span><span class="sxs-lookup"><span data-stu-id="54baa-102">Tutorial: Replicating Data with Mobile Clients</span></span>
  <span data-ttu-id="54baa-103">La replica è una buona soluzione al problema legato al trasferimento dei dati tra un server centrale e client mobili connessi solo occasionalmente.</span><span class="sxs-lookup"><span data-stu-id="54baa-103">Replication is a good solution to the problem of moving data between a central server and mobile clients that are only occasionally connected.</span></span> <span data-ttu-id="54baa-104">Le procedure guidate relative alla replica consentono di eseguire in modo semplificato i passaggi necessari per configurare e amministrare una topologia di replica.</span><span class="sxs-lookup"><span data-stu-id="54baa-104">Using replication's wizards, you can easily configure and administer a replication topology.</span></span> <span data-ttu-id="54baa-105">In questa esercitazione viene illustrato come configurare una topologia di replica per client mobili.</span><span class="sxs-lookup"><span data-stu-id="54baa-105">This tutorial shows you how to configure a replication topology for mobile clients.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="54baa-106">Lezioni dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="54baa-106">What You Will Learn</span></span>  
 <span data-ttu-id="54baa-107">In questa esercitazione verrà utilizzata la replica di tipo merge per pubblicare i dati da un database centrale in uno o più client mobili in modo che ogni utente disponga di un subset di dati filtrato in modo univoco.</span><span class="sxs-lookup"><span data-stu-id="54baa-107">In this tutorial you will use merge replication to publish data from a central database to one or more mobile users so that each user gets a uniquely filtered subset of the data.</span></span> <span data-ttu-id="54baa-108">Nella prima lezione verranno descritte le procedure per la creazione di una pubblicazione in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="54baa-108">The first lesson shows how to use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to create a publication.</span></span> <span data-ttu-id="54baa-109">Nelle lezioni successive verranno descritte le procedure per creare e sincronizzare una sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="54baa-109">Later lessons show how to create and synchronize a subscription.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54baa-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="54baa-110">Requirements</span></span>  
 <span data-ttu-id="54baa-111">Questa esercitazione è destinata agli utenti esperti nelle operazioni di database fondamentali ma con una limitata conoscenza della replica.</span><span class="sxs-lookup"><span data-stu-id="54baa-111">This tutorial is intended for users familiar with fundamental database operations, but who have limited experience with replication.</span></span> <span data-ttu-id="54baa-112">Prima di iniziare questa esercitazione, è necessario completare [l'esercitazione: preparazione del server per la replica](tutorial-preparing-the-server-for-replication.md).</span><span class="sxs-lookup"><span data-stu-id="54baa-112">Before you start this tutorial, you must complete [Tutorial: Preparing the Server for Replication](tutorial-preparing-the-server-for-replication.md).</span></span>  
  
 <span data-ttu-id="54baa-113">Per utilizzare l'esercitazione è necessario che nel sistema siano installati i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="54baa-113">To use this tutorial, your system must have the following components installed:</span></span>  
  
-   <span data-ttu-id="54baa-114">Nel server di pubblicazione (origine):</span><span class="sxs-lookup"><span data-stu-id="54baa-114">At the Publisher server (source):</span></span>  
  
    -   <span data-ttu-id="54baa-115">Qualsiasi edizione di [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], ad eccezione di Express ([!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]) o [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54baa-115">Any edition of [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], except for Express ([!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]) or [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> <span data-ttu-id="54baa-116">Queste edizioni non possono fungere da server di pubblicazione per la replica.</span><span class="sxs-lookup"><span data-stu-id="54baa-116">These editions cannot be a replication Publisher.</span></span>  
  
    -   <span data-ttu-id="54baa-117">Database di esempio [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="54baa-117">The [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="54baa-118">Per una maggiore sicurezza, i database di esempio non vengono installati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="54baa-118">To enhance security, the sample databases are not installed by default.</span></span>  
  
-   <span data-ttu-id="54baa-119">Sottoscrittore (destinazione):</span><span class="sxs-lookup"><span data-stu-id="54baa-119">Subscriber server (destination):</span></span>  
  
    -   <span data-ttu-id="54baa-120">Qualsiasi edizione di [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], ad eccezione di [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54baa-120">Any edition of [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], except for [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> [!INCLUDE[ssEW](../../includes/ssew-md.md)] <span data-ttu-id="54baa-121">non è supportato dalla pubblicazione creata in questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="54baa-121">is not supported by the publication created in this tutorial.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="54baa-122">La replica non è installata per impostazione predefinita in [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54baa-122">Replication is not installed by default on [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="54baa-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]è necessario connettersi al server di pubblicazione e al Sottoscrittore mediante un account di accesso che sia membro del ruolo predefinito del server sysadmin.</span><span class="sxs-lookup"><span data-stu-id="54baa-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you must connect to the Publisher and Subscriber using a login that is a member of the sysadmin fixed server role.</span></span>  
  
 <span data-ttu-id="54baa-124">**Tempo stimato per il completamento di questa esercitazione: 30 minuti.**</span><span class="sxs-lookup"><span data-stu-id="54baa-124">**Estimated time to complete this tutorial: 30 minutes.**</span></span>  
  
## <a name="lessons-in-this-tutorial"></a><span data-ttu-id="54baa-125">Lezioni dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="54baa-125">Lessons in This Tutorial</span></span>  
  
-   [<span data-ttu-id="54baa-126">Lezione 1: Pubblicazione dei dati tramite la replica di tipo merge</span><span class="sxs-lookup"><span data-stu-id="54baa-126">Lesson 1: Publishing Data Using Merge Replication</span></span>](lesson-1-publishing-data-using-merge-replication.md)  
  
-   [<span data-ttu-id="54baa-127">Lezione 2: Creazione di una sottoscrizione per una pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="54baa-127">Lesson 2: Creating a Subscription to the Merge Publication</span></span>](lesson-2-creating-a-subscription-to-the-merge-publication.md)  
  
 [<span data-ttu-id="54baa-128">Avviare l'esercitazione</span><span class="sxs-lookup"><span data-stu-id="54baa-128">Start the Tutorial</span></span>](merge/merge-replication.md)  
  
## <a name="see-also"></a><span data-ttu-id="54baa-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54baa-129">See Also</span></span>  
 [<span data-ttu-id="54baa-130">Concetti di base relativi alla programmazione della replica</span><span class="sxs-lookup"><span data-stu-id="54baa-130">Replication Programming Concepts</span></span>](concepts/replication-programming-concepts.md)  
  
  
