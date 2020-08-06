---
title: Operazione su checkpoint per le tabelle con ottimizzazione per la memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 47975bd5-373f-43cd-946a-da8e8088b610
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 07560ea0bf147198fb759f6769ae1c6d5c68a71e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724695"
---
# <a name="checkpoint-operation-for-memory-optimized-tables"></a><span data-ttu-id="fdf1a-102">Operazione su checkpoint per le tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="fdf1a-102">Checkpoint Operation for Memory-Optimized Tables</span></span>
  <span data-ttu-id="fdf1a-103">Un checkpoint deve essere eseguito periodicamente per consentire l'avanzamento dei dati ottimizzati per la memoria nei file di dati e differenziali nella parte attiva del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="fdf1a-103">A checkpoint needs to occur periodically for memory-optimized data in data and delta files to advance the active part of transaction log.</span></span> <span data-ttu-id="fdf1a-104">Il checkpoint consente il ripristino o il recupero delle tabelle ottimizzate per la memoria all'ultimo checkpoint eseguito correttamente, quindi viene applicata la parte attiva del log delle transazioni per aggiornare le tabelle ottimizzate per la memoria in modo da completare il recupero.</span><span class="sxs-lookup"><span data-stu-id="fdf1a-104">The checkpoint allows memory-optimized tables to restore or recover to the last successful checkpoint and then the active portion of transaction log is applied to update the memory-optimized tables to complete the recovery.</span></span> <span data-ttu-id="fdf1a-105">L'operazione di checkpoint per le tabelle basate su disco e quella per le tabelle ottimizzate per la memoria sono distinte.</span><span class="sxs-lookup"><span data-stu-id="fdf1a-105">The checkpoint operation for disk-based tables and memory-optimized tables are distinct operations.</span></span> <span data-ttu-id="fdf1a-106">Di seguito vengono descritti diversi scenari e viene indicato il comportamento del checkpoint per le tabelle basate su disco e per quelle ottimizzate per la memoria:</span><span class="sxs-lookup"><span data-stu-id="fdf1a-106">The following describes different scenarios and the checkpoint behavior for disk-based and memory-optimized tables:</span></span>  
  
## <a name="manual-checkpoint"></a><span data-ttu-id="fdf1a-107">Checkpoint manuale</span><span class="sxs-lookup"><span data-stu-id="fdf1a-107">Manual Checkpoint</span></span>  
 <span data-ttu-id="fdf1a-108">Quando si crea un checkpoint manuale, il checkpoint per le tabelle basate su disco e per quelle ottimizzate per la memoria viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="fdf1a-108">When you issue a manual checkpoint, it closes the checkpoint for both disk-based and memory-optimized tables.</span></span> <span data-ttu-id="fdf1a-109">Il file di dati attivo viene chiuso anche se è riempito parzialmente.</span><span class="sxs-lookup"><span data-stu-id="fdf1a-109">The active data file is closed even though it may be partially filled.</span></span>  
  
## <a name="automatic-checkpoint"></a><span data-ttu-id="fdf1a-110">Checkpoint automatico</span><span class="sxs-lookup"><span data-stu-id="fdf1a-110">Automatic Checkpoint</span></span>  
 <span data-ttu-id="fdf1a-111">Il checkpoint automatico viene implementato in modo diverso per le tabelle basate su disco e per le tabelle ottimizzate per la memoria a causa dei modi diversi in cui i dati sono resi persistenti.</span><span class="sxs-lookup"><span data-stu-id="fdf1a-111">Automatic checkpoint is implemented differently for disk-based and memory-optimized tables because of the different ways the data is persisted.</span></span>  
  
 <span data-ttu-id="fdf1a-112">Per le tabelle basate su disco, viene acquisito un checkpoint automatico in base all'opzione di configurazione dell'intervallo di recupero. Per altre informazioni, vedere [Modificare il tempo di recupero di riferimento di un database &#40;SQL Server&#41;](../logs/change-the-target-recovery-time-of-a-database-sql-server.md)).</span><span class="sxs-lookup"><span data-stu-id="fdf1a-112">For disk-based tables, an automatic checkpoint is taken based on the recovery interval configuration option (for more information, see [Change the Target Recovery Time of a Database &#40;SQL Server&#41;](../logs/change-the-target-recovery-time-of-a-database-sql-server.md)).</span></span>  
  
 <span data-ttu-id="fdf1a-113">Per le tabelle ottimizzate per la memoria, viene effettuato un checkpoint automatico quando il file di log delle transazioni diventa più grande di 512 MB dall'ultimo checkpoint.</span><span class="sxs-lookup"><span data-stu-id="fdf1a-113">For memory-optimized tables, an automatic checkpoint is taken when transaction log file becomes bigger than 512 MB since the last checkpoint.</span></span> <span data-ttu-id="fdf1a-114">512 MB include i record del log delle transazioni sia per le tabelle basate su disco che per quelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="fdf1a-114">512 MB includes transaction log records for both disk-based and memory-optimized tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdf1a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fdf1a-115">See Also</span></span>  
 [<span data-ttu-id="fdf1a-116">Creazione e gestione dell'archiviazione per gli oggetti ottimizzati per la memoria</span><span class="sxs-lookup"><span data-stu-id="fdf1a-116">Creating and Managing Storage for Memory-Optimized Objects</span></span>](creating-and-managing-storage-for-memory-optimized-objects.md)  
  
  
