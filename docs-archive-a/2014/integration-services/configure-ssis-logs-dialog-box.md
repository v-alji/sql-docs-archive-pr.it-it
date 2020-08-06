---
title: Finestra di dialogo Configura log SSIS | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.configuredtslogs.loggingdetails.f1
- sql12.dts.designer.configuredtslogs.providersandlogs.f1
- sql12.dts.designer.configuredtslogs.containers.f1
helpviewer_keywords:
- Configure SSIS Logs dialog box
ms.assetid: 4b980275-cd9a-4943-8c36-727d51f9a484
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 252b45765fb784790bcca0fb86e2e56e7e7baddc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627338"
---
# <a name="configure-ssis-logs-dialog-box"></a><span data-ttu-id="3b8a3-102">Configura log SSIS - finestra di dialogo</span><span class="sxs-lookup"><span data-stu-id="3b8a3-102">Configure SSIS Logs Dialog Box</span></span>
  <span data-ttu-id="3b8a3-103">Utilizzare la finestra di dialogo **Configura log SSIS** per definire le opzioni di registrazione per un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-103">Use the **Configure SSIS Logs** dialog box to define logging options for a package.</span></span>  
  
 <span data-ttu-id="3b8a3-104">**Per saperne di più**</span><span class="sxs-lookup"><span data-stu-id="3b8a3-104">**What do you want to do?**</span></span>  
  
1.  [<span data-ttu-id="3b8a3-105">Apertura della finestra di dialogo Configura log SSIS</span><span class="sxs-lookup"><span data-stu-id="3b8a3-105">Open the Configure SSIS Logs Dialog Box</span></span>](#open_dialog)  
  
2.  [<span data-ttu-id="3b8a3-106">Configurazione delle opzioni nel riquadro Contenitori</span><span class="sxs-lookup"><span data-stu-id="3b8a3-106">Configure the Options in the Containers Pane</span></span>](#container)  
  
3.  [<span data-ttu-id="3b8a3-107">Configurazione delle opzioni nella scheda Provider e log</span><span class="sxs-lookup"><span data-stu-id="3b8a3-107">Configure the Options on the Providers and Logs Tab</span></span>](#provider)  
  
4.  [<span data-ttu-id="3b8a3-108">Configurazione delle opzioni nella scheda Dettagli</span><span class="sxs-lookup"><span data-stu-id="3b8a3-108">Configure the Options on the Details Tab</span></span>](#detail)  
  
##  <a name="open-the-configure-ssis-logs-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="3b8a3-109">Apertura della finestra di dialogo Configura log SSIS</span><span class="sxs-lookup"><span data-stu-id="3b8a3-109">Open the Configure SSIS Logs Dialog Box</span></span>  
 <span data-ttu-id="3b8a3-110">**Per aprire la finestra di dialogo Configura log SSIS**</span><span class="sxs-lookup"><span data-stu-id="3b8a3-110">**To open the Configure SSIS Logs dialog box**</span></span>  
  
-   <span data-ttu-id="3b8a3-111">In Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] scegliere **Registrazione** nel menu **SSIS** .</span><span class="sxs-lookup"><span data-stu-id="3b8a3-111">In the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click **Logging** on the **SSIS** menu.</span></span>  
  
##  <a name="configure-the-options-in-the-containers-pane"></a><a name="container"></a> <span data-ttu-id="3b8a3-112">Configurazione delle opzioni nel riquadro Contenitori</span><span class="sxs-lookup"><span data-stu-id="3b8a3-112">Configure the Options in the Containers Pane</span></span>  
 <span data-ttu-id="3b8a3-113">Utilizzare il riquadro **Contenitori** della finestra di dialogo **Configura log SSIS** per abilitare il pacchetto e i relativi contenitori per la registrazione.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-113">Use the **Containers** pane of the **Configure SSIS Logs** dialog box to enable the package and its containers for logging.</span></span>  
  
### <a name="options"></a><span data-ttu-id="3b8a3-114">Opzioni</span><span class="sxs-lookup"><span data-stu-id="3b8a3-114">Options</span></span>  
 <span data-ttu-id="3b8a3-115">**Contenitori**</span><span class="sxs-lookup"><span data-stu-id="3b8a3-115">**Containers**</span></span>  
 <span data-ttu-id="3b8a3-116">Nella visualizzazione gerarchica selezionare le caselle di controllo in modo da abilitare il pacchetto e i relativi contenitori per la registrazione:</span><span class="sxs-lookup"><span data-stu-id="3b8a3-116">Select the check boxes in the hierarchical view to enable the package and its containers for logging:</span></span>  
  
-   <span data-ttu-id="3b8a3-117">Se deselezionato, il contenitore non è abilitato per la registrazione.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-117">If cleared, the container is not enabled for logging.</span></span> <span data-ttu-id="3b8a3-118">Selezionarlo per abilitare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-118">Select to enable logging.</span></span>  
  
-   <span data-ttu-id="3b8a3-119">Se visualizzato in grigio, il contenitore utilizza le opzioni di registrazione dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-119">If dimmed, the container uses the logging options of its parent.</span></span> <span data-ttu-id="3b8a3-120">Questa opzione non è disponibile per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-120">This option is not available for the package.</span></span>  
  
-   <span data-ttu-id="3b8a3-121">Se selezionato, il contenitore definisce opzioni di registrazione specifiche.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-121">If checked, the container defines its own logging options.</span></span>  
  
 <span data-ttu-id="3b8a3-122">Se si desidera impostare le opzioni di registrazione per un contenitore visualizzato in grigio, fare doppio clic sulla casella di controllo corrispondente al contenitore in questione.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-122">If a container is dimmed and you want to set logging options on the container, click its check box twice.</span></span> <span data-ttu-id="3b8a3-123">Al primo clic la casella di controllo viene deselezionata e al secondo clic viene selezionata, consentendo di scegliere il provider di log da utilizzare e di specificare le informazioni da registrare.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-123">The first click clears the check box, and the second click selects it, enabling you to choose the log providers to use and select the information to log.</span></span>  
  
##  <a name="configure-the-options-on-the-providers-and-logs-tab"></a><a name="provider"></a> <span data-ttu-id="3b8a3-124">Configurazione delle opzioni nella scheda Provider e log</span><span class="sxs-lookup"><span data-stu-id="3b8a3-124">Configure the Options on the Providers and Logs Tab</span></span>  
 <span data-ttu-id="3b8a3-125">Usare la scheda **Provider e log** della finestra di dialogo **Configura log SSIS** per creare e configurare log per l'acquisizione di eventi di runtime.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-125">Use the **Providers and Logs** tab of the **Configure SSIS Logs** dialog box to create and configure logs for capturing run-time events.</span></span>  
  
### <a name="options"></a><span data-ttu-id="3b8a3-126">Opzioni</span><span class="sxs-lookup"><span data-stu-id="3b8a3-126">Options</span></span>  
 <span data-ttu-id="3b8a3-127">**Tipo provider**</span><span class="sxs-lookup"><span data-stu-id="3b8a3-127">**Provider type**</span></span>  
 <span data-ttu-id="3b8a3-128">Consente di selezionare un tipo di logger nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-128">Select a type of log provider from the list.</span></span>  
  
 <span data-ttu-id="3b8a3-129">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="3b8a3-129">**Add**</span></span>  
 <span data-ttu-id="3b8a3-130">Consente di aggiungere un log del tipo specificato alla raccolta di logger del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-130">Add a log of the specified type to the collection of log providers of the package.</span></span>  
  
 <span data-ttu-id="3b8a3-131">**Nome**</span><span class="sxs-lookup"><span data-stu-id="3b8a3-131">**Name**</span></span>  
 <span data-ttu-id="3b8a3-132">Consente di abilitare o disabilitare log per contenitori o attività selezionati nel riquadro **Contenitori** della finestra di dialogo **Configura log SSIS** usando le caselle di controllo.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-132">Enable or disable logs for containers or tasks selected in the **Containers** pane of the **Configure SSIS Logs** dialog box, by using the check boxes.</span></span> <span data-ttu-id="3b8a3-133">Il campo del nome è modificabile.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-133">The name field is editable.</span></span> <span data-ttu-id="3b8a3-134">Utilizzare il nome predefinito per il provider oppure digitare un nome descrittivo univoco.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-134">Use the default name for the provider, or type a unique descriptive name.</span></span>  
  
 <span data-ttu-id="3b8a3-135">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="3b8a3-135">**Description**</span></span>  
 <span data-ttu-id="3b8a3-136">Il campo della descrizione è modificabile.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-136">The description field is editable.</span></span> <span data-ttu-id="3b8a3-137">Fare clic nel campo e quindi modificare la descrizione predefinita del log.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-137">Click and then modify the default description of the log.</span></span>  
  
 <span data-ttu-id="3b8a3-138">**Configurazione**</span><span class="sxs-lookup"><span data-stu-id="3b8a3-138">**Configuration**</span></span>  
 <span data-ttu-id="3b8a3-139">Selezionare una gestione connessione esistente nell'elenco oppure fare clic su \<**New connection...**> per creare una nuova gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-139">Select an existing connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span> <span data-ttu-id="3b8a3-140">A seconda del tipo di logger, è possibile configurare una gestione connessione OLE DB o una gestione connessione file.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-140">Depending on the type of log provider, you can configure an OLE DB connection manager or a File connection manager.</span></span> <span data-ttu-id="3b8a3-141">Il logger per il registro eventi di [!INCLUDE[msCoName](../includes/msconame-md.md)] non necessita di connessioni.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-141">The log provider for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Event Log requires no connection.</span></span>  
  
 <span data-ttu-id="3b8a3-142">Argomenti correlati: [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md) e [File Connection Manager](connection-manager/file-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="3b8a3-142">Related Topics: [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md) manager, [File Connection Manager](connection-manager/file-connection-manager.md)</span></span>  
  
 <span data-ttu-id="3b8a3-143">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="3b8a3-143">**Delete**</span></span>  
 <span data-ttu-id="3b8a3-144">Selezionare un provider di log e fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-144">Select a log provider and then click **Delete**.</span></span>  
  
##  <a name="configure-the-options-on-the-details-tab"></a><a name="detail"></a> <span data-ttu-id="3b8a3-145">Configurazione delle opzioni nella scheda Dettagli</span><span class="sxs-lookup"><span data-stu-id="3b8a3-145">Configure the Options on the Details Tab</span></span>  
 <span data-ttu-id="3b8a3-146">Utilizzare la scheda **Dettagli** della finestra di dialogo **Configura log SSIS** per indicare gli eventi da abilitare per la registrazione e specificare le informazioni da registrare.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-146">Use the **Details** tab of the **Configure SSIS Logs** dialog box to specify the events to enable for logging and the information details to log.</span></span> <span data-ttu-id="3b8a3-147">Le informazioni selezionate saranno valide per tutti i provider di log nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-147">The information that you select applies to all the log providers in the package.</span></span> <span data-ttu-id="3b8a3-148">Non è ad esempio possibile scrivere informazioni nell'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] diverse da quelle specificate in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-148">For example, you cannot write some information to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance and different information to a text file.</span></span>  
  
### <a name="options"></a><span data-ttu-id="3b8a3-149">Opzioni</span><span class="sxs-lookup"><span data-stu-id="3b8a3-149">Options</span></span>  
 <span data-ttu-id="3b8a3-150">**Eventi**</span><span class="sxs-lookup"><span data-stu-id="3b8a3-150">**Events**</span></span>  
 <span data-ttu-id="3b8a3-151">Consente di abilitare o disabilitare gli eventi per la registrazione.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-151">Enable or disable events for logging.</span></span>  
  
 <span data-ttu-id="3b8a3-152">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="3b8a3-152">**Description**</span></span>  
 <span data-ttu-id="3b8a3-153">Consente di visualizzare una descrizione dell'evento.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-153">View a description of the event.</span></span>  
  
 <span data-ttu-id="3b8a3-154">**Funzionalità avanzate**</span><span class="sxs-lookup"><span data-stu-id="3b8a3-154">**Advanced**</span></span>  
 <span data-ttu-id="3b8a3-155">Consente di selezionare o deselezionare gli eventi da registrare, nonché le informazioni da registrare per ogni evento.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-155">Select or clear events to log, and select or clear information to log for each event.</span></span> <span data-ttu-id="3b8a3-156">Fare clic su **Standard** per nascondere tutti i dettagli di registrazione, ad eccezione dell'elenco di eventi.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-156">Click **Basic** to hide all logging details, except the list of events.</span></span> <span data-ttu-id="3b8a3-157">Per la registrazione sono disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b8a3-157">The following information is available for logging:</span></span>  
  
|<span data-ttu-id="3b8a3-158">valore</span><span class="sxs-lookup"><span data-stu-id="3b8a3-158">Value</span></span>|<span data-ttu-id="3b8a3-159">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3b8a3-159">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3b8a3-160">**Computer**</span><span class="sxs-lookup"><span data-stu-id="3b8a3-160">**Computer**</span></span>|<span data-ttu-id="3b8a3-161">Nome del computer in cui si è verificato l'evento registrato.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-161">The name of the computer on which the logged event occurred.</span></span>|  
|<span data-ttu-id="3b8a3-162">**Operatore**</span><span class="sxs-lookup"><span data-stu-id="3b8a3-162">**Operator**</span></span>|<span data-ttu-id="3b8a3-163">Nome utente dell'utente che ha avviato il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-163">The user name of the person who started the package.</span></span>|  
|<span data-ttu-id="3b8a3-164">**SourceName**</span><span class="sxs-lookup"><span data-stu-id="3b8a3-164">**SourceName**</span></span>|<span data-ttu-id="3b8a3-165">Nome del pacchetto, contenitore o attività in cui si è verificato l'evento registrato.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-165">The name of the package, container, or task in which the logged event occurred.</span></span>|  
|<span data-ttu-id="3b8a3-166">**SourceID**</span><span class="sxs-lookup"><span data-stu-id="3b8a3-166">**SourceID**</span></span>|<span data-ttu-id="3b8a3-167">Identificatore univoco globale (GUID, Global Unique Identifier) del pacchetto, contenitore o attività in cui si è verificato l'evento registrato.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-167">The global unique identifier (GUID) of the package, container, or task in which the logged event occurred.</span></span>|  
|<span data-ttu-id="3b8a3-168">**ExecutionID**</span><span class="sxs-lookup"><span data-stu-id="3b8a3-168">**ExecutionID**</span></span>|<span data-ttu-id="3b8a3-169">Identificatore univoco globale dell'istanza di esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-169">The global unique identifier of the package execution instance.</span></span>|  
|<span data-ttu-id="3b8a3-170">**MessageText**</span><span class="sxs-lookup"><span data-stu-id="3b8a3-170">**MessageText**</span></span>|<span data-ttu-id="3b8a3-171">Messaggio associato alla voce di log.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-171">A message associated with the log entry.</span></span>|  
|<span data-ttu-id="3b8a3-172">**DataBytes**</span><span class="sxs-lookup"><span data-stu-id="3b8a3-172">**DataBytes**</span></span>|<span data-ttu-id="3b8a3-173">Riservato per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-173">Reserved for future use.</span></span>|  
  
 <span data-ttu-id="3b8a3-174">**Base**</span><span class="sxs-lookup"><span data-stu-id="3b8a3-174">**Basic**</span></span>  
 <span data-ttu-id="3b8a3-175">Consente di selezionare o deselezionare gli eventi da registrare.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-175">Select or clear events to log.</span></span> <span data-ttu-id="3b8a3-176">Questa opzione può essere utilizzata per nascondere i dettagli di registrazione, ad eccezione dell'elenco di eventi.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-176">This option hides logging details except the list of events.</span></span> <span data-ttu-id="3b8a3-177">Se si seleziona un evento, per impostazione predefinita verranno selezionati anche tutti i relativi dettagli di registrazione.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-177">If you select an event, all logging details are selected for the event by default.</span></span> <span data-ttu-id="3b8a3-178">Fare clic su **Avanzate** per visualizzarli.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-178">Click **Advanced** to show all logging details.</span></span>  
  
 <span data-ttu-id="3b8a3-179">**Load**</span><span class="sxs-lookup"><span data-stu-id="3b8a3-179">**Load**</span></span>  
 <span data-ttu-id="3b8a3-180">Consente di specificare un file XML esistente da utilizzare come modello per l'impostazione delle opzioni di registrazione.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-180">Specify an existing XML file to use as a template for setting logging options.</span></span>  
  
 <span data-ttu-id="3b8a3-181">**Salva**</span><span class="sxs-lookup"><span data-stu-id="3b8a3-181">**Save**</span></span>  
 <span data-ttu-id="3b8a3-182">Consente di salvare i dettagli di configurazione come modello in un file XML.</span><span class="sxs-lookup"><span data-stu-id="3b8a3-182">Save configuration details as a template to an XML file.</span></span>  
  
  
