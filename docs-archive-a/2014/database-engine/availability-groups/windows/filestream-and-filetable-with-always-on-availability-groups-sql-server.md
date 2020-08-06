---
title: FILESTREAM e FileTable con Gruppi di disponibilità AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], Availability Groups
- FILESTREAM [SQL Server], Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: fdceda9a-a9db-4d1d-8745-345992164a98
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e7de7b4d66890bb5f1fe49799844f666de81f4db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627982"
---
# <a name="filestream-and-filetable-with-alwayson-availability-groups-sql-server"></a><span data-ttu-id="900cc-102">FILESTREAM e FileTable con i gruppi di disponibilità AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="900cc-102">FILESTREAM and FileTable with AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="900cc-103">In questo argomento sono contenute informazioni su come utilizzare le funzionalità FILESTREAM e FileTable con [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="900cc-103">This topic contains information about the using the FILESTREAM and FileTable features with [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="900cc-104">Tutte le funzionalità FILESTREAM sono supportate.</span><span class="sxs-lookup"><span data-stu-id="900cc-104">All FILESTREAM functionality is supported.</span></span> <span data-ttu-id="900cc-105">Dopo un failover, i dati FILESTREAM sono accessibili sia nelle repliche secondarie leggibili sia nella nuova primaria.</span><span class="sxs-lookup"><span data-stu-id="900cc-105">After a failover, FILESTREAM data is accessible on both readable secondary replicas and on the new primary.</span></span>  
  
 <span data-ttu-id="900cc-106">La funzionalità FileTable è supportata parzialmente.</span><span class="sxs-lookup"><span data-stu-id="900cc-106">FileTable functionality is partially supported.</span></span> <span data-ttu-id="900cc-107">Dopo un failover, i dati FileTable sono accessibili nella replica primaria, ma non nelle repliche secondarie leggibili.</span><span class="sxs-lookup"><span data-stu-id="900cc-107">After a failover, FileTable data is accessible on the primary replica, but FileTable data is not accessible on readable secondary replicas.</span></span>  
  
 <span data-ttu-id="900cc-108">**Contenuto dell'argomento**</span><span class="sxs-lookup"><span data-stu-id="900cc-108">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="900cc-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="900cc-109">Prerequisites</span></span>](#Prerequisites)  
  
-   [<span data-ttu-id="900cc-110">Utilizzo di nomi di rete virtuale per FILESTREAM e accesso a FileTable</span><span class="sxs-lookup"><span data-stu-id="900cc-110">Using Virtual Network Names (VNNs) for FILESTREAM and FileTable Access</span></span>](#vnn)  
  
-   [<span data-ttu-id="900cc-111">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="900cc-111">Related Tasks</span></span>](#RelatedTasks)  
  
-   [<span data-ttu-id="900cc-112">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="900cc-112">Related Content</span></span>](#RelatedContent)  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="900cc-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="900cc-113">Prerequisites</span></span>  
  
-   <span data-ttu-id="900cc-114">Prima di aggiungere un database in cui è utilizzato FILESTREAM, con o senza FileTable, a un gruppo di disponibilità, verificare che FILESTREAM sia abilitato su ogni istanza del server in cui è ospitata una replica di disponibilità per il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="900cc-114">Before adding a database that uses FILESTREAM, with or without FileTable, to an availability group, ensure that FILESTREAM is enabled on every server instance that hosts an availability replica for the availability group.</span></span> <span data-ttu-id="900cc-115">Per altre informazioni, vedere [Enable and Configure FILESTREAM](../../../relational-databases/blob/enable-and-configure-filestream.md).</span><span class="sxs-lookup"><span data-stu-id="900cc-115">For more information, see [Enable and Configure FILESTREAM](../../../relational-databases/blob/enable-and-configure-filestream.md).</span></span>  
  
##  <a name="using-virtual-network-names-vnns-for-filestream-and-filetable-access"></a><a name="vnn"></a><span data-ttu-id="900cc-116">Utilizzo dei nomi di rete virtuale (VNN) per l'accesso FILESTREAM e FileTable</span><span class="sxs-lookup"><span data-stu-id="900cc-116">Using Virtual Network Names (VNNs) for FILESTREAM and FileTable Access</span></span>  
 <span data-ttu-id="900cc-117">Quando si abilita FILESTREAM su un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], viene creata una condivisione del livello di istanza per fornire l'accesso ai dati FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="900cc-117">When you enable FILESTREAM on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], an instance-level share is created to provide access to the FILESTREAM data.</span></span> <span data-ttu-id="900cc-118">Si accede a questa condivisione tramite il nome computer nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="900cc-118">You access this share by using the computer name in the following format:</span></span>  
  
 `\\<computer_name>\<filestream_share_name>`  
  
 <span data-ttu-id="900cc-119">In un gruppo di disponibilità AlwaysOn, tuttavia, il nome del computer è virtualizzato tramite un nome di rete virtuale o VNN.</span><span class="sxs-lookup"><span data-stu-id="900cc-119">In an AlwaysOn availability group, however, the name of the computer is virtualized by using a Virtual Network Name, or VNN.</span></span> <span data-ttu-id="900cc-120">Quando il computer è la replica primaria in un gruppo di disponibilità, e i database nel gruppo di disponibilità contengono dati FILESTREAM, allora viene creata anche una condivisione con ambito VNN per fornire l'accesso ai dati FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="900cc-120">When the computer is the primary replica in an availability group, and databases in the availability group contain FILESTREAM data, then a VNN-scoped share is also created to provide access to the FILESTREAM data.</span></span> <span data-ttu-id="900cc-121">Non influisce sull'accesso Transact-SQL ai dati FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="900cc-121">This does not affect Transact-SQL access to FILESTREAM data.</span></span> <span data-ttu-id="900cc-122">Nondimeno le applicazioni che utilizzano le API del file system devono utilizzare la condivisione con ambito VNN che ha un percorso con il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="900cc-122">However applications that use file system APIs have to use the VNN-scoped share, which has a path in the following format:</span></span>  
  
 `\\<VNN>\<filestream_share_name>`  
  
 <span data-ttu-id="900cc-123">Questa condivisione con ambito VNN viene creata quando si verifica uno degli eventi seguenti.</span><span class="sxs-lookup"><span data-stu-id="900cc-123">This VNN-scoped share is created when one of the following events occurs.</span></span>  
  
-   <span data-ttu-id="900cc-124">Quando si aggiunge un database che contiene dati FILESTREAM a un gruppo di disponibilità AlwaysOn sulla replica primaria.</span><span class="sxs-lookup"><span data-stu-id="900cc-124">You add a database that contains FILESTREAM data to an AlwaysOn availability group on the primary replica.</span></span> <span data-ttu-id="900cc-125">In questo caso, la condivisione `\\<computer_name>\<filestream_share_name>` già esiste.</span><span class="sxs-lookup"><span data-stu-id="900cc-125">In this case, the share `\\<computer_name>\<filestream_share_name>` already exists.</span></span> <span data-ttu-id="900cc-126">Viene creata la condivisione `\\<VNN>\<filestream_share_name>` .</span><span class="sxs-lookup"><span data-stu-id="900cc-126">The share `\\<VNN>\<filestream_share_name>` is created.</span></span>  
  
-   <span data-ttu-id="900cc-127">Si abilita FILESTREAM per il file i/o o si trasmette l'accesso su una replica primaria che dispone di gruppi di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="900cc-127">You enable FILESTREAM for file i/o streaming access on a primary replica that has availability groups.</span></span> <span data-ttu-id="900cc-128">Vengono create le seguenti condivisioni:</span><span class="sxs-lookup"><span data-stu-id="900cc-128">The following shares are created:</span></span>  
  
    1.  `\\<computer_name>\<filestream_share_name>`  
  
    2.  <span data-ttu-id="900cc-129">`\\<VNN1>\<filestream_share_name>` per il gruppo di disponibilità 1.</span><span class="sxs-lookup"><span data-stu-id="900cc-129">`\\<VNN1>\<filestream_share_name>` for availability group 1.</span></span>  
  
    3.  <span data-ttu-id="900cc-130">`\\<VNN2>\<filestream_share_name>` per il gruppo di disponibilità 2.</span><span class="sxs-lookup"><span data-stu-id="900cc-130">`\\<VNN2>\<filestream_share_name>` for availability group 2.</span></span>  
  
 <span data-ttu-id="900cc-131">Queste condivisioni con ambito VNN vengono propagate anche in tutte le repliche secondarie.</span><span class="sxs-lookup"><span data-stu-id="900cc-131">These VNN-scoped shares are also propagated to all secondary replicas.</span></span>  
  
 <span data-ttu-id="900cc-132">Quando il database che contiene dati FILESTREAM o FileTable appartiene a un gruppo di disponibilità AlwaysOn:</span><span class="sxs-lookup"><span data-stu-id="900cc-132">When the database that contains FILESTREAM or FileTable data belongs to an AlwaysOn availability group:</span></span>  
  
-   <span data-ttu-id="900cc-133">Le funzioni FILESTREAM e FileTable accettano o restituiscono nomi di rete virtuale anziché nomi computer.</span><span class="sxs-lookup"><span data-stu-id="900cc-133">The FILESTREAM and FileTable functions accept or return virtual network names (VNNs) instead of computer names.</span></span> <span data-ttu-id="900cc-134">Per altre informazioni su queste funzioni, vedere [Funzioni FileStream e FileTable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/filestream-and-filetable-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="900cc-134">For more information about these functions, see [Filestream and FileTable Functions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/filestream-and-filetable-functions-transact-sql).</span></span>  
  
-   <span data-ttu-id="900cc-135">Ogni accesso a dati FILESTREAM o FileTable tramite le API del file system deve utilizzare VNN anziché nomi computer.</span><span class="sxs-lookup"><span data-stu-id="900cc-135">All access to FILESTREAM or FileTable data through the file system APIs should use VNNs instead of computer names.</span></span>  
  
 <span data-ttu-id="900cc-136">Se l'applicazione tenta di accedere alla condivisione tramite il nome computer in formato `\\<computer_name>\<filestream_share_name>` quando il database fa parte di un gruppo di disponibilità, allora viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="900cc-136">If your application tries to access the share by using the computer name in the format `\\<computer_name>\<filestream_share_name>` when the database is part of an availability group, then an error is raised.</span></span>  
  
 <span data-ttu-id="900cc-137">Se l'applicazione tenta di accedere alla condivisione tramite un percorso con ambito VNN quando il database non fa parte di un gruppo di disponibilità, allora la richiesta potrebbe avere esito positivo.</span><span class="sxs-lookup"><span data-stu-id="900cc-137">If your application tries to access the share by using a VNN-scoped path when the database is not part of an availability group, then the request may succeed.</span></span> <span data-ttu-id="900cc-138">In questo caso, il nome della rete virtuale viene risolto nel nome computer.</span><span class="sxs-lookup"><span data-stu-id="900cc-138">In this case, the virtual network name is resolved to the computer name.</span></span> <span data-ttu-id="900cc-139">Questo utilizzo è tuttavia sconsigliato vivamente, poiché il percorso con ambito VNN smetterà di funzionare se viene rilasciato il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="900cc-139">However this usage is strongly discouraged, since the VNN-scoped path will stop working if the availability group is dropped.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="900cc-140">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="900cc-140">Related Tasks</span></span>  
  
-   [<span data-ttu-id="900cc-141">Abilitare e configurare FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="900cc-141">Enable and Configure FILESTREAM</span></span>](../../../relational-databases/blob/enable-and-configure-filestream.md)  
  
-   [<span data-ttu-id="900cc-142">Abilitare i prerequisiti per la tabella FileTable</span><span class="sxs-lookup"><span data-stu-id="900cc-142">Enable the Prerequisites for FileTable</span></span>](../../../relational-databases/blob/enable-the-prerequisites-for-filetable.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="900cc-143">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="900cc-143">Related Content</span></span>  
 <span data-ttu-id="900cc-144">No.</span><span class="sxs-lookup"><span data-stu-id="900cc-144">None.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="900cc-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="900cc-145">See Also</span></span>  
 [<span data-ttu-id="900cc-146">Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="900cc-146">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
