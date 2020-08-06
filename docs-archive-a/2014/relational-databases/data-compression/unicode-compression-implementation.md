---
title: Implementazione della compressione Unicode | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Unicode data compression
- compression [SQL Server], Unicode data
ms.assetid: 44e69e60-9b35-43fe-b9c7-8cf34eaea62a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4c928062169ed7feb03f1031362530474109976a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636202"
---
# <a name="unicode-compression-implementation"></a><span data-ttu-id="61475-102">Implementazione della compressione Unicode</span><span class="sxs-lookup"><span data-stu-id="61475-102">Unicode Compression Implementation</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="61475-103">usa un'implementazione dell'algoritmo SCSU (Standard Compression Scheme for Unicode) per comprimere i valori Unicode archiviati in oggetti compressi di riga o pagina.</span><span class="sxs-lookup"><span data-stu-id="61475-103">uses an implementation of the Standard Compression Scheme for Unicode (SCSU) algorithm to compress Unicode values that are stored in row or page compressed objects.</span></span> <span data-ttu-id="61475-104">Per questi oggetti compressi, la compressione Unicode è automatica per le colonne `nchar(n)` e `nvarchar(n)`.</span><span class="sxs-lookup"><span data-stu-id="61475-104">For these compressed objects, Unicode compression is automatic for `nchar(n)` and `nvarchar(n)` columns.</span></span> <span data-ttu-id="61475-105">[!INCLUDE[ssDE](../../includes/ssde-md.md)] archivia i dati Unicode come 2 byte, indipendentemente dalle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="61475-105">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] stores Unicode data as 2 bytes, regardless of locale.</span></span> <span data-ttu-id="61475-106">Questa funzionalità è nota come codifica UCS-2.</span><span class="sxs-lookup"><span data-stu-id="61475-106">This is known as UCS-2 encoding.</span></span> <span data-ttu-id="61475-107">Per alcune impostazioni locali, l'implementazione della compressione SCSU in SQL Server consente di risparmiare fino al 50 percento di spazio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="61475-107">For some locales, the implementation of SCSU compression in SQL Server can save up to 50 percent in storage space.</span></span>  
  
## <a name="supported-data-types"></a><span data-ttu-id="61475-108">Tipi di dati supportati</span><span class="sxs-lookup"><span data-stu-id="61475-108">Supported Data Types</span></span>  
 <span data-ttu-id="61475-109">La compressione Unicode supporta i tipi di dati a lunghezza fissa `nchar(n)` e `nvarchar(n)`.</span><span class="sxs-lookup"><span data-stu-id="61475-109">Unicode compression supports the fixed-length `nchar(n)` and `nvarchar(n)` data types.</span></span> <span data-ttu-id="61475-110">I valori di dati archiviati all'esterno di righe o in colonne `nvarchar(max)` non sono compressi.</span><span class="sxs-lookup"><span data-stu-id="61475-110">Data values that are stored off row or in `nvarchar(max)` columns are not compressed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="61475-111">La compressione Unicode non è supportata per i dati `nvarchar(max)` anche archiviati nella riga.</span><span class="sxs-lookup"><span data-stu-id="61475-111">Unicode compression is not supported for `nvarchar(max)` data even if it is stored in row.</span></span> <span data-ttu-id="61475-112">Questo tipo di dati, tuttavia, può ancora trarre vantaggio dalla compressione pagina.</span><span class="sxs-lookup"><span data-stu-id="61475-112">However, this data type can still benefit from page compression.</span></span>  
  
## <a name="upgrading-from-earlier-versions-of-sql-server"></a><span data-ttu-id="61475-113">Aggiornamento da versioni precedenti di SQL Server</span><span class="sxs-lookup"><span data-stu-id="61475-113">Upgrading from Earlier Versions of SQL Server</span></span>  
 <span data-ttu-id="61475-114">Quando un database [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene aggiornato a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], le modifiche legate alla compressione Unicode non vengono apportate ad alcun oggetto di database, compresso o meno.</span><span class="sxs-lookup"><span data-stu-id="61475-114">When a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database is upgraded to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], Unicode compression-related changes are not made to any database object, compressed or uncompressed.</span></span> <span data-ttu-id="61475-115">Una volta aggiornato il database, gli effetti sugli oggetti sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="61475-115">After the database is upgraded, objects are affected as follows:</span></span>  
  
-   <span data-ttu-id="61475-116">Se l'oggetto non è compresso, non viene apportata alcuna modifica e l'oggetto continua a funzionare come in precedenza.</span><span class="sxs-lookup"><span data-stu-id="61475-116">If the object is not compressed, no changes are made and the object continues to function as it did previously.</span></span>  
  
-   <span data-ttu-id="61475-117">Gli oggetti sui quali è stata applicata la compressione di riga o di pagina continuano a funzionare come in precedenza.</span><span class="sxs-lookup"><span data-stu-id="61475-117">Row- or page-compressed objects continue to function as they did previously.</span></span> <span data-ttu-id="61475-118">I dati non compressi restano in formato non compresso finché non viene aggiornato il loro valore.</span><span class="sxs-lookup"><span data-stu-id="61475-118">Uncompressed data remains in uncompressed form until its value is updated.</span></span>  
  
-   <span data-ttu-id="61475-119">Le nuove righe inserite in una tabella sulla quale sia stata applicata la compressione di riga o di pagina vengono compresse utilizzando la compressione Unicode.</span><span class="sxs-lookup"><span data-stu-id="61475-119">New rows that are inserted into a row- or page-compressed table are compressed using Unicode compression.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="61475-120">Per sfruttare a pieno i vantaggi della compressione Unicode, l'oggetto deve essere ricompilato con la compressione di pagina o di riga.</span><span class="sxs-lookup"><span data-stu-id="61475-120">To take full advantage of the benefits of Unicode compression, the object must be rebuilt with page or row compression.</span></span>  
  
## <a name="how-unicode-compression-affects-data-storage"></a><span data-ttu-id="61475-121">Influenza della compressione Unicode sull'archiviazione dei dati</span><span class="sxs-lookup"><span data-stu-id="61475-121">How Unicode Compression Affects Data Storage</span></span>  
 <span data-ttu-id="61475-122">Quando un indice viene creato o ricompilato, oppure quando un valore viene modificato in una tabella compressa con compressione di riga o di pagina, l'indice o il valore interessato viene archiviato compresso solo se la sua dimensione compressa è inferiore alla dimensione corrente.</span><span class="sxs-lookup"><span data-stu-id="61475-122">When an index is created or rebuilt or when a value is changed in a table that was compressed with row or page compression, the affected index or value is stored compressed only if its compressed size is less than its current size.</span></span> <span data-ttu-id="61475-123">Ciò impedisce che le dimensioni delle righe in una tabella o in un indice aumentino a causa della compressione Unicode.</span><span class="sxs-lookup"><span data-stu-id="61475-123">This prevents rows in a table or index from increasing in size because of Unicode compression.</span></span>  
  
 <span data-ttu-id="61475-124">Lo spazio di archiviazione risparmiato grazie alla compressione dipende dalle caratteristiche dei dati che si stanno comprimendo e dalle impostazioni locali dei dati.</span><span class="sxs-lookup"><span data-stu-id="61475-124">The storage space that compression saves depends on the characteristics of the data that is being compressed and the locale of the data.</span></span> <span data-ttu-id="61475-125">La seguente tabella elenca i risparmi possibili in termini di spazio per diverse impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="61475-125">The following table lists the space savings that can be achieved for several locales.</span></span>  
  
|<span data-ttu-id="61475-126">Impostazioni locali</span><span class="sxs-lookup"><span data-stu-id="61475-126">Locale</span></span>|<span data-ttu-id="61475-127">Percentuale di compressione</span><span class="sxs-lookup"><span data-stu-id="61475-127">Compression percent</span></span>|  
|------------|-------------------------|  
|<span data-ttu-id="61475-128">Inglese</span><span class="sxs-lookup"><span data-stu-id="61475-128">English</span></span>|<span data-ttu-id="61475-129">50%</span><span class="sxs-lookup"><span data-stu-id="61475-129">50%</span></span>|  
|<span data-ttu-id="61475-130">Tedesco</span><span class="sxs-lookup"><span data-stu-id="61475-130">German</span></span>|<span data-ttu-id="61475-131">50%</span><span class="sxs-lookup"><span data-stu-id="61475-131">50%</span></span>|  
|<span data-ttu-id="61475-132">Hindi</span><span class="sxs-lookup"><span data-stu-id="61475-132">Hindi</span></span>|<span data-ttu-id="61475-133">50%</span><span class="sxs-lookup"><span data-stu-id="61475-133">50%</span></span>|  
|<span data-ttu-id="61475-134">Turco</span><span class="sxs-lookup"><span data-stu-id="61475-134">Turkish</span></span>|<span data-ttu-id="61475-135">48%</span><span class="sxs-lookup"><span data-stu-id="61475-135">48%</span></span>|  
|<span data-ttu-id="61475-136">Vietnamita</span><span class="sxs-lookup"><span data-stu-id="61475-136">Vietnamese</span></span>|<span data-ttu-id="61475-137">39%</span><span class="sxs-lookup"><span data-stu-id="61475-137">39%</span></span>|  
|<span data-ttu-id="61475-138">Giapponese</span><span class="sxs-lookup"><span data-stu-id="61475-138">Japanese</span></span>|<span data-ttu-id="61475-139">15%</span><span class="sxs-lookup"><span data-stu-id="61475-139">15%</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="61475-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61475-140">See Also</span></span>  
 <span data-ttu-id="61475-141">[Compressione dei dati](data-compression.md) </span><span class="sxs-lookup"><span data-stu-id="61475-141">[Data Compression](data-compression.md) </span></span>  
 <span data-ttu-id="61475-142">[sp_estimate_data_compression_savings &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-estimate-data-compression-savings-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="61475-142">[sp_estimate_data_compression_savings &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-estimate-data-compression-savings-transact-sql) </span></span>  
 <span data-ttu-id="61475-143">[Implementazione della compressione di pagina](page-compression-implementation.md) </span><span class="sxs-lookup"><span data-stu-id="61475-143">[Page Compression Implementation](page-compression-implementation.md) </span></span>  
 [<span data-ttu-id="61475-144">sys.dm_db_persisted_sku_features &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="61475-144">sys.dm_db_persisted_sku_features &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-persisted-sku-features-transact-sql)  
  
  
