---
title: Gestire (aprire, sbloccare, rinominare ed eliminare) un progetto Data Quality | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.dqproject.opendqproject.f1
helpviewer_keywords:
- data quality project,delete
- data quality project,rename
- data quality project,unlock
- data quality project,open
ms.assetid: de8a2b04-4673-4beb-b4cf-96a28cdf3a93
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 216c95937676954c509890b879abdee8f55b778c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636884"
---
# <a name="manage-open-unlock-rename-and-delete-a-data-quality-project"></a><span data-ttu-id="d5917-102">Gestione di un progetto Data Quality (apertura, sblocco, ridenominazione ed eliminazione)</span><span class="sxs-lookup"><span data-stu-id="d5917-102">Manage (Open, Unlock, Rename, and Delete) a Data Quality Project</span></span>
  <span data-ttu-id="d5917-103">In questo argomento viene descritto come gestire un progetto Data Quality utilizzando [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] ed effettuare operazioni sul progetto quali apertura, ridenominazione ed eliminazione.</span><span class="sxs-lookup"><span data-stu-id="d5917-103">This topic describes how to manage a data quality project by using [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] such as open, unlock, rename, and delete a data quality project.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d5917-104">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="d5917-104">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="d5917-105">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="d5917-105">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="d5917-106">Non è possibile aprire un progetto bloccato creato da un altro utente.</span><span class="sxs-lookup"><span data-stu-id="d5917-106">You cannot open a locked project that is created by another user.</span></span>  
  
-   <span data-ttu-id="d5917-107">Non è possibile sbloccare, rinominare o eliminare progetti Data Quality creati da altri utenti.</span><span class="sxs-lookup"><span data-stu-id="d5917-107">You cannot unlock, rename, or delete a data quality project that is created by another user.</span></span>  
  
-   <span data-ttu-id="d5917-108">Non è possibile eliminare un progetto Data Quality bloccato.</span><span class="sxs-lookup"><span data-stu-id="d5917-108">You cannot delete a locked data quality project.</span></span> <span data-ttu-id="d5917-109">È necessario procedere allo sblocco prima dell'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="d5917-109">You must first unlock it to delete.</span></span>  
  
-   <span data-ttu-id="d5917-110">È possibile sbloccare solo progetti Data Quality creati dall'utente che sta procedendo allo sblocco.</span><span class="sxs-lookup"><span data-stu-id="d5917-110">You can only unlock a data quality project that is created by you.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="d5917-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d5917-111">Prerequisites</span></span>  
 <span data-ttu-id="d5917-112">È necessario avere almeno un progetto Data Quality da gestire.</span><span class="sxs-lookup"><span data-stu-id="d5917-112">You must have at least one data quality project to manage.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d5917-113">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="d5917-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d5917-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="d5917-114">Permissions</span></span>  
 <span data-ttu-id="d5917-115">Per gestire un progetto Data Quality è necessario disporre del ruolo dqs_kb_editor o dqs_kb_operator nel database DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="d5917-115">You must have the dqs_kb_editor or dqs_kb_operator role on the DQS_MAIN database to manage a data quality project.</span></span>  
  
##  <a name="open-a-data-quality-project"></a><a name="Open"></a> <span data-ttu-id="d5917-116">Apertura di un progetto Data Quality</span><span class="sxs-lookup"><span data-stu-id="d5917-116">Open a Data Quality Project</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="d5917-117">[Eseguire l'applicazione Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="d5917-117">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="d5917-118">Nella pagina iniziale di [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , fare clic su **Apri progetto Data Quality**.</span><span class="sxs-lookup"><span data-stu-id="d5917-118">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open data quality project**.</span></span> <span data-ttu-id="d5917-119">Verrà visualizzata la finestra di dialogo **Apri progetto** .</span><span class="sxs-lookup"><span data-stu-id="d5917-119">The **Open project** screen appears.</span></span>  
  
     <span data-ttu-id="d5917-120">Alternativamente, è possibile aprire direttamente un progetto Data Quality elencato nell'area **Progetto Data Quality recente** facendo clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="d5917-120">Alternately, you can directly open a data quality project listed under **Recent data quality project** area by clicking it.</span></span>  
  
3.  <span data-ttu-id="d5917-121">Nella finestra di dialogo **Apri progetto** fare clic per selezionare il progetto Data Quality che si desidera aprire, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d5917-121">In the **Open project** screen, click to select the data quality project that you want to open, and click **Next**.</span></span>  
  
4.  <span data-ttu-id="d5917-122">Il progetto Data Quality viene aperto nello stesso stato in cui era stata chiusa l'ultima volta l'attività.</span><span class="sxs-lookup"><span data-stu-id="d5917-122">The data quality project opens at the same state of the activity where it was last closed.</span></span> <span data-ttu-id="d5917-123">Un progetto Data Quality può presentare gli stati seguenti:</span><span class="sxs-lookup"><span data-stu-id="d5917-123">A data quality project has the following states:</span></span>  
  
    -   <span data-ttu-id="d5917-124">Per l'attività di **pulizia** , un progetto Data Quality può presentare gli Stati seguenti: **pulizia-Mappa**, **Pulizia-Pulisci**, **pulizia-Gestisci e visualizza risultati**e **pulizia-esportazione**.</span><span class="sxs-lookup"><span data-stu-id="d5917-124">For the **Cleansing** activity, a data quality project can have the following states: **Cleansing - Map**, **Cleansing - Cleanse**, **Cleansing - Manage and View Results**, and **Cleansing - Export**.</span></span>  
  
    -   <span data-ttu-id="d5917-125">Per l'attività di **corrispondenza** , un progetto Data Quality può presentare gli Stati seguenti: **corrispondenza-mappa**, corrispondenza **-** corrispondenza, corrispondenza **-sopravvivenza**e **corrispondenza-esportazione**.</span><span class="sxs-lookup"><span data-stu-id="d5917-125">For the **Matching** activity, a data quality project can have the following states: **Matching - Map**, **Matching - Matching**, **Matching - Survivorship**, and **Matching - Export**.</span></span>  
  
##  <a name="unlock-a-data-quality-project"></a><a name="Unlock"></a> <span data-ttu-id="d5917-126">Sblocco di un progetto Data Quality</span><span class="sxs-lookup"><span data-stu-id="d5917-126">Unlock a Data Quality Project</span></span>  
 <span data-ttu-id="d5917-127">Quando viene creato, un progetto Data Quality è impostato in uno stato bloccato per impedire l'utilizzo o la modifica da parte di altri utenti.</span><span class="sxs-lookup"><span data-stu-id="d5917-127">When you create a data quality project, it is in a locked state to prevent usage or modification by other users.</span></span> <span data-ttu-id="d5917-128">Se si desidera che altri utenti possano lavorare sul progetto Data Quality, una volta completate le proprie attività è necessario sbloccare il progetto.</span><span class="sxs-lookup"><span data-stu-id="d5917-128">You must unlock the data quality project after you have completed your work if you want other users to work on your data quality project.</span></span> <span data-ttu-id="d5917-129">Per i progetti bloccati, viene visualizzato un simbolo a forma di lucchetto.</span><span class="sxs-lookup"><span data-stu-id="d5917-129">A lock symbol is displayed for projects that are locked.</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="d5917-130">[Eseguire l'applicazione Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="d5917-130">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="d5917-131">Nella pagina iniziale di [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , fare clic su **Apri progetto Data Quality**.</span><span class="sxs-lookup"><span data-stu-id="d5917-131">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open data quality project**.</span></span> <span data-ttu-id="d5917-132">Verrà visualizzata la finestra di dialogo **Apri progetto** .</span><span class="sxs-lookup"><span data-stu-id="d5917-132">The **Open project** screen appears.</span></span>  
  
3.  <span data-ttu-id="d5917-133">Nella schermata **Apri progetto** , fare clic con il pulsante destro del mouse su un progetto Data Quality bloccato che sia stato creato dall'utente corrente, quindi scegliere **Sblocca** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="d5917-133">In the **Open project** screen, right-click a locked data quality project that is created by you, and then click **Unlock** in the shortcut menu.</span></span> <span data-ttu-id="d5917-134">Viene visualizzato un segno di spunta verde che indica che il progetto è ora sbloccato.</span><span class="sxs-lookup"><span data-stu-id="d5917-134">A green check mark is displayed for the project indicating that it is unlocked.</span></span>  
  
##  <a name="rename-a-data-quality-project"></a><a name="Rename"></a> <span data-ttu-id="d5917-135">Ridenominazione di un progetto Data Quality</span><span class="sxs-lookup"><span data-stu-id="d5917-135">Rename a Data Quality Project</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="d5917-136">[Eseguire l'applicazione Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="d5917-136">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="d5917-137">Nella pagina iniziale di [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , fare clic su **Apri progetto Data Quality**.</span><span class="sxs-lookup"><span data-stu-id="d5917-137">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open data quality project**.</span></span> <span data-ttu-id="d5917-138">Verrà visualizzata la finestra di dialogo **Apri progetto** .</span><span class="sxs-lookup"><span data-stu-id="d5917-138">The **Open project** screen appears.</span></span>  
  
3.  <span data-ttu-id="d5917-139">Nella schermata **Apri progetto** , fare clic con il pulsante destro del mouse su un progetto Data Quality bloccato che sia stato creato dall'utente corrente, quindi scegliere **Rinomina** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="d5917-139">In the **Open project** screen, right-click a data quality project that is created by you, and then click **Rename** in the shortcut menu.</span></span>  
  
4.  <span data-ttu-id="d5917-140">Il nome del progetto Data Quality diventa modificabile nella colonna **Nome** .</span><span class="sxs-lookup"><span data-stu-id="d5917-140">The data quality project name becomes editable in the **Name** column.</span></span> <span data-ttu-id="d5917-141">Digitare un nuovo nome e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="d5917-141">Type a new name, and then press Enter.</span></span>  
  
##  <a name="delete-a-data-quality-project"></a><a name="Delete"></a> <span data-ttu-id="d5917-142">Eliminazione di un progetto Data Quality</span><span class="sxs-lookup"><span data-stu-id="d5917-142">Delete a Data Quality Project</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="d5917-143">[Eseguire l'applicazione Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="d5917-143">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="d5917-144">Nella pagina iniziale di [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , fare clic su **Apri progetto Data Quality**.</span><span class="sxs-lookup"><span data-stu-id="d5917-144">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open data quality project**.</span></span> <span data-ttu-id="d5917-145">Verrà visualizzata la finestra di dialogo **Apri progetto** .</span><span class="sxs-lookup"><span data-stu-id="d5917-145">The **Open project** screen appears.</span></span>  
  
3.  <span data-ttu-id="d5917-146">Nella schermata **Apri progetto** , fare clic con il pulsante destro del mouse su un progetto Data Quality sbloccato che sia stato creato dall'utente corrente, quindi scegliere **Elimina** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="d5917-146">In the **Open project** screen, right-click an unlocked data quality project that is created by you, and then click **Delete** in the shortcut menu.</span></span>  
  
4.  <span data-ttu-id="d5917-147">Viene visualizzato un messaggio di conferma.</span><span class="sxs-lookup"><span data-stu-id="d5917-147">A confirmation message appears.</span></span> <span data-ttu-id="d5917-148">Fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="d5917-148">Click **Yes**.</span></span>  
  
  
