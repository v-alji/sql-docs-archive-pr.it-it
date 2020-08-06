---
title: Dati XML (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XML [SQL Server]
- XML [SQL Server], about XML
ms.assetid: 6a1793c9-9856-485c-aac5-88fda62f61a8
author: rothja
ms.author: jroth
ms.openlocfilehash: 48ddec1de8492c86aecfd80ea960c4a01673c24f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625255"
---
# <a name="xml-data-sql-server"></a><span data-ttu-id="bab46-102">Dati XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="bab46-102">XML Data (SQL Server)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bab46-103">offre una potente piattaforma per lo sviluppo di applicazioni complete per la gestione di dati semistrutturati.</span><span class="sxs-lookup"><span data-stu-id="bab46-103">provides a powerful platform for developing rich applications for semi-structured data management.</span></span> <span data-ttu-id="bab46-104">Il supporto per XML è integrato in tutti i componenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e include i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="bab46-104">Support for XML is integrated into all the components in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and includes the following:</span></span>  
  
-   <span data-ttu-id="bab46-105">Tipo di dati `xml`.</span><span class="sxs-lookup"><span data-stu-id="bab46-105">The `xml` data type.</span></span> <span data-ttu-id="bab46-106">I valori XML possono essere archiviati in modo nativo in una colonna con tipo di dati `xml` che può essere tipizzata in base a una raccolta di XML Schema oppure lasciata non tipizzata.</span><span class="sxs-lookup"><span data-stu-id="bab46-106">XML values can be stored natively in an `xml` data type column that can be typed according to a collection of XML schemas, or left untyped.</span></span> <span data-ttu-id="bab46-107">È possibile indicizzare la colonna XML.</span><span class="sxs-lookup"><span data-stu-id="bab46-107">You can index the XML column.</span></span>  
  
-   <span data-ttu-id="bab46-108">Possibilità di specificare una query XQuery sui dati XML archiviati in colonne e variabili di tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="bab46-108">The ability to specify an XQuery query against XML data stored in columns and variables of the `xml` type.</span></span>  
  
-   <span data-ttu-id="bab46-109">Funzionalità avanzate di OPENROWSET per consentire il caricamento bulk dei dati XML.</span><span class="sxs-lookup"><span data-stu-id="bab46-109">Enhancements to OPENROWSET to allow bulk loading of XML data.</span></span>  
  
-   <span data-ttu-id="bab46-110">Clausola FOR XML per recuperare dati relazionali in formato XML.</span><span class="sxs-lookup"><span data-stu-id="bab46-110">The FOR XML clause, to retrieve relational data in XML format.</span></span>  
  
-   <span data-ttu-id="bab46-111">Funzione OPENXML per recuperare i dati XML in formato relazionale.</span><span class="sxs-lookup"><span data-stu-id="bab46-111">The OPENXML function, to retrieve XML data in relational format.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bab46-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="bab46-112">In This Section</span></span>  
 [<span data-ttu-id="bab46-113">Colonne e tipo di dati XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bab46-113">XML Data Type and Columns &#40;SQL Server&#41;</span></span>](xml-data-type-and-columns-sql-server.md)  
 [<span data-ttu-id="bab46-114">Indici XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bab46-114">XML Indexes &#40;SQL Server&#41;</span></span>](xml-indexes-sql-server.md)  
 [<span data-ttu-id="bab46-115">Raccolte di XML Schema &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bab46-115">XML Schema Collections &#40;SQL Server&#41;</span></span>](xml-schema-collections-sql-server.md)  
 [<span data-ttu-id="bab46-116">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bab46-116">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
 [<span data-ttu-id="bab46-117">OPENXML &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bab46-117">OPENXML &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/openxml-transact-sql)  
  
## <a name="related-content"></a><span data-ttu-id="bab46-118">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="bab46-118">Related Content</span></span>  
 [<span data-ttu-id="bab46-119">Esempi di importazione ed esportazione bulk di documenti XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bab46-119">Examples of Bulk Import and Export of XML Documents &#40;SQL Server&#41;</span></span>](../import-export/examples-of-bulk-import-and-export-of-xml-documents-sql-server.md)  
 [<span data-ttu-id="bab46-120">Riferimento al linguaggio XQuery &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bab46-120">XQuery Language Reference &#40;SQL Server&#41;</span></span>](/sql/xquery/xquery-language-reference-sql-server)  
  
