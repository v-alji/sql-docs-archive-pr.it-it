---
title: Pagina elementi dipendenti (Gestione report) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4dcfb311-e9c3-4c5d-b2e0-018d79f37d2e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 488b10d7d7985972274340897ee3975618a12639
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625238"
---
# <a name="dependent-items-page-report-manager"></a><span data-ttu-id="428af-102">Pagina Elementi dipendenti (Gestione report)</span><span class="sxs-lookup"><span data-stu-id="428af-102">Dependent Items Page (Report Manager)</span></span>
  <span data-ttu-id="428af-103">La pagina Elementi dipendenti consente di visualizzare un elenco di report e modelli che fanno riferimento a un'origine dati condivisa.</span><span class="sxs-lookup"><span data-stu-id="428af-103">Use the Dependent Items page to view a list of reports and models that reference a shared data source.</span></span> <span data-ttu-id="428af-104">L'icona disponibile per ogni tipo di elemento indica se si tratta di un report o un modello.</span><span class="sxs-lookup"><span data-stu-id="428af-104">The icon for each item type indicates whether it is a report or a model.</span></span> <span data-ttu-id="428af-105">Questa pagina può essere visualizzata nella visualizzazione Elenco o Dettagli.</span><span class="sxs-lookup"><span data-stu-id="428af-105">This page can be viewed in list view or details view.</span></span> <span data-ttu-id="428af-106">Se per ogni elemento si desidera visualizzare un numero maggiore di informazioni, è consigliabile utilizzare la visualizzazione Dettagli.</span><span class="sxs-lookup"><span data-stu-id="428af-106">Use details view to show more information about each item.</span></span> <span data-ttu-id="428af-107">In tale visualizzazione sono infatti disponibili opzioni aggiuntive per la pagina.</span><span class="sxs-lookup"><span data-stu-id="428af-107">Additional page options are available in details view.</span></span> <span data-ttu-id="428af-108">Per semplificare la gestione dell'origine dati condivisa, questa pagina fornisce collegamenti ai report e ai modelli che utilizzano l'origine dati, metriche relative all'ultima esecuzione del report o del modello, nonché i pulsanti Elimina e Sposta, che consentono di rimuovere in modo semplice report e modelli non più utilizzati o di spostarli in una posizione diversa mentre si stabilisce se sono ancora necessari.</span><span class="sxs-lookup"><span data-stu-id="428af-108">To help you manage the shared data source, this page provides links to reports and models that use the data source, metrics on when the report or model was last run or modified, and Delete and Move buttons so that you can easily remove reports and models that are no longer used, or move them to a different location while you determine whether they are still needed.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="428af-109">Spostamento</span><span class="sxs-lookup"><span data-stu-id="428af-109">Navigation</span></span>  
 <span data-ttu-id="428af-110">Utilizzare la procedura riportata di seguito per navigare fino a questo percorso nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="428af-110">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-dependent-items-page"></a><span data-ttu-id="428af-111">Per aprire la pagina Elementi dipendenti</span><span class="sxs-lookup"><span data-stu-id="428af-111">To open the Dependent Items page</span></span>  
  
1.  <span data-ttu-id="428af-112">Aprire Gestione report e individuare l'origine dati condivisa per la quale si desidera visualizzare gli elementi dipendenti.</span><span class="sxs-lookup"><span data-stu-id="428af-112">Open Report Manager, and locate the shared data source for which you want to view dependent items.</span></span>  
  
2.  <span data-ttu-id="428af-113">Posizionare il puntatore del mouse sull'elemento, quindi fare clic sulla freccia a discesa.</span><span class="sxs-lookup"><span data-stu-id="428af-113">Hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="428af-114">Scegliere **Gestisci**dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="428af-114">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="428af-115">Verrà visualizzata la pagina delle proprietà Generale per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="428af-115">This opens the General properties page for the data source.</span></span>  
  
4.  <span data-ttu-id="428af-116">Selezionare la scheda **Elementi dipendenti** .</span><span class="sxs-lookup"><span data-stu-id="428af-116">Select the **Dependent Items** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="428af-117">Opzioni</span><span class="sxs-lookup"><span data-stu-id="428af-117">Options</span></span>  
 <span data-ttu-id="428af-118">**Nome**</span><span class="sxs-lookup"><span data-stu-id="428af-118">**Name**</span></span>  
 <span data-ttu-id="428af-119">Consente di visualizzare il nome del report o del modello.</span><span class="sxs-lookup"><span data-stu-id="428af-119">Shows the name of the report or model.</span></span> <span data-ttu-id="428af-120">Fare clic sul nome del report per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="428af-120">Click the name of the report to open it.</span></span> <span data-ttu-id="428af-121">Fare clic sul nome del modello per aprire le relative pagine delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="428af-121">Click the name of the model to open its property pages.</span></span>  
  
 <span data-ttu-id="428af-122">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="428af-122">**Description**</span></span>  
 <span data-ttu-id="428af-123">Mostra la descrizione del report o del modello.</span><span class="sxs-lookup"><span data-stu-id="428af-123">Shows the description of the report or model.</span></span>  
  
 <span data-ttu-id="428af-124">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="428af-124">**Delete**</span></span>  
 <span data-ttu-id="428af-125">Fare clic per eliminare il report o il  modello dal database del server di report.</span><span class="sxs-lookup"><span data-stu-id="428af-125">Click to delete the report or model from the report server database.</span></span> <span data-ttu-id="428af-126">Prima di fare clic su **Elimina**, selezionare la casella di controllo accanto a ogni elemento che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="428af-126">Before clicking **Delete**, select the check box next to each item that you want to delete.</span></span>  
  
 <span data-ttu-id="428af-127">**Spostamento**</span><span class="sxs-lookup"><span data-stu-id="428af-127">**Move**</span></span>  
 <span data-ttu-id="428af-128">Fare clic per spostare un report o un modello all'interno della gerarchia di cartelle.</span><span class="sxs-lookup"><span data-stu-id="428af-128">Click to relocate a report or model within the folder hierarchy.</span></span> <span data-ttu-id="428af-129">Prima di fare clic su **Sposta**selezionare la casella di controllo accanto a ogni elemento che si desidera spostare.</span><span class="sxs-lookup"><span data-stu-id="428af-129">Before clicking **Move**, select the check box next to each item that you want to move.</span></span> <span data-ttu-id="428af-130">Verrà visualizzata la pagina di spostamento degli elementi, nella quale è possibile esplorare le cartelle per selezionare un nuovo percorso.</span><span class="sxs-lookup"><span data-stu-id="428af-130">This opens the Move Items page, where you can browse through folders to select a new location.</span></span>  
  
 <span data-ttu-id="428af-131">**Modifica**</span><span class="sxs-lookup"><span data-stu-id="428af-131">**Edit**</span></span>  
 <span data-ttu-id="428af-132">Fare clic sull'icona delle proprietà per accedere alle pagine delle proprietà di un report o di un modello.</span><span class="sxs-lookup"><span data-stu-id="428af-132">Click the Property icon to access the property pages of a report, or model.</span></span>  
  
 <span data-ttu-id="428af-133">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="428af-133">**Type**</span></span>  
 <span data-ttu-id="428af-134">Mostra l'icona del tipo di elemento.</span><span class="sxs-lookup"><span data-stu-id="428af-134">Shows the icon of the item type.</span></span>  
  
 <span data-ttu-id="428af-135">**Data ultima modifica**</span><span class="sxs-lookup"><span data-stu-id="428af-135">**Modified Date**</span></span>  
 <span data-ttu-id="428af-136">Mostra la data e l'ora dell'ultima modifica del report o del modello.</span><span class="sxs-lookup"><span data-stu-id="428af-136">Shows the date and time when the report or model was last modified.</span></span>  
  
 <span data-ttu-id="428af-137">**Modificato da**</span><span class="sxs-lookup"><span data-stu-id="428af-137">**Modified By**</span></span>  
 <span data-ttu-id="428af-138">Mostra il nome dell'ultimo utente che ha modificato le proprietà dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="428af-138">Shows the name of the user who last modified the item properties.</span></span>  
  
 <span data-ttu-id="428af-139">**Data ultima esecuzione**</span><span class="sxs-lookup"><span data-stu-id="428af-139">**When Run**</span></span>  
 <span data-ttu-id="428af-140">Per i report eseguiti come snapshot dell'esecuzione del report, visualizza la data e l'ora dell'ultimo aggiornamento del report.</span><span class="sxs-lookup"><span data-stu-id="428af-140">For reports that run as report execution snapshots, displays the date and time at which the report was last refreshed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="428af-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="428af-141">See Also</span></span>  
 <span data-ttu-id="428af-142">[Guida sensibile al contesto Gestione report](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="428af-142">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 <span data-ttu-id="428af-143">[Gestione report &#40;modalità nativa SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="428af-143">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="428af-144">[Pagina contenuti &#40;Gestione report&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="428af-144">[Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span></span>  
 [<span data-ttu-id="428af-145">Guida sensibile al contesto di Gestione report</span><span class="sxs-lookup"><span data-stu-id="428af-145">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
