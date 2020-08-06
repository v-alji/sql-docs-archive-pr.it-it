---
title: Visualizzare lo stato di un database con mirroring (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- states [SQL Server], database mirroring
- database mirroring [SQL Server], states
ms.assetid: 544f4194-253e-4c57-96ca-31c16301434f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fc691e8b746a816ab88448e3399aebad6d8844e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627380"
---
# <a name="view-the-state-of-a-mirrored-database-sql-server-management-studio"></a><span data-ttu-id="351f1-102">Visualizzazione dello stato di un database con mirroring (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="351f1-102">View the State of a Mirrored Database (SQL Server Management Studio)</span></span>
  <span data-ttu-id="351f1-103">Durante una sessione di mirroring del database, è possibile visualizzare lo stato nella pagina **Mirroring** della finestra di dialogo **Proprietà database** .</span><span class="sxs-lookup"><span data-stu-id="351f1-103">During a database mirroring session, you can view the status on the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
### <a name="to-view-the-status-of-a-database-mirroring-session"></a><span data-ttu-id="351f1-104">Per visualizzare lo stato di una sessione di mirroring del database</span><span class="sxs-lookup"><span data-stu-id="351f1-104">To view the status of a database mirroring session</span></span>  
  
1.  <span data-ttu-id="351f1-105">Dopo aver attivato la connessione all'istanza del server principale, in Esplora oggetti fare clic sul nome del server per espandere l'albero.</span><span class="sxs-lookup"><span data-stu-id="351f1-105">After connecting to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="351f1-106">Espandere **Database**e selezionare il database per il mirroring.</span><span class="sxs-lookup"><span data-stu-id="351f1-106">Expand **Databases**, and select the database to be mirrored.</span></span>  
  
3.  <span data-ttu-id="351f1-107">Fare clic con il pulsante destro del mouse sul database, scegliere **Attività**e quindi fare clic su **Server mirror**.</span><span class="sxs-lookup"><span data-stu-id="351f1-107">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="351f1-108">Viene visualizzata la pagina **Mirroring** della finestra di dialogo **Proprietà database** .</span><span class="sxs-lookup"><span data-stu-id="351f1-108">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="351f1-109">In seguito all'avvio del mirroring, nel pannello **Stato** verrà visualizzato lo stato della sessione di mirroring del database nel momento in cui si è selezionata la pagina **Mirroring** o si è fatto clic sul pulsante **Aggiorna** .</span><span class="sxs-lookup"><span data-stu-id="351f1-109">After mirroring begins, the **Status** panel displays the status of the database mirroring session as of when you selected the **Mirroring** page or clicked the **Refresh** button.</span></span> <span data-ttu-id="351f1-110">Gli stati possibili sono indicati di seguito:</span><span class="sxs-lookup"><span data-stu-id="351f1-110">The possible states are as follows:</span></span>  
  
    |<span data-ttu-id="351f1-111">Stati</span><span class="sxs-lookup"><span data-stu-id="351f1-111">States</span></span>|<span data-ttu-id="351f1-112">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="351f1-112">Explanation</span></span>|  
    |------------|-----------------|  
    |\<blank>|<span data-ttu-id="351f1-113">Non esiste alcuna sessione di mirroring del database e non ci sono attività da segnalare nella pagina **Mirroring** .</span><span class="sxs-lookup"><span data-stu-id="351f1-113">No database mirroring session exists and there is no activity to report on the **Mirroring** page.</span></span>|  
    |<span data-ttu-id="351f1-114">Paused</span><span class="sxs-lookup"><span data-stu-id="351f1-114">Paused</span></span>|<span data-ttu-id="351f1-115">Il database principale è in esecuzione, ma non viene inviato alcun log al server mirror.</span><span class="sxs-lookup"><span data-stu-id="351f1-115">The principal database is running but is not sending any logs to the mirror server.</span></span> <span data-ttu-id="351f1-116">La copia mirror del database non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="351f1-116">The mirror copy of the database is not available.</span></span>|  
    |<span data-ttu-id="351f1-117">Nessuna connessione</span><span class="sxs-lookup"><span data-stu-id="351f1-117">No connection</span></span>|<span data-ttu-id="351f1-118">L'istanza del server principale non può connettersi ai partner o all'istanza del server di controllo del mirroring (se disponibile).</span><span class="sxs-lookup"><span data-stu-id="351f1-118">The principal server instance cannot connect to its partner or to the witness server instance (if any)</span></span>|  
    |<span data-ttu-id="351f1-119">Sincronizzazione in corso</span><span class="sxs-lookup"><span data-stu-id="351f1-119">Synchronizing</span></span>|<span data-ttu-id="351f1-120">Il contenuto del database mirror è in ritardo rispetto a quello del database principale.</span><span class="sxs-lookup"><span data-stu-id="351f1-120">The contents of the mirror database are lagging behind the contents of the principal database.</span></span> <span data-ttu-id="351f1-121">L'istanza del server principale invia record di log all'istanza del server mirror, che applica le modifiche al database mirror per eseguirne il rollforward.</span><span class="sxs-lookup"><span data-stu-id="351f1-121">The principal server instance is sending log records to the mirror server instance, which is applying the changes to the mirror database to roll it forward.</span></span><br /><br /> <span data-ttu-id="351f1-122">All'avvio della sessione di mirroring del database, i database mirror e principale sono in stato di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="351f1-122">At the start of a database mirroring session, the mirror and principal databases are in the synchronizing state.</span></span>|  
    |<span data-ttu-id="351f1-123">Failover</span><span class="sxs-lookup"><span data-stu-id="351f1-123">Failover</span></span>|<span data-ttu-id="351f1-124">Nell'istanza del server principale è iniziato un failover manuale (inversione di ruolo), che non è stato ancora accettato dal server mirror.</span><span class="sxs-lookup"><span data-stu-id="351f1-124">On the principal server instance, a manual failover (role swap) has begun but has not yet accepted by the mirror.</span></span>|  
    |<span data-ttu-id="351f1-125">Sincronizzato</span><span class="sxs-lookup"><span data-stu-id="351f1-125">Synchronized</span></span>|<span data-ttu-id="351f1-126">Il database mirror contiene gli stessi dati del database principale.</span><span class="sxs-lookup"><span data-stu-id="351f1-126">The mirror database contains the same data as the principal database.</span></span> <span data-ttu-id="351f1-127">I failover manuale e automatico sono possibili *solo* in stato sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="351f1-127">Manual and automatic failover are possible *only* in the synchronized state.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="351f1-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="351f1-128">See Also</span></span>  
 [<span data-ttu-id="351f1-129">Stati di mirroring &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="351f1-129">Mirroring States &#40;SQL Server&#41;</span></span>](mirroring-states-sql-server.md)  
  
  
