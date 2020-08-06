---
title: Abilitare la compressione in una tabella o un indice | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.compwiz.selectaction.f1
- sql12.swb.compwiz.welcome.f1
- sql12.swb.compwiz.scriptfileoption.f1
- sql12.swb.compwiz.createjob.f1
- sql12.swb.compwiz.progress.f1
- sql12.swb.compwiz.outputoptions.f1
- sql12.swb.compwiz.compressiontype.f1
- sql12.swb.compwiz.summary.f1
helpviewer_keywords:
- data compression wizard
- compression [SQL Server], enable
ms.assetid: b7442cff-e616-475a-9c5a-5a765089e5f2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8a51c3b5e0c4e9b5624911310ce20db5a8e060a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636213"
---
# <a name="enable-compression-on-a-table-or-index"></a><span data-ttu-id="d0c77-102">Abilitare la compressione in una tabella o un indice</span><span class="sxs-lookup"><span data-stu-id="d0c77-102">Enable Compression on a Table or Index</span></span>
  <span data-ttu-id="d0c77-103">In questo argomento viene descritto come abilitare la compressione in una tabella o un indice in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0c77-103">This topic describes how to enable compression on a table or index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="d0c77-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="d0c77-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d0c77-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="d0c77-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d0c77-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="d0c77-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d0c77-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="d0c77-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d0c77-108">**Per abilitare la compressione in una tabella o un indice utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="d0c77-108">**To enable compression on a table or index, using:**</span></span>  
  
     [<span data-ttu-id="d0c77-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d0c77-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d0c77-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d0c77-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d0c77-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="d0c77-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d0c77-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="d0c77-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="d0c77-113">Le tabelle di sistema non possono essere abilitate per la compressione.</span><span class="sxs-lookup"><span data-stu-id="d0c77-113">System tables cannot be enabled for compression.</span></span>  
  
-   <span data-ttu-id="d0c77-114">Se la tabella è un heap, l'operazione di ricompilazione per la modalità ONLINE sarà a thread singolo.</span><span class="sxs-lookup"><span data-stu-id="d0c77-114">If the table is a heap, the rebuild operation for ONLINE mode will be single threaded.</span></span> <span data-ttu-id="d0c77-115">Utilizzare la modalità OFFLINE per un'operazione di ricompilazione di heap multithread.</span><span class="sxs-lookup"><span data-stu-id="d0c77-115">Use OFFLINE mode for a multi-threaded heap rebuild operation.</span></span> <span data-ttu-id="d0c77-116">Per altre informazioni sulla compressione dei dati, vedere [Compressione dei dati](data-compression.md).</span><span class="sxs-lookup"><span data-stu-id="d0c77-116">For a more information about data compression, see [Data Compression](data-compression.md).</span></span>  
  
-   <span data-ttu-id="d0c77-117">Non è possibile modificare l'impostazione di compressione di una singola partizione se la tabella include indici non allineati.</span><span class="sxs-lookup"><span data-stu-id="d0c77-117">You cannot change the compression setting of a single partition if the table has nonaligned indexes.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d0c77-118">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="d0c77-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d0c77-119">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="d0c77-119">Permissions</span></span>  
 <span data-ttu-id="d0c77-120">È richiesta l'autorizzazione ALTER per la tabella o l'indice.</span><span class="sxs-lookup"><span data-stu-id="d0c77-120">Requires ALTER permission on the table or index.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d0c77-121">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d0c77-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-enable-compression-on-a-table-or-index"></a><span data-ttu-id="d0c77-122">Per abilitare la compressione in una tabella o un indice</span><span class="sxs-lookup"><span data-stu-id="d0c77-122">To enable compression on a table or index</span></span>  
  
1.  <span data-ttu-id="d0c77-123">In Esplora oggetti espandere il database contenente la tabella che si desidera comprimere, quindi espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="d0c77-123">In Object Explorer, expand the database that contains the table that you want to compress and then expand the **Tables** folder.</span></span>  
  
2.  <span data-ttu-id="d0c77-124">Per comprimere un indice, espandere la tabella contenente l'indice che si desidera comprimere, quindi espandere la cartella **Indici** .</span><span class="sxs-lookup"><span data-stu-id="d0c77-124">To compress an index, expand the table that contains the index that you want to compress and then expand the **Indexes** folder.</span></span>  
  
3.  <span data-ttu-id="d0c77-125">Fare clic con il pulsante destro del mouse sulla tabella o sull'indice da comprimere, scegliere **Archiviazione** e selezionare **Gestione compressione...** .</span><span class="sxs-lookup"><span data-stu-id="d0c77-125">Right-click the table or index to compress, point to **Storage** and select **Manage Compression...**.</span></span>  
  
4.  <span data-ttu-id="d0c77-126">In Compressione guidata dati nella pagina **Compressione guidata dati** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d0c77-126">In the Data Compression Wizard, on the **Welcome to the Data Compression Wizard** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="d0c77-127">Nella pagina **Seleziona tipo di compressione** selezionare il tipo di compressione da applicare a ogni partizione nella tabella o nell'indice che si desidera comprimere.</span><span class="sxs-lookup"><span data-stu-id="d0c77-127">On the **Select Compression Type** page, select the compression type to apply to each partition in the table or index you want to compress.</span></span> <span data-ttu-id="d0c77-128">Al termine, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d0c77-128">When finished, click **Next**.</span></span>  
  
     <span data-ttu-id="d0c77-129">Le opzioni seguenti sono disponibili nella pagina **Seleziona tipo di compressione** :</span><span class="sxs-lookup"><span data-stu-id="d0c77-129">The following options are available on the **Select Compression Type** page:</span></span>  
  
     <span data-ttu-id="d0c77-130">Casella di controllo**Usa lo stesso tipo di compressione per tutte le partizioni**</span><span class="sxs-lookup"><span data-stu-id="d0c77-130">**Use the same compression type for all partitions** check box</span></span>  
     <span data-ttu-id="d0c77-131">Selezionare questa opzione per configurare la stessa impostazione di compressione per tutte le partizioni.</span><span class="sxs-lookup"><span data-stu-id="d0c77-131">Select to configure the same compression setting for all partitions.</span></span> <span data-ttu-id="d0c77-132">La casella di selezione viene abilitata e la colonna **Tipo di compressione** nella griglia viene disabilitata.</span><span class="sxs-lookup"><span data-stu-id="d0c77-132">This enables the selection box and disables the **Compression Type** column in the grid.</span></span> <span data-ttu-id="d0c77-133">Se viene selezionata, le opzioni nell'elenco adiacente sono **Nessuno**, **Riga**e **Pagina**.</span><span class="sxs-lookup"><span data-stu-id="d0c77-133">When selected, the options in the adjacent list are **None**, **Row**, and **Page**.</span></span>  
  
     <span data-ttu-id="d0c77-134">**Numero partizioni**</span><span class="sxs-lookup"><span data-stu-id="d0c77-134">**Partition Number**</span></span>  
     <span data-ttu-id="d0c77-135">Elenca tutte le partizioni nella tabella o nell'indice.</span><span class="sxs-lookup"><span data-stu-id="d0c77-135">Lists each partition in the table or index.</span></span> <span data-ttu-id="d0c77-136">Questa colonna è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="d0c77-136">This column is read-only.</span></span>  
  
     <span data-ttu-id="d0c77-137">**Tipo di compressione**</span><span class="sxs-lookup"><span data-stu-id="d0c77-137">**Compression Type**</span></span>  
     <span data-ttu-id="d0c77-138">Selezionare l'opzione di compressione per ciascuna partizione.</span><span class="sxs-lookup"><span data-stu-id="d0c77-138">Select the compression option for each partition.</span></span> <span data-ttu-id="d0c77-139">Questa opzione non è disponibile se **Usa lo stesso tipo di compressione per tutte le partizioni** è selezionata.</span><span class="sxs-lookup"><span data-stu-id="d0c77-139">Is not available when **Use the same compression type for all partitions** is selected.</span></span> <span data-ttu-id="d0c77-140">Le opzioni nell'elenco sono **Nessuno**, **Riga**e **Pagina**.</span><span class="sxs-lookup"><span data-stu-id="d0c77-140">List options are **None**, **Row**, and **Page**.</span></span>  
  
     <span data-ttu-id="d0c77-141">**Limite**</span><span class="sxs-lookup"><span data-stu-id="d0c77-141">**Boundary**</span></span>  
     <span data-ttu-id="d0c77-142">Visualizza il limite della partizione.</span><span class="sxs-lookup"><span data-stu-id="d0c77-142">Displays the partition boundary.</span></span> <span data-ttu-id="d0c77-143">Questa colonna è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="d0c77-143">This column is read-only.</span></span>  
  
     <span data-ttu-id="d0c77-144">**Conteggio righe**</span><span class="sxs-lookup"><span data-stu-id="d0c77-144">**Row Count**</span></span>  
     <span data-ttu-id="d0c77-145">Visualizza il numero di righe nella partizione.</span><span class="sxs-lookup"><span data-stu-id="d0c77-145">Displays the number of rows in this partition.</span></span> <span data-ttu-id="d0c77-146">Questa colonna è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="d0c77-146">This column is read-only.</span></span>  
  
     <span data-ttu-id="d0c77-147">**Spazio corrente**</span><span class="sxs-lookup"><span data-stu-id="d0c77-147">**Current Space**</span></span>  
     <span data-ttu-id="d0c77-148">Visualizza lo spazio corrente occupato dalla partizione, espresso in megabyte (MB).</span><span class="sxs-lookup"><span data-stu-id="d0c77-148">Displays the current space this partition occupies in megabytes (MB).</span></span> <span data-ttu-id="d0c77-149">Questa colonna è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="d0c77-149">This column is read-only.</span></span>  
  
     <span data-ttu-id="d0c77-150">**Spazio compresso richiesto**</span><span class="sxs-lookup"><span data-stu-id="d0c77-150">**Requested Compressed Space**</span></span>  
     <span data-ttu-id="d0c77-151">Quando si fa clic su **Calcola**, in questa colonna vengono visualizzate le dimensioni stimate di ciascuna partizione dopo la compressione eseguita mediante l'uso dell'impostazione specificata nella colonna **Tipo di compressione** .</span><span class="sxs-lookup"><span data-stu-id="d0c77-151">After you click **Calculate**, this column displays the estimated size of each partition after compression by using the setting specified in the **Compression Type** column.</span></span> <span data-ttu-id="d0c77-152">Questa colonna è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="d0c77-152">This column is read-only.</span></span>  
  
     <span data-ttu-id="d0c77-153">**Calcola**</span><span class="sxs-lookup"><span data-stu-id="d0c77-153">**Calculate**</span></span>  
     <span data-ttu-id="d0c77-154">Fare clic per eseguire la stima delle dimensioni di ciascuna partizione dopo la compressione eseguita mediante l'uso dell'impostazione specificata nella colonna **Tipo di compressione** .</span><span class="sxs-lookup"><span data-stu-id="d0c77-154">Click to estimate the size of each partition after compression by using the setting specified in the **Compression Type** column.</span></span>  
  
6.  <span data-ttu-id="d0c77-155">Nella pagina **Seleziona un'opzione di output** specificare il modo in cui si desidera completare la compressione.</span><span class="sxs-lookup"><span data-stu-id="d0c77-155">In the **Select an Output Option** page, specify how you want to complete your compression.</span></span> <span data-ttu-id="d0c77-156">Selezionare **Crea script** per creare uno script SQL in base alle pagine precedenti della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="d0c77-156">Select **Create Script** to create a SQL script based the previous pages in the wizard.</span></span> <span data-ttu-id="d0c77-157">Selezionare **Esegui immediatamente** per creare la nuova tabella partizionata dopo aver completato tutte le pagine rimanenti della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="d0c77-157">Select **Run immediately** to create the new partitioned table after completing all remaining pages in the wizard.</span></span> <span data-ttu-id="d0c77-158">Selezionare **Pianifica** per creare la nuova tabella partizionata in un momento predeterminato nel futuro.</span><span class="sxs-lookup"><span data-stu-id="d0c77-158">Select **Schedule** to create the new partitioned table at a predetermined time in the future.</span></span>  
  
     <span data-ttu-id="d0c77-159">Se si seleziona **Crea script**, in **Opzioni di scripting**sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0c77-159">If you select **Create script**, the following options are available under **Script options**:</span></span>  
  
     <span data-ttu-id="d0c77-160">**Genera script nel file**</span><span class="sxs-lookup"><span data-stu-id="d0c77-160">**Script to file**</span></span>  
     <span data-ttu-id="d0c77-161">Genera lo script come file con estensione sql.</span><span class="sxs-lookup"><span data-stu-id="d0c77-161">Generates the script as a .sql file.</span></span> <span data-ttu-id="d0c77-162">Immettere un nome di file e il percorso nella casella **Nome file** o fare clic su **Sfoglia** per aprire la finestra di dialogo **Percorso file script** .</span><span class="sxs-lookup"><span data-stu-id="d0c77-162">Enter a file name and location in the **File name** box or click **Browse** to open the **Script File Location** dialog box.</span></span> <span data-ttu-id="d0c77-163">In **Salva con nome**selezionare **Testo Unicode** o **Testo ANSI**.</span><span class="sxs-lookup"><span data-stu-id="d0c77-163">From **Save As**, select **Unicode text** or **ANSI text**.</span></span>  
  
     <span data-ttu-id="d0c77-164">**Genera script negli Appunti**</span><span class="sxs-lookup"><span data-stu-id="d0c77-164">**Script to Clipboard**</span></span>  
     <span data-ttu-id="d0c77-165">Salva lo script negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="d0c77-165">Saves the script to the Clipboard.</span></span>  
  
     <span data-ttu-id="d0c77-166">**Genera script in nuova finestra Query**</span><span class="sxs-lookup"><span data-stu-id="d0c77-166">**Script to New Query Window**</span></span>  
     <span data-ttu-id="d0c77-167">Genera lo script in una nuova finestra dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="d0c77-167">Generates the script to a new Query Editor window.</span></span> <span data-ttu-id="d0c77-168">Si tratta della selezione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d0c77-168">This is the default selection.</span></span>  
  
     <span data-ttu-id="d0c77-169">Se si seleziona **Pianifica**, fare clic su **Cambia pianificazione**.</span><span class="sxs-lookup"><span data-stu-id="d0c77-169">If you select **Schedule**, click **Change schedule**.</span></span>  
  
    1.  <span data-ttu-id="d0c77-170">Nella casella **Nome** della finestra di dialogo **Nuova pianificazione processo** immettere il nome della pianificazione del processo.</span><span class="sxs-lookup"><span data-stu-id="d0c77-170">In the **New Job Schedule** dialog box, in the **Name** box, enter the job schedule's name.</span></span>  
  
    2.  <span data-ttu-id="d0c77-171">Nell'elenco **Tipo pianificazione** selezionare il tipo di pianificazione:</span><span class="sxs-lookup"><span data-stu-id="d0c77-171">On the **Schedule type** list, select the type of schedule:</span></span>  
  
        -   <span data-ttu-id="d0c77-172">**Avvia automaticamente all'avvio di SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="d0c77-172">**Start automatically when SQL Server Agent starts**</span></span>  
  
        -   <span data-ttu-id="d0c77-173">**Avvia quando la CPU risulta inattiva**</span><span class="sxs-lookup"><span data-stu-id="d0c77-173">**Start whenever the CPUs become idle**</span></span>  
  
        -   <span data-ttu-id="d0c77-174">**Periodica**.</span><span class="sxs-lookup"><span data-stu-id="d0c77-174">**Recurring**.</span></span> <span data-ttu-id="d0c77-175">Selezionare questa opzione se la nuova tabella partizionata viene aggiornata regolarmente con nuove informazioni.</span><span class="sxs-lookup"><span data-stu-id="d0c77-175">Select this option if your new partitioned table updates with new information on a regular basis.</span></span>  
  
        -   <span data-ttu-id="d0c77-176">**Singola occorrenza**.</span><span class="sxs-lookup"><span data-stu-id="d0c77-176">**One time**.</span></span> <span data-ttu-id="d0c77-177">Si tratta della selezione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d0c77-177">This is the default selection.</span></span>  
  
    3.  <span data-ttu-id="d0c77-178">Selezionare o deselezionare la casella di controllo **Abilitata** per abilitare o disabilitare la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="d0c77-178">Select or clear the **Enabled** check box to enable or disable the schedule.</span></span>  
  
    4.  <span data-ttu-id="d0c77-179">Se si seleziona **Periodica**:</span><span class="sxs-lookup"><span data-stu-id="d0c77-179">If you select **Recurring**:</span></span>  
  
        1.  <span data-ttu-id="d0c77-180">In **Frequenza**nell'elenco **Ricorrenza** specificare la frequenza di occorrenza:</span><span class="sxs-lookup"><span data-stu-id="d0c77-180">Under **Frequency**, on the **Occurs** list, specify the frequency of occurrence:</span></span>  
  
            -   <span data-ttu-id="d0c77-181">Se si seleziona **Giornaliera**, nella casella **Ogni** immettere la frequenza in base alla quale si ripete la pianificazione del processo nei giorni.</span><span class="sxs-lookup"><span data-stu-id="d0c77-181">If you select **Daily**, in the **Recurs every** box, enter how often the job schedule repeats in days.</span></span>  
  
            -   <span data-ttu-id="d0c77-182">Se si seleziona **Settimanale**, nella casella **Ogni** immettere la frequenza in base alla quale si ripete la pianificazione del processo nelle settimane.</span><span class="sxs-lookup"><span data-stu-id="d0c77-182">If you select **Weekly**, in the **Recurs every** box, enter how often the job schedule repeats in weeks.</span></span> <span data-ttu-id="d0c77-183">Selezionare i giorni della settimana durante i quali viene eseguita la pianificazione del processo.</span><span class="sxs-lookup"><span data-stu-id="d0c77-183">Select the day or days of the week on which the job schedule is run.</span></span>  
  
            -   <span data-ttu-id="d0c77-184">Se si seleziona **Mensile**, selezionare **Giorno** oppure **Ogni**.</span><span class="sxs-lookup"><span data-stu-id="d0c77-184">If you select **Monthly**, select either **Day** or **The**.</span></span>  
  
                -   <span data-ttu-id="d0c77-185">Se si seleziona **Giorno**, immettere sia la data del mese in cui si desidera sia eseguita la pianificazione del processo sia la frequenza in base alla quale si ripete questa pianificazione nei mesi.</span><span class="sxs-lookup"><span data-stu-id="d0c77-185">If you select **Day**, enter both the date of the month you want the job schedule to run and how often the job schedule repeats in months.</span></span> <span data-ttu-id="d0c77-186">Ad esempio, se si vuole che la pianificazione del processo sia eseguita il giorno 15 del mese a mesi alterni, selezionare **Giorno** e immettere "15" nella prima casella e "2" nella seconda casella.</span><span class="sxs-lookup"><span data-stu-id="d0c77-186">For example, if you want the job schedule to run on the 15th day of the month every other month, select **Day** and enter "15" in the first box and "2" in the second box.</span></span> <span data-ttu-id="d0c77-187">Si noti che il numero più grande consentito nella seconda casella è "99".</span><span class="sxs-lookup"><span data-stu-id="d0c77-187">Please note that the largest number allowed in the second box is "99".</span></span>  
  
                -   <span data-ttu-id="d0c77-188">Se si sceglie **Ogni**, selezionare il giorno specifico della settimana del mese in cui si desidera sia eseguita la pianificazione del processo e la frequenza in base alla quale si ripete questa pianificazione nei mesi.</span><span class="sxs-lookup"><span data-stu-id="d0c77-188">If you select **The**, select the specific day of the week within the month that you want the job schedule to run and how often the job schedule repeats in months.</span></span> <span data-ttu-id="d0c77-189">Ad esempio, se si vuole che la pianificazione del processo sia eseguita l'ultimo giorno feriale del mese a mesi alterni, selezionare **Giorno**, selezionare **ultimo** nel primo elenco e **giorno feriale** nel secondo elenco, quindi immettere "2" nell'ultima casella.</span><span class="sxs-lookup"><span data-stu-id="d0c77-189">For example, if you want the job schedule to run on the last weekday of the month every other month, select **Day**, select **last** from the first list and **weekday** from the second list, and then enter "2" in the last box.</span></span> <span data-ttu-id="d0c77-190">Nei primi due elenchi è anche possibile selezionare **primo**, **secondo**, **terzo** o **quarto**, nonché i giorni della settimana specifici, ad esempio: domenica o mercoledì.</span><span class="sxs-lookup"><span data-stu-id="d0c77-190">You can also select **first**, **second**, **third**, or **fourth**, as well as specific weekdays (for example: Sunday or Wednesday) from the first two lists.</span></span> <span data-ttu-id="d0c77-191">Si noti che il numero più grande consentito nell'ultima casella è "99".</span><span class="sxs-lookup"><span data-stu-id="d0c77-191">Please note that the largest number allowed in the last box is "99".</span></span>  
  
        2.  <span data-ttu-id="d0c77-192">In **Frequenza giornaliera**specificare la frequenza in base alla quale si ripete la pianificazione del processo in quel determinato giorno:</span><span class="sxs-lookup"><span data-stu-id="d0c77-192">Under **Daily frequency**, specify how often the job schedule repeats on the day the job schedule runs:</span></span>  
  
            -   <span data-ttu-id="d0c77-193">Se si seleziona **Una sola volta alle**, immettere l'ora specifica del giorno in cui deve essere eseguita la pianificazione del processo nella casella **Una sola volta alle** .</span><span class="sxs-lookup"><span data-stu-id="d0c77-193">If you select **Occurs once at**, enter the specific time of day when the job schedule should run in the **Occurs once at** box.</span></span> <span data-ttu-id="d0c77-194">Immettere l'ora, il minuto e il secondo del giorno, nonché AM o PM.</span><span class="sxs-lookup"><span data-stu-id="d0c77-194">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
            -   <span data-ttu-id="d0c77-195">Se si seleziona **Ogni**specificare la frequenza in base alla quale la pianificazione del processo viene eseguita durante il giorno scelto in **Frequenza**.</span><span class="sxs-lookup"><span data-stu-id="d0c77-195">If you select **Occurs every**, specify how often the job schedule runs during the day chosen under **Frequency**.</span></span> <span data-ttu-id="d0c77-196">Ad esempio, se si vuole che la pianificazione del processo sia ripetuta ogni 2 ore durante il giorno scelto per questa pianificazione, selezionare **Ogni**, immettere "2" nella prima casella e quindi selezionare **ora/e** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="d0c77-196">For example, if you want the job schedule to repeat every 2 hours during the day that the job schedule is run, select **Occurs every**, enter "2" in the first box, and then select **hour(s)** from the list.</span></span> <span data-ttu-id="d0c77-197">In questo elenco è anche possibile selezionare **minuto/i** e **secondo/i**.</span><span class="sxs-lookup"><span data-stu-id="d0c77-197">From this list you can also select **minute(s)** and **second(s)**.</span></span> <span data-ttu-id="d0c77-198">Si noti che il numero più grande consentito nella prima casella è "100".</span><span class="sxs-lookup"><span data-stu-id="d0c77-198">Please note that the largest number allowed in the first box is "100".</span></span>  
  
                 <span data-ttu-id="d0c77-199">Nella casella **A partire dalle** immettere l'ora in cui dovrebbe iniziare l'esecuzione della pianificazione del processo.</span><span class="sxs-lookup"><span data-stu-id="d0c77-199">In the **Starting at** box, enter the time that the job schedule should start running.</span></span> <span data-ttu-id="d0c77-200">Nella casella **Fino alle** immettere l'ora in cui dovrebbe terminare la ripetizione della pianificazione del processo.</span><span class="sxs-lookup"><span data-stu-id="d0c77-200">In the **Ending at** box, enter the time that the job schedule should stop repeating.</span></span> <span data-ttu-id="d0c77-201">Immettere l'ora, il minuto e il secondo del giorno, nonché AM o PM.</span><span class="sxs-lookup"><span data-stu-id="d0c77-201">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
        3.  <span data-ttu-id="d0c77-202">In **Durata**di **Data inizio**immettere la data in cui si desidera sia avviata l'esecuzione della pianificazione del processo.</span><span class="sxs-lookup"><span data-stu-id="d0c77-202">Under **Duration**, in **Start date**, enter the date that you want the job schedule to start running.</span></span> <span data-ttu-id="d0c77-203">Selezionare **Data fine** o **Nessuna data di fine** per indicare quando dovrebbe terminare l'esecuzione della pianificazione del processo.</span><span class="sxs-lookup"><span data-stu-id="d0c77-203">Select **End date** or **No end date** to indicate when the job schedule should stop running.</span></span> <span data-ttu-id="d0c77-204">Se si seleziona **Data fine**immettere la data in cui si desidera venga terminata l'esecuzione della pianificazione del processo.</span><span class="sxs-lookup"><span data-stu-id="d0c77-204">If you select **End date**, enter the date that you want to job schedule to stop running.</span></span>  
  
    5.  <span data-ttu-id="d0c77-205">Se si seleziona **Singola occorrenza**, in **Singola occorrenza**, nella casella **Data** immettere la data in cui verrà eseguita la pianificazione del processo.</span><span class="sxs-lookup"><span data-stu-id="d0c77-205">If you select **One Time**, under **One-time occurrence**, in the **Date** box, enter the date that the job schedule will be run.</span></span> <span data-ttu-id="d0c77-206">Nella casella **Ora** immettere l'ora in cui verrà eseguita la pianificazione del processo.</span><span class="sxs-lookup"><span data-stu-id="d0c77-206">In the **Time** box, enter the time that the job schedule will be run.</span></span> <span data-ttu-id="d0c77-207">Immettere l'ora, il minuto e il secondo del giorno, nonché AM o PM.</span><span class="sxs-lookup"><span data-stu-id="d0c77-207">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
    6.  <span data-ttu-id="d0c77-208">In **Descrizione**in **Riepilogo**verificare che tutte le impostazioni della pianificazione del processo siano corrette.</span><span class="sxs-lookup"><span data-stu-id="d0c77-208">Under **Summary**, in **Description**, verify that all job schedule settings are correct.</span></span>  
  
    7.  <span data-ttu-id="d0c77-209">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0c77-209">Click **OK**.</span></span>  
  
     <span data-ttu-id="d0c77-210">Dopo aver completato questa pagina, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d0c77-210">After completing this page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="d0c77-211">In **Controlla selezioni** della pagina **Controlla riepilogo**espandere tutte le opzioni disponibili per verificare che tutte le impostazioni di compressione siano corrette.</span><span class="sxs-lookup"><span data-stu-id="d0c77-211">On the **Review Summary** page, under **Review your selections**, expand all available options to verify that all compression settings are correct.</span></span> <span data-ttu-id="d0c77-212">Se tutte le impostazioni sono corrette, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="d0c77-212">If everything is as expected, click **Finish**.</span></span>  
  
8.  <span data-ttu-id="d0c77-213">Nella pagina **Stato Compressione guidata** monitorare le informazioni sullo stato delle azioni della Creazione guidata partizione.</span><span class="sxs-lookup"><span data-stu-id="d0c77-213">On the **Compression Wizard Progress** page, monitor status information about the actions of the Create Partition Wizard.</span></span> <span data-ttu-id="d0c77-214">A seconda delle opzioni selezionate nella procedura guidata, la pagina di stato può contenere una o più azioni.</span><span class="sxs-lookup"><span data-stu-id="d0c77-214">Depending on the options that you selected in the wizard, the progress page might contain one or more actions.</span></span> <span data-ttu-id="d0c77-215">Nella casella superiore viene visualizzato lo stato complessivo della procedura guidata e viene indicato il numero di messaggi di stato, di errore e di avviso restituiti durante l'esecuzione della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="d0c77-215">The top box displays the overall status of the wizard and the number of status, error, and warning messages that the wizard has received.</span></span>  
  
     <span data-ttu-id="d0c77-216">Nella pagina **Stato Compressione guidata** sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0c77-216">The following options are available on the **Compression Wizard Progress** page:</span></span>  
  
     <span data-ttu-id="d0c77-217">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="d0c77-217">**Details**</span></span>  
     <span data-ttu-id="d0c77-218">Consente di visualizzare i messaggi di azione, di stato e di altro tipo restituiti dall'azione eseguita nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="d0c77-218">Provides the action, status, and any messages that are returned from action taken by the wizard.</span></span>  
  
     <span data-ttu-id="d0c77-219">**Azione**</span><span class="sxs-lookup"><span data-stu-id="d0c77-219">**Action**</span></span>  
     <span data-ttu-id="d0c77-220">Specifica il tipo e il nome di ciascuna azione.</span><span class="sxs-lookup"><span data-stu-id="d0c77-220">Specifies the type and name of each action.</span></span>  
  
     <span data-ttu-id="d0c77-221">**Status**</span><span class="sxs-lookup"><span data-stu-id="d0c77-221">**Status**</span></span>  
     <span data-ttu-id="d0c77-222">Indica se l'intera azione della procedura guidata ha restituito il valore **Esito positivo** o **Esito negativo**.</span><span class="sxs-lookup"><span data-stu-id="d0c77-222">Indicates whether the wizard action as a whole returned the value of **Success** or **Failure**.</span></span>  
  
     <span data-ttu-id="d0c77-223">**Messaggio**</span><span class="sxs-lookup"><span data-stu-id="d0c77-223">**Message**</span></span>  
     <span data-ttu-id="d0c77-224">Fornisce tutti i messaggi di errore o di avviso restituiti dal processo.</span><span class="sxs-lookup"><span data-stu-id="d0c77-224">Provides any error or warning messages that are returned from the process.</span></span>  
  
     <span data-ttu-id="d0c77-225">**Report**</span><span class="sxs-lookup"><span data-stu-id="d0c77-225">**Report**</span></span>  
     <span data-ttu-id="d0c77-226">Crea un report contenente i risultati della Creazione guidata partizione.</span><span class="sxs-lookup"><span data-stu-id="d0c77-226">Creates a report that contains the results of the Create Partition Wizard.</span></span> <span data-ttu-id="d0c77-227">Le opzioni sono **Visualizza report**, **Salva report su file**, **Copia report negli Appunti**e **Invia report per posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="d0c77-227">The options are **View Report**, **Save Report to File**, **Copy Report to Clipboard**, and **Send Report as Email**.</span></span>  
  
     <span data-ttu-id="d0c77-228">**Visualizza report**</span><span class="sxs-lookup"><span data-stu-id="d0c77-228">**View Report**</span></span>  
     <span data-ttu-id="d0c77-229">Apre la finestra di dialogo **Visualizza report** in cui è contenuto un report di testo dello stato della Creazione guidata partizione.</span><span class="sxs-lookup"><span data-stu-id="d0c77-229">Opens the **View Report** dialog box, which contains a text report of the progress of the Create Partition Wizard.</span></span>  
  
     <span data-ttu-id="d0c77-230">**Salva report su file**</span><span class="sxs-lookup"><span data-stu-id="d0c77-230">**Save Report to File**</span></span>  
     <span data-ttu-id="d0c77-231">Apre la finestra di dialogo **Salva report con nome** .</span><span class="sxs-lookup"><span data-stu-id="d0c77-231">Opens the **Save Report As** dialog box.</span></span>  
  
     <span data-ttu-id="d0c77-232">**Copia report negli Appunti**</span><span class="sxs-lookup"><span data-stu-id="d0c77-232">**Copy Report to Clipboard**</span></span>  
     <span data-ttu-id="d0c77-233">Copia i risultati del report dello stato della procedura guidata negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="d0c77-233">Copies the results of the wizard's progress report to the Clipboard.</span></span>  
  
     <span data-ttu-id="d0c77-234">**Invia report per posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="d0c77-234">**Send Report as Email**</span></span>  
     <span data-ttu-id="d0c77-235">Copia i risultati del report dello stato della procedura guidata in un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="d0c77-235">Copies the results of the wizard's progress report into an email message.</span></span>  
  
     <span data-ttu-id="d0c77-236">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="d0c77-236">When complete, click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d0c77-237">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d0c77-237">Using Transact-SQL</span></span>  
  
#### <a name="to-enable-compression-on-a-table"></a><span data-ttu-id="d0c77-238">Per abilitare la compressione in una tabella</span><span class="sxs-lookup"><span data-stu-id="d0c77-238">To enable compression on a table</span></span>  
  
1.  <span data-ttu-id="d0c77-239">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0c77-239">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d0c77-240">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="d0c77-240">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d0c77-241">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="d0c77-241">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="d0c77-242">Nell'esempio viene prima eseguita la stored procedure `sp_estimate_data_compression_savings` per restituire la dimensione stimata dell'oggetto qualora venisse utilizzata l'impostazione di compressione ROW.</span><span class="sxs-lookup"><span data-stu-id="d0c77-242">The example first executes the stored procedure `sp_estimate_data_compression_savings` to return the estimated size of the object if it were to use the ROW compression setting.</span></span> <span data-ttu-id="d0c77-243">Nell'esempio viene quindi abilitata la compressione ROW in tutte le partizioni della tabella specificata.</span><span class="sxs-lookup"><span data-stu-id="d0c77-243">The example then enables ROW compression on all partitions in the specified table.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_estimate_data_compression_savings 'Production', 'TransactionHistory', NULL, NULL, 'ROW' ;  
  
    ALTER TABLE Production.TransactionHistory REBUILD PARTITION = ALL  
    WITH (DATA_COMPRESSION = ROW);   
    GO  
    ```  
  
#### <a name="to-enable-compression-on-an-index"></a><span data-ttu-id="d0c77-244">Per abilitare la compressione in un indice</span><span class="sxs-lookup"><span data-stu-id="d0c77-244">To enable compression on an index</span></span>  
  
1.  <span data-ttu-id="d0c77-245">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0c77-245">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d0c77-246">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="d0c77-246">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d0c77-247">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="d0c77-247">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="d0c77-248">Nell'esempio viene innanzitutto eseguita una query sulla vista del catalogo `sys.indexes` per restituire il nome e `index_id` per ogni indice nella tabella `Production.TransactionHistory` .</span><span class="sxs-lookup"><span data-stu-id="d0c77-248">The example first queries the `sys.indexes` catalog view to return the name and `index_id` for each index on the `Production.TransactionHistory` table.</span></span> <span data-ttu-id="d0c77-249">Viene quindi eseguita la stored procedure `sp_estimate_data_compression_savings` per restituire la dimensione stimata dell'ID indice specificato qualora venisse usata l'impostazione di compressione PAGE.</span><span class="sxs-lookup"><span data-stu-id="d0c77-249">It then executes the stored procedure `sp_estimate_data_compression_savings` to return the estimated size of the specified index ID if it were to use the PAGE compression setting.</span></span> <span data-ttu-id="d0c77-250">Viene infine ricompilato l'ID indice 2 (`IX_TransactionHistory_ProductID`), specificando la compressione PAGE.</span><span class="sxs-lookup"><span data-stu-id="d0c77-250">Finally, the example rebuilds index ID 2 (`IX_TransactionHistory_ProductID`), specifying PAGE compression.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    SELECT name, index_id  
    FROM sys.indexes  
    WHERE OBJECT_NAME (object_id) = N'TransactionHistory';  
  
    EXEC sp_estimate_data_compression_savings   
        @schema_name = 'Production',   
        @object_name = 'TransactionHistory',  
        @index_id = 2,   
        @partition_number = NULL,   
        @data_compression = 'PAGE' ;   
  
    ALTER INDEX IX_TransactionHistory_ProductID ON Production.TransactionHistory REBUILD PARTITION = ALL WITH (DATA_COMPRESSION = PAGE);  
    GO  
    ```  
  
 <span data-ttu-id="d0c77-251">Per altre informazioni, vedere [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) e [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d0c77-251">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) and [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0c77-252">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0c77-252">See Also</span></span>  
 <span data-ttu-id="d0c77-253">[Compressione dei dati](data-compression.md) </span><span class="sxs-lookup"><span data-stu-id="d0c77-253">[Data Compression](data-compression.md) </span></span>  
 [<span data-ttu-id="d0c77-254">sp_estimate_data_compression_savings &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d0c77-254">sp_estimate_data_compression_savings &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-estimate-data-compression-savings-transact-sql)  
  
  
