---
title: Tipi di dati dell'istanza di Oracle CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: eec13d8d-c15a-4542-bfc4-da66b1a6bfe0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 71d4ce02db89c1bfd11fe9a3a3535fc92fbc49fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712275"
---
# <a name="oracle-cdc-instance-data-types"></a><span data-ttu-id="66bda-102">Tipi di dati dell'istanza di Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="66bda-102">Oracle CDC Instance Data Types</span></span>
  <span data-ttu-id="66bda-103">L'istanza di Oracle CDC supporta la maggior parte dei tipi di dati Oracle.</span><span class="sxs-lookup"><span data-stu-id="66bda-103">The Oracle CDC Instance supports most Oracle data types.</span></span> <span data-ttu-id="66bda-104">Nelle sezioni seguenti vengono descritti i tipi di dati supportati e non.</span><span class="sxs-lookup"><span data-stu-id="66bda-104">The following sections describe the supported data types and the non-supported data types.</span></span>  
  
## <a name="supported-data-types"></a><span data-ttu-id="66bda-105">Tipi di dati supportati</span><span class="sxs-lookup"><span data-stu-id="66bda-105">Supported Data Types</span></span>  
 <span data-ttu-id="66bda-106">Nella tabella seguente vengono descritti i tipi di dati Oracle che è possibile acquisire e il relativo mapping predefinito a tipi di dati SQL Server nelle tabelle delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="66bda-106">The following table describes the Oracle data types that can be captured and their default mapping to SQL Server data types in the change tables.</span></span> <span data-ttu-id="66bda-107">Quando si aggiunge un'istanza di acquisizione per una tabella Oracle di origine, è possibile eseguire l'override di alcuni mapping.</span><span class="sxs-lookup"><span data-stu-id="66bda-107">When adding a capture instance for a source Oracle table, you can override some of these mappings.</span></span>  
  
|<span data-ttu-id="66bda-108">Tipo di dati del database Oracle</span><span class="sxs-lookup"><span data-stu-id="66bda-108">Oracle Database Data Type</span></span>|<span data-ttu-id="66bda-109">Tipo di dati di SQL Server</span><span class="sxs-lookup"><span data-stu-id="66bda-109">SQL Server Data Type</span></span>|  
|-------------------------------|--------------------------|  
|<span data-ttu-id="66bda-110">BINARY_FLOAT</span><span class="sxs-lookup"><span data-stu-id="66bda-110">BINARY_FLOAT</span></span>|<span data-ttu-id="66bda-111">real</span><span class="sxs-lookup"><span data-stu-id="66bda-111">REAL</span></span>|  
|<span data-ttu-id="66bda-112">BINARY_DOUBLE</span><span class="sxs-lookup"><span data-stu-id="66bda-112">BINARY_DOUBLE</span></span>|<span data-ttu-id="66bda-113">FLOAT</span><span class="sxs-lookup"><span data-stu-id="66bda-113">FLOAT</span></span>|  
|<span data-ttu-id="66bda-114">CHAR</span><span class="sxs-lookup"><span data-stu-id="66bda-114">CHAR</span></span>|<span data-ttu-id="66bda-115">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="66bda-115">NVARCHAR</span></span>|  
|<span data-ttu-id="66bda-116">DATE</span><span class="sxs-lookup"><span data-stu-id="66bda-116">DATE</span></span>|<span data-ttu-id="66bda-117">DATETIME</span><span class="sxs-lookup"><span data-stu-id="66bda-117">DATETIME</span></span>|  
|<span data-ttu-id="66bda-118">FLOAT</span><span class="sxs-lookup"><span data-stu-id="66bda-118">FLOAT</span></span>|<span data-ttu-id="66bda-119">FLOAT</span><span class="sxs-lookup"><span data-stu-id="66bda-119">FLOAT</span></span>|  
|<span data-ttu-id="66bda-120">INT</span><span class="sxs-lookup"><span data-stu-id="66bda-120">INT</span></span>|<span data-ttu-id="66bda-121">NUMERIC (38)</span><span class="sxs-lookup"><span data-stu-id="66bda-121">NUMERIC (38)</span></span>|  
|<span data-ttu-id="66bda-122">INTERVAL</span><span class="sxs-lookup"><span data-stu-id="66bda-122">INTERVAL</span></span>|<span data-ttu-id="66bda-123">DATETIME</span><span class="sxs-lookup"><span data-stu-id="66bda-123">DATETIME</span></span>|  
|<span data-ttu-id="66bda-124">NCHAR</span><span class="sxs-lookup"><span data-stu-id="66bda-124">NCHAR</span></span>|<span data-ttu-id="66bda-125">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="66bda-125">NVARCHAR</span></span>|  
|<span data-ttu-id="66bda-126">NUMBER</span><span class="sxs-lookup"><span data-stu-id="66bda-126">NUMBER</span></span>|<span data-ttu-id="66bda-127">FLOAT</span><span class="sxs-lookup"><span data-stu-id="66bda-127">FLOAT</span></span>|  
|<span data-ttu-id="66bda-128">NVARCHAR2</span><span class="sxs-lookup"><span data-stu-id="66bda-128">NAVARCHAR2</span></span>|<span data-ttu-id="66bda-129">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="66bda-129">NVARCHAR</span></span>|  
|<span data-ttu-id="66bda-130">RAW</span><span class="sxs-lookup"><span data-stu-id="66bda-130">RAW</span></span>|<span data-ttu-id="66bda-131">VARBINARY</span><span class="sxs-lookup"><span data-stu-id="66bda-131">VARBINARY</span></span>|  
|<span data-ttu-id="66bda-132">real</span><span class="sxs-lookup"><span data-stu-id="66bda-132">REAL</span></span>|<span data-ttu-id="66bda-133">FLOAT</span><span class="sxs-lookup"><span data-stu-id="66bda-133">FLOAT</span></span>|  
|<span data-ttu-id="66bda-134">timestamp</span><span class="sxs-lookup"><span data-stu-id="66bda-134">TIMESTAMP</span></span>|<span data-ttu-id="66bda-135">DATETIME2</span><span class="sxs-lookup"><span data-stu-id="66bda-135">DATETIME2</span></span>|  
|<span data-ttu-id="66bda-136">TIMESTAMP WITH TIME ZONE</span><span class="sxs-lookup"><span data-stu-id="66bda-136">TIMESTAMP WITH TIME ZONE</span></span>|<span data-ttu-id="66bda-137">VARCHAR (37)</span><span class="sxs-lookup"><span data-stu-id="66bda-137">VARCHAR (37)</span></span>|  
|<span data-ttu-id="66bda-138">TIMESTAMP WITH LOCAL TIME ZONE</span><span class="sxs-lookup"><span data-stu-id="66bda-138">TIMESTAMP WITH LOCAL TIME ZONE</span></span>|<span data-ttu-id="66bda-139">VARCHAR (37)</span><span class="sxs-lookup"><span data-stu-id="66bda-139">VARCHAR (37)</span></span>|  
|<span data-ttu-id="66bda-140">VARCHAR2</span><span class="sxs-lookup"><span data-stu-id="66bda-140">VARCHAR2</span></span>|<span data-ttu-id="66bda-141">VARCHAR</span><span class="sxs-lookup"><span data-stu-id="66bda-141">VARCHAR</span></span>|  
|<span data-ttu-id="66bda-142">XMLTYPE</span><span class="sxs-lookup"><span data-stu-id="66bda-142">XMLTYPE</span></span>|<span data-ttu-id="66bda-143">NVARCHAR (MAX)</span><span class="sxs-lookup"><span data-stu-id="66bda-143">NVARCHAR (MAX)</span></span>|  
  
## <a name="non-supported-data-types"></a><span data-ttu-id="66bda-144">Tipi di dati non supportati</span><span class="sxs-lookup"><span data-stu-id="66bda-144">Non-Supported Data Types</span></span>  
 <span data-ttu-id="66bda-145">Non è possibile acquisire le tabelle Oracle di origine con colonne dei tipi di dati Oracle seguenti.</span><span class="sxs-lookup"><span data-stu-id="66bda-145">Source Oracle tables with columns of the following Oracle data types cannot be captured.</span></span> <span data-ttu-id="66bda-146">Le colonne acquisite con questi tipi di dati risulteranno Null; tuttavia, una modifica del loro valore viene indicata nella maschera di modifica delle tabelle acquisite.</span><span class="sxs-lookup"><span data-stu-id="66bda-146">Captured columns with these data types will show as null; however, a change in their value is indicated in the change mask of the captured tables.</span></span>  
  
-   <span data-ttu-id="66bda-147">LONG</span><span class="sxs-lookup"><span data-stu-id="66bda-147">LONG</span></span>  
  
-   <span data-ttu-id="66bda-148">XMLTYPE</span><span class="sxs-lookup"><span data-stu-id="66bda-148">XMLTYPE</span></span>  
  
-   <span data-ttu-id="66bda-149">BLOB</span><span class="sxs-lookup"><span data-stu-id="66bda-149">BLOB</span></span>  
  
-   <span data-ttu-id="66bda-150">CLOB</span><span class="sxs-lookup"><span data-stu-id="66bda-150">CLOB</span></span>  
  
 <span data-ttu-id="66bda-151">Non è possibile acquisire le tabelle Oracle di origine con colonne dei tipi di dati Oracle seguenti.</span><span class="sxs-lookup"><span data-stu-id="66bda-151">Source Oracle tables with columns of the following Oracle data types cannot be captured.</span></span>  
  
-   <span data-ttu-id="66bda-152">BFILE</span><span class="sxs-lookup"><span data-stu-id="66bda-152">BFILE</span></span>  
  
-   <span data-ttu-id="66bda-153">ROWID</span><span class="sxs-lookup"><span data-stu-id="66bda-153">ROWID</span></span>  
  
-   <span data-ttu-id="66bda-154">REF</span><span class="sxs-lookup"><span data-stu-id="66bda-154">REF</span></span>  
  
-   <span data-ttu-id="66bda-155">UROWID</span><span class="sxs-lookup"><span data-stu-id="66bda-155">UROWID</span></span>  
  
-   <span data-ttu-id="66bda-156">Tabella nidificata</span><span class="sxs-lookup"><span data-stu-id="66bda-156">Nested Table</span></span>  
  
 <span data-ttu-id="66bda-157">Se in una tabella sono presenti i tipi di dati seguenti, non sarà possibile ottenere dati per alcuna colonna della tabella tramite LogMinder:</span><span class="sxs-lookup"><span data-stu-id="66bda-157">If the following data types are present in a table they will prevent the LogMinder from getting any data for any column of the table:</span></span>  
  
-   <span data-ttu-id="66bda-158">Tipi di dati definiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="66bda-158">User-defined data types</span></span>  
  
-   <span data-ttu-id="66bda-159">VARRAY</span><span class="sxs-lookup"><span data-stu-id="66bda-159">VARRAY</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66bda-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66bda-160">See Also</span></span>  
 <span data-ttu-id="66bda-161">[Progettazione Change Data Capture per Oracle di Attunity](change-data-capture-designer-for-oracle-by-attunity.md) </span><span class="sxs-lookup"><span data-stu-id="66bda-161">[Change Data Capture Designer for Oracle by Attunity](change-data-capture-designer-for-oracle-by-attunity.md) </span></span>  
 [<span data-ttu-id="66bda-162">Istanza di Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="66bda-162">The Oracle CDC Instance</span></span>](the-oracle-cdc-instance.md)  
  
  
