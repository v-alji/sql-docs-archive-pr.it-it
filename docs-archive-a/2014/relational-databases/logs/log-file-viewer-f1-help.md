---
title: Guida sensibile al contesto del Visualizzatore file di log | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configurelogs.errorlog.f1
helpviewer_keywords:
- Log File Viewer
ms.assetid: 2243845c-4880-4aa0-9ee8-0a97a128996b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c6eadb4baa4a47202b40a9cde1eca896022f31d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627246"
---
# <a name="log-file-viewer-f1-help"></a><span data-ttu-id="1dec4-102">Guida sensibile al contesto del Visualizzatore file di log</span><span class="sxs-lookup"><span data-stu-id="1dec4-102">Log File Viewer F1 Help</span></span>
  <span data-ttu-id="1dec4-103">Nel Visualizzatore file di log sono visualizzate informazioni sui log relativi a molti componenti diversi.</span><span class="sxs-lookup"><span data-stu-id="1dec4-103">Log File Viewer displays log information from many different components.</span></span> <span data-ttu-id="1dec4-104">Quando il Visualizzatore file di log è aperto, selezionare i log che si desidera visualizzare nel riquadro **Seleziona log** .</span><span class="sxs-lookup"><span data-stu-id="1dec4-104">When Log File Viewer is open, use the **Select logs** pane to select the logs you want to display.</span></span> <span data-ttu-id="1dec4-105">In ogni log vengono visualizzate le colonne appropriate per il tipo di log specifico.</span><span class="sxs-lookup"><span data-stu-id="1dec4-105">Each log displays columns appropriate to that kind of log.</span></span>  
  
 <span data-ttu-id="1dec4-106">I log disponibili dipendono dalla modalità di apertura del Visualizzatore file di log.</span><span class="sxs-lookup"><span data-stu-id="1dec4-106">The logs that are available depend on how Log File Viewer is opened.</span></span> <span data-ttu-id="1dec4-107">Per altre informazioni, vedere [Aprire il visualizzatore file di log](open-log-file-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="1dec4-107">For more information, see [Open Log File Viewer](open-log-file-viewer.md).</span></span>  
  
 <span data-ttu-id="1dec4-108">Il numero di righe visualizzate per i log di controllo può essere configurato nella pagina **Esplora oggetti di SQL Server/Comandi** della finestra di dialogo **Strumenti/Opzioni** .</span><span class="sxs-lookup"><span data-stu-id="1dec4-108">The number of rows that are displayed for audit logs can be configured on the **SQL Server Object Explorer/Commands** page of the **Tools/Options** dialog box.</span></span> <span data-ttu-id="1dec4-109">Per le descrizioni delle colonne visualizzate per i log di controllo, vedere [sys.fn_get_audit_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-get-audit-file-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1dec4-109">For descriptions of the columns that are displayed for audit logs, see [sys.fn_get_audit_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-get-audit-file-transact-sql).</span></span>  
  
## <a name="options"></a><span data-ttu-id="1dec4-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1dec4-110">Options</span></span>  
 <span data-ttu-id="1dec4-111">**Carica log**</span><span class="sxs-lookup"><span data-stu-id="1dec4-111">**Load Log**</span></span>  
 <span data-ttu-id="1dec4-112">Consente di aprire una finestra di dialogo in cui è possibile specificare un file di log da caricare.</span><span class="sxs-lookup"><span data-stu-id="1dec4-112">Open a dialog box where you can specify a log file to load.</span></span>  
  
 <span data-ttu-id="1dec4-113">**Export**</span><span class="sxs-lookup"><span data-stu-id="1dec4-113">**Export**</span></span>  
 <span data-ttu-id="1dec4-114">Consente di aprire una finestra di dialogo in cui è possibile esportare in un file di testo le informazioni visualizzate nella griglia **Riepilogo file di log** .</span><span class="sxs-lookup"><span data-stu-id="1dec4-114">Open a dialog box that lets you export the information that is shown in the **Log file summary** grid to a text file.</span></span>  
  
 <span data-ttu-id="1dec4-115">**Aggiorna**</span><span class="sxs-lookup"><span data-stu-id="1dec4-115">**Refresh**</span></span>  
 <span data-ttu-id="1dec4-116">Consente di aggiornare la visualizzazione dei log selezionati.</span><span class="sxs-lookup"><span data-stu-id="1dec4-116">Refresh the view of the selected logs.</span></span> <span data-ttu-id="1dec4-117">Il pulsante **Aggiorna** consente di leggere nuovamente i log selezionati dal server di destinazione applicando qualsiasi impostazione di filtro.</span><span class="sxs-lookup"><span data-stu-id="1dec4-117">The **Refresh** button rereads the selected logs from the target server while applying any filter settings.</span></span>  
  
 <span data-ttu-id="1dec4-118">**Filter**</span><span class="sxs-lookup"><span data-stu-id="1dec4-118">**Filter**</span></span>  
 <span data-ttu-id="1dec4-119">Consente di aprire una finestra di dialogo in cui è possibile specificare le impostazioni usate per filtrare il file di log, ad esempio **Connessione**, **Data**o altri criteri di filtro **generali** .</span><span class="sxs-lookup"><span data-stu-id="1dec4-119">Open a dialog box that lets you specify settings that are used to filter the log file, such as **Connection**, **Date**, or other **General** filter criteria.</span></span>  
  
 <span data-ttu-id="1dec4-120">**Ricerca**</span><span class="sxs-lookup"><span data-stu-id="1dec4-120">**Search**</span></span>  
 <span data-ttu-id="1dec4-121">Consente di cercare testo specifico nel file di log.</span><span class="sxs-lookup"><span data-stu-id="1dec4-121">Search the log file for specific text.</span></span> <span data-ttu-id="1dec4-122">La ricerca con caratteri jolly non è supportata.</span><span class="sxs-lookup"><span data-stu-id="1dec4-122">Searching with wildcard characters is not supported.</span></span>  
  
 <span data-ttu-id="1dec4-123">**Stop**</span><span class="sxs-lookup"><span data-stu-id="1dec4-123">**Stop**</span></span>  
 <span data-ttu-id="1dec4-124">Consente di arrestare il caricamento delle voci del file di log.</span><span class="sxs-lookup"><span data-stu-id="1dec4-124">Stops loading the log file entries.</span></span> <span data-ttu-id="1dec4-125">È ad esempio possibile utilizzare questa opzione se il caricamento di un file di log remoto o offline richiede parecchio tempo e si desidera visualizzare solo le voci più recenti.</span><span class="sxs-lookup"><span data-stu-id="1dec4-125">For example, you can use this option if a remote or offline log file takes a long time to load, and you only want to view the most recent entries.</span></span>  
  
 <span data-ttu-id="1dec4-126">**Riepilogo file di log**</span><span class="sxs-lookup"><span data-stu-id="1dec4-126">**Log file summary**</span></span>  
 <span data-ttu-id="1dec4-127">Consente di visualizzare un riepilogo dei filtri del file di log.</span><span class="sxs-lookup"><span data-stu-id="1dec4-127">This information panel displays a summary of the log file filtering.</span></span> <span data-ttu-id="1dec4-128">Se non è stato applicato alcun filtro al file, verrà visualizzato il testo **Nessun filtro applicato**.</span><span class="sxs-lookup"><span data-stu-id="1dec4-128">If the file is not filtered, you will see the following text, **No filter applied**.</span></span> <span data-ttu-id="1dec4-129">Se è stato applicato un filtro al log, verrà visualizzato il testo **Filtra voci del log in cui:** \<filter criteria>.</span><span class="sxs-lookup"><span data-stu-id="1dec4-129">If a filter is applied to the log, you will see the following text, **Filter log entries where:** \<filter criteria>.</span></span>  
  
 <span data-ttu-id="1dec4-130">**Dettagli riga selezionata**</span><span class="sxs-lookup"><span data-stu-id="1dec4-130">**Selected row details**</span></span>  
 <span data-ttu-id="1dec4-131">Consente di selezionare una riga di evento nella parte inferiore della pagina per visualizzare dettagli aggiuntivi sulla riga.</span><span class="sxs-lookup"><span data-stu-id="1dec4-131">Select a row to display additional details about the selected event row at the bottom of the page.</span></span> <span data-ttu-id="1dec4-132">È possibile riordinare le colonne trascinandole su nuove posizioni all'interno della griglia.</span><span class="sxs-lookup"><span data-stu-id="1dec4-132">The columns can be reordered by dragging them to new locations in the grid.</span></span> <span data-ttu-id="1dec4-133">Le colonne possono inoltre essere ridimensionate trascinando verso destra o verso sinistra le corrispondenti barre di separazione nell'intestazione della griglia.</span><span class="sxs-lookup"><span data-stu-id="1dec4-133">The columns can be resized by dragging the column separator bars in the grid header to the left or right.</span></span> <span data-ttu-id="1dec4-134">Per adattare automaticamente le dimensioni della colonna al contenuto, fare doppio clic sulle barre di separazione nell'intestazione della griglia.</span><span class="sxs-lookup"><span data-stu-id="1dec4-134">Double-click the column separator bars in the grid header to automatically size the column to the content width.</span></span>  
  
 <span data-ttu-id="1dec4-135">**Istanza**</span><span class="sxs-lookup"><span data-stu-id="1dec4-135">**Instance**</span></span>  
 <span data-ttu-id="1dec4-136">Nome dell'istanza in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="1dec4-136">The name of the instance on which the event occurred.</span></span> <span data-ttu-id="1dec4-137">Viene visualizzato come *nome computer*\\*nome istanza*.</span><span class="sxs-lookup"><span data-stu-id="1dec4-137">This is displayed as *computer name*\\*instance name*.</span></span>  
  
## <a name="frequently-displayed-columns"></a><span data-ttu-id="1dec4-138">Colonne generalmente visualizzate</span><span class="sxs-lookup"><span data-stu-id="1dec4-138">Frequently Displayed Columns</span></span>  
 <span data-ttu-id="1dec4-139">**Data**</span><span class="sxs-lookup"><span data-stu-id="1dec4-139">**Date**</span></span>  
 <span data-ttu-id="1dec4-140">Visualizza la data dell'evento.</span><span class="sxs-lookup"><span data-stu-id="1dec4-140">Displays the date of the event.</span></span>  
  
 <span data-ttu-id="1dec4-141">**Origine**</span><span class="sxs-lookup"><span data-stu-id="1dec4-141">**Source**</span></span>  
 <span data-ttu-id="1dec4-142">Consente di visualizzare la funzionalità di origine da cui è stato creato l'evento, ad esempio il nome del servizio, come MSSQLSERVER.</span><span class="sxs-lookup"><span data-stu-id="1dec4-142">Displays the source feature from which the event is created, such as the name of the service (MSSQLSERVER, for example).</span></span> <span data-ttu-id="1dec4-143">Questa opzione non viene visualizzata per tutti i tipi di log.</span><span class="sxs-lookup"><span data-stu-id="1dec4-143">This does not appear for all log types.</span></span>  
  
 <span data-ttu-id="1dec4-144">**Messaggio**</span><span class="sxs-lookup"><span data-stu-id="1dec4-144">**Message**</span></span>  
 <span data-ttu-id="1dec4-145">Consente di visualizzare i messaggi associati all'evento.</span><span class="sxs-lookup"><span data-stu-id="1dec4-145">Displays any messages associated with the event.</span></span>  
  
 <span data-ttu-id="1dec4-146">**Tipo log**</span><span class="sxs-lookup"><span data-stu-id="1dec4-146">**Log Type**</span></span>  
 <span data-ttu-id="1dec4-147">Consente di visualizzare il tipo di log cui appartiene l'evento.</span><span class="sxs-lookup"><span data-stu-id="1dec4-147">Displays the type of log to which the event belongs.</span></span> <span data-ttu-id="1dec4-148">Tutti i log selezionati vengono visualizzati nella finestra di riepilogo dei log.</span><span class="sxs-lookup"><span data-stu-id="1dec4-148">All selected logs appear in the log file summary window.</span></span>  
  
 <span data-ttu-id="1dec4-149">**Origine log**</span><span class="sxs-lookup"><span data-stu-id="1dec4-149">**Log Source**</span></span>  
 <span data-ttu-id="1dec4-150">Visualizza una descrizione del log di origine in cui viene acquisito l'evento.</span><span class="sxs-lookup"><span data-stu-id="1dec4-150">Displays a description of the source log in which the event is captured.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="1dec4-151">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="1dec4-151">Permissions</span></span>  
 <span data-ttu-id="1dec4-152">Per accedere ai file di log per le istanze di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] online, è necessaria l'appartenenza al ruolo predefinito del server securityadmin.</span><span class="sxs-lookup"><span data-stu-id="1dec4-152">To access log files for instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that are online, this requires membership in the securityadmin fixed server role.</span></span>  
  
 <span data-ttu-id="1dec4-153">Per accedere a file di log per istanze di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] offline, è necessario avere accesso in lettura sia allo spazio dei nomi WMI **Root\Microsoft\SqlServer\ComputerManagement10** sia alla cartella in cui sono archiviati i file di log.</span><span class="sxs-lookup"><span data-stu-id="1dec4-153">To access log files for instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that are offline, you must have read access to both the **Root\Microsoft\SqlServer\ComputerManagement10** WMI namespace, and to the folder where the log files are stored.</span></span> <span data-ttu-id="1dec4-154">Per altre informazioni, vedere la sezione Autorizzazioni dell'argomento [Visualizzare file di log offline](view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="1dec4-154">For more information, see the Security section of the topic [View Offline Log Files](view-offline-log-files.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dec4-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1dec4-155">See Also</span></span>  
 <span data-ttu-id="1dec4-156">[Visualizzatore file di log](log-file-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="1dec4-156">[Log File Viewer](log-file-viewer.md) </span></span>  
 <span data-ttu-id="1dec4-157">[Aprire il visualizzatore file di log](open-log-file-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="1dec4-157">[Open Log File Viewer](open-log-file-viewer.md) </span></span>  
 [<span data-ttu-id="1dec4-158">Visualizzare file di log offline</span><span class="sxs-lookup"><span data-stu-id="1dec4-158">View Offline Log Files</span></span>](view-offline-log-files.md)  
  
  
