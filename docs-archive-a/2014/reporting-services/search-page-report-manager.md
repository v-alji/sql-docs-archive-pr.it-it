---
title: Pagina Cerca (Gestione report) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 51ffdc07-e1b9-4ed7-acb3-dd98d7cce273
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2528133f5b2ecc4bed4c16fdd476591b3bab52d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629194"
---
# <a name="search-page-report-manager"></a><span data-ttu-id="3b365-102">Pagina Cerca (Gestione report)</span><span class="sxs-lookup"><span data-stu-id="3b365-102">Search Page (Report Manager)</span></span>
  <span data-ttu-id="3b365-103">Utilizzare la pagina Risultati ricerca per visualizzare i risultati di un'operazione di ricerca eseguita in report, report collegati, modelli di report, origini dei dati condivise, cartelle o risorse.</span><span class="sxs-lookup"><span data-stu-id="3b365-103">Use the Search Results page to view the results of a search operation specified for a report, linked report, report model, shared data source, folder, or resource.</span></span> <span data-ttu-id="3b365-104">I risultati della ricerca vengono visualizzati in ordine alfabetico</span><span class="sxs-lookup"><span data-stu-id="3b365-104">Search results are listed alphabetically.</span></span> <span data-ttu-id="3b365-105">e possono essere ordinati in base al tipo, al nome o alla descrizione.</span><span class="sxs-lookup"><span data-stu-id="3b365-105">You can sort by type, name, or description.</span></span>  
  
 <span data-ttu-id="3b365-106">Dalle operazioni di ricerca sono esclusi gli snapshot di report inclusi nella cronologia dei report, le sottoscrizioni e le pianificazioni condivise.</span><span class="sxs-lookup"><span data-stu-id="3b365-106">The following items are excluded from a search operation: report snapshots contained in report history, subscriptions, and shared schedules.</span></span> <span data-ttu-id="3b365-107">In modo analogo, se non si dispone di autorizzazioni sufficienti per la visualizzazione di una cartella o un report, tale elemento verrà escluso dalla ricerca.</span><span class="sxs-lookup"><span data-stu-id="3b365-107">Similarly, insufficient permission to view a folder or report excludes that item from a search.</span></span>  
  
 <span data-ttu-id="3b365-108">Non è possibile cercare testo all'interno di un report o di un modello.</span><span class="sxs-lookup"><span data-stu-id="3b365-108">You cannot search for text within a report or model.</span></span> <span data-ttu-id="3b365-109">Per cercare testo specifico all'interno di un report, utilizzare la barra degli strumenti nella parte superiore del report.</span><span class="sxs-lookup"><span data-stu-id="3b365-109">To search for specific text within a report, use the toolbar at the top of the report.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="3b365-110">Spostamento</span><span class="sxs-lookup"><span data-stu-id="3b365-110">Navigation</span></span>  
 <span data-ttu-id="3b365-111">Utilizzare la procedura riportata di seguito per navigare fino a questo percorso nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="3b365-111">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-search-results-page"></a><span data-ttu-id="3b365-112">Per aprire la pagina Risultati ricerca</span><span class="sxs-lookup"><span data-stu-id="3b365-112">To open the Search Results page</span></span>  
  
1.  <span data-ttu-id="3b365-113">Aprire Gestione report.</span><span class="sxs-lookup"><span data-stu-id="3b365-113">Open Report Manager.</span></span>  
  
2.  <span data-ttu-id="3b365-114">All'inizio della pagina, digitare il criterio di ricerca nella casella **Cerca** .</span><span class="sxs-lookup"><span data-stu-id="3b365-114">At the top of the page, type your search criteria in the **Search** box.</span></span> <span data-ttu-id="3b365-115">Quindi premere Invio o fare clic sulla freccia Cerca.</span><span class="sxs-lookup"><span data-stu-id="3b365-115">Then press Enter or click the Search arrow.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3b365-116">Opzioni</span><span class="sxs-lookup"><span data-stu-id="3b365-116">Options</span></span>  
 <span data-ttu-id="3b365-117">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="3b365-117">**Delete**</span></span>  
 <span data-ttu-id="3b365-118">Fare clic per rimuovere un elemento da un database del server di report.</span><span class="sxs-lookup"><span data-stu-id="3b365-118">Click to remove an item from a report server database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3b365-119">Questo pulsante è disponibile solo in **Visualizzazione Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="3b365-119">This button is available only in **Details View**.</span></span> <span data-ttu-id="3b365-120">Tuttavia, è possibile passare il puntatore del mouse su un elemento e utilizzare il menu per accedere alla funzionalità di eliminazione in **Visualizzazione Dettagli** o in **Visualizzazione Elenco**.</span><span class="sxs-lookup"><span data-stu-id="3b365-120">However, you can hover over an item and use the menu to access the delete functionality in either **Details View** or in **List View**.</span></span>  
  
 <span data-ttu-id="3b365-121">**Spostamento**</span><span class="sxs-lookup"><span data-stu-id="3b365-121">**Move**</span></span>  
 <span data-ttu-id="3b365-122">Fare clic per spostare un elemento.</span><span class="sxs-lookup"><span data-stu-id="3b365-122">Click to relocate an item.</span></span> <span data-ttu-id="3b365-123">Verrà visualizzata la pagina di spostamento degli elementi, nella quale è possibile selezionare un diverso percorso della cartella.</span><span class="sxs-lookup"><span data-stu-id="3b365-123">This opens the Move Items page, where you can select a different folder location.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3b365-124">Questo pulsante è disponibile solo in **Visualizzazione Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="3b365-124">This button is available only in **Details View**.</span></span> <span data-ttu-id="3b365-125">Tuttavia, è possibile passare il puntatore del mouse su un elemento e utilizzare il menu per accedere alla funzionalità di spostamento in **Visualizzazione Dettagli** o in **Visualizzazione Elenco**.</span><span class="sxs-lookup"><span data-stu-id="3b365-125">However, you can hover over an item and use the menu to access the move functionality in either **Details View** or in **List View**.</span></span>  
  
 <span data-ttu-id="3b365-126">Casella di ricerca</span><span class="sxs-lookup"><span data-stu-id="3b365-126">Search box</span></span>  
 <span data-ttu-id="3b365-127">Digitare tutto o parte del nome di un elemento che si desidera individuare, quindi fare clic su **Vai** per avviare la ricerca.</span><span class="sxs-lookup"><span data-stu-id="3b365-127">Type all or part of the name of an item that you want to locate, and then click **Go** to start the search.</span></span> <span data-ttu-id="3b365-128">La stringa di ricerca può essere composta al massimo da 128 caratteri.</span><span class="sxs-lookup"><span data-stu-id="3b365-128">The longest string you can search for is 128 characters.</span></span>  
  
 <span data-ttu-id="3b365-129">Nei risultati di ricerca verranno inclusi i nomi o le descrizioni degli elementi che contengono l'intera stringa di ricerca in qualsiasi posizione nel valore di testo.</span><span class="sxs-lookup"><span data-stu-id="3b365-129">Item names or descriptions that contain the entire search string anywhere in the text value are included in the search results.</span></span>  
  
 <span data-ttu-id="3b365-130">Gli operatori booleani, ad esempio il segno più (+), non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="3b365-130">Boolean operators such as the plus character (+) are not supported.</span></span>  
  
 <span data-ttu-id="3b365-131">**Visualizzazione dettagli**</span><span class="sxs-lookup"><span data-stu-id="3b365-131">**Details View**</span></span>  
 <span data-ttu-id="3b365-132">Fare clic per visualizzare la pagina Risultati ricerca in un elenco che contiene informazioni aggiuntive sugli elementi, quale il tipo di elemento, il nome, la descrizione, la cartella che contiene l'elemento e la data dell'ultima esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3b365-132">Click to display the Search Results page in a list that contains additional information about items, such as the item type, name, description, the folder in which the item is located, and when it was last run.</span></span> <span data-ttu-id="3b365-133">In **Visualizzazione Dettagli**, è possibile utilizzare i pulsanti **Elimina** e **Sposta** per rimuovere e spostare gli elementi nella cartella.</span><span class="sxs-lookup"><span data-stu-id="3b365-133">In **Details View**, you can use **Delete** and **Move** buttons to remove and relocate items in the folder.</span></span>  
  
 <span data-ttu-id="3b365-134">Passare con il puntatore del mouse su un elemento e fare clic sulla freccia a discesa per aprire il menu a discesa dal quale è possibile accedere alle proprietà dell'elemento selezionato ed eseguirne la configurazione.</span><span class="sxs-lookup"><span data-stu-id="3b365-134">Hover over an item and click the drop-down arrow to open the drop-down menu from which you can access and configure properties of the selected item.</span></span>  
  
 <span data-ttu-id="3b365-135">**Visualizzazione elenco**</span><span class="sxs-lookup"><span data-stu-id="3b365-135">**List View**</span></span>  
 <span data-ttu-id="3b365-136">Fare clic su questo pulsante per visualizzare la pagina Risultati ricerca senza dettagli come in **visualizzazione dettagli**.</span><span class="sxs-lookup"><span data-stu-id="3b365-136">Click to display the Search Results page without details as in **Details View**.</span></span> <span data-ttu-id="3b365-137">Visualizzazione Elenco è la visualizzazione predefinita quando viene visualizzata la pagina Risultati ricerca.</span><span class="sxs-lookup"><span data-stu-id="3b365-137">List View is the default view when the Search Results page opens.</span></span>  
  
 <span data-ttu-id="3b365-138">Passare con il puntatore del mouse su un elemento e fare clic sulla freccia a discesa per aprire il menu a discesa dal quale è possibile accedere alle proprietà dell'elemento selezionato ed eseguirne la configurazione.</span><span class="sxs-lookup"><span data-stu-id="3b365-138">Hover over an item and click the drop-down arrow to open the drop-down menu from which you can access and configure properties of the selected item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b365-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b365-139">See Also</span></span>  
 <span data-ttu-id="3b365-140">[Gestione report &#40;modalità nativa SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="3b365-140">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="3b365-141">Guida sensibile al contesto di Gestione report</span><span class="sxs-lookup"><span data-stu-id="3b365-141">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
