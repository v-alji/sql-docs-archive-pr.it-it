---
title: Applicare le modifiche alla destinazione | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],applying changes
ms.assetid: 338a56db-cb14-4784-a692-468eabd30f41
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dd7ab93a299ffaab2259c3d462a5c0a69160ad5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638006"
---
# <a name="apply-the-changes-to-the-destination"></a><span data-ttu-id="98d35-102">Applicazione delle modifiche alla destinazione</span><span class="sxs-lookup"><span data-stu-id="98d35-102">Apply the Changes to the Destination</span></span>
  <span data-ttu-id="98d35-103">Nel flusso di dati di un pacchetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che esegue un caricamento incrementale dei dati delle modifiche la terza e ultima attività consistono nell'applicare le modifiche alla destinazione.</span><span class="sxs-lookup"><span data-stu-id="98d35-103">In the data flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the third and final task is to apply the changes to your destination.</span></span> <span data-ttu-id="98d35-104">Sarà necessario un componente per applicare gli inserimenti, uno per applicare gli aggiornamenti e uno per applicare le eliminazioni.</span><span class="sxs-lookup"><span data-stu-id="98d35-104">You will need one component to apply inserts, one to apply updates, and one to apply deletes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98d35-105">La seconda attività nel progettare il flusso di dati di un pacchetto che esegue un caricamento incrementale dei dati delle modifiche consiste nel separare inserimenti, aggiornamenti ed eliminazioni.</span><span class="sxs-lookup"><span data-stu-id="98d35-105">The second task in designing the data flow of a package that performs an incremental load of change data is to separate inserts, updates, and deletes.</span></span> <span data-ttu-id="98d35-106">Per altre informazioni su questo componente, vedere [Elaborare inserimenti, aggiornamenti ed eliminazioni](process-inserts-updates-and-deletes.md).</span><span class="sxs-lookup"><span data-stu-id="98d35-106">For more information about this component, see [Process Inserts, Updates, and Deletes](process-inserts-updates-and-deletes.md).</span></span> <span data-ttu-id="98d35-107">Per una descrizione del processo complessivo di creazione di un pacchetto in cui viene eseguito un caricamento incrementale dei dati delle modifiche, vedere [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="98d35-107">For a description of the overall process for creating a package that performs an incremental load of change data, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="applying-inserts"></a><span data-ttu-id="98d35-108">Applicazione di inserimenti</span><span class="sxs-lookup"><span data-stu-id="98d35-108">Applying Inserts</span></span>  
 <span data-ttu-id="98d35-109">Per applicare inserimenti, è necessario utilizzare una destinazione OLE DB in quanto le nuove righe non richiedono alcuna gestione speciale.</span><span class="sxs-lookup"><span data-stu-id="98d35-109">To apply inserts, you use an OLE DB destination because the new rows do not require any special handling.</span></span>  
  
#### <a name="to-process-inserts-by-using-an-ole-db-destination"></a><span data-ttu-id="98d35-110">Per elaborare gli inserimenti utilizzando una destinazione OLE DB</span><span class="sxs-lookup"><span data-stu-id="98d35-110">To process inserts by using an OLE DB Destination</span></span>  
  
1.  <span data-ttu-id="98d35-111">Nella scheda **Flusso di dati** aggiungere una destinazione OLE DB.</span><span class="sxs-lookup"><span data-stu-id="98d35-111">On the **Data flow** tab, add an OLE DB destination.</span></span>  
  
2.  <span data-ttu-id="98d35-112">Connettere l'output contenente gli inserimenti dalla trasformazione Suddivisione condizionale alla destinazione OLE DB.</span><span class="sxs-lookup"><span data-stu-id="98d35-112">Connect the output that contains inserts from the Conditional Split transformation to the OLE DB destination.</span></span>  
  
3.  <span data-ttu-id="98d35-113">Nella pagina **Gestione connessione**in **Editor destinazione OLE DB** selezionare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="98d35-113">In the **OLE DB Destination Editor**, on the **Connection Manager** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="98d35-114">Selezionare o creare una gestione connessione OLE DB per il database di destinazione.</span><span class="sxs-lookup"><span data-stu-id="98d35-114">Select or create an OLE DB Connection Manager for the destination database.</span></span>  
  
    2.  <span data-ttu-id="98d35-115">Selezionare un'opzione per **Modalità di accesso ai dati** e quindi selezionare la tabella di destinazione o immettere un'istruzione SQL contenente le colonne di destinazione.</span><span class="sxs-lookup"><span data-stu-id="98d35-115">Select a **Data access mode** option, and then select the destination table or enter a SQL statement that contains the destination columns.</span></span>  
  
4.  <span data-ttu-id="98d35-116">Nella pagina **Mapping** dell'editor eseguire il mapping tra le colonne appropriate dei dati delle modifiche e la tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="98d35-116">On the **Mappings** page of the editor, map the appropriate columns from the change data to the destination table.</span></span>  
  
## <a name="applying-updates"></a><span data-ttu-id="98d35-117">Applicazione di aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="98d35-117">Applying Updates</span></span>  
 <span data-ttu-id="98d35-118">Per applicare aggiornamenti, è necessario utilizzare una trasformazione Comando OLE DB.</span><span class="sxs-lookup"><span data-stu-id="98d35-118">To apply updates, you use an OLE DB Command transformation.</span></span> <span data-ttu-id="98d35-119">Viene utilizzata questa trasformazione in quanto è necessario utilizzare un'istruzione UPDATE con parametri per aggiornare una riga per volta con i nuovi valori di colonna.</span><span class="sxs-lookup"><span data-stu-id="98d35-119">You use this transformation because you have to use a parameterized UPDATE statement to update one row at a time with the new column values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98d35-120">Per applicare gli aggiornamenti, è inoltre possibile utilizzare componenti di destinazione.</span><span class="sxs-lookup"><span data-stu-id="98d35-120">You can also use destination components to apply updates.</span></span> <span data-ttu-id="98d35-121">Quando si sceglie questo approccio, è necessario utilizzare i componenti di destinazione per salvare le righe in tabelle temporanee create allo scopo.</span><span class="sxs-lookup"><span data-stu-id="98d35-121">When using this approach, you use the destination components to save the rows to temporary tables that you create for this purpose.</span></span> <span data-ttu-id="98d35-122">È quindi necessario utilizzare attività Esegui SQL per eseguire operazioni di aggiornamento bulk e di eliminazione bulk sulla destinazione dalle tabelle temporanee.</span><span class="sxs-lookup"><span data-stu-id="98d35-122">Then, you use Execute SQL tasks to perform bulk update and bulk delete operations against the destination from the temporary tables.</span></span>  
  
#### <a name="to-process-updates-by-using-an-ole-db-command-transformation"></a><span data-ttu-id="98d35-123">Per elaborare gli aggiornamenti utilizzando una trasformazione Comando OLE DB</span><span class="sxs-lookup"><span data-stu-id="98d35-123">To process updates by using an OLE DB Command transformation</span></span>  
  
1.  <span data-ttu-id="98d35-124">Nella scheda **Flusso di dati** aggiungere una trasformazione Comando OLE DB.</span><span class="sxs-lookup"><span data-stu-id="98d35-124">On the **Data flow** tab, add an OLE DB Command transformation.</span></span>  
  
2.  <span data-ttu-id="98d35-125">Connettere l'output contenente gli aggiornamenti dalla trasformazione Suddivisione condizionale alla trasformazione Comando OLE DB.</span><span class="sxs-lookup"><span data-stu-id="98d35-125">Connect the output that contains updates from the Conditional Split transformation to the OLE DB Command transformation.</span></span>  
  
3.  <span data-ttu-id="98d35-126">Nella scheda **Gestione connessione**in **Editor avanzato per Comando OLE DB** selezionare o creare una gestione connessione OLE DB per il database di destinazione.</span><span class="sxs-lookup"><span data-stu-id="98d35-126">In the **Advanced Editor for OLE DB Command**, on the **Connection Manager** tab, select or create an OLE DB Connection Manager for the destination database.</span></span>  
  
4.  <span data-ttu-id="98d35-127">Nella scheda **Proprietà componente**in **Editor avanzato per Comando OLE DB** immettere un'istruzione UPDATE con parametri per **SqlCommand**.</span><span class="sxs-lookup"><span data-stu-id="98d35-127">In the **Advanced Editor for OLE DB Command**, on the **Component Properties** tab, for **SqlCommand**, enter a parameterized UPDATE statement.</span></span>  
  
     <span data-ttu-id="98d35-128">Un'istruzione UPDATE per una tabella Customer, ad esempio, potrebbe avere la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="98d35-128">For example, an UPDATE statement for a Customer table might have the following syntax:</span></span>  
  
    ```  
    update CDCSample.Customer  
    set TerritoryID  = ?,  
        CustomerType  = ?,  
        rowguid  = ?,  
        ModifiedDate  = ?  
    where CustomerID = ?  
  
    ```  
  
5.  <span data-ttu-id="98d35-129">Nella scheda **Mapping colonne** dell'editor eseguire il mapping tra le colonne appropriate dei dati delle modifiche e i parametri nell'istruzione UPDATE.</span><span class="sxs-lookup"><span data-stu-id="98d35-129">On the **Column Mappings** tab of the editor, map the appropriate columns from the change data to the parameters in the UPDATE statement.</span></span>  
  
## <a name="applying-deletes"></a><span data-ttu-id="98d35-130">Applicazione di eliminazioni</span><span class="sxs-lookup"><span data-stu-id="98d35-130">Applying Deletes</span></span>  
 <span data-ttu-id="98d35-131">Per applicare eliminazioni, è necessario utilizzare una trasformazione Comando OLE DB.</span><span class="sxs-lookup"><span data-stu-id="98d35-131">To apply deletes, you use an OLE DB Command transformation.</span></span> <span data-ttu-id="98d35-132">Si utilizza questa trasformazione in quanto è necessario utilizzare un'istruzione DELETE con parametri che elimina una sola riga per volta in base al valore di colonna che identifica in modo univoco la riga.</span><span class="sxs-lookup"><span data-stu-id="98d35-132">You use this transformation because you have to use a parameterized DELETE statement that deletes a single row at a time based on the column value that uniquely identifies the row.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98d35-133">Per applicare le eliminazioni, è inoltre possibile utilizzare componenti di destinazione.</span><span class="sxs-lookup"><span data-stu-id="98d35-133">You can also use destination components to apply deletes.</span></span> <span data-ttu-id="98d35-134">Quando si sceglie questo approccio, è necessario utilizzare i componenti di destinazione per salvare le righe in tabelle temporanee create allo scopo.</span><span class="sxs-lookup"><span data-stu-id="98d35-134">When using this approach, you use the destination components to save the rows to temporary tables that you create for this purpose.</span></span> <span data-ttu-id="98d35-135">È quindi necessario utilizzare attività Esegui SQL per eseguire operazioni di aggiornamento bulk e di eliminazione bulk sulla destinazione dalle tabelle temporanee.</span><span class="sxs-lookup"><span data-stu-id="98d35-135">Then, you use Execute SQL tasks to perform bulk update and bulk delete operations against the destination from the temporary tables.</span></span>  
  
#### <a name="to-process-deletes-by-using-an-ole-db-command-transformation"></a><span data-ttu-id="98d35-136">Per elaborare le eliminazioni utilizzando una trasformazione Comando OLE DB</span><span class="sxs-lookup"><span data-stu-id="98d35-136">To process deletes by using an OLE DB Command transformation</span></span>  
  
1.  <span data-ttu-id="98d35-137">Nella scheda **Flusso di dati** aggiungere una trasformazione Comando OLE DB al flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="98d35-137">On the **Data flow** tab, add an OLE DB Command transformation to the data flow.</span></span>  
  
2.  <span data-ttu-id="98d35-138">Connettere l'output contenente le eliminazioni dalla trasformazione Suddivisione condizionale alla trasformazione Comando OLE DB.</span><span class="sxs-lookup"><span data-stu-id="98d35-138">Connect the output that contains deletes from the Conditional Split transformation to the OLE DB Command transformation.</span></span>  
  
3.  <span data-ttu-id="98d35-139">Aprire l'editor avanzato per configurare la trasformazione.</span><span class="sxs-lookup"><span data-stu-id="98d35-139">Open the Advanced Editor to configure the transformation.</span></span>  
  
4.  <span data-ttu-id="98d35-140">Nella scheda **Gestione connessione**in **Editor avanzato per Comando OLE DB** selezionare o creare una gestione connessione OLE DB per il database di destinazione.</span><span class="sxs-lookup"><span data-stu-id="98d35-140">In the **Advanced Editor for OLE DB Command**, on the **Connection Manager** tab, select or create an OLE DB Connection Manager for the destination database.</span></span>  
  
5.  <span data-ttu-id="98d35-141">Nella scheda **Proprietà componente**in **Editor avanzato per Comando OLE DB** immettere un'istruzione DELETE con parametri per **SqlCommand**.</span><span class="sxs-lookup"><span data-stu-id="98d35-141">In the **Advanced Editor for OLE DB Command**, on the **Component Properties** tab of the editor, for **SqlCommand**, enter a parameterized DELETE statement.</span></span>  
  
     <span data-ttu-id="98d35-142">Un'istruzione DELETE per una tabella Customer, ad esempio, potrebbe avere la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="98d35-142">For example, a DELETE statement for a Customer table might have the following syntax:</span></span>  
  
    ```  
    delete from Customer where CustomerID = ?  
  
    ```  
  
6.  <span data-ttu-id="98d35-143">Nella scheda **Mapping colonne** dell'editor eseguire il mapping tra la colonna appropriata dei dati delle modifiche e il parametro nell'istruzione DELETE.</span><span class="sxs-lookup"><span data-stu-id="98d35-143">On the **Column Mappings** tab of the editor, map the appropriate column from the change data to the parameter in the DELETE statement.</span></span>  
  
## <a name="optimizing-inserts-and-updates-by-using-merge-functionality"></a><span data-ttu-id="98d35-144">Ottimizzazione di inserimenti e aggiornamenti tramite la funzionalità MERGE</span><span class="sxs-lookup"><span data-stu-id="98d35-144">Optimizing Inserts and Updates by Using MERGE Functionality</span></span>  
 <span data-ttu-id="98d35-145">È possibile ottimizzare l'elaborazione di inserimenti e aggiornamenti combinando alcune opzioni di Change Data Capture con l'utilizzo della parola chiave MERGE di Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="98d35-145">You can optimize the processing of inserts and updates by combining certain change data capture options with the use of the Transact-SQL MERGE keyword.</span></span> <span data-ttu-id="98d35-146">Per ulteriori informazioni sulla parola chiave MERGE, vedere [MERGE &#40;Transact-SQL&#41;](/sql/t-sql/statements/merge-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="98d35-146">For more information about the MERGE keyword, see [MERGE &#40;Transact-SQL&#41;](/sql/t-sql/statements/merge-transact-sql).</span></span>  
  
 <span data-ttu-id="98d35-147">Nell'istruzione Transact-SQL che recupera i dati delle modifiche, è possibile specificare *all with merge* come valore del parametro *row_filter_option* quando si chiama la funzione **cdc.fn_cdc_get_net_changes_<capture_instance>** .</span><span class="sxs-lookup"><span data-stu-id="98d35-147">In the Transact-SQL statement that retrieves the change data, you can specify *all with merge* as the value of the *row_filter_option* parameter when you call the **cdc.fn_cdc_get_net_changes_<capture_instance>** function.</span></span> <span data-ttu-id="98d35-148">La funzione Change Data Capture ha maggiore efficacia quando non deve eseguire l'elaborazione aggiuntiva necessaria per distinguere gli inserimenti dagli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="98d35-148">This change data capture function operates more efficiently when it does not have to perform the extra processing that is required to distinguish inserts from updates.</span></span> <span data-ttu-id="98d35-149">Quando si specifica il valore di parametro *all with merge* , il valore **__$operation** dei dati delle modifiche è 1 per le eliminazioni e 5 per le modifiche prodotte da inserimenti o aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="98d35-149">When you specify the *all with merge* parameter value, the **__$operation** value of the change data is 1 for deletes or 5 for changes that were caused by inserts or updates.</span></span> <span data-ttu-id="98d35-150">Per ulteriori informazioni sulla funzione Transact-SQL usata per recuperare i dati delle modifiche, vedere [Recuperare e comprendere i dati delle modifiche](retrieve-and-understand-the-change-data.md). Dopo avere recuperato le modifiche con il valore di parametro *all with merge*, è possibile applicare le eliminazioni ed eseguire l'output delle righe rimanenti in una tabella temporanea o una tabella di staging.</span><span class="sxs-lookup"><span data-stu-id="98d35-150">For more information about the Transact-SQL function that is used to retrieve the change data, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).After retrieving changes with the *all with merge* parameter value, you can apply deletes, and output the remaining rows to a temporary table or a staging table.</span></span> <span data-ttu-id="98d35-151">In un'attività Esegui SQL a valle è quindi possibile utilizzare una singola istruzione MERGE per applicare tutti gli inserimenti o gli aggiornamenti dalla tabella di staging alla destinazione.</span><span class="sxs-lookup"><span data-stu-id="98d35-151">Then, in a downstream Execute SQL Task, you can use a single MERGE statement to apply all the inserts or updates from the staging table to the destination.</span></span>  
  
  
