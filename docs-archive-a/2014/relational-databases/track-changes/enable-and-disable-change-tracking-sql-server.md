---
title: Abilitare e disabilitare il rilevamento delle modifiche (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- change tracking [SQL Server], disabling
- data changes [SQL Server]
- change tracking [SQL Server], enabling
- tracking data changes [SQL Server]
- change tracking [SQL Server], configuring
- data [SQL Server], changing
ms.assetid: 1c92ec7e-ae53-4498-8bfd-c66a42a24d54
author: rothja
ms.author: jroth
ms.openlocfilehash: 402c63ae03df14e3a725fbc440575f5233d502f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627659"
---
# <a name="enable-and-disable-change-tracking-sql-server"></a><span data-ttu-id="88370-102">Abilitare e disabilitare il rilevamento delle modifiche (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="88370-102">Enable and Disable Change Tracking (SQL Server)</span></span>
  <span data-ttu-id="88370-103">In questo argomento viene descritto come abilitare e disabilitare il rilevamento delle modifiche per un database e una tabella.</span><span class="sxs-lookup"><span data-stu-id="88370-103">This topic describes how to enable and disable change tracking for a database and a table.</span></span>  
  
## <a name="enable-change-tracking-for-a-database"></a><span data-ttu-id="88370-104">Abilitazione del rilevamento delle modifiche per un database</span><span class="sxs-lookup"><span data-stu-id="88370-104">Enable Change Tracking for a Database</span></span>  
 <span data-ttu-id="88370-105">Prima di utilizzare il rilevamento delle modifiche, è necessario abilitarlo a livello di database.</span><span class="sxs-lookup"><span data-stu-id="88370-105">Before you can use change tracking, you must enable change tracking at the database level.</span></span> <span data-ttu-id="88370-106">Nell'esempio seguente viene illustrato come abilitare il rilevamento delle modifiche usando [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="88370-106">The following example shows how to enable change tracking by using [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
```sql  
ALTER DATABASE AdventureWorks2012  
SET CHANGE_TRACKING = ON  
(CHANGE_RETENTION = 2 DAYS, AUTO_CLEANUP = ON)  
```  
  
 <span data-ttu-id="88370-107">È anche possibile abilitare il rilevamento delle modifiche in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] tramite la finestra di dialogo [Proprietà database &#40;pagina Rilevamento delle modifiche&#41;](../databases/database-properties-changetracking-page.md) .</span><span class="sxs-lookup"><span data-stu-id="88370-107">You can also enable change tracking in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] by using the [Database Properties &#40;ChangeTracking Page&#41;](../databases/database-properties-changetracking-page.md) dialog box.</span></span>  
  
 <span data-ttu-id="88370-108">È possibile specificare le opzioni CHANGE_RETENTION e AUTO_CLEANUP quando si abilita il rilevamento delle modifiche ed è possibile modificare i valori in qualsiasi momento dopo l'abilitazione del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="88370-108">You can specify the CHANGE_RETENTION and AUTO_CLEANUP options when you enable change tracking, and you can change the values at any time after change tracking is enabled.</span></span>  
  
 <span data-ttu-id="88370-109">Il valore di memorizzazione della modifica specifica il periodo di tempo durante il quale vengono mantenute le informazioni sul rilevamento delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="88370-109">The change retention value specifies the time period for which change tracking information is kept.</span></span> <span data-ttu-id="88370-110">Le informazioni sul rilevamento delle modifiche precedenti a tale periodo di tempo vengono rimosse periodicamente.</span><span class="sxs-lookup"><span data-stu-id="88370-110">Change tracking information that is older than this time period is removed periodically.</span></span> <span data-ttu-id="88370-111">Durante l'impostazione di questo valore, considerare la frequenza di sincronizzazione delle applicazioni con le tabelle nel database.</span><span class="sxs-lookup"><span data-stu-id="88370-111">When you are setting this value, you should consider how often applications will synchronize with the tables in the database.</span></span> <span data-ttu-id="88370-112">Il periodo di memorizzazione specificato deve durare almeno quanto il periodo di tempo massimo tra le sincronizzazioni.</span><span class="sxs-lookup"><span data-stu-id="88370-112">The specified retention period must be at least as long as the maximum time period between synchronizations.</span></span> <span data-ttu-id="88370-113">Se un'applicazione ottiene modifiche a intervalli più lunghi, i risultati restituiti potrebbero non essere corretti, poiché alcune delle informazioni sulle modifiche sono state probabilmente rimosse.</span><span class="sxs-lookup"><span data-stu-id="88370-113">If an application obtains changes at longer intervals, the results that are returned might be incorrect because some of the change information has probably been removed.</span></span> <span data-ttu-id="88370-114">Per evitare di ottenere risultati non corretti, un'applicazione può utilizzare la funzione di sistema CHANGE_TRACKING_MIN_VALID_VERSION per determinare se l'intervallo tra sincronizzazioni è stato troppo lungo.</span><span class="sxs-lookup"><span data-stu-id="88370-114">To avoid obtaining incorrect results, an application can use the CHANGE_TRACKING_MIN_VALID_VERSION system function to determine whether the interval between synchronizations has been too long.</span></span>  
  
 <span data-ttu-id="88370-115">Per abilitare o disabilitare l'attività di pulizia che rimuove le informazioni obsolete sul rilevamento delle modifiche, è possibile utilizzare l'opzione AUTO_CLEANUP.</span><span class="sxs-lookup"><span data-stu-id="88370-115">You can use the AUTO_CLEANUP option to enable or disable the cleanup task that removes old change tracking information.</span></span> <span data-ttu-id="88370-116">Questa procedura può risultare utile quando un problema temporaneo impedisce la sincronizzazione delle applicazioni e la procedura di rimozione delle informazioni sul rilevamento delle modifiche precedenti al periodo di memorizzazione deve essere messa in pausa finché il problema non viene risolto.</span><span class="sxs-lookup"><span data-stu-id="88370-116">This can be useful when there is a temporary problem that prevents applications from synchronizing and the process for removing change tracking information older than the retention period must be paused until the problem is resolved.</span></span>  
  
 <span data-ttu-id="88370-117">Per qualsiasi database che utilizza il rilevamento delle modifiche, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="88370-117">For any database that uses change tracking, be aware of the following:</span></span>  
  
-   <span data-ttu-id="88370-118">Per utilizzare il rilevamento delle modifiche, il livello di compatibilità del database deve essere impostato su 90 o su un valore superiore.</span><span class="sxs-lookup"><span data-stu-id="88370-118">To use change tracking, the database compatibility level must be set to 90 or greater.</span></span> <span data-ttu-id="88370-119">Se il livello di compatibilità del database è minore di 90, è possibile comunque configurare il rilevamento delle modifiche,</span><span class="sxs-lookup"><span data-stu-id="88370-119">If a database has a compatibility level of less than 90, you can configure change tracking.</span></span> <span data-ttu-id="88370-120">ma la funzione CHANGETABLE, utilizzata per ottenere informazioni sul rilevamento delle modifiche, restituirà un errore.</span><span class="sxs-lookup"><span data-stu-id="88370-120">However, the CHANGETABLE function, which is used to obtain change tracking information, will return an error.</span></span>  
  
-   <span data-ttu-id="88370-121">L'utilizzo dell'isolamento dello snapshot rappresenta il modo più semplice per garantire che tutte le informazioni sul rilevamento delle modifiche siano coerenti.</span><span class="sxs-lookup"><span data-stu-id="88370-121">Using snapshot isolation is the easiest way for you to help ensure that all change tracking information is consistent.</span></span> <span data-ttu-id="88370-122">Per questo motivo, è consigliabile impostare l'isolamento dello snapshot per il database su ON.</span><span class="sxs-lookup"><span data-stu-id="88370-122">For this reason, we strongly recommend that snapshot isolation be set to ON for the database.</span></span> <span data-ttu-id="88370-123">Per altre informazioni, vedere [Usare il rilevamento delle modifiche &#40;SQL Server&#41;](work-with-change-tracking-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="88370-123">For more information, see [Work with Change Tracking &#40;SQL Server&#41;](work-with-change-tracking-sql-server.md).</span></span>  
  
## <a name="enable-change-tracking-for-a-table"></a><span data-ttu-id="88370-124">Abilitazione del rilevamento delle modifiche per una tabella</span><span class="sxs-lookup"><span data-stu-id="88370-124">Enable Change Tracking for a Table</span></span>  
 <span data-ttu-id="88370-125">Il rilevamento delle modifiche deve essere abilitato per ciascuna tabella per cui si desidera eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="88370-125">Change tracking must be enabled for each table that you want tracked.</span></span> <span data-ttu-id="88370-126">Quando il rilevamento delle modifiche è abilitato, le relative informazioni vengono gestite per tutte le righe della tabella interessate da un'operazione DML.</span><span class="sxs-lookup"><span data-stu-id="88370-126">When change tracking is enabled, change tracking information is maintained for all rows in the table that are affected by a DML operation.</span></span>  
  
 <span data-ttu-id="88370-127">Nell'esempio seguente viene illustrato come abilitare il rilevamento delle modifiche per una tabella tramite [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="88370-127">The following example shows how to enable change tracking for a table by using [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
```sql  
ALTER TABLE Person.Contact  
ENABLE CHANGE_TRACKING  
WITH (TRACK_COLUMNS_UPDATED = ON)  
```  
  
 <span data-ttu-id="88370-128">È anche possibile abilitare il rilevamento delle modifiche per una tabella in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] tramite la finestra di dialogo [Proprietà database &#40;pagina Rilevamento delle modifiche&#41;](../databases/database-properties-changetracking-page.md) .</span><span class="sxs-lookup"><span data-stu-id="88370-128">You can also enable change tracking for a table in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] by using the [Database Properties &#40;ChangeTracking Page&#41;](../databases/database-properties-changetracking-page.md) dialog box.</span></span>  
  
 <span data-ttu-id="88370-129">Quando l'opzione TRACK_COLUMNS_UPDATED è impostata su ON, nel [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] vengono archiviate informazioni aggiuntive sulle colonne aggiornate nella tabella del rilevamento delle modifiche interna.</span><span class="sxs-lookup"><span data-stu-id="88370-129">When the TRACK_COLUMNS_UPDATED option is set to ON, the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] stores extra information about which columns were updated to the internal change tracking table.</span></span> <span data-ttu-id="88370-130">Il rilevamento a livello di colonna consente di sincronizzare solo le colonne aggiornate.</span><span class="sxs-lookup"><span data-stu-id="88370-130">Column tracking can enable an application to synchronize only those columns that were updated.</span></span> <span data-ttu-id="88370-131">Ciò può migliorare efficienza e prestazioni.</span><span class="sxs-lookup"><span data-stu-id="88370-131">This can improve efficiency and performance.</span></span> <span data-ttu-id="88370-132">Tuttavia, poiché la gestione delle informazioni sul rilevamento a livello della colonna aggiunge un ulteriore overhead di archiviazione, per impostazione predefinita questa opzione è impostata su OFF.</span><span class="sxs-lookup"><span data-stu-id="88370-132">However, because maintaining column tracking information adds some extra storage overhead, this option is set to OFF by default.</span></span>  
  
## <a name="disable-change-tracking-for-a-database-or-table"></a><span data-ttu-id="88370-133">Disabilitazione del rilevamento delle modifiche per un database o una tabella</span><span class="sxs-lookup"><span data-stu-id="88370-133">Disable Change Tracking for a Database or Table</span></span>  
 <span data-ttu-id="88370-134">Il rilevamento delle modifiche deve essere prima disabilitato per tutte le tabelle di cui sono state rilevate le modifiche prima che il rilevamento possa essere impostato su OFF per il database.</span><span class="sxs-lookup"><span data-stu-id="88370-134">Change tracking must first be disabled for all change-tracked tables before change tracking can be set to OFF for the database.</span></span> <span data-ttu-id="88370-135">Per determinare le tabelle in cui è abilitato il rilevamento delle modifiche per un database, usare la vista del catalogo [sys.change_tracking_tables](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-tables) .</span><span class="sxs-lookup"><span data-stu-id="88370-135">To determine the tables that have change tracking enabled for a database, use the [sys.change_tracking_tables](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-tables) catalog view.</span></span>  
  
 <span data-ttu-id="88370-136">Quando non vengono rilevate modifiche in nessuna tabella di un database, è possibile disabilitare il rilevamento delle modifiche per il database.</span><span class="sxs-lookup"><span data-stu-id="88370-136">When no tables in a database track changes, you can disable change tracking for the database.</span></span> <span data-ttu-id="88370-137">Nell'esempio seguente viene illustrato come disabilitare il rilevamento delle modifiche per un database tramite [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="88370-137">The following example shows how to disable change tracking for a database by using [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
```sql  
ALTER DATABASE AdventureWorks2012  
SET CHANGE_TRACKING = OFF  
```  
  
 <span data-ttu-id="88370-138">Nell'esempio seguente viene illustrato come disabilitare il rilevamento delle modifiche per una tabella tramite [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="88370-138">The following example shows how to disable change tracking for a table by using [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
```sql  
ALTER TABLE Person.Contact  
DISABLE CHANGE_TRACKING;  
```  
  
## <a name="see-also"></a><span data-ttu-id="88370-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88370-139">See Also</span></span>  
 <span data-ttu-id="88370-140">[Proprietà database &#40;pagina Rilevamento delle modifiche&#41;](../databases/database-properties-changetracking-page.md) </span><span class="sxs-lookup"><span data-stu-id="88370-140">[Database Properties &#40;ChangeTracking Page&#41;](../databases/database-properties-changetracking-page.md) </span></span>  
 <span data-ttu-id="88370-141">[Opzioni ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options) </span><span class="sxs-lookup"><span data-stu-id="88370-141">[ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options) </span></span>  
 <span data-ttu-id="88370-142">[sys.change_tracking_databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-databases) </span><span class="sxs-lookup"><span data-stu-id="88370-142">[sys.change_tracking_databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-databases) </span></span>  
 <span data-ttu-id="88370-143">[sys.change_tracking_tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-tables) </span><span class="sxs-lookup"><span data-stu-id="88370-143">[sys.change_tracking_tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-tables) </span></span>  
 <span data-ttu-id="88370-144">[Tenere traccia delle modifiche ai dati &#40;SQL Server&#41;](track-data-changes-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="88370-144">[Track Data Changes &#40;SQL Server&#41;](track-data-changes-sql-server.md) </span></span>  
 <span data-ttu-id="88370-145">[Informazioni sul rilevamento delle modifiche &#40;SQL Server&#41;](../track-changes/about-change-tracking-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="88370-145">[About Change Tracking &#40;SQL Server&#41;](../track-changes/about-change-tracking-sql-server.md) </span></span>  
 <span data-ttu-id="88370-146">[Usare Change Data &#40;SQL Server&#41;](work-with-change-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="88370-146">[Work with Change Data &#40;SQL Server&#41;](work-with-change-data-sql-server.md) </span></span>  
 [<span data-ttu-id="88370-147">Gestire il rilevamento delle modifiche &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="88370-147">Manage Change Tracking &#40;SQL Server&#41;</span></span>](manage-change-tracking-sql-server.md)  
  
  
