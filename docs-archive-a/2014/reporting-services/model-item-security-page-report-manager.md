---
title: Pagina sicurezza elemento modello (Gestione report) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.modelproperties.modelitemsecurity.f1
ms.assetid: 8c5b29ae-1f17-41f2-ab59-97899b8fb4fc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 928572437990c7f7fe1117c086c65c939aa9c999
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623887"
---
# <a name="model-item-security-page-report-manager"></a><span data-ttu-id="89d31-102">Pagina sicurezza elemento modello (Gestione report)</span><span class="sxs-lookup"><span data-stu-id="89d31-102">Model Item Security Page (Report Manager)</span></span>
  <span data-ttu-id="89d31-103">Questa pagina consente di proteggere parti di un modello concedendo o revocando autorizzazioni di sola lettura per elementi specifici.</span><span class="sxs-lookup"><span data-stu-id="89d31-103">Use this page to secure parts of a model by granting or revoking read-only permissions on particular items.</span></span> <span data-ttu-id="89d31-104">La sicurezza degli elementi dei modelli influisce sull'esplorazione ad hoc dei dati in fase di esecuzione e sulla possibilità di utilizzare parti di un modello pubblicato per la creazione di report in Generatore report.</span><span class="sxs-lookup"><span data-stu-id="89d31-104">Model item security affects ad hoc data exploration at run time and the ability to use parts of a published model when creating reports in Report Builder.</span></span> <span data-ttu-id="89d31-105">Per utilizzare questa caratteristica, è necessario disporre delle autorizzazioni Gestione contenuto.</span><span class="sxs-lookup"><span data-stu-id="89d31-105">To use this feature, you must have Content Manager permissions.</span></span>  
  
 <span data-ttu-id="89d31-106">La sicurezza degli elementi dei modelli si applica a un modello elaborato nel server di report e non influisce sui file con estensione smdl modificati in Progettazione modelli o utilizzati in Progettazione report.</span><span class="sxs-lookup"><span data-stu-id="89d31-106">Model item security is applied to a model that is processed on the report server and does not affect .smdl files that you edit in Model Designer or use in Report Designer.</span></span> <span data-ttu-id="89d31-107">La sicurezza degli elementi dei modelli, inoltre, non ha effetto sugli utenti che dispongono dell'autorizzazione necessaria per modificare una definizione del modello.</span><span class="sxs-lookup"><span data-stu-id="89d31-107">Furthermore, it has no effect on users who have permission to modify a model definition.</span></span> <span data-ttu-id="89d31-108">Qualsiasi utente che dispone di autorizzazioni Gestione contenuto o Pubblicazione in un modello può visualizzarne tutte le parti, indipendentemente dall'applicazione o meno della sicurezza degli elementi dei modelli.</span><span class="sxs-lookup"><span data-stu-id="89d31-108">Any user who has Content Manager or Publisher permissions on a model can see all parts of it, regardless of whether you apply model item security.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89d31-109">Gli elementi dei modelli possono essere protetti ulteriormente tramite l'utilizzo di filtri di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="89d31-109">Model items can be further secured through the use of security filters.</span></span>  
  
 <span data-ttu-id="89d31-110">È possibile definire la sicurezza degli elementi dei modelli in entità, cartelle e singoli campi all'interno di un modello.</span><span class="sxs-lookup"><span data-stu-id="89d31-110">You can define model item security on entities, folders, and individual fields within a model.</span></span> <span data-ttu-id="89d31-111">Poiché un modello include una vasta gamma di elementi a cui è possibile applicare la sicurezza, l'ereditarietà delle autorizzazioni è integrata nel modello, in modo che sia possibile proteggere un numero elevato di elementi tramite un numero relativamente ridotto di assegnazioni di ruolo.</span><span class="sxs-lookup"><span data-stu-id="89d31-111">Because a model presents such a large surface of securable items, permission inheritance is built into the model so that you can secure a large number of items through a relatively small number of role assignments.</span></span> <span data-ttu-id="89d31-112">L'ereditarietà delle autorizzazioni è basata sugli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="89d31-112">Permission inheritance is based on the following:</span></span>  
  
-   <span data-ttu-id="89d31-113">Modello</span><span class="sxs-lookup"><span data-stu-id="89d31-113">Model</span></span>  
  
-   <span data-ttu-id="89d31-114">Nodo radice</span><span class="sxs-lookup"><span data-stu-id="89d31-114">Root node</span></span>  
  
-   <span data-ttu-id="89d31-115">Cartelle o entità</span><span class="sxs-lookup"><span data-stu-id="89d31-115">Folders or entities</span></span>  
  
-   <span data-ttu-id="89d31-116">Campi</span><span class="sxs-lookup"><span data-stu-id="89d31-116">Fields</span></span>  
  
 <span data-ttu-id="89d31-117">Inizialmente, l'autorizzazione di accesso agli elementi del modello viene ereditata tramite le assegnazioni di ruolo impostate nel modello stesso.</span><span class="sxs-lookup"><span data-stu-id="89d31-117">Initially, permission to access to model items is inherited through role assignments that are set on the model itself.</span></span> <span data-ttu-id="89d31-118">Un utente che dispone dell'autorizzazione per visualizzare un modello in una cartella in Gestione report può visualizzare tutti gli elementi del modello.</span><span class="sxs-lookup"><span data-stu-id="89d31-118">A user who has permission to view a model in a folder in Report Manager can view all of the items in the model.</span></span>  
  
 <span data-ttu-id="89d31-119">Se si applica la sicurezza degli elementi dei modelli, è necessario creare almeno un'assegnazione di ruolo nel nodo radice.</span><span class="sxs-lookup"><span data-stu-id="89d31-119">If you apply model item security, you must create at least one role assignment on the root node.</span></span> <span data-ttu-id="89d31-120">Questa assegnazione di ruolo iniziale nel nodo radice diventa la nuova origine di autorizzazioni ereditate.</span><span class="sxs-lookup"><span data-stu-id="89d31-120">This initial role assignment on the root node becomes the new source of inherited permissions.</span></span> <span data-ttu-id="89d31-121">L'assegnazione di ruolo nel nodo radice viene ereditata automaticamente da tutti gli elementi nella gerarchia del modello.</span><span class="sxs-lookup"><span data-stu-id="89d31-121">The role assignment on the root node is automatically inherited by all items in the model hierarchy.</span></span>  
  
 <span data-ttu-id="89d31-122">Per personalizzare ulteriormente le autorizzazioni per l'esplorazione dei dati, è possibile impostare autorizzazioni diverse in cartelle ed entità.</span><span class="sxs-lookup"><span data-stu-id="89d31-122">To further customize permissions on data exploration, you can vary permissions on folders and entities.</span></span> <span data-ttu-id="89d31-123">È infine possibile impostare autorizzazioni nei singoli campi.</span><span class="sxs-lookup"><span data-stu-id="89d31-123">Finally, you can set permissions on individual fields.</span></span>  
  
 <span data-ttu-id="89d31-124">Per semplificare la gestione delle assegnazioni di ruolo, impostare le autorizzazioni solo nelle cartelle o nelle entità anziché in singoli campi.</span><span class="sxs-lookup"><span data-stu-id="89d31-124">To make role assignments easier to maintain, set permissions only on folders or entities rather than individual fields.</span></span> <span data-ttu-id="89d31-125">Non è possibile cercare le assegnazioni di ruolo create.</span><span class="sxs-lookup"><span data-stu-id="89d31-125">You cannot search for role assignments that you create.</span></span> <span data-ttu-id="89d31-126">Se si imposta la sicurezza in campi specifici e successivamente si desidera aggiornarne le impostazioni, è necessario esplorare lo spazio dei nomi del modello per individuare i campi per i quali è stata configurata la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="89d31-126">If you set security on specific fields and you want to update the security settings later, you must click through the model namespace to find the fields you secured.</span></span>  
  
 <span data-ttu-id="89d31-127">Iniziare creando un'assegnazione di ruolo nel nodo radice, quindi creare assegnazioni di ruolo aggiuntive in entità e cartelle.</span><span class="sxs-lookup"><span data-stu-id="89d31-127">To get started, create a role assignment on the root node and then create additional role assignments on entities and folders.</span></span> <span data-ttu-id="89d31-128">Per annullare la sicurezza degli elementi del modello, deselezionare la casella di controllo **sicurezza indipendente dei singoli elementi del modello**.</span><span class="sxs-lookup"><span data-stu-id="89d31-128">To clear model item security, clear the check box for **Secure individual model items independently for this model**.</span></span> <span data-ttu-id="89d31-129">Se si deseleziona questa casella di controllo, vengono ripristinate le autorizzazioni iniziali ereditate dal modello.</span><span class="sxs-lookup"><span data-stu-id="89d31-129">Clearing the check box reverts back to the initial permissions that are inherited from the model.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="89d31-130">Spostamento</span><span class="sxs-lookup"><span data-stu-id="89d31-130">Navigation</span></span>  
 <span data-ttu-id="89d31-131">Utilizzare la procedura riportata di seguito per navigare fino a questo percorso nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="89d31-131">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-general-properties-page-for-a-report"></a><span data-ttu-id="89d31-132">Per aprire la pagina delle proprietà Generale per un report</span><span class="sxs-lookup"><span data-stu-id="89d31-132">To open the General properties page for a report</span></span>  
  
1.  <span data-ttu-id="89d31-133">Aprire Gestione report, quindi individuare il modello per il quale si desidera configurare la sicurezza per gli elementi del modello.</span><span class="sxs-lookup"><span data-stu-id="89d31-133">Open Report Manager, and locate the model for which you want to configure security for model items.</span></span>  
  
2.  <span data-ttu-id="89d31-134">Passare con il puntatore del mouse sul modello, quindi fare clic sulla freccia a discesa.</span><span class="sxs-lookup"><span data-stu-id="89d31-134">Hover over the model, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="89d31-135">Scegliere **Gestisci**dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="89d31-135">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="89d31-136">Verrà visualizzata la pagina delle proprietà Generale per il modello.</span><span class="sxs-lookup"><span data-stu-id="89d31-136">This opens the General properties page for the model.</span></span>  
  
4.  <span data-ttu-id="89d31-137">Selezionare la scheda **Sicurezza elemento modello** .</span><span class="sxs-lookup"><span data-stu-id="89d31-137">Select the **Model Item Security** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="89d31-138">Opzioni</span><span class="sxs-lookup"><span data-stu-id="89d31-138">Options</span></span>  
 <span data-ttu-id="89d31-139">**sicurezza indipendente dei singoli elementi del modello**</span><span class="sxs-lookup"><span data-stu-id="89d31-139">**Secure individual model items independently for this model**</span></span>  
 <span data-ttu-id="89d31-140">Selezionare questa casella di controllo per attivare la sicurezza a livello di elemento del modello.</span><span class="sxs-lookup"><span data-stu-id="89d31-140">Click this check box to enable model item security.</span></span>  
  
 <span data-ttu-id="89d31-141">**Specificare le impostazioni di sicurezza per singoli elementi del modello**</span><span class="sxs-lookup"><span data-stu-id="89d31-141">**Specify security for individual model items in the mode**</span></span>  
 <span data-ttu-id="89d31-142">Visualizza tutti gli elementi inclusi in un modello.</span><span class="sxs-lookup"><span data-stu-id="89d31-142">Shows all of the items in a model.</span></span> <span data-ttu-id="89d31-143">È possibile spostarsi nello spazio dei nomi del modello per selezionare l'elemento per il quale si desidera impostare la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="89d31-143">You can navigate the model namespace to select the item you want to secure.</span></span> <span data-ttu-id="89d31-144">È possibile selezionare un solo elemento per volta.</span><span class="sxs-lookup"><span data-stu-id="89d31-144">You can only select one item at a time.</span></span> <span data-ttu-id="89d31-145">Assicurarsi di creare la prima assegnazione di ruolo nel nodo radice prima di passare alle altre entità e cartelle.</span><span class="sxs-lookup"><span data-stu-id="89d31-145">Be sure to create the first role assignment on the root node before proceeding to other entities and folders.</span></span>  
  
 <span data-ttu-id="89d31-146">**Eredita autorizzazioni dall'elemento padre**</span><span class="sxs-lookup"><span data-stu-id="89d31-146">**Inherit permissions from the parent item**</span></span>  
 <span data-ttu-id="89d31-147">Selezionare questa opzione per ereditare le impostazioni di sicurezza dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="89d31-147">Click this option to inherit the security settings of the parent item.</span></span>  
  
 <span data-ttu-id="89d31-148">**Assegna autorizzazione di lettura ai seguenti utenti e gruppi (separati da un punto e virgola)**</span><span class="sxs-lookup"><span data-stu-id="89d31-148">**Assign read permission to the following users and groups (semi-colon separated)**</span></span>  
 <span data-ttu-id="89d31-149">Selezionare questa opzione per impostare l'account utente o di gruppo per il quale viene stabilito l'accesso.</span><span class="sxs-lookup"><span data-stu-id="89d31-149">Click this option to specify the user or group account for which you are defining access.</span></span> <span data-ttu-id="89d31-150">Se si utilizza la sicurezza predefinita, gli account utente o di gruppo corrispondono agli account di dominio di Windows.</span><span class="sxs-lookup"><span data-stu-id="89d31-150">If you are using default security, the user and group accounts are Windows domain accounts.</span></span> <span data-ttu-id="89d31-151">Specificare gli account nel formato: \* \<domain> \\<account \> \*.</span><span class="sxs-lookup"><span data-stu-id="89d31-151">Specify the accounts in this format: *\<domain>\\<account\>*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89d31-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89d31-152">See Also</span></span>  
 [<span data-ttu-id="89d31-153">Guida sensibile al contesto del server di report in Management Studio</span><span class="sxs-lookup"><span data-stu-id="89d31-153">Report Server in Management Studio F1 Help</span></span>](tools/report-server-in-management-studio-f1-help.md)  
  
  
