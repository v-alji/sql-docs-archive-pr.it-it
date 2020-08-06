---
title: Utilizzo delle classi gestite SQLXML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- sample applications [SQLXML]
- SQLXML Managed Classes, sample applications
- examples [SQLXML], managed classes
- Managed Classes [SQLXML], samples
ms.assetid: 3f021290-00ee-44e1-af4b-33d3ba8c6302
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 634a0e4110b13931201edd026ee95028cb94e859
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716672"
---
# <a name="using-the-sqlxml-managed-classes"></a><span data-ttu-id="e449d-102">Utilizzo di classi gestite SQLXML</span><span class="sxs-lookup"><span data-stu-id="e449d-102">Using the SQLXML Managed Classes</span></span>
  <span data-ttu-id="e449d-103">In questa sezione vengono fornite applicazioni di esempio in cui viene mostrato come utilizzare le classi gestite [!INCLUDE[msCoName](../../includes/msconame-md.md)] SQLXML.</span><span class="sxs-lookup"><span data-stu-id="e449d-103">This section provides sample applications that demonstrate how to use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] SQLXML Managed Classes.</span></span>  
  
 <span data-ttu-id="e449d-104">Per informazioni sull'accesso e la modifica dei dati all' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] interno del [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework e sull'utilizzo di DiffGram per aggiornare i dati nelle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabelle, vedere [accesso alla funzionalità SQLXML nell'ambiente .NET](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/accessing-sqlxml-functionality-in-the-net-environment.md).</span><span class="sxs-lookup"><span data-stu-id="e449d-104">For information about accessing and modifying data in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] within the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework, and about using DiffGrams to update data in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables, see [Accessing SQLXML Functionality in the .NET Environment](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/accessing-sqlxml-functionality-in-the-net-environment.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e449d-105">È anche possibile scrivere applicazioni [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio per eseguire il caricamento bulk di documenti XML utilizzando il caricamento bulk XML.</span><span class="sxs-lookup"><span data-stu-id="e449d-105">You can also write [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio applications to bulk load XML documents by using XML Bulk Load.</span></span> <span data-ttu-id="e449d-106">Per ulteriori informazioni, vedere [esecuzione del caricamento bulk di dati XML &#40;SQLXML 4,0&#41;](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="e449d-106">For more information, see [Performing Bulk Load of XML Data &#40;SQLXML 4.0&#41;](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md).</span></span> <span data-ttu-id="e449d-107">È necessario aggiungere all'applicazione un riferimento alla DLL del caricamento bulk XML (Xblkld4.dll).</span><span class="sxs-lookup"><span data-stu-id="e449d-107">You must add a reference to the XML Bulk Load DLL (Xblkld4.dll) in your application.</span></span> <span data-ttu-id="e449d-108">Si tratta di una DLL COM per la quale in Visual Studio .NET viene creata automaticamente la libreria di wrapper.</span><span class="sxs-lookup"><span data-stu-id="e449d-108">This is a COM DLL for which Visual Studio .NET automatically creates the wrapper library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e449d-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e449d-109">In This Section</span></span>  
 [<span data-ttu-id="e449d-110">Esecuzione di query SQL &#40;classi gestite SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="e449d-110">Executing SQL Queries &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-4-0-net-framework-support-managed-classes.md)  
  [<span data-ttu-id="e449d-111">Esecuzione di query SQL tramite il metodo ExecuteXMLReader</span><span class="sxs-lookup"><span data-stu-id="e449d-111">Executing SQL Queries by Using the ExecuteXMLReader Method</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-sql-queries-by-using-the-executexmlreader-method.md)  
  [<span data-ttu-id="e449d-112">Elaborazione di XML sul lato client &#40;classi gestite SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="e449d-112">Processing XML on the Client Side &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/processing-xml-on-the-client-side-sqlxml-managed-classes.md)  
  [<span data-ttu-id="e449d-113">Esecuzione di query XPath &#40;classi gestite SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="e449d-113">Executing XPath Queries &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-xpath-queries-sqlxml-managed-classes.md)  
  [<span data-ttu-id="e449d-114">Esecuzione di query XPath con spazi dei nomi &#40;classi gestite SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="e449d-114">Executing XPath Queries with Namespaces &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-xpath-queries-with-namespaces-sqlxml-managed-classes.md)  
  [<span data-ttu-id="e449d-115">Esecuzione di file modello mediante la proprietà CommandText</span><span class="sxs-lookup"><span data-stu-id="e449d-115">Executing Template Files by Using the CommandText Property</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-template-files-by-using-the-commandtext-property.md)  
  [<span data-ttu-id="e449d-116">Esecuzione di file modello tramite la proprietà CommandStream</span><span class="sxs-lookup"><span data-stu-id="e449d-116">Executing Template Files by Using the CommandStream Property</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-template-files-by-using-the-commandstream-property.md)  
  [<span data-ttu-id="e449d-117">Applicazione di una trasformazione XSL &#40;classi gestite SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="e449d-117">Applying an XSL Transformation &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/applying-an-xsl-transformation-sqlxml-managed-classes.md)  
  
