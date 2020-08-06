---
title: Schemi XSD con annotazioni in SQLXML 4,0 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XSD schemas
- SQLXML, annotated XSD schemas
- mapping schema [SQLXML]
- XSD schemas [SQLXML]
- XSD schemas [SQLXML], annotations
- schemas [SQLXML]
ms.assetid: eecd0d5f-d3dd-4d20-9586-19820410ad47
author: rothja
ms.author: jroth
ms.openlocfilehash: f97e01b0ade98edc432869c8772fbd4720df9a08
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87634936"
---
# <a name="annotated-xsd-schemas-in-sqlxml-40"></a><span data-ttu-id="50e09-102">Schemi XSD con annotazioni in SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="50e09-102">Annotated XSD Schemas in SQLXML 4.0</span></span>
  <span data-ttu-id="50e09-103">In questa sezione vengono fornite informazioni sull'utilizzo degli schemi XSD con annotazioni in SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="50e09-103">This section provides information about using annotated XSD schemas in SQLXML 4.0.</span></span> <span data-ttu-id="50e09-104">Nelle versioni precedenti di SQLXML, una funzionalità simile veniva fornita con gli schemi XDR (XML-Data Reduced).</span><span class="sxs-lookup"><span data-stu-id="50e09-104">In previous versions of SQLXML, similar functionality was provided with XML-Data Reduced (XDR) schemas.</span></span> <span data-ttu-id="50e09-105">In questa sezione vengono inoltre fornite le informazioni su XDR per le applicazioni legacy.</span><span class="sxs-lookup"><span data-stu-id="50e09-105">This section also provides XDR information for legacy applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="50e09-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="50e09-106">In This Section</span></span>  
 [<span data-ttu-id="50e09-107">Introduzione agli schemi XSD con annotazioni &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="50e09-107">Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;</span></span>](introduction-to-annotated-xsd-schemas-sqlxml-4-0.md)  
 <span data-ttu-id="50e09-108">Viene fornita una panoramica degli schemi XSD con annotazioni in SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="50e09-108">Provides an overview of annotated XSD schemas in SQLXML 4.0.</span></span>  
  
 [<span data-ttu-id="50e09-109">Utilizzo di annotazioni negli schemi XSD &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="50e09-109">Using Annotations in XSD Schemas &#40;SQLXML 4.0&#41;</span></span>](../../sqlxml-annotated-xsd-schemas-using/using-annotations-in-xsd-schemas-sqlxml-4-0.md)  
 <span data-ttu-id="50e09-110">Viene illustrato l'utilizzo delle annotazioni negli schemi XSD in molti scenari e vengono forniti esempi.</span><span class="sxs-lookup"><span data-stu-id="50e09-110">Describes how to use annotations in XSD schemas in numerous scenarios, and provides examples.</span></span>  
  
 [<span data-ttu-id="50e09-111">Utilizzo di schemi XSD con annotazioni nelle query &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="50e09-111">Using Annotated XSD Schemas in Queries &#40;SQLXML 4.0&#41;</span></span>](using-annotated-xsd-schemas-in-queries-sqlxml-4-0.md)  
 <span data-ttu-id="50e09-112">Viene illustrato l'utilizzo degli schemi XSD con annotazioni nelle query.</span><span class="sxs-lookup"><span data-stu-id="50e09-112">Describes how to use annotated XSD schemas in queries.</span></span>  
  
 [<span data-ttu-id="50e09-113">Conversione di schemi XDR con annotazioni in schemi XSD equivalenti &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="50e09-113">Converting Annotated XDR Schemas to Equivalent XSD Schemas &#40;SQLXML 4.0&#41;</span></span>](converting-annotated-xdr-schemas-to-equivalent-xsd-schemas-sqlxml-4-0.md)  
 <span data-ttu-id="50e09-114">Viene illustrata la conversione degli schemi XDR negli schemi XSD equivalenti per SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="50e09-114">Describes how to convert XDR schemas to the equivalent XSD schemas for SQLXML 4.0.</span></span>  
  
 [<span data-ttu-id="50e09-115">Schemi XDR con annotazioni &#40;deprecati in SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="50e09-115">Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;</span></span>](annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md)  
 <span data-ttu-id="50e09-116">Le versioni precedenti di SQLXML supportavano le annotazioni negli schemi XDR.</span><span class="sxs-lookup"><span data-stu-id="50e09-116">Previous versions of SQLXML supported annotations in XDR schemas.</span></span> <span data-ttu-id="50e09-117">Gli schemi XDR con annotazioni sono deprecati in SQLXML 4.0. Questa sezione viene tuttavia fornita come riferimento per le applicazioni legacy.</span><span class="sxs-lookup"><span data-stu-id="50e09-117">Annotated XDR schemas are deprecated in SQLXML 4.0, but this section is provided as a reference for legacy applications.</span></span>  
  
## <a name="other-resources"></a><span data-ttu-id="50e09-118">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="50e09-118">Other Resources</span></span>  
 <span data-ttu-id="50e09-119">Ulteriori informazioni sul linguaggio di definizione di XML Schema (XSD), sul linguaggio XML Path (XPath) e su Extensible Stylesheet Language Transformations (XSLT) sono disponibili nei siti Web seguenti:</span><span class="sxs-lookup"><span data-stu-id="50e09-119">You can find more information about XML Schema Definition language (XSD), XML Path language (XPath), and Extensible Stylesheet Language Transformations (XSLT) at the following Web sites:</span></span>  
  
-   <span data-ttu-id="50e09-120">XML Schema Part 0: primer, raccomandazione W3C (http://www.w3.org/TR/xmlschema-0/)</span><span class="sxs-lookup"><span data-stu-id="50e09-120">XML Schema Part 0: Primer, W3C Recommendation (http://www.w3.org/TR/xmlschema-0/)</span></span>  
  
-   <span data-ttu-id="50e09-121">XML Schema Part 1: Structures, raccomandazione W3C (http://www.w3.org/TR/xmlschema-1/)</span><span class="sxs-lookup"><span data-stu-id="50e09-121">XML Schema Part 1: Structures, W3C Recommendation (http://www.w3.org/TR/xmlschema-1/)</span></span>  
  
-   <span data-ttu-id="50e09-122">XML Schema Part 2: Datatypes, raccomandazione W3C (http://www.w3.org/TR/xmlschema-2/)</span><span class="sxs-lookup"><span data-stu-id="50e09-122">XML Schema Part 2:Datatypes, W3C Recommendation (http://www.w3.org/TR/xmlschema-2/)</span></span>  
  
-   <span data-ttu-id="50e09-123">XPath (XML Path Language) (http://www.w3.org/TR/xpath)</span><span class="sxs-lookup"><span data-stu-id="50e09-123">XML Path Language (XPath) (http://www.w3.org/TR/xpath)</span></span>  
  
-   <span data-ttu-id="50e09-124">Trasformazioni XSL (XSLT) (http://www.w3.org/TR/xslt)</span><span class="sxs-lookup"><span data-stu-id="50e09-124">XSL Transformations (XSLT) (http://www.w3.org/TR/xslt)</span></span>  
  
  
