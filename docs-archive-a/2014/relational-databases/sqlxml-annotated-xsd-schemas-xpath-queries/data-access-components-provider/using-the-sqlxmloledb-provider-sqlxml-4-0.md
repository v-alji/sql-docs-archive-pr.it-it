---
title: Uso del provider SQLXMLOLEDB (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- sample applications [SQLXML]
- SQLXMLOLEDB Provider, samples
- ClientSideXML property
ms.assetid: fbcefac5-29c9-478b-b0e0-d510b593f446
author: rothja
ms.author: jroth
ms.openlocfilehash: 74e3c53eecd657d610c2fe90e108e0290e9b05b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629309"
---
# <a name="using-the-sqlxmloledb-provider-sqlxml-40"></a><span data-ttu-id="c4f1a-102">Utilizzo del provider SQLXMLOLEDB (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="c4f1a-102">Using the SQLXMLOLEDB Provider (SQLXML 4.0)</span></span>
  <span data-ttu-id="c4f1a-103">Negli argomenti di questa sezione vengono fornite applicazioni ADO di esempio che illustrano l'utilizzo delle proprietà specifiche del provider SQLXMLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="c4f1a-103">The topics in this section provide ADO sample applications that illustrate the use of SQLXMLOLEDB Provider-specific properties.</span></span>  
  
## <a name="application-requirements-for-sqlxmloledb-40-provider"></a><span data-ttu-id="c4f1a-104">Requisiti dell'applicazione per il provider SQLXMLOLEDB 4.0</span><span class="sxs-lookup"><span data-stu-id="c4f1a-104">Application Requirements for SQLXMLOLEDB 4.0 Provider</span></span>  
 <span data-ttu-id="c4f1a-105">Per creare esempi reali che utilizzano SQLXMLOLEDB 4.0, è necessario effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c4f1a-105">To create working samples that use SQLXMLOLEDB 4.0, you must do the following:</span></span>  
  
1.  <span data-ttu-id="c4f1a-106">Creare un'applicazione Microsoft Visual Basic con estensione exe e aggiungere uno dei riferimenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c4f1a-106">Create a Microsoft Visual Basic .exe application and add one of the following references:</span></span>  
  
    -   <span data-ttu-id="c4f1a-107">Libreria Microsoft ActiveX Data Objects 2,6</span><span class="sxs-lookup"><span data-stu-id="c4f1a-107">Microsoft ActiveX Data Objects 2.6 Library</span></span>  
  
    -   <span data-ttu-id="c4f1a-108">Libreria Microsoft ActiveX Data Objects 2,7</span><span class="sxs-lookup"><span data-stu-id="c4f1a-108">Microsoft ActiveX Data Objects 2.7 Library</span></span>  
  
    -   <span data-ttu-id="c4f1a-109">Libreria Microsoft ActiveX Data Objects 2.8</span><span class="sxs-lookup"><span data-stu-id="c4f1a-109">Microsoft ActiveX Data Objects 2.8 Library</span></span>  
  
2.  <span data-ttu-id="c4f1a-110">Distribuire e installare SQLXML 4.0 e [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="c4f1a-110">Deploy and install SQLXML 4.0 and the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
     <span data-ttu-id="c4f1a-111">Per ulteriori informazioni, vedere i [concetti di programmazione di SQLXML 4,0](../../sqlxml/sqlxml-4-0-programming-concepts.md) e [installazione di SQL Server Native Client](../../native-client/applications/installing-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="c4f1a-111">For more information, see on [SQLXML 4.0 Programming Concepts](../../sqlxml/sqlxml-4-0-programming-concepts.md) and [Installing SQL Server Native Client](../../native-client/applications/installing-sql-server-native-client.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c4f1a-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c4f1a-112">In This Section</span></span>  
 [<span data-ttu-id="c4f1a-113">Esecuzione di query SQL &#40;provider SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="c4f1a-113">Executing SQL Queries &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-sql-queries-sqlxmloledb-provider.md)  
 <span data-ttu-id="c4f1a-114">Viene illustrato l'utilizzo di ClientSideXML e delle proprietà radice XML per eseguire query SQL.</span><span class="sxs-lookup"><span data-stu-id="c4f1a-114">Illustrates the use of the ClientSideXML and xml root properties to execute SQL queries.</span></span>  
  
 [<span data-ttu-id="c4f1a-115">Esecuzione di modelli che contengono query SQL &#40;provider SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="c4f1a-115">Executing Templates That Contain SQL Queries &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-templates-that-contain-sql-queries-sqlxmloledb-provider.md)  
 <span data-ttu-id="c4f1a-116">Viene illustrato l'utilizzo della proprietà ClientSideXML.</span><span class="sxs-lookup"><span data-stu-id="c4f1a-116">Illustrates the use of the ClientSideXML property.</span></span>  
  
 [<span data-ttu-id="c4f1a-117">Esecuzione di query XPath &#40;provider SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="c4f1a-117">Executing XPath Queries &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-xpath-queries-sqlxmloledb-provider.md)  
 <span data-ttu-id="c4f1a-118">Viene illustrato l'utilizzo delle proprietà ClientSideXML, Path di base e schema di mapping.</span><span class="sxs-lookup"><span data-stu-id="c4f1a-118">Illustrates the use of the ClientSideXML, Base Path, and Mapping Schema properties.</span></span>  
  
 [<span data-ttu-id="c4f1a-119">Esecuzione di query XPath con spazi dei nomi &#40;provider SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="c4f1a-119">Executing XPath Queries with Namespaces &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-xpath-queries-with-namespaces-sqlxmloledb-provider.md)  
 <span data-ttu-id="c4f1a-120">Viene illustrato come eseguire una query sugli schemi qualificati con lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c4f1a-120">Illustrates how to query against namespace-qualified schemas.</span></span>  
  
 [<span data-ttu-id="c4f1a-121">Esecuzione di modelli che contengono query XPath &#40;provider SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="c4f1a-121">Executing Templates That Contain XPath Queries &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-templates-that-contain-xpath-queries-sqlxmloledb-provider.md)  
 <span data-ttu-id="c4f1a-122">Viene illustrato come eseguire modelli con query SQL utilizzando le proprietà ClientSideXML, percorso di base e schema di mapping.</span><span class="sxs-lookup"><span data-stu-id="c4f1a-122">Illustrates how to execute templates with SQL queries using the ClientSideXML, Base Path, and Mapping Schema properties.</span></span>  
  
 [<span data-ttu-id="c4f1a-123">Applicazione di una trasformazione XSL &#40;provider SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="c4f1a-123">Applying an XSL Transformation &#40;SQLXMLOLEDB Provider&#41;</span></span>](applying-an-xsl-transformation-sqlxmloledb-provider.md)  
 <span data-ttu-id="c4f1a-124">Viene illustrato l'utilizzo delle proprietà ClientSideXML e XSL nell'applicazione di una trasformazione XSL.</span><span class="sxs-lookup"><span data-stu-id="c4f1a-124">Illustrates the use of the ClientSideXML and xsl properties in applying an XSL transformation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4f1a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4f1a-125">See Also</span></span>  
 [<span data-ttu-id="c4f1a-126">Requisiti di sistema per SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="c4f1a-126">System Requirements for SQL Server Native Client</span></span>](../../native-client/system-requirements-for-sql-server-native-client.md)  
  
  
