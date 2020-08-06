---
title: 'Lezione 2: Creazione di una sottoscrizione per una pubblicazione transazionale | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 5995b7d2-7c06-46f5-b96c-2bee879bcda2
author: rothja
ms.author: jroth
ms.openlocfilehash: dbf40fa259302dffdd6c0b8e8717b7c35b0cf92d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624571"
---
# <a name="lesson-2-creating-a-subscription-to-the-transactional-publication"></a><span data-ttu-id="98b85-102">Lezione 2: Creazione di una sottoscrizione per una pubblicazione transazionale</span><span class="sxs-lookup"><span data-stu-id="98b85-102">Lesson 2: Creating a Subscription to the Transactional Publication</span></span>
  <span data-ttu-id="98b85-103">In questa lezione verranno descritte le procedure per creare una sottoscrizione in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98b85-103">In this lesson, you will create a subscription using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="98b85-104">Per eseguire questa lezione è necessario aver completato la lezione precedente, [Lezione 1: Pubblicazione dei dati tramite la replica transazionale](lesson-1-publishing-data-using-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="98b85-104">This lesson requires that you have completed the previous lesson, [Lesson 1: Publishing Data Using Transactional Replication](lesson-1-publishing-data-using-transactional-replication.md).</span></span>  
  
### <a name="to-create-the-subscription"></a><span data-ttu-id="98b85-105">Per creare la sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="98b85-105">To create the subscription</span></span>  
  
1.  <span data-ttu-id="98b85-106">Connettersi al server di pubblicazione in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], espandere il nodo del server e quindi la cartella **Replica** .</span><span class="sxs-lookup"><span data-stu-id="98b85-106">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="98b85-107">Nella cartella **Pubblicazioni locali** fare clic con il pulsante destro del mouse sulla pubblicazione **AdvWorksProductTrans** e quindi scegliere **Nuove sottoscrizioni**.</span><span class="sxs-lookup"><span data-stu-id="98b85-107">In the **Local Publications** folder, right-click the **AdvWorksProductTrans** publication, and then click **New Subscriptions**.</span></span>  
  
     <span data-ttu-id="98b85-108">Verrà avviata la Creazione guidata nuova sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="98b85-108">The New Subscription Wizard launches.</span></span>  
  
3.  <span data-ttu-id="98b85-109">Nella pagina Pubblicazione selezionare **AdvWorksProductTrans**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="98b85-109">On the Publication page, select **AdvWorksProductTrans**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="98b85-110">Nella pagina Posizione in cui eseguire l'agente di distribuzione selezionare **Esegui tutti gli agenti nel database di distribuzione**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="98b85-110">On the Distribution Agent Location page, select **Run all agents at the Distributor**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="98b85-111">Nella pagina Sottoscrittori, se il nome dell'istanza del Sottoscrittore non è visualizzato, fare clic su **Aggiungi Sottoscrittore**, quindi su **Aggiungi Sottoscrittore SQL Server**, immettere il nome dell'istanza del Sottoscrittore nella finestra di dialogo **Connetti al server** e quindi fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="98b85-111">On the Subscribers page, if the name of the Subscriber instance is not displayed, click **Add Subscriber**, click **Add SQL Server Subscriber**, enter the Subscriber instance name in the **Connect to Server** dialog box, and then click **Connect**.</span></span>  
  
6.  <span data-ttu-id="98b85-112">Nella pagina Sottoscrittori selezionare il nome dell'istanza del server Sottoscrittore e selezionare **\<New Database>** in **database di sottoscrizione**.</span><span class="sxs-lookup"><span data-stu-id="98b85-112">On the Subscribers page, select the instance name of the Subscriber server, and select **\<New Database>** under **Subscription Database**.</span></span>  
  
7.  <span data-ttu-id="98b85-113">Nella finestra di dialogo **Nuovo database** digitare **ProductReplica** nella casella **Nome database** , fare clic su **OK**e scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="98b85-113">On the **New Database** dialog box, enter **ProductReplica** in the **Database name** box, click **OK**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="98b85-114">Nella finestra di dialogo **sicurezza agente di distribuzione** fare clic sul pulsante con i puntini di sospensione (**..**.), immettere \<_Machine_Name> _**\ repl_distribution** nella casella **account processo** , immettere la password per l'account, fare clic su **OK**e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="98b85-114">In the **Distribution Agent Security** dialog box, click the ellipsis (**...**) button, enter \<_Machine_Name>_**\repl_distribution** in the **Process account** box, enter the password for this account, click **OK**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="98b85-115">Fare clic su **Fine** per accettare i valori predefiniti nelle pagine seguenti e completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="98b85-115">Click **Finish** to accept the default values on the remaining pages and complete the wizard.</span></span>  
  
### <a name="setting-database-permissions-at-the-subscriber"></a><span data-ttu-id="98b85-116">Impostazione delle autorizzazioni per il database nel Sottoscrittore</span><span class="sxs-lookup"><span data-stu-id="98b85-116">Setting database permissions at the Subscriber</span></span>  
  
1.  <span data-ttu-id="98b85-117">Connettersi al Sottoscrittore in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], espandere **Database**, **ProductReplica**e **Sicurezza**, fare clic con il pulsante destro del mouse su **Utenti**e quindi scegliere **Nuovo utente**.</span><span class="sxs-lookup"><span data-stu-id="98b85-117">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand **Databases**, **ProductReplica**, and **Security**, right-click **Users**, and then select **New User**.</span></span>  
  
2.  <span data-ttu-id="98b85-118">Nella pagina **Generale** , nell'elenco della pagina **Tipo utente** selezionare **Utente di Windows**.</span><span class="sxs-lookup"><span data-stu-id="98b85-118">On the **General** page, in the **User type** list, select **Windows user**.</span></span>  
  
3.  <span data-ttu-id="98b85-119">Selezionare la casella **nome utente** e fare clic sul pulsante con i puntini di sospensione (...) nella casella **immettere il nome dell'oggetto da selezionare** <Machine_Name>**\ Repl_distribution**, fare clic su **Controlla nomi**e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="98b85-119">Select the **User name** box and click the ellipsis (...) button, in the **Enter the object name to select** box type <Machine_Name>**\repl_distribution**, click **Check Names**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="98b85-120">Nella pagina **Appartenenze** , in **Appartenenza a ruoli del database** selezionare **db_owner**, quindi scegliere **OK** per creare l'utente.</span><span class="sxs-lookup"><span data-stu-id="98b85-120">On the **Membership** page, in **Database role membership** area, select **db_owner**, and then click **OK** to create the user.</span></span>  
  
### <a name="to-view-the-synchronization-status-of-the-subscription"></a><span data-ttu-id="98b85-121">Per visualizzare lo stato di sincronizzazione della sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="98b85-121">To view the synchronization status of the subscription</span></span>  
  
1.  <span data-ttu-id="98b85-122">Connettersi al server di pubblicazione in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], espandere il nodo del server e quindi la cartella **Replica** .</span><span class="sxs-lookup"><span data-stu-id="98b85-122">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="98b85-123">Nella cartella **Pubblicazioni locali** espandere la pubblicazione **AdvWorksProductTrans** , fare clic con il pulsante destro del mouse sulla sottoscrizione nel database **ProductReplica** e quindi scegliere **Visualizza stato sincronizzazione**.</span><span class="sxs-lookup"><span data-stu-id="98b85-123">In the **Local Publications** folder, expand the **AdvWorksProductTrans** publication, right-click the subscription in the **ProductReplica** database, and then click **View Synchronization Status**.</span></span>  
  
     <span data-ttu-id="98b85-124">Verrà visualizzato lo stato corrente della sincronizzazione della sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="98b85-124">The current synchronization status of the subscription is displayed.</span></span>  
  
3.  <span data-ttu-id="98b85-125">Se la sottoscrizione non è visualizzata in **AdvWorksProductTrans**, premere F5 per aggiornare l'elenco.</span><span class="sxs-lookup"><span data-stu-id="98b85-125">If the subscription is not visible under **AdvWorksProductTrans**, press F5 to refresh the list.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="98b85-126">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="98b85-126">Next Steps</span></span>  
 <span data-ttu-id="98b85-127">In questo modo è stata creata una sottoscrizione per la pubblicazione transazionale.</span><span class="sxs-lookup"><span data-stu-id="98b85-127">You have successfully created a subscription to the transactional publication.</span></span> <span data-ttu-id="98b85-128">Poiché l'agente di distribuzione per questa sottoscrizione è in esecuzione continua, la sottoscrizione viene inizializzata al momento della creazione.</span><span class="sxs-lookup"><span data-stu-id="98b85-128">Because the Distribution Agent for this subscription runs continuously, the subscription is initialized when it is created.</span></span> <span data-ttu-id="98b85-129">Il passaggio successivo consiste nell'utilizzo di token di traccia per verificare che le modifiche sono state replicate nel Sottoscrittore e per determinare la latenza.</span><span class="sxs-lookup"><span data-stu-id="98b85-129">Next, you will use tracer tokens to verify that changes are being replicated to the Subscriber and to determine latency.</span></span> <span data-ttu-id="98b85-130">Vedere [Lezione 3: Convalida della sottoscrizione e misurazione della latenza](lesson-3-validating-the-subscription-and-measuring-latency.md).</span><span class="sxs-lookup"><span data-stu-id="98b85-130">See [Lesson 3: Validating the Subscription and Measuring Latency](lesson-3-validating-the-subscription-and-measuring-latency.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98b85-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98b85-131">See Also</span></span>  
 <span data-ttu-id="98b85-132">[Inizializzare una sottoscrizione con uno snapshot](initialize-a-subscription-with-a-snapshot.md) </span><span class="sxs-lookup"><span data-stu-id="98b85-132">[Initialize a Subscription with a Snapshot](initialize-a-subscription-with-a-snapshot.md) </span></span>  
 <span data-ttu-id="98b85-133">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="98b85-133">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 [<span data-ttu-id="98b85-134">Sottoscrizione delle pubblicazioni</span><span class="sxs-lookup"><span data-stu-id="98b85-134">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
