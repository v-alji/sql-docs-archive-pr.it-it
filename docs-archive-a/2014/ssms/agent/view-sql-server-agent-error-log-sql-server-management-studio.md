---
title: Visualizzare il log degli errori di SQL Server Agent (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], SQL Server Agent
- viewing SQL Server Agent error logs
- displaying SQL Server Agent error logs
- SQL Server Agent, errors
- errors [SQL Server Agent]
ms.assetid: de920425-fa44-469f-b83d-49e3f97e97f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: b88214a158a970a754c5f313bde3d53f2652ae73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719386"
---
# <a name="view-sql-server-agent-error-log-sql-server-management-studio"></a><span data-ttu-id="a0695-102">View SQL Server Agent Error Log (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="a0695-102">View SQL Server Agent Error Log (SQL Server Management Studio)</span></span>
  <span data-ttu-id="a0695-103">In questo argomento viene descritto come visualizzare il log degli errori di  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0695-103">This topic describes how to view the  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="a0695-104">Nel Visualizzatore file di log sono visualizzate informazioni sui log relativi a molti componenti diversi.</span><span class="sxs-lookup"><span data-stu-id="a0695-104">Log File Viewer displays log information from many different components.</span></span> <span data-ttu-id="a0695-105">Quando il Visualizzatore file di log è aperto, selezionare i log che si desidera visualizzare nel riquadro **Seleziona log** .</span><span class="sxs-lookup"><span data-stu-id="a0695-105">When Log File Viewer is open, use the **Select logs** pane to select the logs you want to display.</span></span> <span data-ttu-id="a0695-106">In ogni log vengono visualizzate le colonne appropriate per il tipo di log specifico.</span><span class="sxs-lookup"><span data-stu-id="a0695-106">Each log displays columns appropriate to that kind of log.</span></span> <span data-ttu-id="a0695-107">I log disponibili dipendono dalla modalità di apertura del Visualizzatore file di log.</span><span class="sxs-lookup"><span data-stu-id="a0695-107">The logs that are available depend on how Log File Viewer is opened.</span></span>  
  
 <span data-ttu-id="a0695-108">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="a0695-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a0695-109">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="a0695-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a0695-110">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="a0695-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a0695-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a0695-111">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="a0695-112">Per visualizzare il log degli errori di SQL Server Agent utilizzando SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a0695-112">To view the SQL Server Agent error log, using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a0695-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="a0695-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a0695-114">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="a0695-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="a0695-115">In Esplora oggetti viene visualizzato il nodo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent solo se si dispone dell'autorizzazione per utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="a0695-115">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a0695-116">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a0695-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a0695-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="a0695-117">Permissions</span></span>  
 <span data-ttu-id="a0695-118">Per la corretta esecuzione delle funzioni, è necessario che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sia configurato per utilizzare le credenziali di un account membro del ruolo predefinito del server **sysadmin** in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0695-118">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a0695-119">L'account deve disporre delle autorizzazioni di Windows seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0695-119">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="a0695-120">Accesso come servizio (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="a0695-120">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="a0695-121">Sostituzione di token a livello di processo (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="a0695-121">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="a0695-122">Ignorare controllo incrociato (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="a0695-122">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="a0695-123">Regolazione quote di memoria per un processo (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="a0695-123">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="a0695-124">Per ulteriori informazioni sulle autorizzazioni di Windows necessarie per l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account del servizio Agent, vedere [selezionare un account per il servizio SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md) e [configurare account di servizio e autorizzazioni di Windows](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="a0695-124">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a0695-125">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a0695-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-ssnoversion-agent-error-log"></a><span data-ttu-id="a0695-126">Per visualizzare il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0695-126">To view the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log</span></span>  
  
1.  <span data-ttu-id="a0695-127">In **Esplora oggetti**fare clic sul segno più per espandere il server che contiene il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="a0695-127">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log that you want to view.</span></span>  
  
2.  <span data-ttu-id="a0695-128">Fare clic sul segno più per espandere **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="a0695-128">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="a0695-129">Fare clic sul segno più per espandere la cartella **Log degli errori** .</span><span class="sxs-lookup"><span data-stu-id="a0695-129">Click the plus sign to expand the **Error Logs** folder.</span></span>  
  
4.  <span data-ttu-id="a0695-130">Fare clic con il pulsante destro del mouse sul log degli errori da visualizzare e selezionare **Visualizza log agente**.</span><span class="sxs-lookup"><span data-stu-id="a0695-130">Right-click the error log you want to view and select **View Agent Log**.</span></span>  
  
     <span data-ttu-id="a0695-131">Nella finestra di dialogo **Visualizzatore file di log-**_server_name_ sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0695-131">The following options are available in the **Log File Viewer -**_server_name_ dialog box:</span></span>  
  
     <span data-ttu-id="a0695-132">**Carica log**</span><span class="sxs-lookup"><span data-stu-id="a0695-132">**Load Log**</span></span>  
     <span data-ttu-id="a0695-133">Consente di aprire una finestra di dialogo in cui è possibile specificare un file di log da caricare.</span><span class="sxs-lookup"><span data-stu-id="a0695-133">Open a dialog box where you can specify a log file to load.</span></span>  
  
     <span data-ttu-id="a0695-134">**Export**</span><span class="sxs-lookup"><span data-stu-id="a0695-134">**Export**</span></span>  
     <span data-ttu-id="a0695-135">Consente di aprire una finestra di dialogo in cui è possibile esportare in un file di testo le informazioni visualizzate nella griglia **Riepilogo file di log** .</span><span class="sxs-lookup"><span data-stu-id="a0695-135">Open a dialog box that lets you export the information that is shown in the **Log file summary** grid to a text file.</span></span>  
  
     <span data-ttu-id="a0695-136">**Aggiorna**</span><span class="sxs-lookup"><span data-stu-id="a0695-136">**Refresh**</span></span>  
     <span data-ttu-id="a0695-137">Consente di aggiornare la visualizzazione dei log selezionati.</span><span class="sxs-lookup"><span data-stu-id="a0695-137">Refresh the view of the selected logs.</span></span> <span data-ttu-id="a0695-138">Il pulsante **Aggiorna** consente di leggere nuovamente i log selezionati dal server di destinazione applicando qualsiasi impostazione di filtro.</span><span class="sxs-lookup"><span data-stu-id="a0695-138">The **Refresh** button rereads the selected logs from the target server while applying any filter settings.</span></span>  
  
     <span data-ttu-id="a0695-139">**Filter**</span><span class="sxs-lookup"><span data-stu-id="a0695-139">**Filter**</span></span>  
     <span data-ttu-id="a0695-140">Consente di aprire una finestra di dialogo in cui è possibile specificare le impostazioni usate per filtrare il file di log, ad esempio **Connessione**, **Data**o altri criteri di filtro **generali** .</span><span class="sxs-lookup"><span data-stu-id="a0695-140">Open a dialog box that lets you specify settings that are used to filter the log file, such as **Connection**, **Date**, or other **General** filter criteria.</span></span>  
  
     <span data-ttu-id="a0695-141">**Ricerca**</span><span class="sxs-lookup"><span data-stu-id="a0695-141">**Search**</span></span>  
     <span data-ttu-id="a0695-142">Consente di cercare testo specifico nel file di log.</span><span class="sxs-lookup"><span data-stu-id="a0695-142">Search the log file for specific text.</span></span> <span data-ttu-id="a0695-143">La ricerca con caratteri jolly non è supportata.</span><span class="sxs-lookup"><span data-stu-id="a0695-143">Searching with wildcard characters is not supported.</span></span>  
  
     <span data-ttu-id="a0695-144">**Stop**</span><span class="sxs-lookup"><span data-stu-id="a0695-144">**Stop**</span></span>  
     <span data-ttu-id="a0695-145">Consente di arrestare il caricamento delle voci del file di log.</span><span class="sxs-lookup"><span data-stu-id="a0695-145">Stops loading the log file entries.</span></span> <span data-ttu-id="a0695-146">È ad esempio possibile utilizzare questa opzione se il caricamento di un file di log remoto o offline richiede parecchio tempo e si desidera visualizzare solo le voci più recenti.</span><span class="sxs-lookup"><span data-stu-id="a0695-146">For example, you can use this option if a remote or offline log file takes a long time to load, and you only want to view the most recent entries.</span></span>  
  
     <span data-ttu-id="a0695-147">**Riepilogo file di log**</span><span class="sxs-lookup"><span data-stu-id="a0695-147">**Log file summary**</span></span>  
     <span data-ttu-id="a0695-148">Consente di visualizzare un riepilogo dei filtri del file di log.</span><span class="sxs-lookup"><span data-stu-id="a0695-148">This information panel displays a summary of the log file filtering.</span></span> <span data-ttu-id="a0695-149">Se non è stato applicato alcun filtro al file, verrà visualizzato il testo **Nessun filtro applicato**.</span><span class="sxs-lookup"><span data-stu-id="a0695-149">If the file is not filtered, you will see the following text, **No filter applied**.</span></span> <span data-ttu-id="a0695-150">Se è stato applicato un filtro al log, verrà visualizzato il testo **Filtra voci del log in cui:** \<filter criteria>.</span><span class="sxs-lookup"><span data-stu-id="a0695-150">If a filter is applied to the log, you will see the following text, **Filter log entries where:** \<filter criteria>.</span></span>  
  
     <span data-ttu-id="a0695-151">**Dettagli riga selezionata**</span><span class="sxs-lookup"><span data-stu-id="a0695-151">**Selected row details**</span></span>  
     <span data-ttu-id="a0695-152">Consente di selezionare una riga di evento nella parte inferiore della pagina per visualizzare dettagli aggiuntivi sulla riga.</span><span class="sxs-lookup"><span data-stu-id="a0695-152">Select a row to display additional details about the selected event row at the bottom of the page.</span></span> <span data-ttu-id="a0695-153">È possibile riordinare le colonne trascinandole su nuove posizioni all'interno della griglia.</span><span class="sxs-lookup"><span data-stu-id="a0695-153">The columns can be reordered by dragging them to new locations in the grid.</span></span> <span data-ttu-id="a0695-154">Le colonne possono inoltre essere ridimensionate trascinando verso destra o verso sinistra le corrispondenti barre di separazione nell'intestazione della griglia.</span><span class="sxs-lookup"><span data-stu-id="a0695-154">The columns can be resized by dragging the column separator bars in the grid header to the left or right.</span></span> <span data-ttu-id="a0695-155">Per adattare automaticamente le dimensioni della colonna al contenuto, fare doppio clic sulle barre di separazione nell'intestazione della griglia.</span><span class="sxs-lookup"><span data-stu-id="a0695-155">Double-click the column separator bars in the grid header to automatically size the column to the content width.</span></span>  
  
     <span data-ttu-id="a0695-156">**Istanza**</span><span class="sxs-lookup"><span data-stu-id="a0695-156">**Instance**</span></span>  
     <span data-ttu-id="a0695-157">Nome dell'istanza in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="a0695-157">The name of the instance on which the event occurred.</span></span> <span data-ttu-id="a0695-158">Viene visualizzato come *nome computer*\\*nome istanza*.</span><span class="sxs-lookup"><span data-stu-id="a0695-158">This is displayed as *computer name*\\*instance name*.</span></span>  
  
     <span data-ttu-id="a0695-159">**Data**</span><span class="sxs-lookup"><span data-stu-id="a0695-159">**Date**</span></span>  
     <span data-ttu-id="a0695-160">Visualizza la data dell'evento.</span><span class="sxs-lookup"><span data-stu-id="a0695-160">Displays the date of the event.</span></span>  
  
     <span data-ttu-id="a0695-161">**Origine**</span><span class="sxs-lookup"><span data-stu-id="a0695-161">**Source**</span></span>  
     <span data-ttu-id="a0695-162">Consente di visualizzare la funzionalità di origine da cui è stato creato l'evento, ad esempio il nome del servizio, come MSSQLSERVER.</span><span class="sxs-lookup"><span data-stu-id="a0695-162">Displays the source feature from which the event is created, such as the name of the service (MSSQLSERVER, for example).</span></span> <span data-ttu-id="a0695-163">Questa opzione non viene visualizzata per tutti i tipi di log.</span><span class="sxs-lookup"><span data-stu-id="a0695-163">This does not appear for all log types.</span></span>  
  
     <span data-ttu-id="a0695-164">**Messaggio**</span><span class="sxs-lookup"><span data-stu-id="a0695-164">**Message**</span></span>  
     <span data-ttu-id="a0695-165">Consente di visualizzare i messaggi associati all'evento.</span><span class="sxs-lookup"><span data-stu-id="a0695-165">Displays any messages associated with the event.</span></span>  
  
     <span data-ttu-id="a0695-166">**Tipo log**</span><span class="sxs-lookup"><span data-stu-id="a0695-166">**Log Type**</span></span>  
     <span data-ttu-id="a0695-167">Consente di visualizzare il tipo di log cui appartiene l'evento.</span><span class="sxs-lookup"><span data-stu-id="a0695-167">Displays the type of log to which the event belongs.</span></span> <span data-ttu-id="a0695-168">Tutti i log selezionati vengono visualizzati nella finestra di riepilogo dei log.</span><span class="sxs-lookup"><span data-stu-id="a0695-168">All selected logs appear in the log file summary window.</span></span>  
  
     <span data-ttu-id="a0695-169">**Origine log**</span><span class="sxs-lookup"><span data-stu-id="a0695-169">**Log Source**</span></span>  
     <span data-ttu-id="a0695-170">Visualizza una descrizione del log di origine in cui viene acquisito l'evento.</span><span class="sxs-lookup"><span data-stu-id="a0695-170">Displays a description of the source log in which the event is captured.</span></span>  
  
5.  <span data-ttu-id="a0695-171">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a0695-171">When finished, click **Close**.</span></span>  
  
  
