---
title: Ricerca nei documenti utilizzando gli elenchi dei risultati
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- searches [SQL Server Management Studio], result lists
- result list searches [SQL Server Management Studio]
- searches [SQL Server Management Studio], multiple files
- Query Editor [SQL Server Management Studio], search multiple files
ms.assetid: 275e1b6c-fbd0-4408-af77-35903f90657c
author: rothja
ms.author: jroth
ms.openlocfilehash: 58ff3754bc1667de75426e52b3ddd855e7d1a348
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637215"
---
# <a name="search-documents-using-results-lists"></a><span data-ttu-id="7d1bd-102">Ricerca nei documenti utilizzando gli elenchi dei risultati</span><span class="sxs-lookup"><span data-stu-id="7d1bd-102">Search Documents Using Results Lists</span></span>
  <span data-ttu-id="7d1bd-103">Nella finestra di dialogo **Trova e sostituisci** è possibile eseguire ricerche e sostituzioni di testo in tutti i file di un progetto o di una soluzione o in una cartella di file system, anche se i file non sono aperti in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d1bd-103">Using the **Find and Replace** dialog box, you can search and replace text in all files in a project or solution or in a file system folder, even when they are not open in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="7d1bd-104">Le corrispondenze delle ricerche eseguite con la finestra di dialogo **Trova e sostituisci** vengono visualizzate nelle finestre Risultati ricerca 1 e Risultati ricerca 2, in cui è possibile vedere il testo esatto dalla riga contenente la corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="7d1bd-104">Matches from searches that were performed with the **Find and Replace** dialog box appear in the Find Results 1 and Find Results 2 windows, which allows you to view the exact text from the line containing the match.</span></span>  
  
### <a name="to-search-in-multiple-files"></a><span data-ttu-id="7d1bd-105">Per eseguire la ricerca in più file</span><span class="sxs-lookup"><span data-stu-id="7d1bd-105">To search in multiple files</span></span>  
  
1.  <span data-ttu-id="7d1bd-106">Scegliere **Trova e sostituisci** dal menu **Modifica** e fare clic su **Cerca nei file**.</span><span class="sxs-lookup"><span data-stu-id="7d1bd-106">On the **Edit** menu, point to **Find and Replace,** and then click **Find in Files**.</span></span>  
  
2.  <span data-ttu-id="7d1bd-107">Nella casella di testo **Trova** immettere il testo da cercare.</span><span class="sxs-lookup"><span data-stu-id="7d1bd-107">In the **Find what** text box, enter the text to search for.</span></span>  
  
3.  <span data-ttu-id="7d1bd-108">Nell'elenco **Cerca in** fare clic su **Tutti i documenti aperti**, **Progetto corrente**, **Intera soluzione**o digitare un percorso di directory.</span><span class="sxs-lookup"><span data-stu-id="7d1bd-108">In the **Look in** list, click **All Open Documents**, **Current Project**, **Entire Solution**, or type a directory path.</span></span>  
  
4.  <span data-ttu-id="7d1bd-109">Nell'elenco **Tipi di file** selezionare uno dei set di estensioni di file elencati o immettere le estensioni relative ai tipi di file su cui eseguire la ricerca separandole da un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="7d1bd-109">In the **File types** list, select one of the listed sets of file extensions or enter the extensions for the types of files to be searched, separated by semicolons.</span></span> <span data-ttu-id="7d1bd-110">Usare \*.\* per eseguire la ricerca in tutti i file della directory indicata nell'elenco a discesa **Cerca in** .</span><span class="sxs-lookup"><span data-stu-id="7d1bd-110">Use \*.\* to search all files in the directory listed in the **Look in** drop-down list.</span></span>  
  
5.  <span data-ttu-id="7d1bd-111">Selezionare altre opzioni di ricerca per definire ulteriormente la precisione della ricerca.</span><span class="sxs-lookup"><span data-stu-id="7d1bd-111">Select from the remaining search options to improve the accuracy of the search.</span></span>  
  
6.  <span data-ttu-id="7d1bd-112">Fare clic su **Trova** per iniziare la ricerca.</span><span class="sxs-lookup"><span data-stu-id="7d1bd-112">Click **Find** to begin the search.</span></span>  
  
 <span data-ttu-id="7d1bd-113">Per impostazione predefinita, le corrispondenze della ricerca vengono riportate nella finestra Risultati ricerca 1.</span><span class="sxs-lookup"><span data-stu-id="7d1bd-113">The matches for the search appear in the Find Results 1 window by default.</span></span> <span data-ttu-id="7d1bd-114">È possibile esplorare le corrispondenze della ricerca facendo doppio clic su ogni voce della finestra Risultati ricerca 1.</span><span class="sxs-lookup"><span data-stu-id="7d1bd-114">You can browse the search matches by double-clicking each entry in the Find Results 1 window.</span></span> <span data-ttu-id="7d1bd-115">Per visualizzare i risultati della ricerca in una nuova finestra, selezionare **Visualizza in Risultati ricerca 2**.</span><span class="sxs-lookup"><span data-stu-id="7d1bd-115">To view the search results in a new window, select **Display in Find 2**.</span></span>  
  
#### <a name="to-replace-across-multiple-files-or-folders"></a><span data-ttu-id="7d1bd-116">Per eseguire sostituzioni in più file o cartelle</span><span class="sxs-lookup"><span data-stu-id="7d1bd-116">To replace across multiple files or folders</span></span>  
  
1.  <span data-ttu-id="7d1bd-117">Scegliere **Trova e sostituisci** dal menu **Modifica** e fare clic su **Sostituisci nei file**.</span><span class="sxs-lookup"><span data-stu-id="7d1bd-117">On the **Edit** menu, point to **Find and Replace,** and then click **Replace in Files**.</span></span>  
  
2.  <span data-ttu-id="7d1bd-118">Nella casella di testo **Trova** immettere il testo da cercare.</span><span class="sxs-lookup"><span data-stu-id="7d1bd-118">In the **Find what** text box, enter the text to search for.</span></span>  
  
3.  <span data-ttu-id="7d1bd-119">Nella casella di testo **Sostituisci con** immettere il testo con cui sostituire il testo trovato.</span><span class="sxs-lookup"><span data-stu-id="7d1bd-119">In the **Replace with** box, enter the text to replace the search text.</span></span>  
  
4.  <span data-ttu-id="7d1bd-120">Nell'elenco **Cerca in** fare clic su **Tutti i documenti aperti**, **Progetto corrente**, **Intera soluzione**o digitare un percorso di directory.</span><span class="sxs-lookup"><span data-stu-id="7d1bd-120">In the **Look in** list, click **All Open Documents**, **Current Project**, **Entire Solution**, or type a directory path.</span></span>  
  
5.  <span data-ttu-id="7d1bd-121">Fare clic su **Sostituisci** per sostituire la corrispondenza di ricerca corrente con il testo contenuto nella casella **Sostituisci con** .</span><span class="sxs-lookup"><span data-stu-id="7d1bd-121">Click **Replace** to replace the current search match with the text in the **Replace with** box.</span></span> <span data-ttu-id="7d1bd-122">Fare clic su **Trova successivo** per ignorare una corrispondenza e su **Ignora file**per ignorare un intero file.</span><span class="sxs-lookup"><span data-stu-id="7d1bd-122">You can skip a single match by clicking **Find Next** or skip an entire file clicking **Skip File**.</span></span>  
  
     <span data-ttu-id="7d1bd-123">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="7d1bd-123">\- or -</span></span>  
  
     <span data-ttu-id="7d1bd-124">Scegliere **Sostituisci tutto** per sostituire tutte le corrispondenze di ricerca con il testo contenuto nella casella **Sostituisci con** .</span><span class="sxs-lookup"><span data-stu-id="7d1bd-124">Choose **Replace all** to replace all search matches with the text in the **Replace with** box.</span></span> <span data-ttu-id="7d1bd-125">Selezionare **Non chiudere i file modificati con Sostituisci tutto** se si vuole annullare alcune delle sostituzioni eseguite in un'altra sessione.</span><span class="sxs-lookup"><span data-stu-id="7d1bd-125">Select **Keep modified files open after Replace All** if you want to undo some of the replacements at another time.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7d1bd-126">**Sostituisci tutto** consente di sostituire tutte le corrispondenze di ricerca comprese quelle dei file ignorati con **Ignora file** o **Trova successivo**.</span><span class="sxs-lookup"><span data-stu-id="7d1bd-126">**Replace all** replaces all search matches, including those in files you have skipped with **Skip File** or **Find Next**.</span></span> <span data-ttu-id="7d1bd-127">È possibile usare **Annulla** solo per le sostituzioni eseguite nei file rimasti aperti dopo l'operazione di sostituzione.</span><span class="sxs-lookup"><span data-stu-id="7d1bd-127">You can only use **Undo** for replacements made in files that remain open after the replacement operation.</span></span>  
  
 <span data-ttu-id="7d1bd-128">Per impostazione predefinita, le informazioni di sostituzione vengono visualizzate nella finestra Risultati ricerca 1.</span><span class="sxs-lookup"><span data-stu-id="7d1bd-128">Replacement information appears in the Find Results 1 window by default.</span></span> <span data-ttu-id="7d1bd-129">È possibile esplorare le sostituzioni facendo doppio clic su ogni voce della finestra Risultati ricerca 1.</span><span class="sxs-lookup"><span data-stu-id="7d1bd-129">You can browse replacements by double-clicking each entry in the Find Results 1 window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d1bd-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d1bd-130">See Also</span></span>  
 <span data-ttu-id="7d1bd-131">[Ricerca e sostituzione](search-and-replace.md) </span><span class="sxs-lookup"><span data-stu-id="7d1bd-131">[Search and Replace](search-and-replace.md) </span></span>  
 <span data-ttu-id="7d1bd-132">[Ricerca interattiva all'interno di documenti](search-documents-interactively.md) </span><span class="sxs-lookup"><span data-stu-id="7d1bd-132">[Search Documents Interactively](search-documents-interactively.md) </span></span>  
 <span data-ttu-id="7d1bd-133">[Testo di ricerca con caratteri jolly](search-text-with-wildcards.md) </span><span class="sxs-lookup"><span data-stu-id="7d1bd-133">[Search Text with Wildcards](search-text-with-wildcards.md) </span></span>  
 [<span data-ttu-id="7d1bd-134">Eseguire ricerche di testo con espressioni regolari</span><span class="sxs-lookup"><span data-stu-id="7d1bd-134">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
  
  
