---
title: 'Lezione 1: Pubblicazione dei dati tramite la replica di tipo merge | Microsoft Docs'
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: c3c6e0b6-54cd-4b7d-8efb-2cefe14fcd7f
author: rothja
ms.author: jroth
ms.openlocfilehash: ba1d8829d84c02d1436013af80de4bf0979049e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721371"
---
# <a name="lesson-1-publishing-data-using-merge-replication"></a><span data-ttu-id="509d3-102">Lezione 1: Pubblicazione dei dati tramite la replica di tipo merge</span><span class="sxs-lookup"><span data-stu-id="509d3-102">Lesson 1: Publishing Data Using Merge Replication</span></span>
  <span data-ttu-id="509d3-103">In questa lezione verrà creata una pubblicazione di tipo merge con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per pubblicare un subset delle tabelle **Employee**, **SalesOrderHeader**e **SalesOrderDetail** nel database di esempio [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="509d3-103">In this lesson, you will create a merge publication using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to publish a subset of the **Employee**, **SalesOrderHeader**, and **SalesOrderDetail** tables in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="509d3-104">Queste tabelle vengono filtrate usando filtri di riga con parametri in modo che ogni sottoscrizione contenga una partizione univoca dei dati.</span><span class="sxs-lookup"><span data-stu-id="509d3-104">These tables are filtered with parameterized row filters so that each subscription contains a unique partition of the data.</span></span> <span data-ttu-id="509d3-105">Verrà inoltre aggiunto l'account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usato dall'agente di merge all'elenco di accesso alla pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="509d3-105">You will also add the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used by the Merge Agent to the publication access list (PAL).</span></span> <span data-ttu-id="509d3-106">Per eseguire questa esercitazione è necessario avere completato l'esercitazione precedente [Preparazione del server per la replica](tutorial-preparing-the-server-for-replication.md).</span><span class="sxs-lookup"><span data-stu-id="509d3-106">This tutorial requires that you have completed the previous tutorial, [Preparing the Server for Replication](tutorial-preparing-the-server-for-replication.md).</span></span>  
  
### <a name="to-create-a-publication-and-define-articles"></a><span data-ttu-id="509d3-107">Per creare una pubblicazione e definire articoli</span><span class="sxs-lookup"><span data-stu-id="509d3-107">To create a publication and define articles</span></span>  
  
1.  <span data-ttu-id="509d3-108">Connettersi al server di pubblicazione in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]e quindi espandere il nodo del server.</span><span class="sxs-lookup"><span data-stu-id="509d3-108">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="509d3-109">Espandere la cartella **Replica** , fare clic con il pulsante destro del mouse su **Pubblicazioni locali**e quindi scegliere **Nuova pubblicazione**.</span><span class="sxs-lookup"><span data-stu-id="509d3-109">Expand the **Replication** folder, right-click **Local Publications**, and click **New Publication**.</span></span>  
  
     <span data-ttu-id="509d3-110">Verrà avviata la Creazione guidata nuova pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="509d3-110">The Publication Configuration Wizard launches.</span></span>  
  
3.  <span data-ttu-id="509d3-111">Nella pagina Database di pubblicazione selezionare [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="509d3-111">On the Publication Database page, select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="509d3-112">Nella pagina Tipo di pubblicazione selezionare **Pubblicazione di tipo merge**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="509d3-112">On the Publication Type page, select **Merge publication**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="509d3-113">Nella pagina Tipo di Sottoscrittore verificare che sia selezionato solo [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] o versione successiva, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="509d3-113">On the Subscriber Types page, ensure that only [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or later is selected, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="509d3-114">Nella pagina Articoli espandere il nodo **Tabelle** , selezionare **SalesOrderHeader** e **SalesOrderDetail**, espandere **Employee**, selezionare **EmployeeID** o **LoginID**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="509d3-114">On the Articles page, expand the **Tables** node, select **SalesOrderHeader** and **SalesOrderDetail**, then expand **Employee**, select **EmployeeID** or **LoginID**, and then click **Next**.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="509d3-115">Le colonne necessarie aggiuntive sono selezionate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="509d3-115">Additional required columns are automatically selected.</span></span> <span data-ttu-id="509d3-116">Selezionare tutte le colonne selezionate automaticamente e visualizzare la nota sotto l'elenco **Oggetti da pubblicare** per una spiegazione sul motivo per cui la colonna è necessaria.</span><span class="sxs-lookup"><span data-stu-id="509d3-116">Select any of  the automatically selected columns and view the note below the **Objects to publish** list for an explanation why the column is required.</span></span>  
  
7.  <span data-ttu-id="509d3-117">Nella pagina Filtro righe tabella fare clic su **Aggiungi** e quindi su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="509d3-117">On the Filter Table Rows page, click **Add** and then click **Add Filter**.</span></span>  
  
8.  <span data-ttu-id="509d3-118">Nella finestra di dialogo **Aggiungi filtro** selezionare **Employee (HumanResources)** in **Selezionare la tabella da filtrare**, fare clic sulla colonna **LoginID** , fare clic sulla freccia destra per aggiungere la colonna alla clausola WHERE della query di filtro, quindi modificare la clausola WHERE come segue:</span><span class="sxs-lookup"><span data-stu-id="509d3-118">In the **Add Filter** dialog box, select **Employee (HumanResources)** in **Select the table to filter**, click the **LoginID** column, click the right arrow to add the column to the WHERE clause of the filter query, and modify the WHERE clause as follows:</span></span>  
  
    ```  
    WHERE [LoginID] = HOST_NAME()  
    ```  
  
9. <span data-ttu-id="509d3-119">Selezionare **Una riga di questa tabella verrà inviata a una sola sottoscrizione**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="509d3-119">Click **A row from this table will go to only one subscription**, and click **OK**.</span></span>  
  
10. <span data-ttu-id="509d3-120">Nella pagina **Filtro righe tabella** fare clic su **Employee (Human Resources)**, selezionare **Aggiungi** , quindi scegliere **Aggiungi join per estendere il filtro selezionato**.</span><span class="sxs-lookup"><span data-stu-id="509d3-120">On the **Filter Table Rows** page, click **Employee (Human Resources)**, click **Add,** and then click **Add Join to Extend the Selected Filter**.</span></span>  
  
11. <span data-ttu-id="509d3-121">Nella finestra di dialogo **Aggiungi join** selezionare **Sales.SalesOrderHeader** in **Tabella unita in join**, selezionare **L'istruzione per il join verrà scritta manualmente**e quindi completare l'istruzione per il join come segue:</span><span class="sxs-lookup"><span data-stu-id="509d3-121">In the **Add Join** dialog box, select **Sales.SalesOrderHeader** under **Joined table**, click **Write the join statement manually**, and complete the join statement as follows:</span></span>  
  
    ```  
    ON Employee.EmployeeID = SalesOrderHeader.SalesPersonID  
    ```  
  
12. <span data-ttu-id="509d3-122">In **Specificare le opzioni del join**selezionare **Chiave univoca**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="509d3-122">In **Specify join options**, select **Unique key**, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="509d3-123">Nella pagina Filtro righe tabella fare clic su **SalesOrderHeader**, su **Aggiungi**e quindi su **Aggiungi join per estendere il filtro selezionato**.</span><span class="sxs-lookup"><span data-stu-id="509d3-123">On the Filter Table Rows page, click **SalesOrderHeader**, click **Add**, and then click **Add Join to Extend the Selected Filter**.</span></span>  
  
14. <span data-ttu-id="509d3-124">Nella finestra di dialogo **Aggiungi join** selezionare **Sales.SalesOrderDetail** in **Tabella unita in join**.</span><span class="sxs-lookup"><span data-stu-id="509d3-124">In the **Add Join** dialog box, select **Sales.SalesOrderDetail** under **Joined table**.</span></span>  
  
15. <span data-ttu-id="509d3-125">Fare clic su **L'istruzione per il join verrà scritta manualmente**.</span><span class="sxs-lookup"><span data-stu-id="509d3-125">Click **Write the join statement manually**.</span></span>  
  
16. <span data-ttu-id="509d3-126">In **Colonne tabella filtrata**selezionare **BusinessEntityID**, quindi fare clic sul pulsante freccia per copiare il nome della colonna nell'istruzione per il join.</span><span class="sxs-lookup"><span data-stu-id="509d3-126">In **Filtered table columns**, select **BusinessEntityID**, then click the arrow button to copy the column name to the loin statement.</span></span>  
  
17. <span data-ttu-id="509d3-127">Nella casella **Istruzione per il join** completare l'istruzione per il join come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="509d3-127">In the **Join statement** box, complete the join statement as follows:</span></span>  
  
    ```  
    ON Employee.BusinessEntityID = SalesOrderHeader.SalesPersonID  
    ```  
  
18. <span data-ttu-id="509d3-128">In **Specificare le opzioni del join**selezionare **Chiave univoca**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="509d3-128">In **Specify join options**, select **Unique key**, and then click **OK**.</span></span>  
  
19. <span data-ttu-id="509d3-129">Nella pagina **Filtro righe tabella** fare clic su **SalesOrderHeader (Sales)**, selezionare **Aggiungi**, quindi scegliere **Aggiungi join per estendere il filtro selezionato**.</span><span class="sxs-lookup"><span data-stu-id="509d3-129">On the **Filter Table Rows** page, click **SalesOrderHeader (Sales)**, click **Add**, and then click **Add Join to Extend the Selected Filter**.</span></span>  
  
20. <span data-ttu-id="509d3-130">Nella finestra di dialogo **Aggiungi join** selezionare **Sales.SalesOrderDetail** in **Tabella unita in join**, fare clic su **OK**e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="509d3-130">In the **Add Join** dialog box, select **Sales.SalesOrderDetail** under **Joined table**, click **OK**, and then click **Next**.</span></span>  
  
21. <span data-ttu-id="509d3-131">Selezionare **Crea snapshot immediatamente**, deselezionare **Usa la pianificazione seguente per l'esecuzione dell'agente snapshot**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="509d3-131">Select **Create a snapshot immediately**, clear **Schedule the snapshot agent to run at the following times**, and click **Next**.</span></span>  
  
22. <span data-ttu-id="509d3-132">Nella pagina sicurezza agente fare clic su **impostazioni di sicurezza**, digitare \<_Machine_Name> _**\ Repl_snapshot** nella casella **account processo** , specificare la password per l'account, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="509d3-132">On the Agent Security page, click **Security Settings**, type \<_Machine_Name>_**\repl_snapshot** in the **Process account** box, supply the password for this account, and then click **OK**.</span></span> <span data-ttu-id="509d3-133">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="509d3-133">Click **Finish**.</span></span>  
  
23. <span data-ttu-id="509d3-134">Nella pagina Completamento procedura guidata immettere **AdvWorksSalesOrdersMerge** nella casella **Nome pubblicazione** , quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="509d3-134">On the Complete the Wizard page, enter **AdvWorksSalesOrdersMerge** in the **Publication name** box and click **Finish**.</span></span>  
  
24. <span data-ttu-id="509d3-135">Dopo aver creato la pubblicazione, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="509d3-135">After the publication is created, click **Close**.</span></span>  
  
### <a name="to-view-the-status-of-snapshot-generation"></a><span data-ttu-id="509d3-136">Per visualizzare lo stato della generazione dello snapshot</span><span class="sxs-lookup"><span data-stu-id="509d3-136">To view the status of snapshot generation</span></span>  
  
1.  <span data-ttu-id="509d3-137">Connettersi al server di pubblicazione in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], espandere il nodo del server e quindi la cartella **Replica** .</span><span class="sxs-lookup"><span data-stu-id="509d3-137">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="509d3-138">Nella cartella Pubblicazioni locali fare clic con il pulsante destro del mouse su **AdvWorksSalesOrdersMerge**e quindi scegliere **Visualizza stato agente snapshot**.</span><span class="sxs-lookup"><span data-stu-id="509d3-138">In the Local Publications folder, right-click **AdvWorksSalesOrdersMerge**, and then click **View Snapshot Agent Status**.</span></span>  
  
3.  <span data-ttu-id="509d3-139">Verrà visualizzato lo stato corrente del processo dell'agente snapshot per la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="509d3-139">The current status of the Snapshot Agent job for the publication is displayed.</span></span> <span data-ttu-id="509d3-140">Verificare che il processo snapshot abbia avuto esito positivo prima di passare alla lezione successiva.</span><span class="sxs-lookup"><span data-stu-id="509d3-140">Ensure that the snapshot job has succeeded before you continue to the next lesson.</span></span>  
  
### <a name="to-add-the-merge-agent-login-to-the-pal"></a><span data-ttu-id="509d3-141">Per aggiungere l'account di accesso dell'agente di merge all'elenco di accesso alla pubblicazione</span><span class="sxs-lookup"><span data-stu-id="509d3-141">To add the Merge Agent login to the PAL</span></span>  
  
1.  <span data-ttu-id="509d3-142">Connettersi al server di pubblicazione in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], espandere il nodo del server e quindi la cartella **Replica** .</span><span class="sxs-lookup"><span data-stu-id="509d3-142">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="509d3-143">Nella cartella Pubblicazioni locali fare clic con il pulsante destro del mouse su **AdvWorksSalesOrdersMerge**e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="509d3-143">In the Local Publications folder, right-click **AdvWorksSalesOrdersMerge**, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="509d3-144">Verrà visualizzata la finestra di dialogo **Proprietà pubblicazione** .</span><span class="sxs-lookup"><span data-stu-id="509d3-144">The **Publication Properties** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="509d3-145">Selezionare la pagina **Elenco di accesso alla pubblicazione** e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="509d3-145">Select the **Publication Access List** page, and click **Add**.</span></span>  
  
4.  <span data-ttu-id="509d3-146">Nella finestra di dialogo Aggiungi accesso alla pubblicazione selezionare _<Nome_computer>_**\repl_merge** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="509d3-146">In the Add Publication Access dialog box, select _<Machine_Name>_**\repl_merge** and click **OK**.</span></span> <span data-ttu-id="509d3-147">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="509d3-147">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="509d3-148">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="509d3-148">Next Steps</span></span>  
 <span data-ttu-id="509d3-149">In questo modo è stata creata la pubblicazione di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="509d3-149">You have successfully created the merge publication.</span></span> <span data-ttu-id="509d3-150">Il passaggio successivo consiste nel sottoscrivere la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="509d3-150">Next, you will subscribe to this publication.</span></span> <span data-ttu-id="509d3-151">Vedere [Lezione 2: Creazione di una sottoscrizione per una pubblicazione di tipo merge](lesson-2-creating-a-subscription-to-the-merge-publication.md).</span><span class="sxs-lookup"><span data-stu-id="509d3-151">See [Lesson 2: Creating a Subscription to the Merge Publication](lesson-2-creating-a-subscription-to-the-merge-publication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="509d3-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="509d3-152">See Also</span></span>  
 <span data-ttu-id="509d3-153">[Filtrare i dati pubblicati](publish/filter-published-data.md) </span><span class="sxs-lookup"><span data-stu-id="509d3-153">[Filter Published Data](publish/filter-published-data.md) </span></span>  
 <span data-ttu-id="509d3-154">[Parameterized Row Filters](merge/parameterized-filters-parameterized-row-filters.md) </span><span class="sxs-lookup"><span data-stu-id="509d3-154">[Parameterized Row Filters](merge/parameterized-filters-parameterized-row-filters.md) </span></span>  
 [<span data-ttu-id="509d3-155">Define an Article</span><span class="sxs-lookup"><span data-stu-id="509d3-155">Define an Article</span></span>](publish/define-an-article.md)  
  
  
