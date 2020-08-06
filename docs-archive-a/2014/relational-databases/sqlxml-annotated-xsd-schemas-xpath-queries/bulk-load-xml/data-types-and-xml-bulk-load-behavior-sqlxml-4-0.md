---
title: Tipi di dati e comportamento del caricamento bulk XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- bulk load [SQLXML], data types
- data types [SQLXML], XML Bulk Load
- XML Bulk Load [SQLXML], data types
ms.assetid: d1ac1939-1f6c-4398-b7a7-a79ca608a4f1
author: rothja
ms.author: jroth
ms.openlocfilehash: 34b03423f3bb88166d0d9ce5b0df450d4455e7ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87634961"
---
# <a name="data-types-and-xml-bulk-load-behavior-sqlxml-40"></a><span data-ttu-id="62d80-102">Tipi di dati e comportamento del caricamento bulk XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="62d80-102">Data Types and XML Bulk Load Behavior (SQLXML 4.0)</span></span>
  <span data-ttu-id="62d80-103">I tipi di dati specificati nello schema di mapping (tipo XSD o XDR e `sql:datatype`) vengono in genere ignorati ad eccezione dei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="62d80-103">The data types that are specified in the mapping schema (XSD or XDR type and `sql:datatype`) are generally ignored, except in the following cases:</span></span>  
  
 <span data-ttu-id="62d80-104">In XSD:</span><span class="sxs-lookup"><span data-stu-id="62d80-104">In XSD:</span></span>  
  
-   <span data-ttu-id="62d80-105">Se il tipo è `dateTime` o `time`, è necessario specificare `sql:datatype` in quanto il caricamento bulk XML esegue la conversione dei dati prima di inviare i dati a Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62d80-105">If the type is `dateTime` or `time`, you must specify the `sql:datatype` because XML Bulk Load performs data conversion before sending the data to Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="62d80-106">Quando si esegue il caricamento bulk in una colonna di `uniqueidentifier` tipo in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e il valore XSD è un GUID che include parentesi graffe ({e}), è necessario specificare **SQL: DataType = "uniqueidentifier"** per rimuovere le parentesi graffe prima che il valore venga inserito nella colonna.</span><span class="sxs-lookup"><span data-stu-id="62d80-106">When you are bulk loading into a column of `uniqueidentifier` type in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and the XSD value is a GUID that includes braces ({ and }), you must specify **sql:datatype="uniqueidentifier"** to remove the braces before the value is inserted into the column.</span></span> <span data-ttu-id="62d80-107">Se non si specifica `sql:datatype`, il valore viene inviato con le parentesi graffe e l'inserimento non viene  eseguito.</span><span class="sxs-lookup"><span data-stu-id="62d80-107">If `sql:datatype` is not specified, the value is sent with the braces and the insert fails.</span></span>  
  
 <span data-ttu-id="62d80-108">Per ulteriori informazioni su `sql:datatype` , vedere [coercizione del tipo di dati e l'annotazione sql: DataType &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-using/data-type-coercions-and-the-sql-datatype-annotation-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="62d80-108">For more information about `sql:datatype`, see [Data Type Coercions and the sql:datatype Annotation &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-using/data-type-coercions-and-the-sql-datatype-annotation-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="62d80-109">In XDR:</span><span class="sxs-lookup"><span data-stu-id="62d80-109">In XDR:</span></span>  
  
-   <span data-ttu-id="62d80-110">Se `dt:type` è `datetime`, `time`, `dateTime.tz` o `time.tz`, è necessario specificare i tipi di dati `dt:type` e `sql:datatype`, in quanto il caricamento bulk XML esegue la conversione dei dati prima di inviarli a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62d80-110">If the `dt:type` is `datetime`, `time`, `dateTime.tz`, or `time.tz`, you must specify both the `dt:type` and `sql:datatype` data types because XML Bulk Load performs data conversion before it sends the data to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="62d80-111">Se i dati XML sono di tipo `uuid` , è `sql:datatype` necessario specificare. è necessario anche **DT: Type = "UUID"** , a meno che i dati non siano dati di tipo stringa.</span><span class="sxs-lookup"><span data-stu-id="62d80-111">If your XML data is of type `uuid`, `sql:datatype` must be specified; **dt:type="uuid"** is also required, unless the data is string data.</span></span> <span data-ttu-id="62d80-112">Se non si specifica `dt:uuid`, il caricamento bulk XML accetta stringhe con parentesi graffe e le rimuove, se necessario.</span><span class="sxs-lookup"><span data-stu-id="62d80-112">If you do not specify `dt:uuid`, XML Bulk Load accepts strings with braces (and removes them if needed).</span></span>  
  
-   <span data-ttu-id="62d80-113">Se i dati XML sono di tipo `bin.base64` o `bin.hex`, è necessario specificare il tipo di dati XML con `dt:type`.</span><span class="sxs-lookup"><span data-stu-id="62d80-113">If the XML data is `bin.base64` or `bin.hex`, you must specify the XML data type with `dt:type`.</span></span> <span data-ttu-id="62d80-114">Il caricamento bulk XML carica quindi i dati in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] come rappresentazione esadecimale dei dati.</span><span class="sxs-lookup"><span data-stu-id="62d80-114">XML Bulk Load then loads the data into [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as a hexadecimal representation of the data.</span></span>  
  
  
