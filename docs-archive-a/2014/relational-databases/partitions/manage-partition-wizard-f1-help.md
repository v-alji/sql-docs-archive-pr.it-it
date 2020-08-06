---
title: Guida sensibile al contesto della Gestione guidata partizione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.managepartition.getstart.f1
- sql12.swb.managepartition.selectoutput.f1
- sql12.swb.managepartition.partitionaction.f1
- sql12.swb.managepartition.switchout.f1
- sql12.swb.managepartition.summary.f1
- sql12.swb.managepartition.createjob.f1
- sql12.swb.managepartition.stagingtable.f1
- sql12.swb.managepartition.progress.f1
- sql12.swb.managepartition.switchin.f1
- sql12.swb.managepartition.selectswitchtables.f1
helpviewer_keywords:
- wizards [SQL Server Management Studio] See Manage Partition Wizard
ms.assetid: e2478d26-dea4-428d-98c5-aad2d2a30da8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 09b3e774168e9a48a0a387c3474b29f96081d875
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713104"
---
# <a name="manage-partition-wizard-f1-help"></a><span data-ttu-id="2013a-102">Guida sensibile al contesto della Gestione guidata partizione</span><span class="sxs-lookup"><span data-stu-id="2013a-102">Manage Partition Wizard F1 Help</span></span>
  <span data-ttu-id="2013a-103">Usare la **Gestione guidata partizione** per gestire e modificare tabelle partizionate esistenti tramite il cambio della partizione o l'implementazione di uno scenario basato su finestra temporale scorrevole.</span><span class="sxs-lookup"><span data-stu-id="2013a-103">Use the **Manage Partition Wizard** to manage and modify existing partitioned tables through partition switching or the implementation of a sliding window scenario.</span></span> <span data-ttu-id="2013a-104">Questa procedura guidata può semplificare la gestione delle partizioni e la normale migrazione di dati all'interno e all'esterno delle tabelle.</span><span class="sxs-lookup"><span data-stu-id="2013a-104">This wizard can ease the management of your partitions and simplify the regular migration of data in and out of your tables.</span></span>  
  
### <a name="to-start-the-manage-partition-wizard"></a><span data-ttu-id="2013a-105">Per avviare la Gestione guidata partizione</span><span class="sxs-lookup"><span data-stu-id="2013a-105">To start the Manage Partition Wizard</span></span>  
  
-   <span data-ttu-id="2013a-106">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]selezionare il database, fare clic con il pulsante destro del mouse sulla tabella in cui si desidera creare partizioni, scegliere **Archiviazione**e quindi fare clic su **Gestione partizione**.</span><span class="sxs-lookup"><span data-stu-id="2013a-106">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the database, right-click the table on which you want to create partitions, point to **Storage**, and then click **Manage Partition**.</span></span>  
  
     <span data-ttu-id="2013a-107">`Note`Se **Gestione partizione** non è disponibile, è possibile che sia stata selezionata una tabella che non contiene partizioni.</span><span class="sxs-lookup"><span data-stu-id="2013a-107">`Note` If **Manage Partition** is unavailable, you may have selected a table that does not contain partitions.</span></span> <span data-ttu-id="2013a-108">Fare clic su **Crea partizione** nel sottomenu **Archiviazione** e usare la **Creazione guidata partizione** per creare partizioni nella tabella.</span><span class="sxs-lookup"><span data-stu-id="2013a-108">Click **Create Partition** on the **Storage** submenu and use the **Create Partition Wizard** to create partitions in your table.</span></span>  
  
 <span data-ttu-id="2013a-109">Per informazioni generali su indici e partizioni, vedere [Tabelle e indici partizionati](partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="2013a-109">For general information about partitions and indexes, see [Partitioned Tables and Indexes](partitioned-tables-and-indexes.md).</span></span>  
  
 <span data-ttu-id="2013a-110">Questa sezione include le informazioni necessarie per gestire, modificare e implementare partizioni tramite la **Gestione guidata partizione**.</span><span class="sxs-lookup"><span data-stu-id="2013a-110">This section provides the information that is required to manage, modify, and implement partitions using the **Manage Partition Wizard**.</span></span>  
  
##  <a name="in-this-section"></a><a name="Top"></a> <span data-ttu-id="2013a-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="2013a-111">In This Section</span></span>  
 <span data-ttu-id="2013a-112">Le sezioni seguenti forniscono informazioni sulle pagine della **Gestione guidata partizione**.</span><span class="sxs-lookup"><span data-stu-id="2013a-112">The following sections provide help on the pages of the **Manage Partition Wizard**.</span></span>  
  
 [<span data-ttu-id="2013a-113">Gestione guidata partizione (pagina Selezionare un'azione relativa alla partizione)</span><span class="sxs-lookup"><span data-stu-id="2013a-113">Manage Partition Wizard (Select Partition Action Page)</span></span>](#SelectPartitionAction)  
  
 [<span data-ttu-id="2013a-114">Gestione guidata partizione (pagina Attiva)</span><span class="sxs-lookup"><span data-stu-id="2013a-114">Manage Partition Wizard (Switch In Page)</span></span>](#SwitchIn)  
  
 [<span data-ttu-id="2013a-115">Gestione guidata partizione (pagina Disattiva)</span><span class="sxs-lookup"><span data-stu-id="2013a-115">Manage Partition Wizard (Switch Out Page)</span></span>](#SwitchOut)  
  
 [<span data-ttu-id="2013a-116">Gestione guidata partizione (pagina Seleziona opzioni per la tabella di gestione temporanea)</span><span class="sxs-lookup"><span data-stu-id="2013a-116">Manage Partition Wizard (Select Staging Table Options Page)</span></span>](#StagingTableOptions)  
  
 [<span data-ttu-id="2013a-117">Gestione guidata partizione (pagina Seleziona un'opzione di output)</span><span class="sxs-lookup"><span data-stu-id="2013a-117">Manage Partition Wizard (Select Output Option Page)</span></span>](#OutputOption)  
  
 [<span data-ttu-id="2013a-118">Gestione guidata partizione (pagina Nuova pianificazione processo)</span><span class="sxs-lookup"><span data-stu-id="2013a-118">Manage Partition Wizard (New Job Schedule Page)</span></span>](#NewJob)  
  
 [<span data-ttu-id="2013a-119">Gestione guidata partizione (pagina Riepilogo)</span><span class="sxs-lookup"><span data-stu-id="2013a-119">Manage Partition Wizard (Summary Page)</span></span>](#Summary)  
  
 [<span data-ttu-id="2013a-120">Gestione guidata partizione (pagina Stato)</span><span class="sxs-lookup"><span data-stu-id="2013a-120">Manage Partition Wizard (Progress Page)</span></span>](#Progress)  
  
##  <a name="select-partition-action-page"></a><a name="SelectPartitionAction"></a> <span data-ttu-id="2013a-121">Pagina Selezionare un'azione relativa alla partizione</span><span class="sxs-lookup"><span data-stu-id="2013a-121">Select Partition Action Page</span></span>  
 <span data-ttu-id="2013a-122">Usare la pagina **Selezionare un'azione relativa alla partizione** per scegliere l'azione che si desidera eseguire sulla partizione.</span><span class="sxs-lookup"><span data-stu-id="2013a-122">Use the **Select Partition Action** page to choose the action you want to perform on your partition.</span></span>  
  
### <a name="create-a-staging-table"></a><span data-ttu-id="2013a-123">Creazione di una tabella di gestione temporanea</span><span class="sxs-lookup"><span data-stu-id="2013a-123">Create a Staging Table</span></span>  
 <span data-ttu-id="2013a-124">Il cambio della partizione rappresenta un'attività di partizionamento comune se si dispone di una tabella partizionata in e da cui si esegue regolarmente la migrazione di dati, ad esempio se si dispone di una tabella partizionata in cui vengono archiviati dati trimestrali correnti ed è necessario spostare nuovi dati e archiviare i dati precedenti al termine di ogni trimestre.</span><span class="sxs-lookup"><span data-stu-id="2013a-124">Partition switching is a common partitioning task if you have a partitioned table that you migrate data into and out of on a regular basis; for example, you have a partitioned table that stores current quarterly data, and you must move in new data and archive older data at the end of each quarter.</span></span>  
  
 <span data-ttu-id="2013a-125">La procedura guidata consente di progettare la tabella di staging con la stessa colonna di partizionamento, la stessa struttura di tabelle e colonne e gli stessi indici e di archiviare la nuova tabella nel filegroup in cui è inclusa la partizione di origine.</span><span class="sxs-lookup"><span data-stu-id="2013a-125">The wizard designs the staging table with the same partitioning column, table and column structure, and indexes, and stores the new table in the filegroup where your source partition is located.</span></span>  
  
 <span data-ttu-id="2013a-126">Per creare una tabella di staging in cui e da cui spostare i dati della partizione, selezionare **Crea tabella di staging per il cambio della partizione**.</span><span class="sxs-lookup"><span data-stu-id="2013a-126">To create a staging table to switch in or switch out partition data, select **Create a staging table for partition switching**.</span></span>  
  
### <a name="sliding-window-scenario"></a><span data-ttu-id="2013a-127">Scenario basato su finestra temporale scorrevole</span><span class="sxs-lookup"><span data-stu-id="2013a-127">Sliding Window Scenario</span></span>  
 <span data-ttu-id="2013a-128">Per gestire le partizioni in uno scenario basato su finestra temporale scorrevole, selezionare **Gestisci dati partizionati in uno scenario basato su finestra temporale scorrevole**.</span><span class="sxs-lookup"><span data-stu-id="2013a-128">To manage your partitions in a sliding-window scenario, select **Manage partitioned data in a sliding window scenario**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="2013a-129">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="2013a-129">UI element list</span></span>  
 <span data-ttu-id="2013a-130">**Crea tabella di staging per il cambio della partizione**</span><span class="sxs-lookup"><span data-stu-id="2013a-130">**Create a staging table for partition switching**</span></span>  
 <span data-ttu-id="2013a-131">Consente di creare una tabella di staging per i dati da spostare all'interno o all'esterno della tabella partizionata esistente.</span><span class="sxs-lookup"><span data-stu-id="2013a-131">Creates a staging table for the data you are switching in or switching out of the existing partitioned table.</span></span>  
  
 <span data-ttu-id="2013a-132">**Partizione di disattivazione**</span><span class="sxs-lookup"><span data-stu-id="2013a-132">**Switch out partition**</span></span>  
 <span data-ttu-id="2013a-133">Fornisce le opzioni per la rimozione di una partizione dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="2013a-133">Provides options when removing a partition from the table.</span></span>  
  
 <span data-ttu-id="2013a-134">**Partizione di attivazione**</span><span class="sxs-lookup"><span data-stu-id="2013a-134">**Switch in partition**</span></span>  
 <span data-ttu-id="2013a-135">Fornisce le opzioni per l'aggiunta di una partizione alla tabella.</span><span class="sxs-lookup"><span data-stu-id="2013a-135">Provides options when adding a partition to the table.</span></span>  
  
 <span data-ttu-id="2013a-136">**Gestisci dati partizionati in uno scenario basato su finestra temporale scorrevole**</span><span class="sxs-lookup"><span data-stu-id="2013a-136">**Manage partitioned data in a sliding window scenario**</span></span>  
 <span data-ttu-id="2013a-137">Consente di aggiungere una partizione vuota alla tabella esistente da utilizzare per spostare i dati.</span><span class="sxs-lookup"><span data-stu-id="2013a-137">Appends an empty partition to the existing table that can be used for switching in data.</span></span> <span data-ttu-id="2013a-138">La procedura guidata supporta attualmente lo spostamento all'interno dell'ultima partizione e all'esterno della prima partizione.</span><span class="sxs-lookup"><span data-stu-id="2013a-138">The wizard currently supports switching into the last partition and switching out the first partition.</span></span>  
  
 <span data-ttu-id="2013a-139">![Icona freccia usata con il collegamento Torna all'inizio](../../2014-toc/media/uparrow16x16.gif "Icona freccia usata con il collegamento Torna all'inizio") [In questa sezione](#Top)</span><span class="sxs-lookup"><span data-stu-id="2013a-139">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="select-partition-switching-in-options-page"></a><a name="SwitchIn"></a> <span data-ttu-id="2013a-140">Pagina Seleziona opzioni per l'attivazione della partizione</span><span class="sxs-lookup"><span data-stu-id="2013a-140">Select Partition Switching-In Options Page</span></span>  
 <span data-ttu-id="2013a-141">Usare la pagina **Seleziona opzioni per l'attivazione della partizione** per selezionare la tabella di staging che si desidera attivare nella tabella partizionata.</span><span class="sxs-lookup"><span data-stu-id="2013a-141">Use the **Select Partition Switching-In options** page to select the staging table you are switching into the partitioned table.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="2013a-142">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="2013a-142">UI element list</span></span>  
 <span data-ttu-id="2013a-143">**Mostra tutte le partizioni**</span><span class="sxs-lookup"><span data-stu-id="2013a-143">**Show All Partitions**</span></span>  
 <span data-ttu-id="2013a-144">Selezionare questa opzione per visualizzare tutte le partizioni, incluse le partizioni correnti nella tabella partizionata.</span><span class="sxs-lookup"><span data-stu-id="2013a-144">Select to show all partitions, including the partitions currently in the partitioned table.</span></span>  
  
 <span data-ttu-id="2013a-145">**Griglia partizione**</span><span class="sxs-lookup"><span data-stu-id="2013a-145">**Partition grid**</span></span>  
 <span data-ttu-id="2013a-146">Consente di visualizzare il nome della partizione e i valori per **Limite sinistro**, **Limite destro**, **Filegroup**e **Conteggio righe** delle partizioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="2013a-146">Displays the partition name, **Left boundary**, **Right boundary**, **Filegroup**, and **Row count** of the partitions you selected.</span></span>  
  
 <span data-ttu-id="2013a-147">**Tabella di attivazione**</span><span class="sxs-lookup"><span data-stu-id="2013a-147">**Switch in table**</span></span>  
 <span data-ttu-id="2013a-148">Consente di selezionare la tabella di staging contenente la partizione che si desidera aggiungere alla tabella partizionata.</span><span class="sxs-lookup"><span data-stu-id="2013a-148">Select the staging table that contains the partition that you want to add to your partitioned table.</span></span> <span data-ttu-id="2013a-149">È necessario creare questa tabella di staging prima di attivare partizioni usando la **Gestione guidata partizione**.</span><span class="sxs-lookup"><span data-stu-id="2013a-149">You must create this staging table before you switch-in partitions with the **Manage PartitionsWizard**.</span></span>  
  
 <span data-ttu-id="2013a-150">![Icona freccia usata con il collegamento Torna all'inizio](../../2014-toc/media/uparrow16x16.gif "Icona freccia usata con il collegamento Torna all'inizio") [In questa sezione](#Top)</span><span class="sxs-lookup"><span data-stu-id="2013a-150">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="select-partition-switching-out-options-page"></a><a name="SwitchOut"></a> <span data-ttu-id="2013a-151">Pagina Seleziona opzioni per la disattivazione della partizione</span><span class="sxs-lookup"><span data-stu-id="2013a-151">Select Partition Switching-Out Options Page</span></span>  
 <span data-ttu-id="2013a-152">Usare la pagina **Seleziona opzioni per la disattivazione della partizione** per selezionare la partizione e la tabella di staging contenente i dati partizionati che si desidera disattivare dalla tabella partizionata.</span><span class="sxs-lookup"><span data-stu-id="2013a-152">Use the **Select Partition Switching-Out options** page to select the partition and the staging table to hold the partitioned data that you are switching out of the partitioned table.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="2013a-153">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="2013a-153">UI element list</span></span>  
 <span data-ttu-id="2013a-154">**Griglia partizione**</span><span class="sxs-lookup"><span data-stu-id="2013a-154">**Partition grid**</span></span>  
 <span data-ttu-id="2013a-155">Consente di visualizzare il nome della partizione e i valori per **Limite sinistro**, **Limite destro**, **Filegroup**e **Conteggio righe** delle partizioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="2013a-155">Displays the partition name, **Left boundary**, **Right boundary**, **Filegroup**, and **Row count** of the partitions you selected.</span></span>  
  
 <span data-ttu-id="2013a-156">**Tabella di disattivazione**</span><span class="sxs-lookup"><span data-stu-id="2013a-156">**Switch out table**</span></span>  
 <span data-ttu-id="2013a-157">Consente di scegliere una nuova tabella o una esistente in cui spostare i dati.</span><span class="sxs-lookup"><span data-stu-id="2013a-157">Choose a new table or an existing table to switch-out your data to.</span></span>  
  
 <span data-ttu-id="2013a-158">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="2013a-158">**New**</span></span>  
 <span data-ttu-id="2013a-159">Consente di immettere un nuovo nome per la tabella di staging che si desidera utilizzare per la partizione da disattivare per la tabella di origine corrente.</span><span class="sxs-lookup"><span data-stu-id="2013a-159">Enter a new name for the staging table you want to use for the partition to switch out of the current source table.</span></span>  
  
 <span data-ttu-id="2013a-160">**Esistente**</span><span class="sxs-lookup"><span data-stu-id="2013a-160">**Existing**</span></span>  
 <span data-ttu-id="2013a-161">Consente di selezionare una tabella di staging esistente che si desidera utilizzare per la partizione che si desidera disattivare per la tabella di origine corrente.</span><span class="sxs-lookup"><span data-stu-id="2013a-161">Select an existing staging table you want to use for the partition you want to switch out of the current source table.</span></span> <span data-ttu-id="2013a-162">Gli eventuali dati contenuti nella tabella verranno sovrascritti con i dati utilizzati per la disattivazione.</span><span class="sxs-lookup"><span data-stu-id="2013a-162">If the existing table contains data, this data will be overwritten with the data you are switching out.</span></span>  
  
 <span data-ttu-id="2013a-163">![Icona freccia usata con il collegamento Torna all'inizio](../../2014-toc/media/uparrow16x16.gif "Icona freccia usata con il collegamento Torna all'inizio") [In questa sezione](#Top)</span><span class="sxs-lookup"><span data-stu-id="2013a-163">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="select-the-staging-table-options-page"></a><a name="StagingTableOptions"></a> <span data-ttu-id="2013a-164">Pagina Seleziona opzioni per la tabella di gestione temporanea</span><span class="sxs-lookup"><span data-stu-id="2013a-164">Select the Staging Table Options Page</span></span>  
 <span data-ttu-id="2013a-165">Usare la pagina **Seleziona opzioni per la tabella di staging** per creare la tabella di staging che si desidera utilizzare per lo spostamento dei dati partizionati.</span><span class="sxs-lookup"><span data-stu-id="2013a-165">Use the **Select the Staging Table Options** page to create the staging table you want to use for switching your partitioned data.</span></span>  
  
 <span data-ttu-id="2013a-166">Le tabelle di gestione temporanea devono risiedere nello stesso filegroup della partizione selezionata in cui è presente la tabella di origine.</span><span class="sxs-lookup"><span data-stu-id="2013a-166">Staging tables must reside in the same filegroup of the selected partition where the source table is located.</span></span> <span data-ttu-id="2013a-167">La tabella di staging deve riflettere la struttura della tabella di origine e della tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2013a-167">The staging table must mirror the design of both the source table and the destination table.</span></span>  
  
 <span data-ttu-id="2013a-168">È inoltre possibile creare gli stessi indici nella tabella di staging presenti nella partizione di origine.</span><span class="sxs-lookup"><span data-stu-id="2013a-168">You can also create the same indexes in the staging table that exist in the source partition.</span></span> <span data-ttu-id="2013a-169">La tabella di staging contiene automaticamente un vincolo basato sugli elementi della partizione di origine.</span><span class="sxs-lookup"><span data-stu-id="2013a-169">The staging table automatically contains a constraint based on the elements of the source partition.</span></span> <span data-ttu-id="2013a-170">In genere tale vincolo viene generato dal valore limite della partizione di origine.</span><span class="sxs-lookup"><span data-stu-id="2013a-170">This constraint is typically generated from the boundary value of the source partition.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="2013a-171">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="2013a-171">UI element list</span></span>  
 <span data-ttu-id="2013a-172">**Nome tabella di gestione temporanea**</span><span class="sxs-lookup"><span data-stu-id="2013a-172">**Staging table name**</span></span>  
 <span data-ttu-id="2013a-173">Consente di creare un nome per la tabella di staging o di accettare il nome predefinito visualizzato nella casella di modifica.</span><span class="sxs-lookup"><span data-stu-id="2013a-173">Create a name for the staging table or accept the default name displayed in the edit box.</span></span>  
  
 <span data-ttu-id="2013a-174">**Cambia partizione**</span><span class="sxs-lookup"><span data-stu-id="2013a-174">**Switch partition**</span></span>  
 <span data-ttu-id="2013a-175">Consente di selezionare la partizione di origine che si desidera rimuovere dalla tabella corrente.</span><span class="sxs-lookup"><span data-stu-id="2013a-175">Select the source partition that you want to switch out of the current table.</span></span>  
  
 <span data-ttu-id="2013a-176">**Nuovo valore limite**</span><span class="sxs-lookup"><span data-stu-id="2013a-176">**New boundary value**</span></span>  
 <span data-ttu-id="2013a-177">Consente di selezionare o di immettere il valore limite desiderato per la partizione nella tabella di staging.</span><span class="sxs-lookup"><span data-stu-id="2013a-177">Select or enter the boundary value you want for the partition in the staging table.</span></span>  
  
 <span data-ttu-id="2013a-178">**Filegroup**</span><span class="sxs-lookup"><span data-stu-id="2013a-178">**Filegroup**</span></span>  
 <span data-ttu-id="2013a-179">Consente di selezionare un filegroup per la nuova tabella.</span><span class="sxs-lookup"><span data-stu-id="2013a-179">Select a filegroup for the new table.</span></span>  
  
 <span data-ttu-id="2013a-180">![Icona freccia usata con il collegamento Torna all'inizio](../../2014-toc/media/uparrow16x16.gif "Icona freccia usata con il collegamento Torna all'inizio") [In questa sezione](#Top)</span><span class="sxs-lookup"><span data-stu-id="2013a-180">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="select-output-option-page"></a><a name="OutputOption"></a> <span data-ttu-id="2013a-181">Pagina Seleziona un'opzione di output</span><span class="sxs-lookup"><span data-stu-id="2013a-181">Select Output Option Page</span></span>  
 <span data-ttu-id="2013a-182">Usare la pagina **Seleziona un'opzione di output** per specificare il modo in cui si desidera completare le modifiche alle partizioni.</span><span class="sxs-lookup"><span data-stu-id="2013a-182">Use the **Select Output Option** page to specify how you want to complete the modifications to your partitions.</span></span>  
  
### <a name="create-script"></a><span data-ttu-id="2013a-183">Crea script</span><span class="sxs-lookup"><span data-stu-id="2013a-183">Create Script</span></span>  
 <span data-ttu-id="2013a-184">Al termine della procedura guidata, nell'editor di query viene creato uno script per la modifica delle partizioni nella tabella.</span><span class="sxs-lookup"><span data-stu-id="2013a-184">When the wizard finishes, it creates a script in Query Editor to modify partitions in the table.</span></span> <span data-ttu-id="2013a-185">Selezionare **Crea script** se si desidera controllare lo script e quindi eseguirlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="2013a-185">Select **Create Script** if you want to review the script, and then execute the script manually.</span></span>  
  
 <span data-ttu-id="2013a-186">**Genera script nel file**</span><span class="sxs-lookup"><span data-stu-id="2013a-186">**Script to file**</span></span>  
 <span data-ttu-id="2013a-187">Consente di generare lo script in un file con estensione sql.</span><span class="sxs-lookup"><span data-stu-id="2013a-187">Generate the script to a .sql file.</span></span> <span data-ttu-id="2013a-188">Specificare **Unicode** o **Testo ANSI**.</span><span class="sxs-lookup"><span data-stu-id="2013a-188">Specify either **Unicode** or **ANSI text**.</span></span> <span data-ttu-id="2013a-189">Per specificare un nome e un percorso per il file, scegliere **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="2013a-189">To specify a name and location for the file, click **Browse**.</span></span>  
  
 <span data-ttu-id="2013a-190">**Genera script negli Appunti**</span><span class="sxs-lookup"><span data-stu-id="2013a-190">**Script to Clipboard**</span></span>  
 <span data-ttu-id="2013a-191">Consente di salvare lo script negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="2013a-191">Save the script to the Clipboard.</span></span>  
  
 <span data-ttu-id="2013a-192">**Genera script in nuova finestra Query**</span><span class="sxs-lookup"><span data-stu-id="2013a-192">**Script to New Query Window**</span></span>  
 <span data-ttu-id="2013a-193">Consente di generare lo script in una finestra dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="2013a-193">Generate the script to a Query Editor window.</span></span> <span data-ttu-id="2013a-194">Se non è aperta alcuna finestra dell'editor, ne viene aperta una nuova da utilizzare come destinazione per lo script.</span><span class="sxs-lookup"><span data-stu-id="2013a-194">If no editor window is open, a new editor window opens as the target for the script.</span></span>  
  
### <a name="run-immediately"></a><span data-ttu-id="2013a-195">Esegui immediatamente</span><span class="sxs-lookup"><span data-stu-id="2013a-195">Run Immediately</span></span>  
 <span data-ttu-id="2013a-196">**Run immediately**</span><span class="sxs-lookup"><span data-stu-id="2013a-196">**Run immediately**</span></span>  
 <span data-ttu-id="2013a-197">Per completare l'applicazione di modifiche alle partizioni nella procedura guidata, fare clic su **Avanti** o **Fine**.</span><span class="sxs-lookup"><span data-stu-id="2013a-197">Have the wizard finish modifications to the partitions when you click **Next** or **Finish**.</span></span>  
  
### <a name="schedule"></a><span data-ttu-id="2013a-198">Pianificazione</span><span class="sxs-lookup"><span data-stu-id="2013a-198">Schedule</span></span>  
 <span data-ttu-id="2013a-199">Selezionare questa opzione per modificare le partizioni della tabella a una data e a un'ora pianificata.</span><span class="sxs-lookup"><span data-stu-id="2013a-199">Select to modify the table partitions at a scheduled date and time.</span></span>  
  
 <span data-ttu-id="2013a-200">**Cambia pianificazione**</span><span class="sxs-lookup"><span data-stu-id="2013a-200">**Change schedule**</span></span>  
 <span data-ttu-id="2013a-201">Viene aperta la finestra di dialogo **Nuova pianificazione processo** , in cui è possibile selezionare, modificare o visualizzare le proprietà del processo pianificato.</span><span class="sxs-lookup"><span data-stu-id="2013a-201">Opens the **New Job Schedule** dialog box, where you can select, change, or view the properties of the scheduled job.</span></span>  
  
 <span data-ttu-id="2013a-202">![Icona freccia usata con il collegamento Torna all'inizio](../../2014-toc/media/uparrow16x16.gif "Icona freccia usata con il collegamento Torna all'inizio") [In questa sezione](#Top)</span><span class="sxs-lookup"><span data-stu-id="2013a-202">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="new-job-schedule-page"></a><a name="NewJob"></a> <span data-ttu-id="2013a-203">Pagina Nuova pianificazione processo</span><span class="sxs-lookup"><span data-stu-id="2013a-203">New Job Schedule Page</span></span>  
 <span data-ttu-id="2013a-204">Usare la pagina **Nuova pianificazione processo** per visualizzare e modificare le proprietà della pianificazione.</span><span class="sxs-lookup"><span data-stu-id="2013a-204">Use the **New Job Schedule** page to view and change the properties of the schedule.</span></span>  
  
### <a name="options"></a><span data-ttu-id="2013a-205">Opzioni</span><span class="sxs-lookup"><span data-stu-id="2013a-205">Options</span></span>  
 <span data-ttu-id="2013a-206">Selezionare il tipo di pianificazione desiderata per il processo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="2013a-206">Select the type of schedule you want for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>  
  
 <span data-ttu-id="2013a-207">**Nome**</span><span class="sxs-lookup"><span data-stu-id="2013a-207">**Name**</span></span>  
 <span data-ttu-id="2013a-208">Consente di digitare un nuovo nome per la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="2013a-208">Type a new name for the schedule.</span></span>  
  
 <span data-ttu-id="2013a-209">**Processi nella pianificazione**</span><span class="sxs-lookup"><span data-stu-id="2013a-209">**Jobs in schedule**</span></span>  
 <span data-ttu-id="2013a-210">Consente di visualizzare i processi esistenti che utilizzano la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="2013a-210">View the existing jobs that use the schedule.</span></span>  
  
 <span data-ttu-id="2013a-211">**Tipo pianificazione**</span><span class="sxs-lookup"><span data-stu-id="2013a-211">**Schedule type**</span></span>  
 <span data-ttu-id="2013a-212">Consente di selezionare il tipo di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="2013a-212">Select the type of schedule.</span></span>  
  
 <span data-ttu-id="2013a-213">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="2013a-213">**Enabled**</span></span>  
 <span data-ttu-id="2013a-214">Consente di abilitare o disabilitare la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="2013a-214">Enable or disable the schedule.</span></span>  
  
### <a name="recurring-schedule-types-options"></a><span data-ttu-id="2013a-215">Opzioni relative ai tipi di pianificazione periodica</span><span class="sxs-lookup"><span data-stu-id="2013a-215">Recurring Schedule Types Options</span></span>  
 <span data-ttu-id="2013a-216">Selezionare la frequenza del processo pianificato.</span><span class="sxs-lookup"><span data-stu-id="2013a-216">Select the frequency of the scheduled job.</span></span>  
  
 <span data-ttu-id="2013a-217">**Ricorrenza**</span><span class="sxs-lookup"><span data-stu-id="2013a-217">**Occurs**</span></span>  
 <span data-ttu-id="2013a-218">Consente di selezionare l'intervallo in base al quale ripetere la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="2013a-218">Select the interval at which the schedule recurs.</span></span>  
  
 <span data-ttu-id="2013a-219">**Ogni**</span><span class="sxs-lookup"><span data-stu-id="2013a-219">**Recurs every**</span></span>  
 <span data-ttu-id="2013a-220">Consente di selezionare il numero di giorni o di settimane quale intervallo di esecuzione delle pianificazioni.</span><span class="sxs-lookup"><span data-stu-id="2013a-220">Select the number of days or weeks between recurrences of the schedule.</span></span> <span data-ttu-id="2013a-221">Questa opzione non è disponibile per pianificazioni mensili.</span><span class="sxs-lookup"><span data-stu-id="2013a-221">This option is not available for monthly schedules.</span></span>  
  
 <span data-ttu-id="2013a-222">**Lunedì**</span><span class="sxs-lookup"><span data-stu-id="2013a-222">**Monday**</span></span>  
 <span data-ttu-id="2013a-223">Consente di impostare l'esecuzione del processo ogni lunedì.</span><span class="sxs-lookup"><span data-stu-id="2013a-223">Set the job to occur on a Monday.</span></span> <span data-ttu-id="2013a-224">Questa opzione è disponibile solo per pianificazioni settimanali.</span><span class="sxs-lookup"><span data-stu-id="2013a-224">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="2013a-225">**Martedì**</span><span class="sxs-lookup"><span data-stu-id="2013a-225">**Tuesday**</span></span>  
 <span data-ttu-id="2013a-226">Consente di impostare l'esecuzione del processo ogni martedì.</span><span class="sxs-lookup"><span data-stu-id="2013a-226">Set the job to occur on a Tuesday.</span></span> <span data-ttu-id="2013a-227">Questa opzione è disponibile solo per pianificazioni settimanali.</span><span class="sxs-lookup"><span data-stu-id="2013a-227">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="2013a-228">**Mercoledì**</span><span class="sxs-lookup"><span data-stu-id="2013a-228">**Wednesday**</span></span>  
 <span data-ttu-id="2013a-229">Consente di impostare l'esecuzione del processo ogni mercoledì.</span><span class="sxs-lookup"><span data-stu-id="2013a-229">Set the job to occur on a Wednesday.</span></span> <span data-ttu-id="2013a-230">Questa opzione è disponibile solo per pianificazioni settimanali.</span><span class="sxs-lookup"><span data-stu-id="2013a-230">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="2013a-231">**Giovedì**</span><span class="sxs-lookup"><span data-stu-id="2013a-231">**Thursday**</span></span>  
 <span data-ttu-id="2013a-232">Consente di impostare l'esecuzione del processo ogni giovedì.</span><span class="sxs-lookup"><span data-stu-id="2013a-232">Set the job to occur on a Thursday.</span></span> <span data-ttu-id="2013a-233">Questa opzione è disponibile solo per pianificazioni settimanali.</span><span class="sxs-lookup"><span data-stu-id="2013a-233">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="2013a-234">**Venerdì**</span><span class="sxs-lookup"><span data-stu-id="2013a-234">**Friday**</span></span>  
 <span data-ttu-id="2013a-235">Consente di impostare l'esecuzione del processo ogni venerdì.</span><span class="sxs-lookup"><span data-stu-id="2013a-235">Set the job to occur on a Friday.</span></span> <span data-ttu-id="2013a-236">Questa opzione è disponibile solo per pianificazioni settimanali.</span><span class="sxs-lookup"><span data-stu-id="2013a-236">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="2013a-237">**Sabato**</span><span class="sxs-lookup"><span data-stu-id="2013a-237">**Saturday**</span></span>  
 <span data-ttu-id="2013a-238">Consente di impostare l'esecuzione del processo ogni sabato.</span><span class="sxs-lookup"><span data-stu-id="2013a-238">Set the job to occur on a Saturday.</span></span> <span data-ttu-id="2013a-239">Questa opzione è disponibile solo per pianificazioni settimanali.</span><span class="sxs-lookup"><span data-stu-id="2013a-239">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="2013a-240">**Domenica**</span><span class="sxs-lookup"><span data-stu-id="2013a-240">**Sunday**</span></span>  
 <span data-ttu-id="2013a-241">Consente di impostare l'esecuzione del processo ogni domenica.</span><span class="sxs-lookup"><span data-stu-id="2013a-241">Set the job to occur on a Sunday.</span></span> <span data-ttu-id="2013a-242">Questa opzione è disponibile solo per pianificazioni settimanali.</span><span class="sxs-lookup"><span data-stu-id="2013a-242">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="2013a-243">**Day**</span><span class="sxs-lookup"><span data-stu-id="2013a-243">**Day**</span></span>  
 <span data-ttu-id="2013a-244">Consente di selezionare il giorno del mese in cui eseguire la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="2013a-244">Select the day of the month the schedule occurs.</span></span> <span data-ttu-id="2013a-245">Questa opzione è disponibile solo per pianificazioni mensili.</span><span class="sxs-lookup"><span data-stu-id="2013a-245">Only available for monthly schedules.</span></span>  
  
 <span data-ttu-id="2013a-246">**ogni**</span><span class="sxs-lookup"><span data-stu-id="2013a-246">**of every**</span></span>  
 <span data-ttu-id="2013a-247">Consente di selezionare il numero di mesi tra una pianificazione e l'altra.</span><span class="sxs-lookup"><span data-stu-id="2013a-247">Select the number of months between occurrences of the schedule.</span></span> <span data-ttu-id="2013a-248">Questa opzione è disponibile solo per pianificazioni mensili.</span><span class="sxs-lookup"><span data-stu-id="2013a-248">Only available for monthly schedules.</span></span>  
  
 <span data-ttu-id="2013a-249">**Ogni**</span><span class="sxs-lookup"><span data-stu-id="2013a-249">**The**</span></span>  
 <span data-ttu-id="2013a-250">Consente di specificare una pianificazione per un giorno specifico di una determinata settimana del mese.</span><span class="sxs-lookup"><span data-stu-id="2013a-250">Specify a schedule for a specific day of the week on a specific week within the month.</span></span> <span data-ttu-id="2013a-251">Questa opzione è disponibile solo per pianificazioni mensili.</span><span class="sxs-lookup"><span data-stu-id="2013a-251">Only available for monthly schedules.</span></span>  
  
 <span data-ttu-id="2013a-252">**Una sola volta alle**</span><span class="sxs-lookup"><span data-stu-id="2013a-252">**Occurs once at**</span></span>  
 <span data-ttu-id="2013a-253">Consente di impostare l'ora per l'esecuzione giornaliera di un processo.</span><span class="sxs-lookup"><span data-stu-id="2013a-253">Set the time for a job to occur daily.</span></span>  
  
 <span data-ttu-id="2013a-254">**Ogni**</span><span class="sxs-lookup"><span data-stu-id="2013a-254">**Occurs every**</span></span>  
 <span data-ttu-id="2013a-255">Consente di impostare il numero di ore o di minuti di intervallo tra un'esecuzione e l'altra.</span><span class="sxs-lookup"><span data-stu-id="2013a-255">Set the number of hours or minutes between occurrences.</span></span>  
  
 <span data-ttu-id="2013a-256">**Data inizio**</span><span class="sxs-lookup"><span data-stu-id="2013a-256">**Start date**</span></span>  
 <span data-ttu-id="2013a-257">Consente di impostare la data iniziale di validità per la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="2013a-257">Set the date when this schedule will become effective.</span></span>  
  
 <span data-ttu-id="2013a-258">**Data fine**</span><span class="sxs-lookup"><span data-stu-id="2013a-258">**End date**</span></span>  
 <span data-ttu-id="2013a-259">Consente di impostare la data finale di validità per la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="2013a-259">Set the date when the schedule will no longer be effective.</span></span>  
  
 <span data-ttu-id="2013a-260">**Nessuna data di fine**</span><span class="sxs-lookup"><span data-stu-id="2013a-260">**No end date**</span></span>  
 <span data-ttu-id="2013a-261">Consente di specificare una validità illimitata per la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="2013a-261">Specify that the schedule will remain effective indefinitely.</span></span>  
  
### <a name="one-time-schedule-types-options"></a><span data-ttu-id="2013a-262">Opzioni relative ai tipi di pianificazione da eseguire una sola volta</span><span class="sxs-lookup"><span data-stu-id="2013a-262">One Time Schedule Types Options</span></span>  
 <span data-ttu-id="2013a-263">Se si pianifica una singola esecuzione per un processo, è necessario selezionare una data e un'ora nel futuro.</span><span class="sxs-lookup"><span data-stu-id="2013a-263">If you schedule a job to run once, you must select a date and time in the future.</span></span>  
  
 <span data-ttu-id="2013a-264">**Data**</span><span class="sxs-lookup"><span data-stu-id="2013a-264">**Date**</span></span>  
 <span data-ttu-id="2013a-265">Selezionare la data di esecuzione del processo.</span><span class="sxs-lookup"><span data-stu-id="2013a-265">Select the date for the job to run.</span></span>  
  
 <span data-ttu-id="2013a-266">**Time**</span><span class="sxs-lookup"><span data-stu-id="2013a-266">**Time**</span></span>  
 <span data-ttu-id="2013a-267">Selezionare l'ora di esecuzione del processo.</span><span class="sxs-lookup"><span data-stu-id="2013a-267">Select the time for the job to run.</span></span>  
  
 <span data-ttu-id="2013a-268">![Icona freccia usata con il collegamento Torna all'inizio](../../2014-toc/media/uparrow16x16.gif "Icona freccia usata con il collegamento Torna all'inizio") [In questa sezione](#Top)</span><span class="sxs-lookup"><span data-stu-id="2013a-268">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="2013a-269">Pagina Riepilogo</span><span class="sxs-lookup"><span data-stu-id="2013a-269">Summary Page</span></span>  
 <span data-ttu-id="2013a-270">Usare la pagina **Riepilogo** per verificare le opzioni selezionate nelle pagine precedenti.</span><span class="sxs-lookup"><span data-stu-id="2013a-270">Use the **Summary** page to review the options that you have selected on the previous pages.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="2013a-271">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="2013a-271">UI element list</span></span>  
 <span data-ttu-id="2013a-272">**Controlla selezioni**</span><span class="sxs-lookup"><span data-stu-id="2013a-272">**Review your selections**</span></span>  
 <span data-ttu-id="2013a-273">Consente di visualizzare le opzioni selezionate in ogni pagina della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="2013a-273">Displays the selections you have made for each page of the wizard.</span></span> <span data-ttu-id="2013a-274">Fare clic su un nodo per espandere e visualizzare le opzioni selezionate in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2013a-274">Click a node to expand and view your previously selected options.</span></span>  
  
 <span data-ttu-id="2013a-275">![Icona freccia usata con il collegamento Torna all'inizio](../../2014-toc/media/uparrow16x16.gif "Icona freccia usata con il collegamento Torna all'inizio") [In questa sezione](#Top)</span><span class="sxs-lookup"><span data-stu-id="2013a-275">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="progress-page"></a><a name="Progress"></a> <span data-ttu-id="2013a-276">Pagina Stato</span><span class="sxs-lookup"><span data-stu-id="2013a-276">Progress Page</span></span>  
 <span data-ttu-id="2013a-277">Usare la pagina **Stato** per monitorare le informazioni sullo stato delle azioni eseguite nella **Gestione guidata partizione**.</span><span class="sxs-lookup"><span data-stu-id="2013a-277">Use the **Progress** page to monitor status information about the actions of the **Manage Partition Wizard**.</span></span> <span data-ttu-id="2013a-278">A seconda delle opzioni selezionate nella procedura guidata, la pagina **Stato** può contenere una o più azioni.</span><span class="sxs-lookup"><span data-stu-id="2013a-278">Depending on the options that you selected in the wizard, the **Progress** page might contain one or more actions.</span></span> <span data-ttu-id="2013a-279">Nella casella superiore viene visualizzato lo stato complessivo della procedura guidata e viene indicato il numero di messaggi di stato, di errore e di avviso restituiti durante l'esecuzione della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="2013a-279">The top box displays the overall status of the wizard and the number of status, error, and warning messages that the wizard has received.</span></span>  
  
### <a name="options"></a><span data-ttu-id="2013a-280">Opzioni</span><span class="sxs-lookup"><span data-stu-id="2013a-280">Options</span></span>  
 <span data-ttu-id="2013a-281">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="2013a-281">**Details**</span></span>  
 <span data-ttu-id="2013a-282">Consente di visualizzare i messaggi di azione, di stato e di altro tipo restituiti dall'azione eseguita nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="2013a-282">Provides the action, status, and any messages that are returned from action taken by the wizard.</span></span>  
  
 <span data-ttu-id="2013a-283">**Azione**</span><span class="sxs-lookup"><span data-stu-id="2013a-283">**Action**</span></span>  
 <span data-ttu-id="2013a-284">Specifica il tipo e il nome di ciascuna azione.</span><span class="sxs-lookup"><span data-stu-id="2013a-284">Specifies the type and name of each action.</span></span>  
  
 <span data-ttu-id="2013a-285">**Status**</span><span class="sxs-lookup"><span data-stu-id="2013a-285">**Status**</span></span>  
 <span data-ttu-id="2013a-286">Indica se l'intera azione della procedura guidata ha restituito il valore **Esito positivo** o **Esito negativo**.</span><span class="sxs-lookup"><span data-stu-id="2013a-286">Indicates whether the wizard action as a whole returned the value of **Success** or **Failure**.</span></span>  
  
 <span data-ttu-id="2013a-287">**Messaggio**</span><span class="sxs-lookup"><span data-stu-id="2013a-287">**Message**</span></span>  
 <span data-ttu-id="2013a-288">Fornisce tutti i messaggi di errore o di avviso restituiti dal processo.</span><span class="sxs-lookup"><span data-stu-id="2013a-288">Provides any error or warning messages that are returned from the process.</span></span>  
  
 <span data-ttu-id="2013a-289">**Stop**</span><span class="sxs-lookup"><span data-stu-id="2013a-289">**Stop**</span></span>  
 <span data-ttu-id="2013a-290">Consente di arrestare l'azione della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="2013a-290">Stop the action of the wizard.</span></span>  
  
 <span data-ttu-id="2013a-291">**Report**</span><span class="sxs-lookup"><span data-stu-id="2013a-291">**Report**</span></span>  
 <span data-ttu-id="2013a-292">Consente di creare un report contenente i risultati della **Gestione guidata partizione**.</span><span class="sxs-lookup"><span data-stu-id="2013a-292">Create a report that contains the results of the **Manage Partition Wizard**.</span></span> <span data-ttu-id="2013a-293">Le opzioni disponibili sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="2013a-293">The options are:</span></span>  
  
-   <span data-ttu-id="2013a-294">**Visualizza report**</span><span class="sxs-lookup"><span data-stu-id="2013a-294">**View Report**</span></span>  
  
-   <span data-ttu-id="2013a-295">**Salva report su file**</span><span class="sxs-lookup"><span data-stu-id="2013a-295">**Save Report to File**</span></span>  
  
-   <span data-ttu-id="2013a-296">**Copia report negli Appunti**</span><span class="sxs-lookup"><span data-stu-id="2013a-296">**Copy Report to Clipboard**</span></span>  
  
-   <span data-ttu-id="2013a-297">**Invia report per posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="2013a-297">**Send Report as Email**</span></span>  
  
 <span data-ttu-id="2013a-298">**Visualizza report**</span><span class="sxs-lookup"><span data-stu-id="2013a-298">**View Report**</span></span>  
 <span data-ttu-id="2013a-299">Consente di aprire la finestra di dialogo **Visualizza report** ,</span><span class="sxs-lookup"><span data-stu-id="2013a-299">Open the **View Report** dialog box.</span></span> <span data-ttu-id="2013a-300">che contiene un report di testo dello stato della **Gestione guidata partizione**.</span><span class="sxs-lookup"><span data-stu-id="2013a-300">This dialog box contains a text report of the progress of the **Manage Partition Wizard**.</span></span>  
  
 <span data-ttu-id="2013a-301">**Close**</span><span class="sxs-lookup"><span data-stu-id="2013a-301">**Close**</span></span>  
 <span data-ttu-id="2013a-302">Consente di chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="2013a-302">Close the wizard.</span></span>  
  
 <span data-ttu-id="2013a-303">![Icona freccia usata con il collegamento Torna all'inizio](../../2014-toc/media/uparrow16x16.gif "Icona freccia usata con il collegamento Torna all'inizio") [In questa sezione](#Top)</span><span class="sxs-lookup"><span data-stu-id="2013a-303">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2013a-304">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2013a-304">See Also</span></span>  
 [<span data-ttu-id="2013a-305">Tabelle e indici partizionati</span><span class="sxs-lookup"><span data-stu-id="2013a-305">Partitioned Tables and Indexes</span></span>](partitioned-tables-and-indexes.md)  
  
  
