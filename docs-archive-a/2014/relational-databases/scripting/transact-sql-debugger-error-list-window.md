---
title: Finestra Elenco errori
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- error list window
- SQL Server Management Studio [SQL Server], error list window
ms.assetid: fae6327d-e268-44ae-a474-4a8f8f843129
author: rothja
ms.author: jroth
ms.openlocfilehash: 00455c339344b7b38a48500c49d139aa52df6116
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637216"
---
# <a name="error-list-window-management-studio"></a><span data-ttu-id="bc978-102">Finestra Elenco errori (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="bc978-102">Error List Window (Management Studio)</span></span>
  <span data-ttu-id="bc978-103">La finestra [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]Elenco errori**di** mostra gli errori semantici e di sintassi generati dal codice IntelliSense nell'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc978-103">The [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] **Error List** displays the syntax and semantic errors that are generated from the IntelliSense code in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span>  
  
## <a name="features-of-the-error-list"></a><span data-ttu-id="bc978-104">Caratteristiche della finestra Elenco errori</span><span class="sxs-lookup"><span data-stu-id="bc978-104">Features of the Error List</span></span>  
 <span data-ttu-id="bc978-105">In **Elenco errori** sono disponibili le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="bc978-105">The **Error List** provides the following functionality:</span></span>  
  
-   <span data-ttu-id="bc978-106">Durante la modifica degli script, in **Elenco errori** vengono visualizzati gli errori e gli avvisi prodotti da IntelliSense nell'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bc978-106">As you edit scripts, the **Error List** displays the errors and warnings produced by IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span>  
  
-   <span data-ttu-id="bc978-107">È possibile fare doppio clic su una voce del messaggio di errore per attivare la scheda del file script che ha generato l'errore e spostarsi nella posizione dello stesso.</span><span class="sxs-lookup"><span data-stu-id="bc978-107">You can double-click any error message entry to focus on the tab for the script file that generated the error, and move to the error location.</span></span>  
  
-   <span data-ttu-id="bc978-108">È possibile filtrare le voci e le colonne di informazioni che si desidera visualizzare per ogni voce.</span><span class="sxs-lookup"><span data-stu-id="bc978-108">You can filter which entries you want to display, and which columns of information you want appear for each entry.</span></span>  
  
-   <span data-ttu-id="bc978-109">Dopo avere corretto un errore, la relativa voce viene rimossa da **Elenco errori**.</span><span class="sxs-lookup"><span data-stu-id="bc978-109">After you fix an error, the error entry is removed from the **Error List**.</span></span>  
  
-   <span data-ttu-id="bc978-110">Quando si chiude la scheda di un file script [!INCLUDE[tsql](../../includes/tsql-md.md)] , gli errori relativi al file vengono rimossi da **Elenco errori**.</span><span class="sxs-lookup"><span data-stu-id="bc978-110">When you close the tab for a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file, the errors for that file are removed from the **Error List**.</span></span>  
  
## <a name="working-with-the-error-list"></a><span data-ttu-id="bc978-111">Utilizzo dell'elenco degli errori</span><span class="sxs-lookup"><span data-stu-id="bc978-111">Working with the Error List</span></span>  
 <span data-ttu-id="bc978-112">Per visualizzare **Elenco errori**, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bc978-112">To display the **Error List**, do one of the following:</span></span>  
  
-   <span data-ttu-id="bc978-113">Scegliere **Elenco errori** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="bc978-113">On the **View** menu, click **Error List**.</span></span>  
  
-   <span data-ttu-id="bc978-114">Utilizzare i tasti di scelta rapida CTRL+\\, CTRL+E.</span><span class="sxs-lookup"><span data-stu-id="bc978-114">Enter the keyboard shortcut CTRL+\\, CTRL+E.</span></span>  
  
 <span data-ttu-id="bc978-115">Dopo avere aperto **Elenco errori**, è possibile personalizzare la visualizzazione eseguendo le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bc978-115">After you open the **Error List**, you can customize your view by performing the following actions:</span></span>  
  
-   <span data-ttu-id="bc978-116">Per ordinare l'elenco, fare clic sull'intestazione di una colonna.</span><span class="sxs-lookup"><span data-stu-id="bc978-116">To sort the list, click any column header.</span></span> <span data-ttu-id="bc978-117">Per ordinare nuovamente l'elenco in base a un'altra colonna, fare clic sull'intestazione di un'altra colonna tenendo premuto il tasto MAIUSC.</span><span class="sxs-lookup"><span data-stu-id="bc978-117">To sort again by an additional column, press and hold the SHIFT key, and then click another column header.</span></span>  
  
-   <span data-ttu-id="bc978-118">Per selezionare le colonne da visualizzare e quelle da nascondere, scegliere **Mostra colonne** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="bc978-118">To select which columns are displayed and which are hidden, select **Show Columns** from the shortcut menu.</span></span>  
  
-   <span data-ttu-id="bc978-119">Per modificare l'ordine di visualizzazione delle colonne, trascinare l'intestazione di una colonna verso sinistra o verso destra.</span><span class="sxs-lookup"><span data-stu-id="bc978-119">To change the order in which columns are displayed, drag any column header to the left or right.</span></span>  
  
 <span data-ttu-id="bc978-120">**Elenco errori** non offre collegamenti a informazioni aggiuntive su errori specifici.</span><span class="sxs-lookup"><span data-stu-id="bc978-120">The **Error List** does not link to additional information about specific errors.</span></span>  
  
## <a name="transact-sql-errors-in-management-studio"></a><span data-ttu-id="bc978-121">Errori Transact-SQL in Management Studio</span><span class="sxs-lookup"><span data-stu-id="bc978-121">Transact-SQL Errors in Management Studio</span></span>  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="bc978-122">mostra gli errori relativi agli script [!INCLUDE[tsql](../../includes/tsql-md.md)] nelle seguenti posizioni:</span><span class="sxs-lookup"><span data-stu-id="bc978-122">displays errors for [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts in the following locations:</span></span>  
  
-   <span data-ttu-id="bc978-123">**Elenco errori** contiene tutti gli errori semantici e di sintassi individuati da IntelliSense nell'editor del [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bc978-123">The **Error List** contains all syntax and semantic errors found by IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Editor.</span></span> <span data-ttu-id="bc978-124">L'elenco degli errori viene aggiornato dinamicamente durante la modifica di script [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc978-124">This list of errors is dynamically updated as you edit [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts.</span></span> <span data-ttu-id="bc978-125">e comprende tutti gli errori individuati dall'editor in ogni script [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bc978-125">The list includes all errors that the editor has found in each [!INCLUDE[tsql](../../includes/tsql-md.md)] script.</span></span> <span data-ttu-id="bc978-126">L'editor non arresta l'analisi di un file dopo avere rilevato errori in uno script.</span><span class="sxs-lookup"><span data-stu-id="bc978-126">The editor does not stop parsing a file after encountering errors in a script.</span></span> <span data-ttu-id="bc978-127">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]IntelliSense non supporta tutti gli elementi della sintassi del [!INCLUDE[ssDE](../../includes/ssde-md.md)] nell'editor [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bc978-127">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Editor does not support all [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax elements.</span></span> <span data-ttu-id="bc978-128">**Elenco errori** contiene solo gli errori della sintassi [!INCLUDE[tsql](../../includes/tsql-md.md)] supportata da IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="bc978-128">The **Error List** contains only errors from the [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax that is supported by IntelliSense.</span></span>  
  
-   <span data-ttu-id="bc978-129">La scheda **Messaggi** nella parte inferiore della finestra dell'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)] visualizza tutti gli errori e messaggi restituiti da [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] durante l'esecuzione di uno script [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bc978-129">The **Messages** tab at the bottom of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window displays all errors and messages that are returned by the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] when a [!INCLUDE[tsql](../../includes/tsql-md.md)] script is executed.</span></span> <span data-ttu-id="bc978-130">Questo elenco non subisce modifiche se non viene eseguito nuovamente lo script.</span><span class="sxs-lookup"><span data-stu-id="bc978-130">This list does not change until you execute the script again.</span></span> <span data-ttu-id="bc978-131">Il [!INCLUDE[ssDE](../../includes/ssde-md.md)] arresta l'analisi di un batch dopo l'individuazione di uno o due errori di compilazione; pertanto la scheda **Messaggi** potrebbe non elencare tutti gli errori presenti in uno script.</span><span class="sxs-lookup"><span data-stu-id="bc978-131">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] stops parsing a batch after it finds one or two compile errors; therefore, the **Messages** tab might not list all errors in a script.</span></span>  
  
 <span data-ttu-id="bc978-132">Talvolta gli errori sono elencati in entrambe le posizioni.</span><span class="sxs-lookup"><span data-stu-id="bc978-132">Sometimes errors are listed in both locations.</span></span> <span data-ttu-id="bc978-133">Ad esempio, in un file script potrebbe essere presente un errore di sintassi elencato in **Elenco errori**.</span><span class="sxs-lookup"><span data-stu-id="bc978-133">For example, a script file might have a syntax error that is listed in the **Error List**.</span></span> <span data-ttu-id="bc978-134">Se lo script viene eseguito prima di correggere l'errore, il parser [!INCLUDE[ssDE](../../includes/ssde-md.md)] può rilevare la stessa condizione e restituire un'altra copia del messaggio di errore nella scheda **Messaggi** .</span><span class="sxs-lookup"><span data-stu-id="bc978-134">If you execute the script before you correct the error, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] parser can detect the same condition and return another copy of the error message in the **Messages** tab.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bc978-135">**Elenco errori** visualizza solo gli errori dell'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)] , non gli errori degli editor MDX, DMX o XML/A.</span><span class="sxs-lookup"><span data-stu-id="bc978-135">The **Error List** only displays errors from the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor; it does not display errors from the MDX, DMX, or XML/A Editors.</span></span> <span data-ttu-id="bc978-136">Questi errori vengono visualizzati nella scheda **Messaggi** dei rispettivi editor.</span><span class="sxs-lookup"><span data-stu-id="bc978-136">All MDX, DMX, and XML/A errors are displayed in the **Messages** tab in those editors.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="bc978-137">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="bc978-137">UI element list</span></span>  
 <span data-ttu-id="bc978-138">All'apertura di **Elenco errori** le informazioni sono visualizzate nelle colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="bc978-138">When the **Error List** is open, the information is displayed in the following columns:</span></span>  
  
 <span data-ttu-id="bc978-139">**Ordine predefinito**</span><span class="sxs-lookup"><span data-stu-id="bc978-139">**Default Order**</span></span>  
 <span data-ttu-id="bc978-140">Visualizza un valore intero che indica l'ordine in cui le voci sono state generate.</span><span class="sxs-lookup"><span data-stu-id="bc978-140">Displays an integer that indicates the order in which an entry was generated.</span></span>  
  
 <span data-ttu-id="bc978-141">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="bc978-141">**Description**</span></span>  
 <span data-ttu-id="bc978-142">Visualizza il testo della voce di errore.</span><span class="sxs-lookup"><span data-stu-id="bc978-142">Displays the text of the error entry.</span></span> <span data-ttu-id="bc978-143">Le descrizioni più lunghe vengono suddivise in più righe.</span><span class="sxs-lookup"><span data-stu-id="bc978-143">Lengthy descriptions wrap onto additional lines.</span></span>  
  
 <span data-ttu-id="bc978-144">**File**</span><span class="sxs-lookup"><span data-stu-id="bc978-144">**File**</span></span>  
 <span data-ttu-id="bc978-145">Visualizza il nome del file script che ha generato l'errore.</span><span class="sxs-lookup"><span data-stu-id="bc978-145">Displays the name of the script file that generated the error.</span></span>  
  
 <span data-ttu-id="bc978-146">**Linea**</span><span class="sxs-lookup"><span data-stu-id="bc978-146">**Line**</span></span>  
 <span data-ttu-id="bc978-147">Visualizza un numero intero che indica la riga del codice che contiene l'errore.</span><span class="sxs-lookup"><span data-stu-id="bc978-147">Displays an integer that indicates which line of the code includes the error.</span></span>  
  
 <span data-ttu-id="bc978-148">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="bc978-148">**Column**</span></span>  
 <span data-ttu-id="bc978-149">Visualizza un numero intero che indica la posizione dell'errore nella riga del codice.</span><span class="sxs-lookup"><span data-stu-id="bc978-149">Displays an integer that indicates the position of the error in the line of code.</span></span>  
  
 <span data-ttu-id="bc978-150">**Progetto**</span><span class="sxs-lookup"><span data-stu-id="bc978-150">**Project**</span></span>  
 <span data-ttu-id="bc978-151">Visualizza il nome del progetto che comprende il file script.</span><span class="sxs-lookup"><span data-stu-id="bc978-151">Displays the name of the project that includes the script file.</span></span>  
