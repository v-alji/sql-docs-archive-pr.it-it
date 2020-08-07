---
title: Visualizzare le dimensioni del file sparse di uno snapshot del database (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- snapshots [SQL Server database snapshots], sparse files
- space [SQL Server], sparse files
- sparse files [SQL Server]
- size [SQL Server], sparse files
- maximum sparse file size
- database snapshots [SQL Server], sparse files
- space [SQL Server], database snapshots
ms.assetid: 1867c5f8-d57c-46d3-933d-3642ab0a8e24
author: stevestein
ms.author: sstein
ms.openlocfilehash: 424399b9915c8e7e26e1076fd2e553aafe06fcf0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720003"
---
# <a name="view-the-size-of-the-sparse-file-of-a-database-snapshot-transact-sql"></a><span data-ttu-id="29246-102">Visualizzare le dimensioni del file sparse di uno snapshot del database (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="29246-102">View the Size of the Sparse File of a Database Snapshot (Transact-SQL)</span></span>
  <span data-ttu-id="29246-103">In questo argomento si descrive come utilizzare [!INCLUDE[tsql](../../includes/tsql-md.md)] per verificare che un file di database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sia un file sparse e per conoscere le dimensioni effettive e massime.</span><span class="sxs-lookup"><span data-stu-id="29246-103">This topic describes how to use [!INCLUDE[tsql](../../includes/tsql-md.md)] to verify that a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database file is a sparse file and to find out its actual and maximum sizes.</span></span> <span data-ttu-id="29246-104">I file sparse, che sono una funzionalità del file system NTFS, vengono utilizzati dagli snapshot di database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="29246-104">Sparse files, which are a feature of the NTFS file system, are used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database snapshots.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29246-105">Durante la creazione dello snapshot di database, i file sparse vengono generati utilizzando i nomi di file specificati nell'istruzione CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="29246-105">During database snapshot creation, sparse files are created by using the file names in the CREATE DATABASE statement.</span></span> <span data-ttu-id="29246-106">Questi nomi di file sono archiviati in **sys.master_files** nella colonna **physical_name** .</span><span class="sxs-lookup"><span data-stu-id="29246-106">These file names are stored in **sys.master_files** in the **physical_name** column.</span></span> <span data-ttu-id="29246-107">In **sys.database_files** , sia nel database di origine sia nello snapshot, nella colonna **physical_name** sono sempre inclusi i nomi dei file del database di origine.</span><span class="sxs-lookup"><span data-stu-id="29246-107">In **sys.database_files** (whether in the source database or in a snapshot), the **physical_name** column always contains the names of the source database files.</span></span>  
  
## <a name="verify-that-a-database-file-is-a-sparse-file"></a><span data-ttu-id="29246-108">Verificare che un file di database sia un file sparse</span><span class="sxs-lookup"><span data-stu-id="29246-108">Verify that a Database File is a Sparse File</span></span>  
  
1.  <span data-ttu-id="29246-109">Nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="29246-109">On the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
     <span data-ttu-id="29246-110">Selezionare la colonna **is_sparse** in **sys.database_files** nello snapshot di database oppure in **sys.master_files**.</span><span class="sxs-lookup"><span data-stu-id="29246-110">Select the **is_sparse** column from either **sys.database_files** in the database snapshot or from **sys.master_files**.</span></span> <span data-ttu-id="29246-111">Tramite il valore viene indicato se il file è di tipo sparse, come segue:</span><span class="sxs-lookup"><span data-stu-id="29246-111">The value indicates whether the file is a sparse file, as follows:</span></span>  
  
     <span data-ttu-id="29246-112">1 = il file è di tipo sparse.</span><span class="sxs-lookup"><span data-stu-id="29246-112">1 = File is a sparse file.</span></span>  
  
     <span data-ttu-id="29246-113">0 = il file non è di tipo sparse.</span><span class="sxs-lookup"><span data-stu-id="29246-113">0 = File is not a sparse file.</span></span>  
  
## <a name="find-out-the-actual-size-of-a-sparse-file"></a><span data-ttu-id="29246-114">Conoscere le dimensioni effettive di un file sparse</span><span class="sxs-lookup"><span data-stu-id="29246-114">Find Out the Actual Size of a Sparse File</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29246-115">Le dimensioni dei file sparse aumentano con incrementi di 64 kilobyte (KB) e corrispondono quindi sempre a un multiplo di 64 KB.</span><span class="sxs-lookup"><span data-stu-id="29246-115">Sparse files grow in 64-kilobyte (KB) increments; thus, the size of a sparse file on disk is always a multiple of 64 KB.</span></span>  
  
 <span data-ttu-id="29246-116">Per visualizzare il numero di byte in cui ogni file sparse di uno snapshot è attualmente in uso su disco, eseguire una query sulla colonna **size_on_disk_bytes** della [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vista a gestione dinamica [sys. dm_io_virtual_file_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-io-virtual-file-stats-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="29246-116">To view the number of bytes that each sparse file of a snapshot is currently using on disk, query the **size_on_disk_bytes** column of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][sys.dm_io_virtual_file_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-io-virtual-file-stats-transact-sql) dynamic management view.</span></span>  
  
 <span data-ttu-id="29246-117">Per visualizzare lo spazio su disco usato da un file sparse, fare clic con il pulsante destro del mouse sul file in Microsoft Windows, scegliere **Proprietà**e quindi verificare il valore in **Dimensioni su disco** .</span><span class="sxs-lookup"><span data-stu-id="29246-117">To view the disk space used by a sparse file, right-click the file in Microsoft Windows, click **Properties**, and look at the **Size on disk** value.</span></span>  
  
## <a name="find-out-the-maximum-size-of-a-sparse-file"></a><span data-ttu-id="29246-118">Per rilevare la dimensione massima di un file sparse</span><span class="sxs-lookup"><span data-stu-id="29246-118">Find Out the Maximum Size of a Sparse File</span></span>  
 <span data-ttu-id="29246-119">La dimensione massima consentita per un file sparse equivale alla dimensione del file di database di origine corrispondente al momento della creazione dello snapshot.</span><span class="sxs-lookup"><span data-stu-id="29246-119">The maximum size to which a sparse can grow is the size of the corresponding source database file at the time of the snapshot creation.</span></span> <span data-ttu-id="29246-120">Per informazioni su tale dimensione, è possibile eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="29246-120">To learn this size, you can use one of the following alternatives:</span></span>  
  
-   <span data-ttu-id="29246-121">Per utilizzare il prompt dei comandi di Windows:</span><span class="sxs-lookup"><span data-stu-id="29246-121">Using Windows Command Prompt:</span></span>  
  
    1.  <span data-ttu-id="29246-122">Usare i comandi **dir** di Windows.</span><span class="sxs-lookup"><span data-stu-id="29246-122">Use Windows **dir** commands.</span></span>  
  
    2.  <span data-ttu-id="29246-123">Selezionare il file sparse, aprire la finestra di dialogo **Proprietà** relativa a tale file in Windows e verificare il valore **Dimensioni** .</span><span class="sxs-lookup"><span data-stu-id="29246-123">Select the sparse file, open the file **Properties** dialog box in Windows, and look at the **Size** value.</span></span>  
  
-   <span data-ttu-id="29246-124">Nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="29246-124">On the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
     <span data-ttu-id="29246-125">Selezionare la colonna **size** in **sys.database_files** nello snapshot del database oppure in **sys.master_files**.</span><span class="sxs-lookup"><span data-stu-id="29246-125">Select the **size** column from either **sys.database_files** in the database snapshot or from **sys.master_files**.</span></span> <span data-ttu-id="29246-126">Il valore della colonna **size** indica lo spazio massimo, espresso in pagine SQL, consentito per lo snapshot. Questo valore equivale al campo **Dimensioni** di Windows, ma viene rappresentato in termini di numero di pagine SQL nel file. La dimensione in byte è:</span><span class="sxs-lookup"><span data-stu-id="29246-126">The value of **size** column reflects the maximum space, in SQL pages, that the snapshot can ever use; this value is equivalent to the Windows **Size** field, except that it is represented in terms of the number of SQL pages in the file; the size in bytes is:</span></span>  
  
     <span data-ttu-id="29246-127">( *numero_di_pagine* \* 8192)</span><span class="sxs-lookup"><span data-stu-id="29246-127">( *number_of_pages* \* 8192)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29246-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29246-128">See Also</span></span>  
 <span data-ttu-id="29246-129">[Snapshot del database &#40;SQL Server&#41;](database-snapshots-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="29246-129">[Database Snapshots &#40;SQL Server&#41;](database-snapshots-sql-server.md) </span></span>  
 <span data-ttu-id="29246-130">[sys.fn_virtualfilestats &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-virtualfilestats-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="29246-130">[sys.fn_virtualfilestats &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-virtualfilestats-transact-sql) </span></span>  
 <span data-ttu-id="29246-131">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="29246-131">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span></span>  
 [<span data-ttu-id="29246-132">sys.master_files &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="29246-132">sys.master_files &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql)  
  
  
