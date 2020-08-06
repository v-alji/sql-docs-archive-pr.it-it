---
title: Impostare le autorizzazioni per gli elementi del server di report in un sito di SharePoint (Reporting Services in modalità integrata SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- permissions [Reporting Services], SharePoint integrated mode
- SharePoint integration [Reporting Services], permissions
ms.assetid: 2467c657-a3bf-4ec3-a88c-8877df19823d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f38497843ca99342f13952153d7fed957564e006
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713759"
---
# <a name="set-permissions-for-report-server-items-on-a-sharepoint-site-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="8583a-102">Impostare autorizzazioni per gli elementi del server di report in un sito di SharePoint (Reporting Services in modalità integrata SharePoint)</span><span class="sxs-lookup"><span data-stu-id="8583a-102">Set Permissions for Report Server Items on a SharePoint Site (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="8583a-103">Se le impostazioni di sicurezza predefinite non garantiscono il livello di accesso desiderato, sarà possibile creare nuovi livelli di autorizzazione per fornire l'accesso a operazioni o elementi specifici del server di report.</span><span class="sxs-lookup"><span data-stu-id="8583a-103">If default security settings do not provide the level of access that you require, you can create new permission levels to provide access to specific report server items or operations.</span></span> <span data-ttu-id="8583a-104">Le impostazioni di sicurezza personalizzate possono risultare utili se si desidera limitare l'accesso a un particolare report.</span><span class="sxs-lookup"><span data-stu-id="8583a-104">Custom security settings can be useful if you want to restrict access to a particular report.</span></span>  
  
 <span data-ttu-id="8583a-105">Per creare gruppi e livelli di autorizzazione, è necessario essere proprietari del sito.</span><span class="sxs-lookup"><span data-stu-id="8583a-105">You must be a site owner to create permission levels and groups.</span></span> <span data-ttu-id="8583a-106">I livelli di autorizzazione vengono utilizzati a livello globale nell'intero sito.</span><span class="sxs-lookup"><span data-stu-id="8583a-106">Permission levels are used globally throughout a site.</span></span> <span data-ttu-id="8583a-107">Se si crea un nuovo livello di autorizzazione, questo sarà disponibile ad altri proprietari del sito.</span><span class="sxs-lookup"><span data-stu-id="8583a-107">If you create a new permission level, it will be available to other site owners.</span></span>  
  
 <span data-ttu-id="8583a-108">La maggior parte delle autorizzazioni viene ereditata da un sito padre.</span><span class="sxs-lookup"><span data-stu-id="8583a-108">Most permissions are inherited from a parent site.</span></span> <span data-ttu-id="8583a-109">Se si assegnano autorizzazioni per una raccolta o un elemento specifico, si disattiva l'ereditarietà delle autorizzazioni e sarà necessario eseguire operazioni aggiuntive per la gestione delle autorizzazioni relative al ramo specifico della gerarchia di siti.</span><span class="sxs-lookup"><span data-stu-id="8583a-109">If you assign permissions on a specific library or item, you break permission inheritance and incur additional overhead in how manage permissions for that branch of your site hierarchy.</span></span>  
  
 <span data-ttu-id="8583a-110">Le autorizzazioni possono essere impostate per i file di definizione dei report (con estensione rdl), dei modelli (con estensione smdl) e delle origini dati condivise (con estensione rsds).</span><span class="sxs-lookup"><span data-stu-id="8583a-110">You can set permissions on report definition (.rdl), model (.smdl), and shared data source (.rsds) files.</span></span> <span data-ttu-id="8583a-111">Non è possibile utilizzare una combinazione di autorizzazioni ereditate e gestite per lo stesso elemento.</span><span class="sxs-lookup"><span data-stu-id="8583a-111">You cannot combine inherited and managed permissions on the same item.</span></span> <span data-ttu-id="8583a-112">Se si sceglie di gestire le autorizzazioni direttamente, le autorizzazioni ereditate non avranno effetto sull'elemento corrente.</span><span class="sxs-lookup"><span data-stu-id="8583a-112">If you choose to manage permissions directly, inherited permissions will have no effect on the current item.</span></span> <span data-ttu-id="8583a-113">Se in seguito si desidera riattivare l'ereditarietà delle autorizzazioni, è possibile selezionare **Eredita autorizzazioni** dal menu **Azioni** .</span><span class="sxs-lookup"><span data-stu-id="8583a-113">If you want to resume permission inheritance later, you can select **Inherit Permissions** on the **Actions** menu.</span></span>  
  
 <span data-ttu-id="8583a-114">Per impostare autorizzazioni per entità e prospettive in un modello, è necessario disporre del livello di autorizzazione Controllo completo per il modello.</span><span class="sxs-lookup"><span data-stu-id="8583a-114">To set permissions on entities and perspectives in a model, you must have Full Control level of permission for the model.</span></span> <span data-ttu-id="8583a-115">Controllo completo include "Gestione autorizzazioni", ovvero l'autorizzazione a livello di sito concessa ai proprietari e ai gruppi di SharePoint che dispongono dell'autorizzazione Controllo completo.</span><span class="sxs-lookup"><span data-stu-id="8583a-115">Full Control includes "Manage Permissions", which is a site level permission that is granted to site owners and other SharePoint groups who have Full Control level of permission.</span></span> <span data-ttu-id="8583a-116">Se si desidera offrire a utenti specifici la possibilità di impostare la sicurezza per gli elementi del modello, sarà necessario disattivare l'ereditarietà delle autorizzazioni e concedere autorizzazioni elevate (ad esempio Controllo completo) all'utente o al gruppo per il file del modello.</span><span class="sxs-lookup"><span data-stu-id="8583a-116">If you want to offer specific users the ability to set model item security, you must break permission inheritance and grant elevated permissions (such as Full Control) to the user or group on the model file.</span></span> <span data-ttu-id="8583a-117">Quando si concede il livello di autorizzazione Controllo completo per un elemento, ad esempio un file nella raccolta, l'ambito delle autorizzazioni sarà limitato a tale elemento e non si estenderà all'elemento padre o ad altri elementi nella stessa raccolta.</span><span class="sxs-lookup"><span data-stu-id="8583a-117">When you grant Full Control on an item such as a file in the library, the permissions are scoped to that item and do not extend to the parent or to other items within the same library.</span></span> <span data-ttu-id="8583a-118">Gli utenti che dispongono dell'autorizzazione Gestione autorizzazioni per il modello possono impostare la sicurezza degli elementi del modello tramite il sito di SharePoint o Progettazione modelli.</span><span class="sxs-lookup"><span data-stu-id="8583a-118">After the user has Manage Permissions permission on the model, he or she can use set model item security via the SharePoint site or Model Designer.</span></span>  
  
### <a name="to-set-permissions-on-an-individual-report-model-or-data-source"></a><span data-ttu-id="8583a-119">Per impostare le autorizzazioni per un singolo report, modello o origine dei dati</span><span class="sxs-lookup"><span data-stu-id="8583a-119">To set permissions on an individual report, model, or data source</span></span>  
  
1.  <span data-ttu-id="8583a-120">Se la raccolta non è aperta, fare clic sul nome della raccolta sulla barra di avvio veloce.</span><span class="sxs-lookup"><span data-stu-id="8583a-120">If the library is not already open, click its name on the Quick Launch.</span></span> <span data-ttu-id="8583a-121">Se il nome della raccolta non è visualizzato, fare clic su **Visualizza tutto il contenuto del sito**e quindi sul nome della raccolta desiderata.</span><span class="sxs-lookup"><span data-stu-id="8583a-121">If the name of your library does not appear, click **View All Site Content**, and then click the name of your library.</span></span>  
  
2.  <span data-ttu-id="8583a-122">Selezionare il file del report, del modello di report o dell'origine dati condivisa.</span><span class="sxs-lookup"><span data-stu-id="8583a-122">Point to the report, report model, or shared data source file.</span></span>  
  
3.  <span data-ttu-id="8583a-123">Fare clic sulla freccia verso il basso e scegliere **Gestisci autorizzazioni**dal menu.</span><span class="sxs-lookup"><span data-stu-id="8583a-123">Click the down arrow, and on the menu, click **Manage Permissions**.</span></span>  
  
4.  <span data-ttu-id="8583a-124">Scegliere **Modifica autorizzazioni** dal menu **Azioni**, quindi fare clic su **OK** per confermare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="8583a-124">On the **Actions** menu, click **Edit Permissions**, and then click **OK** to confirm the action.</span></span>  
  
5.  <span data-ttu-id="8583a-125">Per assegnare autorizzazioni a un utente o a un gruppo che non dispone ancora di autorizzazioni per l'utilizzo del file, fare clic su **Nuovo**e quindi su **Aggiungi utenti**.</span><span class="sxs-lookup"><span data-stu-id="8583a-125">To give permissions to a user or group that does not yet have permissions to use the file, click **New**, and then click **Add Users**.</span></span>  
  
6.  <span data-ttu-id="8583a-126">Per rimuovere o modificare le autorizzazioni per un utente o un gruppo esistente, selezionare la casella di controllo accanto al nome dell'utente o del gruppo, quindi scegliere **Rimuovi autorizzazioni utente**o **Modifica autorizzazioni utente** dal menu **Azioni**.</span><span class="sxs-lookup"><span data-stu-id="8583a-126">To remove or modify permissions for an existing user or group, click the check box next to the user or group, click **Actions**, and then click **Remove User Permissions** or **Edit User Permissions**.</span></span>  
  
### <a name="to-set-permissions-that-enable-model-item-security"></a><span data-ttu-id="8583a-127">Per impostare le autorizzazioni che consentono la sicurezza degli elementi del modello</span><span class="sxs-lookup"><span data-stu-id="8583a-127">To set permissions that enable model item security</span></span>  
  
1.  <span data-ttu-id="8583a-128">Accedere al sito di SharePoint utilizzando un account dotato di autorizzazione Gestione autorizzazioni per il sito.</span><span class="sxs-lookup"><span data-stu-id="8583a-128">Log in to the SharePoint site using an account that has Manage Permissions permission on the site.</span></span>  
  
2.  <span data-ttu-id="8583a-129">Aprire la raccolta che contiene il modello.</span><span class="sxs-lookup"><span data-stu-id="8583a-129">Open the library that contains the model.</span></span>  
  
3.  <span data-ttu-id="8583a-130">Selezionare il modello.</span><span class="sxs-lookup"><span data-stu-id="8583a-130">Point to the model.</span></span>  
  
4.  <span data-ttu-id="8583a-131">Fare clic sulla freccia verso il basso accanto al modello, quindi selezionare **Gestisci autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="8583a-131">Click the down arrow next to the model, and click **Manage Permissions**.</span></span>  
  
5.  <span data-ttu-id="8583a-132">Fare clic su **Azioni**.</span><span class="sxs-lookup"><span data-stu-id="8583a-132">Click **Actions**.</span></span>  
  
6.  <span data-ttu-id="8583a-133">Fare clic su **Modifica autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="8583a-133">Click **Edit Permissions**.</span></span> <span data-ttu-id="8583a-134">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8583a-134">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="8583a-135">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8583a-135">Click **New**.</span></span>  
  
8.  <span data-ttu-id="8583a-136">Fare clic su **Aggiungi utenti**.</span><span class="sxs-lookup"><span data-stu-id="8583a-136">Click **Add Users**.</span></span>  
  
9. <span data-ttu-id="8583a-137">In Utenti/Gruppi immettere l'account utente.</span><span class="sxs-lookup"><span data-stu-id="8583a-137">In Users/Groups, enter the user account.</span></span>  
  
10. <span data-ttu-id="8583a-138">Selezionare **Assegna direttamente le autorizzazioni agli utenti**.</span><span class="sxs-lookup"><span data-stu-id="8583a-138">Select **Give users permission directly**.</span></span>  
  
11. <span data-ttu-id="8583a-139">Fare clic su **Controllo completo**.</span><span class="sxs-lookup"><span data-stu-id="8583a-139">Click **Full Control**.</span></span>  
  
12. <span data-ttu-id="8583a-140">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8583a-140">Click **OK**.</span></span> <span data-ttu-id="8583a-141">Quando a un utente viene consentito di gestire le autorizzazioni per un modello specifico, questi può aprire il modello per modificarne le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="8583a-141">Once a user has the ability to manage permissions for a specific model, he or she can open the model to edit permissions within the model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8583a-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8583a-142">See Also</span></span>  
 <span data-ttu-id="8583a-143">[Utilizzare la sicurezza predefinita di Windows SharePoint Services per gli elementi del server di report](use-built-in-security-in-windows-sharepoint-services-for-report-server-items.md) </span><span class="sxs-lookup"><span data-stu-id="8583a-143">[Use Built-in Security in Windows SharePoint Services for Report Server Items](use-built-in-security-in-windows-sharepoint-services-for-report-server-items.md) </span></span>  
 <span data-ttu-id="8583a-144">[Impostare le autorizzazioni per le operazioni del server di report in un'applicazione Web di SharePoint](set-permissions-for-report-server-operations-in-a-sharepoint-web-application.md) </span><span class="sxs-lookup"><span data-stu-id="8583a-144">[Set Permissions for Report Server Operations in a SharePoint Web Application](set-permissions-for-report-server-operations-in-a-sharepoint-web-application.md) </span></span>  
 <span data-ttu-id="8583a-145">[Confrontare ruoli e attività di Reporting Services con autorizzazioni e gruppi di SharePoint](../reporting-services-roles-tasks-vs-sharepoint-groups-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="8583a-145">[Compare Roles and Tasks in Reporting Services to SharePoint Groups and Permissions](../reporting-services-roles-tasks-vs-sharepoint-groups-permissions.md) </span></span>  
 <span data-ttu-id="8583a-146">[Informazioni di riferimento sulle autorizzazioni relative a elenchi e siti di SharePoint per gli elementi del server di report](sharepoint-site-and-list-permission-reference-for-report-server-items.md) </span><span class="sxs-lookup"><span data-stu-id="8583a-146">[SharePoint Site and List Permission Reference for Report Server Items](sharepoint-site-and-list-permission-reference-for-report-server-items.md) </span></span>  
 [<span data-ttu-id="8583a-147">Concessione di autorizzazioni per elementi del server di report in un sito di SharePoint</span><span class="sxs-lookup"><span data-stu-id="8583a-147">Granting Permissions on Report Server Items on a SharePoint Site</span></span>](granting-permissions-on-report-server-items-on-a-sharepoint-site.md)  
  
  
