---
title: Pagina delle proprietà generale, cartelle (Gestione report) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 31d99d9b-2303-4bae-9466-fb67b97cf11a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fb1c3fbf2e9020ac5d1fe5ebbd1e9ed48b45adb9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637103"
---
# <a name="general-properties-page-folders-report-manager"></a><span data-ttu-id="746d5-102">Pagina delle proprietà Generale, Cartelle (Gestione report)</span><span class="sxs-lookup"><span data-stu-id="746d5-102">General Properties Page, Folders (Report Manager)</span></span>
  <span data-ttu-id="746d5-103">La pagina delle proprietà Generale per le cartelle consente di visualizzare e impostare le proprietà per le cartelle create.</span><span class="sxs-lookup"><span data-stu-id="746d5-103">Use the General properties page for folders to view and set properties for the folders that you create.</span></span> <span data-ttu-id="746d5-104">Nella pagina delle proprietà Generale vengono visualizzati il nome dell'utente che ha creato o modificato la cartella e la data e ora di creazione o modifica.</span><span class="sxs-lookup"><span data-stu-id="746d5-104">Information about who created or modified the folder and when the folder was modified appear at the top of the General properties page.</span></span>  
  
 <span data-ttu-id="746d5-105">Le proprietà delle cartelle includono inoltre le impostazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="746d5-105">Folder properties also include security settings.</span></span> <span data-ttu-id="746d5-106">Per ulteriori informazioni sulla sicurezza delle cartelle, vedere [proteggere le cartelle](security/secure-folders.md).</span><span class="sxs-lookup"><span data-stu-id="746d5-106">For more information about folder security, see [Secure Folders](security/secure-folders.md).</span></span>  
  
 <span data-ttu-id="746d5-107">Le cartelle speciali, ad esempio Home, Report personali e Cartelle utenti, non possono essere rinominate o spostate nello spazio dei nomi del server di report.</span><span class="sxs-lookup"><span data-stu-id="746d5-107">Special-purpose folders such as Home, My Reports, and Users folders cannot be renamed or moved within the report server namespace.</span></span> <span data-ttu-id="746d5-108">Per queste cartelle non è disponibile la pagina delle proprietà Generale.</span><span class="sxs-lookup"><span data-stu-id="746d5-108">The General properties page is not available for these folders.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="746d5-109">Spostamento</span><span class="sxs-lookup"><span data-stu-id="746d5-109">Navigation</span></span>  
 <span data-ttu-id="746d5-110">Utilizzare la procedura riportata di seguito per navigare fino a questo percorso nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="746d5-110">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-general-properties-page-for-a-folder"></a><span data-ttu-id="746d5-111">Per aprire la pagina delle proprietà Generale per una cartella</span><span class="sxs-lookup"><span data-stu-id="746d5-111">To open the General properties page for a folder</span></span>  
  
1.  <span data-ttu-id="746d5-112">Aprire Gestione report, quindi aprire la cartella per la quale si desidera visualizzare o configurare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="746d5-112">Open Report Manager, and open the folder for which you want to view or configure properties.</span></span>  
  
2.  <span data-ttu-id="746d5-113">Nell'intestazione della cartella, nella barra degli strumenti, fare clic su **Impostazioni cartella**.</span><span class="sxs-lookup"><span data-stu-id="746d5-113">Under the folder banner, in the toolbar, click **Folder Settings**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="746d5-114">Opzioni</span><span class="sxs-lookup"><span data-stu-id="746d5-114">Options</span></span>  
 <span data-ttu-id="746d5-115">**Nome**</span><span class="sxs-lookup"><span data-stu-id="746d5-115">**Name**</span></span>  
 <span data-ttu-id="746d5-116">Digitare un nome per la cartella.</span><span class="sxs-lookup"><span data-stu-id="746d5-116">Specify a name for the folder.</span></span> <span data-ttu-id="746d5-117">Il nome deve includere almeno un carattere alfanumerico.</span><span class="sxs-lookup"><span data-stu-id="746d5-117">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="746d5-118">È inoltre possibile utilizzare spazi e alcuni simboli.</span><span class="sxs-lookup"><span data-stu-id="746d5-118">It can also include spaces and some symbols.</span></span> <span data-ttu-id="746d5-119">Non utilizzare i caratteri ; ?</span><span class="sxs-lookup"><span data-stu-id="746d5-119">Do not use the characters ; ?</span></span> <span data-ttu-id="746d5-120">: \@ & = +, $ \* \< > | "o/quando si specifica un nome.</span><span class="sxs-lookup"><span data-stu-id="746d5-120">: \@ & = + , $ \* \< > | " or / when specifying a name.</span></span>  
  
 <span data-ttu-id="746d5-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="746d5-121">**Description**</span></span>  
 <span data-ttu-id="746d5-122">Consente di digitare una descrizione del contenuto della cartella.</span><span class="sxs-lookup"><span data-stu-id="746d5-122">Type a description of the folder contents.</span></span> <span data-ttu-id="746d5-123">Questa descrizione viene visualizzata nella pagina Contenuto per gli utenti autorizzati ad accedere alla cartella.</span><span class="sxs-lookup"><span data-stu-id="746d5-123">This description appears on the Contents page for users who have permission to access the folder.</span></span>  
  
 <span data-ttu-id="746d5-124">**Nascondi in visualizzazione Elenco**</span><span class="sxs-lookup"><span data-stu-id="746d5-124">**Hide in list view**</span></span>  
 <span data-ttu-id="746d5-125">Selezionare questa opzione per fare in modo che la cartella non venga visualizzata per gli utenti che utilizzano la modalità di visualizzazione Elenco in Gestione report.</span><span class="sxs-lookup"><span data-stu-id="746d5-125">Select this option to hide the folder from users who are using list view mode in Report Manager.</span></span> <span data-ttu-id="746d5-126">La modalità di visualizzazione Elenco è il formato di visualizzazione predefinito utilizzato per l'esplorazione della gerarchia di cartelle del server di report.</span><span class="sxs-lookup"><span data-stu-id="746d5-126">List view mode is the default view format when browsing the report server folder hierarchy.</span></span> <span data-ttu-id="746d5-127">Nella visualizzazione Elenco i nomi e le descrizioni degli elementi vengono disposti dall'alto in basso nella pagina.</span><span class="sxs-lookup"><span data-stu-id="746d5-127">In list view, item names and descriptions flow across the page.</span></span> <span data-ttu-id="746d5-128">Il formato alternativo è costituito dalla visualizzazione Dettagli,</span><span class="sxs-lookup"><span data-stu-id="746d5-128">The alternate format is details view.</span></span> <span data-ttu-id="746d5-129">in cui non sono incluse le descrizioni ma sono disponibili altre informazioni sugli elementi.</span><span class="sxs-lookup"><span data-stu-id="746d5-129">Details view omits descriptions, but includes other information about the item.</span></span> <span data-ttu-id="746d5-130">Gli elementi possono essere nascosti nella visualizzazione Elenco ma non nella visualizzazione Dettagli.</span><span class="sxs-lookup"><span data-stu-id="746d5-130">Although you can hide an item in list view, you cannot hide an item in details view.</span></span> <span data-ttu-id="746d5-131">Se si desidera limitare l'accesso a un elemento, è necessario creare un'assegnazione di ruolo.</span><span class="sxs-lookup"><span data-stu-id="746d5-131">If you want to restrict access to an item, you must create a role assignment.</span></span>  
  
 <span data-ttu-id="746d5-132">**Applica**</span><span class="sxs-lookup"><span data-stu-id="746d5-132">**Apply**</span></span>  
 <span data-ttu-id="746d5-133">Fare clic per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="746d5-133">Click to save your changes.</span></span>  
  
 <span data-ttu-id="746d5-134">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="746d5-134">**Delete**</span></span>  
 <span data-ttu-id="746d5-135">Fare clic per rimuovere la cartella e il relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="746d5-135">Click to remove the folder and its contents.</span></span>  
  
 <span data-ttu-id="746d5-136">**Spostamento**</span><span class="sxs-lookup"><span data-stu-id="746d5-136">**Move**</span></span>  
 <span data-ttu-id="746d5-137">Fare clic per spostare un report o una cartella all'interno dello spazio dei nomi del server di report.</span><span class="sxs-lookup"><span data-stu-id="746d5-137">Click to relocate a report or folder within the report server namespace.</span></span> <span data-ttu-id="746d5-138">Verrà visualizzata la pagina di spostamento degli elementi, che consente di esplorare le cartelle per selezionare un nuovo percorso.</span><span class="sxs-lookup"><span data-stu-id="746d5-138">Clicking this button opens the Move Items page that allows you to browse folders for a new folder location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="746d5-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="746d5-139">See Also</span></span>  
 <span data-ttu-id="746d5-140">[Gestione report &#40;modalità nativa SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="746d5-140">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="746d5-141">Guida sensibile al contesto di Gestione report</span><span class="sxs-lookup"><span data-stu-id="746d5-141">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
