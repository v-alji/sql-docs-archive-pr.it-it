---
title: Operazioni comuni che richiedono il backup del database | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- recovery [SQL Server replication], actions requiring a backup
- restoring [SQL Server replication], actions requiring a backup
- backups [SQL Server replication], actions requiring a backup
ms.assetid: a5975bf4-183e-42e3-b7d1-ad02f89d2e1d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3eb10bdca8ee188f7b322a46665c38129d57052b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713035"
---
# <a name="common-actions-requiring-an-updated-backup"></a><span data-ttu-id="688c5-102">Operazioni comuni che richiedono il backup del database</span><span class="sxs-lookup"><span data-stu-id="688c5-102">Common Actions Requiring an Updated Backup</span></span>
  <span data-ttu-id="688c5-103">Se si eseguono backup regolari del log, le eventuali modifiche correlate alla replica dovrebbero essere incluse nei backup del log.</span><span class="sxs-lookup"><span data-stu-id="688c5-103">If you perform regular log backups, any replication-related changes should be captured in the log backups.</span></span> <span data-ttu-id="688c5-104">Se non si eseguono backup del log, effettuare un backup dei database di pubblicazione, di distribuzione e di sottoscrizione, nonché dei database **msdb**e **master** dopo avere apportato modifiche alla topologia o allo schema di replica.</span><span class="sxs-lookup"><span data-stu-id="688c5-104">If you don't perform log backups, perform a backup of the publication, distribution, subscription, **msdb**, and **master** databases after making modifications to your replication schema or topology.</span></span>  
  
## <a name="publication-database"></a><span data-ttu-id="688c5-105">Database di pubblicazione</span><span class="sxs-lookup"><span data-stu-id="688c5-105">Publication Database</span></span>  
 <span data-ttu-id="688c5-106">È necessario eseguire il backup del database di pubblicazione in seguito al completamento delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="688c5-106">Backup the publication database after:</span></span>  
  
-   <span data-ttu-id="688c5-107">Creazione di nuove pubblicazioni.</span><span class="sxs-lookup"><span data-stu-id="688c5-107">Creating new publications.</span></span>  
  
-   <span data-ttu-id="688c5-108">Modifica delle proprietà di una pubblicazione, inclusa l'applicazione di filtri.</span><span class="sxs-lookup"><span data-stu-id="688c5-108">Changing any publication property, including filtering.</span></span>  
  
-   <span data-ttu-id="688c5-109">Aggiunta di articoli a una pubblicazione esistente.</span><span class="sxs-lookup"><span data-stu-id="688c5-109">Adding articles to an existing publication.</span></span>  
  
-   <span data-ttu-id="688c5-110">Reinizializzazione delle sottoscrizioni nell'intera pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="688c5-110">Performing a publication-wide reinitialization of subscriptions.</span></span>  
  
-   <span data-ttu-id="688c5-111">Modifica dello schema in una tabella pubblicata.</span><span class="sxs-lookup"><span data-stu-id="688c5-111">Making a schema change on a published table.</span></span>  
  
-   <span data-ttu-id="688c5-112">Esecuzione di uno script su richiesta con [sp_addscriptexec &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addscriptexec-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="688c5-112">Performing on-demand script execution with [sp_addscriptexec &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addscriptexec-transact-sql).</span></span>  
  
-   <span data-ttu-id="688c5-113">Modifica delle proprietà di un articolo.</span><span class="sxs-lookup"><span data-stu-id="688c5-113">Changing any article property.</span></span>  
  
-   <span data-ttu-id="688c5-114">Eliminazione di pubblicazioni.</span><span class="sxs-lookup"><span data-stu-id="688c5-114">Dropping any publications.</span></span>  
  
-   <span data-ttu-id="688c5-115">Eliminazione di articoli.</span><span class="sxs-lookup"><span data-stu-id="688c5-115">Dropping any articles.</span></span>  
  
-   <span data-ttu-id="688c5-116">Disabilitazione della replica.</span><span class="sxs-lookup"><span data-stu-id="688c5-116">Disabling replication.</span></span>  
  
## <a name="distribution-database"></a><span data-ttu-id="688c5-117">Database di distribuzione</span><span class="sxs-lookup"><span data-stu-id="688c5-117">Distribution Database</span></span>  
 <span data-ttu-id="688c5-118">È necessario eseguire il backup del database di distribuzione in seguito al completamento delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="688c5-118">Backup the distribution database after:</span></span>  
  
-   <span data-ttu-id="688c5-119">Creazione o modifica dei profili agenti di replica.</span><span class="sxs-lookup"><span data-stu-id="688c5-119">Creating or modifying replication agent profiles.</span></span>  
  
-   <span data-ttu-id="688c5-120">Modifica dei parametri dei profili agenti di replica.</span><span class="sxs-lookup"><span data-stu-id="688c5-120">Modifying replication agent profile parameters.</span></span>  
  
-   <span data-ttu-id="688c5-121">Modifica delle proprietà degli agenti di replica (incluse le pianificazioni) per qualsiasi sottoscrizione push.</span><span class="sxs-lookup"><span data-stu-id="688c5-121">Changing the replication agent properties (including schedules) for any push subscriptions.</span></span>  
  
-   <span data-ttu-id="688c5-122">Un nuovo intervallo di valori Identity viene assegnato dalla caratteristica di gestione automatica degli intervalli di valori Identity.</span><span class="sxs-lookup"><span data-stu-id="688c5-122">A new range of identities is assigned by the automatic identity range management feature.</span></span>  
  
## <a name="subscription-database"></a><span data-ttu-id="688c5-123">Database di sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="688c5-123">Subscription Database</span></span>  
 <span data-ttu-id="688c5-124">È necessario eseguire il backup del database di sottoscrizione in seguito al completamento delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="688c5-124">Backup the subscription database after:</span></span>  
  
-   <span data-ttu-id="688c5-125">Modifica delle proprietà di una sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="688c5-125">Changing any subscription property.</span></span>  
  
-   <span data-ttu-id="688c5-126">Modifica della priorità di una sottoscrizione di tipo merge nel server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="688c5-126">Changing the priority for a merge subscription at the Publisher.</span></span>  
  
-   <span data-ttu-id="688c5-127">Eliminazione di sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="688c5-127">Dropping any subscriptions.</span></span>  
  
-   <span data-ttu-id="688c5-128">Disabilitazione della replica.</span><span class="sxs-lookup"><span data-stu-id="688c5-128">Disabling replication.</span></span>  
  
## <a name="msdb-database"></a><span data-ttu-id="688c5-129">Database msdb</span><span class="sxs-lookup"><span data-stu-id="688c5-129">msdb Database</span></span>  
 <span data-ttu-id="688c5-130">È necessario eseguire il backup del database di sistema **msdb** nel nodo appropriato in seguito al completamento delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="688c5-130">Backup the **msdb** system database at the appropriate node after:</span></span>  
  
-   <span data-ttu-id="688c5-131">Attivazione o disabilitazione della replica.</span><span class="sxs-lookup"><span data-stu-id="688c5-131">Enabling or disabling replication.</span></span>  
  
-   <span data-ttu-id="688c5-132">Aggiunta o eliminazione di un database di distribuzione (nel server di distribuzione).</span><span class="sxs-lookup"><span data-stu-id="688c5-132">Adding or dropping a distribution database (at the Distributor).</span></span>  
  
-   <span data-ttu-id="688c5-133">Attivazione o disabilitazione di un database per la pubblicazione (nel server di pubblicazione).</span><span class="sxs-lookup"><span data-stu-id="688c5-133">Enabling or disabling a database for publishing (at the Publisher).</span></span>  
  
-   <span data-ttu-id="688c5-134">Creazione o modifica dei profili agenti di replica (nel server di distribuzione).</span><span class="sxs-lookup"><span data-stu-id="688c5-134">Creating or modifying replication agent profiles (at the Distributor).</span></span>  
  
-   <span data-ttu-id="688c5-135">Modifica dei parametri dei profili agenti di replica (nel server di distribuzione).</span><span class="sxs-lookup"><span data-stu-id="688c5-135">Modifying any replication agent profile parameters (at the Distributor).</span></span>  
  
-   <span data-ttu-id="688c5-136">Modifica delle proprietà degli agenti di replica (incluse le pianificazioni) per qualsiasi sottoscrizione push (nel server di distribuzione).</span><span class="sxs-lookup"><span data-stu-id="688c5-136">Changing the replication agent properties (including schedules) for any push subscriptions (at the Distributor).</span></span>  
  
-   <span data-ttu-id="688c5-137">Modifica delle proprietà degli agenti di replica (incluse le pianificazioni) per qualsiasi sottoscrizione pull (nel Sottoscrittore).</span><span class="sxs-lookup"><span data-stu-id="688c5-137">Changing the replication agent properties (including schedules) for any pull subscriptions (at the Subscriber).</span></span>  
  
-   <span data-ttu-id="688c5-138">Creazione di un pacchetto DTS associato a una pubblicazione transazionale che utilizza sottoscrizioni trasformabili (nel server di distribuzione e nel Sottoscrittore).</span><span class="sxs-lookup"><span data-stu-id="688c5-138">Creating a DTS package associated with a transactional publication that uses transformable subscriptions (at the Distributor and Subscriber).</span></span>  
  
-   <span data-ttu-id="688c5-139">Aggiunta o eliminazione di una sottoscrizione trasformabile (nel server di distribuzione e nel Sottoscrittore).</span><span class="sxs-lookup"><span data-stu-id="688c5-139">Adding or dropping a transformable subscription (at the Distributor and Subscriber).</span></span>  
  
## <a name="master-database"></a><span data-ttu-id="688c5-140">Database master</span><span class="sxs-lookup"><span data-stu-id="688c5-140">master Database</span></span>  
 <span data-ttu-id="688c5-141">È necessario eseguire il backup del database di sistema **master** nel nodo appropriato in seguito al completamento delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="688c5-141">Backup the **master** system database at the appropriate node after:</span></span>  
  
-   <span data-ttu-id="688c5-142">Attivazione o disabilitazione della replica.</span><span class="sxs-lookup"><span data-stu-id="688c5-142">Enabling or disabling replication.</span></span>  
  
-   <span data-ttu-id="688c5-143">Aggiunta o eliminazione di un database di distribuzione (nel server di distribuzione).</span><span class="sxs-lookup"><span data-stu-id="688c5-143">Adding or dropping a distribution database (at the Distributor).</span></span>  
  
-   <span data-ttu-id="688c5-144">Attivazione o disabilitazione di un database per la pubblicazione (nel server di pubblicazione).</span><span class="sxs-lookup"><span data-stu-id="688c5-144">Enabling or disabling a database for publishing (at the Publisher).</span></span>  
  
-   <span data-ttu-id="688c5-145">Aggiunta della prima pubblicazione o eliminazione dell'ultima pubblicazione in qualsiasi database (nel server di pubblicazione).</span><span class="sxs-lookup"><span data-stu-id="688c5-145">Adding the first or dropping the last publication in any database (at the Publisher).</span></span>  
  
-   <span data-ttu-id="688c5-146">Aggiunta della prima sottoscrizione o eliminazione dell'ultima sottoscrizione in qualsiasi database (nel Sottoscrittore).</span><span class="sxs-lookup"><span data-stu-id="688c5-146">Adding the first or dropping the last subscription in any database (at the Subscriber).</span></span>  
  
-   <span data-ttu-id="688c5-147">Attivazione o disabilitazione di un server di pubblicazione nel server di pubblicazione di distribuzione (nel server di pubblicazione e nel server di distribuzione).</span><span class="sxs-lookup"><span data-stu-id="688c5-147">Enabling or disabling a Publisher at a Distribution Publisher (at the Publisher and Distributor).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="688c5-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="688c5-148">See Also</span></span>  
 <span data-ttu-id="688c5-149">[Backup e ripristino di database SQL Server](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="688c5-149">[Back Up and Restore of SQL Server Databases](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 [<span data-ttu-id="688c5-150">Eseguire il backup e ripristino di database replicati</span><span class="sxs-lookup"><span data-stu-id="688c5-150">Back Up and Restore Replicated Databases</span></span>](back-up-and-restore-replicated-databases.md)  
  
  
