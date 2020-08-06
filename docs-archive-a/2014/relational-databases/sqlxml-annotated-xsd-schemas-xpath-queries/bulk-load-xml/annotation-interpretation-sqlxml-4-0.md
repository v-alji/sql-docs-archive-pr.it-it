---
title: Interpretazione delle annotazioni (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XSD schemas, XML Bulk Load
- XML Bulk Load [SQLXML], annotation intepretations
- annotations [SQLXML]
- bulk load [SQLXML], annotation interpretations
- annotated XDR schemas, XML Bulk Load
ms.assetid: 1c46bdb6-2812-4a13-b60b-7101c04b299f
author: rothja
ms.author: jroth
ms.openlocfilehash: c31d56f7dd577b4b5a5b582eb0e3b1db312109a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87634965"
---
# <a name="annotation-interpretation-sqlxml-40"></a><span data-ttu-id="9404b-102">Interpretazione delle annotazioni (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="9404b-102">Annotation Interpretation (SQLXML 4.0)</span></span>
  <span data-ttu-id="9404b-103">Negli argomenti riportati in questa sezione viene descritto in che modo il caricamento bulk XML interpreta le annotazioni nello schema XSD.</span><span class="sxs-lookup"><span data-stu-id="9404b-103">The topics in this section describe how XML Bulk Load interprets annotations in the XSD schema.</span></span> <span data-ttu-id="9404b-104">Il comportamento descritto è applicabile anche alle annotazioni nello schema XDR.</span><span class="sxs-lookup"><span data-stu-id="9404b-104">The behavior described here also applies to the annotations in the XDR schema.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9404b-105">Nelle informazioni contenute in questi argomenti vengono descritte solo le annotazioni utilizzate durante l'elaborazione del caricamento bulk XML.</span><span class="sxs-lookup"><span data-stu-id="9404b-105">The information in these topics describes only the annotations used by XML Bulk Load in its processing.</span></span> <span data-ttu-id="9404b-106">Per un elenco completo delle annotazioni per lo schema XSD supportate da SQLXML 4,0, vedere [utilizzo di annotazioni negli schemi xsd &#40;sqlxml 4,0&#41;](../../sqlxml-annotated-xsd-schemas-using/using-annotations-in-xsd-schemas-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="9404b-106">For a complete list of annotations for the XSD schema that are supported by SQLXML 4.0, see [Using Annotations in XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-using/using-annotations-in-xsd-schemas-sqlxml-4-0.md).</span></span> <span data-ttu-id="9404b-107">Per un elenco delle annotazioni supportate per gli schemi XDR, vedere la pagina relativa agli [schemi XDR con Annotazioni &#40;deprecati in SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="9404b-107">For a list of supported annotations for XDR schemas, see [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9404b-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="9404b-108">In This Section</span></span>  
 [<span data-ttu-id="9404b-109">SQL: relationship e regola di ordinamento delle chiavi &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="9404b-109">sql:relationship and the Key Ordering Rule &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sql-relationship-and-key-ordering-rule.md)  
 <span data-ttu-id="9404b-110">Viene descritto in che modo l'annotazione `sql:relationship` viene interpretata nel caricamento bulk XML.</span><span class="sxs-lookup"><span data-stu-id="9404b-110">Describes how the `sql:relationship` annotation is interpreted in XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="9404b-111">SQL: mappato &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="9404b-111">sql:mapped &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sql-mapped.md)  
 <span data-ttu-id="9404b-112">Viene descritto in che modo l'annotazione `sql:mapped` viene interpretata nel caricamento bulk XML.</span><span class="sxs-lookup"><span data-stu-id="9404b-112">Describes how the `sql:mapped` annotation is interpreted in XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="9404b-113">SQL: limit-field e SQL: Limit-Value &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="9404b-113">sql:limit-field and sql:limit-value &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sql-limit-field-and-sql-limit-value.md)  
 <span data-ttu-id="9404b-114">Viene descritto in che modo le annotazioni `sql:limit-field` e `sql:limit-value` vengono interpretate nel caricamento bulk XML.</span><span class="sxs-lookup"><span data-stu-id="9404b-114">Describes how the `sql:limit-field` and `sql:limit-value` annotations are interpreted in XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="9404b-115">SQL: overflow-field &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="9404b-115">sql:overflow-field &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sql-overflow-field.md)  
 <span data-ttu-id="9404b-116">Viene descritto in che modo l'annotazione `sql:overflow` viene interpretata nel caricamento bulk XML.</span><span class="sxs-lookup"><span data-stu-id="9404b-116">Describes how the `sql:overflow` annotation is interpreted in XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="9404b-117">Altre annotazioni &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="9404b-117">Other Annotations &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-other-annotations.md)  
 <span data-ttu-id="9404b-118">Viene descritto in che modo le annotazioni seguenti vengono interpretate nel caricamento bulk XML: `sql:id-prefix`, `sql:use-cdata`, `sql:url-encode`, `sql:is-mapping-schema`, `sql:key-fields`.</span><span class="sxs-lookup"><span data-stu-id="9404b-118">Describes how the following annotations are interpreted in XML Bulk Load: `sql:id-prefix`, `sql:use-cdata`, `sql:url-encode`, `sql:is-mapping-schema`, `sql:key-fields`.</span></span>  
  
  
