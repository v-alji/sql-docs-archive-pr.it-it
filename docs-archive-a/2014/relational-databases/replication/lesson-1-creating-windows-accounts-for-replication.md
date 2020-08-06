---
title: 'Lezione 1: Creazione di account di Windows per la replica | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
- replication [SQL Server], administering
ms.assetid: 65c3816b-47f0-448c-a4a4-ebd3e2a58820
author: rothja
ms.author: jroth
ms.openlocfilehash: 29f1008338b3ba728066ed611108477586a4c899
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624572"
---
# <a name="lesson-1-creating-windows-accounts-for-replication"></a><span data-ttu-id="48361-102">Lezione 1: Creazione di account di Windows per la replica</span><span class="sxs-lookup"><span data-stu-id="48361-102">Lesson 1: Creating Windows Accounts for Replication</span></span>
  <span data-ttu-id="48361-103">In questa lezione verranno creati account di Windows per l'esecuzione degli agenti di replica.</span><span class="sxs-lookup"><span data-stu-id="48361-103">In this lesson, you will create Windows accounts to run replication agents.</span></span> <span data-ttu-id="48361-104">Verrà creato un account di Windows separato nel server locale per gli agenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="48361-104">You will create a separate Windows account on the local server for the following agents:</span></span>  
  
|<span data-ttu-id="48361-105">Agente</span><span class="sxs-lookup"><span data-stu-id="48361-105">Agent</span></span>|<span data-ttu-id="48361-106">Location</span><span class="sxs-lookup"><span data-stu-id="48361-106">Location</span></span>|<span data-ttu-id="48361-107">Nome account</span><span class="sxs-lookup"><span data-stu-id="48361-107">Account name</span></span>|  
|-----------|--------------|------------------|  
|<span data-ttu-id="48361-108">agente snapshot</span><span class="sxs-lookup"><span data-stu-id="48361-108">Snapshot Agent</span></span>|<span data-ttu-id="48361-109">Publisher</span><span class="sxs-lookup"><span data-stu-id="48361-109">Publisher</span></span>|<span data-ttu-id="48361-110">\<*machine_name*>\ repl_snapshot</span><span class="sxs-lookup"><span data-stu-id="48361-110">\<*machine_name*>\repl_snapshot</span></span>|  
|<span data-ttu-id="48361-111">Agente di lettura log</span><span class="sxs-lookup"><span data-stu-id="48361-111">Log Reader Agent</span></span>|<span data-ttu-id="48361-112">Publisher</span><span class="sxs-lookup"><span data-stu-id="48361-112">Publisher</span></span>|<span data-ttu-id="48361-113">\<*machine_name*>\ repl_logreader</span><span class="sxs-lookup"><span data-stu-id="48361-113">\<*machine_name*>\repl_logreader</span></span>|  
|<span data-ttu-id="48361-114">Agente di distribuzione</span><span class="sxs-lookup"><span data-stu-id="48361-114">Distribution Agent</span></span>|<span data-ttu-id="48361-115">Server di pubblicazione e Sottoscrittore</span><span class="sxs-lookup"><span data-stu-id="48361-115">Publisher and Subscriber</span></span>|<span data-ttu-id="48361-116">\<*machine_name*>\ repl_distribution</span><span class="sxs-lookup"><span data-stu-id="48361-116">\<*machine_name*>\repl_distribution</span></span>|  
|<span data-ttu-id="48361-117">Agente di merge</span><span class="sxs-lookup"><span data-stu-id="48361-117">Merge Agent</span></span>|<span data-ttu-id="48361-118">Server di pubblicazione e Sottoscrittore</span><span class="sxs-lookup"><span data-stu-id="48361-118">Publisher and Subscriber</span></span>|<span data-ttu-id="48361-119">\<*machine_name*>\ repl_merge</span><span class="sxs-lookup"><span data-stu-id="48361-119">\<*machine_name*>\repl_merge</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="48361-120">Nelle esercitazioni sulla replica i server di pubblicazione e il server di distribuzione condividono la stessa istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48361-120">In the replication tutorials, the Publisher and Distributor share the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="48361-121">Il server di pubblicazione e il Sottoscrittore possono utilizzare la stessa istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ma ciò non è un requisito.</span><span class="sxs-lookup"><span data-stu-id="48361-121">The Publisher and Subscriber may share the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], but it is not a requirement.</span></span> <span data-ttu-id="48361-122">Se il server di pubblicazione e il Sottoscrittore condividono la stessa istanza, i passaggi utilizzati per creare gli account del Sottoscrittore non sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="48361-122">If the Publisher and Subscriber share the same instance, the steps that are used to create accounts at the Subscriber are not required.</span></span>  
  
### <a name="to-create-local-windows-accounts-for-replication-agents-at-the-publisher"></a><span data-ttu-id="48361-123">Per creare account di Windows locali per gli agenti di replica nel server di pubblicazione</span><span class="sxs-lookup"><span data-stu-id="48361-123">To create local Windows accounts for replication agents at the Publisher</span></span>  
  
1.  <span data-ttu-id="48361-124">Nel server di pubblicazione aprire **Gestione computer** da **strumenti di amministrazione** nel pannello di controllo.</span><span class="sxs-lookup"><span data-stu-id="48361-124">At the Publisher, open **Computer Management** from **Administrative Tools** in Control Panel.</span></span>  
  
2.  <span data-ttu-id="48361-125">In **Utilità di sistema**espandere **Utenti e gruppi locali**.</span><span class="sxs-lookup"><span data-stu-id="48361-125">In **System Tools**, expand **Local Users and Groups**.</span></span>  
  
3.  <span data-ttu-id="48361-126">Fare clic con il pulsante destro del mouse su **utenti** e quindi scegliere **nuovo utente**.</span><span class="sxs-lookup"><span data-stu-id="48361-126">Right-click **Users** and then click **New User**.</span></span>  
  
4.  <span data-ttu-id="48361-127">Immettere `repl_snapshot` nella casella **nome utente** , specificare la password e altre informazioni rilevanti, quindi fare clic su **Crea** per creare l'account repl_snapshot.</span><span class="sxs-lookup"><span data-stu-id="48361-127">Enter `repl_snapshot` in the **User name** box, provide the password and other relevant information, and then click **Create** to create the repl_snapshot account.</span></span>  
  
5.  <span data-ttu-id="48361-128">Ripetere il passaggio precedente per creare gli account repl_logreader, repl_distribution e repl_merge.</span><span class="sxs-lookup"><span data-stu-id="48361-128">Repeat the previous step to create the repl_logreader, repl_distribution, and repl_merge accounts.</span></span>  
  
6.  <span data-ttu-id="48361-129">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="48361-129">Click **Close**.</span></span>  
  
### <a name="to-create-local-windows-accounts-for-replication-agents-at-the-subscriber"></a><span data-ttu-id="48361-130">Per creare account di Windows locali per gli agenti di replica nel Sottoscrittore</span><span class="sxs-lookup"><span data-stu-id="48361-130">To create local Windows accounts for replication agents at the Subscriber</span></span>  
  
1.  <span data-ttu-id="48361-131">Nel Sottoscrittore aprire **Gestione computer** da **strumenti di amministrazione** nel pannello di controllo.</span><span class="sxs-lookup"><span data-stu-id="48361-131">At the Subscriber, open **Computer Management** from **Administrative Tools** in Control Panel.</span></span>  
  
2.  <span data-ttu-id="48361-132">In **Utilità di sistema**espandere **Utenti e gruppi locali**.</span><span class="sxs-lookup"><span data-stu-id="48361-132">In **System Tools**, expand **Local Users and Groups**.</span></span>  
  
3.  <span data-ttu-id="48361-133">Fare clic con il pulsante destro del mouse su **utenti** e quindi scegliere **nuovo utente**.</span><span class="sxs-lookup"><span data-stu-id="48361-133">Right-click **Users** and then click **New User**.</span></span>  
  
4.  <span data-ttu-id="48361-134">Immettere `repl_distribution` nella casella **nome utente** , specificare la password e altre informazioni rilevanti, quindi fare clic su **Crea** per creare l'account repl_distribution.</span><span class="sxs-lookup"><span data-stu-id="48361-134">Enter `repl_distribution` in the **User name** box, provide the password and other relevant information, and then click **Create** to create the repl_distribution account.</span></span>  
  
5.  <span data-ttu-id="48361-135">Ripetere il passaggio precedente per creare l'account repl_merge.</span><span class="sxs-lookup"><span data-stu-id="48361-135">Repeat the previous step to create the repl_merge account.</span></span>  
  
6.  <span data-ttu-id="48361-136">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="48361-136">Click **Close**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="48361-137">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="48361-137">Next Steps</span></span>  
 <span data-ttu-id="48361-138">In questo modo sono stati creati gli account di Windows per gli agenti di replica.</span><span class="sxs-lookup"><span data-stu-id="48361-138">You have successfully created Windows accounts for replication agents.</span></span> <span data-ttu-id="48361-139">Il passaggio successivo consiste nella configurazione della cartella snapshot.</span><span class="sxs-lookup"><span data-stu-id="48361-139">Next, you will configure the snapshot folder.</span></span> <span data-ttu-id="48361-140">Vedere [Lezione 2: Preparazione della cartella snapshot](lesson-2-preparing-the-snapshot-folder.md).</span><span class="sxs-lookup"><span data-stu-id="48361-140">See [Lesson 2: Preparing the Snapshot Folder](lesson-2-preparing-the-snapshot-folder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48361-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48361-141">See Also</span></span>  
 [<span data-ttu-id="48361-142">Panoramica degli agenti di replica</span><span class="sxs-lookup"><span data-stu-id="48361-142">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
