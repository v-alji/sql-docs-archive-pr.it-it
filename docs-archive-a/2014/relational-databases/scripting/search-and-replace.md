---
title: Ricerca e sostituzione
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- match case [SQL Server]
- undo operations
- searches [SQL Server Management Studio]
- replacing text
- quick search and replaces [SQL Server Management Studio]
- Query Editor [SQL Server Management Studio], undo
- Query Editor [SQL Server Management Studio], searching
- regular expressions [SQL Server Management Studio]
- finding text [SQL Server Management Studio]
- text [SQL Server], search and replace operations
- finding [SQL Server Management Studio]
- locating text
- Query Editor [SQL Server Management Studio], replacing text
- Find and Replace dialog box
- wildcard options [SQL Server Management Studio]
- match whole word [SQL Server]
- searches [SQL Server Management Studio], replacing
ms.assetid: 3641c7b3-3e3e-4ddd-af82-c15b50004f94
author: rothja
ms.author: jroth
ms.openlocfilehash: 55422fa7201213477426c7bc25c45ff05acf8945
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625297"
---
# <a name="search-and-replace"></a><span data-ttu-id="634c9-102">Ricerca e sostituzione</span><span class="sxs-lookup"><span data-stu-id="634c9-102">Search and Replace</span></span>
  <span data-ttu-id="634c9-103">È possibile eseguire ricerche e sostituzioni di testo in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="634c9-103">There are several different ways to find and replace text.</span></span> <span data-ttu-id="634c9-104">L'opzione **Trova e sostituisci** del menu **Modifica** offre quattro scelte: **Ricerca veloce**, **Sostituzione veloce**, **Cerca nei file**e **Sostituisci nei file**.</span><span class="sxs-lookup"><span data-stu-id="634c9-104">On the **Edit** menu, **Find and Replace** offers four choices: **Quick Find**, **Quick Replace**, **Find in Files**, or **Replace in Files**.</span></span> <span data-ttu-id="634c9-105">L'aspetto della finestra di dialogo **Trova e sostituisci** cambia in base all'opzione selezionata.</span><span class="sxs-lookup"><span data-stu-id="634c9-105">Each of these opens versions of the **Find and Replace** dialog box.</span></span> <span data-ttu-id="634c9-106">È inoltre possibile eseguire ricerche senza una finestra di dialogo, utilizzando i tasti di scelta rapida per la ricerca incrementale.</span><span class="sxs-lookup"><span data-stu-id="634c9-106">You can also search without a dialog box by using incremental search keyboard shortcut keys.</span></span> <span data-ttu-id="634c9-107">Queste tecniche consentono di controllare l'ambito di ricerca e sostituzione e di scegliere il metodo di analisi dei risultati.</span><span class="sxs-lookup"><span data-stu-id="634c9-107">These techniques allow you to control the scope of find and replace, and choose the method of reviewing search matches and replacements.</span></span>  
  
 <span data-ttu-id="634c9-108">Al momento della ricerca e sostituzione di un testo, è consigliabile tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="634c9-108">You should consider the following when you search and replace text:</span></span>  
  
-   <span data-ttu-id="634c9-109">Le opzioni impostate nella finestra di dialogo **Trova e sostituisci** influenzano tutte le ricerche.</span><span class="sxs-lookup"><span data-stu-id="634c9-109">Options set in the **Find and Replace** dialog box affect all the searches.</span></span> <span data-ttu-id="634c9-110">Le opzioni disponibili sono **Maiuscole/minuscole**, **Parola intera**, **Cerca in alto**, **Cerca nel testo nascosto**, **Caratteri jolly**, **Espressioni regolari**, **Tutti i documenti aperti**e **Progetto corrente**.</span><span class="sxs-lookup"><span data-stu-id="634c9-110">These options include **Match case**, **Match whole word**, **Search up**, **Search hidden text**, **Wildcards**, **Regular Expressions**, **Look in All Open Documents**, and **Look in Current Project**.</span></span> <span data-ttu-id="634c9-111">Le opzioni effettivamente disponibili dipendono dalla versione usata della finestra di dialogo **Trova e sostituisci** .</span><span class="sxs-lookup"><span data-stu-id="634c9-111">All options are not available in all versions of the **Find and Replace** dialog box.</span></span>  
  
-   <span data-ttu-id="634c9-112">L'opzione**Annulla** è disponibile solo per i documenti lasciati aperti dopo un'operazione di sostituzione.</span><span class="sxs-lookup"><span data-stu-id="634c9-112">**Undo** is available only for documents left open after a replace operation.</span></span>  
  
-   <span data-ttu-id="634c9-113">L'opzione**Annulla** per un'operazione **Sostituisci tutto** eseguita su più di un file è considerata un'unica azione bulk su tutti i file interessati.</span><span class="sxs-lookup"><span data-stu-id="634c9-113">**Undo** for a **Replace All** operation that spans more than one file is considered a single, bulk action across all the affected files.</span></span> <span data-ttu-id="634c9-114">Non è quindi possibile annullare la modifica in alcuni file e mantenerla in altri.</span><span class="sxs-lookup"><span data-stu-id="634c9-114">That is, you cannot undo the change in some files while retaining the change in other files.</span></span>  
  
 <span data-ttu-id="634c9-115">Non è in genere possibile eseguire ricerche in elementi grafici.</span><span class="sxs-lookup"><span data-stu-id="634c9-115">Generally, you cannot search items with graphical views.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="634c9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="634c9-116">See Also</span></span>  
 <span data-ttu-id="634c9-117">[Ricerca incrementale in un documento attivo](search-an-active-document-incrementally.md) </span><span class="sxs-lookup"><span data-stu-id="634c9-117">[Search an Active Document Incrementally](search-an-active-document-incrementally.md) </span></span>  
 <span data-ttu-id="634c9-118">[Ricerca interattiva all'interno di documenti](search-documents-interactively.md) </span><span class="sxs-lookup"><span data-stu-id="634c9-118">[Search Documents Interactively](search-documents-interactively.md) </span></span>  
 <span data-ttu-id="634c9-119">[Ricerca nei documenti utilizzando gli elenchi dei risultati](search-documents-using-results-lists.md) </span><span class="sxs-lookup"><span data-stu-id="634c9-119">[Search Documents Using Results Lists](search-documents-using-results-lists.md) </span></span>  
 <span data-ttu-id="634c9-120">[Testo di ricerca con caratteri jolly](search-text-with-wildcards.md) </span><span class="sxs-lookup"><span data-stu-id="634c9-120">[Search Text with Wildcards](search-text-with-wildcards.md) </span></span>  
 [<span data-ttu-id="634c9-121">Eseguire ricerche di testo con espressioni regolari</span><span class="sxs-lookup"><span data-stu-id="634c9-121">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
  
  
