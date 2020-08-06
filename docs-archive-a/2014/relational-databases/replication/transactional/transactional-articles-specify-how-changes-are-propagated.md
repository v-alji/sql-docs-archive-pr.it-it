---
title: Specificare la modalità di propagazione delle modifiche per gli articoli transazionali | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- transactional replication, propagation methods
ms.assetid: a10c5001-22cc-4667-8f0b-3d0818dca2e9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 72d377ba89f1d393eab48bd9c918012b0f503f9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715180"
---
# <a name="specify-how-changes-are-propagated-for-transactional-articles"></a><span data-ttu-id="5e594-102">Impostazione della modalità di propagazione delle modifiche per gli articoli transazionali</span><span class="sxs-lookup"><span data-stu-id="5e594-102">Specify How Changes Are Propagated for Transactional Articles</span></span>
  <span data-ttu-id="5e594-103">La replica transazionale consente di specificare la modalità di propagazione delle modifiche dei dati dal server di pubblicazione ai Sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="5e594-103">Transactional replication allows you to specify how data changes are propagated from the Publisher to Subscribers.</span></span> <span data-ttu-id="5e594-104">Per ogni tabella pubblicata è possibile specificare una delle quattro modalità con cui ogni operazione (INSERT, UPDATE o DELETE) dovrebbe propagarsi al Sottoscrittore:</span><span class="sxs-lookup"><span data-stu-id="5e594-104">For each published table, you can specify one of four ways that each operation (INSERT, UPDATE, or DELETE) should be propagated to the Subscriber:</span></span>  
  
-   <span data-ttu-id="5e594-105">Specificare che la replica transazionale deve inserire in uno script e in un secondo momento chiamare una stored procedure per propagare le modifiche ai Sottoscrittori (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="5e594-105">Specify that transactional replication should script out and subsequently call a stored procedure to propagate changes to Subscribers (the default).</span></span>  
  
-   <span data-ttu-id="5e594-106">Specificare la necessità che la modifica si propaghi tramite un'istruzione INSERT, UPDATE o DELETE (impostazione predefinita per i Sottoscrittori in cui non è in esecuzione[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="5e594-106">Specify that the change should be propagated using an INSERT, UPDATE, or DELETE statement (the default for non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Subscribers).</span></span>  
  
-   <span data-ttu-id="5e594-107">Specificare che è necessario utilizzare una stored procedure personalizzata.</span><span class="sxs-lookup"><span data-stu-id="5e594-107">Specify that a custom stored procedure should be used.</span></span>  
  
-   <span data-ttu-id="5e594-108">Specificare che l'azione non deve essere eseguita in alcun Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="5e594-108">Specify that this action should not be performed at any Subscriber.</span></span> <span data-ttu-id="5e594-109">In tal caso le transazioni non vengono replicate.</span><span class="sxs-lookup"><span data-stu-id="5e594-109">Transactions of that type are not replicated.</span></span>  
  
 <span data-ttu-id="5e594-110">Per impostazione predefinita, la replica transazionale propaga le modifiche ai Sottoscrittori utilizzando un set di stored procedure installate in ogni Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="5e594-110">By default, transactional replication propagates changes to Subscribers through a set of stored procedures that are installed on each Subscriber.</span></span> <span data-ttu-id="5e594-111">Quando in una tabella del server di pubblicazione ha luogo un inserimento, un aggiornamento o un'eliminazione, l'operazione viene convertita in una chiamata a una stored procedure nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="5e594-111">When an insert, update or delete occurs on a table at the Publisher, the operation is translated into a call to a stored procedure at the Subscriber.</span></span> <span data-ttu-id="5e594-112">La stored procedure accetta parametri che eseguono il mapping alle colonne della tabella, consentendo a tali colonne di essere modificate nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="5e594-112">The stored procedure accepts parameters that map to the columns in the table, allowing those columns to be changed at the Subscriber.</span></span>  
  
 <span data-ttu-id="5e594-113">Per impostare il metodo di propagazione per la modifica dei dati negli articoli transazionali, vedere [Impostazione del metodo di propagazione per le modifiche ai dati negli articoli transazionali](../publish/set-the-propagation-method-for-data-changes-to-transactional-articles.md).</span><span class="sxs-lookup"><span data-stu-id="5e594-113">To set the propagation method for data changes to transactional articles, see [Set the Propagation Method for Data Changes to Transactional Articles](../publish/set-the-propagation-method-for-data-changes-to-transactional-articles.md).</span></span>  
  
## <a name="default-and-custom-stored-procedures"></a><span data-ttu-id="5e594-114">Stored procedure predefinite e personalizzate</span><span class="sxs-lookup"><span data-stu-id="5e594-114">Default and custom stored procedures</span></span>  
 <span data-ttu-id="5e594-115">Le tre procedure che la replica crea per impostazione predefinita per ogni articolo di tabella sono:</span><span class="sxs-lookup"><span data-stu-id="5e594-115">The three procedures that replication creates by default for each table article are:</span></span>  
  
-   <span data-ttu-id="5e594-116">**sp_MSins_\<** *tablename* **>** , per la gestione degli inserimenti.</span><span class="sxs-lookup"><span data-stu-id="5e594-116">**sp_MSins_\<** *tablename* **>**, which handles inserts.</span></span>  
  
-   <span data-ttu-id="5e594-117">**sp_MSupd_\<** *tablename* **>** , per la gestione degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="5e594-117">**sp_MSupd_\<** *tablename* **>**, which handles updates.</span></span>  
  
-   <span data-ttu-id="5e594-118">**sp_MSdel_\<** *tablename* **>** , per la gestione delle eliminazioni.</span><span class="sxs-lookup"><span data-stu-id="5e594-118">**sp_MSdel_\<** *tablename* **>**, which handles deletes.</span></span>  
  
 <span data-ttu-id="5e594-119">Il **\<***tablename***>** usato nella procedura dipende dal modo in cui l'articolo è stati aggiunto alla pubblicazione e dal fatto che il database di sottoscrizione contenga o meno una tabella con lo stesso nome, ma di un proprietario diverso.</span><span class="sxs-lookup"><span data-stu-id="5e594-119">The **\<***tablename***>** used in the procedure depends on how the article was added to the publication and whether the subscription database contains a table of the same name with a different owner.</span></span>  
  
 <span data-ttu-id="5e594-120">Ognuna di queste procedure può essere sostituita da una procedura personalizzata che viene specificata durante l'aggiunta di un articolo a una pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="5e594-120">Any of these procedures can be replaced with a custom procedure that you specify when adding an article to a publication.</span></span> <span data-ttu-id="5e594-121">Le procedure personalizzate vengono utilizzate se un'applicazione richiede una logica personalizzata, ad esempio l'inserimento di dati in una tabella di controllo quando una riga viene aggiornata in un Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="5e594-121">Custom procedures are used if an application requires custom logic, such as inserting data into an audit table when a row is updated at a Subscriber.</span></span> <span data-ttu-id="5e594-122">Per ulteriori informazioni sulla definizione di stored procedure personalizzate, vedere l'elenco delle procedure riportato sopra.</span><span class="sxs-lookup"><span data-stu-id="5e594-122">For more information about specifying custom stored procedures, see the how to topics listed above.</span></span>  
  
 <span data-ttu-id="5e594-123">Se si specificano le procedure di replica predefinite o le procedure personalizzate, verrà anche specificata la sintassi di chiamata per ogni procedura. Se si utilizzano le procedure predefinite, la replica selezionerà i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="5e594-123">If you specify the default replication procedures or custom procedures, you also specify call syntax for each procedure (replication selects defaults if you use the default procedures).</span></span> <span data-ttu-id="5e594-124">La sintassi di chiamata determina la struttura dei parametri forniti alla procedura e la quantità di informazioni inviate al Sottoscrittore a ogni modifica dei dati.</span><span class="sxs-lookup"><span data-stu-id="5e594-124">The call syntax determines the structure of the parameters provided to the procedure and how much information is sent to the Subscriber with each data change.</span></span> <span data-ttu-id="5e594-125">Per ulteriori informazioni, vedere la sezione "Sintassi di chiamata per le stored procedure" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="5e594-125">For more information, see the section "Call Syntax for Stored Procedures" in this topic.</span></span>  
  
### <a name="considerations-for-using-custom-stored-procedures"></a><span data-ttu-id="5e594-126">Considerazioni per l'utilizzo di stored procedure personalizzate</span><span class="sxs-lookup"><span data-stu-id="5e594-126">Considerations for Using Custom Stored Procedures</span></span>  
 <span data-ttu-id="5e594-127">È bene tenere a mente le seguenti considerazioni quando si utilizzano stored procedure personalizzate:</span><span class="sxs-lookup"><span data-stu-id="5e594-127">Keep the following considerations in mind when using custom stored procedures:</span></span>  
  
-   <span data-ttu-id="5e594-128">È necessario supportare la logica presente nella stored procedure. [!INCLUDE[msCoName](../../../includes/msconame-md.md)] non fornisce il supporto per la logica personalizzata.</span><span class="sxs-lookup"><span data-stu-id="5e594-128">You must support the logic in the stored procedure; [!INCLUDE[msCoName](../../../includes/msconame-md.md)] does not provide support for custom logic.</span></span>  
  
-   <span data-ttu-id="5e594-129">Per evitare conflitti con le transazioni utilizzate dalla replica, non utilizzare le transazioni esplicite nelle procedure personalizzate.</span><span class="sxs-lookup"><span data-stu-id="5e594-129">In order to avoid conflicts with the transactions used by replication, explicit transactions should not be used in custom procedures.</span></span>  
  
-   <span data-ttu-id="5e594-130">Lo schema nel Sottoscrittore è in genere identico allo schema nel server di pubblicazione, ma può essere anche un subset dello schema del server di pubblicazione se viene utilizzato il filtro delle colonne.</span><span class="sxs-lookup"><span data-stu-id="5e594-130">The schema at the Subscriber is typically identical to the schema at the Publisher, but can also be a subset of the Publisher schema if column filtering is used.</span></span> <span data-ttu-id="5e594-131">Tuttavia, se è necessario trasformare lo schema mentre i dati vengono spostati in modo che lo schema del Sottoscrittore non sia un subset dello schema nel server di pubblicazione, [!INCLUDE[ssISCurrent](../../../includes/ssiscurrent-md.md)] è la soluzione consigliata.</span><span class="sxs-lookup"><span data-stu-id="5e594-131">However, if you need to transform the schema as the data is moved such that the schema on the Subscriber is not a subset of the schema on the Publisher, [!INCLUDE[ssISCurrent](../../../includes/ssiscurrent-md.md)] is the recommended solution.</span></span> <span data-ttu-id="5e594-132">Per altre informazioni, vedere [SQL Server Integration Services](../../../integration-services/sql-server-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="5e594-132">For more information, see [SQL Server Integration Services](../../../integration-services/sql-server-integration-services.md).</span></span>  
  
-   <span data-ttu-id="5e594-133">Se si apportano modifiche allo schema in una tabella pubblicata, è necessario rigenerare le procedure personalizzate.</span><span class="sxs-lookup"><span data-stu-id="5e594-133">If you make schema changes to a published table, the custom procedures must be regenerated.</span></span> <span data-ttu-id="5e594-134">Per altre informazioni, vedere [Rigenerare procedure transazionali personalizzate per riflettere le modifiche dello schema](transactional-articles-regenerate-to-reflect-schema-changes.md).</span><span class="sxs-lookup"><span data-stu-id="5e594-134">For more information, see [Regenerate Custom Transactional Procedures to Reflect Schema Changes](transactional-articles-regenerate-to-reflect-schema-changes.md).</span></span>  
  
-   <span data-ttu-id="5e594-135">Se si usa un valore maggiore di 1 per il parametro **-SubscriptionStreams** dell'agente di distribuzione, sarà necessario verificare che vengano completati gli aggiornamenti alle colonne chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="5e594-135">If you use a value greater than 1 for **-SubscriptionStreams** parameter of the Distribution Agent, you must ensure that updates to primary key columns are successful.</span></span> <span data-ttu-id="5e594-136">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5e594-136">For example:</span></span>  
  
    ```  
    update ... set pk = 2 where pk = 1 -- update 1  
    update ... set pk = 3 where pk = 2 -- update 2  
    ```  
  
     <span data-ttu-id="5e594-137">Se l'agente di distribuzione utilizza più di una connessione, questi due aggiornamenti potrebbero essere replicati su diverse connessioni.</span><span class="sxs-lookup"><span data-stu-id="5e594-137">If the Distribution Agent uses more than one connection, these two updates might be replicated over different connections.</span></span> <span data-ttu-id="5e594-138">Se l'aggiornamento 1 viene applicato per primo, non vi sono problemi; se l'aggiornamento 2 viene applicato per primo, restituirà "Righe interessate 0" in quanto l'aggiornamento 1 non ha ancora avuto luogo.</span><span class="sxs-lookup"><span data-stu-id="5e594-138">If update 1 is applied first, there is no problem; if update 2 is applied first it will return '0 rows affected' because update 1 has not yet occurred.</span></span> <span data-ttu-id="5e594-139">Questa situazione viene gestita nelle procedure predefinite con la generazione di un errore se nessuna riga è interessata da un aggiornamento:</span><span class="sxs-lookup"><span data-stu-id="5e594-139">This situation is handled in the default procedures by raising an error if no rows are affected on an update:</span></span>  
  
    ```  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sys.sp_MSreplraiserror 20598  
    ```  
  
     <span data-ttu-id="5e594-140">La generazione di un errore obbliga l'agente di distribuzione a riprovare il processo di aggiornamento su una singola connessione. Il processo verrà eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="5e594-140">Raising the error forces the Distribution Agent to retry the updates over a single connection, which will succeed.</span></span> <span data-ttu-id="5e594-141">È necessario che le stored procedure personalizzate includano una logica simile.</span><span class="sxs-lookup"><span data-stu-id="5e594-141">Custom stored procedures must include similar logic.</span></span>  
  
### <a name="call-syntax-for-stored-procedures"></a><span data-ttu-id="5e594-142">Sintassi di chiamata per le stored procedure</span><span class="sxs-lookup"><span data-stu-id="5e594-142">Call syntax for stored procedures</span></span>  
 <span data-ttu-id="5e594-143">Sono disponibili cinque opzioni per la sintassi che consente di chiamare le procedure utilizzate dalla replica transazionale:</span><span class="sxs-lookup"><span data-stu-id="5e594-143">There are five options for the syntax used to call the procedures used by transactional replication:</span></span>  
  
-   <span data-ttu-id="5e594-144">Sintassi CALL.</span><span class="sxs-lookup"><span data-stu-id="5e594-144">CALL syntax.</span></span> <span data-ttu-id="5e594-145">Può essere utilizzata per gli inserimenti, gli aggiornamenti e le eliminazioni.</span><span class="sxs-lookup"><span data-stu-id="5e594-145">Can be used for inserts, updates, and deletes.</span></span> <span data-ttu-id="5e594-146">Per impostazione predefinita, la replica utilizza questa sintassi per gli inserimenti e le eliminazioni.</span><span class="sxs-lookup"><span data-stu-id="5e594-146">By default, replication uses this syntax for inserts and deletes.</span></span>  
  
-   <span data-ttu-id="5e594-147">Sintassi SCALL.</span><span class="sxs-lookup"><span data-stu-id="5e594-147">SCALL syntax.</span></span> <span data-ttu-id="5e594-148">Può essere utilizzata solo per gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="5e594-148">Can be used for updates only.</span></span> <span data-ttu-id="5e594-149">Per impostazione predefinita, la replica utilizza questa sintassi per gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="5e594-149">By default, replication uses this syntax for updates.</span></span>  
  
-   <span data-ttu-id="5e594-150">Sintassi MCALL.</span><span class="sxs-lookup"><span data-stu-id="5e594-150">MCALL syntax.</span></span> <span data-ttu-id="5e594-151">Può essere utilizzata solo per gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="5e594-151">Can be used for updates only.</span></span>  
  
-   <span data-ttu-id="5e594-152">Sintassi XCALL.</span><span class="sxs-lookup"><span data-stu-id="5e594-152">XCALL syntax.</span></span> <span data-ttu-id="5e594-153">Può essere utilizzata per gli aggiornamenti e le eliminazioni.</span><span class="sxs-lookup"><span data-stu-id="5e594-153">Can be used for updates and deletes.</span></span>  
  
-   <span data-ttu-id="5e594-154">VCALL.</span><span class="sxs-lookup"><span data-stu-id="5e594-154">VCALL.</span></span> <span data-ttu-id="5e594-155">Utilizzata per le sottoscrizioni aggiornabili.</span><span class="sxs-lookup"><span data-stu-id="5e594-155">Used for updatable subscriptions.</span></span> <span data-ttu-id="5e594-156">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="5e594-156">Internal use only.</span></span>  
  
 <span data-ttu-id="5e594-157">Questi metodi si differenziano per la quantità di dati propagati al Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="5e594-157">Each method differs in the amount of data that is propagated to the Subscriber.</span></span> <span data-ttu-id="5e594-158">Con la sintassi SCALL, ad esempio, vengono passati esclusivamente i valori delle colonne effettivamente interessate da un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="5e594-158">For example, SCALL passes in values only for the columns that are actually affected by an update.</span></span> <span data-ttu-id="5e594-159">Con la sintassi XCALL vengono invece passate tutte le colonne, interessate o meno da un aggiornamento, e tutti i valori di dati precedenti per ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="5e594-159">XCALL, by contrast, requires all columns (whether affected by an update or not) and all the old data values for each column.</span></span> <span data-ttu-id="5e594-160">In molti casi la sintassi appropriata per gli aggiornamenti è SCALL, ma se durante un aggiornamento l'applicazione in uso richiede tutti i valori di dati, è la sintassi XCALL a consentire che ciò avvenga.</span><span class="sxs-lookup"><span data-stu-id="5e594-160">In many cases, SCALL is appropriate for updates, but if your application requires all the data values during an update, XCALL allows for this.</span></span>  
  
#### <a name="call-syntax"></a><span data-ttu-id="5e594-161">Sintassi CALL</span><span class="sxs-lookup"><span data-stu-id="5e594-161">CALL Syntax</span></span>  
 <span data-ttu-id="5e594-162">Stored procedure INSERT</span><span class="sxs-lookup"><span data-stu-id="5e594-162">INSERT stored procedures</span></span>  
 <span data-ttu-id="5e594-163">Alle stored procedure che gestiscono istruzioni INSERT vengono passati i valori inseriti per tutte le colonne:</span><span class="sxs-lookup"><span data-stu-id="5e594-163">Stored procedures handling INSERT statements will be passed the inserted values for all columns:</span></span>  
  
```  
c1, c2, c3,... cn  
```  
  
 <span data-ttu-id="5e594-164">Stored procedure UPDATE</span><span class="sxs-lookup"><span data-stu-id="5e594-164">UPDATE stored procedures</span></span>  
 <span data-ttu-id="5e594-165">Alle stored procedure che gestiscono istruzioni UPDATE vengono passati i valori aggiornati per tutte le colonne definite nell'articolo, seguiti dai valori originali per le colonne chiave primaria. Non viene effettuato alcun tentativo per determinare quali colonne siano state modificate:</span><span class="sxs-lookup"><span data-stu-id="5e594-165">Stored procedures handling UPDATE statements will be passed the updated values for all columns defined in the article, followed by the original values for the primary key columns (no attempt is made to determine which columns were changed.):</span></span>  
  
```  
c1, c2, c3,... cn, pkc1, pkc2, pkc3,... pkcn  
```  
  
 <span data-ttu-id="5e594-166">Stored procedure DELETE</span><span class="sxs-lookup"><span data-stu-id="5e594-166">DELETE stored procedures</span></span>  
 <span data-ttu-id="5e594-167">Alle stored procedure che gestiscono istruzioni DELETE vengono passati i valori per le colonne chiave primaria:</span><span class="sxs-lookup"><span data-stu-id="5e594-167">Stored procedures handling DELETE statements will be passed values for the primary key columns:</span></span>  
  
```  
pkc1, pkc2, pkc3,... pkcn  
```  
  
#### <a name="scall-syntax"></a><span data-ttu-id="5e594-168">Sintassi SCALL</span><span class="sxs-lookup"><span data-stu-id="5e594-168">SCALL Syntax</span></span>  
 <span data-ttu-id="5e594-169">Stored procedure UPDATE</span><span class="sxs-lookup"><span data-stu-id="5e594-169">UPDATE stored procedures</span></span>  
 <span data-ttu-id="5e594-170">Alle stored procedure che gestiscono istruzioni UPDATE vengono passati i valori aggiornati solo per le colonne che sono state modificate, seguiti dai valori originali per le colonne di chiavi primarie e da un parametro di maschera di bit (`binary(n)`) che indica le colonne modificate.</span><span class="sxs-lookup"><span data-stu-id="5e594-170">Stored procedures handling UPDATE statements will be passed the updated values only for those columns that have changed, followed by the original values for the primary key columns, followed by a bitmask (`binary(n)`) parameter that indicates the changed columns.</span></span> <span data-ttu-id="5e594-171">Nell'esempio seguente la colonna 2 (c2) non è stata modificata:</span><span class="sxs-lookup"><span data-stu-id="5e594-171">In the following example, column 2 (c2) has not changed:</span></span>  
  
```  
c1, , c3,... cn, pkc1, pkc2, pkc3,... pkcn, bitmask  
```  
  
#### <a name="mcall-syntax"></a><span data-ttu-id="5e594-172">Sintassi MCALL</span><span class="sxs-lookup"><span data-stu-id="5e594-172">MCALL Syntax</span></span>  
 <span data-ttu-id="5e594-173">Stored procedure UPDATE</span><span class="sxs-lookup"><span data-stu-id="5e594-173">UPDATE stored procedures</span></span>  
 <span data-ttu-id="5e594-174">Alle stored procedure che gestiscono istruzioni UPDATE vengono passati i valori aggiornati per tutte le colonne definite nell'articolo, seguiti dai valori originali per le colonne di chiavi primarie e da un parametro di maschera di bit (`binary(n)`) che indica le colonne modificate:</span><span class="sxs-lookup"><span data-stu-id="5e594-174">Stored procedures handling UPDATE statements will be passed the updated values for all columns defined in the article, followed by the original values for the primary key columns, followed by a bitmask (`binary(n)`) parameter that indicates the changed columns:</span></span>  
  
```  
c1, c2, c3,... cn, pkc1, pkc2, pkc3,... pkcn, bitmask  
```  
  
#### <a name="xcall-syntax"></a><span data-ttu-id="5e594-175">Sintassi XCALL</span><span class="sxs-lookup"><span data-stu-id="5e594-175">XCALL Syntax</span></span>  
 <span data-ttu-id="5e594-176">Stored procedure UPDATE</span><span class="sxs-lookup"><span data-stu-id="5e594-176">UPDATE stored procedures</span></span>  
 <span data-ttu-id="5e594-177">Alle stored procedure che gestiscono istruzioni UPDATE vengono passati i valori originali, ovvero l'immagine precedente all'aggiornamento, per tutte le colonne definite nell'articolo, seguiti dai valori di aggiornamento, ovvero l'immagine successiva all'aggiornamento, per le stesse colonne:</span><span class="sxs-lookup"><span data-stu-id="5e594-177">Stored procedures handling UPDATE statements will be passed the original values (the before image) for all columns defined in the article, followed by the updated values (the after image) for all columns defined in the article:</span></span>  
  
```  
old-c1, old-c2, old-c3,... old-cn, c1, c2, c3,... cn,  
```  
  
 <span data-ttu-id="5e594-178">Stored procedure DELETE</span><span class="sxs-lookup"><span data-stu-id="5e594-178">DELETE stored procedures</span></span>  
 <span data-ttu-id="5e594-179">Alle stored procedure che gestiscono istruzioni DELETE vengono passati i valori originali, ovvero l'immagine precedente all'eliminazione, per tutte le colonne definite nell'articolo:</span><span class="sxs-lookup"><span data-stu-id="5e594-179">Stored procedures handling DELETE statements will be passed the original (the before image) values for all columns defined in the article:</span></span>  
  
```  
old-c1, old-c2, old-c3,... old-cn  
```  
  
> [!NOTE]  
>  <span data-ttu-id="5e594-180">Quando si utilizza la sintassi XCALL, i valori dell'immagine precedente per le colonne di tipo **text** e **image** saranno NULL.</span><span class="sxs-lookup"><span data-stu-id="5e594-180">When using XCALL, the before image values for **text** and **image** columns are expected to be NULL.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="5e594-181">Esempi</span><span class="sxs-lookup"><span data-stu-id="5e594-181">Examples</span></span>  
 <span data-ttu-id="5e594-182">Le procedure che seguono sono le procedure predefinite create per la `Vendor Table` nel database di esempio di [!INCLUDE[ssSampleDBCoShort](../../../includes/sssampledbcoshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5e594-182">The following procedures are the default procedures created for the `Vendor Table` in the [!INCLUDE[ssSampleDBCoShort](../../../includes/sssampledbcoshort-md.md)] sample database.</span></span>  
  
```  
--INSERT procedure using CALL syntax  
create procedure [sp_MSins_PurchasingVendor]   
  @c1 int,@c2 nvarchar(15),@c3 nvarchar(50),@c4 tinyint,@c5 bit,@c6 bit,@c7 nvarchar(1024),@c8 datetime  
as   
begin   
insert into [Purchasing].[Vendor]([VendorID]  
,[AccountNumber]  
,[Name]  
,[CreditRating]  
,[PreferredVendorStatus]  
,[ActiveFlag]  
,[PurchasingWebServiceURL]  
,[ModifiedDate])  
values (   
 @c1  
,@c2  
,@c3  
,@c4  
,@c5  
,@c6  
,@c7  
,@c8  
 )   
end  
go  
  
--UPDATE procedure using SCALL syntax  
create procedure [sp_MSupd_PurchasingVendor]   
 @c1 int = null,@c2 nvarchar(15) = null,@c3 nvarchar(50) = null,@c4 tinyint = null,@c5 bit = null,@c6 bit = null,@c7 nvarchar(1024) = null,@c8 datetime = null,@pkc1 int  
,@bitmap binary(2)  
as  
begin  
update [Purchasing].[Vendor] set   
 [AccountNumber] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [AccountNumber] end  
,[Name] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [Name] end  
,[CreditRating] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [CreditRating] end  
,[PreferredVendorStatus] = case substring(@bitmap,1,1) & 16 when 16 then @c5 else [PreferredVendorStatus] end  
,[ActiveFlag] = case substring(@bitmap,1,1) & 32 when 32 then @c6 else [ActiveFlag] end  
,[PurchasingWebServiceURL] = case substring(@bitmap,1,1) & 64 when 64 then @c7 else [PurchasingWebServiceURL] end  
,[ModifiedDate] = case substring(@bitmap,1,1) & 128 when 128 then @c8 else [ModifiedDate] end  
where [VendorID] = @pkc1  
if @@rowcount = 0  
    if @@microsoftversion>0x07320000  
        exec sp_MSreplraiserror 20598  
end  
go  
  
--DELETE procedure using CALL syntax  
create procedure [sp_MSdel_PurchasingVendor]   
  @pkc1 int  
as   
begin   
delete [Purchasing].[Vendor]  
where [VendorID] = @pkc1  
if @@rowcount = 0  
    if @@microsoftversion>0x07320000  
        exec sp_MSreplraiserror 20598  
end   
go  
```  
  
## <a name="see-also"></a><span data-ttu-id="5e594-183">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e594-183">See Also</span></span>  
 [<span data-ttu-id="5e594-184">Article Options for Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="5e594-184">Article Options for Transactional Replication</span></span>](article-options-for-transactional-replication.md)  
  
  
