---
title: Creare, eliminare o modificare una cartella (Gestione report) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- removing folders
- modifying folders
- deleting folders
- folders [Reporting Services], creating
- folders [Reporting Services], deleting
- folders [Reporting Services], modifying
ms.assetid: d62159a8-ec67-4e28-a9f1-05a9250065bb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9bd7d5ceebdb7b3a48ded66ed108bddda25d8a46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630291"
---
# <a name="create-delete-or-modify-a-folder-report-manager"></a><span data-ttu-id="6c083-102">Creare, eliminare o modificare una cartella (Gestione report)</span><span class="sxs-lookup"><span data-stu-id="6c083-102">Create, Delete, or Modify a Folder (Report Manager)</span></span>
  <span data-ttu-id="6c083-103">È possibile creare cartelle per organizzare e gestire gli elementi pubblicati in un server di report.</span><span class="sxs-lookup"><span data-stu-id="6c083-103">You can create folders to organize and manage the items you publish to a report server.</span></span> <span data-ttu-id="6c083-104">La creazione di cartelle consente agli utenti di individuare in modo semplice i report desiderati.</span><span class="sxs-lookup"><span data-stu-id="6c083-104">Creating folders can help users find reports of interest to them.</span></span> <span data-ttu-id="6c083-105">Per gli utenti con ruolo di gestione del contenuto, le cartelle costituiscono una struttura per l'applicazione di autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="6c083-105">For content managers, folders provide a framework for applying permissions.</span></span> <span data-ttu-id="6c083-106">È possibile creare assegnazioni di ruolo su cartelle specifiche per limitare l'accesso a report in fase di sviluppo o che non devono essere distribuiti su larga scala.</span><span class="sxs-lookup"><span data-stu-id="6c083-106">You can create role assignments on specific folders to restrict access to reports that are in development or that should not be widely distributed.</span></span>  
  
### <a name="to-create-a-folder"></a><span data-ttu-id="6c083-107">Per creare una cartella</span><span class="sxs-lookup"><span data-stu-id="6c083-107">To create a folder</span></span>  
  
1.  <span data-ttu-id="6c083-108">Avviare [Gestione report &#40;modalità nativa SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="6c083-108">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="6c083-109">In Gestione report selezionare la cartella Home e fare clic su **Nuova cartella**.</span><span class="sxs-lookup"><span data-stu-id="6c083-109">In Report Manager, select the Home folder and click **New Folder**.</span></span> <span data-ttu-id="6c083-110">In alternativa, per creare una cartella all'interno di una cartella esistente, passare alla cartella nella pagina **Contenuto** e fare clic sulla cartella per aprirla.</span><span class="sxs-lookup"><span data-stu-id="6c083-110">Or, to create a folder under an existing folder, navigate to that folder in the **Contents** page and click the folder to open it.</span></span> <span data-ttu-id="6c083-111">Fare clic su **Nuova cartella**.</span><span class="sxs-lookup"><span data-stu-id="6c083-111">Then click **New Folder**.</span></span>  
  
     <span data-ttu-id="6c083-112">Verrà visualizzata la pagina **Nuova cartella** .</span><span class="sxs-lookup"><span data-stu-id="6c083-112">The **New Folder** page opens.</span></span>  
  
3.  <span data-ttu-id="6c083-113">Digitare il nome della cartella.</span><span class="sxs-lookup"><span data-stu-id="6c083-113">Type a folder name.</span></span> <span data-ttu-id="6c083-114">I nomi di cartella possono includere spazi, ma non caratteri riservati utilizzati per la codifica degli URL, ad esempio ; ?</span><span class="sxs-lookup"><span data-stu-id="6c083-114">A folder name can include spaces, but cannot include reserved characters that are used for URL encoding: ; ?</span></span> <span data-ttu-id="6c083-115">: \@ & = +, $/\* \< > |.</span><span class="sxs-lookup"><span data-stu-id="6c083-115">: \@ & = + , $ / \* \< > |.</span></span> <span data-ttu-id="6c083-116">Non è possibile digitare una serie di nomi di cartella per creare più cartelle contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="6c083-116">You cannot type a series of folder names to create several folders at once.</span></span>  
  
4.  <span data-ttu-id="6c083-117">Se lo si desidera, digitare una descrizione.</span><span class="sxs-lookup"><span data-stu-id="6c083-117">Optionally type a description.</span></span>  
  
5.  <span data-ttu-id="6c083-118">Selezionare **Nascondi in visualizzazione Elenco** se non si vuole visualizzare la cartella nella visualizzazione predefinita della pagina **Contenuto** .</span><span class="sxs-lookup"><span data-stu-id="6c083-118">Select **Hide in list view** if you do not want to display the folder in the default view of the **Contents** page.</span></span> <span data-ttu-id="6c083-119">La cartella sarà visibile agli utenti solo dopo aver fatto clic su **Mostra dettagli** nella pagina **Contenuto** .</span><span class="sxs-lookup"><span data-stu-id="6c083-119">The folder will be visible to users only when they click **Show Details** on the **Contents** page.</span></span>  
  
6.  <span data-ttu-id="6c083-120">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6c083-120">Click **OK**.</span></span>  
  
### <a name="to-delete-a-folder"></a><span data-ttu-id="6c083-121">Per eliminare una cartella</span><span class="sxs-lookup"><span data-stu-id="6c083-121">To delete a folder</span></span>  
  
1.  <span data-ttu-id="6c083-122">In Gestione report passare alla pagina **Contenuto** e individuare l'elemento che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="6c083-122">In Report Manager, navigate to the **Contents** page, and locate the item that you want to modify.</span></span>  
  
2.  <span data-ttu-id="6c083-123">Posizionare il puntatore del mouse sull'elemento, quindi fare clic sulla freccia a discesa.</span><span class="sxs-lookup"><span data-stu-id="6c083-123">Hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="6c083-124">Scegliere **Elimina**dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="6c083-124">In the drop-down menu, click **Delete**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-modify-or-delete-a-folder"></a><span data-ttu-id="6c083-125">Per modificare o eliminare una cartella</span><span class="sxs-lookup"><span data-stu-id="6c083-125">To modify or delete a folder</span></span>  
  
1.  <span data-ttu-id="6c083-126">In Gestione report passare alla pagina **Contenuto** e individuare l'elemento che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="6c083-126">In Report Manager, navigate to the **Contents** page, and locate the item that you want to modify.</span></span>  
  
2.  <span data-ttu-id="6c083-127">Posizionare il puntatore del mouse sull'elemento, quindi fare clic sulla freccia a discesa.</span><span class="sxs-lookup"><span data-stu-id="6c083-127">Hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="6c083-128">Scegliere **Gestisci**dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="6c083-128">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="6c083-129">Verrà visualizzata la pagina Proprietà generali.</span><span class="sxs-lookup"><span data-stu-id="6c083-129">The General Properties page opens.</span></span>  
  
4.  <span data-ttu-id="6c083-130">Per modificare il percorso della cartella, fare clic su **Sposta**.</span><span class="sxs-lookup"><span data-stu-id="6c083-130">To change the folder location, click **Move**.</span></span> <span data-ttu-id="6c083-131">Digitare il percorso della cartella di destinazione oppure scegliere la cartella di destinazione nell'albero e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6c083-131">Type the location of the destination folder, or choose the destination folder from the tree, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="6c083-132">In alternativa, modificare le proprietà della cartella nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="6c083-132">Or, modify folder properties in the following ways:</span></span>  
  
    -   <span data-ttu-id="6c083-133">Per modificare il testo da visualizzare per la cartella, digitare un nome o una descrizione.</span><span class="sxs-lookup"><span data-stu-id="6c083-133">To modify display text about the folder, type a name or description.</span></span>  
  
    -   <span data-ttu-id="6c083-134">Per visualizzare la cartella nella visualizzazione predefinita nella pagina **Contenuto** , deselezionare **Nascondi in visualizzazione Elenco**.</span><span class="sxs-lookup"><span data-stu-id="6c083-134">To display the folder in the default view on the **Contents** page, clear **Hide in list view**.</span></span>  
  
6.  <span data-ttu-id="6c083-135">In alternativa, per rimuovere la cartella e il suo contenuto, fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="6c083-135">Or, to remove the folder and its contents, click **Delete**.</span></span>  
  
7.  <span data-ttu-id="6c083-136">Fare clic su **Applica** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="6c083-136">Click **Apply** to save changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c083-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c083-137">See Also</span></span>  
 <span data-ttu-id="6c083-138">[Pagina nuova cartella &#40;Gestione report&#41;](../new-folder-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="6c083-138">[New Folder Page &#40;Report Manager&#41;](../new-folder-page-report-manager.md) </span></span>  
 <span data-ttu-id="6c083-139">[Pagina contenuti &#40;Gestione report&#41;](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="6c083-139">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 [<span data-ttu-id="6c083-140">Ricerca, visualizzazione e gestione dei report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="6c083-140">Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;</span></span>](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md)  
  
  
