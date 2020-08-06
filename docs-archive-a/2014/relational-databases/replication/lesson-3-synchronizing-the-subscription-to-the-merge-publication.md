---
title: 'Lezione 3: Sincronizzazione della sottoscrizione con la pubblicazione di tipo merge | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 49008384-2c55-4080-a890-9bceb40e4d6d
author: rothja
ms.author: jroth
ms.openlocfilehash: bf0256c69d69d1236869fa83285bf4dbf5c462da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723695"
---
# <a name="lesson-3-synchronizing-the-subscription-to-the-merge-publication"></a><span data-ttu-id="00dde-102">Lezione 3: Sincronizzazione della sottoscrizione con la pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="00dde-102">Lesson 3: Synchronizing the Subscription to the Merge Publication</span></span>
  <span data-ttu-id="00dde-103">In questa lezione verrà avviato l'agente di merge per inizializzare la sottoscrizione con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00dde-103">In this lesson, you will start the Merge Agent to initialize the subscription using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="00dde-104">È inoltre necessario eseguire questa procedura per la sincronizzazione con il server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="00dde-104">You also use this procedure to synchronize with the Publisher.</span></span> <span data-ttu-id="00dde-105">Per eseguire questa lezione è necessario aver completato la lezione precedente [Lezione 2: Creazione di una sottoscrizione per una pubblicazione di tipo merge](lesson-2-creating-a-subscription-to-the-merge-publication.md).</span><span class="sxs-lookup"><span data-stu-id="00dde-105">This lesson requires that you have completed the previous lesson, [Lesson 2: Creating a Subscription to the Merge Publication](lesson-2-creating-a-subscription-to-the-merge-publication.md).</span></span>  
  
### <a name="to-start-synchronization-and-initialize-the-subscription"></a><span data-ttu-id="00dde-106">Per avviare la sincronizzazione e inizializzare la sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="00dde-106">To start synchronization and initialize the subscription</span></span>  
  
1.  <span data-ttu-id="00dde-107">Connettersi al Sottoscrittore in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], espandere il nodo del server e quindi espandere la cartella **Replica** .</span><span class="sxs-lookup"><span data-stu-id="00dde-107">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="00dde-108">Nella cartella **Sottoscrizioni locali** fare clic con il pulsante destro del mouse sulla sottoscrizione nel database **SalesOrdersReplica** e quindi scegliere **Visualizza stato sincronizzazione**.</span><span class="sxs-lookup"><span data-stu-id="00dde-108">In the **Local Subscriptions** folder, right-click the subscription in the **SalesOrdersReplica** database, and then click **View Synchronization Status**.</span></span>  
  
3.  <span data-ttu-id="00dde-109">Fare clic su **Avvia** per inizializzare la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="00dde-109">Click **Start** to initialize the subscription.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="00dde-110">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="00dde-110">Next Steps</span></span>  
 <span data-ttu-id="00dde-111">In questo modo è stato eseguito l'agente di merge per l'avvio della sincronizzazione e l'inizializzazione della sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="00dde-111">You have successfully run the Merge Agent to start synchronization and initialize the subscription.</span></span> <span data-ttu-id="00dde-112">È anche possibile inserire, aggiornare o eliminare dati nelle tabelle **SalesOrderHeader** o **SalesOrderDetail** nel server di pubblicazione o nel Sottoscrittore, ripetere questa procedura quando è disponibile la connettività di rete per sincronizzare i dati tra il server di pubblicazione e il Sottoscrittore e quindi eseguire query nelle tabelle **SalesOrderHeader** o **SalesOrderDetail** nell'altro server per visualizzare le modifiche replicate.</span><span class="sxs-lookup"><span data-stu-id="00dde-112">You can also insert, update, or delete data in the **SalesOrderHeader** or **SalesOrderDetail** tables at the Publisher or Subscriber, repeat this procedure when network connectivity is available to synchronize data between the Publisher and the Subscriber, and then query the **SalesOrderHeader** or **SalesOrderDetail** tables at the other server to view the replicated changes.</span></span>  
  
 <span data-ttu-id="00dde-113">Questa lezione completa l'esercitazione Replica di dati con client mobili.</span><span class="sxs-lookup"><span data-stu-id="00dde-113">This completes the Replicating Data with Mobile Clients tutorial.</span></span> <span data-ttu-id="00dde-114">Per un'esercitazione simile che usa la replica transazionale, vedere [Esercitazione: Replica di dati tra server con connessione continua](tutorial-replicating-data-between-continuously-connected-servers.md).</span><span class="sxs-lookup"><span data-stu-id="00dde-114">For a similar tutorial that uses transactional replication, see [Tutorial: Replicating Data Between Continuously Connected Servers](tutorial-replicating-data-between-continuously-connected-servers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00dde-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00dde-115">See Also</span></span>  
 <span data-ttu-id="00dde-116">[Inizializzare una sottoscrizione con uno snapshot](initialize-a-subscription-with-a-snapshot.md) </span><span class="sxs-lookup"><span data-stu-id="00dde-116">[Initialize a Subscription with a Snapshot](initialize-a-subscription-with-a-snapshot.md) </span></span>  
 <span data-ttu-id="00dde-117">[Sincronizzare i dati](synchronize-data.md) </span><span class="sxs-lookup"><span data-stu-id="00dde-117">[Synchronize Data](synchronize-data.md) </span></span>  
 [<span data-ttu-id="00dde-118">Sincronizzazione di una sottoscrizione pull</span><span class="sxs-lookup"><span data-stu-id="00dde-118">Synchronize a Pull Subscription</span></span>](synchronize-a-pull-subscription.md)  
  
  
