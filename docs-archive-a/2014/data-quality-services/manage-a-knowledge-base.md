---
title: Gestire una Knowledge Base | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 27f306f4-d67c-47f5-b35c-4260cc5d36e3
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: cc5fdd87ddb3ea687db10a29d7001564fd8ff107
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636897"
---
# <a name="manage-a-knowledge-base"></a><span data-ttu-id="64e69-102">Gestire una Knowledge Base</span><span class="sxs-lookup"><span data-stu-id="64e69-102">Manage a Knowledge Base</span></span>
  <span data-ttu-id="64e69-103">In questo argomento viene descritto come eseguire le funzioni di gestione su una Knowledge Base in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="64e69-103">This topic describes how to perform management functions on a knowledge base in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="64e69-104">È possibile eliminare una Knowledge Base, sbloccarla, annullare le modifiche apportatevi, rinominarla e visualizzarne le proprietà.</span><span class="sxs-lookup"><span data-stu-id="64e69-104">You can delete a knowledge base, unlock it, discard your work on it, rename it, and display its properties.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="64e69-105">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="64e69-105">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="64e69-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="64e69-106">Prerequisites</span></span>  
 <span data-ttu-id="64e69-107">Per gestire una Knowledge Base, è necessario che questa sia già stata creata e pubblicata (se creata da un altro utente) o chiusa (se creata dallo stesso utente).</span><span class="sxs-lookup"><span data-stu-id="64e69-107">To manage a knowledge base, the knowledge base must have already been created, and either published (if another person created it) or have been closed (if you created it).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="64e69-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="64e69-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="64e69-109">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="64e69-109">Permissions</span></span>  
 <span data-ttu-id="64e69-110">Per aprire una Knowledge Base è necessario disporre del ruolo dqs_kb_editor o dqs_administrator nel database DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="64e69-110">You must have the dqs_kb_editor role or the dqs_administrator on the DQS_MAIN database to open a knowledge base.</span></span>  
  
##  <a name="manage-a-knowledge-base"></a><a name="Manage"></a><span data-ttu-id="64e69-111">Gestire una Knowledge base</span><span class="sxs-lookup"><span data-stu-id="64e69-111">Manage a Knowledge Base</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="64e69-112">[Eseguire l'applicazione Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="64e69-112">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="64e69-113">Nella schermata iniziale del [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] fare clic su **Apri Knowledge Base**.</span><span class="sxs-lookup"><span data-stu-id="64e69-113">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open knowledge base**.</span></span>  
  
3.  <span data-ttu-id="64e69-114">Fare clic con il pulsante destro del mouse su una Knowledge Base nella relativa tabella.</span><span class="sxs-lookup"><span data-stu-id="64e69-114">Right-click a knowledge base in the knowledge base table.</span></span>  
  
4.  <span data-ttu-id="64e69-115">Nel menu di scelta rapida è possibile scegliere tra le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="64e69-115">In the context menu, you can do the following:</span></span>  
  
    1.  <span data-ttu-id="64e69-116">**Apri**: fare clic per aprire la Knowledge Base nell'attività selezionata nel riquadro **Seleziona attività** .</span><span class="sxs-lookup"><span data-stu-id="64e69-116">**Open**: Click to open the knowledge base in the activity selected in the **Select Activity** pane.</span></span>  
  
    2.  <span data-ttu-id="64e69-117">**Sblocca**: è possibile sbloccare la Knowledge Base se si è l'utente che ha utilizzato la Knowledge Base in uno dei passaggi dell'attività di gestione del dominio, individuazione delle informazioni e criteri di corrispondenza, e l'ha chiusa.</span><span class="sxs-lookup"><span data-stu-id="64e69-117">**Unlock**: You can unlock the knowledge base if you are the user who was working on the knowledge base in one of the steps of domain management, knowledge discovery, and the matching policy activity, and closed it.</span></span> <span data-ttu-id="64e69-118">Se si sblocca la Knowledge Base, un altro utente potrà aprirla e utilizzarla.</span><span class="sxs-lookup"><span data-stu-id="64e69-118">If you unload the knowledge base, another person will be able to open it and work on it.</span></span> <span data-ttu-id="64e69-119">Questo comando non è disponibile se la Knowledge Base non si trova in uno stato di un'attività.</span><span class="sxs-lookup"><span data-stu-id="64e69-119">This command is not available if the knowledge base is not in a state of an activity.</span></span> <span data-ttu-id="64e69-120">Per altre informazioni, vedere [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span><span class="sxs-lookup"><span data-stu-id="64e69-120">For more information, see [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span></span>  
  
    3.  <span data-ttu-id="64e69-121">**Annulla modifiche apportate**: fare clic quando la Knowledge Base si trova in uno stato di elaborazione, indicato con una voce nel campo Stato della tabella.</span><span class="sxs-lookup"><span data-stu-id="64e69-121">**Discard work**: Click when the knowledge base is in a state of being worked on, as shown with an entry in the State field in the table.</span></span> <span data-ttu-id="64e69-122">Questo comando non è disponibile se la Knowledge Base non si trova in uno stato di un'attività e se la Knowledge Base è bloccata.</span><span class="sxs-lookup"><span data-stu-id="64e69-122">This command is not available if the knowledge base is not in a state of an activity, and it is not available if the knowledge base is locked.</span></span> <span data-ttu-id="64e69-123">Per altre informazioni, vedere [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span><span class="sxs-lookup"><span data-stu-id="64e69-123">For more information, see [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span></span>  
  
    4.  <span data-ttu-id="64e69-124">**Rinomina**: fare clic per potere modificare il campo della tabella per la Knowledge Base selezionata.</span><span class="sxs-lookup"><span data-stu-id="64e69-124">**Rename**: Click to make the Knowledge Base field of the table editable for the knowledge base that you right-clicked on.</span></span> <span data-ttu-id="64e69-125">Modificare il nome, quindi fare clic sulla Knowledge Base e nel campo per accettare la modifica del nome.</span><span class="sxs-lookup"><span data-stu-id="64e69-125">Change the name, and then click on that knowledge base and another one in the field to accept the name change.</span></span>  
  
    5.  <span data-ttu-id="64e69-126">**Elimina**: fare clic per rimuovere la Knowledge Base dal database DQS_MAIN del [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64e69-126">**Delete**: Click to remove the knowledge base from the DQS_MAIN database on [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
    6.  <span data-ttu-id="64e69-127">**Proprietà**: fare clic per visualizzare le proprietà del database in sola lettura.</span><span class="sxs-lookup"><span data-stu-id="64e69-127">**Properties**: Click to display properties for the database in a read-only display.</span></span>  
  
        1.  <span data-ttu-id="64e69-128">**Knowledge Base origine**: Knowledge Base su cui si basa questo database</span><span class="sxs-lookup"><span data-stu-id="64e69-128">**Source Knowledge Base**: the knowledge base that this database was based on.</span></span> <span data-ttu-id="64e69-129">Ciò è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="64e69-129">This is optional.</span></span>  
  
        2.  <span data-ttu-id="64e69-130">**Stato**: indica se la Knowledge Base è **In lavorazione** e se si trova in un'attività di gestione delle informazioni specifica, come indicato dopo l'ultima chiusura.</span><span class="sxs-lookup"><span data-stu-id="64e69-130">**State**: Indicates if the knowledge base is **In Work** and if it is in a specific knowledge management activity, as determined when it was last closed.</span></span> <span data-ttu-id="64e69-131">Lo stato può essere **In lavorazione**in cui la Knowledge Base viene aperta in una sessione di gestione delle informazioni, ma non in un'attività specifica, o **In lavorazione** con un'attività di gestione delle informazioni in cui la Knowledge Base viene aperta in una sessione di gestione delle informazioni e in un'attività specifica.</span><span class="sxs-lookup"><span data-stu-id="64e69-131">The state can be **In Work**, in which the knowledge base is opened in a knowledge management session, but not in a specific activity, or **In Work** plus a knowledge management activity, in which the knowledge base is opened in a knowledge management session, and in a specific activity.</span></span>  
  
        3.  <span data-ttu-id="64e69-132">**Bloccato**: **True** se la Knowledge Base è bloccata, **False** se non lo è.</span><span class="sxs-lookup"><span data-stu-id="64e69-132">**Is Locked**: **True** if the knowledge base was locked, **False** if not</span></span>  
  
        4.  <span data-ttu-id="64e69-133">**Contiene contenuto non pubblicato**: True se la Knowledge Base contiene contenuto non salvato tramite pubblicazione, False se non lo contiene.</span><span class="sxs-lookup"><span data-stu-id="64e69-133">**Contains unpublished content**: True if the knowledge base contains content that has not been saved by publishing, False if not</span></span>  
  
        5.  <span data-ttu-id="64e69-134">**Bloccato da**: nome dell'utente che ha chiuso la Knowledge Base, bloccandola.</span><span class="sxs-lookup"><span data-stu-id="64e69-134">**Locked By**: the name of the user who closed the knowledge base, locking it</span></span>  
  
        6.  <span data-ttu-id="64e69-135">**Data blocco**: data del blocco.</span><span class="sxs-lookup"><span data-stu-id="64e69-135">**Locked Date**: date when locked</span></span>  
  
        7.  <span data-ttu-id="64e69-136">**Creato da**: nome dell'utente che creato la Knowledge Base, con la rete a cui l'utente appartiene.</span><span class="sxs-lookup"><span data-stu-id="64e69-136">**Created By**: the name of the user who created the knowledge base, with the network that he or she belongs to</span></span>  
  
        8.  <span data-ttu-id="64e69-137">**Data creazione**: data della creazione.</span><span class="sxs-lookup"><span data-stu-id="64e69-137">**Created Date**: date when created</span></span>  
  
##  <a name="follow-up-after-managing-a-knowledge-base"></a><a name="FollowUp"></a><span data-ttu-id="64e69-138">Completamento: fasi successive alla gestione di una Knowledge base</span><span class="sxs-lookup"><span data-stu-id="64e69-138">Follow Up: After Managing a Knowledge Base</span></span>  
 <span data-ttu-id="64e69-139">Dopo avere gestito una Knowledge Base, il passaggio successivo dipende dall'azione intrapresa sulla Knowledge Base:</span><span class="sxs-lookup"><span data-stu-id="64e69-139">After you manage a knowledge base, your next step depends upon the action you took on the knowledge base:</span></span>  
  
-   <span data-ttu-id="64e69-140">Se la Knowledge Base è stata aperta, l'utente continuerà nell'attività selezionata.</span><span class="sxs-lookup"><span data-stu-id="64e69-140">If you opened the knowledge base, you will continue in the activity that you selected.</span></span>  
  
-   <span data-ttu-id="64e69-141">Se è stata sbloccata, la Knowledge Base potrà essere aperta e utilizzata da un altro utente nello stato indicato.</span><span class="sxs-lookup"><span data-stu-id="64e69-141">If you unlocked it, it will be available for another person to open and work on, in the state indicated.</span></span>  
  
-   <span data-ttu-id="64e69-142">Se vi sono state annullate le modifiche apportate, la Knowledge Base sarà disponibile nell'ultimo stato pubblicato.</span><span class="sxs-lookup"><span data-stu-id="64e69-142">If you discarded the work on it, the knowledge base will be available in its last published state.</span></span>  
  
-   <span data-ttu-id="64e69-143">Se è stata rinominata, sarà necessario aprire la Knowledge Base rinominata.</span><span class="sxs-lookup"><span data-stu-id="64e69-143">If you renamed it, you will have to open the renamed knowledge base to work on it.</span></span>  
  
-   <span data-ttu-id="64e69-144">Se è stata eliminata, sarà necessario selezionare un'altra Knowledge Base o crearne una nuova.</span><span class="sxs-lookup"><span data-stu-id="64e69-144">If you delete it, you will have to select another knowledge base to work on, or create a new one.</span></span>  
  
  
