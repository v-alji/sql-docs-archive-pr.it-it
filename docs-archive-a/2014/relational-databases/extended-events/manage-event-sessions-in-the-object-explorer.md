---
title: Gestire sessioni di eventi in Esplora oggetti | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
ms.assetid: 16849e38-d3fb-414d-8dcb-797b5ffce6ee
author: rothja
ms.author: jroth
ms.openlocfilehash: 1aa33a97137f63348898e6b1fcb7b19b2d218573
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624169"
---
# <a name="manage-event-sessions-in-the-object-explorer"></a><span data-ttu-id="202dd-102">Gestire sessioni di eventi in Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="202dd-102">Manage Event Sessions in the Object Explorer</span></span>
  <span data-ttu-id="202dd-103">In questo argomento vengono illustrate le azioni eseguibili in **Esplora oggetti** che influiscono su Eventi estesi:</span><span class="sxs-lookup"><span data-stu-id="202dd-103">This topic discusses the actions you can take in **Object Explorer** that affect Extended Events:</span></span>  
  
-   <span data-ttu-id="202dd-104">Creare una sessione Eventi estesi</span><span class="sxs-lookup"><span data-stu-id="202dd-104">Create an Extended Events Session</span></span>  
  
-   <span data-ttu-id="202dd-105">Avviare o arrestare una sessione Eventi estesi</span><span class="sxs-lookup"><span data-stu-id="202dd-105">Starting or Stopping an Extended Events Session</span></span>  
  
-   <span data-ttu-id="202dd-106">Esportare una sessione Eventi estesi</span><span class="sxs-lookup"><span data-stu-id="202dd-106">Export an Extended Events Session</span></span>  
  
-   <span data-ttu-id="202dd-107">Importare un modello di sessione Eventi estesi</span><span class="sxs-lookup"><span data-stu-id="202dd-107">Import an Extended Events Session Template</span></span>  
  
-   <span data-ttu-id="202dd-108">Modificare una sessione Eventi estesi</span><span class="sxs-lookup"><span data-stu-id="202dd-108">Edit an Extended Events Session</span></span>  
  
-   <span data-ttu-id="202dd-109">Eliminare una sessione Eventi estesi</span><span class="sxs-lookup"><span data-stu-id="202dd-109">Delete an Extended Events Session</span></span>  
  
## <a name="create-an-extended-events-session"></a><span data-ttu-id="202dd-110">Creare una sessione Eventi estesi</span><span class="sxs-lookup"><span data-stu-id="202dd-110">Create an Extended Events Session</span></span>  
 <span data-ttu-id="202dd-111">Per altre informazioni sulla creazione di una sessione Eventi estesi, vedere [Create an Extended Events Session](../../database-engine/create-an-extended-events-session.md)(Creare una sessione Eventi estesi).</span><span class="sxs-lookup"><span data-stu-id="202dd-111">For more information about creating an Extended Events session, see [Create an Extended Events Session](../../database-engine/create-an-extended-events-session.md).</span></span>  
  
## <a name="starting-or-stopping-an-extended-events-session"></a><span data-ttu-id="202dd-112">Avviare o arrestare una sessione Eventi estesi</span><span class="sxs-lookup"><span data-stu-id="202dd-112">Starting or Stopping an Extended Events Session</span></span>  
 <span data-ttu-id="202dd-113">È possibile avviare o arrestare una sessione eventi estesi tramite l' **editor di query** utilizzando l' `ALTER EVENT SESSION` istruzione oppure utilizzando il nodo **eventi estesi** di **Esplora oggetti**.</span><span class="sxs-lookup"><span data-stu-id="202dd-113">You can start or stop an Extended Events session through the **Query Editor** using the `ALTER EVENT SESSION` statement, or by using the **Extended Events** node of **Object Explorer**.</span></span>  
  
 <span data-ttu-id="202dd-114">Quando si arresta una sessione eventi, questa non viene più elencata come sessione attiva nella DMV sys.dm_xe_sessions.</span><span class="sxs-lookup"><span data-stu-id="202dd-114">When you stop an event session, the session is no longer listed as an active session in the sys.dm_xe_sessions dynamic management view (DMV).</span></span> <span data-ttu-id="202dd-115">La definizione della sessione rimane tuttavia intatta ed è possibile riavviare la sessione.</span><span class="sxs-lookup"><span data-stu-id="202dd-115">However, the session definition remains intact, and you can restart the session.</span></span> <span data-ttu-id="202dd-116">Per rimuovere completamente una definizione di sessione, è necessario eliminare la sessione.</span><span class="sxs-lookup"><span data-stu-id="202dd-116">To completely remove a session definition, you must delete the session.</span></span>  
  
 <span data-ttu-id="202dd-117">Per avviare o arrestare una sessione Eventi estesi, è necessario disporre dell'autorizzazione ALTER ANY EVENT SESSION.</span><span class="sxs-lookup"><span data-stu-id="202dd-117">To start or stop an Extended Events session, you must have the ALTER ANY EVENT SESSION permission.</span></span>  
  
 <span data-ttu-id="202dd-118">Quando si arresta una sessione che prevede l'uso di una destinazione in memoria, ad esempio destinazioni del contatore degli eventi sincroni, di abbinamento degli eventi, bucket o buffer circolare, tutte le informazioni archiviate nel buffer della sessione (colonna target_data della DMV sys.dm_xe_session_targets) andranno perse.</span><span class="sxs-lookup"><span data-stu-id="202dd-118">When you stop a session that uses an in-memory target, such as the ring buffer, bucketing, event pairing, or synchronous event counter targets, all the information stored in the session's buffer (the target_data column of the sys.dm_xe_session_targets DMV) will be lost.</span></span> <span data-ttu-id="202dd-119">Per accedere ai dati degli eventi dopo aver arrestato la sessione, è necessario salvare i dati prima dell'arresto della sessione oppure configurare la sessione in modo che venga utilizzata la destinazione file.</span><span class="sxs-lookup"><span data-stu-id="202dd-119">To access event data after you stop the session, you should either save the data before you stop the session, or configure the session to use the file target.</span></span>  
  
### <a name="start-or-stop-an-extended-events-session-using-query-editor"></a><span data-ttu-id="202dd-120">Avviare o arrestare una sessione Eventi estesi tramite l'Editor di query</span><span class="sxs-lookup"><span data-stu-id="202dd-120">Start or Stop an Extended Events Session Using Query Editor</span></span>  
 <span data-ttu-id="202dd-121">Per avviare una sessione, eseguire le istruzioni seguenti sostituendo *session_name* con il nome della sessione Eventi estesi:</span><span class="sxs-lookup"><span data-stu-id="202dd-121">To start a session, issue the following statements, replacing *session_name* with the name of the Extended Events session:</span></span>  
  
```  
ALTER EVENT SESSION [session_name]  
ON SERVER  
STATE = START  
```  
  
 <span data-ttu-id="202dd-122">Per arrestare una sessione, eseguire le istruzioni seguenti sostituendo *session_name* con il nome della sessione Eventi estesi:</span><span class="sxs-lookup"><span data-stu-id="202dd-122">To stop a session, issue the following statements, replacing *session_name* with the name of the Extended Events session:</span></span>  
  
```  
ALTER EVENT SESSION [session_name]  
ON SERVER  
STATE = STOP  
```  
  
### <a name="start-or-stop-an-extended-events-session-in-object-explorer"></a><span data-ttu-id="202dd-123">Avviare o arrestare una sessione Eventi estesi in Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="202dd-123">Start or Stop an Extended Events Session in Object Explorer</span></span>  
 <span data-ttu-id="202dd-124">Per avviare o arrestare una sessione Eventi estesi in **Esplora oggetti**, espandere i nodi **Gestione**, **Eventi estesi**e **Sessioni** , fare clic con il pulsante destro del mouse su una sessione, quindi scegliere **Avvia sessione** o **Arresta sessione**.</span><span class="sxs-lookup"><span data-stu-id="202dd-124">To start or stop an Extended Events session in **Object Explorer**, expand the **Management**, **Extended Events**, and then **Sessions** nodes and right click on a session and then click **Start Session** or **Stop Session**.</span></span>  
  
## <a name="export-an-extended-events-session-template"></a><span data-ttu-id="202dd-125">Esportare un modello di sessione Eventi estesi</span><span class="sxs-lookup"><span data-stu-id="202dd-125">Export an Extended Events Session Template</span></span>  
 <span data-ttu-id="202dd-126">È possibile esportare una sessione Eventi estesi usando **Esplora oggetti**e salvarla come file modello xml.</span><span class="sxs-lookup"><span data-stu-id="202dd-126">You can export an Extended Events session using **Object Explorer**, and save it as an .xml template file.</span></span> <span data-ttu-id="202dd-127">Ad esempio, è possibile esportare una sessione, quindi applicare il modello a una nuova sessione eventi usando la **Creazione guidata nuova sessione** o la procedura guidata **Nuova sessione** .</span><span class="sxs-lookup"><span data-stu-id="202dd-127">For example, you may want to export a session and then apply the template to a new event session using the **New Session Wizard** or the **New Session** wizard.</span></span>  
  
 <span data-ttu-id="202dd-128">Quando si esporta una sessione, assicurarsi di salvare il file modello in un percorso che utilizza il file system NTFS e di limitare l'accesso agli utenti autorizzati a visualizzare le informazioni.</span><span class="sxs-lookup"><span data-stu-id="202dd-128">When you export a session, make sure that you save the template file to a location that uses the NTFS file system, and that you restrict access to users who are authorized to view the information.</span></span>  
  
 <span data-ttu-id="202dd-129">Per esportare una sessione Eventi estesi in **Esplora oggetti**:</span><span class="sxs-lookup"><span data-stu-id="202dd-129">To export an Extended Events session in **Object Explorer**:</span></span>  
  
1.  <span data-ttu-id="202dd-130">Espandere i nodi **Gestione**, **Eventi estesi**, quindi **Sessioni** .</span><span class="sxs-lookup"><span data-stu-id="202dd-130">Expand the **Management**, **Extended Events**, and then **Sessions** nodes</span></span>  
  
2.  <span data-ttu-id="202dd-131">Fare clic con il pulsante destro del mouse sulla sessione che si vuole esportare e selezionare **Esporta sessione**.</span><span class="sxs-lookup"><span data-stu-id="202dd-131">Right-click the session that you want to export, and select **Export Session**.</span></span>  
  
3.  <span data-ttu-id="202dd-132">Nella finestra di dialogo **Salva con nome** selezionare un percorso in cui salvare il file, digitare il nome del file nella casella **Nome file** , quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="202dd-132">In the **Save As** dialog box, select a location to save the file, type the file name in the **File name** box, and then click **Save**.</span></span>  
  
     <span data-ttu-id="202dd-133">Se si salva il file nel percorso predefinito dei modelli di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , il modello sarà visualizzato nell'elenco a discesa di modelli predefiniti quando si usano la **Creazione guidata nuova sessione** e la finestra di dialogo **Nuova sessione** .</span><span class="sxs-lookup"><span data-stu-id="202dd-133">If you save the file to the default [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] template location, the template will appear in the dropdown list of predefined templates when you use the **New Session Wizard** and **New Session** dialog.</span></span>  
  
## <a name="import-an-extended-events-session-template"></a><span data-ttu-id="202dd-134">Importare un modello di sessione Eventi estesi</span><span class="sxs-lookup"><span data-stu-id="202dd-134">Import an Extended Events Session Template</span></span>  
 <span data-ttu-id="202dd-135">Usando **Esplora oggetti**è possibile importare un modello per una sessione Eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="202dd-135">Using **Object Explorer**, you can import a template for an Extended Events session.</span></span> <span data-ttu-id="202dd-136">È possibile, ad esempio, effettuare questa operazione per creare una sessione da un modello esportato da un'altra istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="202dd-136">For example, you may want to do this to create a session from a template that was exported from another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="202dd-137">Per importare una sessione Eventi estesi, è necessario disporre delle autorizzazioni `ALTER ANY EVENT SESSION`.</span><span class="sxs-lookup"><span data-stu-id="202dd-137">To import an Extended Events session, you must have the necessary `ALTER ANY EVENT SESSION` permissions.</span></span>  
  
 <span data-ttu-id="202dd-138">Prima di importare un file modello, verificare che il file provenga da una fonte attendibile.</span><span class="sxs-lookup"><span data-stu-id="202dd-138">Before you import a template file, make sure that the file is from a trusted source.</span></span> <span data-ttu-id="202dd-139">È necessario salvare i file modello in un percorso che utilizza il file system NTFS e in cui l'accesso è limitato agli utenti autorizzati a visualizzare le informazioni.</span><span class="sxs-lookup"><span data-stu-id="202dd-139">Template files should be saved to a location that uses the NTFS file system and where access is restricted to users who are authorized to view the information.</span></span>  
  
 <span data-ttu-id="202dd-140">Per importare una sessione Eventi estesi:</span><span class="sxs-lookup"><span data-stu-id="202dd-140">To import an Extended Events session:</span></span>  
  
1.  <span data-ttu-id="202dd-141">In **Esplora oggetti**espandere i nodi **Gestione**, quindi **Eventi estesi** .</span><span class="sxs-lookup"><span data-stu-id="202dd-141">In **Object Explorer**, expand the **Management**, and then **Extended Events** nodes.</span></span>  
  
2.  <span data-ttu-id="202dd-142">Fare clic con il pulsante destro del mouse su **Sessioni** e selezionare **Nuova sessione**.</span><span class="sxs-lookup"><span data-stu-id="202dd-142">Right-click **Sessions** and select **New Session**.</span></span>  
  
3.  <span data-ttu-id="202dd-143">Consente di specificare un nome per la sessione.</span><span class="sxs-lookup"><span data-stu-id="202dd-143">Specify a name for the session.</span></span>  
  
4.  <span data-ttu-id="202dd-144">Espandere la casella di riepilogo a discesa **Modello** .</span><span class="sxs-lookup"><span data-stu-id="202dd-144">Expand the **Template** drop down box.</span></span>  
  
5.  <span data-ttu-id="202dd-145">Fare clic su **\<File From ...>Apri** e individuare la sessione (file XML) che si desidera importare.</span><span class="sxs-lookup"><span data-stu-id="202dd-145">Click **\<File From ...>Open** and browse for the session (XML file) you want to import.</span></span>  
  
 <span data-ttu-id="202dd-146">La sessione verrà visualizzata nel nodo **Sessioni** .</span><span class="sxs-lookup"><span data-stu-id="202dd-146">The session appears under the **Sessions** node.</span></span> <span data-ttu-id="202dd-147">Per impostazione predefinita,la sessione non viene avviata.</span><span class="sxs-lookup"><span data-stu-id="202dd-147">By default, the session is not started.</span></span>  
  
## <a name="edit-an-extended-events-session"></a><span data-ttu-id="202dd-148">Modificare una sessione Eventi estesi</span><span class="sxs-lookup"><span data-stu-id="202dd-148">Edit an Extended Events Session</span></span>  
 <span data-ttu-id="202dd-149">È possibile modificare una sessione Eventi estesi in Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="202dd-149">You can edit an Extended Events session in Object Explorer.</span></span>  
  
 <span data-ttu-id="202dd-150">Per modificare una sessione Eventi estesi:</span><span class="sxs-lookup"><span data-stu-id="202dd-150">To edit an Extended Events session:</span></span>  
  
1.  <span data-ttu-id="202dd-151">In **Esplora oggetti**espandere i nodi **Gestione**, **Eventi estesi**, quindi **Sessioni** .</span><span class="sxs-lookup"><span data-stu-id="202dd-151">In **Object Explorer**, expand the **Management**, **Extended Events**, and then **Sessions** nodes.</span></span>  
  
2.  <span data-ttu-id="202dd-152">Fare clic con il pulsante destro del mouse su una sessione e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="202dd-152">Right-click a session and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="202dd-153">Nella sezione **Selezione pagina** selezionare la pagina o le pagine che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="202dd-153">In the **Select a page** section, select the page or pages you want to edit.</span></span>  
  
4.  <span data-ttu-id="202dd-154">Dopo avere completato l'esame della sessione eventi, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="202dd-154">After you finish revising the event session, click **OK**.</span></span>  
  
## <a name="script-an-event-session-definition-using-tsql"></a><span data-ttu-id="202dd-155">Creare uno script per la definizione di una sessione eventi tramite [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="202dd-155">Script an Event Session Definition Using [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
 <span data-ttu-id="202dd-156">Sia nella Creazione guidata nuova sessione che nella finestra di dialogo Nuova sessione è presente un'opzione Script che consente di generare codice [!INCLUDE[tsql](../../includes/tsql-md.md)] per definire la sessione Eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="202dd-156">Both the New Session Wizard and the New Session dialog have a Script option that generates the [!INCLUDE[tsql](../../includes/tsql-md.md)] that defines the Extended Events session.</span></span>  
  
 <span data-ttu-id="202dd-157">Per accedere a [!INCLUDE[tsql](../../includes/tsql-md.md)] per una sessione Eventi estesi esistente, fare clic con il pulsante destro del mouse sul nome della sessione, scegliere **Crea script per sessione**e selezionare quindi **Genera codice per istruzione CREATE in**.</span><span class="sxs-lookup"><span data-stu-id="202dd-157">You can access the [!INCLUDE[tsql](../../includes/tsql-md.md)] for an existing Extended Events session by right clicking the session name, selecting **Script Session as**, and then selecting **Create to**.</span></span>  
  
## <a name="delete-an-extended-events-session"></a><span data-ttu-id="202dd-158">Eliminare una sessione Eventi estesi</span><span class="sxs-lookup"><span data-stu-id="202dd-158">Delete an Extended Events Session</span></span>  
 <span data-ttu-id="202dd-159">È possibile eliminare una sessione Eventi estesi:</span><span class="sxs-lookup"><span data-stu-id="202dd-159">You can delete an Extended Events session:</span></span>  
  
-   <span data-ttu-id="202dd-160">Nell'Editor di query tramite `DROP EVENT SESSION`.</span><span class="sxs-lookup"><span data-stu-id="202dd-160">In Query Editor using `DROP EVENT SESSION`.</span></span>  
  
-   <span data-ttu-id="202dd-161">In **Esplora oggetti**.</span><span class="sxs-lookup"><span data-stu-id="202dd-161">In **Object Explorer**.</span></span>  
  
 <span data-ttu-id="202dd-162">Quando si elimina una sessione eventi, tutte le informazioni di configurazione vengono rimosse e la definizione della sessione non viene più visualizzata nella vista del catalogo sys.server_event_sessions.</span><span class="sxs-lookup"><span data-stu-id="202dd-162">When you delete an event session, all configuration information is removed and the session definition no longer appears in the sys.server_event_sessions catalog view.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="202dd-163">system_health e AlwaysOn_health sono inclusi in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ; non eliminarli.</span><span class="sxs-lookup"><span data-stu-id="202dd-163">system_health and AlwaysOn_health are included with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]; do not delete them.</span></span> <span data-ttu-id="202dd-164">system_health è eliminata per impostazione predefinita (per altre informazioni, vedere [Utilizzare la sessione system_health](use-the-ssms-xe-profiler.md)).</span><span class="sxs-lookup"><span data-stu-id="202dd-164">system_health is enabled by default (for more information, see [Use the system_health Session](use-the-ssms-xe-profiler.md)).</span></span> <span data-ttu-id="202dd-165">Per impostazione predefinita, AlwaysOn_health è disattivato.</span><span class="sxs-lookup"><span data-stu-id="202dd-165">AlwaysOn_health is off by default.</span></span> <span data-ttu-id="202dd-166">Tramite queste sessioni vengono raccolti dati che possono essere utili per la diagnosi dei problemi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="202dd-166">These sessions collect data that can be useful for diagnosing performance issues.</span></span>  
  
 <span data-ttu-id="202dd-167">Per eliminare una sessione Eventi estesi, è necessario disporre dell'autorizzazione ALTER ANY EVENT SESSION.</span><span class="sxs-lookup"><span data-stu-id="202dd-167">To delete an Extended Events session, you must have the ALTER ANY EVENT SESSION permission.</span></span>  
  
 <span data-ttu-id="202dd-168">Per eliminare una sessione Eventi estesi in **Esplora oggetti**:</span><span class="sxs-lookup"><span data-stu-id="202dd-168">To delete an Extended Events session in **Object Explorer**:</span></span>  
  
1.  <span data-ttu-id="202dd-169">Espandere i nodi **Gestione**, **Eventi estesi**, quindi **Sessioni** .</span><span class="sxs-lookup"><span data-stu-id="202dd-169">Expand the **Management**, **Extended Events**, and then **Sessions** nodes.</span></span>  
  
2.  <span data-ttu-id="202dd-170">Fare clic con il pulsante destro del mouse su una sessione e selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="202dd-170">Right-click a session and select **Delete**.</span></span>  
  
3.  <span data-ttu-id="202dd-171">Nella finestra di dialogo **Elimina oggetto** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="202dd-171">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
4.  <span data-ttu-id="202dd-172">Dopo avere completato l'esame della sessione eventi, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="202dd-172">After you finish revising the event session, click **OK**.</span></span>  
  
 <span data-ttu-id="202dd-173">Per eliminare una sessione Eventi estesi nell' **Editor di query**, eseguire le istruzioni seguenti, sostituendo *session_name* con il nome della sessione Eventi estesi da eliminare:</span><span class="sxs-lookup"><span data-stu-id="202dd-173">To delete an Extended Events session in the **Query Editor**, Issue the following statements, replacing *session_name* with the name of the Extended Events session that you want to delete:</span></span>  
  
```  
DROP EVENT SESSION [session_name]  
ON SERVER  
```  
  
  
