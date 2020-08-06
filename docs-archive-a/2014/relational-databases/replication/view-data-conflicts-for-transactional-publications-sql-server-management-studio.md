---
title: Visualizzare i conflitti di dati per le pubblicazioni transazionali (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- conflict resolution [SQL Server replication], queued updating subscriptions
- queued updating subscriptions [SQL Server replication]
- viewing conflict information
ms.assetid: 9977dd75-b0de-4376-9c13-86d80567d8aa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 228753c113bcf43ed276d989a3996e9bf23bfc16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636021"
---
# <a name="view-data-conflicts-for-transactional-publications-sql-server-management-studio"></a><span data-ttu-id="7bef5-102">Visualizzazione di conflitti di dati per le pubblicazioni transazionali (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="7bef5-102">View Data Conflicts for Transactional Publications (SQL Server Management Studio)</span></span>
  <span data-ttu-id="7bef5-103">Il Visualizzatore conflitti di replica [!INCLUDE[msCoName](../../includes/msconame-md.md)] consente di visualizzare i conflitti per la replica transazionale peer-to-peer e per la replica transazionale con sottoscrizioni ad aggiornamento in coda.</span><span class="sxs-lookup"><span data-stu-id="7bef5-103">You can view conflicts for peer-to-peer transactional replication and transactional replication with queued updating subscriptions in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Replication Conflict Viewer.</span></span> <span data-ttu-id="7bef5-104">Per informazioni sul rilevamento e la risoluzione dei conflitti, vedere [Rilevamento dei conflitti nella replica peer-to-peer](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md) e [Impostare le opzioni di risoluzione dei conflitti per l'aggiornamento in coda &#40;SQL Server Management Studio&#41;](publish/create-an-updatable-subscription-to-a-transactional-publication.md).</span><span class="sxs-lookup"><span data-stu-id="7bef5-104">For information about how conflicts are detected and resolved, see [Conflict Detection in Peer-to-Peer Replication](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md) and [Set Queued Updating Conflict Resolution Options &#40;SQL Server Management Studio&#41;](publish/create-an-updatable-subscription-to-a-transactional-publication.md).</span></span>  
  
 <span data-ttu-id="7bef5-105">La disponibilità di dati dei conflitti dipende dal tipo di replica e dal periodo di memorizzazione dei conflitti:</span><span class="sxs-lookup"><span data-stu-id="7bef5-105">The availability of conflict data depends on the type of replication and the conflict retention period:</span></span>  
  
-   <span data-ttu-id="7bef5-106">Per la replica peer-to-peer, per impostazione predefinita quando viene rilevato un conflitto si verifica un errore dell'agente di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7bef5-106">For peer-to-peer replication, by default, the Distribution Agent fails when it detects a conflict.</span></span> <span data-ttu-id="7bef5-107">Nel log degli errori viene registrato un errore di conflitto, ma nella tabella dei conflitti non vengono registrati dati, che non sono quindi disponibili per la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="7bef5-107">A conflict error is logged into the error log, but no conflict data is logged into the conflict table; therefore it is not available for viewing.</span></span> <span data-ttu-id="7bef5-108">Se l'esecuzione dell'agente di distribuzione può continuare, viene registrato localmente un conflitto in ogni nodo in cui è stato rilevato.</span><span class="sxs-lookup"><span data-stu-id="7bef5-108">If the Distribution Agent is allowed to continue, a conflict is logged locally on each node where it was detected.</span></span> <span data-ttu-id="7bef5-109">Per ulteriori informazioni, vedere la sezione relativa alla gestione dei conflitti in [Conflict Detection in Peer-to-Peer Replication](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md).</span><span class="sxs-lookup"><span data-stu-id="7bef5-109">For more information, see "Handling Conflicts" in [Conflict Detection in Peer-to-Peer Replication](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md).</span></span>  
  
-   <span data-ttu-id="7bef5-110">Per le sottoscrizioni ad aggiornamento in coda, sono disponibili dati per ogni conflitto.</span><span class="sxs-lookup"><span data-stu-id="7bef5-110">For queued updating subscriptions, data is available for every conflict.</span></span> <span data-ttu-id="7bef5-111">I dati dei conflitti sono disponibili nel Visualizzatore conflitti di replica per l'intervallo di tempo specificato per il periodo di memorizzazione dei conflitti, che per impostazione predefinita è di 14 giorni.</span><span class="sxs-lookup"><span data-stu-id="7bef5-111">Conflict data is available in the Replication Conflict Viewer for the amount of time specified for the conflict retention period, with a default of 14 days.</span></span> <span data-ttu-id="7bef5-112">Per impostare il periodo di memorizzazione dei conflitti, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7bef5-112">To set the conflict retention period, perform either of the following:</span></span>  
  
    -   <span data-ttu-id="7bef5-113">Specificare un valore del periodo di memorizzazione per il parametro @conflict_retention di [sp_addpublication](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7bef5-113">Specify a retention value for the @conflict_retention parameter of [sp_addpublication](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql).</span></span>  
  
    -   <span data-ttu-id="7bef5-114">Specificare il valore `'conflict_retention'` per il @property parametro e un valore di memorizzazione per il @value parametro di [sp_changepublication](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7bef5-114">Specify a value of `'conflict_retention'` for the @property parameter and a retention value for the @value parameter of [sp_changepublication](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql).</span></span>  
  
### <a name="to-view-conflicts"></a><span data-ttu-id="7bef5-115">Per visualizzare i conflitti</span><span class="sxs-lookup"><span data-stu-id="7bef5-115">To view conflicts</span></span>  
  
1.  <span data-ttu-id="7bef5-116">Connettersi al server appropriato in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], quindi espandere il nodo del server:</span><span class="sxs-lookup"><span data-stu-id="7bef5-116">Connect to the appropriate server in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node:</span></span>  
  
    -   <span data-ttu-id="7bef5-117">Per la replica peer-to-peer, si tratta del nodo in cui si è verificato il conflitto.</span><span class="sxs-lookup"><span data-stu-id="7bef5-117">For peer-to-peer replication, this is the node at which the conflict occurred.</span></span>  
  
    -   <span data-ttu-id="7bef5-118">Per le sottoscrizioni ad aggiornamento in coda, si tratta di server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="7bef5-118">For queued updating subscriptions, this is the Publisher.</span></span>  
  
2.  <span data-ttu-id="7bef5-119">Espandere la cartella **Replica** e quindi la cartella **Pubblicazioni locali** .</span><span class="sxs-lookup"><span data-stu-id="7bef5-119">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="7bef5-120">Fare clic con il pulsante destro del mouse sulla pubblicazione per la quale si desidera visualizzare i conflitti e quindi scegliere **Visualizza conflitti**.</span><span class="sxs-lookup"><span data-stu-id="7bef5-120">Right-click the publication for which you want to view conflicts, and then click **View Conflicts**.</span></span>  
  
4.  <span data-ttu-id="7bef5-121">Nella finestra di dialogo **Seleziona tabella con conflitti** selezionare un database, una pubblicazione e una tabella per cui visualizzare i conflitti.</span><span class="sxs-lookup"><span data-stu-id="7bef5-121">In the **Select Conflict Table** dialog box, select a database, publication, and table for which to view conflicts.</span></span>  
  
5.  <span data-ttu-id="7bef5-122">Nel Visualizzatore conflitti di replica è possibile:</span><span class="sxs-lookup"><span data-stu-id="7bef5-122">In the Replication Conflict Viewer, you can:</span></span>  
  
    -   <span data-ttu-id="7bef5-123">Filtrare le righe con i pulsanti a destra della griglia superiore.</span><span class="sxs-lookup"><span data-stu-id="7bef5-123">Filter rows with the buttons to the right of the upper grid.</span></span>  
  
    -   <span data-ttu-id="7bef5-124">Selezionare una riga nella griglia superiore per visualizzare le informazioni su tale riga nella griglia inferiore.</span><span class="sxs-lookup"><span data-stu-id="7bef5-124">Select a row in the upper grid to display information on that row in the lower grid.</span></span>  
  
    -   <span data-ttu-id="7bef5-125">Selezionare una o più righe nella griglia superiore e quindi fare clic su **Rimuovi**per rimuovere la riga dalla tabella di metadati dei conflitti.</span><span class="sxs-lookup"><span data-stu-id="7bef5-125">Select one or more rows in the upper grid, and then click **Remove**, which removes the row from the conflicts metadata table.</span></span>  
  
    -   <span data-ttu-id="7bef5-126">Fare clic sul pulsante delle proprietà (**...**) per visualizzare altre informazioni su una colonna coinvolta in un conflitto.</span><span class="sxs-lookup"><span data-stu-id="7bef5-126">Click the properties button (**...**) to view more information on a column involved in a conflict.</span></span>  
  
    -   <span data-ttu-id="7bef5-127">Selezionare **Registra informazioni dettagliate sul conflitto** per registrare i dati del conflitto in un file.</span><span class="sxs-lookup"><span data-stu-id="7bef5-127">Select **Log the details of this conflict** to log conflict data to a file.</span></span> <span data-ttu-id="7bef5-128">Per specificare un percorso per il file, scegliere **Opzioni** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="7bef5-128">To specify a location for the file, point to the **View** menu, and then click **Options**.</span></span> <span data-ttu-id="7bef5-129">Immettere un valore o fare clic sul pulsante Sfoglia (**...**) e quindi passare al file appropriato.</span><span class="sxs-lookup"><span data-stu-id="7bef5-129">Enter a value, or click the browse button (**...**), and then navigate to the appropriate file.</span></span> <span data-ttu-id="7bef5-130">Fare clic su **OK** per chiudere la finestra di dialogo **Opzioni** .</span><span class="sxs-lookup"><span data-stu-id="7bef5-130">Click **OK** to close the **Options** dialog box.</span></span>  
  
6.  <span data-ttu-id="7bef5-131">Chiudere il Visualizzatore conflitti di replica.</span><span class="sxs-lookup"><span data-stu-id="7bef5-131">Close the Replication Conflict Viewer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bef5-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bef5-132">See Also</span></span>  
 <span data-ttu-id="7bef5-133">[Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md) </span><span class="sxs-lookup"><span data-stu-id="7bef5-133">[Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md) </span></span>  
 [<span data-ttu-id="7bef5-134">Queued Updating Conflict Detection and Resolution</span><span class="sxs-lookup"><span data-stu-id="7bef5-134">Queued Updating Conflict Detection and Resolution</span></span>](transactional/updatable-subscriptions-queued-updating-conflict-resolution.md)  
  
  
