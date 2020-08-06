---
title: "Specifica dell'attributo SQL: inverse in SQL: Relationship (SQLXML 4,0) | Microsoft Docs"
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- sql:relationship
- bulk load [SQLXML]
- inverse attribute
- relationships [SQLXML], inverse orders
- relationship annotation
- XSD schemas [SQLXML], relationships
- annotated XSD schemas, relationships
- updategrams [SQLXML], relationships
- sql:inverse
ms.assetid: 08904cbd-9c86-493d-90c3-f5e1d13ce59d
author: rothja
ms.author: jroth
ms.openlocfilehash: 5b0781102371b98cced72a5a0edee70c9567c372
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628605"
---
# <a name="specifying-the-sqlinverse-attribute-on-sqlrelationship-sqlxml-40"></a><span data-ttu-id="2460d-102">Specifica dell'attributo sql:inverse in sql:relationship (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="2460d-102">Specifying the sql:inverse Attribute on sql:relationship (SQLXML 4.0)</span></span>
  <span data-ttu-id="2460d-103">L'attributo `sql:inverse` risulta utile solo quando lo schema XSD viene utilizzato per il caricamento bulk o da un updategram.</span><span class="sxs-lookup"><span data-stu-id="2460d-103">The `sql:inverse` attribute is useful only when the XSD schema is used for either bulk load or by an updategram.</span></span> <span data-ttu-id="2460d-104">L' `sql:inverse` attributo può essere specificato nell' **\<sql:relationship>** elemento.</span><span class="sxs-lookup"><span data-stu-id="2460d-104">The `sql:inverse` attribute can be specified on the **\<sql:relationship>** element.</span></span> <span data-ttu-id="2460d-105">Negli updategram la relativa logica interpreta lo schema nella determinazione delle tabelle e delle colonne aggiornate dall'operazione dell'updategram.</span><span class="sxs-lookup"><span data-stu-id="2460d-105">In updategrams, the updategram logic interprets the schema in determining the tables and columns that are updated by the updategram operation.</span></span> <span data-ttu-id="2460d-106">Le relazioni padre-figlio specificate nello schema determinano l'ordine di modifica (inserimento o eliminazione) dei record.</span><span class="sxs-lookup"><span data-stu-id="2460d-106">The parent-child relationships that are specified in the schema determine the order in which the records are modified (inserted or deleted).</span></span>  
  
 <span data-ttu-id="2460d-107">Nel caso di uno schema XSD in cui la relazione padre-figlio viene specificata nell'ordine inverso a quello della relazione chiave primaria/chiave esterna tra le colonne del database corrispondenti, l'operazione di inserimento o eliminazione dell'updategram non riuscirà a causa della violazione della relazione chiave primaria/chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="2460d-107">If you have an XSD schema in which the parent-child relationship is specified in the inverse order of the primary-key/foreign-key relationship between the corresponding database columns, the insert or delete updategram operation will fail because of the primary-key/foreign-key violation.</span></span> <span data-ttu-id="2460d-108">In questi casi, l' `sql:inverse` attributo viene specificato ( `sql:inverse="true"` ) nell' **\<sql:relationship>** elemento e la logica dell'updategram inverte l'interpretazione della relazione padre-figlio specificata nello schema.</span><span class="sxs-lookup"><span data-stu-id="2460d-108">In such cases, the `sql:inverse` attribute is specified (`sql:inverse="true"`) in the **\<sql:relationship>** element, and the updategram logic inverses its interpretation of the parent-child relationship specified in the schema.</span></span>  
  
 <span data-ttu-id="2460d-109">L'attributo `sql:inverse` utilizza un valore booleano (0=false, 1=true).</span><span class="sxs-lookup"><span data-stu-id="2460d-109">The `sql:inverse` attribute takes a Boolean value (0=false, 1=true).</span></span> <span data-ttu-id="2460d-110">I valori possibili sono 0, 1, true e false.</span><span class="sxs-lookup"><span data-stu-id="2460d-110">The acceptable values are 0, 1, true, and false.</span></span>  
  
 <span data-ttu-id="2460d-111">Per un esempio funzionante di utilizzo dell' `sql:inverse` annotazione, vedere [specifica di uno schema di mapping con annotazioni in un updategram](../sqlxml-annotated-xsd-schemas-xpath-queries/updategrams/specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="2460d-111">For a working sample using the `sql:inverse` annotation, see [Specifying an Annotated Mapping Schema in an Updategram](../sqlxml-annotated-xsd-schemas-xpath-queries/updategrams/specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2460d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2460d-112">See Also</span></span>  
 [<span data-ttu-id="2460d-113">Definizione di relazioni tramite SQL: Relationship &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="2460d-113">Specifying Relationships Using sql:relationship &#40;SQLXML 4.0&#41;</span></span>](specifying-relationships-using-sql-relationship-sqlxml-4-0.md)  
  
  
