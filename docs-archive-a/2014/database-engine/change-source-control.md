---
title: Modificare il controllo del codice sorgente | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- IDD_SCC_CONNECTION_DIALOG
helpviewer_keywords:
- Change Source Control dialog box
ms.assetid: e6a5d83c-5809-4c56-907a-73d0c7ccdd7a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 55831529243608e8c71972a31009e5672fb0234f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630072"
---
# <a name="change-source-control"></a><span data-ttu-id="004c2-102">Modificare il controllo del codice sorgente</span><span class="sxs-lookup"><span data-stu-id="004c2-102">Change Source Control</span></span>
  <span data-ttu-id="004c2-103">Consente di creare e gestire le connessioni e le associazioni che collegano una soluzione o un progetto salvato localmente a una cartella del database del controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="004c2-103">Creates and manages the connections and bindings that link a locally saved solution or project to a source control database folder.</span></span>  
  
## <a name="dialog-box-access"></a><span data-ttu-id="004c2-104">Accesso alla finestra di dialogo</span><span class="sxs-lookup"><span data-stu-id="004c2-104">Dialog Box Access</span></span>  
 <span data-ttu-id="004c2-105">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] selezionare un elemento in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="004c2-105">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], select an item in Solution Explorer.</span></span> <span data-ttu-id="004c2-106">Scegliere **controllo del codice sorgente**dal menu **file** , quindi **modificare il controllo del codice sorgente**.</span><span class="sxs-lookup"><span data-stu-id="004c2-106">On the **File** menu, click **Source Control**, and then **Change Source Control**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="004c2-107">Per accedere a questa finestra di dialogo, è inoltre possibile fare clic con il pulsante destro del mouse sull'elemento in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="004c2-107">This dialog box is also available by right-clicking the item in Solution Explorer.</span></span>  
  
## <a name="options"></a><span data-ttu-id="004c2-108">Opzioni</span><span class="sxs-lookup"><span data-stu-id="004c2-108">Options</span></span>  
 <span data-ttu-id="004c2-109">**Associare**</span><span class="sxs-lookup"><span data-stu-id="004c2-109">**Bind**</span></span>  
 <span data-ttu-id="004c2-110">Consente di associare gli elementi selezionati a un determinato percorso del server del controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="004c2-110">Associate selected items with a specified source control server location.</span></span> <span data-ttu-id="004c2-111">È ad esempio possibile utilizzare questo pulsante per eseguire l'associazione all'ultima cartella e all'ultimo database noti del server del controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="004c2-111">For example, you can use this button to bind to the last known source control server folder and database.</span></span> <span data-ttu-id="004c2-112">Se non è possibile individuare una cartella o un database recente del server, verrà chiesto di specificarne un altro.</span><span class="sxs-lookup"><span data-stu-id="004c2-112">If a recent server folder or database cannot be found, you are prompted to specify another.</span></span>  
  
 <span data-ttu-id="004c2-113">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="004c2-113">**Browse**</span></span>  
 <span data-ttu-id="004c2-114">Consente di selezionare un nuovo percorso del server del controllo del codice sorgente per l'elemento specificato.</span><span class="sxs-lookup"><span data-stu-id="004c2-114">Navigate to a new source control server location for the specified item.</span></span>  
  
 <span data-ttu-id="004c2-115">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="004c2-115">**Columns**</span></span>  
 <span data-ttu-id="004c2-116">Consente di identificare le colonne da visualizzare e il relativo ordine di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="004c2-116">Identify columns to display and the order in which they are displayed.</span></span>  
  
 <span data-ttu-id="004c2-117">**Connettere**</span><span class="sxs-lookup"><span data-stu-id="004c2-117">**Connect**</span></span>  
 <span data-ttu-id="004c2-118">Consente di creare una connessione tra gli elementi selezionati e il server del controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="004c2-118">Create a connection between selected items and the source control server.</span></span>  
  
 <span data-ttu-id="004c2-119">**Connessione effettuata**</span><span class="sxs-lookup"><span data-stu-id="004c2-119">**Connected**</span></span>  
 <span data-ttu-id="004c2-120">Consente di visualizzare lo stato di connessione di una soluzione o di un progetto selezionato.</span><span class="sxs-lookup"><span data-stu-id="004c2-120">Displays the connection status of a selected solution or project.</span></span>  
  
 <span data-ttu-id="004c2-121">**Disconnetti**</span><span class="sxs-lookup"><span data-stu-id="004c2-121">**Disconnect**</span></span>  
 <span data-ttu-id="004c2-122">Consente di disconnettere la copia locale di una soluzione o di un progetto archiviata nel computer dalla corrispondente copia master memorizzata nel database.</span><span class="sxs-lookup"><span data-stu-id="004c2-122">Disconnect the local copy of a solution or project on your computer from its master copy in the database.</span></span> <span data-ttu-id="004c2-123">Utilizzare questo comando prima di disconnettere il computer dal server di controllo del codice sorgente, ad esempio durante una sessione di lavoro sul portatile in modalità offline.</span><span class="sxs-lookup"><span data-stu-id="004c2-123">Use this command before disconnecting your computer from the source control server, for example, when working offline on your laptop.</span></span>  
  
 <span data-ttu-id="004c2-124">**OK**</span><span class="sxs-lookup"><span data-stu-id="004c2-124">**OK**</span></span>  
 <span data-ttu-id="004c2-125">Consente di accettare le modifiche eseguite in questa finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="004c2-125">Accept changes made in the dialog box.</span></span>  
  
 <span data-ttu-id="004c2-126">**Provider**</span><span class="sxs-lookup"><span data-stu-id="004c2-126">**Provider**</span></span>  
 <span data-ttu-id="004c2-127">Consente di visualizzare il nome del plug-in del controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="004c2-127">Displays the name of your source control plug-in.</span></span>  
  
 <span data-ttu-id="004c2-128">**Aggiorna**</span><span class="sxs-lookup"><span data-stu-id="004c2-128">**Refresh**</span></span>  
 <span data-ttu-id="004c2-129">Consente di aggiornare le informazioni sulla connessione di tutti i progetti elencati in questa finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="004c2-129">Refreshes the connection information for all projects listed in this dialog box.</span></span>  
  
 <span data-ttu-id="004c2-130">**Associazione server**</span><span class="sxs-lookup"><span data-stu-id="004c2-130">**Server Binding**</span></span>  
 <span data-ttu-id="004c2-131">Indica l'associazione dell'elemento a un server del controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="004c2-131">Indicates the item's binding to a source control server.</span></span>  
  
 <span data-ttu-id="004c2-132">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="004c2-132">**Server Name**</span></span>  
 <span data-ttu-id="004c2-133">Consente di visualizzare il nome del server del controllo del codice sorgente a cui è associato il progetto o la soluzione corrispondente.</span><span class="sxs-lookup"><span data-stu-id="004c2-133">Displays the name of the source control server to which the corresponding solution or project is bound.</span></span>  
  
 <span data-ttu-id="004c2-134">**Soluzione/Progetto**</span><span class="sxs-lookup"><span data-stu-id="004c2-134">**Solution/Project**</span></span>  
 <span data-ttu-id="004c2-135">Consente di visualizzare il nome di ogni soluzione e progetto presente nella selezione corrente.</span><span class="sxs-lookup"><span data-stu-id="004c2-135">Displays the name of each solution and project in the current selection.</span></span>  
  
 <span data-ttu-id="004c2-136">**Sort**</span><span class="sxs-lookup"><span data-stu-id="004c2-136">**Sort**</span></span>  
 <span data-ttu-id="004c2-137">Consente di eseguire l'ordinamento delle colonne visualizzate.</span><span class="sxs-lookup"><span data-stu-id="004c2-137">Sort the order of displayed columns.</span></span>  
  
 <span data-ttu-id="004c2-138">**Status**</span><span class="sxs-lookup"><span data-stu-id="004c2-138">**Status**</span></span>  
 <span data-ttu-id="004c2-139">Consente di identificare lo stato di associazione e di connessione di un elemento.</span><span class="sxs-lookup"><span data-stu-id="004c2-139">Identifies the binding and connection status of an item.</span></span> <span data-ttu-id="004c2-140">Le opzioni possibili sono:</span><span class="sxs-lookup"><span data-stu-id="004c2-140">Possible options are:</span></span>  
  
|<span data-ttu-id="004c2-141">**Opzione**</span><span class="sxs-lookup"><span data-stu-id="004c2-141">**Option**</span></span>|<span data-ttu-id="004c2-142">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="004c2-142">**Description**</span></span>|  
|----------------|---------------------|  
|<span data-ttu-id="004c2-143">Valido</span><span class="sxs-lookup"><span data-stu-id="004c2-143">Valid</span></span>|<span data-ttu-id="004c2-144">L'elemento è correttamente associato e connesso alla cartella del server di appartenenza.</span><span class="sxs-lookup"><span data-stu-id="004c2-144">The item is correctly bound and connected to the server folder to which it belongs.</span></span>|  
|<span data-ttu-id="004c2-145">Non valido</span><span class="sxs-lookup"><span data-stu-id="004c2-145">Invalid</span></span>|<span data-ttu-id="004c2-146">L'elemento è associato in modo non corretto o è disconnesso dalla cartella di appartenenza.</span><span class="sxs-lookup"><span data-stu-id="004c2-146">The item is incorrectly bound to or disconnected from the folder to which it belongs.</span></span> <span data-ttu-id="004c2-147">Usare il comando **Aggiungi al controllo del codice sorgente** anziché **associa** per questo elemento.</span><span class="sxs-lookup"><span data-stu-id="004c2-147">Use the **Add to Source Control** command instead of **Bind** for this item.</span></span>|  
|<span data-ttu-id="004c2-148">Unknown</span><span class="sxs-lookup"><span data-stu-id="004c2-148">Unknown</span></span>|<span data-ttu-id="004c2-149">Lo stato dell'elemento incluso nel controllo del codice sorgente non è ancora stato determinato.</span><span class="sxs-lookup"><span data-stu-id="004c2-149">The status of the item under source control has not yet been determined.</span></span>|  
|<span data-ttu-id="004c2-150">Non incluso nel controllo del codice sorgente</span><span class="sxs-lookup"><span data-stu-id="004c2-150">Not Controlled</span></span>|<span data-ttu-id="004c2-151">L'elemento non è inserito nel controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="004c2-151">The item has not been placed under source control.</span></span>|  
  
 <span data-ttu-id="004c2-152">**Separa**</span><span class="sxs-lookup"><span data-stu-id="004c2-152">**Unbind**</span></span>  
 <span data-ttu-id="004c2-153">Consente di visualizzare la finestra di dialogo **controllo del codice sorgente** che consente di rimuovere gli elementi selezionati dal controllo del codice sorgente e di annullare in modo definitivo gli elementi delle cartelle presenti.</span><span class="sxs-lookup"><span data-stu-id="004c2-153">Display the **Source Control** dialog box to allow you to remove selected items from source control and permanently disassociate the items from their present folders.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="004c2-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="004c2-154">See Also</span></span>  
 [<span data-ttu-id="004c2-155">Controllo del codice sorgente di Esplora soluzioni</span><span class="sxs-lookup"><span data-stu-id="004c2-155">Solution Explorer Source Control</span></span>](../../2014/database-engine/solution-explorer-source-control.md)  
  
  
