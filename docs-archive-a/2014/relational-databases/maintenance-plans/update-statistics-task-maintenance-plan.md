---
title: Attività Aggiorna statistiche (Piano di manutenzione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.statistics.f1
helpviewer_keywords:
- Updates Statistics Task dialog box
ms.assetid: 22902fd0-eb39-4f18-af94-3fcb69d2a3a4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 486ef2da96785ed200900f497435117ef6437cb5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637845"
---
# <a name="update-statistics-task-maintenance-plan"></a><span data-ttu-id="1db8e-102">Attività Aggiorna statistiche (Piano di manutenzione)</span><span class="sxs-lookup"><span data-stu-id="1db8e-102">Update Statistics Task (Maintenance Plan)</span></span>
  <span data-ttu-id="1db8e-103">Usare la finestra di dialogo **Attività Aggiorna statistiche** per aggiornare le informazioni di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sui dati contenuti nelle tabelle e negli indici.</span><span class="sxs-lookup"><span data-stu-id="1db8e-103">Use the **Update Statistics Task** dialog to update [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] information about the data in the tables and indexes.</span></span> <span data-ttu-id="1db8e-104">Questa attività consente di eseguire un nuovo campionamento delle statistiche di distribuzione di tutti gli indice creati per le tabelle utente del database.</span><span class="sxs-lookup"><span data-stu-id="1db8e-104">This task resamples the distribution statistics of each index created on user tables in the database.</span></span> <span data-ttu-id="1db8e-105">Le statistiche di distribuzione vengono utilizzate da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per ottimizzare le operazioni di navigazione tra le tabelle durante l'elaborazione delle istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1db8e-105">The distribution statistics are used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to optimize navigation through tables during the processing of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="1db8e-106">Per compilare automaticamente le statistiche di distribuzione, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] esegue, per ogni indice, un campionamento periodico dei dati della tabella corrispondente</span><span class="sxs-lookup"><span data-stu-id="1db8e-106">To build the distribution statistics automatically, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] periodically samples the data in the corresponding table for each index.</span></span> <span data-ttu-id="1db8e-107">La dimensione del campione è basata sul numero di righe della tabella e sulla frequenza di modifica dei dati.</span><span class="sxs-lookup"><span data-stu-id="1db8e-107">This size of the sample is based on the number of rows in the table and the frequency of data modification.</span></span> <span data-ttu-id="1db8e-108">Questa opzione consente di eseguire un ulteriore campionamento utilizzando una determinata percentuale di dati delle tabelle.</span><span class="sxs-lookup"><span data-stu-id="1db8e-108">Use this option to perform an additional sampling using the specified percentage of data in the tables.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1db8e-109">usa queste informazioni per creare piani di query più efficienti.</span><span class="sxs-lookup"><span data-stu-id="1db8e-109">uses this information to create better query plans.</span></span>  
  
 <span data-ttu-id="1db8e-110">Questa attività esegue l'istruzione UPDATE STATISTICS.</span><span class="sxs-lookup"><span data-stu-id="1db8e-110">This task executes the UPDATE STATISTICS statement.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1db8e-111">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1db8e-111">Options</span></span>  
 <span data-ttu-id="1db8e-112">**Connection**</span><span class="sxs-lookup"><span data-stu-id="1db8e-112">**Connection**</span></span>  
 <span data-ttu-id="1db8e-113">Consente di selezionare la connessione server da utilizzare per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="1db8e-113">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="1db8e-114">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="1db8e-114">**New**</span></span>  
 <span data-ttu-id="1db8e-115">Consente di creare una nuova connessione server da utilizzare per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="1db8e-115">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="1db8e-116">La finestra di dialogo **Nuova connessione** è descritta di seguito.</span><span class="sxs-lookup"><span data-stu-id="1db8e-116">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="1db8e-117">**Database**</span><span class="sxs-lookup"><span data-stu-id="1db8e-117">**Databases**</span></span>  
 <span data-ttu-id="1db8e-118">Consente di specificare i database su cui verrà eseguita l'attività.</span><span class="sxs-lookup"><span data-stu-id="1db8e-118">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="1db8e-119">**Tutti i database**</span><span class="sxs-lookup"><span data-stu-id="1db8e-119">**All databases**</span></span>  
  
     <span data-ttu-id="1db8e-120">Consente di generare un piano per l'esecuzione di attività di manutenzione su tutti i database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ad eccezione di tempdb.</span><span class="sxs-lookup"><span data-stu-id="1db8e-120">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases, except tempdb.</span></span>  
  
-   <span data-ttu-id="1db8e-121">**Tutti i database di sistema**</span><span class="sxs-lookup"><span data-stu-id="1db8e-121">**All system databases**</span></span>  
  
     <span data-ttu-id="1db8e-122">Consente di generare un piano di manutenzione per l'esecuzione di attività di manutenzione su ogni database di sistema di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ad eccezione di tempdb.</span><span class="sxs-lookup"><span data-stu-id="1db8e-122">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except tempdb.</span></span> <span data-ttu-id="1db8e-123">Non vengono eseguite attività di manutenzione sui database creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="1db8e-123">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="1db8e-124">**Tutti i database utente**</span><span class="sxs-lookup"><span data-stu-id="1db8e-124">**All user databases**</span></span>  
  
     <span data-ttu-id="1db8e-125">Consente di generare un piano per l'esecuzione di attività di manutenzione su tutti i database creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="1db8e-125">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="1db8e-126">Nessuna attività di manutenzione viene eseguita sui database di sistema di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1db8e-126">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="1db8e-127">**Database specifici**</span><span class="sxs-lookup"><span data-stu-id="1db8e-127">**These specific databases**</span></span>  
  
     <span data-ttu-id="1db8e-128">Consente di generare un piano per l'esecuzione di attività di manutenzione solo sui database selezionati.</span><span class="sxs-lookup"><span data-stu-id="1db8e-128">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="1db8e-129">Se si sceglie questa opzione, è necessario selezionare almeno un database nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="1db8e-129">At least one database in the list must be selected if this option is chosen.</span></span>  
  
 <span data-ttu-id="1db8e-130">**Nota** I piani di manutenzione vengono eseguiti solo su database il cui livello di compatibilità è impostato su 80 o su un valore superiore.</span><span class="sxs-lookup"><span data-stu-id="1db8e-130">**Note** Maintenance plans only run against databases set to compatibility level 80 or higher.</span></span> <span data-ttu-id="1db8e-131">I database per cui è impostato un livello di compatibilità 70 o inferiore non vengono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="1db8e-131">Databases set to compatibility level 70 or lower are not displayed.</span></span>  
  
 <span data-ttu-id="1db8e-132">**Object**</span><span class="sxs-lookup"><span data-stu-id="1db8e-132">**Object**</span></span>  
 <span data-ttu-id="1db8e-133">Consente di limitare la griglia **Selezione** per visualizzare tabelle, viste o entrambe.</span><span class="sxs-lookup"><span data-stu-id="1db8e-133">Limit the **Selection** grid to display tables, views, or both.</span></span>  
  
 <span data-ttu-id="1db8e-134">**Selezione**</span><span class="sxs-lookup"><span data-stu-id="1db8e-134">**Selection**</span></span>  
 <span data-ttu-id="1db8e-135">Specificare le tabelle o gli indici su cui verrà eseguita l'attività.</span><span class="sxs-lookup"><span data-stu-id="1db8e-135">Specify the tables or indexes affected by this task.</span></span> <span data-ttu-id="1db8e-136">Questa opzione non è disponibile quando si seleziona **Tabelle e viste** nella casella Oggetto.</span><span class="sxs-lookup"><span data-stu-id="1db8e-136">Not available when **Tables and Views** is selected in the Object box.</span></span>  
  
 <span data-ttu-id="1db8e-137">**Tutte le statistiche esistenti**</span><span class="sxs-lookup"><span data-stu-id="1db8e-137">**All existing statistics**</span></span>  
 <span data-ttu-id="1db8e-138">Consente di aggiornare le statistiche sia per le colonne che per gli indici.</span><span class="sxs-lookup"><span data-stu-id="1db8e-138">Update statistics for both columns and indexes.</span></span>  
  
 <span data-ttu-id="1db8e-139">**Solo statistiche colonne**</span><span class="sxs-lookup"><span data-stu-id="1db8e-139">**Column statistics only**</span></span>  
 <span data-ttu-id="1db8e-140">Consente di aggiornare soltanto le statistiche relative alle colonne.</span><span class="sxs-lookup"><span data-stu-id="1db8e-140">Only update column statistics.</span></span>  
  
 <span data-ttu-id="1db8e-141">**Solo statistiche indici**</span><span class="sxs-lookup"><span data-stu-id="1db8e-141">**Index statistics only**</span></span>  
 <span data-ttu-id="1db8e-142">Consente di aggiornare soltanto le statistiche relative agli indici.</span><span class="sxs-lookup"><span data-stu-id="1db8e-142">Only update index statistics.</span></span>  
  
 <span data-ttu-id="1db8e-143">**Tipo analisi**</span><span class="sxs-lookup"><span data-stu-id="1db8e-143">**Scan type**</span></span>  
 <span data-ttu-id="1db8e-144">Tipo di analisi utilizzata per raccogliere statistiche aggiornate.</span><span class="sxs-lookup"><span data-stu-id="1db8e-144">Type of scan used to gather updated statistics.</span></span>  
  
 <span data-ttu-id="1db8e-145">**Analisi completa**</span><span class="sxs-lookup"><span data-stu-id="1db8e-145">**Full scan**</span></span>  
 <span data-ttu-id="1db8e-146">Consente di leggere tutte le righe della tabella o della vista per raccogliere le statistiche.</span><span class="sxs-lookup"><span data-stu-id="1db8e-146">Read all rows in the table or view to gather the statistics.</span></span>  
  
 <span data-ttu-id="1db8e-147">**Campionamento per**</span><span class="sxs-lookup"><span data-stu-id="1db8e-147">**Sample by**</span></span>  
 <span data-ttu-id="1db8e-148">Specificare la percentuale della tabella o della vista indicizzata o il numero di righe da utilizzare come campione durante la raccolta di statistiche per tabelle o viste di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="1db8e-148">Specify the percentage of the table or indexed view, or the number of rows to sample when collecting statistics for larger tables or views.</span></span>  
  
 <span data-ttu-id="1db8e-149">**Visualizza codice T-SQL**</span><span class="sxs-lookup"><span data-stu-id="1db8e-149">**View T-SQL**</span></span>  
 <span data-ttu-id="1db8e-150">Consente di visualizzare le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] eseguite sul server per questa attività, in base alle opzioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="1db8e-150">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1db8e-151">Se il numero di oggetti interessato dall'attività è elevato, la visualizzazione del codice potrebbe richiedere una considerevole quantità di tempo.</span><span class="sxs-lookup"><span data-stu-id="1db8e-151">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="1db8e-152">Finestra di dialogo Nuova connessione</span><span class="sxs-lookup"><span data-stu-id="1db8e-152">New Connection Dialog Box</span></span>  
 <span data-ttu-id="1db8e-153">**Nome connessione**</span><span class="sxs-lookup"><span data-stu-id="1db8e-153">**Connection name**</span></span>  
 <span data-ttu-id="1db8e-154">Consente di immettere un nome per la nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="1db8e-154">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="1db8e-155">**Selezionare o immettere il nome di un server**</span><span class="sxs-lookup"><span data-stu-id="1db8e-155">**Select or enter a server name**</span></span>  
 <span data-ttu-id="1db8e-156">Consente di selezionare il server a cui connettersi per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="1db8e-156">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="1db8e-157">**Aggiorna**</span><span class="sxs-lookup"><span data-stu-id="1db8e-157">**Refresh**</span></span>  
 <span data-ttu-id="1db8e-158">Consente di aggiornare l'elenco dei server disponibili.</span><span class="sxs-lookup"><span data-stu-id="1db8e-158">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="1db8e-159">**Immettere le informazioni per l'accesso al server**</span><span class="sxs-lookup"><span data-stu-id="1db8e-159">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="1db8e-160">Consente di specificare le opzioni di autenticazione per l'accesso al server.</span><span class="sxs-lookup"><span data-stu-id="1db8e-160">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="1db8e-161">**Usa la sicurezza integrata di Windows NT**</span><span class="sxs-lookup"><span data-stu-id="1db8e-161">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="1db8e-162">Consente di connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando l'autenticazione di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="1db8e-162">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="1db8e-163">**Usa nome utente e password specifici**</span><span class="sxs-lookup"><span data-stu-id="1db8e-163">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="1db8e-164">Consente di connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1db8e-164">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="1db8e-165">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="1db8e-165">This option is not available.</span></span>  
  
 <span data-ttu-id="1db8e-166">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="1db8e-166">**User name**</span></span>  
 <span data-ttu-id="1db8e-167">Consente di specificare un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da utilizzare per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="1db8e-167">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="1db8e-168">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="1db8e-168">This option is not available.</span></span>  
  
 <span data-ttu-id="1db8e-169">**Password**</span><span class="sxs-lookup"><span data-stu-id="1db8e-169">**Password**</span></span>  
 <span data-ttu-id="1db8e-170">Consente di specificare una password da utilizzare per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="1db8e-170">Provide a password to use when authenticating.</span></span> <span data-ttu-id="1db8e-171">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="1db8e-171">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1db8e-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1db8e-172">See Also</span></span>  
 [<span data-ttu-id="1db8e-173">UPDATE STATISTICS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1db8e-173">UPDATE STATISTICS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/update-statistics-transact-sql)  
  
  
