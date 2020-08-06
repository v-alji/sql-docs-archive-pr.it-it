---
title: Finestra di dialogo SQL Server Profiler-trova | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.find.f1
helpviewer_keywords:
- Find dialog box
ms.assetid: dfaeec04-93d3-4214-9fc1-38b80179b36b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cedf50930c06d211ebcee0c45a249667219f392c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721712"
---
# <a name="sql-server-profiler---find-dialog-box"></a><span data-ttu-id="1379f-102">SQL Server Profiler - Finestra di dialogo Trova</span><span class="sxs-lookup"><span data-stu-id="1379f-102">SQL Server Profiler - Find Dialog Box</span></span>
  <span data-ttu-id="1379f-103">Usare la finestra di dialogo **Trova** per eseguire la ricerca all'interno di una traccia in base a parole o caratteri specifici.</span><span class="sxs-lookup"><span data-stu-id="1379f-103">Use the **Find** dialog box to search a trace for specific characters or words.</span></span> <span data-ttu-id="1379f-104">Per annullare la ricerca in corso, premere ESC.</span><span class="sxs-lookup"><span data-stu-id="1379f-104">To cancel a search in progress, press ESC.</span></span>  
  
 <span data-ttu-id="1379f-105">Per aprire questa finestra di dialogo in [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], scegliere **Trova** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="1379f-105">To open this dialog box in [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], on the **Edit** menu, click **Find**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1379f-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1379f-106">Options</span></span>  
 <span data-ttu-id="1379f-107">**Trova**</span><span class="sxs-lookup"><span data-stu-id="1379f-107">**Find what**</span></span>  
 <span data-ttu-id="1379f-108">Immettere il testo che si desidera cercare.</span><span class="sxs-lookup"><span data-stu-id="1379f-108">Enter the text that you want to search for.</span></span> <span data-ttu-id="1379f-109">La ricerca individua tutte le stringhe contenenti la stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="1379f-109">The search matches any string containing the specified string.</span></span> <span data-ttu-id="1379f-110">Ad esempio, se si cerca "Completed", viene individuata la stringa "SQL:BatchCompleted."</span><span class="sxs-lookup"><span data-stu-id="1379f-110">For example, searching for "Completed" matches "SQL:BatchCompleted."</span></span> <span data-ttu-id="1379f-111">I caratteri jolly (\*, ? e così via) non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="1379f-111">Wild card characters (\*, ?, etc.) are not supported.</span></span>  
  
 <span data-ttu-id="1379f-112">**Cerca nella colonna**</span><span class="sxs-lookup"><span data-stu-id="1379f-112">**Search in column**</span></span>  
 <span data-ttu-id="1379f-113">Fare clic su una colonna di dati in cui eseguire la ricerca o su **\<All columns>** per cercare tutte le colonne di dati nella traccia.</span><span class="sxs-lookup"><span data-stu-id="1379f-113">Click a data column to search, or click **\<All columns>** to search all the data columns in the trace.</span></span>  
  
 <span data-ttu-id="1379f-114">**Maiuscole/minuscole**</span><span class="sxs-lookup"><span data-stu-id="1379f-114">**Match case**</span></span>  
 <span data-ttu-id="1379f-115">Consente di trovare una stringa di testo con le stesse lettere maiuscole e minuscole di quella specificata nella casella **Trova** .</span><span class="sxs-lookup"><span data-stu-id="1379f-115">Finds text that has the same case as the **Find what** box.</span></span> <span data-ttu-id="1379f-116">Deselezionare questa casella di controllo per trovare stringhe di testo nella traccia che corrispondono al testo specificato indipendentemente dai caratteri maiuscoli o minuscoli.</span><span class="sxs-lookup"><span data-stu-id="1379f-116">Clear this check box to find examples in the trace that are in both uppercase and lowercase text characters.</span></span>  
  
 <span data-ttu-id="1379f-117">**Parola intera**</span><span class="sxs-lookup"><span data-stu-id="1379f-117">**Match whole word**</span></span>  
 <span data-ttu-id="1379f-118">Consente di limitare l'ambito della ricerca alle parole intere.</span><span class="sxs-lookup"><span data-stu-id="1379f-118">Restricts the search to entire words.</span></span> <span data-ttu-id="1379f-119">Deselezionare la casella di controllo **Parola intera** per cercare un insieme di caratteri all'interno di una parola.</span><span class="sxs-lookup"><span data-stu-id="1379f-119">Clear the **Match whole word** check box to search for characters within a word.</span></span>  
  
 <span data-ttu-id="1379f-120">**Trova successivo**</span><span class="sxs-lookup"><span data-stu-id="1379f-120">**Find Next**</span></span>  
 <span data-ttu-id="1379f-121">Consente di trovare l'esempio successivo dei caratteri specificati nella casella **Trova** .</span><span class="sxs-lookup"><span data-stu-id="1379f-121">Finds the next example of the characters in the **Find what** box.</span></span>  
  
 <span data-ttu-id="1379f-122">**Trova precedente**</span><span class="sxs-lookup"><span data-stu-id="1379f-122">**Find Previous**</span></span>  
 <span data-ttu-id="1379f-123">Consente di eseguire una ricerca all'indietro per trovare l'esempio precedente dei caratteri specificati nella casella **Trova** .</span><span class="sxs-lookup"><span data-stu-id="1379f-123">Searches backwards in the trace, to find the previous example of the characters in the **Find what** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1379f-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1379f-124">See Also</span></span>  
 <span data-ttu-id="1379f-125">[Trovare un valore o una colonna di dati durante la traccia &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/find-a-value-or-data-column-while-tracing-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="1379f-125">[Find a Value or Data Column While Tracing &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/find-a-value-or-data-column-while-tracing-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="1379f-126">[Creare una traccia &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="1379f-126">[Create a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="1379f-127">[Aprire una tabella di traccia &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/open-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="1379f-127">[Open a Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/open-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="1379f-128">[Aprire un file di traccia &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="1379f-128">[Open a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="1379f-129">[Modelli e autorizzazioni di SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="1379f-129">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="1379f-130">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="1379f-130">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
