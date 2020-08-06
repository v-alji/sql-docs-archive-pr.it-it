---
title: Servizio Writer SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- VDI [SQL Server]
- restoring [SQL Server], SQL Writer Service
- backups [SQL Server], while SQL Server running
- Volume Shadow Copy Service
- volume backups while running [SQL Server]
- Virtual Backup Device Interface [SQL Server]
- SQL Writer Service
- services [SQL Server], SQL Writer
- MSDE Writer
- VSS
ms.assetid: 0f299867-f499-4c2a-ad6f-b2ef1869381d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 310722c6617c7a2c9e0f384ec23ae371ab230536
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624340"
---
# <a name="sql-writer-service"></a><span data-ttu-id="5af26-102">servizio writer SQL</span><span class="sxs-lookup"><span data-stu-id="5af26-102">SQL Writer Service</span></span>
  <span data-ttu-id="5af26-103">Il servizio writer SQL offre funzionalità aggiuntive per il backup e il ripristino di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tramite l'infrastruttura del Servizio Copia Shadow del volume.</span><span class="sxs-lookup"><span data-stu-id="5af26-103">The SQL Writer Service provides added functionality for backup and restore of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] through the Volume Shadow Copy Service framework.</span></span>  
  
 <span data-ttu-id="5af26-104">Il servizio SQL Writer viene installato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5af26-104">The SQL Writer Service is installed automatically.</span></span> <span data-ttu-id="5af26-105">Il servizio deve essere in esecuzione quando l'applicazione del servizio Copia Shadow del volume (VSS) richiede un backup o un ripristino.</span><span class="sxs-lookup"><span data-stu-id="5af26-105">It must be running when the Volume Shadow Copy Service (VSS) application requests a backup or restore.</span></span> <span data-ttu-id="5af26-106">Per configurare il servizio, utilizzare l'applet Servizi [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="5af26-106">To configure the service, use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Services applet.</span></span> <span data-ttu-id="5af26-107">Il servizio writer SQL viene installato in tutti i sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="5af26-107">The SQL Writer Service installs on all operating systems.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="5af26-108">Scopo</span><span class="sxs-lookup"><span data-stu-id="5af26-108">Purpose</span></span>  
 <span data-ttu-id="5af26-109">Durante l'esecuzione, il [!INCLUDE[ssDE](../../includes/ssde-md.md)] viene bloccato e dispone dell'accesso esclusivo ai file di dati.</span><span class="sxs-lookup"><span data-stu-id="5af26-109">When running, [!INCLUDE[ssDE](../../includes/ssde-md.md)] locks and has exclusive access to the data files.</span></span> <span data-ttu-id="5af26-110">Quando il servizio writer SQL non è in esecuzione, i programmi di backup in esecuzione in Windows non dispongono di accesso ai file di dati e per creare backup è necessario utilizzare il backup di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5af26-110">When the SQL Writer Service is not running, backup programs running in Windows do not have access to the data files, and backups must be performed using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup.</span></span>  
  
 <span data-ttu-id="5af26-111">Utilizzare il servizio writer SQL per consentire ai programmi di backup di Windows di copiare i file di dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] durante l'esecuzione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5af26-111">Use the SQL Writer Service to permit Windows backup programs to copy [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data files while [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span>  
  
## <a name="volume-shadow-copy-service"></a><span data-ttu-id="5af26-112">Servizio Copia Shadow del volume</span><span class="sxs-lookup"><span data-stu-id="5af26-112">Volume Shadow Copy Service</span></span>  
 <span data-ttu-id="5af26-113">Il Servizio Copia Shadow del volume (VSS) è costituito da un set di API COM che implementa un'infrastruttura per consentire l'esecuzione di backup dei volumi mentre le applicazioni in un sistema continuano a scrivere nei volumi.</span><span class="sxs-lookup"><span data-stu-id="5af26-113">The VSS is a set of COM APIs that implements a framework to allow volume backups to be performed while applications on a system continue to write to the volumes.</span></span> <span data-ttu-id="5af26-114">Tale servizio offre un'interfaccia uniforme, che consente la coordinazione tra le applicazioni utente per l'aggiornamento di dati sul disco, ovvero i writer, e quelle per il backup delle applicazioni, ovvero i richiedenti.</span><span class="sxs-lookup"><span data-stu-id="5af26-114">The VSS provides a consistent interface that allows coordination between user applications that update data on disk (writers) and those that back up applications (requestors).</span></span>  
  
 <span data-ttu-id="5af26-115">Il Servizio Copia Shadow del volume acquisisce e copia immagini stabili per il backup nei sistemi in esecuzione, in particolare nei server, senza ridurre inutilmente le prestazioni e la stabilità dei servizi offerti.</span><span class="sxs-lookup"><span data-stu-id="5af26-115">The VSS captures and copies stable images for backup on running systems, particularly servers, without unduly degrading the performance and stability of the services they provide.</span></span> <span data-ttu-id="5af26-116">Per ulteriori informazioni, vedere la documentazione del Servizio Copia Shadow del volume.</span><span class="sxs-lookup"><span data-stu-id="5af26-116">For more information on the VSS, see your Windows documentation.</span></span>  
  
## <a name="virtual-backup-device-interface-vdi"></a><span data-ttu-id="5af26-117">Virtual Backup Device Interface (VDI)</span><span class="sxs-lookup"><span data-stu-id="5af26-117">Virtual Backup Device Interface (VDI)</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5af26-118">è disponibile un'API denominata Virtual Backup Device Interface (VDI) che consente ai fornitori di software indipendenti di integrare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nei propri prodotti, in modo da fornire supporto per operazioni di backup e di ripristino.</span><span class="sxs-lookup"><span data-stu-id="5af26-118">provides an API called Virtual Backup Device Interface (VDI) that enables independent software vendors to integrate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] into their products for providing support for backup and restore operations.</span></span> <span data-ttu-id="5af26-119">Queste API sono state progettate per offrire affidabilità e prestazioni ottimali e per supportare la gamma completa di funzionalità di backup e di ripristino di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , incluse tutte le capacità di backup a caldo e di snapshot.</span><span class="sxs-lookup"><span data-stu-id="5af26-119">These APIs are engineered to provide maximum reliability and performance, and support the full range of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup and restore functionality, including the full range of hot and snapshot backup capabilities.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="5af26-120">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="5af26-120">Permissions</span></span>  
 <span data-ttu-id="5af26-121">Il servizio writer SQL deve essere eseguito utilizzando l'account di **sistema locale** .</span><span class="sxs-lookup"><span data-stu-id="5af26-121">The SQL Writer service must run under the **Local System** account.</span></span> <span data-ttu-id="5af26-122">Per la connessione a **il servizio writer SQL usa l'account di accesso** NT Service\SQLWriter [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5af26-122">The SQL Writer service uses the **NT Service\SQLWriter** login to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5af26-123">Con l'account di accesso **NT Service\SQLWriter** il processo del servizio writer SQL può essere eseguito con un livello di privilegi più basso in un account designato come **senza account di accesso**. In questo modo viene limitata la vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="5af26-123">Using the **NT Service\SQLWriter** login allows the SQL Writer process to run at a lower privilege level in an account designated as **no login**, which limits vulnerability.</span></span> <span data-ttu-id="5af26-124">Se il servizio writer SQL viene disabilitato, qualsiasi utilità basata su snapshot VSS, ad esempio System Center Data Protection Manager, e alcuni altri prodotti di terze parti vengono interrotti o, nel peggiore dei casi, vi è il rischio di eseguire backup di database non coerenti.</span><span class="sxs-lookup"><span data-stu-id="5af26-124">If the SQL Writer service is disabled, then any utility which in relies on VSS snapshots, such as System Center Data Protection Manager, as well as some other 3rd-party products, would be broken, or worse, at risk of taking backups of databases which were not consistent.</span></span> <span data-ttu-id="5af26-125">Se né [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], il sistema in cui si effettua l'esecuzione, né il sistema host (in caso di macchina virtuale) necessitano di altri elementi oltre al backup di [!INCLUDE[tsql](../../includes/tsql-md.md)] , il servizio writer SQL può essere disabilitato in modo sicuro e l'account di accesso può essere rimosso.</span><span class="sxs-lookup"><span data-stu-id="5af26-125">If neither [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the system it runs on, nor the host system (in the event of a virtual machine), need to use anything besides [!INCLUDE[tsql](../../includes/tsql-md.md)] backup, then the SQL Writer service can be safely disabled and the login removed.</span></span>  <span data-ttu-id="5af26-126">Si noti che il servizio writer SQL può essere richiamato da un backup a livello di sistema o di volume, se il backup è basato direttamente o meno su snapshot.</span><span class="sxs-lookup"><span data-stu-id="5af26-126">Note that the SQL Writer service may be invoked by a system or volume level backup, whether the backup is directly snapshot-based or not.</span></span> <span data-ttu-id="5af26-127">Alcuni prodotti per il backup del sistema usano VSS per evitare il blocco causato da file aperti o bloccati.</span><span class="sxs-lookup"><span data-stu-id="5af26-127">Some system backup products use VSS to avoid being blocked by open or locked files.</span></span> <span data-ttu-id="5af26-128">Il servizio writer SQL necessita di autorizzazioni elevate in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] perché nel corso delle proprie attività deve bloccare brevemente tutte le operazioni di I/O per l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5af26-128">The SQL Writer service needs elevated permissions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] because in the course of its activities it briefly freezes all I/O for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="features"></a><span data-ttu-id="5af26-129">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="5af26-129">Features</span></span>  
 <span data-ttu-id="5af26-130">Il servizio writer SQL supporta:</span><span class="sxs-lookup"><span data-stu-id="5af26-130">SQL Writer supports:</span></span>  
  
-   <span data-ttu-id="5af26-131">Backup e ripristino completo del database, inclusi i cataloghi full-text</span><span class="sxs-lookup"><span data-stu-id="5af26-131">Full database backup and restore including full-text catalogs</span></span>  
  
-   <span data-ttu-id="5af26-132">Backup e ripristino differenziale</span><span class="sxs-lookup"><span data-stu-id="5af26-132">Differential backup and restore</span></span>  
  
-   <span data-ttu-id="5af26-133">Ripristino con spostamento</span><span class="sxs-lookup"><span data-stu-id="5af26-133">Restore with move</span></span>  
  
-   <span data-ttu-id="5af26-134">Ridenominazione del database</span><span class="sxs-lookup"><span data-stu-id="5af26-134">Database rename</span></span>  
  
-   <span data-ttu-id="5af26-135">Backup di sola copia</span><span class="sxs-lookup"><span data-stu-id="5af26-135">Copy-only backup</span></span>  
  
-   <span data-ttu-id="5af26-136">Recupero automatico dello snapshot del database</span><span class="sxs-lookup"><span data-stu-id="5af26-136">Auto-recovery of database snapshot</span></span>  
  
 <span data-ttu-id="5af26-137">Il servizio writer SQL non supporta:</span><span class="sxs-lookup"><span data-stu-id="5af26-137">SQL Writer does not support:</span></span>  
  
-   <span data-ttu-id="5af26-138">Backup del log</span><span class="sxs-lookup"><span data-stu-id="5af26-138">Log backups</span></span>  
  
-   <span data-ttu-id="5af26-139">Backup di file e filegroup</span><span class="sxs-lookup"><span data-stu-id="5af26-139">File and filegroup backup</span></span>  
  
-   <span data-ttu-id="5af26-140">Ripristino di pagine</span><span class="sxs-lookup"><span data-stu-id="5af26-140">Page restore</span></span>  
  
  
