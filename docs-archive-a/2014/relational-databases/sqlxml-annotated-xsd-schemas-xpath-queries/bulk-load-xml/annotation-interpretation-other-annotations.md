---
title: Altre annotazioni (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- url-encode annotation
- sql:key-fields
- use-cdata annotation
- sql:is-mapping-schema
- sql:url-encode
- sql:id-prefix
- sql:use-cdata
- key-fields annotation
- id-prefix annotation [SQLXML]
- is-mapping-schema annotation
ms.assetid: f7b4d37b-d6d3-4ac3-b2fd-a0b534a924e4
author: rothja
ms.author: jroth
ms.openlocfilehash: b654568c93df0a0c3e08cf6eaa615b7026a9c18a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628593"
---
# <a name="other-annotations-sqlxml-40"></a><span data-ttu-id="ef4cd-102">Altre annotazioni (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="ef4cd-102">Other Annotations (SQLXML 4.0)</span></span>
  <span data-ttu-id="ef4cd-103">Oltre alle annotazioni descritte negli argomenti precedenti di questa sezione, il caricamento bulk XML interpreta queste altre annotazioni, come segue:</span><span class="sxs-lookup"><span data-stu-id="ef4cd-103">In addition to the annotations discussed in the previous topics in this section, XML Bulk Load interprets these other annotations, as follows:</span></span>  
  
 `sql:id-prefix`  
 <span data-ttu-id="ef4cd-104">Se lo schema specifica i prefissi dei dati XML, il caricamento bulk XML rimuove i prefissi prima di inviare i dati a Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef4cd-104">If the schema specifies prefixes to the XML data, XML Bulk Load removes the prefixes before sending the data to Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 `sql:use-cdata`  
 <span data-ttu-id="ef4cd-105">Il caricamento bulk XML legge il testo archiviato nelle sezioni CDATA e lo invia a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef4cd-105">XML Bulk Load reads the text that is stored in the CDATA sections and sends it to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 `sql:url-encode`  
 <span data-ttu-id="ef4cd-106">Il caricamento bulk XML non supporta questa annotazione.</span><span class="sxs-lookup"><span data-stu-id="ef4cd-106">XML Bulk Load does not support this annotation.</span></span> <span data-ttu-id="ef4cd-107">Non è possibile ad esempio specificare un URL nei dati XML di input e prevedere che il caricamento bulk XML legga i dati da tale posizione per archiviarli nel database.</span><span class="sxs-lookup"><span data-stu-id="ef4cd-107">For example, you cannot specify a URL in the XML data input and expect XML Bulk Load to read data from that location to store it in the database.</span></span>  
  
 `sql:is-mapping-schema`  
 <span data-ttu-id="ef4cd-108">Il caricamento bulk XML non supporta questa annotazione né supporta `sql:id`.</span><span class="sxs-lookup"><span data-stu-id="ef4cd-108">XML Bulk Load does not support this annotation, nor does it support `sql:id`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ef4cd-109">Il caricamento bulk XML non supporta schemi di mapping inline.</span><span class="sxs-lookup"><span data-stu-id="ef4cd-109">XML Bulk Load does not support inline mapping schemas.</span></span>  
  
 `sql:key-fields`  
 <span data-ttu-id="ef4cd-110">Il caricamento bulk XML ignora sempre questa annotazione.</span><span class="sxs-lookup"><span data-stu-id="ef4cd-110">XML Bulk Load always ignores this annotation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef4cd-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef4cd-111">See Also</span></span>  
 [<span data-ttu-id="ef4cd-112">Interpretazione dell'annotazione &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ef4cd-112">Annotation Interpretation &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sqlxml-4-0.md)  
  
  
