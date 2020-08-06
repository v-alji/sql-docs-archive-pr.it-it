---
title: Ripristinare un database fino a una transazione contrassegnata (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.restoretlog.markedtransaction.f1
helpviewer_keywords:
- database restores [SQL Server], marked transactions
- restoring databases [SQL Server], marked transactions
- marked transactions [SQL Server], restoring
ms.assetid: 8f0ea144-1819-4832-905f-e5d0f49b066b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8de9ef5bed389f020f14e60ccd99f39698e7110f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635678"
---
# <a name="restore-a-database-to-a-marked-transaction-sql-server-management-studio"></a><span data-ttu-id="b42af-102">Ripristino di un database fino a una transazione contrassegnata (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="b42af-102">Restore a Database to a Marked Transaction (SQL Server Management Studio)</span></span>
  <span data-ttu-id="b42af-103">Quando un database è in stato di ripristino, è possibile usare la finestra di dialogo **Ripristina log delle transazioni** per ripristinare il database a una transazione contrassegnata nei backup del log disponibili.</span><span class="sxs-lookup"><span data-stu-id="b42af-103">When a database is in the restoring state, you can use the **Restore Transaction Log** dialog box to restore the database to a marked transaction in the available log backups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b42af-104">Per altre informazioni, vedere [Usare transazioni contrassegnate per recuperare coerentemente i database correlati &#40;modello di recupero con registrazione completa&#41;](use-marked-transactions-to-recover-related-databases-consistently.md) e [Recupero di database correlati che contengono transazioni contrassegnate](recovery-of-related-databases-that-contain-marked-transaction.md).</span><span class="sxs-lookup"><span data-stu-id="b42af-104">For more information, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md) and [Recovery of Related  Databases That Contain Marked Transaction](recovery-of-related-databases-that-contain-marked-transaction.md).</span></span>  
  
### <a name="to-restore-a-marked-transaction"></a><span data-ttu-id="b42af-105">Per ripristinare una transazione contrassegnata</span><span class="sxs-lookup"><span data-stu-id="b42af-105">To restore a marked transaction</span></span>  
  
1.  <span data-ttu-id="b42af-106">Dopo aver stabilito la connessione all'istanza appropriata di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Esplora oggetti fare clic sul nome del server per espanderne l'albero.</span><span class="sxs-lookup"><span data-stu-id="b42af-106">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="b42af-107">Espandere **Database**e, a seconda del database, selezionare un database utente o espandere **Database di sistema** e selezionare un database di sistema.</span><span class="sxs-lookup"><span data-stu-id="b42af-107">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="b42af-108">Fare clic con il pulsante destro del mouse sul database, scegliere **Attività**e quindi fare clic su **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="b42af-108">Right-click the database, point to **Tasks**, and then click **Restore**.</span></span>  
  
4.  <span data-ttu-id="b42af-109">Fare clic su **Log delle transazioni**per visualizzare la finestra di dialogo **Ripristina log delle transazioni** .</span><span class="sxs-lookup"><span data-stu-id="b42af-109">Click **Transaction Log**, which opens the **Restore Transaction Log** dialog box.</span></span>  
  
5.  <span data-ttu-id="b42af-110">Nella sezione **Ripristina fino a** della pagina **Generale** fare clic su **Transazione contrassegnata**per visualizzare la finestra di dialogo **Seleziona transazione contrassegnata** .</span><span class="sxs-lookup"><span data-stu-id="b42af-110">On the **General** page, in the **Restore To** section, select **Marked transaction**, which opens the **Select Marked Transaction** dialog box.</span></span> <span data-ttu-id="b42af-111">In tale finestra è visualizzata una griglia in cui sono elencate le transazioni contrassegnate disponibili nei backup dei log delle transazioni selezionati.</span><span class="sxs-lookup"><span data-stu-id="b42af-111">This dialog box displays a grid listing the marked transactions available in the selected transaction log backups.</span></span>  
  
     <span data-ttu-id="b42af-112">Per impostazione predefinita, il ripristino viene eseguito fino alla transazione contrassegnata esclusa.</span><span class="sxs-lookup"><span data-stu-id="b42af-112">By default, the restore is up to, but excluding, the marked transaction.</span></span> <span data-ttu-id="b42af-113">Per ripristinare anche la transazione contrassegnata, selezionare l'opzione **Includi transazione contrassegnata**.</span><span class="sxs-lookup"><span data-stu-id="b42af-113">To restore the marked transaction also, select **Include marked transaction**.</span></span>  
  
     <span data-ttu-id="b42af-114">Nella tabella seguente vengono elencate le intestazioni delle colonne della griglia con una descrizione dei rispettivi valori.</span><span class="sxs-lookup"><span data-stu-id="b42af-114">The following table lists the column headers of the grid and describes their values.</span></span>  
  
    |<span data-ttu-id="b42af-115">Intestazione</span><span class="sxs-lookup"><span data-stu-id="b42af-115">Header</span></span>|<span data-ttu-id="b42af-116">valore</span><span class="sxs-lookup"><span data-stu-id="b42af-116">Value</span></span>|  
    |------------|-----------|  
    |\<blank>|<span data-ttu-id="b42af-117">Consente di visualizzare una casella di controllo per selezionare il contrassegno.</span><span class="sxs-lookup"><span data-stu-id="b42af-117">Displays a checkbox for selecting the mark.</span></span>|  
    |<span data-ttu-id="b42af-118">**Contrassegno transazione**</span><span class="sxs-lookup"><span data-stu-id="b42af-118">**Transaction Mark**</span></span>|<span data-ttu-id="b42af-119">Nome della transazione contrassegnata specificato dall'utente durante l'esecuzione del commit della transazione.</span><span class="sxs-lookup"><span data-stu-id="b42af-119">Name of the marked transaction specified by the user when the transaction was committed.</span></span>|  
    |<span data-ttu-id="b42af-120">**Data**</span><span class="sxs-lookup"><span data-stu-id="b42af-120">**Date**</span></span>|<span data-ttu-id="b42af-121">Data e ora assegnate alla transazione quando ne è stato eseguito il commit.</span><span class="sxs-lookup"><span data-stu-id="b42af-121">Date and time of the transaction when it was committed.</span></span> <span data-ttu-id="b42af-122">Vengono visualizzate la data e l'ora della transazione registrate nella tabella **msdbgmarkhistory** , non nella data e ora del computer client.</span><span class="sxs-lookup"><span data-stu-id="b42af-122">Transaction date and time are displayed as recorded in the **msdbgmarkhistory** table, not in the client computer's date and time.</span></span>|  
    |<span data-ttu-id="b42af-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b42af-123">**Description**</span></span>|<span data-ttu-id="b42af-124">Eventuale descrizione della transazione contrassegnata specificata dall'utente quando è stato eseguito il commit della transazione.</span><span class="sxs-lookup"><span data-stu-id="b42af-124">Description of marked transaction specified by the user when the transaction was committed (if any).</span></span>|  
    |<span data-ttu-id="b42af-125">**LSN**</span><span class="sxs-lookup"><span data-stu-id="b42af-125">**LSN**</span></span>|<span data-ttu-id="b42af-126">Numero di sequenza del file di log (LSN) della transazione contrassegnata.</span><span class="sxs-lookup"><span data-stu-id="b42af-126">Log sequence number of the marked transaction.</span></span>|  
    |<span data-ttu-id="b42af-127">**Database**</span><span class="sxs-lookup"><span data-stu-id="b42af-127">**Database**</span></span>|<span data-ttu-id="b42af-128">Nome del database in cui è stato eseguito il commit della transazione contrassegnata.</span><span class="sxs-lookup"><span data-stu-id="b42af-128">Name of the database where the marked transaction was committed.</span></span>|  
    |<span data-ttu-id="b42af-129">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="b42af-129">**User Name**</span></span>|<span data-ttu-id="b42af-130">Nome dell'utente del database che ha eseguito il commit della transazione contrassegnata.</span><span class="sxs-lookup"><span data-stu-id="b42af-130">Name of the database user who committed the marked transaction.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b42af-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b42af-131">See Also</span></span>  
 <span data-ttu-id="b42af-132">[Ripristinare un backup del database &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="b42af-132">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span></span>  
 [<span data-ttu-id="b42af-133">Ripristinare un backup del log delle transazioni &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b42af-133">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
  
