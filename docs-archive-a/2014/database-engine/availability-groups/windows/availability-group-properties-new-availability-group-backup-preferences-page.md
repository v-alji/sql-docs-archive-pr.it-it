---
title: 'Proprietà del gruppo di disponibilità: nuovo gruppo di disponibilità (pagina Preferenze di backup) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroupproperties.backuppreferences.f1
helpviewer_keywords:
- read-only routing
ms.assetid: 65fff22d-5963-4a8c-8b31-fe9ab247a03e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7914d4b1d7af06bcaf4f3fd05a260138e3edf5fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624370"
---
# <a name="availability-group-properties-new-availability-group-backup-preferences-page"></a><span data-ttu-id="65026-102">Proprietà del gruppo di disponibilità: Nuovo gruppo di disponibilità (pagina Preferenze di backup)</span><span class="sxs-lookup"><span data-stu-id="65026-102">Availability Group Properties: New Availability Group (Backup Preferences Page)</span></span>
  <span data-ttu-id="65026-103">Utilizzare questa finestra di dialogo per visualizzare e modificare le preferenze di backup del gruppo di disponibilità selezionato.</span><span class="sxs-lookup"><span data-stu-id="65026-103">Use this dialog box to view and change the backup preferences of the selected availability group.</span></span>  
  
 <span data-ttu-id="65026-104">**Per visualizzare le proprietà del gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="65026-104">**To view availability group properties**</span></span>  
  
-   [<span data-ttu-id="65026-105">Visualizzazione delle Proprietà dei gruppi di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="65026-105">View Availability Group Properties &#40;SQL Server&#41;</span></span>](view-availability-group-properties-sql-server.md)  
  
-   [<span data-ttu-id="65026-106">Usare il Dashboard Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="65026-106">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
## <a name="where-should-backups-occur"></a><span data-ttu-id="65026-107">Destinazione dei backup</span><span class="sxs-lookup"><span data-stu-id="65026-107">Where should backups occur?</span></span>  
 <span data-ttu-id="65026-108">**Preferisco secondario**</span><span class="sxs-lookup"><span data-stu-id="65026-108">**Prefer Secondary**</span></span>  
 <span data-ttu-id="65026-109">Specifica che i backup devono essere eseguiti su una replica secondaria tranne quando la replica primaria è l'unica replica online.</span><span class="sxs-lookup"><span data-stu-id="65026-109">Specifies that backups should occur on a secondary replica except when the primary replica is the only replica online.</span></span> <span data-ttu-id="65026-110">In tal caso il backup deve essere eseguito sulla replica primaria.</span><span class="sxs-lookup"><span data-stu-id="65026-110">In that case, the backup should occur on the primary replica.</span></span> <span data-ttu-id="65026-111">Questa è l'opzione predefinita.</span><span class="sxs-lookup"><span data-stu-id="65026-111">This is the default option.</span></span>  
  
 <span data-ttu-id="65026-112">**Solo secondaria**</span><span class="sxs-lookup"><span data-stu-id="65026-112">**Secondary only**</span></span>  
 <span data-ttu-id="65026-113">Specifica che i backup non devono mai essere eseguiti sulla replica primaria.</span><span class="sxs-lookup"><span data-stu-id="65026-113">Specifies that backups should never be performed on the primary replica.</span></span> <span data-ttu-id="65026-114">Se la replica primaria è l'unica replica online, il backup non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="65026-114">If the primary replica is the only replica online, the backup should not occur.</span></span>  
  
 <span data-ttu-id="65026-115">**Server/istanza primaria**</span><span class="sxs-lookup"><span data-stu-id="65026-115">**Primary**</span></span>  
 <span data-ttu-id="65026-116">Specifica che i backup devono essere sempre eseguiti sulla replica primaria.</span><span class="sxs-lookup"><span data-stu-id="65026-116">Specifies that the backups should always occur on the primary replica.</span></span> <span data-ttu-id="65026-117">Questa opzione è utile se sono necessarie funzionalità di backup, ad esempio la creazione di backup differenziali, che non sono supportate quando il backup viene eseguito su una replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="65026-117">This option is useful if you need backup features, such as creating differential backups, that are not supported when backup is run on a secondary replica.</span></span>  
  
 <span data-ttu-id="65026-118">**Qualsiasi replica**</span><span class="sxs-lookup"><span data-stu-id="65026-118">**Any Replica**</span></span>  
 <span data-ttu-id="65026-119">Specifica che si preferisce che i processi di backup ignorino il ruolo delle repliche di disponibilità nella scelta della replica per l'esecuzione dei backup.</span><span class="sxs-lookup"><span data-stu-id="65026-119">Specifies that you prefer that backup jobs ignore the role of the availability replicas when choosing the replica to perform backups.</span></span> <span data-ttu-id="65026-120">Si noti che i processi di backup potrebbero valutare altri fattori, ad esempio la priorità di backup di ogni replica di disponibilità in combinazione con lo stato operativo e lo stato connesso.</span><span class="sxs-lookup"><span data-stu-id="65026-120">Note backup jobs might evaluate other factors such as backup priority of each availability replica in combination with its operational state and connected state.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="65026-121">L'impostazione della preferenza di backup non viene forzata.</span><span class="sxs-lookup"><span data-stu-id="65026-121">There is no enforcement of the backup-preference setting.</span></span> <span data-ttu-id="65026-122">L'interpretazione di questa preferenza dipende dall'eventuale logica su cui si basano gli script dei processi di backup per i database in un determinato gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="65026-122">The interpretation of this preference depends on the logic, if any, that you script into back jobs for the databases in a given availability group.</span></span> <span data-ttu-id="65026-123">Per ulteriori informazioni, vedere [repliche secondarie attive: backup in repliche secondarie (gruppi di disponibilità AlwaysOn)](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="65026-123">For more information, see [Active Secondaries: Backup on Secondary Replicas (AlwaysOn Availability Groups)](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md).</span></span>  
  
## <a name="replica-backup-priorities"></a><span data-ttu-id="65026-124">Priorità backup repliche</span><span class="sxs-lookup"><span data-stu-id="65026-124">Replica backup priorities</span></span>  
 <span data-ttu-id="65026-125">In questa griglia è indicata la priorità di backup corrente di ogni istanza del server che ospita una replica per il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="65026-125">This grid displays the current backup priority of each server instance that hosts a replica for the availability group.</span></span> <span data-ttu-id="65026-126">Utilizzare questa griglia per modificare la priorità di backup di una o più repliche di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="65026-126">Use this grid to change the backup priority of one or more availability replicas.</span></span>  
  
 <span data-ttu-id="65026-127">**Istanza del server**</span><span class="sxs-lookup"><span data-stu-id="65026-127">**Server Instance**</span></span>  
 <span data-ttu-id="65026-128">Nome dell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] che ospita la replica di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="65026-128">The name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the availability replica.</span></span>  
  
 <span data-ttu-id="65026-129">**Priorità di backup (Più bassa=1, Più alta=100)**</span><span class="sxs-lookup"><span data-stu-id="65026-129">**Backup Priority (Lowest=1, Highest=100)**</span></span>  
 <span data-ttu-id="65026-130">Specifica la priorità di esecuzione dei backup nella replica rispetto alle altre repliche nello stesso gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="65026-130">Specifies your priority for performing backups on this replica relative to the other replicas in the same availability group.</span></span> <span data-ttu-id="65026-131">Il valore è un numero intero compreso nell'intervallo 0-100.</span><span class="sxs-lookup"><span data-stu-id="65026-131">The value is an integer in the range of 0..100.</span></span> <span data-ttu-id="65026-132">1 indica la priorità più bassa e 100 indica la priorità più alta.</span><span class="sxs-lookup"><span data-stu-id="65026-132">1 indicates the lowest priority, and 100 indicates the highest priority.</span></span> <span data-ttu-id="65026-133">Se **Priorità di backup** = 1, la replica di disponibilità viene scelta per l'esecuzione dei backup solo se non sono disponibili repliche di disponibilità con priorità più alta.</span><span class="sxs-lookup"><span data-stu-id="65026-133">If **Backup Priority** = 1, the availability replica would be chosen for performing backups only if no higher priority availability replicas are currently available.</span></span>  
  
 <span data-ttu-id="65026-134">**Escludi replica**</span><span class="sxs-lookup"><span data-stu-id="65026-134">**Exclude Replica**</span></span>  
 <span data-ttu-id="65026-135">Selezionare questa opzione se si desidera che questa replica di disponibilità non venga mai scelta per l'esecuzione dei backup.</span><span class="sxs-lookup"><span data-stu-id="65026-135">Select if you never want this availability replica to be chosen for performing backups.</span></span> <span data-ttu-id="65026-136">Ciò si rivela utile, ad esempio, per una replica di disponibilità remota in cui non si desidera eseguire mai il failover dei backup.</span><span class="sxs-lookup"><span data-stu-id="65026-136">This is useful, for example, for a remote availability replica to which you never want backups to fail over.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65026-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65026-137">See Also</span></span>  
 <span data-ttu-id="65026-138">[Repliche secondarie attive: backup in repliche secondarie (Gruppi di disponibilità AlwaysOn)](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="65026-138">[Active Secondaries: Backup on Secondary Replicas (AlwaysOn Availability Groups)](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="65026-139">ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="65026-139">ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-availability-group-transact-sql)  
  
  
