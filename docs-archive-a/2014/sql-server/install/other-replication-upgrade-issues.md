---
title: Altri problemi di aggiornamento della replica | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- system tables [SQL Server], replication
- passwords [SQL Server replication]
- versions [SQL Server replication]
- connections [SQL Server replication]
- scripts [SQL Server replication]
- ActiveX controls [SQL Server replication]
ms.assetid: 8a5e74be-4992-4f17-b20c-c3dce8f49329
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: e8ce3f35ead9d3322c636462f682ef391703cfe2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636533"
---
# <a name="other-replication-upgrade-issues"></a><span data-ttu-id="0c0cd-102">Altri problemi di aggiornamento della replica</span><span class="sxs-lookup"><span data-stu-id="0c0cd-102">Other Replication Upgrade Issues</span></span>
  <span data-ttu-id="0c0cd-103">In questo argomento vengono analizzati alcuni problemi relativi all'aggiornamento che non sono segnalati da Preparazione aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="0c0cd-103">This topic covers a number of upgrade issues that are not reported by Upgrade Advisor.</span></span>  
  
## <a name="versions-supported"></a><span data-ttu-id="0c0cd-104">Versioni supportate</span><span class="sxs-lookup"><span data-stu-id="0c0cd-104">Versions Supported</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="0c0cd-105">supporta l'aggiornamento di database replicati da versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c0cd-105">supports upgrading replicated databases from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0c0cd-106">Durante l'aggiornamento di un nodo, non è necessario arrestare l'attività eseguita su altri nodi.</span><span class="sxs-lookup"><span data-stu-id="0c0cd-106">You do not have to stop activity at other nodes while a node is being upgraded.</span></span> <span data-ttu-id="0c0cd-107">Verificare che vengano osservate le regole relative alle versioni supportate in una topologia.</span><span class="sxs-lookup"><span data-stu-id="0c0cd-107">Ensure that you adhere to the rules regarding which versions are supported in a topology.</span></span>  
  
 <span data-ttu-id="0c0cd-108">È possibile eseguire funzionalità di replica tra versioni diverse di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anche se tali funzionalità sono in genere limitate a quelle supportate dalla versione meno recente utilizzata.</span><span class="sxs-lookup"><span data-stu-id="0c0cd-108">When you replicate between or among different versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you are usually limited to the functionality of the earliest version that is being used.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0c0cd-109">Poiché in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] il formato di archiviazione su disco è lo stesso in ambienti a 64 bit e a 32 bit, in una topologia di replica possono essere presenti istanze del server eseguite in un ambiente a 32 bit e istanze del server eseguite in un ambiente a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="0c0cd-109">Because the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on-disk storage format is the same in the 64-bit and 32-bit environments, a replication topology can combine server instances that run in a 32-bit environment and server instances that run in a 64-bit environment.</span></span>  
  
 <span data-ttu-id="0c0cd-110">Per tutti i tipi di replica, la versione del server di distribuzione non deve essere precedente a quella del server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="0c0cd-110">For all types of replication, the Distributor version must be no earlier than the Publisher version.</span></span> <span data-ttu-id="0c0cd-111">In molti casi l'istanza del server di distribuzione è la stessa di quella del server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="0c0cd-111">(Frequently, the Distributor is the same instance as the Publisher.)</span></span>  
  
 <span data-ttu-id="0c0cd-112">In caso di replica transazionale, la versione di un Sottoscrittore di una pubblicazione transazionale è limitata a un intervallo di due versioni in base alla versione del server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="0c0cd-112">For transactional replication, a Subscriber to a transactional publication can be any version within two versions of the Publisher version.</span></span>  
  
 <span data-ttu-id="0c0cd-113">In caso di replica di tipo merge, è possibile utilizzare qualsiasi versione del Sottoscrittore di una pubblicazione di tipo merge, purché non sia successiva a quella del server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="0c0cd-113">For merge replication, a Subscriber to a merge publication can be any version no later than the Publisher version.</span></span>  
  
## <a name="merge-replication-batches-changes"></a><span data-ttu-id="0c0cd-114">Modifiche eseguite in batch della replica di tipo merge</span><span class="sxs-lookup"><span data-stu-id="0c0cd-114">Merge Replication Batches Changes</span></span>  
 <span data-ttu-id="0c0cd-115">Le modifiche apportate dall'agente di merge vengono eseguite in batch per migliorare le prestazioni. Di conseguenza, all'interno di una singola istruzione è possibile inserire, aggiornare o eliminare più righe.</span><span class="sxs-lookup"><span data-stu-id="0c0cd-115">Changes that are made by the Merge Agent are batched to improve performance; therefore, more than one row can be inserted, updated, or deleted within a single statement.</span></span> <span data-ttu-id="0c0cd-116">Se nei database di pubblicazione o di sottoscrizione sono presenti tabelle pubblicate che contengono trigger, verificare che i trigger siano in grado di gestire gli inserimenti, gli aggiornamenti e le eliminazioni di più righe.</span><span class="sxs-lookup"><span data-stu-id="0c0cd-116">If any published tables in the publication or subscription databases have triggers, ensure that the triggers can handle multirow inserts, updates, and deletes.</span></span> <span data-ttu-id="0c0cd-117">Per ulteriori informazioni, vedere "Considerazioni sulle istruzioni che interessano più righe per i trigger DML" nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c0cd-117">For more information, see "Multirow Considerations for DML Triggers" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="activex-control-changes"></a><span data-ttu-id="0c0cd-118">Modifiche ai controlli ActiveX</span><span class="sxs-lookup"><span data-stu-id="0c0cd-118">ActiveX Control Changes</span></span>  
 <span data-ttu-id="0c0cd-119">Ai controlli ActiveX della replica sono state apportate le seguenti modifiche:</span><span class="sxs-lookup"><span data-stu-id="0c0cd-119">The following changes have been made for replication ActiveX controls:</span></span>  
  
-   <span data-ttu-id="0c0cd-120">Tutti i controlli ActiveX sono contrassegnati come non sicuri per la generazione di script e l'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="0c0cd-120">All ActiveX controls are marked as unsafe for scripting and initialization.</span></span>  
  
-   <span data-ttu-id="0c0cd-121">Il controllo ActiveX snapshot è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="0c0cd-121">The Snapshot ActiveX control has been dropped.</span></span> <span data-ttu-id="0c0cd-122">È possibile creare e gestire snapshot utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oppure a livello di programmazione mediante stored procedure di replica.</span><span class="sxs-lookup"><span data-stu-id="0c0cd-122">You can create and manage snapshots by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or programmatically by using replication stored procedures.</span></span> <span data-ttu-id="0c0cd-123">Per ulteriori informazioni, vedere gli argomenti "Procedura: Creazione e applicazione dello snapshot iniziale ([!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)])" e "Procedura: Creazione dello snapshot iniziale (programmazione Transact-SQL della replica)" nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c0cd-123">For more information, see the topics "How to: Create and Apply the Initial Snapshot ([!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)])" and "How to: Create the Initial Snapshot (Replication Transact-SQL Programming)" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
-   <span data-ttu-id="0c0cd-124">I controlli ActiveX distribuzione e ActiveX merge sono stati deprecati.</span><span class="sxs-lookup"><span data-stu-id="0c0cd-124">The Distribution ActiveX control and Merge ActiveX control have been deprecated.</span></span> <span data-ttu-id="0c0cd-125">Una funzionalità analoga viene fornita per applicazioni del codice gestito da oggetti RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="0c0cd-125">Similar functionality is provided for managed code applications using Replication Management Objects (RMO).</span></span> <span data-ttu-id="0c0cd-126">Per ulteriori informazioni, vedere l'argomento relativo alla sincronizzazione delle sottoscrizioni (programmazione RMO) nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c0cd-126">For more information, see "Synchronizing Subscriptions (RMO Programming)" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c0cd-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c0cd-127">See Also</span></span>  
 [<span data-ttu-id="0c0cd-128">Problemi di aggiornamento della replica</span><span class="sxs-lookup"><span data-stu-id="0c0cd-128">Replication Upgrade Issues</span></span>](../../../2014/sql-server/install/replication-upgrade-issues.md)  
  
  
