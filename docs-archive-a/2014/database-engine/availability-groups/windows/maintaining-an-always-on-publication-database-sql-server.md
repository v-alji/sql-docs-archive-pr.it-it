---
title: Gestione di un database di pubblicazione AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], interoperability
- replication [SQL Server], AlwaysOn Availability Groups
ms.assetid: 55b345fe-2eb9-4b04-a900-63d858eec360
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e8f36d29049140b6e5bbdfc1a4e716d41a766a06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627970"
---
# <a name="maintaining-an-alwayson-publication-database-sql-server"></a><span data-ttu-id="4d0b4-102">Gestione di un database di pubblicazione AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4d0b4-102">Maintaining an AlwaysOn Publication Database (SQL Server)</span></span>
  <span data-ttu-id="4d0b4-103">In questo argomento verranno illustrate alcune considerazioni speciali per la gestione di un database di pubblicazione quando si utilizzano gruppi di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-103">This topic discusses special considerations for maintaining a publication database when you use AlwaysOn availability groups.</span></span>  
  
 
  
##  <a name="maintaining-a-published-database-in-an-availability-group"></a><a name="MaintainPublDb"></a><span data-ttu-id="4d0b4-104">Gestione di un database pubblicato in un gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="4d0b4-104">Maintaining a Published Database in an Availability Group</span></span>  
 <span data-ttu-id="4d0b4-105">La gestione di un database di pubblicazione AlwaysOn è sostanzialmente analoga a quella di un database di pubblicazione standard, con le considerazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d0b4-105">Maintaining an AlwaysOn publication database is basically the same as maintaining a standard publication database, with the following considerations:</span></span>  
  
-   <span data-ttu-id="4d0b4-106">L'amministrazione deve avvenire nell'host della replica primaria.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-106">Administration must occur at the primary replica host.</span></span> <span data-ttu-id="4d0b4-107">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]le pubblicazioni vengono visualizzate nella cartella **Pubblicazioni locali** per l'host della replica primaria e per le repliche secondarie leggibili.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-107">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], publications appear under the **Local Publications** folder for the primary replica host and also for readable secondary replicas.</span></span> <span data-ttu-id="4d0b4-108">Dopo il failover potrebbe essere necessario aggiornare manualmente [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] per riflettere la modifica se la replica secondaria promossa a primaria non era leggibile.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-108">After failover, you might have to manually refresh [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] for the change to be reflected if the secondary that was promoted to primary was not readable.</span></span>  
  
-   <span data-ttu-id="4d0b4-109">In Monitoraggio replica le informazioni sulla pubblicazione vengono sempre visualizzate nel server di pubblicazione originale.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-109">Replication Monitor always displays publication information under the original publisher.</span></span> <span data-ttu-id="4d0b4-110">Queste informazioni possono tuttavia essere visualizzate in Monitoraggio replica da qualsiasi replica aggiungendo il server di pubblicazione originale come server.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-110">However, this information can be viewed in Replication Monitor from any replica by adding the original publisher as a server.</span></span>  
  
-   <span data-ttu-id="4d0b4-111">Se l'amministrazione viene effettuata nella replica primaria corrente mediante oggetti RMO (Replication Management Objects) o stored procedure, nei casi in cui si specifica il nome del server di pubblicazione è necessario specificare il nome dell'istanza in cui il database è stato abilitato per la replica, ovvero il server di pubblicazione originale.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-111">When using stored procedures or Replication Management Objects (RMO) to administer replication at the current primary, for cases in which you specify the Publisher name, you must specify the name of the instance on which the database was enabled for replication (the original publisher).</span></span> <span data-ttu-id="4d0b4-112">Per determinare il nome appropriato, utilizzare la funzione `PUBLISHINGSERVERNAME`.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-112">To determine the appropriate name, use the `PUBLISHINGSERVERNAME` function.</span></span> <span data-ttu-id="4d0b4-113">Quando un database di pubblicazione viene unito in join a un gruppo di disponibilità, i metadati di replica archiviati nelle repliche di database secondarie sono identici a quelli della replica primaria.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-113">When a publishing database joins an availability group, the replication metadata stored in the secondary database replicas is identical to that at the primary.</span></span> <span data-ttu-id="4d0b4-114">Ne consegue che, per i database di pubblicazione abilitati per la replica nel database primario, il nome dell'istanza del server di pubblicazione archiviato in tabelle di sistema nel database secondario equivale al nome del database primario e non a quello del database secondario.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-114">Consequently, for publication databases enabled for replication at the primary, the publisher instance name stored in system tables at the secondary is the name of the primary, not the secondary.</span></span> <span data-ttu-id="4d0b4-115">Ciò influisce sulla manutenzione e sulla configurazione della replica se viene eseguito il failover del database di pubblicazione su un database secondario.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-115">This affects replication configuration and maintenance if the publication database fails over to a secondary.</span></span> <span data-ttu-id="4d0b4-116">Se, ad esempio, si configura la replica con stored procedure in un database secondario dopo il failover e si desidera una sottoscrizione pull a un database di pubblicazione abilitato in una replica diversa, è necessario specificare il nome del server di pubblicazione originale anziché del server di pubblicazione corrente come *@publisher* parametro di `sp_addpullsubscription` o `sp_addmergepulllsubscription` .</span><span class="sxs-lookup"><span data-stu-id="4d0b4-116">For example, if you are configuring replication with stored procedures at a secondary after failover, and you want a pull subscription to a publication database that was enabled at a different replica, you must specify the name of the original publisher instead of the current publisher as the *@publisher* parameter of `sp_addpullsubscription` or `sp_addmergepulllsubscription`.</span></span> <span data-ttu-id="4d0b4-117">Se tuttavia si abilita un database di pubblicazione dopo il failover, il nome dell'istanza del server di pubblicazione archiviato nelle tabelle di sistema corrisponde al nome dell'host primario corrente.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-117">However, if you enable a publication database after failover, the publisher instance name stored in the system tables is the name of the current primary host.</span></span> <span data-ttu-id="4d0b4-118">In questo caso, si utilizzerà il nome host della replica primaria corrente per il *@publisher* parametro.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-118">In this case, you would use the host name of the current primary replica for the *@publisher* parameter.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4d0b4-119">Per alcune procedure, ad esempio `sp_addpublication` , il *@publisher* parametro è supportato solo per i Publisher che non sono istanze di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ; in questi casi, non è pertinente per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-119">For some procedures, such as `sp_addpublication`, the *@publisher* parameter is supported only for publishers that are not instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]; in these cases, it is not relevant for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] AlwaysOn.</span></span>  
  
-   <span data-ttu-id="4d0b4-120">Per sincronizzare una sottoscrizione in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] dopo un failover, sincronizzare le sottoscrizioni pull dal Sottoscrittore e le sottoscrizioni push dal server di pubblicazione attivo.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-120">To synchronize a subscription in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] after a failover, synchronize pull subscriptions from the subscriber and synchronize push subscriptions from the active publisher.</span></span>  
  
##  <a name="removing-a-published-database-from-an-availability-group"></a><a name="RemovePublDb"></a> <span data-ttu-id="4d0b4-121">Rimozione di un database di pubblicazione da un gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="4d0b4-121">Removing a Published Database from an Availability Group</span></span>  
 <span data-ttu-id="4d0b4-122">Considerare i problemi seguenti se un database pubblicato viene rimosso da un gruppo di disponibilità o se un gruppo di disponibilità che dispone di un database del membro pubblicato viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-122">Consider the following issues if a published database is removed from an availability group, or if an availability group that has a published member database is dropped.</span></span>  
  
-   <span data-ttu-id="4d0b4-123">Se il database di pubblicazione nel server di pubblicazione originale viene rimosso da una replica primaria del gruppo di disponibilità, è necessario eseguire `sp_redirect_publisher` senza specificare un valore per il *@redirected_publisher* parametro per rimuovere il reindirizzamento per la coppia server di pubblicazione/database.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-123">If the publication database at the original publisher is removed from an availability group primary replica, you must run `sp_redirect_publisher` without specifying a value for the *@redirected_publisher* parameter in order to remove the redirection for the publisher/database pair.</span></span>  
  
    ```  
    EXEC sys.sp_redirect_publisher   
        @original_publisher = 'MyPublisher',  
        @published_database = 'MyPublishedDB';  
    ```  
  
     <span data-ttu-id="4d0b4-124">Il database rimarrà nello stato di recupero nella replica primaria e dovrà essere ripristinato.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-124">The database will be left in the recovering state at the primary and must be restored.</span></span> <span data-ttu-id="4d0b4-125">Una volta effettuata questa operazione, la replica dovrebbe funzionare invariata rispetto al server di pubblicazione originale.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-125">Once you do this, replication should work unchanged against the original Publisher.</span></span>  
  
-   <span data-ttu-id="4d0b4-126">Nel caso di failover del database di pubblicazione dal server di pubblicazione originale su una replica e se il database viene rimosso dalla replica primaria del gruppo di disponibilità, utilizzare la stored procedure `sp_redirect_publisher` per reindirizzare in modo esplicito il server di pubblicazione originale al nuovo server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-126">If the publication database fails over from the original publisher to a replica and the database is removed from the availability group primary replica, use the stored procedure `sp_redirect_publisher` to explicitly redirect the original publisher to the new publisher.</span></span> <span data-ttu-id="4d0b4-127">Il database rimarrà nello stato di recupero e dovrà essere ripristinato.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-127">The database will be left in the recovering state and must be restored.</span></span> <span data-ttu-id="4d0b4-128">Una volta effettuata questa operazione, la replica dovrebbe continuare a funzionare come nel gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-128">Once you do this, replication should continue to work as it did under the availability group.</span></span>  
  
    ```  
    EXEC sys.sp_redirect_publisher   
        @original_publisher = 'MyPublisher',  
        @published_database = 'MyPublishedDB',  
        @redirected_publisher = 'MyNewPublisher';  
    ```  
  
     <span data-ttu-id="4d0b4-129">Non rimuovere il server remoto per il server di pubblicazione originale dal distributore, anche se non è più possibile accedere al server.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-129">Do not remove the remote server for the original publisher from the distributor, even if the server can no longer be accessed.</span></span> <span data-ttu-id="4d0b4-130">I metadati del server per il server di pubblicazione originale sono necessari nel distributore per rispondere alle query sui metadati di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-130">The server metadata for the original publisher is needed at the distributor to satisfy publication metadata queries.</span></span>  
  
-   <span data-ttu-id="4d0b4-131">Se viene rimosso un gruppo di disponibilità completo, il comportamento di un database replicato membro è lo stesso di un database pubblicato rimosso da un gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-131">If a complete availability group is removed, the behavior with regard to a member replicated database is the same as when a published database is removed from an availability group.</span></span> <span data-ttu-id="4d0b4-132">È possibile riprendere la replica dall'ultima replica primaria non appena viene ripristinato il database e modificato il reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-132">Replication can be resumed from the last primary as soon as the database has been restored and the redirection has been modified.</span></span> <span data-ttu-id="4d0b4-133">Se il database viene ripristinato nel server di pubblicazione originale, il reindirizzamento deve essere rimosso.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-133">If the database is restored at its original publisher, redirection should be removed.</span></span> <span data-ttu-id="4d0b4-134">Se il database viene ripristinato in un host diverso, il reindirizzamento deve essere effettuato in modo esplicito al nuovo host.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-134">If the database is restored at a different host, redirection should be explicitly directed to the new host.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4d0b4-135">Quando viene rimosso un gruppo di disponibilità contenente database membro pubblicati o viene rimosso un database pubblicato da un gruppo di disponibilità, tutte le copie dei database pubblicati rimarranno nello stato di recupero.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-135">When an availability group is removed that has published member databases, or a published database is removed from an availability group, all copies of the published databases will be left in the recovering state.</span></span> <span data-ttu-id="4d0b4-136">Se ripristinati, saranno tutti visualizzati come database pubblicato.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-136">If restored, each will appear as a published database.</span></span> <span data-ttu-id="4d0b4-137">Sarà necessario mantenere una sola copia con i metadati di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-137">Only one copy should be retained with publication metadata.</span></span> <span data-ttu-id="4d0b4-138">Per disabilitare la replica per una copia del database pubblicato, è necessario prima rimuovere tutte le sottoscrizioni e le pubblicazioni dal database.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-138">To disable replication for a published database copy, first remove all subscriptions and publications from the database.</span></span>  
  
     <span data-ttu-id="4d0b4-139">Eseguire `sp_dropsubscription` per rimuovere le sottoscrizioni della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-139">Run `sp_dropsubscription` to remove publication subscriptions.</span></span> <span data-ttu-id="4d0b4-140">Assicurarsi di impostare il parametro *@ignore_distributributor* su 1 per mantenere i metadati per il database di pubblicazione attivo nel server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-140">Make sure to set the parameter *@ignore_distributributor* to 1 to preserve the metadata for the active publishing database at the distributor.</span></span>  
  
    ```  
    USE MyDBName;  
    GO  
  
    EXEC sys.sp_dropsubscription   
        @subscriber = 'MySubscriber',  
        @publication = 'MyPublication',  
        @article = 'all',  
        @ignore_distributor = 1;  
    ```  
  
     <span data-ttu-id="4d0b4-141">Eseguire `sp_droppublication` per rimuovere tutte le pubblicazioni.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-141">Run `sp_droppublication` to remove all publications.</span></span> <span data-ttu-id="4d0b4-142">Impostare di nuovo il parametro *@ignore_distributor* su 1 per mantenere i metadati per il database di pubblicazione attivo nel server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-142">Again, set the parameter *@ignore_distributor* to 1 to preserve the metadata for the active publishing database at the distributor.</span></span>  
  
    ```  
    EXEC sys.sp_droppublication   
        @publication = 'MyPublication',  
        @ignore_distributor = 1;  
    ```  
  
     <span data-ttu-id="4d0b4-143">Eseguire `sp_replicationdboption` per disabilitare replica per il database.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-143">Run `sp_replicationdboption` to disable replication for the database.</span></span>  
  
    ```  
    EXEC sys.sp_replicationdboption  
        @dbname = 'MyDBName',  
        @optname = 'publish',  
        @value = 'false';  
    ```  
  
     <span data-ttu-id="4d0b4-144">A questo punto la copia del database pubblicato può essere mantenuta o eliminata.</span><span class="sxs-lookup"><span data-stu-id="4d0b4-144">At this point, the copy of the published database can be retained or dropped.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="4d0b4-145">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="4d0b4-145">Related Tasks</span></span>  
  
-   [<span data-ttu-id="4d0b4-146">Configurare la replica per i gruppi di disponibilità AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4d0b4-146">Configure Replication for AlwaysOn Availability Groups (SQL Server)</span></span>](always-on-availability-groups-sql-server.md)  
  
-   [<span data-ttu-id="4d0b4-147">Replica, Rilevamento modifiche, Change Data Capture e Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4d0b4-147">Replication, Change Tracking, Change Data Capture, and AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](replicate-track-change-data-capture-always-on-availability.md)  
  
-   [<span data-ttu-id="4d0b4-148">Domande frequenti sull'amministrazione della replica</span><span class="sxs-lookup"><span data-stu-id="4d0b4-148">Replication Administration FAQ</span></span>](../../../relational-databases/replication/administration/frequently-asked-questions-for-replication-administrators.md)  
  
-   [<span data-ttu-id="4d0b4-149">Sottoscrittori della replica e Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4d0b4-149">Replication Subscribers and AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](replication-subscribers-and-always-on-availability-groups-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="4d0b4-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d0b4-150">See Also</span></span>  
 <span data-ttu-id="4d0b4-151">[Prerequisiti, restrizioni e consigli per Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="4d0b4-151">[Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span></span>  
 <span data-ttu-id="4d0b4-152">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4d0b4-152">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="4d0b4-153">[Gruppi di disponibilità AlwaysOn: interoperabilità (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4d0b4-153">[AlwaysOn Availability Groups: Interoperability (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span></span>  
 [<span data-ttu-id="4d0b4-154">Replica di SQL Server</span><span class="sxs-lookup"><span data-stu-id="4d0b4-154">SQL Server Replication</span></span>](../../../relational-databases/replication/sql-server-replication.md)  
  
  
