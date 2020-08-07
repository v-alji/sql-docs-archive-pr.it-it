---
title: Introduzione agli updategram (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- explicit schema mapping [SQLXML]
- updategrams [SQLXML], mapping schema specifying
- namespaces [SQLXML]
- updategrams [SQLXML], about updategrams
- attribute-centric mapping
- invalid characters [SQLXML]
- element-centric mapping [SQLXML]
- mapping schema [SQLXML], updategrams
- namespaces [SQLXML], updategrams
- executing updategrams [SQLXML]
- implicit schema mapping
ms.assetid: cfe24e82-a645-4f93-ab16-39c21f90cce6
author: rothja
ms.author: jroth
ms.openlocfilehash: eb2f29d7f5d86d28254dacb9c55cceb9b4c72d8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716127"
---
# <a name="introduction-to-updategrams-sqlxml-40"></a><span data-ttu-id="63dd0-102">Introduzione sugli updategram (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="63dd0-102">Introduction to Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="63dd0-103">È possibile modificare (inserire, aggiornare o eliminare) un database in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] da un documento XML esistente utilizzando un updategram o la [!INCLUDE[tsql](../../../includes/tsql-md.md)] funzione OPENXML.</span><span class="sxs-lookup"><span data-stu-id="63dd0-103">You can modify (insert, update, or delete) a database in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] from an existing XML document by using an updategram or the OPENXML [!INCLUDE[tsql](../../../includes/tsql-md.md)] function.</span></span>  
  
 <span data-ttu-id="63dd0-104">La funzione OPENXML modifica un database suddividendo il documento XML esistente e fornendo un set di righe che può essere passato a un'istruzione INSERT, UPDATE o DELETE.</span><span class="sxs-lookup"><span data-stu-id="63dd0-104">The OPENXML function modifies a database by shredding the existing XML document and providing a rowset that can be passed to an INSERT, UPDATE, or DELETE statement.</span></span> <span data-ttu-id="63dd0-105">Con OPENXML, le operazioni vengono eseguite direttamente sulle tabelle del database.</span><span class="sxs-lookup"><span data-stu-id="63dd0-105">With OPENXML, operations are performed directly against the database tables.</span></span> <span data-ttu-id="63dd0-106">OPENXML rappresenta pertanto la scelta più appropriata ogni volte che un provider di set di righe, ad esempio una tabella, può essere visualizzato come origine.</span><span class="sxs-lookup"><span data-stu-id="63dd0-106">Therefore, OPENXML is most appropriate wherever rowset providers, such as a table, can appear as a source.</span></span>  
  
 <span data-ttu-id="63dd0-107">Analogamente a OPENXML, un updategram consente di inserire, aggiornare o eliminare dati nel database. Un updategram, tuttavia, agisce sulle viste XML fornite dallo schema XSD (o XDR) con annotazioni, applicando, ad esempio, gli aggiornamenti alla vista XML fornita dallo schema di mapping.</span><span class="sxs-lookup"><span data-stu-id="63dd0-107">Like OPENXML, an updategram allows you to insert, update, or delete data in the database; however, an updategram works against the XML views provided by the annotated XSD (or an XDR) schema; for example, the updates are applied to the XML view provided by the mapping schema.</span></span> <span data-ttu-id="63dd0-108">Lo schema di mapping, a sua volta, dispone delle informazioni necessarie per eseguire il mapping di elementi e attributi XML alle tabelle e alle colonne di database corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="63dd0-108">The mapping schema, in turn, has the necessary information to map XML elements and attributes to the corresponding database tables and columns.</span></span> <span data-ttu-id="63dd0-109">L'updategram utilizza queste informazioni di mapping per aggiornare le tabelle e le colonne di database.</span><span class="sxs-lookup"><span data-stu-id="63dd0-109">The updategram uses this mapping information to update the database tables and columns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63dd0-110">In questa documentazione si presuppone che l'utente disponga di una certa familiarità con i modelli e il supporto dello schema di mapping in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63dd0-110">This documentation assumes that you are familiar with templates and mapping schema support in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="63dd0-111">Per ulteriori informazioni, vedere [Introduzione agli schemi XSD con Annotazioni &#40;SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="63dd0-111">For more information, see [Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span></span> <span data-ttu-id="63dd0-112">Per le applicazioni legacy che usano XDR, vedere la pagina relativa agli [schemi XDR con Annotazioni &#40;deprecati in SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="63dd0-112">For legacy applications that use XDR, see [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
## <a name="required-namespaces-in-the-updategram"></a><span data-ttu-id="63dd0-113">Spazi dei nomi necessari nell'updategram</span><span class="sxs-lookup"><span data-stu-id="63dd0-113">Required Namespaces in the Updategram</span></span>  
 <span data-ttu-id="63dd0-114">Le parole chiave in un updategram, ad esempio **\<sync>** , **\<before>** e **\<after>** , sono presenti nello `urn:schemas-microsoft-com:xml-updategram` spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="63dd0-114">The keywords in an updategram, such as **\<sync>**, **\<before>**, and **\<after>**, exist in the `urn:schemas-microsoft-com:xml-updategram` namespace.</span></span> <span data-ttu-id="63dd0-115">Il prefisso dello spazio dei nomi utilizzato è arbitrario.</span><span class="sxs-lookup"><span data-stu-id="63dd0-115">The namespace prefix that you use is arbitrary.</span></span> <span data-ttu-id="63dd0-116">In questa documentazione il prefisso `updg` indica lo spazio dei nomi `updategram`.</span><span class="sxs-lookup"><span data-stu-id="63dd0-116">In this documentation, the `updg` prefix denotes the `updategram` namespace.</span></span>  
  
## <a name="reviewing-syntax"></a><span data-ttu-id="63dd0-117">Esame della sintassi</span><span class="sxs-lookup"><span data-stu-id="63dd0-117">Reviewing Syntax</span></span>  
 <span data-ttu-id="63dd0-118">Un updategram è un modello con **\<sync>** **\<before>** blocchi, e **\<after>** che formano la sintassi dell'updategram.</span><span class="sxs-lookup"><span data-stu-id="63dd0-118">An updategram is a template with **\<sync>**, **\<before>**, and **\<after>** blocks that form the syntax of the updategram.</span></span> <span data-ttu-id="63dd0-119">Tale sintassi, nella sua forma più semplice, viene illustrata nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="63dd0-119">The following code shows this syntax in its simplest form:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync [mapping-schema= "AnnotatedSchemaFile.xml"] >  
    <updg:before>  
        ...  
    </updg:before>  
    <updg:after>  
        ...  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="63dd0-120">Nelle definizioni seguenti viene descritto il ruolo di ogni blocco:</span><span class="sxs-lookup"><span data-stu-id="63dd0-120">The following definitions describe the role of each of these blocks:</span></span>  
  
 **\<before>**  
 <span data-ttu-id="63dd0-121">Identifica lo stato esistente, denominato anche "stato before", dell'istanza del record.</span><span class="sxs-lookup"><span data-stu-id="63dd0-121">Identifies the existing state (also called "the before state") of the record instance.</span></span>  
  
 **\<after>**  
 <span data-ttu-id="63dd0-122">Identifica il nuovo stato in cui devono essere modificati i dati.</span><span class="sxs-lookup"><span data-stu-id="63dd0-122">Identifies the new state to which data is to be changed.</span></span>  
  
 **\<sync>**  
 <span data-ttu-id="63dd0-123">Contiene i **\<before>** **\<after>** blocchi e.</span><span class="sxs-lookup"><span data-stu-id="63dd0-123">Contains the **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="63dd0-124">Un **\<sync>** blocco può contenere più di un set di **\<before>** **\<after>** blocchi e.</span><span class="sxs-lookup"><span data-stu-id="63dd0-124">A **\<sync>** block can contain more than one set of **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="63dd0-125">Se è presente più di un set di **\<before>** **\<after>** blocchi e, questi blocchi (anche se sono vuoti) devono essere specificati come coppie.</span><span class="sxs-lookup"><span data-stu-id="63dd0-125">If there is more than one set of **\<before>** and **\<after>** blocks, these blocks (even if they are empty) must be specified as pairs.</span></span> <span data-ttu-id="63dd0-126">Inoltre, un updategram può avere più di un **\<sync>** blocco.</span><span class="sxs-lookup"><span data-stu-id="63dd0-126">Furthermore, an updategram can have more than one **\<sync>** block.</span></span> <span data-ttu-id="63dd0-127">Ogni **\<sync>** blocco è costituito da un'unità di transazione (il che significa che tutti gli elementi del **\<sync>** blocco sono completati o che non viene eseguita alcuna operazione).</span><span class="sxs-lookup"><span data-stu-id="63dd0-127">Each **\<sync>** block is one unit of transaction (which means that either everything in the **\<sync>** block is done or nothing is done).</span></span> <span data-ttu-id="63dd0-128">Se si specificano più **\<sync>** blocchi in un updategram, l'errore di un **\<sync>** blocco non influisce sugli altri **\<sync>** blocchi.</span><span class="sxs-lookup"><span data-stu-id="63dd0-128">If you specify multiple **\<sync>** blocks in an updategram, the failure of one **\<sync>** block does not affect the other **\<sync>** blocks.</span></span>  
  
 <span data-ttu-id="63dd0-129">Se un updategram elimina, inserisce o aggiorna un'istanza di record, dipende dal contenuto dei **\<before>** **\<after>** blocchi e:</span><span class="sxs-lookup"><span data-stu-id="63dd0-129">Whether an updategram deletes, inserts, or updates a record instance depends on the contents of the **\<before>** and **\<after>** blocks:</span></span>  
  
-   <span data-ttu-id="63dd0-130">Se un'istanza di record viene visualizzata solo nel **\<before>** blocco senza alcuna istanza corrispondente nel **\<after>** blocco, l'updategram esegue un'operazione di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="63dd0-130">If a record instance appears only in the **\<before>** block with no corresponding instance in the **\<after>** block, the updategram performs a delete operation.</span></span>  
  
-   <span data-ttu-id="63dd0-131">Se un'istanza di record viene visualizzata solo nel **\<after>** blocco senza alcuna istanza corrispondente nel **\<before>** blocco, si tratta di un'operazione di inserimento.</span><span class="sxs-lookup"><span data-stu-id="63dd0-131">If a record instance appears only in the **\<after>** block with no corresponding instance in the **\<before>** block, it is an insert operation.</span></span>  
  
-   <span data-ttu-id="63dd0-132">Se un'istanza di record viene visualizzata nel **\<before>** blocco e dispone di un'istanza corrispondente nel **\<after>** blocco, si tratta di un'operazione di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="63dd0-132">If a record instance appears in the **\<before>** block and has a corresponding instance in the **\<after>** block, it is an update operation.</span></span> <span data-ttu-id="63dd0-133">In questo caso, l'updategram aggiorna l'istanza del record ai valori specificati nel **\<after>** blocco.</span><span class="sxs-lookup"><span data-stu-id="63dd0-133">In this case, the updategram updates the record instance to the values that are specified in the **\<after>** block.</span></span>  
  
## <a name="specifying-a-mapping-schema-in-the-updategram"></a><span data-ttu-id="63dd0-134">Definizione di uno schema di mapping nell'updategram</span><span class="sxs-lookup"><span data-stu-id="63dd0-134">Specifying a Mapping Schema in the Updategram</span></span>  
 <span data-ttu-id="63dd0-135">In un updategram l'astrazione XML fornita da uno schema di mapping (sono supportati gli schemi XSD e XDR) può essere implicita o esplicita, ovvero un updategram può essere utilizzato con o senza uno schema di mapping specificato.</span><span class="sxs-lookup"><span data-stu-id="63dd0-135">In an updategram, the XML abstraction that is provided by a mapping schema (both XSD and XDR schemas are supported) can be implicit or explicit (that is, an updategram can work with or without a specified mapping schema).</span></span> <span data-ttu-id="63dd0-136">Se non si specifica uno schema di mapping, l'updategram presuppone un mapping implicito (il mapping predefinito), in cui ogni elemento nel **\<before>** blocco o nel **\<after>** blocco viene mappato a una tabella e l'attributo o l'elemento figlio di ogni elemento viene mappato a una colonna nel database.</span><span class="sxs-lookup"><span data-stu-id="63dd0-136">If you do not specify a mapping schema, the updategram assumes an implicit mapping (the default mapping), where each element in the **\<before>** block or **\<after>** block maps to a table and each element's child element or attribute maps to a column in the database.</span></span> <span data-ttu-id="63dd0-137">Se si specifica in modo esplicito uno schema di mapping, gli elementi e gli attributi nell'updategram deve corrispondere agli elementi e agli attributi nello schema di mapping.</span><span class="sxs-lookup"><span data-stu-id="63dd0-137">If you explicitly specify a mapping schema, the elements and attributes in the updategram must match the elements and attributes in the mapping schema.</span></span>  
  
### <a name="implicit-default-mapping"></a><span data-ttu-id="63dd0-138">Mapping implicito (predefinito)</span><span class="sxs-lookup"><span data-stu-id="63dd0-138">Implicit (default) Mapping</span></span>  
 <span data-ttu-id="63dd0-139">Nella maggior parte dei casi, un updategram che esegue aggiornamenti semplici può non richiedere uno schema di mapping.</span><span class="sxs-lookup"><span data-stu-id="63dd0-139">In most cases, an updategram that performs simple updates might not require a mapping schema.</span></span> <span data-ttu-id="63dd0-140">In questo caso, l'updategram si basa sullo schema di mapping predefinito.</span><span class="sxs-lookup"><span data-stu-id="63dd0-140">In this case, the updategram relies on the default mapping schema.</span></span>  
  
 <span data-ttu-id="63dd0-141">Nell'updategram seguente viene illustrato il mapping implicito.</span><span class="sxs-lookup"><span data-stu-id="63dd0-141">The following updategram demonstrates implicit mapping.</span></span> <span data-ttu-id="63dd0-142">In questo esempio l'updategram inserisce un nuovo cliente nella tabella Sales.Customer.</span><span class="sxs-lookup"><span data-stu-id="63dd0-142">In this example, the updategram inserts a new customer in the Sales.Customer table.</span></span> <span data-ttu-id="63dd0-143">Poiché questo updategram utilizza il mapping implicito, l' \<Sales.Customer> elemento esegue il mapping alla tabella Sales. Customer e gli attributi CustomerID e SalesPersonID vengono mappati alle colonne corrispondenti nella tabella Sales. Customer.</span><span class="sxs-lookup"><span data-stu-id="63dd0-143">Because this updategram uses implicit mapping, the \<Sales.Customer> element maps to the Sales.Customer table, and the CustomerID and SalesPersonID attributes map to the corresponding columns in the Sales.Customer table.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
<updg:before>  
</updg:before>  
<updg:after>  
    <Sales.Customer CustomerID="1" SalesPersonID="277" />  
    </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
### <a name="explicit-mapping"></a><span data-ttu-id="63dd0-144">Mapping esplicito</span><span class="sxs-lookup"><span data-stu-id="63dd0-144">Explicit Mapping</span></span>  
 <span data-ttu-id="63dd0-145">Se si specifica uno schema di mapping (XSD o XDR), l'updategram utilizza lo schema per determinare le tabelle e le colonne di database che devono essere aggiornate.</span><span class="sxs-lookup"><span data-stu-id="63dd0-145">If you specify a mapping schema (either XSD or XDR), the updategram uses the schema to determine the database tables and columns that are to be updated.</span></span>  
  
 <span data-ttu-id="63dd0-146">Se l'updategram esegue un aggiornamento complesso, ad esempio l'inserimento di record in più tabelle sulla base della relazione padre-figlio specificata nello schema di mapping, è necessario fornire in modo esplicito lo schema di mapping tramite l'attributo `mapping-schema` sui cui viene eseguito l'updategram.</span><span class="sxs-lookup"><span data-stu-id="63dd0-146">If the updategram performs a complex update (for example, inserting records in multiple tables on the basis of the parent-child relationship that is specified in the mapping schema), you must explicitly provide the mapping schema by using the `mapping-schema` attribute against which the updategram executes.</span></span>  
  
 <span data-ttu-id="63dd0-147">Poiché un updategram è un modello, il percorso specificato per lo schema di mapping nell'updategram è relativo al percorso del file di modello (relativo alla posizione di archiviazione dell'updategram).</span><span class="sxs-lookup"><span data-stu-id="63dd0-147">Because an updategram is a template, the path specified for the mapping schema in the updategram is relative to the location of the template file (relative to where the updategram is stored).</span></span> <span data-ttu-id="63dd0-148">Per ulteriori informazioni, vedere [specifica di uno schema di mapping con annotazioni in un Updategram &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="63dd0-148">For more information, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
## <a name="element-centric-and-attribute-centric-mapping-in-updategrams"></a><span data-ttu-id="63dd0-149">Mapping incentrato sugli elementi e mapping incentrato sugli attributi negli updategram</span><span class="sxs-lookup"><span data-stu-id="63dd0-149">Element-centric and Attribute-centric Mapping in Updategrams</span></span>  
 <span data-ttu-id="63dd0-150">Utilizzando il mapping predefinito, quando lo schema di mapping non viene specificato nell'updategram, gli elementi dell'updategram vengono mappati a tabelle, mentre gli elementi figlio (nel caso di mapping incentrato sugli elementi) e gli attributi (nel caso di mapping incentrato sugli attributi) vengono mappati a colonne.</span><span class="sxs-lookup"><span data-stu-id="63dd0-150">With default mapping (when the mapping schema is not specified in the updategram), the updategram elements map to tables and the  child elements (in the case of element-centric mapping) and the attributes (in the case of attribute-centric mapping) map to columns.</span></span>  
  
### <a name="element-centric-mapping"></a><span data-ttu-id="63dd0-151">Mapping incentrato sugli elementi</span><span class="sxs-lookup"><span data-stu-id="63dd0-151">Element-centric Mapping</span></span>  
 <span data-ttu-id="63dd0-152">In un updategram incentrato sugli elementi, un elemento contiene elementi figlio che indicano le proprietà dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="63dd0-152">In an element-centric updategram, an element contains child elements that denote the properties of the element.</span></span> <span data-ttu-id="63dd0-153">Si consideri, ad esempio, l'updategram seguente.</span><span class="sxs-lookup"><span data-stu-id="63dd0-153">As an example, refer to the following updategram.</span></span> <span data-ttu-id="63dd0-154">L' **\<Person.Contact>** elemento contiene gli **\<FirstName>** **\<LastName>** elementi figlio e.</span><span class="sxs-lookup"><span data-stu-id="63dd0-154">The **\<Person.Contact>** element contains the **\<FirstName>** and **\<LastName>** child elements.</span></span> <span data-ttu-id="63dd0-155">Questi elementi figlio sono proprietà dell' **\<Person.Contact>** elemento.</span><span class="sxs-lookup"><span data-stu-id="63dd0-155">These child elements are properties of the **\<Person.Contact>** element.</span></span>  
  
 <span data-ttu-id="63dd0-156">Poiché questo updategram non specifica uno schema di mapping, l'updategram utilizza il mapping implicito, in cui viene eseguito il mapping dell' **\<Person.Contact>** elemento alla tabella Person. Contact e i relativi elementi figlio vengono mappati alle colonne FirstName e LastName.</span><span class="sxs-lookup"><span data-stu-id="63dd0-156">Because this updategram does not specify a mapping schema, the updategram uses implicit mapping, where the **\<Person.Contact>** element maps to the Person.Contact table and its child elements map to the FirstName and LastName columns.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
  <updg:after>  
    <Person.Contact>  
       <FirstName>Catherine</FirstName>  
       <LastName>Abel</LastName>  
    </Person.Contact>  
  </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
### <a name="attribute-centric-mapping"></a><span data-ttu-id="63dd0-157">mapping incentrato sugli attributi</span><span class="sxs-lookup"><span data-stu-id="63dd0-157">Attribute-centric Mapping</span></span>  
 <span data-ttu-id="63dd0-158">In un mapping incentrato sugli attributi, gli elementi includono attributi.</span><span class="sxs-lookup"><span data-stu-id="63dd0-158">In an attribute-centric mapping, the elements have attributes.</span></span> <span data-ttu-id="63dd0-159">Nell'updategram seguente viene utilizzato il mapping incentrato sugli attributi.</span><span class="sxs-lookup"><span data-stu-id="63dd0-159">The following updategram uses attribute-centric mapping.</span></span> <span data-ttu-id="63dd0-160">In questo esempio l' **\<Person.Contact>** elemento è costituito dagli attributi **FirstName** e **LastName** .</span><span class="sxs-lookup"><span data-stu-id="63dd0-160">In this example, the **\<Person.Contact>** element consists of the **FirstName** and **LastName** attributes.</span></span> <span data-ttu-id="63dd0-161">Questi attributi sono le proprietà dell' **\<Person.Contact>** elemento.</span><span class="sxs-lookup"><span data-stu-id="63dd0-161">These attributes are the properties of the **\<Person.Contact>** element.</span></span> <span data-ttu-id="63dd0-162">Come nell'esempio precedente, questo updategram non specifica alcuno schema di mapping, pertanto si basa sul mapping implicito per eseguire il mapping dell' **\<Person.Contact>** elemento alla tabella Person. Contact e degli attributi dell'elemento alle rispettive colonne nella tabella.</span><span class="sxs-lookup"><span data-stu-id="63dd0-162">As in the previous example, this updategram specifies no mapping schema, so it relies on implicit mapping to map the **\<Person.Contact>** element to the Person.Contact table and the element's attributes to the respective columns in the table.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
  <updg:before>  
  </updg:before>  
  <updg:after>  
    <Person.Contact FirstName="Catherine" LastName="Abel" />  
  </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
### <a name="using-both-element-centric-and-attribute-centric-mapping"></a><span data-ttu-id="63dd0-163">Utilizzo di una combinazione di mapping incentrato sugli elementi e mapping incentrato sugli attributi</span><span class="sxs-lookup"><span data-stu-id="63dd0-163">Using Both Element-centric and Attribute-centric Mapping</span></span>  
 <span data-ttu-id="63dd0-164">È possibile specificare una combinazione di mapping incentrato sugli elementi e mapping incentrato sugli attributi, come illustrato nell'updategram seguente.</span><span class="sxs-lookup"><span data-stu-id="63dd0-164">You can specify a mix of element-centric and attribute-centric mapping, as shown in the following updategram.</span></span> <span data-ttu-id="63dd0-165">Si noti che l' **\<Person.Contact>** elemento contiene sia un attributo sia un elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="63dd0-165">Notice that the **\<Person.Contact>** element contains both an attribute and a child element.</span></span> <span data-ttu-id="63dd0-166">L'updategram si basa inoltre su un mapping implicito.</span><span class="sxs-lookup"><span data-stu-id="63dd0-166">Also, this updategram relies on implicit mapping.</span></span> <span data-ttu-id="63dd0-167">Pertanto, l'attributo **FirstName** e l' **\<LastName>** elemento figlio vengono mappati alle colonne corrispondenti nella tabella Person. Contact.</span><span class="sxs-lookup"><span data-stu-id="63dd0-167">Thus, the **FirstName** attribute and the **\<LastName>** child element map to corresponding columns in the Person.Contact table.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
  <updg:before>  
  </updg:before>  
  <updg:after>  
    <Person.Contact FirstName="Catherine" >  
       <LastName>Abel</LastName>  
    </Person.Contact>  
  </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
## <a name="working-with-characters-valid-in-sql-server-but-not-valid-in-xml"></a><span data-ttu-id="63dd0-168">Utilizzo di caratteri validi in SQL Server ma non validi in XML</span><span class="sxs-lookup"><span data-stu-id="63dd0-168">Working with Characters Valid in SQL Server but Not Valid in XML</span></span>  
 <span data-ttu-id="63dd0-169">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] i nomi di tabella possono includere uno spazio.</span><span class="sxs-lookup"><span data-stu-id="63dd0-169">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], table names can include a space.</span></span> <span data-ttu-id="63dd0-170">Questo tipo di nome di tabella, tuttavia, non è valido in XML.</span><span class="sxs-lookup"><span data-stu-id="63dd0-170">However, this type of table name is not valid in XML.</span></span>  
  
 <span data-ttu-id="63dd0-171">Per codificare i caratteri che sono [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] identificatori validi ma non sono identificatori XML validi, usare ' __xHHHH \_ \_ ' come valore di codifica, dove HHHH rappresenta il codice UCS-2 esadecimale a quattro cifre per il carattere nell'ordine del primo bit più significativo.</span><span class="sxs-lookup"><span data-stu-id="63dd0-171">To encode characters that are valid [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] identifiers but are not valid XML identifiers, use '__xHHHH\_\_' as the encoding value, where HHHH stands for the four-digit hexadecimal UCS-2 code for the character in the most significant bit-first order.</span></span> <span data-ttu-id="63dd0-172">Utilizzando questo schema di codifica, un carattere spazio viene sostituito con x0020 (il codice esadecimale a quattro cifre per uno spazio); in questo modo, il nome della tabella [Order Details] in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] diventa _x005B_Order_x0020_Details_x005D \_ in XML.</span><span class="sxs-lookup"><span data-stu-id="63dd0-172">Using this encoding scheme, a space character gets replaced with x0020 (the four-digit hexadecimal code for a space character); thus, the table name [Order Details] in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] becomes _x005B_Order_x0020_Details_x005D\_ in XML.</span></span>  
  
 <span data-ttu-id="63dd0-173">Analogamente, potrebbe essere necessario specificare nomi di elementi in tre parti, ad esempio \<[database].[owner].[table]> .</span><span class="sxs-lookup"><span data-stu-id="63dd0-173">Similarly, you might need to specify three-part element names, such as \<[database].[owner].[table]>.</span></span> <span data-ttu-id="63dd0-174">Poiché i caratteri parentesi quadre ([e]) non sono validi in XML, è necessario specificarlo come \<_x005B_database_x005D\_._x005B_owner_x005D\_._x005B_table_x005D\_> , dove _x005B \_ è la codifica per la parentesi quadra aperta ([) e _x005D \_ è la codifica per la parentesi quadra chiusa (]).</span><span class="sxs-lookup"><span data-stu-id="63dd0-174">Because the bracket characters ([ and ]) are not valid in XML, you must specify this as \<_x005B_database_x005D\_._x005B_owner_x005D\_._x005B_table_x005D\_>, where _x005B\_ is the encoding for the left bracket ([) and _x005D\_ is the encoding for the right bracket (]).</span></span>  
  
## <a name="executing-updategrams"></a><span data-ttu-id="63dd0-175">Esecuzione di updategram</span><span class="sxs-lookup"><span data-stu-id="63dd0-175">Executing Updategrams</span></span>  
 <span data-ttu-id="63dd0-176">Poiché un updategram è un modello, utilizza tutti i meccanismi di elaborazione di un modello.</span><span class="sxs-lookup"><span data-stu-id="63dd0-176">Because an updategram is a template, all the processing mechanisms of a template apply to the updategram.</span></span> <span data-ttu-id="63dd0-177">Per SQLXML 4.0, è possibile eseguire un updategram in una delle modalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="63dd0-177">For SQLXML 4.0, you can execute an updategram in either of the following ways:</span></span>  
  
-   <span data-ttu-id="63dd0-178">Inviandolo in un comando ADO.</span><span class="sxs-lookup"><span data-stu-id="63dd0-178">By submitting it in an ADO command.</span></span>  
  
-   <span data-ttu-id="63dd0-179">Inviandolo come comando OLE DB.</span><span class="sxs-lookup"><span data-stu-id="63dd0-179">By submitting it as an OLE DB command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63dd0-180">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63dd0-180">See Also</span></span>  
 [<span data-ttu-id="63dd0-181">Considerazioni sulla sicurezza degli updategram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="63dd0-181">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
