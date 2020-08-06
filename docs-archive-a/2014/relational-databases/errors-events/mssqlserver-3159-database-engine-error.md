---
title: MSSQLSERVER_3159 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3159 (Database Engine error)
ms.assetid: c93c1003-0e3a-40aa-9873-44a0f5b8b57e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6b469842b2aab15980c72ea01e46270c55ef29e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628731"
---
# <a name="mssqlserver_3159"></a><span data-ttu-id="4304e-102">MSSQLSERVER_3159</span><span class="sxs-lookup"><span data-stu-id="4304e-102">MSSQLSERVER_3159</span></span>
    
## <a name="details"></a><span data-ttu-id="4304e-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="4304e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4304e-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="4304e-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="4304e-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="4304e-105">Event ID</span></span>|<span data-ttu-id="4304e-106">3159</span><span class="sxs-lookup"><span data-stu-id="4304e-106">3159</span></span>|  
|<span data-ttu-id="4304e-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="4304e-107">Event Source</span></span>|<span data-ttu-id="4304e-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4304e-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4304e-109">Componente</span><span class="sxs-lookup"><span data-stu-id="4304e-109">Component</span></span>|<span data-ttu-id="4304e-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4304e-110">SQLEngine</span></span>|  
|<span data-ttu-id="4304e-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="4304e-111">Symbolic Name</span></span>|<span data-ttu-id="4304e-112">LDDB_LOGNOTBACKEDUP</span><span class="sxs-lookup"><span data-stu-id="4304e-112">LDDB_LOGNOTBACKEDUP</span></span>|  
|<span data-ttu-id="4304e-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="4304e-113">Message Text</span></span>|<span data-ttu-id="4304e-114">La parte finale del log per il database "%ls" non è stata inclusa nel backup.</span><span class="sxs-lookup"><span data-stu-id="4304e-114">The tail of the log for the database "%ls" has not been backed up.</span></span> <span data-ttu-id="4304e-115">Se il log contiene informazioni che non si desidera perdere, utilizzare BACKUP LOG WITH NORECOVERY per eseguire il backup del log.</span><span class="sxs-lookup"><span data-stu-id="4304e-115">Use BACKUP LOG WITH NORECOVERY to back up the log if it contains work that you do not want to lose.</span></span> <span data-ttu-id="4304e-116">Se si desidera semplicemente sovrascrivere il contenuto del log, utilizzare la clausola WITH REPLACE o WITH STOPAT dell'istruzione RESTORE.</span><span class="sxs-lookup"><span data-stu-id="4304e-116">Use the WITH REPLACE or WITH STOPAT clause of the RESTORE statement to just overwrite the contents of the log.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4304e-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="4304e-117">Explanation</span></span>  
 <span data-ttu-id="4304e-118">Nella maggioranza dei casi, nel modello di recupero con registrazione completa o nel modello di recupero con registrazione minima delle operazioni bulk [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] richiede l'esecuzione di un backup della parte finale del log per acquisire i record del log di cui non è stato ancora eseguito il backup.</span><span class="sxs-lookup"><span data-stu-id="4304e-118">In most cases, under the full or bulk-logged recovery models, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requires that you back up the tail of the log to capture the log records that have not yet been backed up.</span></span> <span data-ttu-id="4304e-119">Un backup del log eseguito sulla parte finale del log stesso appena prima di un'operazione di ripristino è detto backup della parte finale del log.</span><span class="sxs-lookup"><span data-stu-id="4304e-119">A log backup taken of the tail of the log just before a restore operation is called a tail-log backup.</span></span>  
  
 <span data-ttu-id="4304e-120">Quando si recupera un database fino al punto di un errore, il backup della parte finale del log è l'ultimo backup di interesse nel piano di recupero.</span><span class="sxs-lookup"><span data-stu-id="4304e-120">When you are recovering a database to the point of a failure, the tail-log backup is the last backup of interest in the recovery plan.</span></span> <span data-ttu-id="4304e-121">Se risulta impossibile eseguire il backup della parte finale del log, è possibile ripristinare un database solo fino alla fine dell'ultimo backup creato prima dell'errore.</span><span class="sxs-lookup"><span data-stu-id="4304e-121">If you cannot back up the tail of the log, you can recover a database only to the end of the last backup that was created before the failure.</span></span>  
  
 <span data-ttu-id="4304e-122">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è in genere necessario eseguire il backup della parte finale del log prima di avviare il ripristino di un database.</span><span class="sxs-lookup"><span data-stu-id="4304e-122">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usually requires that you take a tail-log backup before you start to restore a database.</span></span> <span data-ttu-id="4304e-123">Il backup della parte finale del log impedisce la perdita di dati e mantiene intatta la catena di log.</span><span class="sxs-lookup"><span data-stu-id="4304e-123">The tail-log backup prevents work loss and keeps the log chain intact.</span></span> <span data-ttu-id="4304e-124">Non in tutti gli scenari di ripristino è tuttavia necessario un backup della parte finale del log.</span><span class="sxs-lookup"><span data-stu-id="4304e-124">However, not all restore scenarios require a tail-log backup.</span></span> <span data-ttu-id="4304e-125">Non è necessario eseguire il backup della parte finale del log se il punto di recupero è incluso in un backup del log precedente o se si sta spostando o sostituendo (sovrascrivendo) il database e non è necessario ripristinarlo fino a un punto nel tempo dopo l'ultimo backup.</span><span class="sxs-lookup"><span data-stu-id="4304e-125">You do not have to have a tail-log backup if the recovery point is included in an earlier log backup, or if you are moving or replacing (overwriting) the database and do not need to restore it to a point of time after the most recent backup.</span></span> <span data-ttu-id="4304e-126">Inoltre, se i file di log sono danneggiati e non è possibile creare un backup della parte finale del log, è necessario ripristinare il database senza utilizzare un backup della parte finale del log.</span><span class="sxs-lookup"><span data-stu-id="4304e-126">Also, if the log files are damaged and a tail-log backup cannot be created, you must restore the database without using a tail-log backup.</span></span> <span data-ttu-id="4304e-127">Qualsiasi transazione di cui sia stato eseguito il commit dopo l'ultimo backup del log andrà persa.</span><span class="sxs-lookup"><span data-stu-id="4304e-127">Any transactions committed after the latest log backup are lost.</span></span> <span data-ttu-id="4304e-128">Per ulteriori informazioni, vedere "Ripristino senza utilizzare un backup della parte finale del log" di seguito in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="4304e-128">For more information, see "Restoring Without Using a Tail-Log Backup," later in this topic.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="4304e-129">È consigliabile utilizzare REPLACE raramente e solo dopo un'attenta valutazione.</span><span class="sxs-lookup"><span data-stu-id="4304e-129">REPLACE should be used rarely, and only after careful consideration.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4304e-130">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="4304e-130">User Action</span></span>  
 <span data-ttu-id="4304e-131">Eseguire un backup della parte finale del log e ripetere l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="4304e-131">Take a tail-log backup, and retry the restore operation.</span></span>  
  
 <span data-ttu-id="4304e-132">Se non è possibile eseguire il backup della parte finale del log, utilizzare WITH STOPAT o WITH REPLACE nelle istruzioni RESTORE.</span><span class="sxs-lookup"><span data-stu-id="4304e-132">If you cannot back up the tail of the log, use WITH STOPAT or WITH REPLACE in your RESTORE statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4304e-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4304e-133">See Also</span></span>  
 <span data-ttu-id="4304e-134">[Ripristinare un database di SQL Server fino a un punto specifico &#40;Modello di recupero con registrazione completa&#41;](../backup-restore/restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="4304e-134">[Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](../backup-restore/restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span></span>  
 <span data-ttu-id="4304e-135">[Eseguire il backup del log delle transazioni quando il database è danneggiato &#40;SQL Server&#41;](../backup-restore/back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4304e-135">[Back Up the Transaction Log When the Database Is Damaged &#40;SQL Server&#41;](../backup-restore/back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md) </span></span>  
 <span data-ttu-id="4304e-136">[Backup di un log delle transazioni &#40;SQL Server&#41;](../backup-restore/back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4304e-136">[Back Up a Transaction Log &#40;SQL Server&#41;](../backup-restore/back-up-a-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="4304e-137">Backup della parte finale del log &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4304e-137">Tail-Log Backups &#40;SQL Server&#41;</span></span>](../backup-restore/tail-log-backups-sql-server.md)  
  
  
