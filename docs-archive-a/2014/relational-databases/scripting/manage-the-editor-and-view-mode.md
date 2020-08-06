---
title: Gestione dell'editor e della modalità di visualizzazione
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Query Editor [SQL Server Management Studio], managing window behavior
- workbench view modes [SQL Server Management Studio]
- full screen mode [SQL Server Management Studio]
- fonts [SQL Server Management Studio]
- word wraps [SQL Server Management Studio]
- virtual space mode [SQL Server Management Studio]
- splitting document views
- displaying line numbers
- view modes [SQL Server Management Studio]
ms.assetid: 25c58a14-9f94-4296-9770-7d84c6bc3969
author: rothja
ms.author: jroth
ms.openlocfilehash: 36788b1fe831a6c15c4aa0668d1759c088fcaa73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636676"
---
# <a name="manage-the-editor-and-view-mode"></a><span data-ttu-id="c484a-102">Gestione dell'editor e della modalità di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="c484a-102">Manage the Editor and View Mode</span></span>
  <span data-ttu-id="c484a-103">Nell'editor sono disponibili vari modi per gestire la visualizzazione del codice.</span><span class="sxs-lookup"><span data-stu-id="c484a-103">The Editor gives you a number of ways to control the view of your code.</span></span>  
  
## <a name="changing-the-view-mode"></a><span data-ttu-id="c484a-104">Modifica della modalità di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="c484a-104">Changing the View Mode</span></span>  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="c484a-105">offre una modalità di visualizzazione denominata **Documenti a schede**che consente di aprire contemporaneamente più editor e documenti e di accedervi tramite schede visualizzate nella parte superiore dell'editor.</span><span class="sxs-lookup"><span data-stu-id="c484a-105">features a view mode called **Tabbed Documents**, which allows you to open multiple editors and documents simultaneously and access them through tabs at the top of the Editor.</span></span> <span data-ttu-id="c484a-106">In alternativa, è possibile aprire l'ambiente [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] in modalità interfaccia a più documenti (MDI, Multiple Document Interface), nella quale le finestre sono visualizzate senza schede e possono essere ancorate, affiancate, ridotte a icona e così via.</span><span class="sxs-lookup"><span data-stu-id="c484a-106">You can alternatively open the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] environment in Multiple Document Interface (MDI) mode, which joins windows without the tabs, and allows each window to be tiled, minimized, and so on.</span></span>  
  
#### <a name="to-switch-between-view-modes"></a><span data-ttu-id="c484a-107">Per passare da una modalità di visualizzazione all'altra</span><span class="sxs-lookup"><span data-stu-id="c484a-107">To switch between view modes</span></span>  
  
1.  <span data-ttu-id="c484a-108">Scegliere **Opzioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="c484a-108">Click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="c484a-109">Fare clic su **Ambiente**.</span><span class="sxs-lookup"><span data-stu-id="c484a-109">Click **Environment**.</span></span> <span data-ttu-id="c484a-110">Fare clic su **Generale**.</span><span class="sxs-lookup"><span data-stu-id="c484a-110">Click **General**.</span></span>  
  
3.  <span data-ttu-id="c484a-111">Selezionare **Documenti a schede** o **Ambiente MDI**.</span><span class="sxs-lookup"><span data-stu-id="c484a-111">Click **Tabbed documents** or **MDI environment**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c484a-112">Le modifiche verranno applicate solo dopo il riavvio di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c484a-112">The changes will not take effect until [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is restarted.</span></span>  
  
## <a name="splitting-the-view"></a><span data-ttu-id="c484a-113">Divisione di una finestra di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="c484a-113">Splitting the View</span></span>  
 <span data-ttu-id="c484a-114">È possibile dividere una finestra dell'editor in due parti distinte per semplificare le operazioni di modifica.</span><span class="sxs-lookup"><span data-stu-id="c484a-114">An Editor window can be split into two separate parts for easier editing.</span></span>  
  
#### <a name="to-split-a-window"></a><span data-ttu-id="c484a-115">Per dividere una finestra</span><span class="sxs-lookup"><span data-stu-id="c484a-115">To split a window</span></span>  
  
1.  <span data-ttu-id="c484a-116">Fare clic sulla barra di divisione visualizzata sopra la barra di scorrimento.</span><span class="sxs-lookup"><span data-stu-id="c484a-116">Click the splitter bar (located above the scroll bar).</span></span>  
  
2.  <span data-ttu-id="c484a-117">Trascinare la barra di divisione verso il basso.</span><span class="sxs-lookup"><span data-stu-id="c484a-117">Drag the splitter bar downward.</span></span>  
  
3.  <span data-ttu-id="c484a-118">Per visualizzare di nuovo un solo riquadro, fare doppio clic sulla barra di divisione che separa i due riquadri.</span><span class="sxs-lookup"><span data-stu-id="c484a-118">To go back to a single pane, double-click the splitter bar dividing the two panes.</span></span>  
  
 <span data-ttu-id="c484a-119">Nel nuovo riquadro sarà visualizzato lo stesso documento e qualsiasi modifica apportata in un riquadro si rifletterà nell'altro, purché si sia posizionati nello stesso punto del documento.</span><span class="sxs-lookup"><span data-stu-id="c484a-119">The new pane contains the same document, and any changes made to one pane are reflected in the other pane as long as that pane displays the same place in the document.</span></span>  
  
## <a name="word-wrap"></a><span data-ttu-id="c484a-120">A capo automatico</span><span class="sxs-lookup"><span data-stu-id="c484a-120">Word Wrap</span></span>  
 <span data-ttu-id="c484a-121">Quando si attiva l'opzione A capo automatico, la barra di scorrimento orizzontale viene rimossa e le righe di codice con una larghezza superiore alle dimensioni della finestra dell'editor vengono automaticamente mandate a capo sulla riga successiva visualizzata anziché scorrere nella parte non visibile della finestra.</span><span class="sxs-lookup"><span data-stu-id="c484a-121">When you activate Word Wrap, the horizontal scrollbar is removed and lines of code that exceed the width of the Editor's window size automatically wraps to the next displayed line rather than scrolling off the side of the window.</span></span>  
  
#### <a name="to-activate-word-wrap"></a><span data-ttu-id="c484a-122">Per attivare il ritorno a capo automatico</span><span class="sxs-lookup"><span data-stu-id="c484a-122">To activate word wrap</span></span>  
  
1.  <span data-ttu-id="c484a-123">Scegliere **Opzioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="c484a-123">Click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="c484a-124">Fare clic su **Editor di testo**.</span><span class="sxs-lookup"><span data-stu-id="c484a-124">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="c484a-125">Aprire la cartella del linguaggio desiderato, oppure la cartella **Tutti i linguaggi** per eseguire l'impostazione per tutti i linguaggi.</span><span class="sxs-lookup"><span data-stu-id="c484a-125">Open the appropriate language folder (or **All Languages** to affect all languages).</span></span>  
  
4.  <span data-ttu-id="c484a-126">Selezionare **A capo automatico**.</span><span class="sxs-lookup"><span data-stu-id="c484a-126">Select **Word wrap**.</span></span>  
  
## <a name="enabling-virtual-space-mode"></a><span data-ttu-id="c484a-127">Attivazione della modalità spazio virtuale</span><span class="sxs-lookup"><span data-stu-id="c484a-127">Enabling Virtual Space Mode</span></span>  
 <span data-ttu-id="c484a-128">Nella modalità **Spazio virtuale** le righe di codice possono continuare oltre l'area visibile dello schermo come se lo spazio alla fine di ogni riga fosse riempito da un numero infinito di spazi.</span><span class="sxs-lookup"><span data-stu-id="c484a-128">In **Virtual Space** mode, the Editor acts as if the space past the end of each line is filled with an infinite number of spaces, allowing code lines to continue off the side of the visible screen area.</span></span>  
  
#### <a name="to-enable-virtual-space-mode"></a><span data-ttu-id="c484a-129">Per attivare la modalità spazio virtuale</span><span class="sxs-lookup"><span data-stu-id="c484a-129">To enable Virtual Space mode</span></span>  
  
1.  <span data-ttu-id="c484a-130">Scegliere **Opzioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="c484a-130">Click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="c484a-131">Fare clic su **Editor di testo**.</span><span class="sxs-lookup"><span data-stu-id="c484a-131">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="c484a-132">Aprire la cartella del linguaggio desiderato, oppure la cartella **Tutti i linguaggi** per eseguire l'impostazione per tutti i linguaggi.</span><span class="sxs-lookup"><span data-stu-id="c484a-132">Open the appropriate language folder (or **All Languages** to affect all languages).</span></span>  
  
4.  <span data-ttu-id="c484a-133">Selezionare **Attiva spazio virtuale**.</span><span class="sxs-lookup"><span data-stu-id="c484a-133">Select **Enable virtual space**.</span></span>  
  
 <span data-ttu-id="c484a-134">Quando la modalità spazio virtuale non è attivata, il cursore si sposta dalla fine di una riga al primo carattere della riga successiva e viceversa.</span><span class="sxs-lookup"><span data-stu-id="c484a-134">When Virtual Space mode is not enabled, the cursor wraps from the end of one line to the first character of the next line and vice-versa.</span></span>  
  
## <a name="displaying-line-numbers"></a><span data-ttu-id="c484a-135">visualizzazione di numeri di riga</span><span class="sxs-lookup"><span data-stu-id="c484a-135">Displaying Line Numbers</span></span>  
 <span data-ttu-id="c484a-136">È possibile attivare la numerazione delle righe del codice.</span><span class="sxs-lookup"><span data-stu-id="c484a-136">You can turn on line numbering in your code.</span></span> <span data-ttu-id="c484a-137">I numeri di riga sono utili per spostarsi all'interno del codice.</span><span class="sxs-lookup"><span data-stu-id="c484a-137">Line numbers are useful for navigating code.</span></span> <span data-ttu-id="c484a-138">Per altre informazioni, vedere [Spostarsi nel codice e nel testo](navigate-code-and-text.md).</span><span class="sxs-lookup"><span data-stu-id="c484a-138">For more information, see [Navigate Code and Text](navigate-code-and-text.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c484a-139">L'attivazione dei numeri di riga non attiva la stampa dei numeri di riga nel documento.</span><span class="sxs-lookup"><span data-stu-id="c484a-139">Turning on line numbering does not mean that the document will print with line numbers.</span></span> <span data-ttu-id="c484a-140">Per stampare i numeri di riga è necessario selezionare la casella di controllo **Numeri di riga** nella finestra di dialogo **Imposta pagina** a cui si accede dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="c484a-140">For line numbers to print, you must select the **Line numbers** check box in the **Page Setup** command on the **File** menu.</span></span>  
  
#### <a name="to-display-line-numbers-in-code"></a><span data-ttu-id="c484a-141">Per visualizzare i numeri di riga nel codice</span><span class="sxs-lookup"><span data-stu-id="c484a-141">To display line numbers in code</span></span>  
  
1.  <span data-ttu-id="c484a-142">Scegliere **Opzioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="c484a-142">Click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="c484a-143">Fare clic su **Editor di testo**.</span><span class="sxs-lookup"><span data-stu-id="c484a-143">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="c484a-144">Fare clic su **Tutti i linguaggi**.</span><span class="sxs-lookup"><span data-stu-id="c484a-144">Click **All Languages**.</span></span>  
  
4.  <span data-ttu-id="c484a-145">Fare clic su **Generale**.</span><span class="sxs-lookup"><span data-stu-id="c484a-145">Click **General**.</span></span>  
  
5.  <span data-ttu-id="c484a-146">Selezionare **Numeri di riga**.</span><span class="sxs-lookup"><span data-stu-id="c484a-146">Select **Line numbers**.</span></span>  
  
 <span data-ttu-id="c484a-147">Per impostare la numerazione delle righe solo per alcuni linguaggi di programmazione, selezionare **Numeri di riga** nella cartella appropriata.</span><span class="sxs-lookup"><span data-stu-id="c484a-147">To specify line numbering for only some programming languages, select **Line Numbers** in the appropriate folder.</span></span>  
  
## <a name="enabling-full-screen-mode"></a><span data-ttu-id="c484a-148">Attivazione della modalità Schermo intero</span><span class="sxs-lookup"><span data-stu-id="c484a-148">Enabling Full Screen Mode</span></span>  
 <span data-ttu-id="c484a-149">È possibile attivare la modalità Schermo intero per nascondere tutte le finestre degli strumenti e visualizzare solo le finestre dei documenti.</span><span class="sxs-lookup"><span data-stu-id="c484a-149">You can choose to hide all tool windows and view only document windows by enabling Full Screen mode.</span></span>  
  
#### <a name="to-enable-full-screen-mode"></a><span data-ttu-id="c484a-150">Per attivare la modalità Schermo intero</span><span class="sxs-lookup"><span data-stu-id="c484a-150">To enable Full Screen mode</span></span>  
  
1.  <span data-ttu-id="c484a-151">Per attivare (e successivamente disattivare) la modalità Schermo intero, premere ALT+MAIUSC+INVIO.</span><span class="sxs-lookup"><span data-stu-id="c484a-151">Press ALT+SHIFT+ENTER to toggle Full Screen mode.</span></span>  
  
## <a name="using-auto-hide-all"></a><span data-ttu-id="c484a-152">Utilizzo dell'opzione Nascondi tutto automaticamente</span><span class="sxs-lookup"><span data-stu-id="c484a-152">Using Auto Hide All</span></span>  
  
#### <a name="to-hide-all-the-tool-windows-at-once"></a><span data-ttu-id="c484a-153">Per nascondere tutte le finestre degli strumenti contemporaneamente</span><span class="sxs-lookup"><span data-stu-id="c484a-153">To hide all the tool windows at once</span></span>  
  
1.  <span data-ttu-id="c484a-154">Scegliere **Nascondi tutto automaticamente** dal menu **Finestra** .</span><span class="sxs-lookup"><span data-stu-id="c484a-154">Select **Auto Hide All** on the **Window** menu.</span></span>  
  
  
