---
title: Pagina sottoscrizioni (Gestione report) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: cf3a6bd0-e0b2-4875-a532-63ef34cfa860
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c67895babe99c92b7c09afd8cb75ca88d5cd7553
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719428"
---
# <a name="subscriptions-page-report-manager"></a><span data-ttu-id="ac5d3-102">Pagina Sottoscrizioni (Gestione report)</span><span class="sxs-lookup"><span data-stu-id="ac5d3-102">Subscriptions Page (Report Manager)</span></span>
  <span data-ttu-id="ac5d3-103">La pagina Sottoscrizioni consente di visualizzare un elenco di tutte le sottoscrizioni del report o dell'origine dati condivisa corrente.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-103">Use the Subscriptions page to list all of the subscriptions for the current report or shared data source.</span></span> <span data-ttu-id="ac5d3-104">Se sono disponibili autorizzazioni sufficienti (quelle assegnate dall'attività Gestione di tutte le sottoscrizioni) è possibile visualizzare le sottoscrizioni di tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-104">If you have sufficient permission (as conveyed by the "Manage all subscriptions" task), you can view the subscriptions of all users.</span></span> <span data-ttu-id="ac5d3-105">In caso contrario, in questa pagina vengono visualizzate solo le sottoscrizioni personali.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-105">Otherwise, this page shows only the subscriptions that you own.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ac5d3-106">Le informazioni sulle sottoscrizioni sono disponibili anche in altre pagine.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-106">Other pages also contain subscription information.</span></span> <span data-ttu-id="ac5d3-107">Per ulteriori informazioni, vedere la [pagina Sottoscrizioni personali &#40;Gestione report&#41;](../../2014/reporting-services/my-subscriptions-page-report-manager.md) per accedere a tutte le sottoscrizioni in un'unica posizione o nella [pagina nuova sottoscrizione o modifica sottoscrizione &#40;Gestione report&#41;](../../2014/reporting-services/new-subscription-or-edit-subscription-page-report-manager.md) per creare o modificare una sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-107">For more information, see [My Subscriptions Page &#40;Report Manager&#41;](../../2014/reporting-services/my-subscriptions-page-report-manager.md) to access all your subscriptions in one place or the [New Subscription or Edit Subscription Page &#40;Report Manager&#41;](../../2014/reporting-services/new-subscription-or-edit-subscription-page-report-manager.md) to create or edit a subscription.</span></span>  
  
 <span data-ttu-id="ac5d3-108">Alcune opzioni sono disponibili solo in presenza di sottoscrizioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-108">Some options are visible only if there are existing subscriptions to work with.</span></span> <span data-ttu-id="ac5d3-109">Se non esistono sottoscrizioni definite e si accede a questa pagina da un report, saranno disponibili solo i pulsanti **Nuova sottoscrizione** e **Nuova sottoscrizione guidata dai dati** .</span><span class="sxs-lookup"><span data-stu-id="ac5d3-109">If no subscriptions are defined and you are accessing this page from a report, the **New Subscription** and **New Data-Driven Subscription** are the only options on the page.</span></span>  
  
 <span data-ttu-id="ac5d3-110">Prima di creare una nuova sottoscrizione, è necessario verificare che l'origine dati del report utilizzi credenziali archiviate.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-110">Before you can create a new subscription, you must verify that the report data source uses stored credentials.</span></span> <span data-ttu-id="ac5d3-111">Per archiviare le credenziali, utilizzare la pagina delle proprietà Origini dati.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-111">Use the Data Sources properties page to store credentials.</span></span> <span data-ttu-id="ac5d3-112">Per ulteriori informazioni, vedere la [pagina delle proprietà origini dati &#40;Gestione report&#41;](../../2014/reporting-services/data-sources-properties-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="ac5d3-112">For more information, see [Data Sources Properties Page &#40;Report Manager&#41;](../../2014/reporting-services/data-sources-properties-page-report-manager.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ac5d3-113">Questa funzionalità non è disponibile in ogni edizione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac5d3-113">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ac5d3-114">Per un elenco delle funzionalità supportate dalle edizioni di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], vedere [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="ac5d3-114">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="ac5d3-115">Spostamento</span><span class="sxs-lookup"><span data-stu-id="ac5d3-115">Navigation</span></span>  
 <span data-ttu-id="ac5d3-116">Utilizzare la procedura riportata di seguito per navigare fino a questo percorso nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-116">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-subscriptions-page-for-report"></a><span data-ttu-id="ac5d3-117">Per aprire la pagina Sottoscrizioni per il report</span><span class="sxs-lookup"><span data-stu-id="ac5d3-117">To open the Subscriptions page for report</span></span>  
  
1.  <span data-ttu-id="ac5d3-118">Aprire Gestione report, quindi individuare il report per il quale si desidera visualizzare o configurare una sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-118">Open Report Manager, and locate the report for which you want to view or configure a subscription.</span></span>  
  
2.  <span data-ttu-id="ac5d3-119">Passare con il puntatore del mouse sul report, quindi fare clic sulla freccia a discesa.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-119">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="ac5d3-120">Scegliere **Gestisci**dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-120">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="ac5d3-121">Verrà visualizzata la pagina delle proprietà Generale per il report.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-121">This opens the General properties page for the report.</span></span>  
  
4.  <span data-ttu-id="ac5d3-122">Selezionare la scheda **Sottoscrizioni** .</span><span class="sxs-lookup"><span data-stu-id="ac5d3-122">Select the **Subscriptions** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ac5d3-123">Opzioni</span><span class="sxs-lookup"><span data-stu-id="ac5d3-123">Options</span></span>  
 <span data-ttu-id="ac5d3-124">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="ac5d3-124">**Delete**</span></span>  
 <span data-ttu-id="ac5d3-125">Fare clic per eliminare una sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-125">Click to delete a subscription.</span></span> <span data-ttu-id="ac5d3-126">Prima di poter eliminare una sottoscrizione è necessario selezionare la casella di controllo accanto a ogni sottoscrizione che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-126">Before you can delete a subscription, select the check box next to each subscription that you want to delete.</span></span>  
  
 <span data-ttu-id="ac5d3-127">**Nuova sottoscrizione**</span><span class="sxs-lookup"><span data-stu-id="ac5d3-127">**New Subscription**</span></span>  
 <span data-ttu-id="ac5d3-128">Fare clic per creare una nuova sottoscrizione del report corrente.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-128">Click to create a new subscription to the current report.</span></span> <span data-ttu-id="ac5d3-129">Questo pulsante è abilitato quando il report utilizza credenziali archiviate o non utilizza credenziali.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-129">This button is enabled when the report uses stored credentials or no credentials.</span></span> <span data-ttu-id="ac5d3-130">Questo pulsante non è disponibile quando si accede alla pagina Sottoscrizioni per un'origine dati condivisa.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-130">This button is not available when you open the Subscriptions page for a shared data source.</span></span>  
  
 <span data-ttu-id="ac5d3-131">**Nuova sottoscrizione guidata dai dati**</span><span class="sxs-lookup"><span data-stu-id="ac5d3-131">**New Data-Driven Subscription**</span></span>  
 <span data-ttu-id="ac5d3-132">Fare clic per generare un elenco di Sottoscrittori e di opzioni di recapito da un comando o da una query su un archivio dati contenente tali informazioni.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-132">Click to generate a subscriber list and delivery options from a command or query against a data store that contains this information.</span></span> <span data-ttu-id="ac5d3-133">Questo pulsante è abilitato quando il report utilizza credenziali archiviate o non utilizza credenziali.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-133">This button is enabled when the report uses stored credentials or no credentials.</span></span> <span data-ttu-id="ac5d3-134">Questo pulsante non è disponibile quando si accede alla pagina Sottoscrizioni per un'origine dati condivisa.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-134">This button is not available when you open the Subscriptions page for a shared data source.</span></span>  
  
 <span data-ttu-id="ac5d3-135">**Modifica**</span><span class="sxs-lookup"><span data-stu-id="ac5d3-135">**Edit**</span></span>  
 <span data-ttu-id="ac5d3-136">Fare clic per visualizzare o modificare la descrizione.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-136">Click to view or edit the description.</span></span>  
  
 <span data-ttu-id="ac5d3-137">**Report**</span><span class="sxs-lookup"><span data-stu-id="ac5d3-137">**Report**</span></span>  
 <span data-ttu-id="ac5d3-138">Quando si apre la pagina da un'origine dati condivisa, questa colonna indica il report per cui è stata definita la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-138">When you open this page from a shared data source, this column identifies the report for which the subscription is defined.</span></span> <span data-ttu-id="ac5d3-139">Nella colonna **Cartella** è indicato il percorso del report.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-139">The **Folder** column identifies the location of the report.</span></span>  
  
 <span data-ttu-id="ac5d3-140">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ac5d3-140">**Description**</span></span>  
 <span data-ttu-id="ac5d3-141">Mostra una descrizione della sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-141">Shows a description of the subscription.</span></span>  
  
 <span data-ttu-id="ac5d3-142">**Trigger**</span><span class="sxs-lookup"><span data-stu-id="ac5d3-142">**Trigger**</span></span>  
 <span data-ttu-id="ac5d3-143">Indica i criteri per l'esecuzione della sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-143">Identifies criteria that cause the subscription to run.</span></span> <span data-ttu-id="ac5d3-144">Un trigger **TimedSubscription** è basato su una pianificazione che stabilisce quando viene eseguita la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-144">A **TimedSubscription** trigger is based on a schedule that defines when the subscription runs.</span></span> <span data-ttu-id="ac5d3-145">Un trigger **SnapshotUpdated** è basato sull'aggiornamento di uno snapshot del report.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-145">A **SnapshotUpdated** trigger is based on an update to a report snapshot.</span></span>  
  
 <span data-ttu-id="ac5d3-146">**Proprietario**</span><span class="sxs-lookup"><span data-stu-id="ac5d3-146">**Owner**</span></span>  
 <span data-ttu-id="ac5d3-147">Mostra il nome dell'utente che ha creato la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-147">Shows the name of the user who created the subscription.</span></span>  
  
 <span data-ttu-id="ac5d3-148">**Ultima esecuzione**</span><span class="sxs-lookup"><span data-stu-id="ac5d3-148">**Last Run**</span></span>  
 <span data-ttu-id="ac5d3-149">Mostra la data e ora dell'ultima elaborazione della sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-149">Shows the last time that the subscription was processed.</span></span>  
  
 <span data-ttu-id="ac5d3-150">**Status**</span><span class="sxs-lookup"><span data-stu-id="ac5d3-150">**Status**</span></span>  
 <span data-ttu-id="ac5d3-151">Mostra lo stato della sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-151">Shows the status of the subscription.</span></span> <span data-ttu-id="ac5d3-152">In genere il valore dello stato corrisponde a Nuovo oppure alla data e ora dell'ultima esecuzione della sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-152">Usually, the status value is either New or the date and time at which the subscription last ran.</span></span>  
  
 <span data-ttu-id="ac5d3-153">Il valore "Dati non validi" indica che la sottoscrizione include un puntatore a valori crittografati non più validi per le credenziali archiviate utilizzate per eseguire il report.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-153">A status value of "Bad Data" occurs when the subscription includes a pointer to encrypted values that are no longer valid (that is, to the stored credentials used to run the report).</span></span> <span data-ttu-id="ac5d3-154">I valori crittografati esistenti diventano inutilizzabili quando le chiavi simmetriche utilizzate per crittografare e decrittografare i dati vengono ricreate sul server di report.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-154">Existing encrypted values become unusable when the symmetric keys used to encrypt and decrypt data are recreated on the report server.</span></span>  
  
 <span data-ttu-id="ac5d3-155">Non è possibile elaborare una sottoscrizione se è stata disattivata.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-155">A subscription cannot be processed if it has been deactivated.</span></span> <span data-ttu-id="ac5d3-156">Per aggiornare la sottoscrizione e renderla valida, aprire e salvare la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="ac5d3-156">To update the subscription and make it operational, open and then save the subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac5d3-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac5d3-157">See Also</span></span>  
 <span data-ttu-id="ac5d3-158">[Gestione report &#40;modalità nativa SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="ac5d3-158">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="ac5d3-159">[Creare, modificare ed eliminare sottoscrizioni standard &#40;Reporting Services in modalità nativa&#41;](subscriptions/create-and-manage-subscriptions-for-native-mode-report-servers.md) </span><span class="sxs-lookup"><span data-stu-id="ac5d3-159">[Create, Modify, and Delete Standard Subscriptions &#40;Reporting Services in Native Mode&#41;](subscriptions/create-and-manage-subscriptions-for-native-mode-report-servers.md) </span></span>  
 <span data-ttu-id="ac5d3-160">[Create, Modify, and Delete Schedules](subscriptions/create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="ac5d3-160">[Create, Modify, and Delete Schedules](subscriptions/create-modify-and-delete-schedules.md) </span></span>  
 [<span data-ttu-id="ac5d3-161">Guida sensibile al contesto di Gestione report</span><span class="sxs-lookup"><span data-stu-id="ac5d3-161">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
