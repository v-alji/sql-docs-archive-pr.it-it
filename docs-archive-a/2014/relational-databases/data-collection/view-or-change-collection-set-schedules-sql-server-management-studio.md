---
title: Visualizzare o modificare le pianificazioni dei set di raccolta (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dc.collectionsetprop.uploads.f1
- sql12.swb.dc.collectionsetprop.general.f1
- sql12.swb.dc.collectionsetprop.description.f1
helpviewer_keywords:
- collection sets [SQL Server], changing schedules
- schedules [SQL Server], changing collection set
- collection sets [SQL Server], viewing schedules
- schedules [SQL Server], viewing collection set
ms.assetid: 26336c98-78c5-414f-8d6a-574fc3af60c4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2eb1acf0346b3e16bd1d54829abbc070e1d9d63b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636220"
---
# <a name="view-or-change-collection-set-schedules-sql-server-management-studio"></a><span data-ttu-id="eb360-102">Visualizzazione o modifica delle pianificazioni dei set di raccolta (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="eb360-102">View or Change Collection Set Schedules (SQL Server Management Studio)</span></span>
  <span data-ttu-id="eb360-103">È possibile visualizzare o modificare le pianificazioni dei set di raccolta utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb360-103">You can view or change collection set schedules by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="eb360-104">La modalità di raccolta, ovvero in cache o non in cache, determina il tipo di modifiche che è possibile apportare a una pianificazione.</span><span class="sxs-lookup"><span data-stu-id="eb360-104">The collection mode, cached or non-cached, determines how you can make changes to a schedule.</span></span> <span data-ttu-id="eb360-105">La modalità cache utilizza pianificazioni separate per la raccolta e il caricamento.</span><span class="sxs-lookup"><span data-stu-id="eb360-105">Cached mode uses separate schedules for collection and upload.</span></span> <span data-ttu-id="eb360-106">La modalità non in cache utilizza la stessa pianificazione per la raccolta e il caricamento.</span><span class="sxs-lookup"><span data-stu-id="eb360-106">Non-cached mode uses the same schedule for collection and upload.</span></span> <span data-ttu-id="eb360-107">I tipi di modalità di raccolta per ognuno dei set di raccolta dati di sistema sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="eb360-107">The type of collection mode for each of the System Datacollection sets is as follows:</span></span>  
  
-   <span data-ttu-id="eb360-108">**Utilizzo disco** usa la modalità di raccolta non in cache.</span><span class="sxs-lookup"><span data-stu-id="eb360-108">**Disk Usage** uses non-cached collection mode.</span></span>  
  
-   <span data-ttu-id="eb360-109">**Statistiche query** utilizza la modalità di raccolta cache.</span><span class="sxs-lookup"><span data-stu-id="eb360-109">**Query Statistics** uses cached collection mode.</span></span>  
  
-   <span data-ttu-id="eb360-110">**Attività Server** utilizza la modalità di raccolta cache.</span><span class="sxs-lookup"><span data-stu-id="eb360-110">**Server Activity** uses cached collection mode.</span></span>  
  
### <a name="to-view-collection-set-schedules"></a><span data-ttu-id="eb360-111">Per visualizzare le pianificazioni dei set di raccolta</span><span class="sxs-lookup"><span data-stu-id="eb360-111">To view collection set schedules</span></span>  
  
1.  <span data-ttu-id="eb360-112">In Esplora oggetti espandere il nodo **Gestione** , **Raccolta dati**, quindi **Set di raccolta dati di sistema**.</span><span class="sxs-lookup"><span data-stu-id="eb360-112">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="eb360-113">Fare clic con il pulsante destro del mouse sul nome di un set di raccolta e selezionare **Proprietà** per aprire la finestra di dialogo [Proprietà set di raccolta dati](#CollectionSet) .</span><span class="sxs-lookup"><span data-stu-id="eb360-113">Right-click a collection set name, and then click **Properties** to open the [Data Collection Set Properties](#CollectionSet) dialog box.</span></span>  
  
### <a name="to-change-the-schedules-for-a-cached-mode-collection-set"></a><span data-ttu-id="eb360-114">Per modificare le pianificazioni per un set di raccolta in modalità cache</span><span class="sxs-lookup"><span data-stu-id="eb360-114">To change the schedules for a cached mode collection set</span></span>  
  
1.  <span data-ttu-id="eb360-115">In Esplora oggetti espandere il nodo **Gestione** , **Raccolta dati**, quindi **Set di raccolta dati di sistema**.</span><span class="sxs-lookup"><span data-stu-id="eb360-115">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="eb360-116">Fare clic con il pulsante destro del mouse su un set di raccolta che usa una modalità cache, ad esempio **Statistiche query**e scegliere **Proprietà** per aprire la finestra di dialogo [Proprietà set di raccolta dati](#CollectionSet) .</span><span class="sxs-lookup"><span data-stu-id="eb360-116">Right-click a collection set that uses cached mode, such as **Query Statistics**, and then click **Properties** to open the [Data Collection Set Properties](#CollectionSet) dialog box.</span></span>  
  
3.  <span data-ttu-id="eb360-117">Per modificare la frequenza di raccolta, utilizzare la pagina **Generale** .</span><span class="sxs-lookup"><span data-stu-id="eb360-117">You can change the collection frequency on the **General** page.</span></span> <span data-ttu-id="eb360-118">A questo scopo, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="eb360-118">To do this, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="eb360-119">Nel riquadro dei dettagli fare doppio clic sul numero visualizzato per la colonna **Frequenza di raccolta (sec)** nella tabella **Elementi della raccolta** .</span><span class="sxs-lookup"><span data-stu-id="eb360-119">In the details pane, double-click the number that is displayed for the **Collection Frequency (sec)** column in the **Collection items** table.</span></span>  
  
    2.  <span data-ttu-id="eb360-120">Per aumentare o ridurre la frequenza di raccolta, digitare un numero minore o maggiore, quindi premere INVIO per archiviare il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="eb360-120">To increase or decrease the collection frequency, type a lower or higher number, and then press ENTER to store the new value.</span></span>  
  
4.  <span data-ttu-id="eb360-121">Per modificare la pianificazione di caricamento corrente per il set di raccolta, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="eb360-121">To change the existing upload schedule for the collection set, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="eb360-122">Fare clic sulla pagina **Caricamenti** .</span><span class="sxs-lookup"><span data-stu-id="eb360-122">Click the **Uploads** page.</span></span>  
  
    2.  <span data-ttu-id="eb360-123">Nel riquadro dei dettagli fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="eb360-123">In the details pane, click **Pick**.</span></span>  
  
         <span data-ttu-id="eb360-124">Verrà visualizzata la finestra di dialogo **Seleziona pianificazione per il processo** .</span><span class="sxs-lookup"><span data-stu-id="eb360-124">The **Pick Schedule for Job** dialog box opens.</span></span> <span data-ttu-id="eb360-125">Le pianificazioni disponibili sono visualizzate sotto forma di tabella.</span><span class="sxs-lookup"><span data-stu-id="eb360-125">The available schedules appear as a table.</span></span>  
  
    3.  <span data-ttu-id="eb360-126">Fare clic sulla riga contenente la pianificazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="eb360-126">Click the row with the schedule that you want.</span></span> <span data-ttu-id="eb360-127">Per modificare ad esempio la pianificazione su ogni 5 minuti, fare clic sulla riga in cui il nome della pianificazione è **CollectorSchedule_Every_5min.**</span><span class="sxs-lookup"><span data-stu-id="eb360-127">For example, to change the schedule to every 5 minutes, click the row where the schedule name is **CollectorSchedule_Every_5min.**</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="eb360-128">Per visualizzare e modificare le proprietà per la pianificazione selezionata, fare clic su **Proprietà** per aprire la finestra di dialogo **Proprietà pianificazione processo** per la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="eb360-128">You can view and edit the properties for the selected schedule by clicking **Properties** to open the **Job Schedule Properties** dialog box for the schedule.</span></span> <span data-ttu-id="eb360-129">È possibile utilizzare questa finestra di dialogo per modificare le informazioni sulla pianificazione, ad esempio la frequenza.</span><span class="sxs-lookup"><span data-stu-id="eb360-129">You can use this dialog box to change schedule information, such as the frequency.</span></span>  
        >   
        >  <span data-ttu-id="eb360-130">In alternativa alla modifica di una pianificazione esistente, è possibile creare una nuova pianificazione di caricamento facendo clic su **Nuovo** nella pagina **Caricamenti** .</span><span class="sxs-lookup"><span data-stu-id="eb360-130">As an alternative to modifying an existing schedule, you can create a new upload schedule by clicking **New** on the **Uploads** page.</span></span> <span data-ttu-id="eb360-131">Verrà visualizzata la finestra di dialogo **Nuova pianificazione processo** , in cui è possibile creare una pianificazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="eb360-131">This action opens the **New Job Schedule** dialog box, which you can use to create a custom schedule.</span></span>  
  
    4.  <span data-ttu-id="eb360-132">Dopo aver configurato la pianificazione, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb360-132">When you are finished configuring the schedule, click **OK**.</span></span>  
  
         <span data-ttu-id="eb360-133">Le modifiche apportate vengono visualizzate nella pagina **Caricamenti** .</span><span class="sxs-lookup"><span data-stu-id="eb360-133">The changes that you made appear on the **Uploads** page.</span></span>  
  
5.  <span data-ttu-id="eb360-134">Fare clic su **OK** per salvare le modifiche apportate alla frequenza di raccolta e alla pianificazione del caricamento, quindi chiudere la finestra di dialogo **Proprietà set di raccolta dati** .</span><span class="sxs-lookup"><span data-stu-id="eb360-134">Click **OK** to save the changes to the collection frequency and the upload schedule, and to close the **Data Collection Set Properties** dialog box.</span></span>  
  
### <a name="to-change-the-schedule-for-a-non-cached-mode-collection-set"></a><span data-ttu-id="eb360-135">Per modificare la pianificazione per un set di raccolta in modalità non in cache</span><span class="sxs-lookup"><span data-stu-id="eb360-135">To change the schedule for a non-cached mode collection set</span></span>  
  
1.  <span data-ttu-id="eb360-136">In Esplora oggetti espandere il nodo **Gestione** , **Raccolta dati**, quindi **Set di raccolta dati di sistema**.</span><span class="sxs-lookup"><span data-stu-id="eb360-136">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="eb360-137">Fare clic con il pulsante destro del mouse su un set di raccolta che usa una modalità non cache, ad esempio **Utilizzo disco**e scegliere **Proprietà** per aprire la finestra di dialogo [Proprietà set di raccolta dati](#CollectionSet) .</span><span class="sxs-lookup"><span data-stu-id="eb360-137">Right-click a collection set that uses non-cached mode, such as **Disk Usage**, and then click **Properties** to open the [Data Collection Set Properties](#CollectionSet) dialog box.</span></span>  
  
     <span data-ttu-id="eb360-138">Viene visualizzata la finestra di dialogo **Proprietà set di raccolta dati** in una vista a pagine contenente le proprietà del set di raccolta.</span><span class="sxs-lookup"><span data-stu-id="eb360-138">The **Data Collection Set Properties** dialog box displays a paged view of the collection set properties.</span></span>  
  
3.  <span data-ttu-id="eb360-139">Per modificare la pianificazione per il set di raccolta, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="eb360-139">To change the schedule for the collection set, click **Pick**.</span></span>  
  
     <span data-ttu-id="eb360-140">Verrà visualizzata la finestra di dialogo **Seleziona pianificazione per il processo** .</span><span class="sxs-lookup"><span data-stu-id="eb360-140">The **Pick Schedule for Job** dialog box opens.</span></span> <span data-ttu-id="eb360-141">Le pianificazioni disponibili sono visualizzate sotto forma di tabella.</span><span class="sxs-lookup"><span data-stu-id="eb360-141">The available schedules are displayed as a table.</span></span>  
  
4.  <span data-ttu-id="eb360-142">Fare clic sulla riga contenente la pianificazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="eb360-142">Click the row with the schedule that you want.</span></span> <span data-ttu-id="eb360-143">Per modificare ad esempio la pianificazione su ogni 5 minuti, fare clic sulla riga in cui il nome della pianificazione è **CollectorSchedule_Every_5min**.</span><span class="sxs-lookup"><span data-stu-id="eb360-143">For example, to change the schedule to every 5 minutes, click the row where the schedule name is **CollectorSchedule_Every_5min**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="eb360-144">Per visualizzare e modificare le proprietà per la pianificazione selezionata, fare clic su **Proprietà** per aprire la finestra di dialogo **Proprietà pianificazione processo** per la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="eb360-144">You can view and edit the properties for the selected schedule by clicking **Properties** to open the **Job Schedule Properties** dialog box for the schedule.</span></span> <span data-ttu-id="eb360-145">È possibile utilizzare questa finestra di dialogo per modificare le informazioni sulla pianificazione, ad esempio la frequenza.</span><span class="sxs-lookup"><span data-stu-id="eb360-145">You can use this dialog box to change schedule information, such as the frequency.</span></span>  
    >   
    >  <span data-ttu-id="eb360-146">In alternativa alla modifica di una pianificazione esistente, è possibile creare una nuova pianificazione di raccolta e caricamento facendo clic su **Nuovo** nella pagina **Generale** .</span><span class="sxs-lookup"><span data-stu-id="eb360-146">As an alternative to modifying an existing schedule, you can create a new collect and upload schedule by clicking **New** on the **General** page.</span></span> <span data-ttu-id="eb360-147">Verrà visualizzata la finestra di dialogo **Nuova pianificazione processo** .</span><span class="sxs-lookup"><span data-stu-id="eb360-147">This action opens the **New Job Schedule** dialog box.</span></span>  
  
5.  <span data-ttu-id="eb360-148">Dopo aver configurato la pianificazione, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb360-148">When you are finished configuring the schedule, click **OK**.</span></span>  
  
6.  <span data-ttu-id="eb360-149">Fare clic su **OK** per salvare le modifiche e chiudere la finestra di dialogo **Proprietà set di raccolta dati** .</span><span class="sxs-lookup"><span data-stu-id="eb360-149">Click **OK** to save the changes and to close the **Data Collection Set Properties** dialog box.</span></span>  
  
####  <a name="data-collection-set-properties-dialog-box"></a><a name="CollectionSet"></a> <span data-ttu-id="eb360-150">Finestra di dialogo Proprietà set di raccolta dati</span><span class="sxs-lookup"><span data-stu-id="eb360-150">Data Collection Set Properties Dialog Box</span></span>  
 <span data-ttu-id="eb360-151">**Pagina Generale**</span><span class="sxs-lookup"><span data-stu-id="eb360-151">**General Page**</span></span>  
  
 <span data-ttu-id="eb360-152">Utilizzare questa pagina per configurare la modalità di raccolta e caricamento dei dati, le pianificazioni e i periodi di memorizzazione dei dati nel data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="eb360-152">Use this page to configure how data is collected and uploaded, configure schedules, and configure data retention periods in the management data warehouse.</span></span> <span data-ttu-id="eb360-153">Questa pagina inoltre fornisce informazioni sui set di raccolte, quali le frequenze di raccolta e i tipi di agente di raccolta, nonché i parametri di input utilizzati per un set di raccolta.</span><span class="sxs-lookup"><span data-stu-id="eb360-153">This page also provides information about collection sets, such as collector types and collection frequencies, as well as the input parameters that are used for a collection set.</span></span>  
  
 <span data-ttu-id="eb360-154">**Nome**</span><span class="sxs-lookup"><span data-stu-id="eb360-154">**Name**</span></span>  
 <span data-ttu-id="eb360-155">Consente di visualizzare il nome del set di raccolta al quale fa riferimento questa pagina.</span><span class="sxs-lookup"><span data-stu-id="eb360-155">Displays the name of the collection set that this page refers to.</span></span>  
  
 <span data-ttu-id="eb360-156">**Raccolta e caricamento dati**</span><span class="sxs-lookup"><span data-stu-id="eb360-156">**Data collection and upload**</span></span>  
 <span data-ttu-id="eb360-157">Consente di specificare la modalità di raccolta e caricamento dei dati nel data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="eb360-157">Specifies how data is collected and uploaded to the management data warehouse.</span></span> <span data-ttu-id="eb360-158">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="eb360-158">Pick one of the following options.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eb360-159">**Non-memorizzato nella cache - Raccogli e carica dati in base alla stessa pianificazione.**</span><span class="sxs-lookup"><span data-stu-id="eb360-159">**Non-cached. Collection and data upload on the same schedule.**</span></span>|<span data-ttu-id="eb360-160">Se viene selezionata questa opzione, specificare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="eb360-160">When selected, specify one of the following:</span></span><br /><br /> <span data-ttu-id="eb360-161">**Su richiesta**.</span><span class="sxs-lookup"><span data-stu-id="eb360-161">**On-demand**.</span></span> <span data-ttu-id="eb360-162">I dati sono raccolti e caricati su richiesta.</span><span class="sxs-lookup"><span data-stu-id="eb360-162">Data is collected and uploaded on demand.</span></span><br /><br /> <span data-ttu-id="eb360-163">**Pianifica**</span><span class="sxs-lookup"><span data-stu-id="eb360-163">**Schedule**.</span></span> <span data-ttu-id="eb360-164">I dati sono raccolti e caricati in base a una pianificazione.</span><span class="sxs-lookup"><span data-stu-id="eb360-164">Data is collected and uploaded according to a schedule.</span></span> <span data-ttu-id="eb360-165">Fare clic su **Seleziona** per selezionare da un elenco predefinito di pianificazioni oppure su **Nuovo** per creare una pianificazione nuova.</span><span class="sxs-lookup"><span data-stu-id="eb360-165">Click **Pick** to select from a predefined list of schedules, or click **New** to create a new schedule.</span></span>|  
|<span data-ttu-id="eb360-166">**Memorizzato nella cache - Raccogli e memorizza nella cache i dati in base a un set di frequenze di raccolta. Carica dati memorizzati nella cache in base a una pianificazione separata.**</span><span class="sxs-lookup"><span data-stu-id="eb360-166">**Cached. Collect and cache data at a set of collection frequencies. Upload cached data on a separate schedule.**</span></span>|<span data-ttu-id="eb360-167">I dati sono raccolti e memorizzati nella cache in base alla frequenza di raccolta specificata.</span><span class="sxs-lookup"><span data-stu-id="eb360-167">Collect and cache data for a specified collection frequency.</span></span> <span data-ttu-id="eb360-168">I dati raccolti sono caricati in base a una pianificazione separata.</span><span class="sxs-lookup"><span data-stu-id="eb360-168">Upload the collected data on a separate schedule.</span></span>|  
  
 <span data-ttu-id="eb360-169">**Elementi della raccolta**</span><span class="sxs-lookup"><span data-stu-id="eb360-169">**Collection items**</span></span>  
 <span data-ttu-id="eb360-170">Consente di visualizzare gli elementi del set di raccolta.</span><span class="sxs-lookup"><span data-stu-id="eb360-170">Displays the collection items in the collection set.</span></span> <span data-ttu-id="eb360-171">Per ogni elemento della raccolta sono disponibili le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="eb360-171">The following information is provided for each collection item:</span></span>  
  
-   <span data-ttu-id="eb360-172">**Nome**</span><span class="sxs-lookup"><span data-stu-id="eb360-172">**Name**</span></span>  
  
-   <span data-ttu-id="eb360-173">**Tipo agente di raccolta**</span><span class="sxs-lookup"><span data-stu-id="eb360-173">**Collector Type**</span></span>  
  
-   <span data-ttu-id="eb360-174">**Frequenza di raccolta** (sec).</span><span class="sxs-lookup"><span data-stu-id="eb360-174">**Collection Frequency** (secs).</span></span> <span data-ttu-id="eb360-175">Questo campo può essere modificato se per **Raccolta e caricamento dati** è configurata la memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="eb360-175">This field is editable if **Data collection and upload** is configured as cached.</span></span> <span data-ttu-id="eb360-176">Fare doppio clic su questa cella per impostare la frequenza della raccolta.</span><span class="sxs-lookup"><span data-stu-id="eb360-176">Double-click this cell to set the collection frequency.</span></span>  
  
 <span data-ttu-id="eb360-177">**Parametri di input**</span><span class="sxs-lookup"><span data-stu-id="eb360-177">**Input parameters**</span></span>  
 <span data-ttu-id="eb360-178">Consente di visualizzare i parametri di input utilizzati per il set di raccolta.</span><span class="sxs-lookup"><span data-stu-id="eb360-178">Displays the input parameters used for the collection set.</span></span>  
  
 <span data-ttu-id="eb360-179">**Esegui come**</span><span class="sxs-lookup"><span data-stu-id="eb360-179">**Run as**</span></span>  
 <span data-ttu-id="eb360-180">Consente di specificare l'account utilizzato per eseguire il set di raccolta.</span><span class="sxs-lookup"><span data-stu-id="eb360-180">Specifies the account used to run the collection set.</span></span> <span data-ttu-id="eb360-181">L'impostazione predefinita corrisponde all'account del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agente.</span><span class="sxs-lookup"><span data-stu-id="eb360-181">By default this is the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Service Account.</span></span> <span data-ttu-id="eb360-182">Se sono definiti account proxy, questo elenco contiene i nomi degli account proxy disponibili.</span><span class="sxs-lookup"><span data-stu-id="eb360-182">If proxy accounts are defined, this list includes the names of the available proxy accounts.</span></span>  
  
 <span data-ttu-id="eb360-183">**Specificare per quanto tempo mantenere i dati nel data warehouse di gestione.**</span><span class="sxs-lookup"><span data-stu-id="eb360-183">**Set how long collected data will be retained in the management data warehouse.**</span></span>  
 <span data-ttu-id="eb360-184">Consente di specificare per quanto tempo sono mantenuti i dati raccolti.</span><span class="sxs-lookup"><span data-stu-id="eb360-184">Specifies how long collected data is retained.</span></span> <span data-ttu-id="eb360-185">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="eb360-185">Pick one of the following options.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eb360-186">**Mantieni dati per**</span><span class="sxs-lookup"><span data-stu-id="eb360-186">**Retain data for**</span></span>|<span data-ttu-id="eb360-187">Questa opzione è selezionata per impostazione predefinita e il periodo di memorizzazione predefinito è 14 giorni.</span><span class="sxs-lookup"><span data-stu-id="eb360-187">This option is selected by default, and the default retention period is 14 days.</span></span>|  
|<span data-ttu-id="eb360-188">**Mantieni i dati per un periodo illimitato**</span><span class="sxs-lookup"><span data-stu-id="eb360-188">**Retain data indefinitely**</span></span>|<span data-ttu-id="eb360-189">I dati sono mantenuti senza limiti temporali.</span><span class="sxs-lookup"><span data-stu-id="eb360-189">There is no time limit on the length of time that data is retained.</span></span>|  
  
 <span data-ttu-id="eb360-190">**Pagina Caricamenti**</span><span class="sxs-lookup"><span data-stu-id="eb360-190">**Uploads Page**</span></span>  
  
 <span data-ttu-id="eb360-191">Utilizzare questa pagina per configurare la pianificazione di caricamento per i dati raccolti da questo set di raccolta.</span><span class="sxs-lookup"><span data-stu-id="eb360-191">Use this page to configure the upload schedule for data that is collected by this collection set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eb360-192">Questa scheda è abilitata solo se per **Raccolta e caricamento dati** è configurata l'opzione **Nella cache**.</span><span class="sxs-lookup"><span data-stu-id="eb360-192">This tab is only enabled if the **Cached** option is configured for **Data collection and upload**.</span></span>  
  
 <span data-ttu-id="eb360-193">**Server**</span><span class="sxs-lookup"><span data-stu-id="eb360-193">**Server**</span></span>  
 <span data-ttu-id="eb360-194">Consente di visualizzare il nome del server in cui risiede il data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="eb360-194">Displays the name of the server that hosts the management data warehouse.</span></span> <span data-ttu-id="eb360-195">Per altre informazioni, vedere [Configurare il data warehouse di gestione &#40;SQL Server Management Studio&#41;](configure-the-management-data-warehouse-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="eb360-195">For more information, see [Configure the Management Data Warehouse &#40;SQL Server Management Studio&#41;](configure-the-management-data-warehouse-sql-server-management-studio.md).</span></span>  
  
 <span data-ttu-id="eb360-196">**Data warehouse di gestione**</span><span class="sxs-lookup"><span data-stu-id="eb360-196">**Management data warehouse**</span></span>  
 <span data-ttu-id="eb360-197">Consente di visualizzare il nome del data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="eb360-197">Displays the name of the management data warehouse.</span></span> <span data-ttu-id="eb360-198">Per altre informazioni, vedere [Configurare il data warehouse di gestione &#40;SQL Server Management Studio&#41;](configure-the-management-data-warehouse-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="eb360-198">For more information, see [Configure the Management Data Warehouse &#40;SQL Server Management Studio&#41;](configure-the-management-data-warehouse-sql-server-management-studio.md).</span></span>  
  
 <span data-ttu-id="eb360-199">**Ultimo caricamento**</span><span class="sxs-lookup"><span data-stu-id="eb360-199">**Last upload**</span></span>  
 <span data-ttu-id="eb360-200">Consente di visualizzare le informazioni sulla data e ora in cui è stato eseguito l'ultimo caricamento per il set di raccolta.</span><span class="sxs-lookup"><span data-stu-id="eb360-200">Displays date and time information for the last upload done for the collection set.</span></span>  
  
 <span data-ttu-id="eb360-201">**Pianificazione caricamento**</span><span class="sxs-lookup"><span data-stu-id="eb360-201">**Upload schedule**</span></span>  
 <span data-ttu-id="eb360-202">Consente di specificare la pianificazione di caricamento per il set di raccolta.</span><span class="sxs-lookup"><span data-stu-id="eb360-202">Specifies the upload schedule for the collection set.</span></span> <span data-ttu-id="eb360-203">Se abilitata, fare clic su **Seleziona** per selezionare da un elenco predefinito di pianificazioni oppure su **Nuovo** per creare una nuova pianificazione.</span><span class="sxs-lookup"><span data-stu-id="eb360-203">If enabled, Click **Pick** to select from a predefined list of schedules, or click **New** to create a new schedule.</span></span>  
  
 <span data-ttu-id="eb360-204">**Pagina Descrizione**</span><span class="sxs-lookup"><span data-stu-id="eb360-204">**Description Page**</span></span>  
  
 <span data-ttu-id="eb360-205">Utilizzare questa pagina per visualizzare una descrizione del set di raccolta a cui fa riferimento questa pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="eb360-205">Use this page to view a description of the collection set that this properties page refers to.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb360-206">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb360-206">See Also</span></span>  
 <span data-ttu-id="eb360-207">[Gestire raccolta dati](manage-data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="eb360-207">[Manage Data Collection](manage-data-collection.md) </span></span>  
 [<span data-ttu-id="eb360-208">Raccolta dati</span><span class="sxs-lookup"><span data-stu-id="eb360-208">Data Collection</span></span>](data-collection.md)  
  
  
