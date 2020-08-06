---
title: Tipi di dati supportati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: a7380ef0-c9d7-49e4-b6de-fad34752b9f3
author: rothja
ms.author: jroth
ms.openlocfilehash: a7dda500486c39a66f871d5934f957028fc51e9d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724664"
---
# <a name="supported-data-types"></a><span data-ttu-id="7f234-102">Tipi di dati supportati</span><span class="sxs-lookup"><span data-stu-id="7f234-102">Supported Data Types</span></span>
  <span data-ttu-id="7f234-103">I tipi di dati seguenti sono **supportati** nelle tabelle ottimizzate per la memoria e nelle stored procedure compilate in modo nativo:</span><span class="sxs-lookup"><span data-stu-id="7f234-103">The following data types are **supported** in memory-optimized tables and natively compiled stored procedures:</span></span>  
  
 <span data-ttu-id="7f234-104">**Tipi di dati numerici**</span><span class="sxs-lookup"><span data-stu-id="7f234-104">**Numeric Data Types**</span></span>  
  
|<span data-ttu-id="7f234-105">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7f234-105">Data type</span></span>|<span data-ttu-id="7f234-106">Per ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="7f234-106">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="7f234-107">int</span><span class="sxs-lookup"><span data-stu-id="7f234-107">int</span></span>|[<span data-ttu-id="7f234-108">int, bigint, smallint e tinyint &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7f234-108">int, bigint, smallint, and tinyint &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)|  
|<span data-ttu-id="7f234-109">bigint</span><span class="sxs-lookup"><span data-stu-id="7f234-109">bigint</span></span>|[<span data-ttu-id="7f234-110">int, bigint, smallint e tinyint &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7f234-110">int, bigint, smallint, and tinyint &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)|  
|<span data-ttu-id="7f234-111">smallint</span><span class="sxs-lookup"><span data-stu-id="7f234-111">smallint</span></span>|[<span data-ttu-id="7f234-112">int, bigint, smallint e tinyint &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7f234-112">int, bigint, smallint, and tinyint &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)|  
|<span data-ttu-id="7f234-113">TINYINT</span><span class="sxs-lookup"><span data-stu-id="7f234-113">tinyint</span></span>|[<span data-ttu-id="7f234-114">int, bigint, smallint e tinyint &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7f234-114">int, bigint, smallint, and tinyint &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)|  
|<span data-ttu-id="7f234-115">decimal</span><span class="sxs-lookup"><span data-stu-id="7f234-115">decimal</span></span>|[<span data-ttu-id="7f234-116">decimal e numeric &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7f234-116">decimal and numeric &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/decimal-and-numeric-transact-sql)|  
|<span data-ttu-id="7f234-117">NUMERIC</span><span class="sxs-lookup"><span data-stu-id="7f234-117">numeric</span></span>|[<span data-ttu-id="7f234-118">decimal e numeric &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7f234-118">decimal and numeric &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/decimal-and-numeric-transact-sql)|  
|<span data-ttu-id="7f234-119">float</span><span class="sxs-lookup"><span data-stu-id="7f234-119">float</span></span>|[<span data-ttu-id="7f234-120">float e real &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7f234-120">float and real &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/float-and-real-transact-sql)|  
|<span data-ttu-id="7f234-121">real</span><span class="sxs-lookup"><span data-stu-id="7f234-121">real</span></span>|[<span data-ttu-id="7f234-122">float e real &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7f234-122">float and real &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/float-and-real-transact-sql)|  
|<span data-ttu-id="7f234-123">money</span><span class="sxs-lookup"><span data-stu-id="7f234-123">money</span></span>|[<span data-ttu-id="7f234-124">money e smallmoney &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7f234-124">money and smallmoney &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/money-and-smallmoney-transact-sql)|  
|<span data-ttu-id="7f234-125">SMALLMONEY</span><span class="sxs-lookup"><span data-stu-id="7f234-125">smallmoney</span></span>|[<span data-ttu-id="7f234-126">money e smallmoney &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7f234-126">money and smallmoney &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/money-and-smallmoney-transact-sql)|  
  
 <span data-ttu-id="7f234-127">**Tipi di dati stringa**</span><span class="sxs-lookup"><span data-stu-id="7f234-127">**String Data Types**</span></span>  
  
|<span data-ttu-id="7f234-128">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7f234-128">Data type</span></span>|<span data-ttu-id="7f234-129">Per ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="7f234-129">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="7f234-130">char(n)</span><span class="sxs-lookup"><span data-stu-id="7f234-130">char(n)</span></span>|[<span data-ttu-id="7f234-131">char e varchar &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7f234-131">char and varchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/char-and-varchar-transact-sql)|  
|<span data-ttu-id="7f234-132">varchar (n) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7f234-132">varchar(n) <sup>1</sup></span></span>|[<span data-ttu-id="7f234-133">char e varchar &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7f234-133">char and varchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/char-and-varchar-transact-sql)|  
|<span data-ttu-id="7f234-134">nchar(n)</span><span class="sxs-lookup"><span data-stu-id="7f234-134">nchar(n)</span></span>|[<span data-ttu-id="7f234-135">nchar e nvarchar &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7f234-135">nchar and nvarchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql)|  
|<span data-ttu-id="7f234-136">nvarchar (n) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7f234-136">nvarchar(n) <sup>1</sup></span></span>|[<span data-ttu-id="7f234-137">nchar e nvarchar &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7f234-137">nchar and nvarchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql)|  
|<span data-ttu-id="7f234-138">sysname</span><span class="sxs-lookup"><span data-stu-id="7f234-138">sysname</span></span>|[<span data-ttu-id="7f234-139">nchar e nvarchar &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7f234-139">nchar and nvarchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql)|  
  
 <span data-ttu-id="7f234-140"><sup>1</sup> il limite è di 8060 byte per riga totale, conteggio (n) in tipi a lunghezza variabile.</span><span class="sxs-lookup"><span data-stu-id="7f234-140"><sup>1</sup> Limitation is 8060 bytes per row total, counting (n) in variable-length types.</span></span>  
  
 <span data-ttu-id="7f234-141">Per informazioni sulle regole di confronto supportate, vedere [regole di confronto e tabelle codici](../../database-engine/collations-and-code-pages.md).</span><span class="sxs-lookup"><span data-stu-id="7f234-141">For information about supported collations, see [Collations and Code Pages](../../database-engine/collations-and-code-pages.md).</span></span>  
  
 <span data-ttu-id="7f234-142">**Tipi di dati di data e ora**</span><span class="sxs-lookup"><span data-stu-id="7f234-142">**Date and Time Data Types**</span></span>  
  
|<span data-ttu-id="7f234-143">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7f234-143">Data type</span></span>|<span data-ttu-id="7f234-144">Per ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="7f234-144">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="7f234-145">date</span><span class="sxs-lookup"><span data-stu-id="7f234-145">date</span></span>|[<span data-ttu-id="7f234-146">date &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7f234-146">date &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/date-transact-sql)|  
|<span data-ttu-id="7f234-147">time</span><span class="sxs-lookup"><span data-stu-id="7f234-147">time</span></span>|[<span data-ttu-id="7f234-148">time &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7f234-148">time &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/time-transact-sql)|  
|<span data-ttu-id="7f234-149">Datetime</span><span class="sxs-lookup"><span data-stu-id="7f234-149">datetime</span></span>|[<span data-ttu-id="7f234-150">datetime &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7f234-150">datetime &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/datetime-transact-sql)|  
|<span data-ttu-id="7f234-151">datetime2</span><span class="sxs-lookup"><span data-stu-id="7f234-151">datetime2</span></span>|[<span data-ttu-id="7f234-152">datetime2 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7f234-152">datetime2 &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/datetime2-transact-sql)|  
|<span data-ttu-id="7f234-153">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="7f234-153">smalldatetime</span></span>|[<span data-ttu-id="7f234-154">smalldatetime &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7f234-154">smalldatetime &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/smalldatetime-transact-sql)|  
  
 <span data-ttu-id="7f234-155">**Tipi di dati binari**</span><span class="sxs-lookup"><span data-stu-id="7f234-155">**Binary Data Types**</span></span>  
  
|<span data-ttu-id="7f234-156">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7f234-156">Data type</span></span>|<span data-ttu-id="7f234-157">Per ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="7f234-157">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="7f234-158">bit</span><span class="sxs-lookup"><span data-stu-id="7f234-158">bit</span></span>|[<span data-ttu-id="7f234-159">bit &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7f234-159">bit &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/bit-transact-sql)|  
|<span data-ttu-id="7f234-160">binary(n)</span><span class="sxs-lookup"><span data-stu-id="7f234-160">binary(n)</span></span>|[<span data-ttu-id="7f234-161">binary e varbinary &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7f234-161">binary and varbinary &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/binary-and-varbinary-transact-sql)|  
|<span data-ttu-id="7f234-162">varbinary (n) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7f234-162">varbinary(n) <sup>1</sup></span></span>|[<span data-ttu-id="7f234-163">binary e varbinary &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7f234-163">binary and varbinary &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/binary-and-varbinary-transact-sql)|  
  
 <span data-ttu-id="7f234-164"><sup>1</sup> il limite è di 8060 byte per riga totale, conteggio (n) in tipi a lunghezza variabile.</span><span class="sxs-lookup"><span data-stu-id="7f234-164"><sup>1</sup> Limitation is 8060 bytes per row total, counting (n) in variable-length types.</span></span>  
  
 <span data-ttu-id="7f234-165">**Altri tipi di dati**</span><span class="sxs-lookup"><span data-stu-id="7f234-165">**Other data types**</span></span>  
  
|<span data-ttu-id="7f234-166">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7f234-166">Data type</span></span>|<span data-ttu-id="7f234-167">Per ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="7f234-167">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="7f234-168">UNIQUEIDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="7f234-168">uniqueidentifier</span></span>|[<span data-ttu-id="7f234-169">uniqueidentifier &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7f234-169">uniqueidentifier &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/uniqueidentifier-transact-sql)|  
  
 <span data-ttu-id="7f234-170">**Tipi di dati non supportati**</span><span class="sxs-lookup"><span data-stu-id="7f234-170">**Unsupported Data Types**</span></span>  
  
 <span data-ttu-id="7f234-171">I tipi di dati indicati di seguito non sono supportati:</span><span class="sxs-lookup"><span data-stu-id="7f234-171">The following data types are not supported:</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="7f234-172">DATETIMEOFFSET</span><span class="sxs-lookup"><span data-stu-id="7f234-172">DATETIMEOFFSET</span></span>|<span data-ttu-id="7f234-173">GEOGRAPHY</span><span class="sxs-lookup"><span data-stu-id="7f234-173">GEOGRAPHY</span></span>|<span data-ttu-id="7f234-174">GEOMETRY</span><span class="sxs-lookup"><span data-stu-id="7f234-174">GEOMETRY</span></span>|  
|<span data-ttu-id="7f234-175">HIERARCHYID</span><span class="sxs-lookup"><span data-stu-id="7f234-175">HIERARCHYID</span></span>|<span data-ttu-id="7f234-176">Oggetti di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="7f234-176">Large Objects (LOBs).</span></span> <span data-ttu-id="7f234-177">Ad esempio, varchar(max), nvarchar(max), varbinary(max), image, xml, text e ntext.</span><span class="sxs-lookup"><span data-stu-id="7f234-177">For example, varchar(max), nvarchar(max), varbinary(max), image, xml, text, and ntext.</span></span>|<span data-ttu-id="7f234-178">ROWVERSION</span><span class="sxs-lookup"><span data-stu-id="7f234-178">ROWVERSION</span></span>|  
|<span data-ttu-id="7f234-179">sql_variant</span><span class="sxs-lookup"><span data-stu-id="7f234-179">sql_variant</span></span>|<span data-ttu-id="7f234-180">Funzioni CLR</span><span class="sxs-lookup"><span data-stu-id="7f234-180">CLR functions</span></span>|<span data-ttu-id="7f234-181">Tipi definiti dall'utente (UDT)</span><span class="sxs-lookup"><span data-stu-id="7f234-181">User-defined types (UDTs)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7f234-182">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f234-182">See Also</span></span>  
 <span data-ttu-id="7f234-183">[Supporto di Transact-SQL per OLTP in memoria](transact-sql-support-for-in-memory-oltp.md) </span><span class="sxs-lookup"><span data-stu-id="7f234-183">[Transact-SQL Support for In-Memory OLTP](transact-sql-support-for-in-memory-oltp.md) </span></span>  
 <span data-ttu-id="7f234-184">[Implementazione di colonne LOB in una tabella ottimizzata per la memoria](../../database-engine/implementing-lob-columns-in-a-memory-optimized-table.md) </span><span class="sxs-lookup"><span data-stu-id="7f234-184">[Implementing LOB Columns in a Memory-Optimized Table](../../database-engine/implementing-lob-columns-in-a-memory-optimized-table.md) </span></span>  
 [<span data-ttu-id="7f234-185">Implementazione di SQL_VARIANT in una tabella con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="7f234-185">Implementing SQL_VARIANT in a Memory-Optimized Table</span></span>](implementing-sql-variant-in-a-memory-optimized-table.md)  
  
  
