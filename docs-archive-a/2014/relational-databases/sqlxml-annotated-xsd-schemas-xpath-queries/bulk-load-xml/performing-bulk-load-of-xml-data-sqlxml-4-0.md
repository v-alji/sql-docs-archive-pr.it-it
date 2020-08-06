---
title: Esecuzione del caricamento bulk di dati XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XML Bulk Load [SQLXML]
- bulk load [SQLXML]
- data insertions [SQLXML]
- SQLXML, bulk loading
- XSD schemas [SQLXML], XML Bulk Load
- XDR schemas [SQLXML], XML Bulk Load
- inserting data
ms.assetid: 3708b493-322e-4f3c-9b27-441d0c0ee346
author: rothja
ms.author: jroth
ms.openlocfilehash: ec540ff082b02fa43b9abd9f294752073eb68d5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711823"
---
# <a name="performing-bulk-load-of-xml-data-sqlxml-40"></a><span data-ttu-id="29978-102">Esecuzione del caricamento bulk di dati XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="29978-102">Performing Bulk Load of XML Data (SQLXML 4.0)</span></span>
  <span data-ttu-id="29978-103">Il caricamento bulk XML è un oggetto COM autonomo che consente di caricare dati XML semistrutturati nelle tabelle Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29978-103">XML Bulk Load is a standalone COM object that allows you to load semistructured XML data into Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tables.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="29978-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="29978-104">In This Section</span></span>  
 [<span data-ttu-id="29978-105">Introduzione al caricamento bulk XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="29978-105">Introduction to XML Bulk Load &#40;SQLXML 4.0&#41;</span></span>](introduction-to-xml-bulk-load-sqlxml-4-0.md)  
 <span data-ttu-id="29978-106">Vengono fornite informazioni generali sul caricamento bulk di dati XML con l'utilità di caricamento bulk XML.</span><span class="sxs-lookup"><span data-stu-id="29978-106">Provides general information about bulk loading XML data with the XML Bulk Load utility.</span></span> <span data-ttu-id="29978-107">Negli argomenti sono inclusi il flusso dei dati XML e le operazioni di caricamento bulk in e non in transazioni.</span><span class="sxs-lookup"><span data-stu-id="29978-107">Topics include XML data streaming and transacted vs. nontransacted bulk load operations.</span></span>  
  
 [<span data-ttu-id="29978-108">Processo di generazione di record &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="29978-108">Record Generation Process &#40;SQLXML 4.0&#41;</span></span>](record-generation-process-sqlxml-4-0.md)  
 <span data-ttu-id="29978-109">Vengono illustrati il processo e le regole in base ai quali vengono generati i record per il caricamento bulk XML.</span><span class="sxs-lookup"><span data-stu-id="29978-109">Describes the process and rules by which records are generated for XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="29978-110">Interpretazione dell'annotazione &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="29978-110">Annotation Interpretation &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sqlxml-4-0.md)  
 <span data-ttu-id="29978-111">Viene illustrato come vengono interpretate le annotazioni degli schemi XSD e XDR dal caricamento bulk XML.</span><span class="sxs-lookup"><span data-stu-id="29978-111">Describes how XML Bulk Load interprets annotations in XSD and XDR schemas.</span></span>  
  
 [<span data-ttu-id="29978-112">SQL Server modello a oggetti per il caricamento bulk XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="29978-112">SQL Server XML Bulk Load Object Model &#40;SQLXML 4.0&#41;</span></span>](sql-server-xml-bulk-load-object-model-sqlxml-4-0.md)  
 <span data-ttu-id="29978-113">Descrive l'oggetto SQLXMLBulkLoad e i relativi metodi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="29978-113">Describes the SQLXMLBulkLoad object and its methods and properties.</span></span>  
  
 [<span data-ttu-id="29978-114">Esempi di caricamento bulk XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="29978-114">XML Bulk Load Examples &#40;SQLXML 4.0&#41;</span></span>](xml-bulk-load-examples-sqlxml-4-0.md)  
 <span data-ttu-id="29978-115">Viene fornito il codice di esempio che utilizza il caricamento bulk XML.</span><span class="sxs-lookup"><span data-stu-id="29978-115">Provides example code that uses XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="29978-116">Tipi di dati e comportamento del caricamento bulk XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="29978-116">Data Types and XML Bulk Load Behavior &#40;SQLXML 4.0&#41;</span></span>](data-types-and-xml-bulk-load-behavior-sqlxml-4-0.md)  
 <span data-ttu-id="29978-117">Viene illustrato il comportamento del caricamento bulk XML con i diversi tipi in XSD e XDR.</span><span class="sxs-lookup"><span data-stu-id="29978-117">Describes XML Bulk Load Behavior with different types in XSD and XDR.</span></span>  
  
 [<span data-ttu-id="29978-118">Linee guida e limitazioni del caricamento bulk XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="29978-118">Guidelines and Limitations of XML Bulk Load &#40;SQLXML 4.0&#41;</span></span>](guidelines-and-limitations-of-xml-bulk-load-sqlxml-4-0.md)  
 <span data-ttu-id="29978-119">Vengono elencati alcuni problemi da tener presente quando si utilizza il caricamento bulk XML.</span><span class="sxs-lookup"><span data-stu-id="29978-119">Lists some issues to be aware of when working with XML Bulk Load.</span></span>  
  
  
