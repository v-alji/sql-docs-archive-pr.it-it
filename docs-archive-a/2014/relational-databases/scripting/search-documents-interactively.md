---
title: Ricerca interattiva all'interno di documenti
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- interactive searches [SQL Server Management Studio]
- searches [SQL Server Management Studio], interactive
- Query Editor [SQL Server Management Studio], interactive search
ms.assetid: dae65ac5-67af-45c6-a6e0-952fea26d680
author: rothja
ms.author: jroth
ms.openlocfilehash: 5603db77ea4f58d4bb036635a23ec3cfa400a818
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637220"
---
# <a name="search-documents-interactively"></a><span data-ttu-id="be6b9-102">Ricerca interattiva all'interno di documenti</span><span class="sxs-lookup"><span data-stu-id="be6b9-102">Search Documents Interactively</span></span>
  <span data-ttu-id="be6b9-103">La finestra di dialogo **Trova e sostituisci** consente di eseguire una ricerca in uno o più file o finestre aperti e passare da un risultato della ricerca all'altro.</span><span class="sxs-lookup"><span data-stu-id="be6b9-103">Using the **Find and Replace** dialog box, you can search one or more open files or windows and move through the search matches one by one.</span></span> <span data-ttu-id="be6b9-104">Questa tecnica consente di esaminare ogni singola corrispondenza della ricerca contestualmente, ossia nel testo che la precede e la segue.</span><span class="sxs-lookup"><span data-stu-id="be6b9-104">This technique allows you to review each individual search match in the context of the text around the match.</span></span> <span data-ttu-id="be6b9-105">È inoltre possibile eseguire operazioni di ricerca bulk ed esaminare i risultati corrispondenti in formato report usando la finestra di dialogo **Trova e sostituisci** .</span><span class="sxs-lookup"><span data-stu-id="be6b9-105">You also have the option of performing bulk find operations and reviewing search matches in report format using the **Find and Replace** dialog box.</span></span>  
  
### <a name="to-search-all-open-documents"></a><span data-ttu-id="be6b9-106">Per eseguire la ricerca in tutti i documenti aperti</span><span class="sxs-lookup"><span data-stu-id="be6b9-106">To search all open documents</span></span>  
  
1.  <span data-ttu-id="be6b9-107">Aprire gli elementi nei quali si desidera eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="be6b9-107">Open the items you wish to search.</span></span>  
  
2.  <span data-ttu-id="be6b9-108">Scegliere **Trova e sostituisci** dal menu **Modifica** e quindi fare clic su **Ricerca veloce**.</span><span class="sxs-lookup"><span data-stu-id="be6b9-108">On the **Edit** menu, point to **Find and Replace,** and then click **QuickFind**.</span></span>  
  
3.  <span data-ttu-id="be6b9-109">Nella casella di testo **Trova e sostituisci** immettere il testo che si desidera cercare.</span><span class="sxs-lookup"><span data-stu-id="be6b9-109">In the **Find and Replace** text box, enter the text to search for.</span></span>  
  
4.  <span data-ttu-id="be6b9-110">Nell'elenco **Cerca in** selezionare **Tutti i documenti aperti**.</span><span class="sxs-lookup"><span data-stu-id="be6b9-110">In the **Look in** list, select **All Open Documents**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="be6b9-111">Quando si seleziona **Tutti i documenti aperti** , è possibile che la ricerca non venga eseguita in alcuni file aperti.</span><span class="sxs-lookup"><span data-stu-id="be6b9-111">Certain open files might not be searched when **All Open Documents** is selected.</span></span> <span data-ttu-id="be6b9-112">Nella ricerca vengono inclusi solo i file attualmente aperti in una visualizzazione di testo, ad esempio in visualizzazione Codice.</span><span class="sxs-lookup"><span data-stu-id="be6b9-112">Only files currently open in a textual view, such as Code view, are included in searches.</span></span> <span data-ttu-id="be6b9-113">I file in visualizzazione di progettazione non vengono inclusi nella ricerca.</span><span class="sxs-lookup"><span data-stu-id="be6b9-113">Files in Designer view are not included in searches.</span></span>  
  
5.  <span data-ttu-id="be6b9-114">Per migliorare la precisione della ricerca, selezionare opzioni di ricerca aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="be6b9-114">Select additional search options to increase the accuracy of the search.</span></span>  
  
6.  <span data-ttu-id="be6b9-115">Fare clic su **Trova successivo** per avviare la ricerca e continuare a fare clic su **Trova successivo** fino al termine della ricerca nell'ultimo file.</span><span class="sxs-lookup"><span data-stu-id="be6b9-115">Click **Find Next** to start the search, and continue clicking **Find Next** until the last file has been searched.</span></span>  
  
 <span data-ttu-id="be6b9-116">Quando la ricerca raggiunge l'inizio o la fine del documento, nella barra di stato viene visualizzato un messaggio.</span><span class="sxs-lookup"><span data-stu-id="be6b9-116">When the search passes the beginning or end of the document, a message is displayed in the status bar.</span></span> <span data-ttu-id="be6b9-117">Quando viene raggiunto il punto iniziale della ricerca, viene visualizzata una finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="be6b9-117">A message box appears when the search reaches the starting point of the search.</span></span>  
  
#### <a name="to-replace-in-all-active-files-interactively"></a><span data-ttu-id="be6b9-118">Per eseguire una sostituzione in tutti i file attivi in modo interattivo</span><span class="sxs-lookup"><span data-stu-id="be6b9-118">To replace in all active files interactively</span></span>  
  
1.  <span data-ttu-id="be6b9-119">Scegliere **Trova e sostituisci** dal menu **Modifica**e quindi fare clic su **Sostituzione veloce**.</span><span class="sxs-lookup"><span data-stu-id="be6b9-119">On the **Edit** menu, point to **Find and Replace**, and then click **QuickReplace**.</span></span>  
  
2.  <span data-ttu-id="be6b9-120">Nella casella di testo **Trova** immettere il testo da cercare.</span><span class="sxs-lookup"><span data-stu-id="be6b9-120">In the **Find what** box, enter the text to search for.</span></span>  
  
3.  <span data-ttu-id="be6b9-121">Nella casella di testo **Sostituisci con** immettere il testo con cui sostituire il testo trovato.</span><span class="sxs-lookup"><span data-stu-id="be6b9-121">In the **Replace with** box, enter the text to replace the search text.</span></span>  
  
4.  <span data-ttu-id="be6b9-122">Nell'elenco **Cerca in** selezionare **Tutti i documenti aperti**.</span><span class="sxs-lookup"><span data-stu-id="be6b9-122">In the **Look in** list, select **All Open Documents**.</span></span>  
  
5.  <span data-ttu-id="be6b9-123">Fare clic su **Sostituisci**e continuare a fare clic su **Sostituisci** fino all'ultima sostituzione nell'ultimo file.</span><span class="sxs-lookup"><span data-stu-id="be6b9-123">Click **Replace**, and continue clicking **Replace** until the last match in the last file has been replaced.</span></span> <span data-ttu-id="be6b9-124">Fare clic su **Trova successivo** per ignorare una corrispondenza che non si desidera sostituire.</span><span class="sxs-lookup"><span data-stu-id="be6b9-124">Click **Find Next** to skip a match you do not want to replace.</span></span>  
  
     <span data-ttu-id="be6b9-125">-oppure-</span><span class="sxs-lookup"><span data-stu-id="be6b9-125">-or-</span></span>  
  
     <span data-ttu-id="be6b9-126">Scegliere **Sostituisci tutto** per sostituire tutte le corrispondenze.</span><span class="sxs-lookup"><span data-stu-id="be6b9-126">Choose **Replace All** to replace all matches.</span></span> <span data-ttu-id="be6b9-127">Verrà visualizzata una finestra di messaggio con il numero totale di sostituzioni.</span><span class="sxs-lookup"><span data-stu-id="be6b9-127">A message box appears, listing the total number of replacements.</span></span>  
  
 <span data-ttu-id="be6b9-128">Il comando **Sostituisci tutto** esegue la sostituzione di tutte le corrispondenze, comprese quelle che sono state ignorate usando il pulsante **Trova successivo** .</span><span class="sxs-lookup"><span data-stu-id="be6b9-128">The **Replace All** command replaces all search matches, including those you have skipped with the **Find Next** button.</span></span> <span data-ttu-id="be6b9-129">Per annullare il comando **Sostituisci tutto**, scegliere **Annulla** dal menu **Modifica** prima di chiudere un file.</span><span class="sxs-lookup"><span data-stu-id="be6b9-129">To cancel **Replace All**, click **Undo** from the **Edit** menu before closing any of the files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be6b9-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be6b9-130">See Also</span></span>  
 <span data-ttu-id="be6b9-131">[Ricerca incrementale in un documento attivo](search-an-active-document-incrementally.md) </span><span class="sxs-lookup"><span data-stu-id="be6b9-131">[Search an Active Document Incrementally](search-an-active-document-incrementally.md) </span></span>  
 <span data-ttu-id="be6b9-132">[Ricerca e sostituzione](search-and-replace.md) </span><span class="sxs-lookup"><span data-stu-id="be6b9-132">[Search and Replace](search-and-replace.md) </span></span>  
 <span data-ttu-id="be6b9-133">[Ricerca nei documenti utilizzando gli elenchi dei risultati](search-documents-using-results-lists.md) </span><span class="sxs-lookup"><span data-stu-id="be6b9-133">[Search Documents Using Results Lists](search-documents-using-results-lists.md) </span></span>  
 <span data-ttu-id="be6b9-134">[Testo di ricerca con caratteri jolly](search-text-with-wildcards.md) </span><span class="sxs-lookup"><span data-stu-id="be6b9-134">[Search Text with Wildcards](search-text-with-wildcards.md) </span></span>  
 [<span data-ttu-id="be6b9-135">Eseguire ricerche di testo con espressioni regolari</span><span class="sxs-lookup"><span data-stu-id="be6b9-135">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
  
  
