---
title: 'Esercitazione: Preparazione del server per la replica | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: ce30a095-2975-4387-9377-94a461ac78ee
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e1f036ff2a111ee6b5f97655b9bebaf34391a436
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637742"
---
# <a name="tutorial-preparing-the-server-for-replication"></a><span data-ttu-id="55cc2-102">Esercitazione: Preparazione del server per la replica</span><span class="sxs-lookup"><span data-stu-id="55cc2-102">Tutorial: Preparing the Server for Replication</span></span>
  <span data-ttu-id="55cc2-103">È importante pianificare la sicurezza prima di configurare la topologia di replica.</span><span class="sxs-lookup"><span data-stu-id="55cc2-103">It is important to plan for security before you configure your replication topology.</span></span> <span data-ttu-id="55cc2-104">In questa esercitazione viene illustrato come proteggere la topologia di replica e come configurare la distribuzione, ovvero il primo passaggio nella replica dei dati.</span><span class="sxs-lookup"><span data-stu-id="55cc2-104">This tutorial shows you how to better secure a replication topology as well as how to configure distribution, which is the first step in replicating data.</span></span> <span data-ttu-id="55cc2-105">È necessario completare questa esercitazione prima delle altre esercitazioni sulla replica.</span><span class="sxs-lookup"><span data-stu-id="55cc2-105">You must complete this tutorial before any of the others.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="55cc2-106">Per eseguire in modo protetto la replica dei dati tra server, è consigliabile seguire le indicazioni riportate in [Procedure consigliate per la sicurezza della replica](security/replication-security-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="55cc2-106">To replicate data securely between servers, you should implement all of the recommendations in [Replication Security Best Practices](security/replication-security-best-practices.md).</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="55cc2-107">Lezioni dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="55cc2-107">What You Will Learn</span></span>  
 <span data-ttu-id="55cc2-108">In questa esercitazione verranno descritte le procedure per preparare i server in modo che la replica possa essere eseguita in modo protetto con privilegi minimi.</span><span class="sxs-lookup"><span data-stu-id="55cc2-108">In this tutorial you will learn how to prepare a server so that replication can run securely with least privileges.</span></span> <span data-ttu-id="55cc2-109">Nella prima lezione viene illustrato come creare gli account di servizio Windows utilizzati per l'esecuzione degli agenti di replica.</span><span class="sxs-lookup"><span data-stu-id="55cc2-109">The first lesson shows how to create the Windows service accounts used to run replication agents.</span></span> <span data-ttu-id="55cc2-110">Nella seconda lezione viene illustrato come configurare la cartella utilizzata per creare e archiviare gli snapshot di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="55cc2-110">The second lesson shows how to configure the folder used to generate and store publication snapshots.</span></span> <span data-ttu-id="55cc2-111">Nella terza lezione viene illustrato come configurare la distribuzione e impostare le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="55cc2-111">The third lesson shows how to configure distribution and set permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55cc2-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="55cc2-112">Requirements</span></span>  
 <span data-ttu-id="55cc2-113">Questa esercitazione è destinata agli utenti esperti nelle operazioni di database fondamentali ma con una limitata conoscenza della replica.</span><span class="sxs-lookup"><span data-stu-id="55cc2-113">This tutorial is intended for users familiar with fundamental database operations, but who have limited exposure to replication.</span></span>  
  
 <span data-ttu-id="55cc2-114">Per utilizzare l'esercitazione è necessario che nel sistema siano installati i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="55cc2-114">To use this tutorial, your system must have the following components installed:</span></span>  
  
-   [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] <span data-ttu-id="55cc2-115">con il database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="55cc2-115">with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="55cc2-116">Per una maggiore sicurezza, i database di esempio non vengono installati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="55cc2-116">To enhance security, the sample databases are not installed by default.</span></span>  
  
 <span data-ttu-id="55cc2-117">**Tempo stimato per il completamento di questa esercitazione: 30 minuti.**</span><span class="sxs-lookup"><span data-stu-id="55cc2-117">**Estimated time to complete this tutorial: 30 minutes.**</span></span>  
  
## <a name="lessons-in-this-tutorial"></a><span data-ttu-id="55cc2-118">Lezioni dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="55cc2-118">Lessons in This Tutorial</span></span>  
  
-   [<span data-ttu-id="55cc2-119">Lezione 1: Creazione di account di Windows per la replica</span><span class="sxs-lookup"><span data-stu-id="55cc2-119">Lesson 1: Creating Windows Accounts for Replication</span></span>](lesson-1-creating-windows-accounts-for-replication.md)  
  
-   [<span data-ttu-id="55cc2-120">Lezione 2: Preparazione della cartella snapshot</span><span class="sxs-lookup"><span data-stu-id="55cc2-120">Lesson 2: Preparing the Snapshot Folder</span></span>](lesson-2-preparing-the-snapshot-folder.md)  
  
-   [<span data-ttu-id="55cc2-121">Lezione 3: Configurazione della distribuzione</span><span class="sxs-lookup"><span data-stu-id="55cc2-121">Lesson 3: Configuring Distribution</span></span>](lesson-3-configuring-distribution.md)  
  
 [<span data-ttu-id="55cc2-122">Avviare l'esercitazione</span><span class="sxs-lookup"><span data-stu-id="55cc2-122">Start the Tutorial</span></span>](lesson-1-creating-windows-accounts-for-replication.md)  
  
## <a name="see-also"></a><span data-ttu-id="55cc2-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55cc2-123">See Also</span></span>  
 <span data-ttu-id="55cc2-124">[Configura distribuzione](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="55cc2-124">[Configure Distribution](configure-distribution.md) </span></span>  
 [<span data-ttu-id="55cc2-125">Sicurezza replica di SQL Server</span><span class="sxs-lookup"><span data-stu-id="55cc2-125">SQL Server Replication Security</span></span>](security/view-and-modify-replication-security-settings.md)  
  
  
