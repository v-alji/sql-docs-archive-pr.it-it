---
title: Imposta valori soglia avvisi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dbmmonitor.setwarningthreshold.f1
ms.assetid: 17f93147-e7d9-4092-b4c2-c11b38051171
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2d5fd9c0213d74f3a6b5d0d4cb2f11d3531d336d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716716"
---
# <a name="set-warning-thresholds"></a><span data-ttu-id="3a66a-102">Imposta valori soglia avvisi</span><span class="sxs-lookup"><span data-stu-id="3a66a-102">Set Warning Thresholds</span></span>
  <span data-ttu-id="3a66a-103">Usare questa finestra di dialogo per abilitare e configurare una o più soglie degli avvisi per il database selezionato nell'albero di navigazione della finestra di dialogo **Monitoraggio mirroring del database** .</span><span class="sxs-lookup"><span data-stu-id="3a66a-103">Use this dialog box to enable and configure one or more warning thresholds for the database selected in the navigation tree of the **Database Mirroring Monitor** dialog box.</span></span>  
  
 <span data-ttu-id="3a66a-104">La finestra di dialogo tenta di connettersi a entrambe le istanze del server.</span><span class="sxs-lookup"><span data-stu-id="3a66a-104">The dialog box tries to connect to both server instances.</span></span> <span data-ttu-id="3a66a-105">Queste connessioni vengono stabilite in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="3a66a-105">These connections are established asynchronously.</span></span> <span data-ttu-id="3a66a-106">Nella finestra di dialogo viene visualizzato lo stato di connessione di ogni partner.</span><span class="sxs-lookup"><span data-stu-id="3a66a-106">The dialog shows the connection status of each partner.</span></span> <span data-ttu-id="3a66a-107">Se il partner non è connesso, fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="3a66a-107">If the partner is not connected, you can click **Connect**.</span></span>  
  
 <span data-ttu-id="3a66a-108">**Per utilizzare SQL Server Management Studio per il monitoraggio del mirroring del database**</span><span class="sxs-lookup"><span data-stu-id="3a66a-108">**To use SQL Server Management Studio to monitor database mirroring**</span></span>  
  
-   [<span data-ttu-id="3a66a-109">Avviare il monitoraggio mirroring del database &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3a66a-109">Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;</span></span>](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md)  
  
## <a name="options"></a><span data-ttu-id="3a66a-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="3a66a-110">Options</span></span>  
 <span data-ttu-id="3a66a-111">*Istanza del server e relativo stato di connessione*</span><span class="sxs-lookup"><span data-stu-id="3a66a-111">*Server instance and its connection status*</span></span>  
 <span data-ttu-id="3a66a-112">Nome di un'istanza del server partner nel form _SYSTEM_ **\\** _instance_name_di sistema.</span><span class="sxs-lookup"><span data-stu-id="3a66a-112">Name of a partner server instance in the form _SYSTEM_**\\**_INSTANCE_NAME_.</span></span> <span data-ttu-id="3a66a-113">Per un'istanza del server predefinita, viene visualizzato solo il nome di sistema.</span><span class="sxs-lookup"><span data-stu-id="3a66a-113">For a default server instance, only the system name is displayed.</span></span>  
  
 <span data-ttu-id="3a66a-114">Il campo indica inoltre se il monitoraggio è attualmente connesso all'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="3a66a-114">This field also indicates whether the monitor is currently connected to this server instance.</span></span> <span data-ttu-id="3a66a-115">I possibili stati di connessione sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a66a-115">The possible connection statuses are:</span></span>  
  
-   <span data-ttu-id="3a66a-116">**Non connesso a** *nome_istanza_server*</span><span class="sxs-lookup"><span data-stu-id="3a66a-116">**Not connected to**  *server_instance_name*</span></span>  
  
-   <span data-ttu-id="3a66a-117">**Tentativo di connessione a** *nome_istanza_server* in corso</span><span class="sxs-lookup"><span data-stu-id="3a66a-117">**Trying to connect to**  *server_instance_name*</span></span>  
  
-   <span data-ttu-id="3a66a-118">**Connesso a** *nome_istanza_server*</span><span class="sxs-lookup"><span data-stu-id="3a66a-118">**Connected to**  *server_instance_name*</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3a66a-119">In caso di non appartenenza al ruolo predefinito del server **sysadmin**, lo stato è impostato su **Connesso a** *nome_istanza_server* **(autorizzazioni limitate)** .</span><span class="sxs-lookup"><span data-stu-id="3a66a-119">If you do are not a member of the **sysadmin** fixed server role, this status is **Connected to** *server_instance_name* **(Limited permissions)**.</span></span>  
  
 <span data-ttu-id="3a66a-120">Il nome di ogni istanza del server partner è visualizzato in un campo *Istanza del server e relativo stato di connessione* separato.</span><span class="sxs-lookup"><span data-stu-id="3a66a-120">The name of each of the partner server instances is displayed in a separate *Server instance and its connection status* field.</span></span> <span data-ttu-id="3a66a-121">Il campo in alto indica il server principale all'avvio dell'esecuzione del monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="3a66a-121">The top field lists the principal server when the monitor started running.</span></span>  
  
 <span data-ttu-id="3a66a-122">**Connetti**/**Annulla**</span><span class="sxs-lookup"><span data-stu-id="3a66a-122">**Connect**/**Cancel**</span></span>  
 <span data-ttu-id="3a66a-123">Un pulsante **Connetti**/**Annulla** è associato a ogni *istanza del server e al relativo stato di connessione* .</span><span class="sxs-lookup"><span data-stu-id="3a66a-123">A **Connect**/**Cancel** button is associated with each *Server instance and its connection status* fields.</span></span> <span data-ttu-id="3a66a-124">Lo stato del pulsante dipende dallo stato di connessione:</span><span class="sxs-lookup"><span data-stu-id="3a66a-124">The state of the button depends on the connection status:</span></span>  
  
-   <span data-ttu-id="3a66a-125">Se non è presente alcuna connessione all'istanza del server, il testo del pulsante è **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="3a66a-125">If there is no connection to the server instance, the button text is **Connect**.</span></span> <span data-ttu-id="3a66a-126">Fare clic sul pulsante per connettersi all'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="3a66a-126">Click to connect to the server instance.</span></span>  
  
-   <span data-ttu-id="3a66a-127">Quando è in corso un tentativo di connessione, il testo del pulsante è **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="3a66a-127">When a connection attempt is in progress, the button text is **Cancel**.</span></span> <span data-ttu-id="3a66a-128">Fare clic sul pulsante per annullare il tentativo di connessione.</span><span class="sxs-lookup"><span data-stu-id="3a66a-128">Click to cancel the connection attempt.</span></span>  
  
-   <span data-ttu-id="3a66a-129">Se il server è connesso, il testo del pulsante è **Connesso**e il pulsante è disattivato.</span><span class="sxs-lookup"><span data-stu-id="3a66a-129">If the server is connected, the button text is **Connected**, and the button is dimmed.</span></span>  
  
 <span data-ttu-id="3a66a-130">**Thresholds**</span><span class="sxs-lookup"><span data-stu-id="3a66a-130">**Thresholds**</span></span>  
 <span data-ttu-id="3a66a-131">Nella griglia **Valori soglia** sono visualizzate le impostazioni degli avvisi per le due istanze del server.</span><span class="sxs-lookup"><span data-stu-id="3a66a-131">The **Thresholds** grid displays the warnings settings for the two server instances.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3a66a-132">Se un'istanza del server non è connessa, le relative colonne sono visualizzate con celle vuote e uno sfondo grigio.</span><span class="sxs-lookup"><span data-stu-id="3a66a-132">If a server instance is not connected, its columns are displayed with empty cells and a gray background.</span></span> <span data-ttu-id="3a66a-133">Quando viene stabilita la connessione, nella griglia viene visualizzato automaticamente il contenuto dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="3a66a-133">When the connection opens, the grid automatically displays the content from the instance.</span></span>  
  
 <span data-ttu-id="3a66a-134">La griglia include le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a66a-134">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="3a66a-135">**Avvisi**</span><span class="sxs-lookup"><span data-stu-id="3a66a-135">**Warnings**</span></span>  
 <span data-ttu-id="3a66a-136">Elenca gli avvisi supportati:</span><span class="sxs-lookup"><span data-stu-id="3a66a-136">Lists the supported warnings:</span></span>  
  
|<span data-ttu-id="3a66a-137">Avviso</span><span class="sxs-lookup"><span data-stu-id="3a66a-137">Warning</span></span>|<span data-ttu-id="3a66a-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a66a-138">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3a66a-139">**Avvisa se il log non inviato supera la soglia**</span><span class="sxs-lookup"><span data-stu-id="3a66a-139">**Warn if the unsent log exceeds the threshold**</span></span>|<span data-ttu-id="3a66a-140">La soglia indica il numero di kilobyte (KB), del log non inviato nella coda di invio sull'istanza del server principale.</span><span class="sxs-lookup"><span data-stu-id="3a66a-140">The threshold indicates the number of kilobytes (KB) of the unsent log in the send queue on the principal.</span></span>|  
|<span data-ttu-id="3a66a-141">**Avvisa se il log non ripristinato supera la soglia**</span><span class="sxs-lookup"><span data-stu-id="3a66a-141">**Warn if the unrestored log exceeds the threshold**</span></span>|<span data-ttu-id="3a66a-142">La soglia indica il numero di KB della coda di rollforward sull'istanza del server mirror.</span><span class="sxs-lookup"><span data-stu-id="3a66a-142">The threshold indicates the number of KB of the redo queue on the mirror server instance.</span></span>|  
|<span data-ttu-id="3a66a-143">**Avvisa se il tempo di memorizzazione della transazione non inviata meno recente è superiore alla soglia**</span><span class="sxs-lookup"><span data-stu-id="3a66a-143">**Warn if the age of the oldest unsent transaction exceeds the threshold**</span></span>|<span data-ttu-id="3a66a-144">La soglia indica il numero di minuti delle transazioni non ancora inviate dalla coda di invio all'istanza del server mirror.</span><span class="sxs-lookup"><span data-stu-id="3a66a-144">The threshold indicates the number of minutes of transactions that have not yet been sent from the send queue to the mirror server instance.</span></span> <span data-ttu-id="3a66a-145">Questo valore consente di misurare la potenziale perdita di dati in termini di tempo.</span><span class="sxs-lookup"><span data-stu-id="3a66a-145">This value helps measure the potential for data loss in terms of time.</span></span>|  
|<span data-ttu-id="3a66a-146">**Avvisa se l'overhead di commit del mirror supera la soglia**</span><span class="sxs-lookup"><span data-stu-id="3a66a-146">**Warn if the mirror commit overhead exceeds the threshold**</span></span>|<span data-ttu-id="3a66a-147">La soglia indica il numero di millisecondi di ritardo per transazione (rilevante solo in modalità a protezione elevata).</span><span class="sxs-lookup"><span data-stu-id="3a66a-147">The threshold indicates the number of milliseconds of delay per transaction (relevant only in high-safety mode).</span></span> <span data-ttu-id="3a66a-148">Questo ritardo rappresenta la quantità di overhead generato mentre l'istanza del server principale è in attesa che l'istanza del server mirror scriva il record di log della transazione nella coda di rollforward.</span><span class="sxs-lookup"><span data-stu-id="3a66a-148">This delay is the amount of overhead incurred while the principal server instance waits for the mirror server instance to write the transaction's log record into the redo queue.</span></span>|  
  
 <span data-ttu-id="3a66a-149">**Abilitato su '** *\<server instance>* **'**</span><span class="sxs-lookup"><span data-stu-id="3a66a-149">**Enabled at '** *\<server instance>* **'**</span></span>  
 <span data-ttu-id="3a66a-150">Una casella di controllo deselezionata indica che l'avviso è attualmente disabilitato sull'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="3a66a-150">A blank check box indicates that the warning is currently disabled on the server instance.</span></span> <span data-ttu-id="3a66a-151">Per abilitare un avviso, selezionare la relativa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="3a66a-151">To enable a warning, click its check box.</span></span>  
  
 <span data-ttu-id="3a66a-152">**Valore soglia su '** *\<server instance>* **'**</span><span class="sxs-lookup"><span data-stu-id="3a66a-152">**Threshold at '** *\<server instance>* **'**</span></span>  
 <span data-ttu-id="3a66a-153">Quando un avviso è abilitato, impostare la soglia nella parte sinistra della colonna.</span><span class="sxs-lookup"><span data-stu-id="3a66a-153">When a warning is enabled, set the threshold on the left side of this column.</span></span> <span data-ttu-id="3a66a-154">Un evento si verifica se la soglia specificata viene raggiunta all'aggiornamento della tabella dello stato.</span><span class="sxs-lookup"><span data-stu-id="3a66a-154">An event occurs if the specified threshold has been reached when the status table is updated.</span></span> <span data-ttu-id="3a66a-155">Se si disabilita una soglia dopo aver configurato un valore, il valore configurato rimane nel campo e verrà utilizzato in caso di riabilitazione dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="3a66a-155">If you disable a threshold after configuring a value, your value remains in this field and will be used if you re-enable the warning.</span></span>  
  
 <span data-ttu-id="3a66a-156">Quando un avviso non è abilitato, il campo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="3a66a-156">When a warning is not enabled, this field is inactive.</span></span>  
  
 <span data-ttu-id="3a66a-157">**OK**</span><span class="sxs-lookup"><span data-stu-id="3a66a-157">**OK**</span></span>  
 <span data-ttu-id="3a66a-158">Se si fa clic su **OK** , questa finestra di dialogo viene chiusa e vengono visualizzati i valori attualmente specificati per le soglie degli avvisi nella griglia **Valori di soglia** della pagina a schede **Avvisi**.</span><span class="sxs-lookup"><span data-stu-id="3a66a-158">Clicking **OK** closes this dialog box and displays the currently specified values of warning thresholds in the **Thresholds** grid on the **Warnings**tabbed page.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a66a-159">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3a66a-159">Remarks</span></span>  
 <span data-ttu-id="3a66a-160">Una soglia è applicabile solo a un partner per volta, ma è consigliabile impostare una soglia per un determinato evento su entrambi i partner per assicurare che l'avviso venga mantenuto in caso di failover del database.</span><span class="sxs-lookup"><span data-stu-id="3a66a-160">A threshold is only applicable at one partner at a time, but we recommend that you set a threshold for a given event on both partners to ensure that the warning persists if the database fails over.</span></span> <span data-ttu-id="3a66a-161">La soglia appropriata per ogni partner dipende dalle capacità in termini di prestazioni del sistema di tale partner.</span><span class="sxs-lookup"><span data-stu-id="3a66a-161">The appropriate threshold for each partner depends on the performance capabilities of that partner's system.</span></span>  
  
 <span data-ttu-id="3a66a-162">Un evento viene scritto nel log eventi per una prestazione solo se il relativo valore è uguale o superiore alla relativa soglia quando la tabella dello stato è in fase di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="3a66a-162">An event is written to the event log for a performance only if its value is at or above its threshold when the status table is being updated.</span></span> <span data-ttu-id="3a66a-163">Se un valore di picco raggiunge la soglia solo temporaneamente tra gli aggiornamenti di stato, tale picco non viene segnalato.</span><span class="sxs-lookup"><span data-stu-id="3a66a-163">If a peak value reaches the threshold momentarily between status updates that peak is missed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a66a-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a66a-164">See Also</span></span>  
 <span data-ttu-id="3a66a-165">[Avviare il monitoraggio mirroring del database &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="3a66a-165">[Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="3a66a-166">[Monitoraggio del mirroring del database &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3a66a-166">[Monitoring Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="3a66a-167">Avvio della Configurazione guidata sicurezza mirroring del database &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3a66a-167">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
  
