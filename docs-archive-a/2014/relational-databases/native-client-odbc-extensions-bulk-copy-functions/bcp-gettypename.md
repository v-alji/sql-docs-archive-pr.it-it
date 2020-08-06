---
title: bcp_gettypename | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_gettypename
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_gettypename function
ms.assetid: 65f036d1-f60e-4b8a-97b3-76fccf0dfed4
author: rothja
ms.author: jroth
ms.openlocfilehash: b2d92498b9d863fa2cb700ec4d88868c0984c4d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626765"
---
# <a name="bcp_gettypename"></a><span data-ttu-id="1ae56-102">bcp_gettypename</span><span class="sxs-lookup"><span data-stu-id="1ae56-102">bcp_gettypename</span></span>
  <span data-ttu-id="1ae56-103">Restituisce il nome del tipo SQL per il nome di un tipo di token specificato.</span><span class="sxs-lookup"><span data-stu-id="1ae56-103">Returns the SQL type name for a specified BCP type token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ae56-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1ae56-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_gettypename (  
INT   
token  
,  
DBBOOL   
fIsMaxType  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="1ae56-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="1ae56-105">Arguments</span></span>  
 <span data-ttu-id="1ae56-106">*token*</span><span class="sxs-lookup"><span data-stu-id="1ae56-106">*token*</span></span>  
 <span data-ttu-id="1ae56-107">Valore che indica un token di tipo BCP.</span><span class="sxs-lookup"><span data-stu-id="1ae56-107">A value indicating a BCP type token.</span></span>  
  
 <span data-ttu-id="1ae56-108">*campo*</span><span class="sxs-lookup"><span data-stu-id="1ae56-108">*field*</span></span>  
 <span data-ttu-id="1ae56-109">Indica se il token richiesto è un tipo max.</span><span class="sxs-lookup"><span data-stu-id="1ae56-109">Indicates if token requested is a max type.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="1ae56-110">Restituisce</span><span class="sxs-lookup"><span data-stu-id="1ae56-110">Returns</span></span>  
 <span data-ttu-id="1ae56-111">Una stringa che contiene il nome del tipo SQL che corrisponde al tipo BCP.</span><span class="sxs-lookup"><span data-stu-id="1ae56-111">A string containing the SQL type name corresponding to the BCP type.</span></span> <span data-ttu-id="1ae56-112">Se viene specificato un tipo BCP non valido, viene restituita una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="1ae56-112">If an invalid BCP type is specified, an empty string is returned..</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ae56-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1ae56-113">Remarks</span></span>  
 <span data-ttu-id="1ae56-114">I token del tipo BCP vengono definiti nel file di intestazione sqlncli.h e nella libreria sqlncli11.lib.</span><span class="sxs-lookup"><span data-stu-id="1ae56-114">The BCP type tokens are defined in the sqlncli.h header file and the sqlncli11.lib library.</span></span>  
  
 <span data-ttu-id="1ae56-115">Nella tabella seguente viene specificato quali sono i possibili tipi BCP, se si tratta di tipi max e l'output previsto.</span><span class="sxs-lookup"><span data-stu-id="1ae56-115">The table below specifies the possible BCP types, whether or not they are max types, and the expected output.</span></span>  
  
|<span data-ttu-id="1ae56-116">Nome del tipo BCP</span><span class="sxs-lookup"><span data-stu-id="1ae56-116">BCP type name</span></span>|<span data-ttu-id="1ae56-117">MaxType</span><span class="sxs-lookup"><span data-stu-id="1ae56-117">MaxType</span></span>|<span data-ttu-id="1ae56-118">Output</span><span class="sxs-lookup"><span data-stu-id="1ae56-118">Output</span></span>|  
|-------------------|-------------|------------|  
|`SQLDECIMAL`|<span data-ttu-id="1ae56-119">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-119">Either</span></span>|<span data-ttu-id="1ae56-120">**decimal**</span><span class="sxs-lookup"><span data-stu-id="1ae56-120">**decimal**</span></span>|  
|`SQLNUMERIC`|<span data-ttu-id="1ae56-121">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-121">Either</span></span>|<span data-ttu-id="1ae56-122">**numeric**</span><span class="sxs-lookup"><span data-stu-id="1ae56-122">**numeric**</span></span>|  
|`SQLINT1`|<span data-ttu-id="1ae56-123">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-123">Either</span></span>|<span data-ttu-id="1ae56-124">**tinyint**</span><span class="sxs-lookup"><span data-stu-id="1ae56-124">**tinyint**</span></span>|  
|`SQLINT2`|<span data-ttu-id="1ae56-125">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-125">Either</span></span>|<span data-ttu-id="1ae56-126">**smallint**</span><span class="sxs-lookup"><span data-stu-id="1ae56-126">**smallint**</span></span>|  
|`SQLINT4`|<span data-ttu-id="1ae56-127">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-127">Either</span></span>|<span data-ttu-id="1ae56-128">**int**</span><span class="sxs-lookup"><span data-stu-id="1ae56-128">**int**</span></span>|  
|`SQLMONEY`|<span data-ttu-id="1ae56-129">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-129">Either</span></span>|<span data-ttu-id="1ae56-130">**money**</span><span class="sxs-lookup"><span data-stu-id="1ae56-130">**money**</span></span>|  
|`SQLFLT8`|<span data-ttu-id="1ae56-131">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-131">Either</span></span>|<span data-ttu-id="1ae56-132">**float**</span><span class="sxs-lookup"><span data-stu-id="1ae56-132">**float**</span></span>|  
|`SQLDATETIME`|<span data-ttu-id="1ae56-133">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-133">Either</span></span>|<span data-ttu-id="1ae56-134">**datetime**</span><span class="sxs-lookup"><span data-stu-id="1ae56-134">**datetime**</span></span>|  
|`SQLBITN`|<span data-ttu-id="1ae56-135">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-135">Either</span></span>|<span data-ttu-id="1ae56-136">**bit-null**</span><span class="sxs-lookup"><span data-stu-id="1ae56-136">**bit-null**</span></span>|  
|`SQLBIT`|<span data-ttu-id="1ae56-137">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-137">Either</span></span>|<span data-ttu-id="1ae56-138">**bit**</span><span class="sxs-lookup"><span data-stu-id="1ae56-138">**bit**</span></span>|  
|`SQLBIGCHAR`|<span data-ttu-id="1ae56-139">No</span><span class="sxs-lookup"><span data-stu-id="1ae56-139">No</span></span>|<span data-ttu-id="1ae56-140">**char**</span><span class="sxs-lookup"><span data-stu-id="1ae56-140">**char**</span></span>|  
|`SQLCHARACTER`|<span data-ttu-id="1ae56-141">No</span><span class="sxs-lookup"><span data-stu-id="1ae56-141">No</span></span>|<span data-ttu-id="1ae56-142">**char**</span><span class="sxs-lookup"><span data-stu-id="1ae56-142">**char**</span></span>|  
|`SQLBIGVARCHAR`|<span data-ttu-id="1ae56-143">No</span><span class="sxs-lookup"><span data-stu-id="1ae56-143">No</span></span>|<span data-ttu-id="1ae56-144">**varchar**</span><span class="sxs-lookup"><span data-stu-id="1ae56-144">**varchar**</span></span>|  
|`SQLVARCHAR`|<span data-ttu-id="1ae56-145">No</span><span class="sxs-lookup"><span data-stu-id="1ae56-145">No</span></span>|<span data-ttu-id="1ae56-146">**varchar**</span><span class="sxs-lookup"><span data-stu-id="1ae56-146">**varchar**</span></span>|  
|`SQLTEXT`|<span data-ttu-id="1ae56-147">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-147">Either</span></span>|<span data-ttu-id="1ae56-148">**text**</span><span class="sxs-lookup"><span data-stu-id="1ae56-148">**text**</span></span>|  
|`SQLBIGBINARY`|<span data-ttu-id="1ae56-149">No</span><span class="sxs-lookup"><span data-stu-id="1ae56-149">No</span></span>|<span data-ttu-id="1ae56-150">**binary**</span><span class="sxs-lookup"><span data-stu-id="1ae56-150">**binary**</span></span>|  
|`SQLBINARY`|<span data-ttu-id="1ae56-151">No</span><span class="sxs-lookup"><span data-stu-id="1ae56-151">No</span></span>|<span data-ttu-id="1ae56-152">**Binario**</span><span class="sxs-lookup"><span data-stu-id="1ae56-152">**Binary**</span></span>|  
|`SQLBIGVARBINARY`|<span data-ttu-id="1ae56-153">No</span><span class="sxs-lookup"><span data-stu-id="1ae56-153">No</span></span>|<span data-ttu-id="1ae56-154">**Varbinary**</span><span class="sxs-lookup"><span data-stu-id="1ae56-154">**Varbinary**</span></span>|  
|`SQLVARBINARY`|<span data-ttu-id="1ae56-155">No</span><span class="sxs-lookup"><span data-stu-id="1ae56-155">No</span></span>|<span data-ttu-id="1ae56-156">**Varbinary**</span><span class="sxs-lookup"><span data-stu-id="1ae56-156">**Varbinary**</span></span>|  
|`SQLIMAGE`|<span data-ttu-id="1ae56-157">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-157">Either</span></span>|<span data-ttu-id="1ae56-158">**Immagine**</span><span class="sxs-lookup"><span data-stu-id="1ae56-158">**Image**</span></span>|  
|`SQLINTN`|<span data-ttu-id="1ae56-159">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-159">Either</span></span>|<span data-ttu-id="1ae56-160">**int-null**</span><span class="sxs-lookup"><span data-stu-id="1ae56-160">**int-null**</span></span>|  
|`SQLDATETIMN`|<span data-ttu-id="1ae56-161">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-161">Either</span></span>|<span data-ttu-id="1ae56-162">**datetime-null**</span><span class="sxs-lookup"><span data-stu-id="1ae56-162">**datetime-null**</span></span>|  
|`SQLMONEYN`|<span data-ttu-id="1ae56-163">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-163">Either</span></span>|<span data-ttu-id="1ae56-164">**money-null**</span><span class="sxs-lookup"><span data-stu-id="1ae56-164">**money-null**</span></span>|  
|`SQLFLTN`|<span data-ttu-id="1ae56-165">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-165">Either</span></span>|<span data-ttu-id="1ae56-166">**float-null**</span><span class="sxs-lookup"><span data-stu-id="1ae56-166">**float-null**</span></span>|  
|`SQLAOPSUM`|<span data-ttu-id="1ae56-167">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-167">Either</span></span>|<span data-ttu-id="1ae56-168">**Somma**</span><span class="sxs-lookup"><span data-stu-id="1ae56-168">**Sum**</span></span>|  
|`SQLAOPAVG`|<span data-ttu-id="1ae56-169">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-169">Either</span></span>|<span data-ttu-id="1ae56-170">**AVG**</span><span class="sxs-lookup"><span data-stu-id="1ae56-170">**Avg**</span></span>|  
|`SQLAOPCNT`|<span data-ttu-id="1ae56-171">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-171">Either</span></span>|<span data-ttu-id="1ae56-172">**Numero**</span><span class="sxs-lookup"><span data-stu-id="1ae56-172">**Count**</span></span>|  
|`SQLAOPMIN`|<span data-ttu-id="1ae56-173">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-173">Either</span></span>|<span data-ttu-id="1ae56-174">**Min**</span><span class="sxs-lookup"><span data-stu-id="1ae56-174">**Min**</span></span>|  
|`SQLAOPMAX`|<span data-ttu-id="1ae56-175">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-175">Either</span></span>|<span data-ttu-id="1ae56-176">**Max**</span><span class="sxs-lookup"><span data-stu-id="1ae56-176">**Max**</span></span>|  
|`SQLDATETIM4`|<span data-ttu-id="1ae56-177">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-177">Either</span></span>|<span data-ttu-id="1ae56-178">**smalldatetime**</span><span class="sxs-lookup"><span data-stu-id="1ae56-178">**smalldatetime**</span></span>|  
|`SQLMONEY4`|<span data-ttu-id="1ae56-179">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-179">Either</span></span>|<span data-ttu-id="1ae56-180">**Smallmoney**</span><span class="sxs-lookup"><span data-stu-id="1ae56-180">**Smallmoney**</span></span>|  
|`SQLFLT4`|<span data-ttu-id="1ae56-181">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-181">Either</span></span>|<span data-ttu-id="1ae56-182">**Reale**</span><span class="sxs-lookup"><span data-stu-id="1ae56-182">**Real**</span></span>|  
|`SQLUNIQUEID`|<span data-ttu-id="1ae56-183">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-183">Either</span></span>|<span data-ttu-id="1ae56-184">**uniqueidentifier**</span><span class="sxs-lookup"><span data-stu-id="1ae56-184">**uniqueidentifier**</span></span>|  
|`SQLNCHAR`|<span data-ttu-id="1ae56-185">No</span><span class="sxs-lookup"><span data-stu-id="1ae56-185">No</span></span>|<span data-ttu-id="1ae56-186">**Nchar**</span><span class="sxs-lookup"><span data-stu-id="1ae56-186">**Nchar**</span></span>|  
|`SQLNVARCHAR`|<span data-ttu-id="1ae56-187">No</span><span class="sxs-lookup"><span data-stu-id="1ae56-187">No</span></span>|<span data-ttu-id="1ae56-188">**Nvarchar**</span><span class="sxs-lookup"><span data-stu-id="1ae56-188">**Nvarchar**</span></span>|  
|`SQLNTEXT`|<span data-ttu-id="1ae56-189">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-189">Either</span></span>|<span data-ttu-id="1ae56-190">**Ntext**</span><span class="sxs-lookup"><span data-stu-id="1ae56-190">**Ntext**</span></span>|  
|`SQLVARIANT`|<span data-ttu-id="1ae56-191">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-191">Either</span></span>|<span data-ttu-id="1ae56-192">**sql_variant**</span><span class="sxs-lookup"><span data-stu-id="1ae56-192">**sql_variant**</span></span>|  
|`SQLINT8`|<span data-ttu-id="1ae56-193">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-193">Either</span></span>|<span data-ttu-id="1ae56-194">**Bigint**</span><span class="sxs-lookup"><span data-stu-id="1ae56-194">**Bigint**</span></span>|  
|`SQLCHARACTER`|<span data-ttu-id="1ae56-195">Sì</span><span class="sxs-lookup"><span data-stu-id="1ae56-195">Yes</span></span>|<span data-ttu-id="1ae56-196">**ntext**</span><span class="sxs-lookup"><span data-stu-id="1ae56-196">**varchar(max)**</span></span>|  
|`SQLBIGCHAR`|<span data-ttu-id="1ae56-197">Sì</span><span class="sxs-lookup"><span data-stu-id="1ae56-197">Yes</span></span>|<span data-ttu-id="1ae56-198">**ntext**</span><span class="sxs-lookup"><span data-stu-id="1ae56-198">**varchar(max)**</span></span>|  
|`SQLBIGVARCHAR`|<span data-ttu-id="1ae56-199">Sì</span><span class="sxs-lookup"><span data-stu-id="1ae56-199">Yes</span></span>|<span data-ttu-id="1ae56-200">**ntext**</span><span class="sxs-lookup"><span data-stu-id="1ae56-200">**varchar(max)**</span></span>|  
|`SQLVARCHAR`|<span data-ttu-id="1ae56-201">Sì</span><span class="sxs-lookup"><span data-stu-id="1ae56-201">Yes</span></span>|<span data-ttu-id="1ae56-202">**ntext**</span><span class="sxs-lookup"><span data-stu-id="1ae56-202">**varchar(max)**</span></span>|  
|`SQLBINARY`|<span data-ttu-id="1ae56-203">Sì</span><span class="sxs-lookup"><span data-stu-id="1ae56-203">Yes</span></span>|<span data-ttu-id="1ae56-204">**varbinary(max)**</span><span class="sxs-lookup"><span data-stu-id="1ae56-204">**varbinary(max)**</span></span>|  
|`SQLBIGBINARY`|<span data-ttu-id="1ae56-205">Sì</span><span class="sxs-lookup"><span data-stu-id="1ae56-205">Yes</span></span>|<span data-ttu-id="1ae56-206">**varbinary(max)**</span><span class="sxs-lookup"><span data-stu-id="1ae56-206">**varbinary(max)**</span></span>|  
|`SQLBIGVARBINARY`|<span data-ttu-id="1ae56-207">Sì</span><span class="sxs-lookup"><span data-stu-id="1ae56-207">Yes</span></span>|<span data-ttu-id="1ae56-208">**varbinary(max)**</span><span class="sxs-lookup"><span data-stu-id="1ae56-208">**varbinary(max)**</span></span>|  
|`SQLVARBINARY`|<span data-ttu-id="1ae56-209">Sì</span><span class="sxs-lookup"><span data-stu-id="1ae56-209">Yes</span></span>|<span data-ttu-id="1ae56-210">**varbinary(max)**</span><span class="sxs-lookup"><span data-stu-id="1ae56-210">**varbinary(max)**</span></span>|  
|`SQLNCHAR`|<span data-ttu-id="1ae56-211">Sì</span><span class="sxs-lookup"><span data-stu-id="1ae56-211">Yes</span></span>|<span data-ttu-id="1ae56-212">**nvarchar(max)**</span><span class="sxs-lookup"><span data-stu-id="1ae56-212">**nvarchar(max)**</span></span>|  
|`SQLNVARCHAR`|<span data-ttu-id="1ae56-213">Sì</span><span class="sxs-lookup"><span data-stu-id="1ae56-213">Yes</span></span>|<span data-ttu-id="1ae56-214">**nvarchar(max)**</span><span class="sxs-lookup"><span data-stu-id="1ae56-214">**nvarchar(max)**</span></span>|  
|`SQLXML`|<span data-ttu-id="1ae56-215">Sì</span><span class="sxs-lookup"><span data-stu-id="1ae56-215">Yes</span></span>|<span data-ttu-id="1ae56-216">**Xml**</span><span class="sxs-lookup"><span data-stu-id="1ae56-216">**Xml**</span></span>|  
|`SQLUDT`|<span data-ttu-id="1ae56-217">Prima o dopo</span><span class="sxs-lookup"><span data-stu-id="1ae56-217">Either</span></span>|<span data-ttu-id="1ae56-218">**UDT**</span><span class="sxs-lookup"><span data-stu-id="1ae56-218">**Udt**</span></span>|  
  
## <a name="bcp_gettypename-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="1ae56-219">Supporto di bcp_gettypename per le caratteristiche avanzate di data e ora</span><span class="sxs-lookup"><span data-stu-id="1ae56-219">bcp_gettypename Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="1ae56-220">I valori dei parametri del token per i tipi data/ora vengono descritti nella colonna "tipo in sqlncli. h" della tabella nelle [modifiche della copia bulk per i tipi di data e ora avanzati &#40;OLE DB e ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="1ae56-220">The token parameter values for date/time types are described in the "Type in sqlncli.h" column of the table in [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span> <span data-ttu-id="1ae56-221">Il valore restituito si trova nella riga corrispondente della colonna "Tipo di archiviazione di file".</span><span class="sxs-lookup"><span data-stu-id="1ae56-221">The returned value is in the corresponding row of the "File storage type" column.</span></span>  
  
 <span data-ttu-id="1ae56-222">Per ulteriori informazioni, vedere [miglioramenti di data e ora &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="1ae56-222">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ae56-223">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ae56-223">See Also</span></span>  
 [<span data-ttu-id="1ae56-224">Funzioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="1ae56-224">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
