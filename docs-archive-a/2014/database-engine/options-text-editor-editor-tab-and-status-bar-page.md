---
title: 'Opzioni (editor di testo: pagina scheda Editor e barra di stato) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqleditors.editorcontextsettings
- VS.ToolsOptionsPages.Text_Editor.EditorTabAndStatusBar
ms.assetid: e4815678-7885-4631-878f-c6a2b857ee05
author: rothja
ms.author: jroth
ms.openlocfilehash: 920b7d48b5f7a2472a521af21c8217b1adba486a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636384"
---
# <a name="options-text-editor-editor-tab-and-status-bar-page"></a><span data-ttu-id="07d5d-102">Opzioni (pagina Editor di testo: Scheda editor e barra di stato)</span><span class="sxs-lookup"><span data-stu-id="07d5d-102">Options (Text Editor: Editor Tab and Status Bar Page)</span></span>
  <span data-ttu-id="07d5d-103">Nella **pagina Scheda editor e barra di stato** è possibile personalizzare le informazioni visualizzate dagli editor di query di [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07d5d-103">The **Editor Tab and Status Bar Page** lets you customize the information displayed by the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] Query Editors.</span></span> <span data-ttu-id="07d5d-104">È possibile specificare il livello di informazioni da visualizzare nella scheda e sulla barra di stato della finestra dell'editor di query, nonché specificare se la barra di stato viene visualizzata nella parte superiore o inferiore della finestra dell'editor.</span><span class="sxs-lookup"><span data-stu-id="07d5d-104">You can specify the level of information displayed in the tab and status bar of the Query Editor window, and whether the status bar appears at the top or bottom of the editor window.</span></span>  
  
## <a name="option-settings-by-editor"></a><span data-ttu-id="07d5d-105">Impostazioni delle opzioni in base all'editor</span><span class="sxs-lookup"><span data-stu-id="07d5d-105">Option Settings by Editor</span></span>  
 <span data-ttu-id="07d5d-106">La scheda dell'editor e la barra di stato sono disponibili in tutti gli editor di [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , ma offrono livelli di funzionalità diversi.</span><span class="sxs-lookup"><span data-stu-id="07d5d-106">The editor tab and the status bar are available in all of the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] editors, but have different levels of functionality.</span></span>  
  
 <span data-ttu-id="07d5d-107">L'editor di query del Motore di database è in grado di eseguire la connessione a un gruppo di server e in tal caso vengono aperte connessioni a tutte le istanze nel gruppo di server e la stessa query può venire eseguita contemporaneamente in ogni connessione.</span><span class="sxs-lookup"><span data-stu-id="07d5d-107">The Database Engine Query Editor can connect to a server group, in which case it opens connections to all the instances in the Server Group and can simultaneously run the same query on each connection.</span></span> <span data-ttu-id="07d5d-108">È possibile usare questa finestra di dialogo per specificare che la barra di stato ha un colore diverso quando viene stabilita una connessione a più istanze anziché a un'unica istanza. Per modificare le opzioni relative ai risultati multiserver, usare la pagina [Opzioni (Risultati query/SQL Server/Multiserver)](../../2014/database-engine/options-query-results-sql-server-multi-server.md) .</span><span class="sxs-lookup"><span data-stu-id="07d5d-108">You can use this dialog to specify that the status bar has different colors when connected to multiple instances rather than one instance.To change the multi-server results options, use the [Options (Query Results/SQL Server/Multi-Server)](../../2014/database-engine/options-query-results-sql-server-multi-server.md) page.</span></span>  
  
## <a name="status-bar-content"></a><span data-ttu-id="07d5d-109">Contenuto della barra di stato</span><span class="sxs-lookup"><span data-stu-id="07d5d-109">Status Bar Content</span></span>  
 <span data-ttu-id="07d5d-110">Consente di specificare le informazioni visualizzate nella barra di stato dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="07d5d-110">Specifies the information that appears in the Query Editor status bar.</span></span>  
  
 <span data-ttu-id="07d5d-111">**Visualizza tempo di esecuzione**</span><span class="sxs-lookup"><span data-stu-id="07d5d-111">**Display execution time**</span></span>  
 <span data-ttu-id="07d5d-112">Consente di indicare il tempo di esecuzione degli script.</span><span class="sxs-lookup"><span data-stu-id="07d5d-112">Includes the script execution time.</span></span> <span data-ttu-id="07d5d-113">Sono disponibili le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="07d5d-113">The settings are as follows:</span></span>  
  
 <span data-ttu-id="07d5d-114">**Nessuno**</span><span class="sxs-lookup"><span data-stu-id="07d5d-114">**None**</span></span>  
 <span data-ttu-id="07d5d-115">Sulla barra di stato non viene visualizzata alcuna informazione relativa alla durata dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="07d5d-115">The status bar displays no time information.</span></span>  
  
 <span data-ttu-id="07d5d-116">**Fine**</span><span class="sxs-lookup"><span data-stu-id="07d5d-116">**End**</span></span>  
 <span data-ttu-id="07d5d-117">Sulla barra di stato viene visualizzata l'ora corrente del giorno in cui è in corso l'esecuzione dello script.</span><span class="sxs-lookup"><span data-stu-id="07d5d-117">The status bar displays the current time of day while the script is running.</span></span> <span data-ttu-id="07d5d-118">Quando lo script viene completato, viene visualizzata l'ora corrente del giorno del completamento dello script.</span><span class="sxs-lookup"><span data-stu-id="07d5d-118">When the script completes, the display shows the time of day that the script completed.</span></span>  
  
 <span data-ttu-id="07d5d-119">**Trascorso**</span><span class="sxs-lookup"><span data-stu-id="07d5d-119">**Elapsed**</span></span>  
 <span data-ttu-id="07d5d-120">Sulla barra di stato viene visualizzata la quantità di tempo trascorso da quando lo script è stato eseguito.</span><span class="sxs-lookup"><span data-stu-id="07d5d-120">The status bar displays the length of time that the script has been running.</span></span> <span data-ttu-id="07d5d-121">Quando lo script viene completato, viene visualizzata la quantità di tempo utilizzata per l'esecuzione dello script.</span><span class="sxs-lookup"><span data-stu-id="07d5d-121">When the script completes, the display shows how much time was taken to run the script.</span></span>  
  
 <span data-ttu-id="07d5d-122">**Includi nome database**</span><span class="sxs-lookup"><span data-stu-id="07d5d-122">**Include database name**</span></span>  
 <span data-ttu-id="07d5d-123">Consente di includere il nome del database corrente per la connessione.</span><span class="sxs-lookup"><span data-stu-id="07d5d-123">Includes the name of the current database for the connection.</span></span> <span data-ttu-id="07d5d-124">Quando l'editor di query viene aperto per la prima volta, viene visualizzato il database predefinito per l'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="07d5d-124">When the query editor is first opened, this is the default database for the login.</span></span> <span data-ttu-id="07d5d-125">Il contesto del database può essere modificato successivamente mediante l'istruzione Transact-SQL USE.</span><span class="sxs-lookup"><span data-stu-id="07d5d-125">The database context can later be changed by using the Transact-SQL USE statement.</span></span>  
  
 <span data-ttu-id="07d5d-126">**Includi nome account di accesso**</span><span class="sxs-lookup"><span data-stu-id="07d5d-126">**Include login name**</span></span>  
 <span data-ttu-id="07d5d-127">Consente di includere il nome dell'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="07d5d-127">Includes the login name.</span></span>  
  
 <span data-ttu-id="07d5d-128">**Includi conteggio righe**</span><span class="sxs-lookup"><span data-stu-id="07d5d-128">**Include row count**</span></span>  
 <span data-ttu-id="07d5d-129">Consente di includere un conteggio delle righe elaborate dallo script eseguito.</span><span class="sxs-lookup"><span data-stu-id="07d5d-129">Includes a count of the rows that have been processed by the script that is currently executing.</span></span>  
  
 <span data-ttu-id="07d5d-130">**Includi nome server**</span><span class="sxs-lookup"><span data-stu-id="07d5d-130">**Include server name**</span></span>  
 <span data-ttu-id="07d5d-131">Consente di includere il nome del server.</span><span class="sxs-lookup"><span data-stu-id="07d5d-131">Includes the server name.</span></span> <span data-ttu-id="07d5d-132">Per le connessioni locali, si tratta del nome dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="07d5d-132">For local connections, this is the instance name.</span></span> <span data-ttu-id="07d5d-133">Per le connessioni remote, si tratta del nome del computer remoto e del nome dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="07d5d-133">For remote connections, this is the remote computer name and instance name.</span></span>  
  
## <a name="status-bar-layout-and-colors"></a><span data-ttu-id="07d5d-134">Layout e colori barra di stato</span><span class="sxs-lookup"><span data-stu-id="07d5d-134">Status Bar Layout and Colors</span></span>  
 <span data-ttu-id="07d5d-135">Consente di specificare i colori per gli elementi visualizzati sulla barra di stato dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="07d5d-135">Specifies the colors for items in the Query Editor status bar.</span></span>  
  
 <span data-ttu-id="07d5d-136">**Connessioni di gruppo**</span><span class="sxs-lookup"><span data-stu-id="07d5d-136">**Group connections**</span></span>  
 <span data-ttu-id="07d5d-137">Consente di impostare il colore della barra di stato quando l'editor di query dispone di più di una connessione.</span><span class="sxs-lookup"><span data-stu-id="07d5d-137">Set the color of the status bar when the Query Editor has more than one connection.</span></span>  
  
 <span data-ttu-id="07d5d-138">**Connessioni a un unico server**</span><span class="sxs-lookup"><span data-stu-id="07d5d-138">**Single server connections**</span></span>  
 <span data-ttu-id="07d5d-139">Consente di impostare il colore della barra di stato quando l'editor di query dispone di un'unica connessione.</span><span class="sxs-lookup"><span data-stu-id="07d5d-139">Set the color of the status bar when the Query Editor has one connection.</span></span>  
  
 <span data-ttu-id="07d5d-140">**Posizione della barra di stato**</span><span class="sxs-lookup"><span data-stu-id="07d5d-140">**Status bar location**</span></span>  
 <span data-ttu-id="07d5d-141">Consente di specificare la posizione della barra di stato.</span><span class="sxs-lookup"><span data-stu-id="07d5d-141">Specifies the location of the status bar.</span></span> <span data-ttu-id="07d5d-142">Sono disponibili le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="07d5d-142">The settings are as follows:</span></span>  
  
 <span data-ttu-id="07d5d-143">**Top**</span><span class="sxs-lookup"><span data-stu-id="07d5d-143">**Top**</span></span>  
 <span data-ttu-id="07d5d-144">La barra di stato viene visualizzata nella parte superiore della finestra dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="07d5d-144">The status bar appears at the top of the Query Editor window.</span></span>  
  
 <span data-ttu-id="07d5d-145">**Ultimo**</span><span class="sxs-lookup"><span data-stu-id="07d5d-145">**Bottom**</span></span>  
 <span data-ttu-id="07d5d-146">La barra di stato viene visualizzata nella parte inferiore della finestra dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="07d5d-146">The status bar appears at the bottom of the Query Editor window.</span></span>  
  
## <a name="tab-text"></a><span data-ttu-id="07d5d-147">Testo scheda</span><span class="sxs-lookup"><span data-stu-id="07d5d-147">Tab Text</span></span>  
 <span data-ttu-id="07d5d-148">Consente di specificare il testo visualizzato nella scheda nella parte superiore di una finestra dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="07d5d-148">Specifies the text that appears in the tab at the top of a Query Editor window.</span></span> <span data-ttu-id="07d5d-149">Se il testo è troppo lungo da visualizzare, è possibile visualizzare la stringa completa in una descrizione comando, spostando il puntatore del mouse sulla scheda.</span><span class="sxs-lookup"><span data-stu-id="07d5d-149">If the text is too long to display, you can view the full string in a tooltip that is displayed if you hover over the tab.</span></span>  
  
 <span data-ttu-id="07d5d-150">**Includi nome database**</span><span class="sxs-lookup"><span data-stu-id="07d5d-150">**Include database name**</span></span>  
 <span data-ttu-id="07d5d-151">Consente di includere il nome del database corrente per la connessione.</span><span class="sxs-lookup"><span data-stu-id="07d5d-151">Includes the name of the current database for the connection.</span></span> <span data-ttu-id="07d5d-152">Quando l'editor di query viene aperto per la prima volta, viene visualizzato il database predefinito per l'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="07d5d-152">When the query editor is first opened, this is the default database for the login.</span></span> <span data-ttu-id="07d5d-153">Il contesto del database può essere modificato successivamente mediante l'istruzione Transact-SQL USE.</span><span class="sxs-lookup"><span data-stu-id="07d5d-153">The database context can later be changed by using the Transact-SQL USE statement.</span></span>  
  
 <span data-ttu-id="07d5d-154">**Includi nome file**</span><span class="sxs-lookup"><span data-stu-id="07d5d-154">**Include file name**</span></span>  
 <span data-ttu-id="07d5d-155">Consente di includere il nome del file in cui è archiviato lo script.</span><span class="sxs-lookup"><span data-stu-id="07d5d-155">Includes the name of the file where the script is stored.</span></span>  
  
 <span data-ttu-id="07d5d-156">**Includi nome cartella**</span><span class="sxs-lookup"><span data-stu-id="07d5d-156">**Include folder name**</span></span>  
 <span data-ttu-id="07d5d-157">Consente di includere il percorso della cartella in cui è archiviato il file di script.</span><span class="sxs-lookup"><span data-stu-id="07d5d-157">Includes the path of the folder where the script file is stored.</span></span>  
  
 <span data-ttu-id="07d5d-158">**Includi nome account di accesso**</span><span class="sxs-lookup"><span data-stu-id="07d5d-158">**Include login name**</span></span>  
 <span data-ttu-id="07d5d-159">Consente di includere il nome dell'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="07d5d-159">Includes the login name.</span></span>  
  
 <span data-ttu-id="07d5d-160">**Includi nome server**</span><span class="sxs-lookup"><span data-stu-id="07d5d-160">**Include server name**</span></span>  
 <span data-ttu-id="07d5d-161">Consente di includere il nome del server.</span><span class="sxs-lookup"><span data-stu-id="07d5d-161">Includes the server name.</span></span> <span data-ttu-id="07d5d-162">Per le connessioni locali, si tratta del nome dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="07d5d-162">For local connections, this is the instance name.</span></span> <span data-ttu-id="07d5d-163">Per le connessioni remote, si tratta del nome del computer remoto e del nome dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="07d5d-163">For remote connections, this is the remote computer name and instance name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07d5d-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07d5d-164">See Also</span></span>  
 <span data-ttu-id="07d5d-165">[Opzioni &#40;ambiente: pagina tipi di carattere e colori&#41;](../ssms/menu-help/options-environment-fonts-and-colors-page.md) </span><span class="sxs-lookup"><span data-stu-id="07d5d-165">[Options &#40;Environment: Fonts and Colors Page&#41;](../ssms/menu-help/options-environment-fonts-and-colors-page.md) </span></span>  
 [<span data-ttu-id="07d5d-166">Codifica con colori negli editor di query</span><span class="sxs-lookup"><span data-stu-id="07d5d-166">Color Coding in Query Editors</span></span>](../relational-databases/scripting/color-coding-in-query-editors.md)  
  
  
