---
title: Informazioni sul rilevamento delle modifiche (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- data changes [SQL Server]
- tracking data changes [SQL Server]
- change tracking [SQL Server], about change tracking
- change tracking [SQL Server]
- data [SQL Server], changing
ms.assetid: 5e0ef05a-8317-4c98-be20-b19d4cd78f12
author: rothja
ms.author: jroth
ms.openlocfilehash: 4e8a817421aeca7906d31e4a70c25a12b6af7c0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630399"
---
# <a name="about-change-tracking-sql-server"></a><span data-ttu-id="66bb2-102">Informazioni sul rilevamento delle modifiche (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="66bb2-102">About Change Tracking (SQL Server)</span></span>
  <span data-ttu-id="66bb2-103">Il rilevamento delle modifiche è una soluzione semplice che consente di rilevare in modo efficiente le modifiche per le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="66bb2-103">Change tracking is a lightweight solution that provides an efficient change tracking mechanism for applications.</span></span> <span data-ttu-id="66bb2-104">Per consentire alle applicazioni di eseguire una query per le modifiche apportate ai dati in un database e di accedere alle informazioni correlate, gli sviluppatori di applicazioni dovevano in genere implementare meccanismi di rilevamento delle modifiche personalizzati.</span><span class="sxs-lookup"><span data-stu-id="66bb2-104">Typically, to enable applications to query for changes to data in a database and access information that is related to the changes, application developers had to implement custom change tracking mechanisms.</span></span> <span data-ttu-id="66bb2-105">La creazione di questi meccanismi comporta in genere una grande quantità di lavoro e spesso implica l'utilizzo di una combinazione di trigger, `timestamp` colonne, nuove tabelle per archiviare le informazioni di rilevamento e processi di pulizia personalizzati.</span><span class="sxs-lookup"><span data-stu-id="66bb2-105">Creating these mechanisms usually involved a lot of work and frequently involved using a combination of triggers, `timestamp` columns, new tables to store tracking information, and custom cleanup processes.</span></span>  
  
 <span data-ttu-id="66bb2-106">A tipi diversi di applicazioni sono associati requisiti diversi correlati alla quantità di informazioni necessarie relative alle modifiche.</span><span class="sxs-lookup"><span data-stu-id="66bb2-106">Different types of applications have different requirements for how much information they need about the changes.</span></span> <span data-ttu-id="66bb2-107">Il rilevamento delle modifiche può essere utilizzato nelle applicazioni per fornire risposte alle domande seguenti relative alle modifiche apportate a una tabella utente:</span><span class="sxs-lookup"><span data-stu-id="66bb2-107">Applications can use change tracking to answer the following questions about the changes that have been made to a user table:</span></span>  
  
-   <span data-ttu-id="66bb2-108">Quali righe sono state modificate per una tabella utente?</span><span class="sxs-lookup"><span data-stu-id="66bb2-108">What rows have changed for a user table?</span></span>  
  
    -   <span data-ttu-id="66bb2-109">È necessario sapere solo che una riga è stata modificata. Non è necessario sapere il numero di modifiche apportate alla riga o i valori di qualsiasi modifica intermedia.</span><span class="sxs-lookup"><span data-stu-id="66bb2-109">Only the fact that a row has changed is required, not how many times the row has changed or the values of any intermediate changes.</span></span>  
  
    -   <span data-ttu-id="66bb2-110">Gli ultimi dati possono essere ottenuti direttamente dalla tabella per cui viene eseguito il rilevamento.</span><span class="sxs-lookup"><span data-stu-id="66bb2-110">The latest data can be obtained directly from the table that is being tracked.</span></span>  
  
-   <span data-ttu-id="66bb2-111">Una riga è stata modificata?</span><span class="sxs-lookup"><span data-stu-id="66bb2-111">Has a row changed?</span></span>  
  
    -   <span data-ttu-id="66bb2-112">È necessario sapere che una riga è stata modificata. Le informazioni sulla modifica devono inoltre essere disponibili e devono essere state registrate nel momento in cui la modifica è stata apportata nella stessa transazione.</span><span class="sxs-lookup"><span data-stu-id="66bb2-112">The fact that a row has changed and information about the change must be available and recorded at the time that the change was made in the same transaction.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="66bb2-113">Se per un'applicazione è necessario conoscere le informazioni relative a tutte le modifiche apportate e i valori intermedi dei dati modificati, potrebbe risultare appropriato utilizzare la funzionalità Change Data Capture anziché il rilevamento delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="66bb2-113">If an application requires information about all the changes that were made and the intermediate values of the changed data, using change data capture, instead of change tracking, might be appropriate.</span></span> <span data-ttu-id="66bb2-114">Per altre informazioni, vedere [Informazioni su Change Data Capture &#40;SQL Server&#41;](../track-changes/about-change-data-capture-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="66bb2-114">For more information, see [About Change Data Capture &#40;SQL Server&#41;](../track-changes/about-change-data-capture-sql-server.md).</span></span>  
  
## <a name="one-way-and-two-way-synchronization-applications"></a><span data-ttu-id="66bb2-115">Applicazioni di sincronizzazione unidirezionale e bidirezionale</span><span class="sxs-lookup"><span data-stu-id="66bb2-115">One-Way and Two-Way Synchronization Applications</span></span>  
 <span data-ttu-id="66bb2-116">Le applicazioni che devono sincronizzare dati con un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] devono poter eseguire query per le modifiche.</span><span class="sxs-lookup"><span data-stu-id="66bb2-116">Applications that have to synchronize data with an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] must be able to query for changes.</span></span> <span data-ttu-id="66bb2-117">Il rilevamento delle modifiche può essere utilizzato come base per le applicazioni di sincronizzazione unidirezionale e bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="66bb2-117">Change tracking can be used as a foundation for both one-way and two-way synchronization applications.</span></span>  
  
### <a name="one-way-synchronization-applications"></a><span data-ttu-id="66bb2-118">Applicazioni di sincronizzazione unidirezionale</span><span class="sxs-lookup"><span data-stu-id="66bb2-118">One-Way Synchronization Applications</span></span>  
 <span data-ttu-id="66bb2-119">Le applicazioni di sincronizzazione unidirezionale, ad esempio un'applicazione client o un'applicazione di memorizzazione nella cache di livello medio, possono essere compilate in modo che utilizzino il rilevamento delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="66bb2-119">One-way synchronization applications, such as a client or mid-tier caching application, can be built that use change tracking.</span></span> <span data-ttu-id="66bb2-120">Come illustrato nella figura seguente, per un'applicazione di memorizzazione nella cache è necessario che i dati siano archiviati nel [!INCLUDE[ssDE](../../includes/ssde-md.md)] e siano memorizzati nella cache in altri archivi dati.</span><span class="sxs-lookup"><span data-stu-id="66bb2-120">As shown in the following illustration, a caching application requires data to be stored in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and to be cached in other data stores.</span></span> <span data-ttu-id="66bb2-121">L'applicazione deve essere in grado di mantenere aggiornata la cache con qualsiasi modifica apportata alle tabelle di database.</span><span class="sxs-lookup"><span data-stu-id="66bb2-121">The application must be able to keep the cache up-to-date with any changes that have been made to the database tables.</span></span> <span data-ttu-id="66bb2-122">Non è presente alcuna modifica da passare nuovamente al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66bb2-122">There are no changes to pass back to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="66bb2-123">![Mostra le applicazioni di sincronizzazione unidirezionale](../../database-engine/media/one-waysync.gif "Mostra le applicazioni di sincronizzazione unidirezionale")</span><span class="sxs-lookup"><span data-stu-id="66bb2-123">![Shows one-way synchronization applications](../../database-engine/media/one-waysync.gif "Shows one-way synchronization applications")</span></span>  
  
### <a name="two-way-synchronization-applications"></a><span data-ttu-id="66bb2-124">Applicazioni di sincronizzazione bidirezionale</span><span class="sxs-lookup"><span data-stu-id="66bb2-124">Two-Way Synchronization Applications</span></span>  
 <span data-ttu-id="66bb2-125">Anche le applicazioni di sincronizzazione bidirezionale possono essere compilate in modo che utilizzino il rilevamento delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="66bb2-125">Two-way synchronization applications can also be built that use change tracking.</span></span> <span data-ttu-id="66bb2-126">In questo scenario i dati contenuti in un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] sono sincronizzati con uno o più archivi dati.</span><span class="sxs-lookup"><span data-stu-id="66bb2-126">In this scenario, the data in an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is synchronized with one or more data stores.</span></span> <span data-ttu-id="66bb2-127">I dati in tali archivi possono essere aggiornati e le modifiche devono essere sincronizzate nuovamente nel [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66bb2-127">The data in those stores can be updated and the changes must be synchronized back to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="66bb2-128">![Mostra le applicazioni di sincronizzazione bidirezionale](../../database-engine/media/two-waysync.gif "Mostra le applicazioni di sincronizzazione bidirezionale")</span><span class="sxs-lookup"><span data-stu-id="66bb2-128">![Shows two-way synchronization applications](../../database-engine/media/two-waysync.gif "Shows two-way synchronization applications")</span></span>  
  
 <span data-ttu-id="66bb2-129">Un valido esempio di applicazione di sincronizzazione bidirezionale è un'applicazione che esegue occasionalmente una connessione.</span><span class="sxs-lookup"><span data-stu-id="66bb2-129">A good example of two-way synchronization application is an occasionally connected application.</span></span> <span data-ttu-id="66bb2-130">In questo caso un'applicazione client esegue una query e aggiorna un archivio locale.</span><span class="sxs-lookup"><span data-stu-id="66bb2-130">In this type of application, a client application queries and updates a local store.</span></span> <span data-ttu-id="66bb2-131">Quando tra un client e un server è disponibile una connessione, l'applicazione si sincronizzerà con un server e i dati fluiscono in entrambe le direzioni.</span><span class="sxs-lookup"><span data-stu-id="66bb2-131">When a connection is available between a client and server, the application will synchronize with a server, and changed data flows in both directions.</span></span>  
  
 <span data-ttu-id="66bb2-132">Le applicazioni di sincronizzazione bidirezionale devono essere in grado di rilevare i conflitti.</span><span class="sxs-lookup"><span data-stu-id="66bb2-132">The two-way synchronization applications must be able to detect conflicts.</span></span> <span data-ttu-id="66bb2-133">Un conflitto potrebbe verificarsi se gli stessi dati sono stati modificati in entrambi gli archivi dati nel periodo di tempo che intercorre tra le sincronizzazioni.</span><span class="sxs-lookup"><span data-stu-id="66bb2-133">A conflict would occur if the same data was changed in both data stores in the time between synchronizations.</span></span> <span data-ttu-id="66bb2-134">Grazie alla possibilità di rilevare conflitti, un'applicazione può garantire che le modifiche non vadano perse.</span><span class="sxs-lookup"><span data-stu-id="66bb2-134">With the ability to detect conflicts, an application can make sure that changes are not lost.</span></span>  
  
## <a name="how-change-tracking-works"></a><span data-ttu-id="66bb2-135">Funzionamento del rilevamento delle modifiche</span><span class="sxs-lookup"><span data-stu-id="66bb2-135">How Change Tracking Works</span></span>  
 <span data-ttu-id="66bb2-136">Per configurare il rilevamento delle modifiche, è possibile utilizzare istruzioni DDL o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66bb2-136">To configure change tracking, you can use DDL statements or [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="66bb2-137">Per altre informazioni, vedere [Abilitare e disabilitare il rilevamento delle modifiche &#40;SQL Server&#41;](../track-changes/enable-and-disable-change-tracking-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="66bb2-137">For more information, see [Enable and Disable Change Tracking &#40;SQL Server&#41;](../track-changes/enable-and-disable-change-tracking-sql-server.md).</span></span> <span data-ttu-id="66bb2-138">Per rilevare le modifiche, è necessario innanzitutto abilitare il rilevamento delle modifiche per il database, quindi abilitarlo per le tabelle desiderate all'interno del database stesso.</span><span class="sxs-lookup"><span data-stu-id="66bb2-138">To track changes, change tracking must first be enabled for the database and then enabled for the tables that you want to track within that database.</span></span> <span data-ttu-id="66bb2-139">La definizione della tabella non deve essere modificata in alcun modo e non viene creato alcun trigger.</span><span class="sxs-lookup"><span data-stu-id="66bb2-139">The table definition does not have to be changed in any way, and no triggers are created.</span></span>  
  
 <span data-ttu-id="66bb2-140">Una volta configurato il rilevamento delle modifiche per una tabella, qualsiasi istruzione DML che influisce sulle righe nella tabella causerà la registrazione delle informazioni sul rilevamento delle modifiche per ciascuna riga modificata.</span><span class="sxs-lookup"><span data-stu-id="66bb2-140">After change tracking is configured for a table, any DML statement that affects rows in the table will cause change tracking information for each modified row to be recorded.</span></span> <span data-ttu-id="66bb2-141">Per eseguire query per le righe che sono state modificate e per ottenere informazioni sulle modifiche, è possibile usare le [funzioni di rilevamento delle modifiche](/sql/relational-databases/system-functions/change-tracking-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="66bb2-141">To query for the rows that have changed and to obtain information about the changes, you can use [change tracking functions](/sql/relational-databases/system-functions/change-tracking-functions-transact-sql).</span></span>  
  
 <span data-ttu-id="66bb2-142">I valori della colonna chiave primaria costituiscono le sole informazioni presenti nella tabella con rilevamento registrate con le informazioni relative alle modifiche.</span><span class="sxs-lookup"><span data-stu-id="66bb2-142">The values of the primary key column is only information from the tracked table that is recorded with the change information.</span></span> <span data-ttu-id="66bb2-143">Tali valori identificano le righe modificate.</span><span class="sxs-lookup"><span data-stu-id="66bb2-143">These values identify the rows that have been changed.</span></span> <span data-ttu-id="66bb2-144">Per ottenere i dati più recenti per tali righe, un'applicazione può utilizzare i valori della colonna chiave primaria per creare un join tra la tabella di origine e quella con rilevamento.</span><span class="sxs-lookup"><span data-stu-id="66bb2-144">To obtain the latest data for those rows, an application can use the primary key column values to join the source table with the tracked table.</span></span>  
  
 <span data-ttu-id="66bb2-145">È inoltre possibile utilizzare il rilevamento delle modifiche per ottenere informazioni sulla modifica apportata a ogni riga,</span><span class="sxs-lookup"><span data-stu-id="66bb2-145">Information about the change that was made to each row can also be obtained by using change tracking.</span></span> <span data-ttu-id="66bb2-146">ad esempio il tipo di operazione DML che ha provocato la modifica (inserimento, aggiornamento o eliminazione) o le colonne modificate come parte di un'operazione di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="66bb2-146">For example, the type of DML operation that caused the change (insert, update, or delete) or the columns that were changed as part of an update operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66bb2-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66bb2-147">See Also</span></span>  
 <span data-ttu-id="66bb2-148">[Abilitare e disabilitare Rilevamento modifiche &#40;SQL Server&#41;](../track-changes/enable-and-disable-change-tracking-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="66bb2-148">[Enable and Disable Change Tracking &#40;SQL Server&#41;](../track-changes/enable-and-disable-change-tracking-sql-server.md) </span></span>  
 <span data-ttu-id="66bb2-149">[Usare Rilevamento modifiche &#40;SQL Server&#41;](../track-changes/work-with-change-tracking-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="66bb2-149">[Work with Change Tracking &#40;SQL Server&#41;](../track-changes/work-with-change-tracking-sql-server.md) </span></span>  
 <span data-ttu-id="66bb2-150">[Gestire Rilevamento modifiche &#40;SQL Server&#41;](../track-changes/manage-change-tracking-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="66bb2-150">[Manage Change Tracking &#40;SQL Server&#41;](../track-changes/manage-change-tracking-sql-server.md) </span></span>  
 [<span data-ttu-id="66bb2-151">Rilevare le modifiche ai dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="66bb2-151">Track Data Changes &#40;SQL Server&#41;</span></span>](../track-changes/track-data-changes-sql-server.md)  
  
  