---
title: Sintassi del percorso di elemento per i dati del report XML (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ElementPath syntax
- XML [Reporting Services], data retrieval
ms.assetid: 07bd7a4e-fd7a-4a72-9344-3258f7c286d1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b7d66b39761dc278abff25a3b22ccd18ca74272b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726560"
---
# <a name="element-path-syntax-for-xml-report-data-ssrs"></a><span data-ttu-id="2fcf0-102">Sintassi del percorso di elemento per i dati del report XML (SSRS)</span><span class="sxs-lookup"><span data-stu-id="2fcf0-102">Element Path Syntax for XML Report Data (SSRS)</span></span>
  <span data-ttu-id="2fcf0-103">In Progettazione report è possibile specificare i dati da utilizzare per un report da un'origine dati XML definendo un percorso di elemento con distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-103">In Report Designer, you specify the data to use for a report from an XML data source by defining a case-sensitive element path.</span></span> <span data-ttu-id="2fcf0-104">Un percorso di elemento indica come attraversare i nodi gerarchici XML e i relativi attributi nell'origine dei dati XML.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-104">An element path indicates how to traverse the XML hierarchical nodes and their attributes in the XML data source.</span></span> <span data-ttu-id="2fcf0-105">Per utilizzare il percorso di elemento predefinito, lasciare vuota la query del set di dati o il nodo `ElementPath` XML dell'elemento `Query` XML.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-105">To use the default element path, leave the dataset query or the XML `ElementPath` of the XML `Query` empty.</span></span> <span data-ttu-id="2fcf0-106">Quando vengono recuperati i dati dall'origine dei dati XML, i nodi elemento con valori di testo e gli attributi dei nodi elemento diventano colonne del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-106">When data is retrieved from the XML data source, element nodes that have text values and element node attributes become columns in the result set.</span></span> <span data-ttu-id="2fcf0-107">Quando si esegue la query, i valori dei nodi e degli attributi diventano i dati delle righe.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-107">The values of the nodes and attributes become the row data when you run the query.</span></span> <span data-ttu-id="2fcf0-108">Le colonne sono visualizzate come raccolta di campi di set di dati nel riquadro Dati report.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-108">The columns appear as the dataset field collection in the Report Data pane.</span></span> <span data-ttu-id="2fcf0-109">In questo argomento viene descritta la sintassi del percorso di elemento.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-109">This topic describes the element path syntax.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2fcf0-110">La sintassi del percorso di elemento è indipendente dallo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-110">Element path syntax is namespace-independent.</span></span> <span data-ttu-id="2fcf0-111">Per utilizzare gli spazi dei nomi in un percorso di elemento, utilizzare la sintassi di query XML che include un `ElementPath` elemento XML descritto nella [sintassi XML query per i dati del Report XML &#40;&#41;SSRS ](report-data-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2fcf0-111">To use namespaces in an element path, use the XML query syntax that includes an XML `ElementPath` element described in [XML Query Syntax for XML Report Data &#40;SSRS&#41;](report-data-ssrs.md).</span></span>  
  
 <span data-ttu-id="2fcf0-112">Nella tabella seguente vengono descritte le convenzioni utilizzate per definire un percorso di elemento.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-112">The following table describes conventions used to define an element path.</span></span>  
  
|<span data-ttu-id="2fcf0-113">Convenzione</span><span class="sxs-lookup"><span data-stu-id="2fcf0-113">Convention</span></span>|<span data-ttu-id="2fcf0-114">Utilizzo</span><span class="sxs-lookup"><span data-stu-id="2fcf0-114">Used for</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2fcf0-115">**grassetto**</span><span class="sxs-lookup"><span data-stu-id="2fcf0-115">**bold**</span></span>|<span data-ttu-id="2fcf0-116">Il testo deve essere digitato esattamente come illustrato.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-116">Text that must be typed exactly as shown.</span></span>|  
|<span data-ttu-id="2fcf0-117">&#124; (barra verticale)</span><span class="sxs-lookup"><span data-stu-id="2fcf0-117">&#124; (vertical bar)</span></span>|<span data-ttu-id="2fcf0-118">Separa gli elementi della sintassi.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-118">Separates syntax items.</span></span> <span data-ttu-id="2fcf0-119">Indica che è possibile scegliere un solo elemento.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-119">You can choose only one of the items.</span></span>|  
|`[ ] (brackets)`|<span data-ttu-id="2fcf0-120">Elementi sintattici facoltativi.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-120">Optional syntax items.</span></span> <span data-ttu-id="2fcf0-121">Le parentesi quadre non devono essere digitate.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-121">Do not type the brackets.</span></span>|  
|<span data-ttu-id="2fcf0-122">**{}** (parentesi graffe)</span><span class="sxs-lookup"><span data-stu-id="2fcf0-122">**{ }** (braces)</span></span>|<span data-ttu-id="2fcf0-123">Delimitano i parametri degli elementi della sintassi.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-123">Delimits parameters of syntax items.</span></span>|  
|<span data-ttu-id="2fcf0-124">[ **,** ...*n*]</span><span class="sxs-lookup"><span data-stu-id="2fcf0-124">[**,**...*n*]</span></span>|<span data-ttu-id="2fcf0-125">Indica che l'elemento precedente può essere ripetuto *n* volte.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-125">Indicates the preceding item can be repeated *n* number of times.</span></span> <span data-ttu-id="2fcf0-126">Le occorrenze sono separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-126">The occurrences are separated by commas.</span></span>|  
  
## <a name="syntax"></a><span data-ttu-id="2fcf0-127">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2fcf0-127">Syntax</span></span>  
  
```  
  
Element path ::=  
    ElementNode[/Element path]  
ElementNode ::=  
    XMLName[(Encoding)][{[FieldList]}]  
XMLName ::=  
    [NamespacePrefix:]XMLLocalName  
Encoding ::=  
        HTMLEncoded | Base64Encoded  
FieldList ::=  
    Field[,FieldList]  
Field ::=  
    Attribute | Value | Element | ElementNode  
Attribute ::=  
        @XMLName[(Type)]  
Value ::=  
        @[(Type)]  
Element ::=  
    XMLName[(Type)]  
Type ::=  
        String | Integer | Boolean | Float | Decimal | Date | XML   
NamespacePrefix ::=  
    Identifier that specifies the namespace.  
XMLLocalName :: =  
    Identifier in the XML tag.   
```  
  
## <a name="remarks"></a><span data-ttu-id="2fcf0-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2fcf0-128">Remarks</span></span>  
 <span data-ttu-id="2fcf0-129">Nella tabella seguente sono riepilogati i termini del percorso di elemento.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-129">The following table summarizes element path terms.</span></span> <span data-ttu-id="2fcf0-130">Gli esempi della tabella si riferiscono al documento XML di esempio Customers.xml, incluso nella sezione relativa agli esempi di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-130">Examples in the table refer to the example XML document Customers.xml, which is included in the Examples section of this topic.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2fcf0-131">Nei tag XML viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-131">XML tags are case-sensitive.</span></span> <span data-ttu-id="2fcf0-132">Se nel percorso di elemento si specifica un nodo ElementNode, è necessario che corrisponda esattamente ai tag XML dell'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-132">When you specify an ElementNode in the element path, you must exactly match the XML tags in the data source.</span></span>  
  
|<span data-ttu-id="2fcf0-133">Termine</span><span class="sxs-lookup"><span data-stu-id="2fcf0-133">Term</span></span>|<span data-ttu-id="2fcf0-134">Definizione</span><span class="sxs-lookup"><span data-stu-id="2fcf0-134">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="2fcf0-135">Element path</span><span class="sxs-lookup"><span data-stu-id="2fcf0-135">Element path</span></span>|<span data-ttu-id="2fcf0-136">Definisce la sequenza di nodi da attraversare nel documento XML per recuperare i dati del campo di un set di dati con un'origine dei dati XML.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-136">Defines the sequence of nodes to traverse within the XML document in order to retrieve field data for a dataset with an XML data source.</span></span>|  
|`ElementNode`|<span data-ttu-id="2fcf0-137">Nodo XML nel documento XML.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-137">The XML node in the XML document.</span></span> <span data-ttu-id="2fcf0-138">I nodi sono designati da tag e sono correlati agli altri nodi in base a una relazione gerarchica.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-138">Nodes are designated by tags and exist in a hierarchical relationship with other nodes.</span></span> <span data-ttu-id="2fcf0-139">Ad esempio, \<Customers> è il nodo elemento radice.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-139">For example, \<Customers> is the root element node.</span></span> <span data-ttu-id="2fcf0-140">\<Customer>è un sottoelemento di \<Customers> .</span><span class="sxs-lookup"><span data-stu-id="2fcf0-140">\<Customer> is a subelement of \<Customers>.</span></span>|  
|`XMLName`|<span data-ttu-id="2fcf0-141">Il nome del nodo.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-141">The name of the node.</span></span> <span data-ttu-id="2fcf0-142">Il nome del nodo Customers, ad esempio, è Customers.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-142">For example, the name of the Customers node is Customers.</span></span> <span data-ttu-id="2fcf0-143">`XMLName` può essere preceduto da un identificatore dello spazio dei nomi, per assegnare a ogni nodo un nome univoco.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-143">An `XMLName` can be prefixed with a namespace identifier to uniquely name every node.</span></span>|  
|`Encoding`|<span data-ttu-id="2fcf0-144">Indica che il valore `Value` dell'elemento è un valore XML con codifica e deve essere decodificato e incluso come sottoelemento dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-144">Indicates that the `Value` for this element is encoded XML and needs to be decoded and included as a subelement of this element.</span></span>|  
|`FieldList`|<span data-ttu-id="2fcf0-145">Definisce il set di elementi e attributi da utilizzare per recuperare i dati.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-145">Defines the set of elements and attributes to use to retrieve data.</span></span><br /><br /> <span data-ttu-id="2fcf0-146">Se non specificato, vengono utilizzati come campi tutti gli attributi e i sottoelementi.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-146">If not specified, all attributes and subelements are used as fields.</span></span> <span data-ttu-id="2fcf0-147">Se viene specificato un elenco di campi vuoto ( **{}** ), non viene utilizzato alcun campo di questo nodo.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-147">If the empty field list is specified (**{}**), no fields from this node are used.</span></span><br /><br /> <span data-ttu-id="2fcf0-148">Un elemento `FieldList` potrebbe non contenere sia `Value` che `Element` o `ElementNode`.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-148">A `FieldList` may not contain both a `Value` and an `Element` or `ElementNode`.</span></span>|  
|`Field`|<span data-ttu-id="2fcf0-149">Specifica i dati recuperati come campo del set di dati.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-149">Specifies the data that is retrieved as a dataset field.</span></span>|  
|`Attribute`|<span data-ttu-id="2fcf0-150">Coppia nome-valore contenuta in `ElementNode`.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-150">A name-value pair within the `ElementNode`.</span></span> <span data-ttu-id="2fcf0-151">Nel nodo elemento, ad esempio \<Customer ID="1"> , `ID` è un attributo e `@ID(Integer)` restituisce "1" come tipo integer nel campo dati corrispondente `ID` .</span><span class="sxs-lookup"><span data-stu-id="2fcf0-151">For example, in the element node \<Customer ID="1">, `ID` is an attribute and `@ID(Integer)` returns "1" as an integer type in the corresponding data field `ID`.</span></span>|  
|`Value`|<span data-ttu-id="2fcf0-152">Valore dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-152">The value of the element.</span></span> <span data-ttu-id="2fcf0-153">`Value` può essere utilizzato solo nell'ultimo `ElementNode` del percorso di elemento.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-153">`Value` can only be used on the last `ElementNode` in the element path.</span></span> <span data-ttu-id="2fcf0-154">Ad esempio, poiché \<Return> è un nodo foglia, se lo si include alla fine di un percorso di elemento, il valore di `Return {@}` è `Chair` .</span><span class="sxs-lookup"><span data-stu-id="2fcf0-154">For example, because \<Return> is a leaf node, if you include it at the end of an element path, the value of `Return {@}` is `Chair`.</span></span>|  
|`Element`|<span data-ttu-id="2fcf0-155">Valore del sottoelemento denominato.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-155">The value of the named subelement.</span></span> <span data-ttu-id="2fcf0-156">Customers {}/Customer {}/LastName recupera, ad esempio, i valori solo per l'elemento LastName.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-156">For example, Customers {}/Customer {}/LastName retrieves values for only the LastName element.</span></span>|  
|`Type`|<span data-ttu-id="2fcf0-157">Tipo di dati facoltativo da utilizzare per il campo creato da questo elemento.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-157">The optional data type to use for the field created from this element.</span></span>|  
|`NamespacePrefix`|<span data-ttu-id="2fcf0-158">`NamespacePrefix` è definito nell'elemento Query XML.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-158">`NamespacePrefix` is defined in the XML Query element.</span></span> <span data-ttu-id="2fcf0-159">Se non è presente alcun elemento Query XML, gli spazi dei nomi del nodo `ElementPath` XML vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-159">If no XML Query element exists, namespaces in the XML `ElementPath` are ignored.</span></span> <span data-ttu-id="2fcf0-160">Se è presente un elemento Query XML, il nodo `ElementPath` XML include un attributo `IgnoreNamespaces` facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-160">If there is an XML Query element, the XML `ElementPath` has an optional attribute `IgnoreNamespaces`.</span></span> <span data-ttu-id="2fcf0-161">Se IgnoreNamespaces è `true` , gli spazi dei nomi nel file XML `ElementPath` e il documento XML vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-161">If IgnoreNamespaces is `true`, namespaces in the XML `ElementPath` and the XML document are ignored.</span></span> <span data-ttu-id="2fcf0-162">Per altre informazioni, vedere [Sintassi di XML Query per i dati del report XML &#40;SSRS&#41;](report-data-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2fcf0-162">For more information, see [XML Query Syntax for XML Report Data &#40;SSRS&#41;](report-data-ssrs.md).</span></span>|  
  
## <a name="example---no-namespaces"></a><span data-ttu-id="2fcf0-163">Esempio - Nessuno spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="2fcf0-163">Example - No Namespaces</span></span>  
 <span data-ttu-id="2fcf0-164">Negli esempi seguenti viene utilizzato il documento XML Customers.xml.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-164">The following examples use the XML document Customers.xml.</span></span> <span data-ttu-id="2fcf0-165">In questa tabella sono illustrati esempi di sintassi del percorso di elemento e i risultati dell'utilizzo del percorso di elemento in una query per la definizione di un set di dati, basata sul documento XML come origine dati.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-165">This table shows examples of element path syntax and the results of using the element path in a query that defines a dataset, based on the XML document as a data source.</span></span>  
  
 <span data-ttu-id="2fcf0-166">Si noti che quando il percorso dell'elemento è vuoto, la query usa il percorso dell'elemento predefinito, ovvero il primo percorso di una raccolta di nodi foglia.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-166">Note that when the element path is empty, the query uses the default element path: the first path to a leaf node collection.</span></span> <span data-ttu-id="2fcf0-167">Nel primo esempio l'utilizzo di un percorso di elemento vuoto corrisponde alla definizione del percorso di elemento /Customers/Customer/Orders/Order.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-167">In the first example, leaving the element path empty is equivalent to specifying the element path /Customers/Customer/Orders/Order.</span></span> <span data-ttu-id="2fcf0-168">Tutti gli attributi e i valori del nodo nel percorso vengono restituiti nel set di risultati, mentre i nomi degli attributi e del nodo vengono visualizzati come campi del set di dati.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-168">All node value and attributes along the path are returned in the result set, and the node names and attributes names appear as dataset fields.</span></span>  
  
-   <span data-ttu-id="2fcf0-169">*Vuoto*</span><span class="sxs-lookup"><span data-stu-id="2fcf0-169">*Empty*</span></span>  
  
    |<span data-ttu-id="2fcf0-170">JSON</span><span class="sxs-lookup"><span data-stu-id="2fcf0-170">Order</span></span>|<span data-ttu-id="2fcf0-171">Qtà</span><span class="sxs-lookup"><span data-stu-id="2fcf0-171">Qty</span></span>|<span data-ttu-id="2fcf0-172">ID</span><span class="sxs-lookup"><span data-stu-id="2fcf0-172">ID</span></span>|<span data-ttu-id="2fcf0-173">FirstName</span><span class="sxs-lookup"><span data-stu-id="2fcf0-173">FirstName</span></span>|<span data-ttu-id="2fcf0-174">LastName</span><span class="sxs-lookup"><span data-stu-id="2fcf0-174">LastName</span></span>|<span data-ttu-id="2fcf0-175">Customer.ID</span><span class="sxs-lookup"><span data-stu-id="2fcf0-175">Customer.ID</span></span>|<span data-ttu-id="2fcf0-176">xmlns</span><span class="sxs-lookup"><span data-stu-id="2fcf0-176">xmlns</span></span>|  
    |-----------|---------|--------|---------------|--------------|-----------------|-----------|  
    |<span data-ttu-id="2fcf0-177">Chair</span><span class="sxs-lookup"><span data-stu-id="2fcf0-177">Chair</span></span>|<span data-ttu-id="2fcf0-178">6</span><span class="sxs-lookup"><span data-stu-id="2fcf0-178">6</span></span>|<span data-ttu-id="2fcf0-179">1</span><span class="sxs-lookup"><span data-stu-id="2fcf0-179">1</span></span>|<span data-ttu-id="2fcf0-180">Bobby</span><span class="sxs-lookup"><span data-stu-id="2fcf0-180">Bobby</span></span>|<span data-ttu-id="2fcf0-181">Moore</span><span class="sxs-lookup"><span data-stu-id="2fcf0-181">Moore</span></span>|<span data-ttu-id="2fcf0-182">11</span><span class="sxs-lookup"><span data-stu-id="2fcf0-182">11</span></span>|http://www.adventure-works.com|  
    |<span data-ttu-id="2fcf0-183">Tabella</span><span class="sxs-lookup"><span data-stu-id="2fcf0-183">Table</span></span>|<span data-ttu-id="2fcf0-184">1</span><span class="sxs-lookup"><span data-stu-id="2fcf0-184">1</span></span>|<span data-ttu-id="2fcf0-185">2</span><span class="sxs-lookup"><span data-stu-id="2fcf0-185">2</span></span>|<span data-ttu-id="2fcf0-186">Bobby</span><span class="sxs-lookup"><span data-stu-id="2fcf0-186">Bobby</span></span>|<span data-ttu-id="2fcf0-187">Moore</span><span class="sxs-lookup"><span data-stu-id="2fcf0-187">Moore</span></span>|<span data-ttu-id="2fcf0-188">11</span><span class="sxs-lookup"><span data-stu-id="2fcf0-188">11</span></span>|http://www.adventure-works.com|  
    |<span data-ttu-id="2fcf0-189">Sofa</span><span class="sxs-lookup"><span data-stu-id="2fcf0-189">Sofa</span></span>|<span data-ttu-id="2fcf0-190">2</span><span class="sxs-lookup"><span data-stu-id="2fcf0-190">2</span></span>|<span data-ttu-id="2fcf0-191">8</span><span class="sxs-lookup"><span data-stu-id="2fcf0-191">8</span></span>|<span data-ttu-id="2fcf0-192">Crystal</span><span class="sxs-lookup"><span data-stu-id="2fcf0-192">Crystal</span></span>|<span data-ttu-id="2fcf0-193">Hu</span><span class="sxs-lookup"><span data-stu-id="2fcf0-193">Hu</span></span>|<span data-ttu-id="2fcf0-194">20</span><span class="sxs-lookup"><span data-stu-id="2fcf0-194">20</span></span>|http://www.adventure-works.com|  
    |<span data-ttu-id="2fcf0-195">EndTables</span><span class="sxs-lookup"><span data-stu-id="2fcf0-195">EndTables</span></span>|<span data-ttu-id="2fcf0-196">2</span><span class="sxs-lookup"><span data-stu-id="2fcf0-196">2</span></span>|<span data-ttu-id="2fcf0-197">15</span><span class="sxs-lookup"><span data-stu-id="2fcf0-197">15</span></span>|<span data-ttu-id="2fcf0-198">Wyatt</span><span class="sxs-lookup"><span data-stu-id="2fcf0-198">Wyatt</span></span>|<span data-ttu-id="2fcf0-199">Diaz</span><span class="sxs-lookup"><span data-stu-id="2fcf0-199">Diaz</span></span>|<span data-ttu-id="2fcf0-200">33</span><span class="sxs-lookup"><span data-stu-id="2fcf0-200">33</span></span>|http://www.adventure-works.com|  
  
-   `Customers {}/Customer`  
  
    |<span data-ttu-id="2fcf0-201">FirstName</span><span class="sxs-lookup"><span data-stu-id="2fcf0-201">FirstName</span></span>|<span data-ttu-id="2fcf0-202">LastName</span><span class="sxs-lookup"><span data-stu-id="2fcf0-202">LastName</span></span>|<span data-ttu-id="2fcf0-203">ID</span><span class="sxs-lookup"><span data-stu-id="2fcf0-203">ID</span></span>|  
    |---------------|--------------|--------|  
    |<span data-ttu-id="2fcf0-204">Bobby</span><span class="sxs-lookup"><span data-stu-id="2fcf0-204">Bobby</span></span>|<span data-ttu-id="2fcf0-205">Moore</span><span class="sxs-lookup"><span data-stu-id="2fcf0-205">Moore</span></span>|<span data-ttu-id="2fcf0-206">11</span><span class="sxs-lookup"><span data-stu-id="2fcf0-206">11</span></span>|  
    |<span data-ttu-id="2fcf0-207">Crystal</span><span class="sxs-lookup"><span data-stu-id="2fcf0-207">Crystal</span></span>|<span data-ttu-id="2fcf0-208">Hu</span><span class="sxs-lookup"><span data-stu-id="2fcf0-208">Hu</span></span>|<span data-ttu-id="2fcf0-209">20</span><span class="sxs-lookup"><span data-stu-id="2fcf0-209">20</span></span>|  
    |<span data-ttu-id="2fcf0-210">Wyatt</span><span class="sxs-lookup"><span data-stu-id="2fcf0-210">Wyatt</span></span>|<span data-ttu-id="2fcf0-211">Diaz</span><span class="sxs-lookup"><span data-stu-id="2fcf0-211">Diaz</span></span>|<span data-ttu-id="2fcf0-212">33</span><span class="sxs-lookup"><span data-stu-id="2fcf0-212">33</span></span>|  
  
-   `Customers {}/Customer {}/LastName`  
  
    |<span data-ttu-id="2fcf0-213">LastName</span><span class="sxs-lookup"><span data-stu-id="2fcf0-213">LastName</span></span>|  
    |--------------|  
    |<span data-ttu-id="2fcf0-214">Moore</span><span class="sxs-lookup"><span data-stu-id="2fcf0-214">Moore</span></span>|  
    |<span data-ttu-id="2fcf0-215">Hu</span><span class="sxs-lookup"><span data-stu-id="2fcf0-215">Hu</span></span>|  
    |<span data-ttu-id="2fcf0-216">Diaz</span><span class="sxs-lookup"><span data-stu-id="2fcf0-216">Diaz</span></span>|  
  
-   `Customers {}/Customer {}/Orders/Order {@,@Qty}`  
  
    |<span data-ttu-id="2fcf0-217">JSON</span><span class="sxs-lookup"><span data-stu-id="2fcf0-217">Order</span></span>|<span data-ttu-id="2fcf0-218">Qtà</span><span class="sxs-lookup"><span data-stu-id="2fcf0-218">Qty</span></span>|  
    |-----------|---------|  
    |<span data-ttu-id="2fcf0-219">Chair</span><span class="sxs-lookup"><span data-stu-id="2fcf0-219">Chair</span></span>|<span data-ttu-id="2fcf0-220">6</span><span class="sxs-lookup"><span data-stu-id="2fcf0-220">6</span></span>|  
    |<span data-ttu-id="2fcf0-221">Tabella</span><span class="sxs-lookup"><span data-stu-id="2fcf0-221">Table</span></span>|<span data-ttu-id="2fcf0-222">1</span><span class="sxs-lookup"><span data-stu-id="2fcf0-222">1</span></span>|  
    |<span data-ttu-id="2fcf0-223">Sofa</span><span class="sxs-lookup"><span data-stu-id="2fcf0-223">Sofa</span></span>|<span data-ttu-id="2fcf0-224">2</span><span class="sxs-lookup"><span data-stu-id="2fcf0-224">2</span></span>|  
    |<span data-ttu-id="2fcf0-225">EndTables</span><span class="sxs-lookup"><span data-stu-id="2fcf0-225">EndTables</span></span>|<span data-ttu-id="2fcf0-226">2</span><span class="sxs-lookup"><span data-stu-id="2fcf0-226">2</span></span>|  
  
-   `Customers {}/Customer/Orders/Order{ @ID(Integer)}`  
  
    |<span data-ttu-id="2fcf0-227">Order.ID</span><span class="sxs-lookup"><span data-stu-id="2fcf0-227">Order.ID</span></span>|<span data-ttu-id="2fcf0-228">FirstName</span><span class="sxs-lookup"><span data-stu-id="2fcf0-228">FirstName</span></span>|<span data-ttu-id="2fcf0-229">LastName</span><span class="sxs-lookup"><span data-stu-id="2fcf0-229">LastName</span></span>|<span data-ttu-id="2fcf0-230">ID</span><span class="sxs-lookup"><span data-stu-id="2fcf0-230">ID</span></span>|  
    |--------------|---------------|--------------|--------|  
    |<span data-ttu-id="2fcf0-231">1</span><span class="sxs-lookup"><span data-stu-id="2fcf0-231">1</span></span>|<span data-ttu-id="2fcf0-232">Bobby</span><span class="sxs-lookup"><span data-stu-id="2fcf0-232">Bobby</span></span>|<span data-ttu-id="2fcf0-233">Moore</span><span class="sxs-lookup"><span data-stu-id="2fcf0-233">Moore</span></span>|<span data-ttu-id="2fcf0-234">11</span><span class="sxs-lookup"><span data-stu-id="2fcf0-234">11</span></span>|  
    |<span data-ttu-id="2fcf0-235">2</span><span class="sxs-lookup"><span data-stu-id="2fcf0-235">2</span></span>|<span data-ttu-id="2fcf0-236">Bobby</span><span class="sxs-lookup"><span data-stu-id="2fcf0-236">Bobby</span></span>|<span data-ttu-id="2fcf0-237">Moore</span><span class="sxs-lookup"><span data-stu-id="2fcf0-237">Moore</span></span>|<span data-ttu-id="2fcf0-238">11</span><span class="sxs-lookup"><span data-stu-id="2fcf0-238">11</span></span>|  
    |<span data-ttu-id="2fcf0-239">8</span><span class="sxs-lookup"><span data-stu-id="2fcf0-239">8</span></span>|<span data-ttu-id="2fcf0-240">Crystal</span><span class="sxs-lookup"><span data-stu-id="2fcf0-240">Crystal</span></span>|<span data-ttu-id="2fcf0-241">Hu</span><span class="sxs-lookup"><span data-stu-id="2fcf0-241">Hu</span></span>|<span data-ttu-id="2fcf0-242">20</span><span class="sxs-lookup"><span data-stu-id="2fcf0-242">20</span></span>|  
    |<span data-ttu-id="2fcf0-243">15</span><span class="sxs-lookup"><span data-stu-id="2fcf0-243">15</span></span>|<span data-ttu-id="2fcf0-244">Wyatt</span><span class="sxs-lookup"><span data-stu-id="2fcf0-244">Wyatt</span></span>|<span data-ttu-id="2fcf0-245">Diaz</span><span class="sxs-lookup"><span data-stu-id="2fcf0-245">Diaz</span></span>|<span data-ttu-id="2fcf0-246">33</span><span class="sxs-lookup"><span data-stu-id="2fcf0-246">33</span></span>|  
  
#### <a name="xml-document-customersxml"></a><span data-ttu-id="2fcf0-247">Documento XML: Customers.xml</span><span class="sxs-lookup"><span data-stu-id="2fcf0-247">XML document: Customers.xml</span></span>  
 <span data-ttu-id="2fcf0-248">Per provare gli esempi di percorso di elemento nella sezione precedente, copiare questo codice XML e salvarlo in un URL accessibile da Progettazione report e quindi usare il documento XML come origine dati XML, ad esempio `http://localhost/Customers.xml`.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-248">To try out the element path examples in the previous section, you can copy this XML and save it to a URL that is accessible by Report Designer, and then use the XML document as an XML data source: for example, `http://localhost/Customers.xml`.</span></span>  
  
```  
<?xml version="1.0"?>  
<Customers xmlns="http://www.adventure-works.com">  
   <Customer ID="11">  
      <FirstName>Bobby</FirstName>  
      <LastName>Moore</LastName>  
      <Orders>  
         <Order ID="1" Qty="6">Chair</Order>  
         <Order ID="2" Qty="1">Table</Order>  
      </Orders>  
      <Returns>  
         <Return ID="1" Qty="2">Chair</Return>  
      </Returns>  
   </Customer>  
   <Customer ID="20">  
      <FirstName>Crystal</FirstName>  
      <LastName>Hu</LastName>  
      <Orders>  
         <Order ID="8" Qty="2">Sofa</Order>  
      </Orders>  
      <Returns/>  
   </Customer>  
   <Customer ID="33">  
      <FirstName>Wyatt</FirstName>  
      <LastName>Diaz</LastName>  
      <Orders>  
         <Order ID="15" Qty="2">EndTables</Order>  
      </Orders>  
      <Returns/>  
   </Customer>  
</Customers>  
```  
  
 <span data-ttu-id="2fcf0-249">In alternativa, è possibile creare un'origine dati XML senza una stringa di connessione e incorporare Customers.XML nella query, attenendosi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="2fcf0-249">Alternatively, you can create an XML data source that has no connection string and embed Customers.XML in the query, using the following procedure:</span></span>  
  
###### <a name="to-embed-customersxml-in-a-query"></a><span data-ttu-id="2fcf0-250">Per incorporare Customers.XML in una query</span><span class="sxs-lookup"><span data-stu-id="2fcf0-250">To embed Customers.XML in a query</span></span>  
  
1.  <span data-ttu-id="2fcf0-251">Creare un'origine dati XML con una stringa di connessione vuota.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-251">Create an XML data source with a blank connection string.</span></span>  
  
2.  <span data-ttu-id="2fcf0-252">Creare un nuovo set di dati per l'origine dati XML.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-252">Create a new dataset for the XML data source.</span></span>  
  
3.  <span data-ttu-id="2fcf0-253">Nella finestra di dialogo **Proprietà set di dati** fare clic su **Progettazione query**.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-253">In the **Dataset Properties** dialog box, click **Query Designer**.</span></span> <span data-ttu-id="2fcf0-254">Verrà visualizzata la finestra di dialogo Progettazione query basata su testo.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-254">The text-based query designer dialog box opens.</span></span>  
  
4.  <span data-ttu-id="2fcf0-255">Nel riquadro delle query immettere le due righe seguenti:</span><span class="sxs-lookup"><span data-stu-id="2fcf0-255">In the query pane, enter the following two lines:</span></span>  
  
     `<Query>`  
  
     `<XmlData>`  
  
5.  <span data-ttu-id="2fcf0-256">Copiare Customers.XML e incollare il testo nel riquadro delle query dopo `<XmlData>`.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-256">Copy Customers.XML and paste the text in the query pane after `<XmlData>`.</span></span>  
  
6.  <span data-ttu-id="2fcf0-257">Nel riquadro delle query eliminare la prima riga copiata da Customers.XML: `<?xml version="1.0"?>`</span><span class="sxs-lookup"><span data-stu-id="2fcf0-257">In the query pane, delete the first line that you copied from Customers.XML: `<?xml version="1.0"?>`</span></span>  
  
7.  <span data-ttu-id="2fcf0-258">Aggiungere le due righe seguenti alla fine della query:</span><span class="sxs-lookup"><span data-stu-id="2fcf0-258">At the end of the query, add the following two lines:</span></span>  
  
     `<XmlData>`  
  
     `<Query>`  
  
8.  <span data-ttu-id="2fcf0-259">Fare clic su **Esegui query** (!).</span><span class="sxs-lookup"><span data-stu-id="2fcf0-259">Click **Run Query** (!).</span></span>  
  
     <span data-ttu-id="2fcf0-260">Nel set di risultati vengono visualizzate 4 righe di dati con le colonne seguenti: `xmlns`, `Customer.ID`, `FirstName`, `LastName`, `ID`, `Qty`, `Order`.</span><span class="sxs-lookup"><span data-stu-id="2fcf0-260">The result set displays 4 lines of data with the following columns: `xmlns`, `Customer.ID`, `FirstName`, `LastName`, `ID`, `Qty`, `Order`.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2fcf0-261">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2fcf0-261">See Also</span></span>  
 <span data-ttu-id="2fcf0-262">[Tipo di connessione XML &#40;SSRS&#41;](xml-connection-type-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2fcf0-262">[XML Connection Type &#40;SSRS&#41;](xml-connection-type-ssrs.md) </span></span>  
 <span data-ttu-id="2fcf0-263">[Reporting Services esercitazioni &#40;SSRS&#41;](../reporting-services-tutorials-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2fcf0-263">[Reporting Services Tutorials &#40;SSRS&#41;](../reporting-services-tutorials-ssrs.md) </span></span>  
 [<span data-ttu-id="2fcf0-264">Aggiunta, modifica e aggiornamento di campi nel riquadro dei dati del report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2fcf0-264">Add, Edit, Refresh Fields in the Report Data Pane &#40;Report Builder and SSRS&#41;</span></span>](add-edit-refresh-fields-in-the-report-data-pane-report-builder-and-ssrs.md)  
  
  
