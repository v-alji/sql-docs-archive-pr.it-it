---
title: Popolare gli indici full-text | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- index populations [full-text search]
- incremental populations [full-text search]
- populations [full-text search]
- full-text search [SQL Server], populations
- crawls [full-text search]
- automatic full-text index updates
- change tracking-based populations [full-text search]
- manual updates [full-text search]
- manual populations [full-text search]
- auto populations [full-text search]
- full-text indexes [SQL Server], key column
- full populations [full-text search]
- full-text indexes [SQL Server], populations
ms.assetid: 76767b20-ef55-49ce-8dc4-e77cb8ff618a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9ab93a3514fa260c8c3836da85c767da3c3051a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635998"
---
# <a name="populate-full-text-indexes"></a><span data-ttu-id="d2d01-102">Popolamento degli indici full-text</span><span class="sxs-lookup"><span data-stu-id="d2d01-102">Populate Full-Text Indexes</span></span>
  <span data-ttu-id="d2d01-103">La creazione e la gestione di un indice full-text comporta il popolamento dell'indice con un processo denominato *popolamento* , noto anche con il termine *ricerca per indicizzazione*.</span><span class="sxs-lookup"><span data-stu-id="d2d01-103">Creating and maintaining a full-text index involves populating the index by using a process called a *population* (also known as a *crawl*).</span></span>  
  
##  <a name="types-of-population"></a><a name="types"></a><span data-ttu-id="d2d01-104">Tipi di popolamento</span><span class="sxs-lookup"><span data-stu-id="d2d01-104">Types of Population</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="d2d01-105">supporta i tipi seguenti di popolamento: popolamento completo, popolamento automatico o manuale basato sul rilevamento delle modifiche e popolamento incrementale basato su timestamp.</span><span class="sxs-lookup"><span data-stu-id="d2d01-105">supports the following types of population: full population, change tracking-based automatic or manual population, and incremental timestamp-based population.</span></span>  
  
### <a name="full-population"></a><span data-ttu-id="d2d01-106">Popolamento completo</span><span class="sxs-lookup"><span data-stu-id="d2d01-106">Full Population</span></span>  
 <span data-ttu-id="d2d01-107">Durante un popolamento completo, vengono compilate voci di indice per tutte le righe di una tabella o di una vista indicizzata.</span><span class="sxs-lookup"><span data-stu-id="d2d01-107">During a full population, index entries are built for all the rows of a table or indexed view.</span></span> <span data-ttu-id="d2d01-108">Durante un popolamento completo di un indice full-text, vengono compilate voci di indice per tutte le righe di una tabella di base o di una vista indicizzata.</span><span class="sxs-lookup"><span data-stu-id="d2d01-108">A full population of a full-text index, builds index entries for all the rows of the base table or indexed view.</span></span>  
  
 <span data-ttu-id="d2d01-109">Per impostazione predefinita, in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] un nuovo indice full-text viene popolato completamente non appena viene creato.</span><span class="sxs-lookup"><span data-stu-id="d2d01-109">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] populates a new full-text index fully as soon as it is created.</span></span> <span data-ttu-id="d2d01-110">Un popolamento completo può tuttavia richiedere una quantità significativa di risorse.</span><span class="sxs-lookup"><span data-stu-id="d2d01-110">However, a full population can consume a significant amount of resources.</span></span> <span data-ttu-id="d2d01-111">Di conseguenza, quando si crea un indice full-text durante periodi di intensa attività è spesso consigliabile rimandare il popolamento completo a un periodo di attività meno intensa, in particolare se la tabella di base di un indice full-text è di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="d2d01-111">Therefore, when creating a full-text index during peak periods, it is often a best practice to delay the full population until an off-peak time, particularly if the base table of an full-text index is large.</span></span> <span data-ttu-id="d2d01-112">Tuttavia, il catalogo full-text a cui appartiene l'indice non può essere utilizzato finché non vengono popolati tutti i relativi indici full-text.</span><span class="sxs-lookup"><span data-stu-id="d2d01-112">However, the full-text catalog to which the index belongs is not usable until all of its full-text indexes are populated.</span></span> <span data-ttu-id="d2d01-113">Per creare un indice full-text senza popolarlo immediatamente, specificare la clausola CHANGE_TRACKING OFF, NO POPULATION nell'istruzione CREATE FULLTEXT INDEX.</span><span class="sxs-lookup"><span data-stu-id="d2d01-113">To create a full-text index without populating it immediately, specify the CHANGE_TRACKING OFF, NO POPULATION clause in the CREATE FULLTEXT INDEX statement.</span></span> <span data-ttu-id="d2d01-114">Se viene specificato CHANGE_TRACKING MANUAL, il motore di ricerca full-text utilizza l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="d2d01-114">If you specify CHANGE_TRACKING MANUAL, the Full-Text Engine uses statement.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="d2d01-115">il nuovo indice full-text non verrà popolato fino a quando non si esegue un'istruzione ALTER FULLTEXT INDEX utilizzando la clausola START FULL POPULATION o START INCREMENTAl population.</span><span class="sxs-lookup"><span data-stu-id="d2d01-115">will not populate the new full-text index until you execute an ALTER FULLTEXT INDEX statement using the START FULL POPULATION or START INCREMENTAL POPULATION clause.</span></span> <span data-ttu-id="d2d01-116">Per ulteriori informazioni, vedere gli esempi A.</span><span class="sxs-lookup"><span data-stu-id="d2d01-116">For more information, see examples "A.</span></span> <span data-ttu-id="d2d01-117">Creazione di un indice full-text senza eseguire un popolamento completo" e "B.</span><span class="sxs-lookup"><span data-stu-id="d2d01-117">Creating a full-text index without running a full population" and "B.</span></span> <span data-ttu-id="d2d01-118">Esecuzione di un popolamento completo nella tabella", più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d2d01-118">Running a full population on table," later in this topic.</span></span>  
  

  
### <a name="change-tracking-based-population"></a><span data-ttu-id="d2d01-119">Popolamento basato sul rilevamento delle modifiche</span><span class="sxs-lookup"><span data-stu-id="d2d01-119">Change Tracking-Based Population</span></span>  
 <span data-ttu-id="d2d01-120">Facoltativamente, è possibile utilizzare il rilevamento delle modifiche per gestire un indice full-text dopo il popolamento completo iniziale.</span><span class="sxs-lookup"><span data-stu-id="d2d01-120">Optionally, you can use change tracking to maintain a full-text index after its initial full population.</span></span> <span data-ttu-id="d2d01-121">Al rilevamento delle modifiche è associato un overhead perché in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è presente una tabella nella quale vengono rilevate le modifiche apportate alla tabella di base dopo l'ultimo popolamento.</span><span class="sxs-lookup"><span data-stu-id="d2d01-121">There is a small overhead associated with change tracking because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] maintains a table in which it tracks changes to the base table since the last population.</span></span> <span data-ttu-id="d2d01-122">Quando si utilizza il rilevamento delle modifiche, in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene mantenuto un record delle righe della tabella di base o della vista indicizzata modificate tramite aggiornamenti, eliminazioni o inserimenti.</span><span class="sxs-lookup"><span data-stu-id="d2d01-122">When change tracking is used, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] maintains a record of the rows in the base table or indexed view that have been modified by updates, deletes, or inserts.</span></span> <span data-ttu-id="d2d01-123">Le modifiche apportate ai dati tramite WRITETEXT e UPDATETEXT non vengono riflesse nell'indice full-text, pertanto non vengono registrate dalla funzione di rilevamento delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="d2d01-123">Data changes through WRITETEXT and UPDATETEXT are not reflected in the full-text index, and are not picked up with change tracking.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d2d01-124">Per le tabelle che contengono una colonna `timestamp`, è possibile utilizzare i popolamenti incrementali.</span><span class="sxs-lookup"><span data-stu-id="d2d01-124">For tables containing a `timestamp` column, you can use incremental populations.</span></span>  
  
 <span data-ttu-id="d2d01-125">Quando il rilevamento delle modifiche viene abilitato durante la creazione dell'indice, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] esegue il popolamento completo del nuovo indice full-text subito dopo la creazione.</span><span class="sxs-lookup"><span data-stu-id="d2d01-125">When change tracking is enabled during index creation, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fully populates the new full-text index immediately after it is created.</span></span> <span data-ttu-id="d2d01-126">Le modifiche vengono quindi rilevate e propagate all'indice full-text.</span><span class="sxs-lookup"><span data-stu-id="d2d01-126">Thereafter, changes are tracked and propagated to the full-text index.</span></span> <span data-ttu-id="d2d01-127">Il rilevamento delle modifiche può essere di due tipi, ovvero automatico (opzione CHANGE_TRACKING AUTO) e manuale (opzione CHANGE_TRACKING MANUAL).</span><span class="sxs-lookup"><span data-stu-id="d2d01-127">There are two types of change tracking, automatic (CHANGE_TRACKING AUTO option) and manual (CHANGE_TRACKING MANUAL option).</span></span> <span data-ttu-id="d2d01-128">Il rilevamento delle modifiche automatico è il comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="d2d01-128">Automatic change tracking is the default behavior.</span></span>  
  
 <span data-ttu-id="d2d01-129">La modalità di popolamento dell'indice full-text dipende dal tipo di rilevamento delle modifiche:</span><span class="sxs-lookup"><span data-stu-id="d2d01-129">The type of change tracking determines how the full-text index is populated, as follows:</span></span>  
  
-   <span data-ttu-id="d2d01-130">Popolamento automatico</span><span class="sxs-lookup"><span data-stu-id="d2d01-130">Automatic population</span></span>  
  
     <span data-ttu-id="d2d01-131">Per impostazione predefinita o se si specifica CHANGE_TRACKING AUTO, il motore di ricerca full-text utilizza il popolamento automatico per l'indice full-text.</span><span class="sxs-lookup"><span data-stu-id="d2d01-131">By default, or if you specify CHANGE_TRACKING AUTO, the Full-Text Engine uses automatic population on the full-text index.</span></span> <span data-ttu-id="d2d01-132">Al termine del popolamento completo iniziale, le modifiche vengono rilevate man mano che i dati vengono modificati nella tabella di base e le modifiche rilevate vengono propagate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d2d01-132">After the initial full population completes, changes are tracked as data is modified in the base table, and the tracked changes are propagated automatically.</span></span> <span data-ttu-id="d2d01-133">L'indice full-text viene aggiornato in background, pertanto le modifiche propagate potrebbero non venire riflesse immediatamente nell'indice.</span><span class="sxs-lookup"><span data-stu-id="d2d01-133">The full-text index is updated in the background, however, so propagated changes might not be reflected immediately in the index.</span></span>  
  
     <span data-ttu-id="d2d01-134">**Per configurare il rilevamento delle modifiche con il popolamento automatico**</span><span class="sxs-lookup"><span data-stu-id="d2d01-134">**To set up tracking changes with automatic population**</span></span>  
  
    -   <span data-ttu-id="d2d01-135">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING AUTO</span><span class="sxs-lookup"><span data-stu-id="d2d01-135">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING AUTO</span></span>  
  
    -   <span data-ttu-id="d2d01-136">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING AUTO</span><span class="sxs-lookup"><span data-stu-id="d2d01-136">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING AUTO</span></span>  
  
     <span data-ttu-id="d2d01-137">Per ulteriori informazioni, vedere l'esempio "E.</span><span class="sxs-lookup"><span data-stu-id="d2d01-137">For more information, see example "E.</span></span> <span data-ttu-id="d2d01-138">Modifica di un indice full-text per l'utilizzo del rilevamento delle modifiche automatico", più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d2d01-138">Altering a full-text index to use automatic change tracking," later in this topic.</span></span>  
  
-   <span data-ttu-id="d2d01-139">Popolamento manuale</span><span class="sxs-lookup"><span data-stu-id="d2d01-139">Manual population</span></span>  
  
     <span data-ttu-id="d2d01-140">Se si specifica CHANGE_TRACKING MANUAL, il motore di ricerca full-text utilizza il popolamento manuale per l'indice full-text.</span><span class="sxs-lookup"><span data-stu-id="d2d01-140">If you specify CHANGE_TRACKING MANUAL, the Full-Text Engine uses manual population on the full-text index.</span></span> <span data-ttu-id="d2d01-141">Al termine del popolamento completo iniziale, le modifiche vengono rilevate man mano che i dati vengono modificati nella tabella di base.</span><span class="sxs-lookup"><span data-stu-id="d2d01-141">After the initial full population completes, changes are tracked as data is modified in the base table.</span></span> <span data-ttu-id="d2d01-142">Non vengono invece propagate nell'indice full-text finché non viene eseguita un'istruzione ALTER FULLTEXT INDEX ... START UPDATE POPULATION .</span><span class="sxs-lookup"><span data-stu-id="d2d01-142">However, they are not propagated to the full-text index until you execute an ALTER FULLTEXT INDEX ... START UPDATE POPULATION statement.</span></span> <span data-ttu-id="d2d01-143">Per chiamare questa istruzione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] periodicamente, è possibile utilizzare [!INCLUDE[tsql](../../includes/tsql-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="d2d01-143">You can use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to call this [!INCLUDE[tsql](../../includes/tsql-md.md)] statement periodically.</span></span>  
  
     <span data-ttu-id="d2d01-144">**Per avviare il rilevamento delle modifiche con il popolamento manuale**</span><span class="sxs-lookup"><span data-stu-id="d2d01-144">**To start tracking changes with manual population**</span></span>  
  
    -   <span data-ttu-id="d2d01-145">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING MANUAL</span><span class="sxs-lookup"><span data-stu-id="d2d01-145">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING MANUAL</span></span>  
  
    -   <span data-ttu-id="d2d01-146">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING MANUAL</span><span class="sxs-lookup"><span data-stu-id="d2d01-146">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING MANUAL</span></span>  
  
     <span data-ttu-id="d2d01-147">Per ulteriori informazioni, vedere gli esempi "C.</span><span class="sxs-lookup"><span data-stu-id="d2d01-147">For more information, see examples "C.</span></span> <span data-ttu-id="d2d01-148">Creazione di un indice full-text con il rilevamento delle modifiche manuale" e "D.</span><span class="sxs-lookup"><span data-stu-id="d2d01-148">Creating a full-text index with manual change tracking" and "D.</span></span> <span data-ttu-id="d2d01-149">Esecuzione di un popolamento manuale" di seguito in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d2d01-149">Running a manual population," later in this topic.</span></span>  
  
 <span data-ttu-id="d2d01-150">**Per disattivare il rilevamento delle modifiche**</span><span class="sxs-lookup"><span data-stu-id="d2d01-150">**To turn off change tracking**</span></span>  
  
-   <span data-ttu-id="d2d01-151">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING OFF</span><span class="sxs-lookup"><span data-stu-id="d2d01-151">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING OFF</span></span>  
  
-   <span data-ttu-id="d2d01-152">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING OFF</span><span class="sxs-lookup"><span data-stu-id="d2d01-152">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING OFF</span></span>  
  

  
### <a name="incremental-timestamp-based-population"></a><span data-ttu-id="d2d01-153">Popolamento incrementale basato su timestamp</span><span class="sxs-lookup"><span data-stu-id="d2d01-153">Incremental Timestamp-Based Population</span></span>  
 <span data-ttu-id="d2d01-154">Un popolamento incrementale è un meccanismo alternativo per il popolamento manuale di un indice full-text.</span><span class="sxs-lookup"><span data-stu-id="d2d01-154">An incremental population is an alternative mechanism for manually populating a full-text index.</span></span> <span data-ttu-id="d2d01-155">È possibile eseguire un popolamento incrementale per un indice full-text per il quale CHANGE_TRACKING è impostato su MANUAL o OFF.</span><span class="sxs-lookup"><span data-stu-id="d2d01-155">You can run an incremental population for a full-text index that has CHANGE_TRACKING set to MANUAL or OFF.</span></span> <span data-ttu-id="d2d01-156">Se il primo popolamento di un indice full-text è incrementale, vengono indicizzate tutte le righe e il risultato è equivalente a un popolamento completo.</span><span class="sxs-lookup"><span data-stu-id="d2d01-156">If the first population on a full-text index is an incremental population, it indexes all rows, making it equivalent to a full population.</span></span>  
  
 <span data-ttu-id="d2d01-157">Per eseguire il popolamento incrementale, è necessario che la tabella indicizzata contenga una colonna del tipo di dati `timestamp`.</span><span class="sxs-lookup"><span data-stu-id="d2d01-157">The requirement for incremental population is that the indexed table must have a column of the `timestamp` data type.</span></span> <span data-ttu-id="d2d01-158">Se non è disponibile una colonna `timestamp`, il popolamento incrementale non può essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="d2d01-158">If a `timestamp` column does not exist, incremental population cannot be performed.</span></span> <span data-ttu-id="d2d01-159">Se viene richiesto un popolamento incrementale per una tabella senza una colonna `timestamp`, verrà eseguito un popolamento completo.</span><span class="sxs-lookup"><span data-stu-id="d2d01-159">A request for incremental population on a table without a `timestamp` column results in a full population operation.</span></span> <span data-ttu-id="d2d01-160">Se alcuni metadati che interessano l'indice full-text della tabella sono stati modificati dopo l'ultimo popolamento, le richieste di popolamento vengono implementate come popolamenti completi.</span><span class="sxs-lookup"><span data-stu-id="d2d01-160">Also, if any metadata that affects the full-text index for the table has changed since the last population, incremental population requests are implemented as full populations.</span></span> <span data-ttu-id="d2d01-161">Sono incluse le modifiche ai metadati causate dall'alterazione di qualsiasi definizione di colonna, indice o indice full-text.</span><span class="sxs-lookup"><span data-stu-id="d2d01-161">This includes metadata changes caused by altering any column, index, or full-text index definitions.</span></span>  
  
 <span data-ttu-id="d2d01-162">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene utilizzata la colonna `timestamp` per identificare le righe che sono state modificate dopo l'ultimo popolamento.</span><span class="sxs-lookup"><span data-stu-id="d2d01-162">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses the `timestamp` column to identify rows that have changed since the last population.</span></span> <span data-ttu-id="d2d01-163">Il popolamento incrementale aggiorna l'indice full-text per le righe aggiunte, eliminate o modificate dopo l'ultimo popolamento o durante la sua esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d2d01-163">The incremental population then updates the full-text index for rows added, deleted, or modified after the last population, or while the last population was in progress.</span></span> <span data-ttu-id="d2d01-164">Se in una tabella vengono eseguiti molti inserimenti, l'utilizzo del popolamento incrementale può rivelarsi più efficiente dell'utilizzo del popolamento manuale.</span><span class="sxs-lookup"><span data-stu-id="d2d01-164">If a table experiences a high volume of inserts, using incremental population can be more efficient that using manual population.</span></span>  
  
 <span data-ttu-id="d2d01-165">Al termine di un popolamento, il motore di ricerca full-text registra un nuovo valore `timestamp`,</span><span class="sxs-lookup"><span data-stu-id="d2d01-165">At the end of a population, the Full-Text Engine records a new `timestamp` value.</span></span> <span data-ttu-id="d2d01-166">che corrisponde al valore `timestamp` maggiore rilevato da SQL Gatherer.</span><span class="sxs-lookup"><span data-stu-id="d2d01-166">This value is the largest `timestamp` value that SQL Gatherer has encountered.</span></span> <span data-ttu-id="d2d01-167">Questo valore verrà utilizzato all'avvio del successivo popolamento incrementale.</span><span class="sxs-lookup"><span data-stu-id="d2d01-167">This value will be used when a subsequent incremental population starts.</span></span>  
  
 <span data-ttu-id="d2d01-168">Per eseguire un popolamento incrementale, eseguire un'istruzione ALTER FULLTEXT INDEX utilizzando la clausola START INCREMENTAL POPULATION.</span><span class="sxs-lookup"><span data-stu-id="d2d01-168">To run an incremental population, execute an ALTER FULLTEXT INDEX statement using the START INCREMENTAL POPULATION clause.</span></span>  
  

  
##  <a name="examples-of-populating-full-text-indexes"></a><a name="examples"></a><span data-ttu-id="d2d01-169">Esempi di popolamento di indici full-text</span><span class="sxs-lookup"><span data-stu-id="d2d01-169">Examples of Populating Full-Text Indexes</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d2d01-170">Negli esempi inclusi in questa sezione viene utilizzata la tabella `Production.Document` o `HumanResources.JobCandidate` del database di esempio `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="d2d01-170">The examples in this section use the `Production.Document` or `HumanResources.JobCandidate` table of the `AdventureWorks` sample database.</span></span>  
  
### <a name="a-creating-a-full-text-index-without-running-a-full-population"></a><span data-ttu-id="d2d01-171">R.</span><span class="sxs-lookup"><span data-stu-id="d2d01-171">A.</span></span> <span data-ttu-id="d2d01-172">Creazione di un indice full-text senza eseguire un popolamento completo</span><span class="sxs-lookup"><span data-stu-id="d2d01-172">Creating a full-text index without running a full population</span></span>  
 <span data-ttu-id="d2d01-173">Nell'esempio seguente viene creato un indice full-text nella tabella `Production.Document` del database di esempio `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="d2d01-173">The following example creates a full-text index on the `Production.Document` table of the `AdventureWorks` sample database.</span></span> <span data-ttu-id="d2d01-174">In questo esempio viene utilizzato WITH CHANGE_TRACKING OFF, NO POPULATION per rimandare il popolamento completo iniziale.</span><span class="sxs-lookup"><span data-stu-id="d2d01-174">This example uses WITH CHANGE_TRACKING OFF, NO POPULATION to delay the initial full population.</span></span>  
  
```  
CREATE UNIQUE INDEX ui_ukDoc ON Production.Document(DocumentID);  
CREATE FULLTEXT CATALOG AW_Production_FTCat;  
CREATE FULLTEXT INDEX ON Production.Document  
(  
    Document                         --Full-text index column name   
        TYPE COLUMN FileExtension    --Name of column that contains file type information  
        Language 1033                 --1033 is LCID for the English language  
)  
    KEY INDEX ui_ukDoc  
    ON AW_Production_FTCat  
    WITH CHANGE_TRACKING OFF, NO POPULATION;  
GO  
  
```  
  
### <a name="b-running-a-full-population-on-table"></a><span data-ttu-id="d2d01-175">B.</span><span class="sxs-lookup"><span data-stu-id="d2d01-175">B.</span></span> <span data-ttu-id="d2d01-176">Esecuzione di un popolamento completo nella tabella</span><span class="sxs-lookup"><span data-stu-id="d2d01-176">Running a full population on table</span></span>  
 <span data-ttu-id="d2d01-177">Nell'esempio seguente viene eseguito un popolamento completo nella tabella `Production.Document` del database di esempio `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="d2d01-177">The following example runs a full population on the `Production.Document` table of the `AdventureWorks` sample database.</span></span>  
  
```  
ALTER FULLTEXT INDEX ON Production.Document  
   START FULL POPULATION;  
```  
  
### <a name="c-creating-a-full-text-index-with-manual-change-tracking"></a><span data-ttu-id="d2d01-178">C.</span><span class="sxs-lookup"><span data-stu-id="d2d01-178">C.</span></span> <span data-ttu-id="d2d01-179">Creazione di un indice full-text con il rilevamento delle modifiche manuale</span><span class="sxs-lookup"><span data-stu-id="d2d01-179">Creating a full-text index with manual change tracking</span></span>  
 <span data-ttu-id="d2d01-180">Nell'esempio seguente viene creato un indice full-text che utilizzerà il rilevamento delle modifiche con popolamento manuale nella tabella `HumanResources.JobCandidate` del database di esempio `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="d2d01-180">The following example creates a full-text index that will use change tracking with manual population on the `HumanResources.JobCandidate` table of the `AdventureWorks` sample database.</span></span>  
  
```  
USE AdventureWorks;  
GO  
CREATE UNIQUE INDEX ui_ukJobCand ON HumanResources.JobCandidate(JobCandidateID);  
CREATE FULLTEXT CATALOG ft AS DEFAULT;  
CREATE FULLTEXT INDEX ON HumanResources.JobCandidate(Resume)   
   KEY INDEX ui_ukJobCand   
   WITH CHANGE_TRACKING=MANUAL;  
GO  
```  
  
### <a name="d-running-a-manual-population"></a><span data-ttu-id="d2d01-181">D.</span><span class="sxs-lookup"><span data-stu-id="d2d01-181">D.</span></span> <span data-ttu-id="d2d01-182">Esecuzione di un popolamento manuale</span><span class="sxs-lookup"><span data-stu-id="d2d01-182">Running a manual population</span></span>  
 <span data-ttu-id="d2d01-183">Nell'esempio seguente viene eseguito un popolamento manuale nell'indice full-text con rilevamento delle modifiche della tabella `HumanResources.JobCandidate` del database di esempio `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="d2d01-183">The following example runs a manual population on the change-tracked full-text index of the `HumanResources.JobCandidate` table of the `AdventureWorks` sample database.</span></span>  
  
```  
USE AdventureWorks;  
GO  
ALTER FULLTEXT INDEX ON HumanResources.JobCandidate START UPDATE POPULATION;  
GO  
```  
  
### <a name="e-altering-a-full-text-index-to-use-automatic-change-tracking"></a><span data-ttu-id="d2d01-184">E.</span><span class="sxs-lookup"><span data-stu-id="d2d01-184">E.</span></span> <span data-ttu-id="d2d01-185">Modifica di un indice full-text per l'utilizzo del rilevamento delle modifiche automatico</span><span class="sxs-lookup"><span data-stu-id="d2d01-185">Altering a full-text index to use automatic change tracking</span></span>  
 <span data-ttu-id="d2d01-186">Nell'esempio seguente viene creato un indice full-text della tabella `HumanResources.JobCandidate` del database di esempio `AdventureWorks` per l'utilizzo del rilevamento delle modifiche con il popolamento automatico.</span><span class="sxs-lookup"><span data-stu-id="d2d01-186">The following example changes the full-text index of the `HumanResources.JobCandidate` table of the `AdventureWorks` sample database to use change tracking with automatic population.</span></span>  
  
```  
USE AdventureWorks;  
GO  
ALTER FULLTEXT INDEX ON HumanResources.JobCandidate SET CHANGE_TRACKING AUTO;  
GO   
```  
  

  
##  <a name="creating-or-changing-a-schedule-for-incremental-population"></a><a name="create"></a><span data-ttu-id="d2d01-187">Creazione o modifica di una pianificazione per il popolamento incrementale</span><span class="sxs-lookup"><span data-stu-id="d2d01-187">Creating or Changing a Schedule for Incremental Population</span></span>  
  
#### <a name="to-create-or-change-a-schedule-for-incremental-population-in-management-studio"></a><span data-ttu-id="d2d01-188">Per creare o modificare una pianificazione per popolamento incrementale in Management Studio</span><span class="sxs-lookup"><span data-stu-id="d2d01-188">To create or change a schedule for incremental population in Management Studio</span></span>  
  
1.  <span data-ttu-id="d2d01-189">In Esplora oggetti espandere il server.</span><span class="sxs-lookup"><span data-stu-id="d2d01-189">In Object Explorer, expand the server.</span></span>  
  
2.  <span data-ttu-id="d2d01-190">Espandere **Database**e quindi il database contenente l'indice full-text.</span><span class="sxs-lookup"><span data-stu-id="d2d01-190">Expand **Databases**, and then expand the database that contains the full-text index.</span></span>  
  
3.  <span data-ttu-id="d2d01-191">Espandere **Tabelle**.</span><span class="sxs-lookup"><span data-stu-id="d2d01-191">Expand **Tables**.</span></span>  
  
 <span data-ttu-id="d2d01-192">Fare clic con il pulsante destro del mouse sulla tabella in cui viene definito l'indice full-text, scegliere **Indice full-text**e quindi **Proprietà** dal menu di scelta rapida **Indice full-text**.</span><span class="sxs-lookup"><span data-stu-id="d2d01-192">Right-click the table on which the full-text index is defined, select **Full-Text index**, and on the **Full-Text index** context menu, click **Properties**.</span></span> <span data-ttu-id="d2d01-193">Verrà visualizzata la finestra di dialogo **Proprietà indice full-text** .</span><span class="sxs-lookup"><span data-stu-id="d2d01-193">This opens the **Full-text index Properties** dialog box.</span></span>  
  
1.  <span data-ttu-id="d2d01-194">Nel riquadro **Selezione pagina** Selezionare pianificazioni.</span><span class="sxs-lookup"><span data-stu-id="d2d01-194">In the **Select a page** pane, select Schedules.</span></span>  
  
     <span data-ttu-id="d2d01-195">Utilizzare questa pagina per creare o gestire le pianificazioni per un processo di SQL Server Agent che consente di avviare un popolamento incrementale della tabella di base o della vista indicizzata dell'indice full-text.</span><span class="sxs-lookup"><span data-stu-id="d2d01-195">Use this page to create or manage schedules for a SQL Server Agent job that starts an incremental table population on the base table or indexed view of the full-text index.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="d2d01-196">Se la tabella di base o la vista indicizzata non contiene una colonna del tipo di dati `timestamp`, viene eseguito un popolamento completo.</span><span class="sxs-lookup"><span data-stu-id="d2d01-196">If the base table or view does not contain a column of the `timestamp` data type, a full population is performed.</span></span>  
  
     <span data-ttu-id="d2d01-197">descritte di seguito:</span><span class="sxs-lookup"><span data-stu-id="d2d01-197">The options are as follows:</span></span>  
  
    -   <span data-ttu-id="d2d01-198">Per creare una nuova pianificazione, fare clic su **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="d2d01-198">To create a new schedule, click **New**.</span></span>  
  
         <span data-ttu-id="d2d01-199">Verrà visualizzata la finestra di dialogo **Nuova pianificazione tabella indicizzazione full-text** , in cui è possibile creare una pianificazione.</span><span class="sxs-lookup"><span data-stu-id="d2d01-199">This opens the **New Full-Text Indexing Table Schedule** dialog box, where you can create a schedule.</span></span> <span data-ttu-id="d2d01-200">Per salvare la pianificazione, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2d01-200">To save the schedule, click **OK**.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="d2d01-201">Dopo la chiusura della finestra di dialogo *Proprietà indice full-text*, alla nuova pianificazione viene associato un processo di SQL Server Agent, Start Incremental Table Population on*database_name*. **table_name** (Avvio popolamento incrementale tabella in nome_database.nome_tabella).</span><span class="sxs-lookup"><span data-stu-id="d2d01-201">A SQL Server Agent job (Start Incremental Table Population on *database_name*.*table_name*) is associated with a new schedule after you exit the **Full-Text Index Properties** dialog box.</span></span> <span data-ttu-id="d2d01-202">Se vengono create più pianificazioni per l'indice full-text, tutte utilizzano lo stesso processo.</span><span class="sxs-lookup"><span data-stu-id="d2d01-202">If you create multiple schedules for the full-text index, they all use the same job.</span></span>  
  
    -   <span data-ttu-id="d2d01-203">Per modificare una pianificazione, selezionarla e fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="d2d01-203">To change a schedule, select it and click **Edit**.</span></span>  
  
         <span data-ttu-id="d2d01-204">Verrà visualizzata la finestra di dialogo **Nuova pianificazione tabella indicizzazione full-text** , in cui è possibile modificare la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="d2d01-204">This opens the **New Full-Text Indexing Table Schedule** dialog box, where you can modify the schedule.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="d2d01-205">Per informazioni sulla modifica di un processo, vedere [Modificare un processo](../../ssms/agent/modify-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="d2d01-205">For information about modifying a job, see [Modify a Job](../../ssms/agent/modify-a-job.md).</span></span>  
  
    -   <span data-ttu-id="d2d01-206">Per rimuovere una pianificazione, selezionarla e fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="d2d01-206">To remove a schedule, select it and click **Delete**.</span></span>  
  
2.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  

  
##  <a name="troubleshooting-errors-in-a-full-text-population-crawl"></a><a name="crawl"></a><span data-ttu-id="d2d01-207">Risoluzione degli errori in un popolamento full-text (Ricerca per indicizzazione)</span><span class="sxs-lookup"><span data-stu-id="d2d01-207">Troubleshooting Errors in a Full-Text Population (Crawl)</span></span>  
 <span data-ttu-id="d2d01-208">Quando si verifica un errore durante una ricerca per indicizzazione, la funzionalità di registrazione corrispondente per la ricerca full-text crea e gestisce un log di tipo ricerca per indicizzazione in formato testo normale.</span><span class="sxs-lookup"><span data-stu-id="d2d01-208">When an error occurs during a crawl, the Full-Text Search crawl logging facility creates and maintains a crawl log, which is a plain text file.</span></span> <span data-ttu-id="d2d01-209">Ogni log di tipo ricerca per indicizzazione corrisponde a un catalogo full-text specifico.</span><span class="sxs-lookup"><span data-stu-id="d2d01-209">Each crawl log corresponds to a particular full-text catalog.</span></span> <span data-ttu-id="d2d01-210">Per impostazione predefinita, i log di tipo ricerca per indicizzazione per un'istanza specifica, in questo caso la prima, si trovano nella cartella %Programmi%\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\LOG.</span><span class="sxs-lookup"><span data-stu-id="d2d01-210">By default crawl logs for a given instance, in this case, the first instance, are located in %ProgramFiles%\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\LOG folder.</span></span> <span data-ttu-id="d2d01-211">Il file del log di tipo ricerca per indicizzazione segue lo schema di denominazione seguente:</span><span class="sxs-lookup"><span data-stu-id="d2d01-211">The crawl log file follows the following naming scheme:</span></span>  
  
 <span data-ttu-id="d2d01-212">SQLFT \<DatabaseID> \<FullTextCatalogID> . LOG [ \<n> ]</span><span class="sxs-lookup"><span data-stu-id="d2d01-212">SQLFT\<DatabaseID>\<FullTextCatalogID>.LOG[\<n>]</span></span>  
  
 <`DatabaseID`>  
 <span data-ttu-id="d2d01-213">ID di un database.</span><span class="sxs-lookup"><span data-stu-id="d2d01-213">The ID of a database.</span></span><span data-ttu-id="d2d01-214"> <`dbid`> è un numero a cinque cifre con zeri iniziali.</span><span class="sxs-lookup"><span data-stu-id="d2d01-214"> <`dbid`> is a five digit number with leading zeros.</span></span>  
  
 <`FullTextCatalogID`>  
 <span data-ttu-id="d2d01-215">ID del catalogo full-text.</span><span class="sxs-lookup"><span data-stu-id="d2d01-215">Full-text catalog ID.</span></span><span data-ttu-id="d2d01-216"> <`catid`> è un numero a cinque cifre con zeri iniziali.</span><span class="sxs-lookup"><span data-stu-id="d2d01-216"> <`catid`> is a five digit number with leading zeros.</span></span>  
  
 <`n`>  
 <span data-ttu-id="d2d01-217">È un numero intero che indica l'esistenza di uno o più log di tipo ricerca per indicizzazione per lo stesso catalogo full-text.</span><span class="sxs-lookup"><span data-stu-id="d2d01-217">Is an integer that indicates one or more crawl logs of the same full-text catalog exist.</span></span>  
  
 <span data-ttu-id="d2d01-218">Ad esempio, SQLFT0000500008.2 è il file del log di tipo ricerca per indicizzazione per un database con ID database = 5 e ID catalogo full-text = 8.</span><span class="sxs-lookup"><span data-stu-id="d2d01-218">For example, SQLFT0000500008.2 is the crawl log file for a database with database ID = 5, and full-text catalog ID = 8.</span></span> <span data-ttu-id="d2d01-219">Il 2 alla fine del nome file indica che sono disponibili due file del log di tipo ricerca per indicizzazione per questa coppia di database/catalogo.</span><span class="sxs-lookup"><span data-stu-id="d2d01-219">The 2 at the end of the file name indicates that there are two crawl log files for this database/catalog pair.</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="d2d01-220">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2d01-220">See Also</span></span>  
 <span data-ttu-id="d2d01-221">[sys.dm_fts_index_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d2d01-221">[sys.dm_fts_index_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql) </span></span>  
 <span data-ttu-id="d2d01-222">[Introduzione alla ricerca full-text](get-started-with-full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="d2d01-222">[Get Started with Full-Text Search](get-started-with-full-text-search.md) </span></span>  
 <span data-ttu-id="d2d01-223">[Creazione e gestione di indici full-text](create-and-manage-full-text-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="d2d01-223">[Create and Manage Full-Text Indexes](create-and-manage-full-text-indexes.md) </span></span>  
 <span data-ttu-id="d2d01-224">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d2d01-224">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span></span>  
 [<span data-ttu-id="d2d01-225">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d2d01-225">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-index-transact-sql)  
  
  
