---
title: Utilizzo di annotazioni negli schemi XSD (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XSD schemas, about annotated XSD schemas
- annotations [SQLXML]
- relationships [SQLXML]
- relationships [SQLXML], hierarchical relationships
- hierarchical relationships [SQLXML]
- mapping schema [SQLXML], scenarios for using
ms.assetid: 78f318a4-7a36-473b-9852-a4bae6940ce5
author: rothja
ms.author: jroth
ms.openlocfilehash: e2be94aa5815593d7a5a2e0c00bcd8849e81484e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628602"
---
# <a name="using-annotations-in-xsd-schemas-sqlxml-40"></a><span data-ttu-id="94c53-102">Utilizzo delle annotazioni negli schemi XSD (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="94c53-102">Using Annotations in XSD Schemas (SQLXML 4.0)</span></span>
  <span data-ttu-id="94c53-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] SQLXML 4.0 il linguaggio dello schema XSD supporta le annotazioni in una modalità analoga a quella delle annotazioni introdotte con il linguaggio dello schema XDR (XML-Data Reduced).</span><span class="sxs-lookup"><span data-stu-id="94c53-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] SQLXML 4.0, the XSD schema language supports annotations in a manner similar to the annotations introduced in the XML-Data Reduced (XDR) schema language.</span></span> <span data-ttu-id="94c53-104">In XSD sono state introdotte alcune annotazioni aggiuntive che non sono supportate in XDR.</span><span class="sxs-lookup"><span data-stu-id="94c53-104">There are additional annotations introduced in XSD that are not supported in XDR.</span></span>  
  
 <span data-ttu-id="94c53-105">Queste annotazioni possono essere utilizzate all'interno dello schema XSD per specificare un mapping tra dati XML e dati relazionali,</span><span class="sxs-lookup"><span data-stu-id="94c53-105">These annotations can be used within the XSD schema to specify XML-to-relational mapping.</span></span> <span data-ttu-id="94c53-106">incluso un mapping tra elementi e attributi nello schema XSD e tabelle (viste) e colonne nei database.</span><span class="sxs-lookup"><span data-stu-id="94c53-106">This includes mapping between elements and attributes in the XSD schema to tables (views) and columns in the databases.</span></span>  
  
 <span data-ttu-id="94c53-107">Se non si specificano le annotazioni, viene eseguito il mapping predefinito.</span><span class="sxs-lookup"><span data-stu-id="94c53-107">If you do not specify the annotations, default mapping takes place.</span></span> <span data-ttu-id="94c53-108">Per impostazione predefinita, un elemento XSD con un tipo complesso viene mappato a un nome di tabella (vista) nel database specificato e un elemento o attributo con un tipo semplice viene mappato alla colonna che riporta lo stesso nome dell'elemento o dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="94c53-108">By default, an XSD element with a complex type maps to a table (view) name in the specified database, and an element or attribute with a simple type maps to the column with the same name as the element or attribute.</span></span>  
  
 <span data-ttu-id="94c53-109">Queste annotazioni possono essere utilizzate anche per specificare le relazioni gerarchiche in XML, rappresentando in questo modo le relazioni nel database, perché uno schema XSD è semplicemente una visualizzazione XML dei dati relazionali.</span><span class="sxs-lookup"><span data-stu-id="94c53-109">These annotations can also be used to specify the hierarchical relationships in XML-thus representing the relationships in the database, because an XSD schema is simply an XML view of relational data.</span></span>  
  
 <span data-ttu-id="94c53-110">In questa sezione vengono descritte le annotazioni che è possibile utilizzare con schemi XSD ed esempi pratici del loro utilizzo.</span><span class="sxs-lookup"><span data-stu-id="94c53-110">This section provides descriptions of the annotations you can use with XSD schemas and examples of their usage.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="94c53-111">In tutti gli esempi di questa sezione sono specificate query XPath semplici sullo schema XSD con annotazioni descritto in ogni esempio.</span><span class="sxs-lookup"><span data-stu-id="94c53-111">All the examples in this section specify simple XPath queries against the annotated XSD schema described in each example.</span></span> <span data-ttu-id="94c53-112">Si presuppone che l'utente abbia già acquisito familiarità con il linguaggio XPath.</span><span class="sxs-lookup"><span data-stu-id="94c53-112">Familiarity with the XPath language is assumed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="94c53-113">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="94c53-113">In This Section</span></span>  
 [<span data-ttu-id="94c53-114">Annotazioni XSD &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="94c53-114">XSD Annotations &#40;SQLXML 4.0&#41;</span></span>](xsd-annotations-sqlxml-4-0.md)  
 <span data-ttu-id="94c53-115">Vengono elencate le annotazioni che è possibile utilizzare con gli schemi XSD, le relative descrizioni e le annotazioni equivalenti per XDR.</span><span class="sxs-lookup"><span data-stu-id="94c53-115">Lists the annotations you can use with XSD schemas, their descriptions, and the equivalent annotations for XDR.</span></span>  
  
 [<span data-ttu-id="94c53-116">Mapping predefinito di elementi e attributi XSD a tabelle e colonne &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="94c53-116">Default Mapping of XSD Elements and Attributes to Tables and Columns &#40;SQLXML 4.0&#41;</span></span>](default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-4-0.md)  
 <span data-ttu-id="94c53-117">Viene illustrato il mapping predefinito e vengono forniti esempi di attività relative al mapping predefinito.</span><span class="sxs-lookup"><span data-stu-id="94c53-117">Explains default mapping and provides examples of tasks related to default mapping.</span></span>  
  
 [<span data-ttu-id="94c53-118">Mapping esplicito di attributi e elementi XSD a tabelle e colonne &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="94c53-118">Explicit Mapping of XSD Elements and Attributes to Tables and Columns &#40;SQLXML 4.0&#41;</span></span>](explicit-mapping-xsd-elements-and-attributes-to-tables-and-columns.md)  
 <span data-ttu-id="94c53-119">Viene illustrato il mapping esplicito con le annotazioni `sql:relation` e `sql:field` e vengono forniti esempi.</span><span class="sxs-lookup"><span data-stu-id="94c53-119">Explains explicit mapping with the `sql:relation` and `sql:field` annotations, and provides examples.</span></span>  
  
 [<span data-ttu-id="94c53-120">Definizione di relazioni tramite SQL: Relationship &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="94c53-120">Specifying Relationships Using sql:relationship &#40;SQLXML 4.0&#41;</span></span>](specifying-relationships-using-sql-relationship-sqlxml-4-0.md)  
 <span data-ttu-id="94c53-121">Viene descritta l'annotazione `sql:relationship` e vengono forniti esempi.</span><span class="sxs-lookup"><span data-stu-id="94c53-121">Describes and provides examples of the `sql:relationship` annotation.</span></span>  
  
 [<span data-ttu-id="94c53-122">Specifica dell'attributo SQL: inverse in SQL: Relationship &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="94c53-122">Specifying the sql:inverse Attribute on sql:relationship &#40;SQLXML 4.0&#41;</span></span>](specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md)  
 <span data-ttu-id="94c53-123">Viene descritta l'annotazione `sql:inverse`.</span><span class="sxs-lookup"><span data-stu-id="94c53-123">Describes the `sql:inverse` annotation.</span></span>  
  
 [<span data-ttu-id="94c53-124">Creazione di elementi costanti tramite SQL: is-constant &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="94c53-124">Creating Constant Elements Using sql:is-constant &#40;SQLXML 4.0&#41;</span></span>](creating-constant-elements-using-sql-is-constant-sqlxml-4-0.md)  
 <span data-ttu-id="94c53-125">Viene descritta l'annotazione `sql:is-constant` e vengono forniti esempi.</span><span class="sxs-lookup"><span data-stu-id="94c53-125">Describes and provides examples of the `sql:is-constant` annotation.</span></span>  
  
 [<span data-ttu-id="94c53-126">Esclusione di elementi dello schema dal documento XML risultante tramite SQL: mapping &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="94c53-126">Excluding Schema Elements from the Resulting XML Document Using sql:mapped &#40;SQLXML 4.0&#41;</span></span>](excluding-schema-elements-from-the-xml-document-using-sql-mapped.md)  
 <span data-ttu-id="94c53-127">Viene descritta l'annotazione `sql:mapped` e vengono forniti esempi.</span><span class="sxs-lookup"><span data-stu-id="94c53-127">Describes and provides examples of the `sql:mapped` annotation.</span></span>  
  
 [<span data-ttu-id="94c53-128">Filtro di valori tramite SQL: limit-field e SQL: Limit-Value &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="94c53-128">Filtering Values Using sql:limit-field and sql:limit-value &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/annotation-interpretation-sql-limit-field-and-sql-limit-value.md)  
 <span data-ttu-id="94c53-129">Vengono descritte le annotazioni `sql:limit-field` e `sql:limit-value` e vengono forniti esempi.</span><span class="sxs-lookup"><span data-stu-id="94c53-129">Describes and provides examples of the `sql:limit-field` and `sql:limit-value` annotations.</span></span>  
  
 [<span data-ttu-id="94c53-130">Identificazione delle colonne chiave mediante SQL: key-fields &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="94c53-130">Identifying Key Columns Using sql:key-fields &#40;SQLXML 4.0&#41;</span></span>](identifying-key-columns-using-sql-key-fields-sqlxml-4-0.md)  
 <span data-ttu-id="94c53-131">Viene descritta l'annotazione `sql:key-fields` e vengono forniti esempi.</span><span class="sxs-lookup"><span data-stu-id="94c53-131">Describes and provides examples of the `sql:key-fields` annotation.</span></span>  
  
 [<span data-ttu-id="94c53-132">Specifica di uno spazio dei nomi di destinazione mediante l'attributo targetNamespace &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="94c53-132">Specifying a Target Namespace Using the targetNamespace Attribute &#40;SQLXML 4.0&#41;</span></span>](specifying-a-target-namespace-using-the-targetnamespace-attribute-sqlxml-4-0.md)  
 <span data-ttu-id="94c53-133">Descrive e fornisce esempi dell'attributo **targetNamespace** .</span><span class="sxs-lookup"><span data-stu-id="94c53-133">Describes and provides examples of the **targetNamespace** attribute.</span></span>  
  
 [<span data-ttu-id="94c53-134">Creazione di attributi di tipo ID, IDREF e IDREFS validi con SQL: prefix &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="94c53-134">Creating Valid ID, IDREF, and IDREFS Type Attributes Using sql:prefix &#40;SQLXML 4.0&#41;</span></span>](creating-valid-id-idref-and-idrefs-type-attributes-using-sql-prefix-sqlxml-4-0.md)  
 <span data-ttu-id="94c53-135">Viene descritta l'annotazione `sql:prefix` e vengono forniti esempi.</span><span class="sxs-lookup"><span data-stu-id="94c53-135">Describes and provides examples of the `sql:prefix` annotation.</span></span>  
  
 [<span data-ttu-id="94c53-136">Coercizioni dei tipi di dati e l'annotazione sql: DataType &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="94c53-136">Data Type Coercions and the sql:datatype Annotation &#40;SQLXML 4.0&#41;</span></span>](data-type-coercions-and-the-sql-datatype-annotation-sqlxml-4-0.md)  
 <span data-ttu-id="94c53-137">Viene descritta l'annotazione `sql:datatype` e vengono forniti esempi.</span><span class="sxs-lookup"><span data-stu-id="94c53-137">Describes and provides examples of the `sql:datatype` annotation.</span></span>  
  
 [<span data-ttu-id="94c53-138">Mapping dei tipi di dati XSD ai tipi di dati XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="94c53-138">Mapping XSD Data Types to XPath Data Types &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md)  
 <span data-ttu-id="94c53-139">Viene fornita una tabella in cui i tipi di dati XSD, XDR e XPath vengono messi a confronto e le relative conversioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengono elencate.</span><span class="sxs-lookup"><span data-stu-id="94c53-139">Provides a table that compares XSD, XDR, and XPath datatypes and lists the relevant [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conversions.</span></span>  
  
 [<span data-ttu-id="94c53-140">Creazione di sezioni CDATA mediante SQL: Use-CDATA &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="94c53-140">Creating CDATA Sections Using sql:use-cdata &#40;SQLXML 4.0&#41;</span></span>](creating-cdata-sections-using-sql-use-cdata-sqlxml-4-0.md)  
 <span data-ttu-id="94c53-141">Viene descritta l'annotazione `sql:use-data` e vengono forniti esempi.</span><span class="sxs-lookup"><span data-stu-id="94c53-141">Describes and provides examples of the `sql:use-data` annotation.</span></span>  
  
 [<span data-ttu-id="94c53-142">Richiesta di riferimenti URL a dati BLOB tramite SQL: encode &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="94c53-142">Requesting URL References to BLOB Data Using sql:encode &#40;SQLXML 4.0&#41;</span></span>](requesting-url-references-to-blob-data-using-sql-encode-sqlxml-4-0.md)  
 <span data-ttu-id="94c53-143">Viene descritta l'annotazione `sql:encode` e vengono forniti esempi.</span><span class="sxs-lookup"><span data-stu-id="94c53-143">Describes and provides examples of the `sql:encode` annotation.</span></span>  
  
 [<span data-ttu-id="94c53-144">Recupero di dati non utilizzati tramite SQL: overflow-field &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="94c53-144">Retrieving Unconsumed Data Using the sql:overflow-field &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/annotation-interpretation-sql-overflow-field.md)  
 <span data-ttu-id="94c53-145">Viene descritta l'annotazione `sql:overflow-field` e vengono forniti esempi.</span><span class="sxs-lookup"><span data-stu-id="94c53-145">Describes and provides examples of the `sql:overflow-field` annotation.</span></span>  
  
 [<span data-ttu-id="94c53-146">Nascondere gli elementi e gli attributi utilizzando sql:hide</span><span class="sxs-lookup"><span data-stu-id="94c53-146">Hiding Elements and Attributes by Using sql:hide</span></span>](hiding-elements-and-attributes-by-using-sql-hide.md)  
 <span data-ttu-id="94c53-147">Viene descritta l'annotazione `sql:hide` e vengono forniti esempi.</span><span class="sxs-lookup"><span data-stu-id="94c53-147">Describes and provides examples of the `sql:hide` annotation.</span></span>  
  
 [<span data-ttu-id="94c53-148">Utilizzo delle annotazioni sql:identity e sql:guid</span><span class="sxs-lookup"><span data-stu-id="94c53-148">Using the sql:identity and sql:guid Annotations</span></span>](using-the-sql-identity-and-sql-guid-annotations.md)  
 <span data-ttu-id="94c53-149">Vengono descritte le annotazioni `sql:identity` e `sql:guid` e vengono forniti esempi.</span><span class="sxs-lookup"><span data-stu-id="94c53-149">Describes and provides examples of the `sql:identity` and `sql:guid` annotations.</span></span>  
  
 [<span data-ttu-id="94c53-150">Specifica del livello di nidificazione nelle relazioni ricorsive mediante sql:max-depth</span><span class="sxs-lookup"><span data-stu-id="94c53-150">Specifying Depth in Recursive Relationships by Using sql:max-depth</span></span>](specifying-depth-in-recursive-relationships-by-using-sql-max-depth.md)  
 <span data-ttu-id="94c53-151">Viene descritta l'annotazione `sql:max-depth` e vengono forniti esempi.</span><span class="sxs-lookup"><span data-stu-id="94c53-151">Describes and provides examples of the `sql:max-depth` annotation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94c53-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94c53-152">See Also</span></span>  
 [<span data-ttu-id="94c53-153">Considerazioni sulla sicurezza dello schema con annotazioni &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="94c53-153">Annotated Schema Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md)  
  
  
