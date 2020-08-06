---
title: MSSQLSERVER_2527 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2527 (Database Engine error)
ms.assetid: 1cef90ef-9c39-44e6-bc7f-316c8f53c10c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 900707634a016ecfd29f9f676e68b4d2f557ccea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626791"
---
# <a name="mssqlserver_2527"></a><span data-ttu-id="49066-102">MSSQLSERVER_2527</span><span class="sxs-lookup"><span data-stu-id="49066-102">MSSQLSERVER_2527</span></span>
    
## <a name="details"></a><span data-ttu-id="49066-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="49066-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="49066-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="49066-104">Product Name</span></span>|<span data-ttu-id="49066-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="49066-105">SQL Server</span></span>|  
|<span data-ttu-id="49066-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="49066-106">Event ID</span></span>|<span data-ttu-id="49066-107">2527</span><span class="sxs-lookup"><span data-stu-id="49066-107">2527</span></span>|  
|<span data-ttu-id="49066-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="49066-108">Event Source</span></span>|<span data-ttu-id="49066-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="49066-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="49066-110">Componente</span><span class="sxs-lookup"><span data-stu-id="49066-110">Component</span></span>|<span data-ttu-id="49066-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="49066-111">SQLEngine</span></span>|  
|<span data-ttu-id="49066-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="49066-112">Symbolic Name</span></span>|<span data-ttu-id="49066-113">DBCC_INDEX_FILEGROUP_IS_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="49066-113">DBCC_INDEX_FILEGROUP_IS_OFFLINE</span></span>|  
|<span data-ttu-id="49066-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="49066-114">Message Text</span></span>|<span data-ttu-id="49066-115">Impossibile elaborare l'indice I_NAME della tabella O_NAME perché il filegroup F_NAME è offline.</span><span class="sxs-lookup"><span data-stu-id="49066-115">Unable to process index I_NAME of table O_NAME because filegroup F_NAME is offline.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="49066-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="49066-116">Explanation</span></span>  
 <span data-ttu-id="49066-117">Questo messaggio informativo indica che non è possibile verificare l'indice perché uno dei filegroup che archivia i dati dell'indice è offline.</span><span class="sxs-lookup"><span data-stu-id="49066-117">This informational message indicates that the index cannot be checked because one of the filegroups that stores data for the index is offline.</span></span> <span data-ttu-id="49066-118">Lo stato dei file di un filegroup determina la disponibilità dell'intero filegroup.</span><span class="sxs-lookup"><span data-stu-id="49066-118">The state of the files in a filegroup determines the availability of the whole filegroup.</span></span> <span data-ttu-id="49066-119">Un filegroup è disponibile se tutti i file in esso inclusi sono online.</span><span class="sxs-lookup"><span data-stu-id="49066-119">For a filegroup to be available, all files within the filegroup must be online.</span></span> <span data-ttu-id="49066-120">In assenza di altri problemi, tutti gli altri indici dello stesso oggetto verranno verificati.</span><span class="sxs-lookup"><span data-stu-id="49066-120">If there are no other problems, all other indexes of the same object will be checked.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="49066-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="49066-121">User Action</span></span>  
 <span data-ttu-id="49066-122">Per visualizzare lo stato dei file per il filegroup specificato, eseguire una query sulla vista del catalogo **sys.database_files** o **sys.master_files**.</span><span class="sxs-lookup"><span data-stu-id="49066-122">To view the state of the files for the specified filegroup, query either the **sys.database_files** or **sys.master_files** catalog view.</span></span>  
  
 <span data-ttu-id="49066-123">Ripristinare il file offline da un backup.</span><span class="sxs-lookup"><span data-stu-id="49066-123">Restore the offline file from a backup.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49066-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49066-124">See Also</span></span>  
 <span data-ttu-id="49066-125">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="49066-125">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span></span>  
 <span data-ttu-id="49066-126">[sys. master_files &#40;&#41;Transact-SQL](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="49066-126">[sys.master_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) </span></span>  
 [<span data-ttu-id="49066-127">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="49066-127">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
