---
title: Opzioni (ambiente-pagina generale) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Environment.SQLEnvironmentOptions
ms.assetid: c32ccdb8-2cf8-4c78-b474-a3abd3dbbd13
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7712c568b478bd2ba958237ba3204246657b3a72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638221"
---
# <a name="options-environment-general-page"></a><span data-ttu-id="821b0-102">Opzioni (pagina Ambiente/Generale)</span><span class="sxs-lookup"><span data-stu-id="821b0-102">Options (Environment-General Page)</span></span>
  <span data-ttu-id="821b0-103">Usare la finestra di dialogo **Opzioni** per configurare le azioni di avvio di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], le opzioni generali di gestione della finestra e altre impostazioni generali.</span><span class="sxs-lookup"><span data-stu-id="821b0-103">Use the **Options** dialog box to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] startup actions, general window management options, and other general settings.</span></span> <span data-ttu-id="821b0-104">Scegliere **Opzioni** dal menu **Strumenti**, espandere la cartella **Ambiente** e quindi fare clic su **Generale**.</span><span class="sxs-lookup"><span data-stu-id="821b0-104">On the **Tools** menu, click **Options**, expand the **Environment** folder, and then click **General**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="821b0-105">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="821b0-105">UI element list</span></span>  
 <span data-ttu-id="821b0-106">**All'avvio**</span><span class="sxs-lookup"><span data-stu-id="821b0-106">**At startup**</span></span>  
 <span data-ttu-id="821b0-107">Consente di selezionare l'azione che deve essere eseguita da [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] all'avvio.</span><span class="sxs-lookup"><span data-stu-id="821b0-107">Select the action for [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to perform when it is started.</span></span> <span data-ttu-id="821b0-108">Le opzioni disponibili sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="821b0-108">The options are:</span></span>  
  
-   <span data-ttu-id="821b0-109">**Apri Esplora oggetti** richiede di stabilire una connessione e quindi apre Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="821b0-109">**Open Object Explorer** prompts for a connection and then opens Object Explorer.</span></span>  
  
-   <span data-ttu-id="821b0-110">**Apri nuova finestra Query** richiede di stabilire una connessione e quindi apre Editor di query SQL.</span><span class="sxs-lookup"><span data-stu-id="821b0-110">**Open new query window** prompts for a connection and then opens SQL Query Editor.</span></span>  
  
-   <span data-ttu-id="821b0-111">**Apri Esplora oggetti e nuova finestra Query** richiede di stabilire una connessione e quindi la usa per aprire sia Esplora oggetti sia Editor di query SQL.</span><span class="sxs-lookup"><span data-stu-id="821b0-111">**Open Object Explorer and new query** prompts for a connection, then opens both Object Explorer and SQL Query Editor with that connection.</span></span>  
  
-   <span data-ttu-id="821b0-112">**Apri ambiente vuoto** apre [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] senza visualizzare una finestra dell'editor di query SQL né connettere Esplora oggetti a un server.</span><span class="sxs-lookup"><span data-stu-id="821b0-112">**Open empty environment** opens [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] without a SQL Query editor window and without connecting Object Explorer to a server.</span></span>  
  
 <span data-ttu-id="821b0-113">**Nascondi oggetti di sistema in Esplora oggetti**</span><span class="sxs-lookup"><span data-stu-id="821b0-113">**Hide system objects in Object Explorer**</span></span>  
 <span data-ttu-id="821b0-114">Selezionare questa casella di controllo per rimuovere database, tabelle, viste e stored procedure di sistema dalla visualizzazione dell'albero in Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="821b0-114">Select this check box to remove the system databases, system tables, system views, and system stored procedures from tree view in Object Explorer.</span></span> <span data-ttu-id="821b0-115">Le funzioni e i tipi di dati di sistema non vengono nascosti.</span><span class="sxs-lookup"><span data-stu-id="821b0-115">System functions and system data types are not hidden.</span></span> <span data-ttu-id="821b0-116">Questa opzione si applica solo alle istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e non ha alcun effetto sui server già connessi in Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="821b0-116">This option only applies to instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and does not affect servers already connected in Object Explorer.</span></span>  
  
## <a name="environment-layout"></a><span data-ttu-id="821b0-117">Layout ambiente</span><span class="sxs-lookup"><span data-stu-id="821b0-117">Environment Layout</span></span>  
 <span data-ttu-id="821b0-118">Per passare dalla modalità di ambiente a documenti a schede a quella a interfaccia per documenti multipli (MDI, Multiple-Document Interface) è necessario chiudere e riaprire [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="821b0-118">You must close and reopen [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to change between tabbed document and multiple-document interface (MDI) environment mode.</span></span>  
  
 <span data-ttu-id="821b0-119">**Documenti a schede**</span><span class="sxs-lookup"><span data-stu-id="821b0-119">**Tabbed documents**</span></span>  
 <span data-ttu-id="821b0-120">Selezionare questa opzione per visualizzare le finestre di documento a schede raggruppate all'interno degli editor.</span><span class="sxs-lookup"><span data-stu-id="821b0-120">Select this option to display document windows that are tabbed together within editors.</span></span> <span data-ttu-id="821b0-121">Le finestre di documento a schede sono utili per organizzare i documenti aperti e passare da un documento all'altro.</span><span class="sxs-lookup"><span data-stu-id="821b0-121">Tabbed document windows are useful for organizing and switching between multiple open documents.</span></span>  
  
 <span data-ttu-id="821b0-122">**Ambiente MDI**</span><span class="sxs-lookup"><span data-stu-id="821b0-122">**MDI environment**</span></span>  
 <span data-ttu-id="821b0-123">Selezionare questa opzione per aprire i documenti in un ambiente MDI.</span><span class="sxs-lookup"><span data-stu-id="821b0-123">Select this option to open documents in a MDI environment.</span></span> <span data-ttu-id="821b0-124">Le finestre di documento MDI sono utili per risparmiare lo spazio sullo schermo che in un ambiente a documenti a schede è occupato dalle schede.</span><span class="sxs-lookup"><span data-stu-id="821b0-124">MDI document windows are useful for gaining the screen space that is otherwise taken up by the tabs in the tabbed documents environment.</span></span> <span data-ttu-id="821b0-125">Quando è abilitata la modalità MDI, è possibile spostarsi tra i documenti premendo CTRL+TAB oppure usando le opzioni di affiancamento nel menu **Finestra** .</span><span class="sxs-lookup"><span data-stu-id="821b0-125">When working in MDI mode, you can switch between documents by pressing CTRL+TAB, or you can use the tile options located on the **Window** menu.</span></span>  
  
## <a name="docked-tool-window-behavior"></a><span data-ttu-id="821b0-126">Comportamento finestra degli strumenti ancorata</span><span class="sxs-lookup"><span data-stu-id="821b0-126">Docked Tool Window Behavior</span></span>  
 <span data-ttu-id="821b0-127">**Pulsante Chiudi valido solo per la scheda attiva**</span><span class="sxs-lookup"><span data-stu-id="821b0-127">**Close button affects active tab only**</span></span>  
 <span data-ttu-id="821b0-128">Quando questa casella di controllo è selezionata, viene chiusa solo la finestra degli strumenti attiva e non tutte le finestre degli strumenti presenti nel set ancorato.</span><span class="sxs-lookup"><span data-stu-id="821b0-128">Specifies that when this check box is selected, only the tool window that has focus currently is closed and not all of the tool windows in the docked set.</span></span> <span data-ttu-id="821b0-129">Questa casella di controllo è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="821b0-129">By default, this check box is selected.</span></span>  
  
 <span data-ttu-id="821b0-130">**Pulsante Nascondi automaticamente valido solo per la scheda attiva**</span><span class="sxs-lookup"><span data-stu-id="821b0-130">**Auto Hide button affects active tab only**</span></span>  
 <span data-ttu-id="821b0-131">Quando questa casella di controllo è selezionata, viene nascosta automaticamente solo la finestra degli strumenti attiva e non tutte le finestre degli strumenti presenti nel set ancorato.</span><span class="sxs-lookup"><span data-stu-id="821b0-131">Specifies that when this check box is selected, only the tool window that has focus currently is hidden automatically, not all of the tool windows in the docked set.</span></span> <span data-ttu-id="821b0-132">Per impostazione predefinita, tale casella di controllo è deselezionata.</span><span class="sxs-lookup"><span data-stu-id="821b0-132">By default, this check box is cleared.</span></span>  
  
## <a name="display"></a><span data-ttu-id="821b0-133">Schermo</span><span class="sxs-lookup"><span data-stu-id="821b0-133">Display</span></span>  
 <span data-ttu-id="821b0-134">**Visualizza n file nell'elenco degli ultimi file usati**</span><span class="sxs-lookup"><span data-stu-id="821b0-134">**Display n files in recently used list**</span></span>  
 <span data-ttu-id="821b0-135">Consente di scegliere il numero di progetti e file recenti da visualizzare nel menu **File** .</span><span class="sxs-lookup"><span data-stu-id="821b0-135">Customizes the number of recent projects and recent files that appear on the **File** menu.</span></span> <span data-ttu-id="821b0-136">Digitare un numero compreso tra 1 e 24.</span><span class="sxs-lookup"><span data-stu-id="821b0-136">Type a number between 1 and 24.</span></span> <span data-ttu-id="821b0-137">Il valore predefinito è 4.</span><span class="sxs-lookup"><span data-stu-id="821b0-137">The default is 4.</span></span> <span data-ttu-id="821b0-138">Questa opzione consente di recuperare con facilità i file e i progetti script utilizzati più di recente.</span><span class="sxs-lookup"><span data-stu-id="821b0-138">This is an easy way to retrieve recently used script projects and files and script projects.</span></span>  
  
  
