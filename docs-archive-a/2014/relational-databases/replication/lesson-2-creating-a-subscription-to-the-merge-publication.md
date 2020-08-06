---
title: 'Lezione 2: Creazione di una sottoscrizione per una pubblicazione di tipo merge | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 06722baa-9065-443e-b1d5-99036cf89074
author: rothja
ms.author: jroth
ms.openlocfilehash: 2ca4f9cdf9c40d80b428d65b4201be61c2ea3eae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629777"
---
# <a name="lesson-2-creating-a-subscription-to-the-merge-publication"></a><span data-ttu-id="cbe41-102">Lezione 2: Creazione di una sottoscrizione per una pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="cbe41-102">Lesson 2: Creating a Subscription to the Merge Publication</span></span>
  <span data-ttu-id="cbe41-103">In questa lezione verranno descritte le procedure per creare una sottoscrizione in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbe41-103">In this lesson, you will create the subscription using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="cbe41-104">Verranno quindi impostate le autorizzazioni per il database di sottoscrizione e verrà generato manualmente lo snapshot dei dati filtrati per la nuova sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="cbe41-104">You will then set permissions on the subscription database and manually generate the filtered data snapshot for the new subscription.</span></span> <span data-ttu-id="cbe41-105">Per eseguire questa lezione è necessario aver completato la lezione precedente [Lezione 1: Pubblicazione dei dati tramite la replica di tipo merge](lesson-1-publishing-data-using-merge-replication.md).</span><span class="sxs-lookup"><span data-stu-id="cbe41-105">This lesson requires that you have completed the previous lesson, [Lesson 1: Publishing Data Using Merge Replication](lesson-1-publishing-data-using-merge-replication.md).</span></span>  
  
### <a name="to-create-the-subscription"></a><span data-ttu-id="cbe41-106">Per creare la sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="cbe41-106">To create the subscription</span></span>  
  
1.  <span data-ttu-id="cbe41-107">Connettersi al Sottoscrittore in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], espandere il nodo del server, espandere la cartella **Replica** , fare clic con il pulsante destro del mouse sulla cartella **Sottoscrizioni locali** e scegliere **Nuova sottoscrizione**.</span><span class="sxs-lookup"><span data-stu-id="cbe41-107">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, expand the **Replication** folder, right-click the **Local Subscriptions** folder, and then click **New Subscriptions**.</span></span>  
  
     <span data-ttu-id="cbe41-108">Verrà avviata la Creazione guidata nuova sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="cbe41-108">The New Subscription Wizard launches.</span></span>  
  
2.  <span data-ttu-id="cbe41-109">Nella pagina **Pubblicazione** selezionare **Trova server di pubblicazione SQL Server** nell'elenco **Server di pubblicazione** .</span><span class="sxs-lookup"><span data-stu-id="cbe41-109">On the **Publication** page, click **Find SQL Server Publisher** in the **Publisher** list.</span></span>  
  
3.  <span data-ttu-id="cbe41-110">Nella finestra di dialogo **Connetti al server** immettere il nome dell'istanza del server di pubblicazione nella casella **Nome server** e fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="cbe41-110">In the **Connect to Server** dialog box, enter the name of the Publisher instance in the **Server name** box, and click **Connect**.</span></span>  
  
4.  <span data-ttu-id="cbe41-111">Fare clic su **AdvWorksSalesOrdersMerge**e su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cbe41-111">Click **AdvWorksSalesOrdersMerge**, and click **Next**.</span></span>  
  
5.  <span data-ttu-id="cbe41-112">Nella pagina Posizione in cui eseguire l'agente di merge fare clic su **Esegui ogni agente nel relativo Sottoscrittore**e su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cbe41-112">On the Merge Agent Location page, click **Run each agent at its Subscriber**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="cbe41-113">Nella pagina Sottoscrittori selezionare il nome dell'istanza del server del sottoscrittore e selezionare **dall'elenco in**Database di sottoscrizione **\<New Database>** .</span><span class="sxs-lookup"><span data-stu-id="cbe41-113">On the Subscribers page, select the instance name of the Subscriber server, and under **Subscription Database**, select **\<New Database>** from the list.</span></span>  
  
7.  <span data-ttu-id="cbe41-114">Nella finestra di dialogo **Nuovo database** immettere **SalesOrdersReplica** nella casella **Nome database** , selezionare **OK**e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cbe41-114">In the **New Database** dialog box, enter **SalesOrdersReplica** in the **Database name** box, click **OK**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="cbe41-115">Nella pagina sicurezza agente di merge fare clic sul pulsante con i puntini di sospensione (**..**.), immettere \<_Machine_Name> _**\ Repl_merge** nella casella **account processo** , specificare la password per l'account, fare clic su **OK**, su **Avanti**e quindi di nuovo su **Avanti** .</span><span class="sxs-lookup"><span data-stu-id="cbe41-115">On the Merge Agent Security page, click the ellipsis (**...**) button, enter \<_Machine_Name>_**\repl_merge** in the **Process account** box, supply the password for this account, click **OK**, click **Next**, and then click **Next** again.</span></span>  
  
9. <span data-ttu-id="cbe41-116">Nella pagina Inizializzazione sottoscrizioni selezionare **Alla prima sincronizzazione** dall'elenco **Quando** , fare clic su **Avanti**e di nuovo su **Avanti** .</span><span class="sxs-lookup"><span data-stu-id="cbe41-116">On the Initialize Subscriptions page, select **At first synchronization** from the **Initialize When** list, click **Next**, and then click **Next** again.</span></span>  
  
10. <span data-ttu-id="cbe41-117">Nella pagina Valori HOST_NAME immettere un valore `adventure-works\pamela0` nella casella **valore HOST_NAME** , quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="cbe41-117">On the HOST_NAME Values page, enter a value of `adventure-works\pamela0` in the **HOST_NAME Value** box, and then click **Finish**.</span></span>  
  
11. <span data-ttu-id="cbe41-118">Fare di nuovo clic su **Fine** e dopo aver creato la sottoscrizione fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="cbe41-118">Click **Finish** again, and after the subscription is created, click **Close**.</span></span>  
  
### <a name="setting-database-permissions-at-the-subscriber"></a><span data-ttu-id="cbe41-119">Impostazione delle autorizzazioni per il database nel Sottoscrittore</span><span class="sxs-lookup"><span data-stu-id="cbe41-119">Setting database permissions at the Subscriber</span></span>  
  
1.  <span data-ttu-id="cbe41-120">Connettersi al Sottoscrittore in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], espandere **Database**, **SalesOrdersReplica**e **Sicurezza**, fare clic con il pulsante destro del mouse su **Utenti**e scegliere **Nuovo utente**.</span><span class="sxs-lookup"><span data-stu-id="cbe41-120">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand **Databases**, **SalesOrdersReplica**, and **Security**, right-click **Users**, and then select **New User**.</span></span>  
  
2.  <span data-ttu-id="cbe41-121">Nella pagina **generale** immettere \<_Machine_Name> _ **\ repl_merge** nella casella **nome utente** , fare clic sul pulsante con i puntini di sospensione (**...**), fare \<_Machine_Name> clic su **Sfoglia**, selezionare _ **\ repl_merge**, fare clic su **OK**, quindi su **Controlla nomi**e infine su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cbe41-121">On the **General** page, enter \<_Machine_Name>_**\repl_merge** in the **User name** box, click the ellipsis (**...**) button, click **Browse**, select \<_Machine_Name>_**\repl_merge**, click **OK**, click **Check Names**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="cbe41-122">In **Appartenenza a ruoli del database**selezionare **db_owner**e fare clic su **OK** per creare l'utente.</span><span class="sxs-lookup"><span data-stu-id="cbe41-122">In **Database role membership**, select **db_owner**, and then click **OK** to create the user.</span></span>  
  
### <a name="to-create-the-filtered-data-snapshot-for-the-subscription"></a><span data-ttu-id="cbe41-123">Per creare lo snapshot dei dati filtrati per la sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="cbe41-123">To create the filtered data snapshot for the subscription</span></span>  
  
1.  <span data-ttu-id="cbe41-124">Connettersi al server di pubblicazione in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], espandere il nodo del server e quindi la cartella **Replica** .</span><span class="sxs-lookup"><span data-stu-id="cbe41-124">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="cbe41-125">Nella cartella **Pubblicazioni locali** fare clic con il pulsante destro del mouse sulla pubblicazione **AdvWorksSalesOrdersMerge** e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="cbe41-125">In the **Local Publications** folder, right-click the **AdvWorksSalesOrdersMerge** publication, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="cbe41-126">Verrà visualizzata la finestra di dialogo **Proprietà pubblicazione** .</span><span class="sxs-lookup"><span data-stu-id="cbe41-126">The **Publication Properties** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="cbe41-127">Selezionare la pagina **Partizioni dati** e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="cbe41-127">Select the **Data Partitions** page, and click **Add**.</span></span>  
  
4.  <span data-ttu-id="cbe41-128">Nella finestra di dialogo **Aggiungi partizione dati** Digitare `adventure-works\pamela0` nella casella **valore HOST_NAME** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cbe41-128">In the **Add Data Partition** dialog box, type `adventure-works\pamela0` in the **HOST_NAME Value** box, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="cbe41-129">Selezionare la partizione appena aggiunta, selezionare **Genera gli snapshot selezionati adesso**e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cbe41-129">Select the newly added partition, click **Generate the selected snapshots now**, and then click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="cbe41-130">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="cbe41-130">Next Steps</span></span>  
 <span data-ttu-id="cbe41-131">In questo modo è stata creata una sottoscrizione per la pubblicazione di tipo merge ed è stato generato lo snapshot dei dati filtrati per la nuova partizione dati della sottoscrizione in modo che sia disponibile all'inizializzazione della sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="cbe41-131">You have successfully created a subscription to the merge publication and generated the filtered snapshot for the new subscription's data partition so that it will be available when the subscription is initialized.</span></span> <span data-ttu-id="cbe41-132">Il passaggio successivo consiste nella concessione dei diritti all'agente di merge nel database di sottoscrizione e nell'esecuzione dell'agente di merge per l'avvio della sincronizzazione e l'inizializzazione della sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="cbe41-132">Next, you will grant rights to the Merge Agent on the subscription database and run the Merge Agent to start synchronization and initialize the subscription.</span></span> <span data-ttu-id="cbe41-133">Vedere [Lezione 3: Sincronizzazione della sottoscrizione con la pubblicazione di tipo merge](lesson-3-synchronizing-the-subscription-to-the-merge-publication.md).</span><span class="sxs-lookup"><span data-stu-id="cbe41-133">See [Lesson 3: Synchronizing the Subscription to the Merge Publication](lesson-3-synchronizing-the-subscription-to-the-merge-publication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbe41-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbe41-134">See Also</span></span>  
 <span data-ttu-id="cbe41-135">[Subscribe to Publications](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="cbe41-135">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 <span data-ttu-id="cbe41-136">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="cbe41-136">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 [<span data-ttu-id="cbe41-137">Snapshot per pubblicazioni di tipo merge con filtri con parametri</span><span class="sxs-lookup"><span data-stu-id="cbe41-137">Snapshots for Merge Publications with Parameterized Filters</span></span>](snapshots-for-merge-publications-with-parameterized-filters.md)  
  
  
