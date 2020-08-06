---
title: 'Lezione 1: Pubblicazione dei dati tramite la replica transazionale | Microsoft Docs'
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 9c55aa3c-4664-41fc-943f-e817c31aad5e
author: rothja
ms.author: jroth
ms.openlocfilehash: ce20f4ed8863ede34c8709d2b77bf032e7d14a97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713032"
---
# <a name="lesson-1-publishing-data-using-transactional-replication"></a><span data-ttu-id="5f696-102">Lezione 1: Pubblicazione dei dati tramite la replica transazionale</span><span class="sxs-lookup"><span data-stu-id="5f696-102">Lesson 1: Publishing Data Using Transactional Replication</span></span>
  <span data-ttu-id="5f696-103">In questa lezione verrà creata una pubblicazione transazionale con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per pubblicare un subset filtrato della tabella **Product** nel database di esempio [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5f696-103">In this lesson, you will create a transactional publication using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to publish a filtered subset of the **Product** table in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="5f696-104">Verrà inoltre aggiunto l'account di accesso di SQL Server utilizzato dall'agente di distribuzione all'elenco di accesso alla pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="5f696-104">You will also add the SQL Server login used by the Distribution Agent to the publication access list (PAL).</span></span> <span data-ttu-id="5f696-105">Per eseguire questa esercitazione è necessario avere completato l'esercitazione precedente [Preparazione del server per la replica](tutorial-preparing-the-server-for-replication.md).</span><span class="sxs-lookup"><span data-stu-id="5f696-105">Before starting this tutorial, you should have completed the previous tutorial, [Preparing the Server for Replication](tutorial-preparing-the-server-for-replication.md).</span></span>  
  
### <a name="to-create-a-publication-and-define-articles"></a><span data-ttu-id="5f696-106">Per creare una pubblicazione e definire articoli</span><span class="sxs-lookup"><span data-stu-id="5f696-106">To create a publication and define articles</span></span>  
  
1.  <span data-ttu-id="5f696-107">Connettersi al server di pubblicazione in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]e quindi espandere il nodo del server.</span><span class="sxs-lookup"><span data-stu-id="5f696-107">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="5f696-108">Espandere la cartella **Replica** , fare clic con il pulsante destro del mouse sulla cartella **Pubblicazioni locali** e quindi scegliere **Nuova pubblicazione**.</span><span class="sxs-lookup"><span data-stu-id="5f696-108">Expand the **Replication** folder, right-click the **Local Publications** folder, and click **New Publication**.</span></span>  
  
     <span data-ttu-id="5f696-109">Verrà avviata la Creazione guidata nuova pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="5f696-109">The Publication Configuration Wizard launches.</span></span>  
  
3.  <span data-ttu-id="5f696-110">Nella pagina Database di pubblicazione selezionare [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5f696-110">On the Publication Database page, select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="5f696-111">Nella pagina Tipo di pubblicazione selezionare **Pubblicazione transazionale**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5f696-111">On the Publication Type page, select **Transactional publication**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="5f696-112">Nella pagina Articoli espandere il nodo **Tabelle** , selezionare la casella di controllo **Product** , quindi espandere **Product** e deselezionare le caselle di controllo **ListPrice** e **StandardCost** .</span><span class="sxs-lookup"><span data-stu-id="5f696-112">On the Articles page, expand the **Tables** node, select the **Product** check box, then expand **Product** and clear the **ListPrice** and **StandardCost** check boxes.</span></span> <span data-ttu-id="5f696-113">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5f696-113">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="5f696-114">Nella pagina Filtro righe tabella fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5f696-114">On the Filter Table Rows page, click **Add**.</span></span>  
  
7.  <span data-ttu-id="5f696-115">Nella finestra di dialogo **Aggiungi filtro** fare clic sulla colonna **SafetyStockLevel** , fare clic sulla freccia destra per aggiungere la colonna alla clausola WHERE dell'istruzione per il filtro e modificare la clausola WHERE come segue:</span><span class="sxs-lookup"><span data-stu-id="5f696-115">In the **Add Filter** dialog box, click the **SafetyStockLevel** column, click the right arrow to add the column to the Filter statement WHERE clause of the filter query, and modify the WHERE clause as follows:</span></span>  
  
    ```  
    WHERE [SafetyStockLevel] < 500  
    ```  
  
8.  <span data-ttu-id="5f696-116">Fare clic su **OK** e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5f696-116">Click **OK**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="5f696-117">Selezionare la casella di controllo **Crea uno snapshot immediatamente e mantieni lo snapshot disponibile per l'inizializzazione delle sottoscrizioni** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5f696-117">Select the **Create a snapshot immediately and keep the snapshot available to initialize subscriptions** check box, and click **Next**.</span></span>  
  
10. <span data-ttu-id="5f696-118">Nella pagina Sicurezza agente deselezionare la casella di controllo **Usa le impostazioni di sicurezza dell'agente snapshot** .</span><span class="sxs-lookup"><span data-stu-id="5f696-118">On the Agent Security page, clear **Use the security settings from the Snapshot Agent** check box.</span></span>  
  
11. <span data-ttu-id="5f696-119">Fare clic su **impostazioni di sicurezza** per il agente di snapshot, immettere \<_Machine_Name> _**\ Repl_snapshot** nella casella **account processo** , specificare la password per l'account, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5f696-119">Click **Security Settings** for the Snapshot Agent, enter \<_Machine_Name>_**\repl_snapshot** in the **Process account** box, supply the password for this account, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="5f696-120">Ripetere il passaggio precedente per impostare repl_logreader come account di processo per l'agente di lettura log e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="5f696-120">Repeat the previous step to set repl_logreader as the process account for the Log Reader Agent, and then click **Finish**.</span></span>  
  
13. <span data-ttu-id="5f696-121">Nella pagina Completamento procedura guidata digitare **AdvWorksProductTrans** nella casella **Nome pubblicazione** , quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="5f696-121">On the Complete the Wizard page, type **AdvWorksProductTrans** in the **Publication name** box, and click **Finish**.</span></span>  
  
14. <span data-ttu-id="5f696-122">Dopo aver creato la pubblicazione, fare clic su **Chiudi** per completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="5f696-122">After the publication is created, click **Close** to complete the wizard.</span></span>  
  
### <a name="to-view-the-status-of-snapshot-generation"></a><span data-ttu-id="5f696-123">Per visualizzare lo stato della generazione dello snapshot</span><span class="sxs-lookup"><span data-stu-id="5f696-123">To view the status of snapshot generation</span></span>  
  
1.  <span data-ttu-id="5f696-124">Connettersi al server di pubblicazione in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], espandere il nodo del server e quindi la cartella **Replica** .</span><span class="sxs-lookup"><span data-stu-id="5f696-124">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="5f696-125">Nella cartella **Pubblicazioni locali** fare clic con il pulsante destro del mouse su **AdvWorksProductTrans**e quindi scegliere **Visualizza stato agente snapshot**.</span><span class="sxs-lookup"><span data-stu-id="5f696-125">In the **Local Publications** folder, right-click **AdvWorksProductTrans**, and then click **View Snapshot Agent Status**.</span></span>  
  
3.  <span data-ttu-id="5f696-126">Verrà visualizzato lo stato corrente del processo dell'agente snapshot per la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="5f696-126">The current status of the Snapshot Agent job for the publication is displayed.</span></span> <span data-ttu-id="5f696-127">Verificare che il processo snapshot abbia avuto esito positivo prima di passare alla lezione successiva.</span><span class="sxs-lookup"><span data-stu-id="5f696-127">Verify that the snapshot job has succeeded before you continue to the next lesson.</span></span>  
  
### <a name="to-add-the-distribution-agent-login-to-the-pal"></a><span data-ttu-id="5f696-128">Per aggiungere l'account di accesso dell'agente di distribuzione all'elenco di accesso alla pubblicazione</span><span class="sxs-lookup"><span data-stu-id="5f696-128">To add the Distribution Agent login to the PAL</span></span>  
  
1.  <span data-ttu-id="5f696-129">Connettersi al server di pubblicazione in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], espandere il nodo del server e quindi la cartella **Replica** .</span><span class="sxs-lookup"><span data-stu-id="5f696-129">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="5f696-130">Nella cartella **Pubblicazioni locali** fare clic con il pulsante destro del mouse su **AdvWorksProductTrans**e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="5f696-130">In the **Local Publications** folder, right-click **AdvWorksProductTrans**, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="5f696-131">Verrà visualizzata la finestra di dialogo **Proprietà pubblicazione** .</span><span class="sxs-lookup"><span data-stu-id="5f696-131">The **Publication Properties** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="5f696-132">Selezionare la pagina **Elenco di accesso alla pubblicazione** e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5f696-132">Select the **Publication Access List** page, and click **Add**.</span></span>  
  
4.  <span data-ttu-id="5f696-133">Nella finestra di dialogo **Aggiungi accesso alla pubblicazione** selezionare _<Machine_Name>_**\repl_distribution** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5f696-133">\In the **Add Publication Access** dialog box, select _<Machine_Name>_**\repl_distribution** and click **OK**.</span></span> <span data-ttu-id="5f696-134">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5f696-134">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5f696-135">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="5f696-135">Next Steps</span></span>  
 <span data-ttu-id="5f696-136">In questo modo è stata creata la pubblicazione transazionale.</span><span class="sxs-lookup"><span data-stu-id="5f696-136">You have successfully created the transactional publication.</span></span> <span data-ttu-id="5f696-137">Il passaggio successivo consiste nel sottoscrivere la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="5f696-137">Next, you will subscribe to this publication.</span></span> <span data-ttu-id="5f696-138">Vedere [Lezione 2: Creazione di una sottoscrizione per una pubblicazione transazionale](lesson-2-creating-a-subscription-to-the-transactional-publication.md).</span><span class="sxs-lookup"><span data-stu-id="5f696-138">See [Lesson 2: Creating a Subscription to the Transactional Publication](lesson-2-creating-a-subscription-to-the-transactional-publication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f696-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f696-139">See Also</span></span>  
 <span data-ttu-id="5f696-140">[Filtrare i dati pubblicati](publish/filter-published-data.md) </span><span class="sxs-lookup"><span data-stu-id="5f696-140">[Filter Published Data](publish/filter-published-data.md) </span></span>  
 <span data-ttu-id="5f696-141">[Define an Article](publish/define-an-article.md) </span><span class="sxs-lookup"><span data-stu-id="5f696-141">[Define an Article](publish/define-an-article.md) </span></span>  
 [<span data-ttu-id="5f696-142">Creare e applicare lo snapshot</span><span class="sxs-lookup"><span data-stu-id="5f696-142">Create and Apply the Snapshot</span></span>](create-and-apply-the-snapshot.md)  
  
  
