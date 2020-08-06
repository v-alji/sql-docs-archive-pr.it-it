---
title: Monitoraggio e risoluzione dei problemi di merge per coppie di file di dati e differenziali | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: a8b0bacc-4d2c-42e4-84bf-1a97e0bd385b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5dc57d08f3db1792a9359b3aa79aaceecd03a025
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636879"
---
# <a name="monitoring-and-troubleshooting-merge-for-data-and-delta-file-pairs"></a><span data-ttu-id="581cb-102">Monitoraggio e risoluzione di problemi relativi all'unione di coppie di file di dati e differenziali</span><span class="sxs-lookup"><span data-stu-id="581cb-102">Monitoring and Troubleshooting Merge for Data and Delta File Pairs</span></span>
  <span data-ttu-id="581cb-103">OLTP in memoria utilizza i criteri di unione per unire automaticamente coppie di file di dati e differenziali adiacenti.</span><span class="sxs-lookup"><span data-stu-id="581cb-103">In-Memory OLTP uses a merge policy to merge adjacent data and delta file pairs automatically.</span></span> <span data-ttu-id="581cb-104">Non è possibile disabilitare l'attività di unione.</span><span class="sxs-lookup"><span data-stu-id="581cb-104">You cannot disable merge activity.</span></span>  
  
 <span data-ttu-id="581cb-105">È possibile monitorare le coppie di file di dati e differenziali come segue:</span><span class="sxs-lookup"><span data-stu-id="581cb-105">You can monitor data and delta file pairs, as follows:</span></span>  
  
-   <span data-ttu-id="581cb-106">Confrontare le dimensioni di archiviazione in memoria con le dimensioni di archiviazione complessive.</span><span class="sxs-lookup"><span data-stu-id="581cb-106">Compare the size of in-memory storage to overall size of storage.</span></span> <span data-ttu-id="581cb-107">Se le dimensioni di archiviazione sono eccessivamente grandi, è probabile che l'unione non venga attivata.</span><span class="sxs-lookup"><span data-stu-id="581cb-107">If the storage is dis-proportionately large, then it is likely that merge is not getting triggered.</span></span> <span data-ttu-id="581cb-108">Per informazioni</span><span class="sxs-lookup"><span data-stu-id="581cb-108">For information</span></span>  
  
-   <span data-ttu-id="581cb-109">Esaminare lo spazio utilizzato nei file di dati e differenziali utilizzando [sys. dm_db_xtp_checkpoint_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-checkpoint-files-transact-sql) per verificare se il merge non viene attivato quando necessario.</span><span class="sxs-lookup"><span data-stu-id="581cb-109">Look at the used space in data and delta files using [sys.dm_db_xtp_checkpoint_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-checkpoint-files-transact-sql) to see if merge is not getting triggered when it should.</span></span>  
  
## <a name="performing-a-manual-merge"></a><span data-ttu-id="581cb-110">Esecuzione di un'unione manuale</span><span class="sxs-lookup"><span data-stu-id="581cb-110">Performing a Manual Merge</span></span>  
 <span data-ttu-id="581cb-111">È possibile utilizzare [sys. sp_xtp_merge_checkpoint_files &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-merge-checkpoint-files-transact-sql) per eseguire un'operazione di merge manuale.</span><span class="sxs-lookup"><span data-stu-id="581cb-111">You can use [sys.sp_xtp_merge_checkpoint_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-merge-checkpoint-files-transact-sql) to perform a manual merge.</span></span>  
  
 <span data-ttu-id="581cb-112">Utilizzare la seguente query per recuperare le informazioni sui file di dati e differenziali.</span><span class="sxs-lookup"><span data-stu-id="581cb-112">Use the following query to retrieve information about the data and delta files,</span></span>  
  
```sql  
select checkpoint_file_id, file_type_desc, internal_storage_slot, file_size_in_bytes, file_size_used_in_bytes,   
inserted_row_count, deleted_row_count, lower_bound_tsn, upper_bound_tsn   
from sys.dm_db_xtp_checkpoint_files  
where state = 1  
order by file_type_desc, upper_bound_tsn  
```  
  
 <span data-ttu-id="581cb-113">Si supponga di aver trovato tre file di dati che non sono stati uniti.</span><span class="sxs-lookup"><span data-stu-id="581cb-113">Assume that you found three data files that have not been merged.</span></span> <span data-ttu-id="581cb-114">Utilizzando il valore `lower_bound_tsn` del primo file di dati e `upper_bound_tsn` dell'ultimo file di dati, è possibile eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="581cb-114">Using the `lower_bound_tsn` value of the first data file and the `upper_bound_tsn` of the last data file, you can issue the following command:</span></span>  
  
```sql  
exec sys.sp_xtp_merge_checkpoint_files 'H_DB',  12345, 67890  
```  
  
 <span data-ttu-id="581cb-115">Si supponga che le tre coppie di file di dati e differenziali contengano ciascuna 15.836 righe e 5.279 righe eliminate.</span><span class="sxs-lookup"><span data-stu-id="581cb-115">Assume that the three data and delta file pairs each had 15,836 rows and 5,279 deleted rows.</span></span> <span data-ttu-id="581cb-116">Dopo l'unione, il nuovo file di dati contiene 31.872 righe e 0 righe eliminate.</span><span class="sxs-lookup"><span data-stu-id="581cb-116">After the merge, the new data file has 31,872 rows and 0 deleted rows.</span></span> <span data-ttu-id="581cb-117">Le dimensioni del nuovo file di dati possono essere molto maggiori rispetto a quelle inizialmente allocate di 128 MB.</span><span class="sxs-lookup"><span data-stu-id="581cb-117">The size of the new data file can be much larger than the initially allocated size of 128MB.</span></span> <span data-ttu-id="581cb-118">Ciò avviene perché l'unione manuale esegue l'override dei criteri di unione e forza l'unione dei file richiesti.</span><span class="sxs-lookup"><span data-stu-id="581cb-118">This is because manual merge overrides the merge policy and forces the merge of the requested files.</span></span>  
  
 <span data-ttu-id="581cb-119">La [transizione di stato del Blog dei file del checkpoint nei database con tabelle ottimizzate](https://cloudblogs.microsoft.com/sqlserver/2014/01/23/state-transition-of-checkpoint-files-in-databases-with-memory-optimized-tables/) per la memoria descrive la transizione di stato delle coppie di file di dati e differenziali da inizio a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="581cb-119">The blog [State Transition of Checkpoint Files in Databases with Memory-Optimized Tables](https://cloudblogs.microsoft.com/sqlserver/2014/01/23/state-transition-of-checkpoint-files-in-databases-with-memory-optimized-tables/) describes state transition of data and delta file pairs from inception to garbage collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="581cb-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="581cb-120">See Also</span></span>  
 [<span data-ttu-id="581cb-121">Creazione e gestione dell'archiviazione per gli oggetti ottimizzati per la memoria</span><span class="sxs-lookup"><span data-stu-id="581cb-121">Creating and Managing Storage for Memory-Optimized Objects</span></span>](../relational-databases/in-memory-oltp/creating-and-managing-storage-for-memory-optimized-objects.md)  
  
