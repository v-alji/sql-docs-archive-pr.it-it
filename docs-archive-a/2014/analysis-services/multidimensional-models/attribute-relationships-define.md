---
title: Definire relazioni tra attributi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Analysis Services], relationships
- relationships [Analysis Services], attributes
ms.assetid: 9184d344-e96d-4025-ad6f-3f75129746df
author: minewiskan
ms.author: owend
ms.openlocfilehash: a694c68a55de2533c4ce7791d3be865008b6321f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624410"
---
# <a name="define-attribute-relationships"></a><span data-ttu-id="c9f1b-102">Definire relazioni tra attributi</span><span class="sxs-lookup"><span data-stu-id="c9f1b-102">Define Attribute Relationships</span></span>
  <span data-ttu-id="c9f1b-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] gli attributi rappresentano il blocco predefinito fondamentale di una dimensione.</span><span class="sxs-lookup"><span data-stu-id="c9f1b-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], attributes are the fundamental building block of a dimension.</span></span> <span data-ttu-id="c9f1b-104">Una dimensione contiene un set di attributi organizzato in base alle relazioni tra attributi.</span><span class="sxs-lookup"><span data-stu-id="c9f1b-104">A dimension contains a set of attributes that are organized based on attribute relationships.</span></span>  
  
 <span data-ttu-id="c9f1b-105">Per ogni tabella inclusa in una dimensione, vi è una relazione tra attributi che mette in relazione l'attributo chiave della tabella agli altri attributi di quella tabella.</span><span class="sxs-lookup"><span data-stu-id="c9f1b-105">For each table included in a dimension, there is an attribute relationship that relates the table's key attribute to other attributes from that table.</span></span> <span data-ttu-id="c9f1b-106">Si crea questa relazione quando si crea la dimensione.</span><span class="sxs-lookup"><span data-stu-id="c9f1b-106">You create this relationship when you create the dimension.</span></span>  
  
 <span data-ttu-id="c9f1b-107">Una relazione tra attributi fornisce i vantaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9f1b-107">An attribute relationship provides the following advantages:</span></span>  
  
-   <span data-ttu-id="c9f1b-108">Riduce la quantità di memoria necessaria per l'elaborazione della dimensione.</span><span class="sxs-lookup"><span data-stu-id="c9f1b-108">Reduces the amount of memory needed for dimension processing.</span></span> <span data-ttu-id="c9f1b-109">Ciò consente di rendere più rapida l’elaborazione di dimensioni, partizioni e query.</span><span class="sxs-lookup"><span data-stu-id="c9f1b-109">This speeds up dimension, partition, and query processing.</span></span>  
  
-   <span data-ttu-id="c9f1b-110">Aumenta le prestazioni di esecuzione delle query in quanto l'accesso all'archiviazione è più veloce ed i piani di esecuzione sono ottimizzati.</span><span class="sxs-lookup"><span data-stu-id="c9f1b-110">Increases query performance because storage access is faster and execution plans are better optimized.</span></span>  
  
-   <span data-ttu-id="c9f1b-111">Determina la selezione di aggregati più efficaci da parte degli algoritmi di progettazione delle aggregazioni, purché siano presenti gerarchie definite dall'utente nei percorsi delle relazioni.</span><span class="sxs-lookup"><span data-stu-id="c9f1b-111">Results in the selection of more effective aggregates by the aggregation design algorithms, provided that user-defined hierarchies have been defined along the relationship paths.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c9f1b-112">Per ulteriori informazioni sull'importanza e le implicazioni della definizione e della configurazione delle relazioni tra attributi, vedere la sezione relativa all'ottimizzazione delle prestazioni delle query nella [Guida alle prestazioni di SQL Server 2005 Analysis Services](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span><span class="sxs-lookup"><span data-stu-id="c9f1b-112">For more information about the importance and implications of defining and configuring attribute relationships, see the section, "Enhancing query performance," in the [SQL Server 2005 Analysis Services Performance Guide](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span></span>  
  
## <a name="attribute-relationship-considerations"></a><span data-ttu-id="c9f1b-113">Considerazioni sulle relazioni tra attributi</span><span class="sxs-lookup"><span data-stu-id="c9f1b-113">Attribute Relationship Considerations</span></span>  
 <span data-ttu-id="c9f1b-114">Quando i dati sottostanti lo supportano, si devono definire anche relazioni univoche tra attributi.</span><span class="sxs-lookup"><span data-stu-id="c9f1b-114">When the underlying data supports it, you should also define unique attribute relationships between attributes.</span></span> <span data-ttu-id="c9f1b-115">Per definire relazioni tra attributi univoche, usare la scheda **Relazioni tra attributi** di Progettazione dimensioni.</span><span class="sxs-lookup"><span data-stu-id="c9f1b-115">To define unique attribute relationships, use the **Attribute Relationships** tab of Dimension Designer.</span></span>  
  
 <span data-ttu-id="c9f1b-116">Qualsiasi attributo che ha una relazione in uscita deve avere una chiave univoca relativa all'attributo correlato.</span><span class="sxs-lookup"><span data-stu-id="c9f1b-116">Any attribute that has an outgoing relationship must have a unique key relative to its related attribute.</span></span> <span data-ttu-id="c9f1b-117">In altre parole, un membro in un attributo di origine deve identificare un solo membro in un attributo correlato.</span><span class="sxs-lookup"><span data-stu-id="c9f1b-117">In other words, a member in a source attribute must identify one and only one member in a related attribute.</span></span> <span data-ttu-id="c9f1b-118">Si consideri, ad esempio, la relazione, Città -> Stato.</span><span class="sxs-lookup"><span data-stu-id="c9f1b-118">For example, consider the relationship, City -> State.</span></span> <span data-ttu-id="c9f1b-119">In questa relazione, l'attributo di origine è Città e l'attributo correlato è Stato.</span><span class="sxs-lookup"><span data-stu-id="c9f1b-119">In this relationship, the source attribute is City and the related attribute is State.</span></span> <span data-ttu-id="c9f1b-120">L'attributo di origine è il lato "molti" e il lato correlato è il lato "uno" della relazione molti-a-uno.</span><span class="sxs-lookup"><span data-stu-id="c9f1b-120">The source attribute is the "many" side and the related side is the "one" side of the many-to-one relationship.</span></span> <span data-ttu-id="c9f1b-121">La chiave per l'attributo di origine sarebbe Città + Stato.</span><span class="sxs-lookup"><span data-stu-id="c9f1b-121">The key for the source attribute would be City + State.</span></span> <span data-ttu-id="c9f1b-122">Per altre informazioni, vedere [Creare, modificare o eliminare una relazione tra attributi](attribute-relationships-create-modify-or-delete-relationship.md).</span><span class="sxs-lookup"><span data-stu-id="c9f1b-122">For more information, see [Create, Modify, or Delete an Attribute Relationship](attribute-relationships-create-modify-or-delete-relationship.md).</span></span>  
  
 <span data-ttu-id="c9f1b-123">Per altre informazioni sulle proprietà di una relazione tra attributi, vedere [Configurare le proprietà della relazione tra attributi](attribute-relationships-configure-attribute-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c9f1b-123">For more information about properties of an attribute relationship, see [Configure Attribute Relationship Properties](attribute-relationships-configure-attribute-properties.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c9f1b-124">Definire erroneamente relazioni tra attributi può produrre risultati della query non validi.</span><span class="sxs-lookup"><span data-stu-id="c9f1b-124">Defining attribute relationships incorrectly can cause invalid query results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9f1b-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9f1b-125">See Also</span></span>  
 [<span data-ttu-id="c9f1b-126">Relazioni tra attributi</span><span class="sxs-lookup"><span data-stu-id="c9f1b-126">Attribute Relationships</span></span>](../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md)  
  
  
