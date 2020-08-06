---
title: Ricerca incrementale in un documento attivo
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- searches [SQL Server Management Studio], incremental
- Query Editor [SQL Server Management Studio], incremental search
- incremental searches [SQL Server Management Studio]
ms.assetid: 490bb36c-dd43-4219-9e2a-ff27046b9395
author: rothja
ms.author: jroth
ms.openlocfilehash: aefc2f0b7abff5992a8f4f7817e564ef1b72009d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625300"
---
# <a name="search-an-active-document-incrementally"></a><span data-ttu-id="43f08-102">Ricerca incrementale in un documento attivo</span><span class="sxs-lookup"><span data-stu-id="43f08-102">Search an Active Document Incrementally</span></span>
  <span data-ttu-id="43f08-103">È possibile eseguire una ricerca incrementale in un singolo documento o in una singola finestra immettendo il testo.</span><span class="sxs-lookup"><span data-stu-id="43f08-103">You can search a single document or window incrementally by entering text.</span></span> <span data-ttu-id="43f08-104">Verrà evidenziato il primo set di caratteri che corrisponde ai caratteri immessi durante la ricerca incrementale nel documento o nella finestra.</span><span class="sxs-lookup"><span data-stu-id="43f08-104">The search operation highlights the first set of characters that matches the characters entered during the incremental search in the document or window.</span></span> <span data-ttu-id="43f08-105">La ricerca viene estesa automaticamente a tutto il testo all'interno di un documento o di una finestra, fatta eccezione per il testo nascosto.</span><span class="sxs-lookup"><span data-stu-id="43f08-105">Incremental search automatically searches all of the text within a document or window except for text that has been hidden.</span></span>  
  
 <span data-ttu-id="43f08-106">Se viene scelta l'opzione **Maiuscole/minuscole** , per la ricerca incrementale verranno usati i criteri della ricerca precedente.</span><span class="sxs-lookup"><span data-stu-id="43f08-106">For the **Match case** option, incremental search uses the criteria from your previous search.</span></span> <span data-ttu-id="43f08-107">Se, ad esempio, in precedenza è stata eseguita una ricerca su più file tramite la finestra di dialogo **Cerca nei file** , viene selezionata l'opzione **Maiuscole/minuscole**e quindi viene eseguita una ricerca incrementale. Nella ricerca verrà fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="43f08-107">For example, if you searched across multiple files using the **Find in Files** dialog box and select **Match Case**, and you next search incrementally, the search will be case-sensitive.</span></span>  
  
### <a name="to-search-incrementally"></a><span data-ttu-id="43f08-108">Per eseguire una ricerca incrementale</span><span class="sxs-lookup"><span data-stu-id="43f08-108">To search incrementally</span></span>  
  
1.  <span data-ttu-id="43f08-109">Aprire il file o la finestra in cui si desidera eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="43f08-109">Open the file or window to you want to search.</span></span>  
  
2.  <span data-ttu-id="43f08-110">Scegliere **Avanzate** dal menu **Modifica**e quindi fare clic su **Ricerca incrementale**.</span><span class="sxs-lookup"><span data-stu-id="43f08-110">On the **Edit** menu, point to **Advanced**, and then click **Incremental Search**.</span></span>  
  
     <span data-ttu-id="43f08-111">L'icona del cursore si trasforma in un binocolo con una freccia, che indica la direzione della ricerca, mentre sulla barra di stato viene visualizzato "Ricerca incrementale".</span><span class="sxs-lookup"><span data-stu-id="43f08-111">The cursor icon changes to a binocular with an arrow, indicating the search direction, and the status bar displays "Incremental Search."</span></span>  
  
3.  <span data-ttu-id="43f08-112">Iniziare a digitare la stringa di testo.</span><span class="sxs-lookup"><span data-stu-id="43f08-112">Begin typing the text string.</span></span>  
  
     <span data-ttu-id="43f08-113">Sulla barra di stato viene visualizzato il testo immesso mentre l'editor evidenzia la prima occorrenza corrispondente.</span><span class="sxs-lookup"><span data-stu-id="43f08-113">The status bar displays the text you are entering while the editor highlights the first occurrence that matches the text.</span></span> <span data-ttu-id="43f08-114">Mentre la digitazione continua, l'editor si sposta sulla corrispondenza successiva e la evidenzia.</span><span class="sxs-lookup"><span data-stu-id="43f08-114">As you continue typing, the editor moves to the next match and highlights it.</span></span> <span data-ttu-id="43f08-115">Se non viene trovata nessuna corrispondenza, sulla barra di stato viene visualizzato quanto segue.</span><span class="sxs-lookup"><span data-stu-id="43f08-115">If no matches are available, the status bar displays the following.</span></span>  
  
    ```  
    Incremental Search: <text> (not found)  
    ```  
  
 <span data-ttu-id="43f08-116">Le ricerche incrementali vengono eseguite procedendo verso il basso e da sinistra a destra a partire dalla posizione corrente nel documento.</span><span class="sxs-lookup"><span data-stu-id="43f08-116">Incremental searches are performed from the current location in the document downwards from left to right.</span></span> <span data-ttu-id="43f08-117">È possibile utilizzare i tasti di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="43f08-117">Incremental searches can be done using keyboard shortcut keys.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="43f08-118">Per un elenco completo dei tasti di scelta rapida, vedere [Tasti di scelta rapida di SQL Server Management Studio](../../ssms/sql-server-management-studio-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="43f08-118">For a complete list of keyboard shortcut keys, see [SQL Server Management Studio Keyboard Shortcuts](../../ssms/sql-server-management-studio-keyboard-shortcuts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43f08-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43f08-119">See Also</span></span>  
 <span data-ttu-id="43f08-120">[Ricerca e sostituzione](search-and-replace.md) </span><span class="sxs-lookup"><span data-stu-id="43f08-120">[Search and Replace](search-and-replace.md) </span></span>  
 <span data-ttu-id="43f08-121">[Ricerca interattiva all'interno di documenti](search-documents-interactively.md) </span><span class="sxs-lookup"><span data-stu-id="43f08-121">[Search Documents Interactively](search-documents-interactively.md) </span></span>  
 <span data-ttu-id="43f08-122">[Ricerca nei documenti utilizzando gli elenchi dei risultati](search-documents-using-results-lists.md) </span><span class="sxs-lookup"><span data-stu-id="43f08-122">[Search Documents Using Results Lists](search-documents-using-results-lists.md) </span></span>  
 <span data-ttu-id="43f08-123">[Testo di ricerca con caratteri jolly](search-text-with-wildcards.md) </span><span class="sxs-lookup"><span data-stu-id="43f08-123">[Search Text with Wildcards](search-text-with-wildcards.md) </span></span>  
 [<span data-ttu-id="43f08-124">Eseguire ricerche di testo con espressioni regolari</span><span class="sxs-lookup"><span data-stu-id="43f08-124">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
  
  
