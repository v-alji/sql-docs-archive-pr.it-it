---
title: Utilizzo di query XPath in SQLXML 4,0 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML]
- annotated XSD schemas, XPath queries
- queries [SQLXML], XPath
- XML views [SQLXML]
ms.assetid: 7814d099-81ec-4fb8-894a-729cdbb5015a
author: rothja
ms.author: jroth
ms.openlocfilehash: 80d82513b22d2a50aedb37955a210dd33746db86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87634945"
---
# <a name="using-xpath-queries-in-sqlxml-40"></a><span data-ttu-id="337d8-102">Utilizzo di query XPath in SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="337d8-102">Using XPath Queries in SQLXML 4.0</span></span>
  <span data-ttu-id="337d8-103">Il supporto in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] degli schemi XSD con annotazioni consente di creare viste XML dei dati relazionali archiviati nel database.</span><span class="sxs-lookup"><span data-stu-id="337d8-103">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] support for annotated XSD schemas allows you to create XML views of the relational data stored in the database.</span></span> <span data-ttu-id="337d8-104">È possibile utilizzare un subset del linguaggio XPath per eseguire una query sulle viste XML create da uno schema XSD con annotazioni.</span><span class="sxs-lookup"><span data-stu-id="337d8-104">You can use a subset of the XPath language to query the XML views created by an annotated XSD schema.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="337d8-105">Per comprendere le query XPath in SQLXML 4.0, è necessario avere familiarità con le viste XML e con concetti correlati quali i modelli e lo schema di mapping.</span><span class="sxs-lookup"><span data-stu-id="337d8-105">To understand XPath queries in SQLXML 4.0, you must be familiar with XML views and related concepts such as templates and mapping schema.</span></span> <span data-ttu-id="337d8-106">Per ulteriori informazioni, vedere [Introduzione agli schemi XSD con Annotazioni &#40;SQLXML 4,0&#41;](../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="337d8-106">For more information, see [Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span></span> <span data-ttu-id="337d8-107">Per ulteriori informazioni su XPath, vedere la pagina relativa allo standard XPath definito dal World Wide Web Consortium (W3C) in http://www.w3.org/TR/xpath .</span><span class="sxs-lookup"><span data-stu-id="337d8-107">For more information about XPath, see the XPath standard defined by the World Wide Web Consortium (W3C) at http://www.w3.org/TR/xpath.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="337d8-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="337d8-108">In This Section</span></span>  
 [<span data-ttu-id="337d8-109">Introduzione all'utilizzo di query XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="337d8-109">Introduction to Using XPath Queries &#40;SQLXML 4.0&#41;</span></span>](introduction-to-using-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="337d8-110">Vengono fornite informazioni introduttive sulle query XPath in SQLXML 4.0, incluse le funzionalità supportate e non supportate dalla specifica XPath di W3C.</span><span class="sxs-lookup"><span data-stu-id="337d8-110">Provides introductory information about XPath queries in SQLXML 4.0, including supported and unsupported functionality from the W3C XPath specification.</span></span>  
  
 [<span data-ttu-id="337d8-111">Specifica del percorso &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="337d8-111">Specifying a Location Path &#40;SQLXML 4.0&#41;</span></span>](location-path/specifying-a-location-path-sqlxml-4-0.md)  
 <span data-ttu-id="337d8-112">Viene descritto come specificare i percorsi nelle query XPath.</span><span class="sxs-lookup"><span data-stu-id="337d8-112">Describes how to specify location paths in XPath queries.</span></span>  
  
 [<span data-ttu-id="337d8-113">Query XPath di esempio &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="337d8-113">Sample XPath Queries &#40;SQLXML 4.0&#41;</span></span>](samples/sample-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="337d8-114">Vengono fornite query Xpath di esempio per SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="337d8-114">Provides sample XPath queries for SQLXML 4.0.</span></span>  
  
 [<span data-ttu-id="337d8-115">Tipi di dati XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="337d8-115">XPath Data Types &#40;SQLXML 4.0&#41;</span></span>](xpath-data-types-sqlxml-4-0.md)  
 <span data-ttu-id="337d8-116">Vengono descritti i tipi di dati XPath che sono significativamente diversi dai tipi di dati [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e XSD.</span><span class="sxs-lookup"><span data-stu-id="337d8-116">Describes XPath data types, which are significantly different from those of both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and XSD.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="337d8-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="337d8-117">See Also</span></span>  
 [<span data-ttu-id="337d8-118">Formattazione XML sul lato client &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="337d8-118">Client-side XML Formatting &#40;SQLXML 4.0&#41;</span></span>](../sqlxml/formatting/client-side-xml-formatting-sqlxml-4-0.md)  
  
  
