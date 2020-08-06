---
title: Relazioni tra attributi | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- member properties [Analysis Services], attribute relationships
- security [Analysis Services], properties
- PROPERTIES keyword
- storage [Analysis Services], attribute relationships
- natural hierarchies [Analysis Services]
- dimensions [Analysis Services], member properties
- queries [MDX], attribute relationships
- user-defined hierarchies [Analysis Services]
- attributes [Analysis Services], relationships
- member properties [Analysis Services]
- members [Analysis Services], attribute relationships
- storing data [Analysis Services], attribute relationships
- relationships [Analysis Services], attributes
ms.assetid: 2491422a-4cf5-4b23-b6ab-289222b22ce8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 122638a2728a8a85ee58661196797383da20eef8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716907"
---
# <a name="attribute-relationships"></a><span data-ttu-id="5f057-102">Relazioni tra attributi</span><span class="sxs-lookup"><span data-stu-id="5f057-102">Attribute Relationships</span></span>
  <span data-ttu-id="5f057-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] gli attributi all'interno di una dimensione sono sempre correlati direttamente o indirettamente all'attributo chiave.</span><span class="sxs-lookup"><span data-stu-id="5f057-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], attributes within a dimension are always related either directly or indirectly to the key attribute.</span></span> <span data-ttu-id="5f057-104">Quando si definisce una dimensione in base a uno schema star, in cui tutti gli attributi della dimensione sono derivati dalla stessa tabella relazionale, viene automaticamente definita una relazione tra l'attributo chiave e ogni attributo non chiave della dimensione.</span><span class="sxs-lookup"><span data-stu-id="5f057-104">When you define a dimension based on a star schema, which is where all dimension attributes are derived from the same relational table, an attribute relationship is automatically defined between the key attribute and each non-key attribute of the dimension.</span></span> <span data-ttu-id="5f057-105">Quando si definisce una dimensione in base a uno schema snowflake, in cui gli attributi della dimensione sono derivati da più tabelle correlate, viene automaticamente definita una relazione tra attributi come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="5f057-105">When you define a dimension based on a snowflake schema, which is where dimension attributes are derived from multiple related tables, an attribute relationship is automatically defined as follows:</span></span>  
  
-   <span data-ttu-id="5f057-106">Tra l'attributo chiave e ogni attributo non chiave associato alle colonne della tabella principale della dimensione.</span><span class="sxs-lookup"><span data-stu-id="5f057-106">Between the key attribute and each non-key attribute bound to columns in the main dimension table.</span></span>  
  
-   <span data-ttu-id="5f057-107">Tra l'attributo chiave e l'attributo associato alla chiave esterna della tabella secondaria che collega le tabelle delle dimensioni sottostanti.</span><span class="sxs-lookup"><span data-stu-id="5f057-107">Between the key attribute and the attribute bound to the foreign key in the secondary table that links the underlying dimension tables.</span></span>  
  
-   <span data-ttu-id="5f057-108">Tra l'attributo associato alla chiave esterna della tabella secondaria e ogni attributo non chiave associato alle colonne della tabella secondaria.</span><span class="sxs-lookup"><span data-stu-id="5f057-108">Between the attribute bound to foreign key in the secondary table and each non-key attribute bound to columns from the secondary table.</span></span>  
  
 <span data-ttu-id="5f057-109">Vi sono, tuttavia, molti motivi per cui potrebbe essere necessario modificare queste relazioni tra attributi predefinite.</span><span class="sxs-lookup"><span data-stu-id="5f057-109">However, there are a number of reasons why you might want to change these default attribute relationships.</span></span> <span data-ttu-id="5f057-110">Potrebbe, ad esempio, essere necessario definire una gerarchia naturale, un ordinamento personalizzato o una granularità della dimensione basata su un attributo non chiave.</span><span class="sxs-lookup"><span data-stu-id="5f057-110">For example, you might want to define a natural hierarchy, a custom sort order, or dimension granularity based on a non-key attribute.</span></span> <span data-ttu-id="5f057-111">Per ulteriori informazioni, vedere [riferimento alle proprietà degli attributi delle dimensioni](../multidimensional-models/dimension-attribute-properties-reference.md).</span><span class="sxs-lookup"><span data-stu-id="5f057-111">For more information, see [Dimension Attribute Properties Reference](../multidimensional-models/dimension-attribute-properties-reference.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5f057-112">Le relazioni tra attributi sono note nelle espressioni MDX (Multidimensional Expression) come proprietà del membro.</span><span class="sxs-lookup"><span data-stu-id="5f057-112">Attribute relationships are known in Multidimensional Expressions (MDX) as member properties.</span></span>  
  
## <a name="natural-hierarchy-relationships"></a><span data-ttu-id="5f057-113">Relazioni di gerarchia naturale</span><span class="sxs-lookup"><span data-stu-id="5f057-113">Natural Hierarchy Relationships</span></span>  
 <span data-ttu-id="5f057-114">Una gerarchia è naturale quando ogni attributo incluso nella gerarchia definita dall'utente ha una relazione uno-a-molti con l'attributo immediatamente sottostante.</span><span class="sxs-lookup"><span data-stu-id="5f057-114">A hierarchy is a natural hierarchy when each attribute included in the user-defined hierarchy has a one to many relationship with the attribute immediately below it.</span></span> <span data-ttu-id="5f057-115">Considerare, ad esempio, una dimensione Customer basata su una tabella di origine relazionale con otto colonne:</span><span class="sxs-lookup"><span data-stu-id="5f057-115">For example, consider a Customer dimension based on a relational source table with eight columns:</span></span>  
  
-   <span data-ttu-id="5f057-116">CustomerKey</span><span class="sxs-lookup"><span data-stu-id="5f057-116">CustomerKey</span></span>  
  
-   <span data-ttu-id="5f057-117">CustomerName</span><span class="sxs-lookup"><span data-stu-id="5f057-117">CustomerName</span></span>  
  
-   <span data-ttu-id="5f057-118">Età</span><span class="sxs-lookup"><span data-stu-id="5f057-118">Age</span></span>  
  
-   <span data-ttu-id="5f057-119">Sesso</span><span class="sxs-lookup"><span data-stu-id="5f057-119">Gender</span></span>  
  
-   <span data-ttu-id="5f057-120">Email</span><span class="sxs-lookup"><span data-stu-id="5f057-120">Email</span></span>  
  
-   <span data-ttu-id="5f057-121">Città</span><span class="sxs-lookup"><span data-stu-id="5f057-121">City</span></span>  
  
-   <span data-ttu-id="5f057-122">Country</span><span class="sxs-lookup"><span data-stu-id="5f057-122">Country</span></span>  
  
-   <span data-ttu-id="5f057-123">Region</span><span class="sxs-lookup"><span data-stu-id="5f057-123">Region</span></span>  
  
 <span data-ttu-id="5f057-124">La dimensione di Analysis Services corrispondente ha sette attributi:</span><span class="sxs-lookup"><span data-stu-id="5f057-124">The corresponding Analysis Services dimension has seven attributes:</span></span>  
  
-   <span data-ttu-id="5f057-125">Customer (basato su CustomerKey, con CustomerName che definisce i nomi dei membri)</span><span class="sxs-lookup"><span data-stu-id="5f057-125">Customer (based on CustomerKey, with CustomerName supplying member names)</span></span>  
  
-   <span data-ttu-id="5f057-126">Age, Gender, Email, City, Region, Country</span><span class="sxs-lookup"><span data-stu-id="5f057-126">Age, Gender, Email, City, Region, Country</span></span>  
  
 <span data-ttu-id="5f057-127">Le relazioni che rappresentano gerarchie naturali vengono applicate creando una relazione fra l'attributo per un livello e l'attributo per il livello sottostante.</span><span class="sxs-lookup"><span data-stu-id="5f057-127">Relationships representing natural hierarchies are enforced by creating an attribute relationship between the attribute for a level and the attribute for the level below it.</span></span> <span data-ttu-id="5f057-128">Per [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] questa operazione specifica una relazione naturale e un'aggregazione potenziale.</span><span class="sxs-lookup"><span data-stu-id="5f057-128">For [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], this specifies a natural relationship and potential aggregation.</span></span> <span data-ttu-id="5f057-129">Nella dimensione Customer è presente una gerarchia naturale per gli attributi Country, Region, City e Customer.</span><span class="sxs-lookup"><span data-stu-id="5f057-129">In the Customer dimension, a natural hierarchy exists for the Country, Region, City, and Customer attributes.</span></span> <span data-ttu-id="5f057-130">La gerarchia naturale per `{Country, Region, City, Customer}` viene descritta aggiungendo le relazioni tra attributi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5f057-130">The natural hierarchy for `{Country, Region, City, Customer}` is described by adding the following attribute relationships:</span></span>  
  
-   <span data-ttu-id="5f057-131">Attributo Country come relazione tra attributi dell'attributo Region.</span><span class="sxs-lookup"><span data-stu-id="5f057-131">The Country attribute as an attribute relationship to the Region attribute.</span></span>  
  
-   <span data-ttu-id="5f057-132">Attributo Region come relazione tra attributi dell'attributo City.</span><span class="sxs-lookup"><span data-stu-id="5f057-132">The Region attribute as an attribute relationship to the City attribute.</span></span>  
  
-   <span data-ttu-id="5f057-133">Attributo City come relazione tra attributi dell'attributo Customer.</span><span class="sxs-lookup"><span data-stu-id="5f057-133">The City attribute as an attribute relationship to the Customer attribute.</span></span>  
  
 <span data-ttu-id="5f057-134">Per spostarsi tra i dati nel cubo, è inoltre possibile creare una gerarchia definita dall'utente che non rappresenti una gerarchia naturale nei dati (denominata gerarchia *ad hoc* o di *Reporting* ).</span><span class="sxs-lookup"><span data-stu-id="5f057-134">For navigating data in the cube, you can also create a user-defined hierarchy that does not represent a natural hierarchy in the data (which is called an *ad hoc* or *reporting* hierarchy).</span></span> <span data-ttu-id="5f057-135">È ad esempio possibile creare una gerarchia basata su `{Age, Gender}`.</span><span class="sxs-lookup"><span data-stu-id="5f057-135">For example, you could create a user-defined hierarchy based on `{Age, Gender}`.</span></span> <span data-ttu-id="5f057-136">Gli utenti non vedono alcuna differenza nel comportamento delle due gerarchie, anche se la gerarchia naturale trae vantaggio dalle strutture di aggregazione e indicizzazione, nascoste dall'utente, che rappresentano le relazioni naturali nei dati di origine.</span><span class="sxs-lookup"><span data-stu-id="5f057-136">Users do not see any difference in how the two hierarchies behave, although the natural hierarchy benefits from aggregating and indexing structures - hidden from the user - that account for the natural relationships in the source data.</span></span>  
  
 <span data-ttu-id="5f057-137">La proprietà `SourceAttribute` di un livello determina l'attributo utilizzato per descrivere il livello.</span><span class="sxs-lookup"><span data-stu-id="5f057-137">The `SourceAttribute` property of a level determines which attribute is used to describe the level.</span></span> <span data-ttu-id="5f057-138">La proprietà `KeyColumns` dell'attributo specifica la colonna della vista origine dati che definisce i membri.</span><span class="sxs-lookup"><span data-stu-id="5f057-138">The `KeyColumns` property on the attribute specifies the column in the data source view that supplies the members.</span></span> <span data-ttu-id="5f057-139">La proprietà `NameColumn` dell'attributo può specificare una colonna dei nomi differente per i membri.</span><span class="sxs-lookup"><span data-stu-id="5f057-139">The `NameColumn` property on the attribute can specify a different name column for the members.</span></span>  
  
 <span data-ttu-id="5f057-140">Per definire un livello in una gerarchia definita dall'utente utilizzando [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] , **Progettazione dimensioni** consente di selezionare un attributo della dimensione, una colonna in una tabella della dimensione o una colonna di una tabella correlata inclusa nella vista origine dati per il cubo.</span><span class="sxs-lookup"><span data-stu-id="5f057-140">To define a level in a user-defined hierarchy using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], the **Dimension Designer** allows you to select a dimension attribute, a column in a dimension table, or a column from a related table included in the data source view for the cube.</span></span> <span data-ttu-id="5f057-141">Per ulteriori informazioni sulla creazione di gerarchie definite dall'utente, vedere [creare gerarchie definite dall'utente](../multidimensional-models/user-defined-hierarchies-create.md).</span><span class="sxs-lookup"><span data-stu-id="5f057-141">For more information about creating user-defined hierarchies, see [Create User-Defined Hierarchies](../multidimensional-models/user-defined-hierarchies-create.md).</span></span>  
  
 <span data-ttu-id="5f057-142">Relativamente al contenuto dei membri, in Analysis Services ci si basa in genere sul presupposto che</span><span class="sxs-lookup"><span data-stu-id="5f057-142">In Analysis Services, an assumption is usually made about the content of members.</span></span> <span data-ttu-id="5f057-143">i membri foglia non abbiano discendenti e contengano dati derivati dalle origini dei dati sottostanti,</span><span class="sxs-lookup"><span data-stu-id="5f057-143">Leaf members have no descendents and contain data derived from underlying data sources.</span></span> <span data-ttu-id="5f057-144">mentre i membri non foglia abbiano discendenti e contengano dati derivati dalle aggregazioni eseguite sui membri figlio.</span><span class="sxs-lookup"><span data-stu-id="5f057-144">Nonleaf members have descendents and contain data derived from aggregations performed on child members.</span></span> <span data-ttu-id="5f057-145">Nei livelli aggregati i membri sono basati sulle aggregazioni di livelli subordinati.</span><span class="sxs-lookup"><span data-stu-id="5f057-145">In aggregated levels, members are based on aggregations of subordinate levels.</span></span> <span data-ttu-id="5f057-146">Quando, perciò, la proprietà `IsAggregatable` viene impostata su `False` in un attributo di origine per un livello, non devono essere aggiunti attributi che possono essere aggregati come livelli al di sopra di esso.</span><span class="sxs-lookup"><span data-stu-id="5f057-146">Therefore, when the `IsAggregatable` property is set to `False` on a source attribute for a level, no aggregatable attributes should be added as levels above it.</span></span>  
  
## <a name="defining-an-attribute-relationship"></a><span data-ttu-id="5f057-147">Definizione di una relazione tra attributi</span><span class="sxs-lookup"><span data-stu-id="5f057-147">Defining an Attribute Relationship</span></span>  
 <span data-ttu-id="5f057-148">Il vincolo principale quando si crea una relazione tra attributi consiste nel verificare che l'attributo a cui la relazione fa riferimento non abbia più di un valore per ogni membro nell'attributo a cui appartiene la relazione tra attributi.</span><span class="sxs-lookup"><span data-stu-id="5f057-148">The main constraint when you create an attribute relationship is to make sure that the attribute referred to by the attribute relationship has no more than one value for any member in the attribute to which the attribute relationship belongs.</span></span> <span data-ttu-id="5f057-149">Se, ad esempio, si definisce una relazione tra un attributo City e un attributo State, ogni città può essere in relazione solo con un unico stato.</span><span class="sxs-lookup"><span data-stu-id="5f057-149">For example, if you define a relationship between a City attribute and a State attribute, each city can only relate to a single state.</span></span>  
  
## <a name="attribute-relationship-queries"></a><span data-ttu-id="5f057-150">Query sulla relazione tra attributi</span><span class="sxs-lookup"><span data-stu-id="5f057-150">Attribute Relationship Queries</span></span>  
 <span data-ttu-id="5f057-151">È possibile utilizzare query MDX per recuperare dati dalle relazioni tra attributi in forma di proprietà del membro, tramite la parola chiave `PROPERTIES` dell'istruzione `SELECT` MDX.</span><span class="sxs-lookup"><span data-stu-id="5f057-151">You can use MDX queries to retrieve data from attribute relationships, in the form of member properties, with the `PROPERTIES` keyword of the MDX `SELECT` statement.</span></span> <span data-ttu-id="5f057-152">Per ulteriori informazioni sull'utilizzo di MDX per recuperare le proprietà dei membri, vedere [utilizzo delle proprietà dei membri &#40;&#41;MDX ](../multidimensional-models/mdx/mdx-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="5f057-152">For more information about how to use MDX to retrieve member properties, see [Using Member Properties &#40;MDX&#41;](../multidimensional-models/mdx/mdx-member-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f057-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f057-153">See Also</span></span>  
 <span data-ttu-id="5f057-154">[Attributi e gerarchie di attributi](attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="5f057-154">[Attributes and Attribute Hierarchies](attributes-and-attribute-hierarchies.md) </span></span>  
 <span data-ttu-id="5f057-155">[Riferimento alle proprietà degli attributi delle dimensioni](../multidimensional-models/dimension-attribute-properties-reference.md) </span><span class="sxs-lookup"><span data-stu-id="5f057-155">[Dimension Attribute Properties Reference](../multidimensional-models/dimension-attribute-properties-reference.md) </span></span>  
 <span data-ttu-id="5f057-156">[Gerarchie utente](user-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="5f057-156">[User Hierarchies](user-hierarchies.md) </span></span>  
 [<span data-ttu-id="5f057-157">Proprietà delle gerarchie definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="5f057-157">User Hierarchy Properties</span></span>](user-hierarchies-properties.md)  
  
  
