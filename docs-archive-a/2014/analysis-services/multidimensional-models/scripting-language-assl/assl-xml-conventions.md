---
title: Convenzioni XML di ASSL | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- whitespace [Analysis Services Scripting Language]
- trailing whitespace
- XSD data types [Analysis Services Scripting Language]
- inheritance [Analysis Services Scripting Language]
- cardinality [Analysis Services Scripting Language]
- white space [Analysis Services Scripting Language]
- ASSL, XML conventions
- defaults [Analysis Services Scripting Language]
- leading whitespace
- Analysis Services Scripting Language, XML conventions
- XML [Analysis Services Scripting Language]
- hierarchies [Analysis Services Scripting Language]
- inherited defaults [Analysis Services Scripting Language]
ms.assetid: bce4edad-4420-41ce-9672-8c00c5c0dec6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9b70742b07fd6450b01cf205147a05f40c4b6121
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721876"
---
# <a name="assl-xml-conventions"></a><span data-ttu-id="c5e11-102">Convenzioni XML di ASSL</span><span class="sxs-lookup"><span data-stu-id="c5e11-102">ASSL XML Conventions</span></span>
  <span data-ttu-id="c5e11-103">Nel linguaggio ASSL (Analysis Services Scripting Language) la gerarchia di oggetti viene rappresentata come un set di tipi di elementi, ciascuno dei quali definisce gli elementi figlio che può contenere.</span><span class="sxs-lookup"><span data-stu-id="c5e11-103">Analysis Services Scripting Language (ASSL) represents the hierarchy of objects as a set of element types, each of which defines the child elements they can contain.</span></span>  
  
 <span data-ttu-id="c5e11-104">Per rappresentare la gerarchia di oggetti, in ASSL vengono utilizzate le convenzioni XML seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5e11-104">To represent the object hierarchy, ASSL uses the following XML conventions:</span></span>  
  
-   <span data-ttu-id="c5e11-105">Tutti gli oggetti e le proprietà sono rappresentati come elementi, ad eccezione degli attributi XML standard, ad esempio "XML: lang".</span><span class="sxs-lookup"><span data-stu-id="c5e11-105">All objects and properties are represented as elements, except for standard XML attributes such as 'xml:lang'.</span></span>  
  
-   <span data-ttu-id="c5e11-106">Sia i nomi di elemento che i valori di enumerazione seguono la convenzione di denominazione di Microsoft .NET Framework basata sulla convenzione Pascal senza caratteri di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="c5e11-106">Both element names and enumeration values follow the Microsoft .NET Framework naming convention of Pascal casing with no underscores.</span></span>  
  
-   <span data-ttu-id="c5e11-107">La combinazione di lettere maiuscole e minuscole di tutti i valori viene mantenuta.</span><span class="sxs-lookup"><span data-stu-id="c5e11-107">The case of all values is preserved.</span></span> <span data-ttu-id="c5e11-108">I valori relativi alle enumerazioni rispettano inoltre la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="c5e11-108">Values for enumerations are also case-sensitive.</span></span>  
  
 <span data-ttu-id="c5e11-109">Oltre all'elenco di convenzioni indicato, in Analysis Services vengono seguite inoltre convenzioni specifiche relative alla cardinalità, l'ereditarietà, gli spazi vuoti, i tipi di dati e i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="c5e11-109">In addition to this list of conventions, Analysis Services also follows certain conventions regarding cardinality, inheritance, whitespace, data types, and default values.</span></span>  
  
## <a name="cardinality"></a><span data-ttu-id="c5e11-110">Cardinalità</span><span class="sxs-lookup"><span data-stu-id="c5e11-110">Cardinality</span></span>  
 <span data-ttu-id="c5e11-111">Quando la cardinalità di un elemento è maggiore di 1, è presente una raccolta di elementi XML che incapsula tale elemento.</span><span class="sxs-lookup"><span data-stu-id="c5e11-111">When an element has a cardinality that is greater than 1, there is an XML element collection that encapsulates this element.</span></span> <span data-ttu-id="c5e11-112">Per il nome della raccolta viene utilizzata la forma plurale degli elementi contenuti nella raccolta stessa.</span><span class="sxs-lookup"><span data-stu-id="c5e11-112">The name of collection uses the plural form of the elements contained in the collection.</span></span> <span data-ttu-id="c5e11-113">Nel frammento XML seguente, ad esempio, viene rappresentata la raccolta `Dimensions` in un elemento `Database`:</span><span class="sxs-lookup"><span data-stu-id="c5e11-113">For example, the following XML fragment represents the `Dimensions` collection within a `Database` element:</span></span>  
  
 `<Database>`  
  
 `...`  
  
 `<Dimensions>`  
  
 `<Dimension>`  
  
 `...`  
  
 `</Dimension>`  
  
 `<Dimension>`  
  
 `...`  
  
 `</Dimension>`  
  
 `</Dimensions>`  
  
 `</Database>`  
  
 ``  
  
 <span data-ttu-id="c5e11-114">L'ordine in cui sono visualizzati gli elementi non è importante.</span><span class="sxs-lookup"><span data-stu-id="c5e11-114">The order in which elements appear is unimportant.</span></span>  
  
## <a name="inheritance"></a><span data-ttu-id="c5e11-115">Ereditarietà</span><span class="sxs-lookup"><span data-stu-id="c5e11-115">Inheritance</span></span>  
 <span data-ttu-id="c5e11-116">L'ereditarietà viene utilizzata quando sono presenti oggetti distinti cui sono associati set di proprietà sovrapposti, ma con differenze significative.</span><span class="sxs-lookup"><span data-stu-id="c5e11-116">Inheritance is used when there are distinct objects that have overlapping but significantly different sets of properties.</span></span> <span data-ttu-id="c5e11-117">Esempi di tali oggetti sovrapposti, ma distinti, sono i cubi virtuali, i cubi collegati e i cubi regolari.</span><span class="sxs-lookup"><span data-stu-id="c5e11-117">Examples of such overlapping but distinct objects are virtual cubes, linked cubes, and regular cubes.</span></span> <span data-ttu-id="c5e11-118">Per questo tipo di oggetti, in Analysis Services viene utilizzato l'attributo standard `type` dello spazio dei nomi di istanze XML per indicare l'ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="c5e11-118">For overlapping but distinct object, Analysis Services uses the standard `type` attribute from the XML Instance Namespace to indicate the inheritance.</span></span> <span data-ttu-id="c5e11-119">Nel frammento XML seguente viene illustrato ad esempio il modo in cui l'attributo `type` identifica se un elemento `Cube` eredita da un cubo regolare o da un cubo virtuale:</span><span class="sxs-lookup"><span data-stu-id="c5e11-119">For example, the following XML fragment shows how the `type` attribute identifies whether a `Cube` element inherits from a regular cube or from a virtual cube:</span></span>  
  
 `<Cubes>`  
  
 `<Cube xsi:type="RegularCube">`  
  
 `<Name>Sales</Name>`  
  
 `...`  
  
 `</Cube>`  
  
 `<Cube xsi:type="VirtualCube">`  
  
 `<Name>SalesAndInventory</Name>`  
  
 `...`  
  
 `</Cube>`  
  
 `</Cubes>`  
  
 ``  
  
 <span data-ttu-id="c5e11-120">In genere l'ereditarietà non viene utilizzata quando a più tipi è associata una proprietà con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="c5e11-120">Inheritance is generally not used when multiple types have a property of the same name.</span></span> <span data-ttu-id="c5e11-121">Le proprietà `Name` e `ID` vengono visualizzate ad esempio in molti elementi, ma non sono state promosse a un tipo astratto.</span><span class="sxs-lookup"><span data-stu-id="c5e11-121">For example, the `Name` and `ID` properties appear on many elements, but these properties have not been promoted to an abstract type.</span></span>  
  
## <a name="whitespace"></a><span data-ttu-id="c5e11-122">Spazi vuoti</span><span class="sxs-lookup"><span data-stu-id="c5e11-122">Whitespace</span></span>  
 <span data-ttu-id="c5e11-123">Gli spazi vuoti all'interno di un valore di elemento vengono mantenuti,</span><span class="sxs-lookup"><span data-stu-id="c5e11-123">Whitespace within an element value is preserved.</span></span> <span data-ttu-id="c5e11-124">mentre gli spazi vuoti iniziali e finali vengono sempre rimossi.</span><span class="sxs-lookup"><span data-stu-id="c5e11-124">However, leading and trailing whitespace is always trimmed.</span></span> <span data-ttu-id="c5e11-125">Gli elementi seguenti contengono ad esempio lo stesso testo che differisce tuttavia per il numero di spazi vuoti all'interno. Di conseguenza tali elementi vengono considerati come se i relativi valori fossero diversi:</span><span class="sxs-lookup"><span data-stu-id="c5e11-125">For example, the following elements have the same text but differing amounts of whitespace within that text, and are therefore treated as if they have different values:</span></span>  
  
 `<Description>My text<Description>`  
  
 `<Description>My  text<Description>`  
  
 ``  
  
 <span data-ttu-id="c5e11-126">Gli elementi seguenti differiscono invece solo per gli spazi vuoti iniziali e finali e vengono pertanto considerati come se i relativi valori fossero equivalenti:</span><span class="sxs-lookup"><span data-stu-id="c5e11-126">However, the following elements vary only in leading and trailing whitespace, and are therefore treated as if they have equivalent values:</span></span>  
  
 `<Description>My text<Description>`  
  
 `<Description>  My text  <Description>`  
  
 ``  
  
## <a name="data-types"></a><span data-ttu-id="c5e11-127">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="c5e11-127">Data Types</span></span>  
 <span data-ttu-id="c5e11-128">In Analysis Services vengono utilizzati i seguenti tipi di dati XML Schema Definition Language (XSD) standard:</span><span class="sxs-lookup"><span data-stu-id="c5e11-128">Analysis Services uses the following standard XML Schema definition language (XSD) data types:</span></span>  
  
 `Int`  
 <span data-ttu-id="c5e11-129">Valore intero compreso tra-231 e 231-1.</span><span class="sxs-lookup"><span data-stu-id="c5e11-129">An integer value in the range of -231 to 231 - 1.</span></span>  
  
 `Long`  
 <span data-ttu-id="c5e11-130">Un valore intero compreso tra-263 e 263-1.</span><span class="sxs-lookup"><span data-stu-id="c5e11-130">An integer value in range of -263 to 263 - 1.</span></span>  
  
 `String`  
 <span data-ttu-id="c5e11-131">Valore stringa conforme alle regole globali seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5e11-131">A string value that conforms to the following global rules:</span></span>  
  
-   <span data-ttu-id="c5e11-132">Rimozione dei caratteri di controllo.</span><span class="sxs-lookup"><span data-stu-id="c5e11-132">Control characters are stripped out.</span></span>  
  
-   <span data-ttu-id="c5e11-133">Eliminazione degli spazi vuoti iniziali e finali.</span><span class="sxs-lookup"><span data-stu-id="c5e11-133">Leading and trailing white space is trimmed.</span></span>  
  
-   <span data-ttu-id="c5e11-134">Mantenimento degli spazi vuoti interni.</span><span class="sxs-lookup"><span data-stu-id="c5e11-134">Internal white space is preserved.</span></span>  
  
 <span data-ttu-id="c5e11-135">Per le proprietà `Name` e `ID` sono presenti limitazioni speciali relative ai caratteri validi negli elementi della stringa.</span><span class="sxs-lookup"><span data-stu-id="c5e11-135">`Name` and `ID` properties have special limitations on valid characters in string elements.</span></span> <span data-ttu-id="c5e11-136">Per ulteriori informazioni sulle `Name` `ID` convenzioni e, vedere [oggetti ASSL e caratteristiche degli](assl-objects-and-object-characteristics.md)oggetti.</span><span class="sxs-lookup"><span data-stu-id="c5e11-136">For additional information about `Name` and `ID` conventions, see [ASSL Objects and Object Characteristics](assl-objects-and-object-characteristics.md).</span></span>  
  
 `DateTime`  
 <span data-ttu-id="c5e11-137">`DateTime`Struttura dalla .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c5e11-137">A `DateTime` structure from the .NET Framework.</span></span> <span data-ttu-id="c5e11-138">Un valore `DateTime` non può essere NULL.</span><span class="sxs-lookup"><span data-stu-id="c5e11-138">A `DateTime` value cannot be NULL.</span></span> <span data-ttu-id="c5e11-139">La data meno recente supportata dal tipo di dati `DataTime` è rappresentata dall'1 gennaio 1601, disponibile per i programmatori come `DateTime.MinValue`.</span><span class="sxs-lookup"><span data-stu-id="c5e11-139">The lowest date supported by the `DataTime` data type is January 1, 1601, which is available to programmers as `DateTime.MinValue`.</span></span> <span data-ttu-id="c5e11-140">La data meno recente supportata indica che un valore `DateTime` è mancante.</span><span class="sxs-lookup"><span data-stu-id="c5e11-140">The lowest supported date indicates that a `DateTime` value is missing.</span></span>  
  
 `Boolean`  
 <span data-ttu-id="c5e11-141">Enumerazione con due soli valori, ovvero {true, false} o {0, 1}.</span><span class="sxs-lookup"><span data-stu-id="c5e11-141">An enumeration with only two values, such as {true, false} or {0, 1}.</span></span>  
  
## <a name="default-values"></a><span data-ttu-id="c5e11-142">Valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="c5e11-142">Default Values</span></span>  
 <span data-ttu-id="c5e11-143">In Analysis Services vengono utilizzati i valori predefiniti elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="c5e11-143">Analysis Services uses the defaults listed in the following table.</span></span>  
  
|<span data-ttu-id="c5e11-144">Tipo di dati XML</span><span class="sxs-lookup"><span data-stu-id="c5e11-144">XML data type</span></span>|<span data-ttu-id="c5e11-145">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="c5e11-145">Default value</span></span>|  
|-------------------|-------------------|  
|`Boolean`|<span data-ttu-id="c5e11-146">Falso</span><span class="sxs-lookup"><span data-stu-id="c5e11-146">False</span></span>|  
|`String`|<span data-ttu-id="c5e11-147">"" (stringa vuota)</span><span class="sxs-lookup"><span data-stu-id="c5e11-147">"" (empty string)</span></span>|  
|<span data-ttu-id="c5e11-148">`Integer` o `Long`</span><span class="sxs-lookup"><span data-stu-id="c5e11-148">`Integer` or `Long`</span></span>|<span data-ttu-id="c5e11-149">0 (zero)</span><span class="sxs-lookup"><span data-stu-id="c5e11-149">0 (zero)</span></span>|  
|`Timestamp`|<span data-ttu-id="c5e11-150">12:00:00 AM, 1/1/0001 (corrispondente a .NET Framework `System.DateTime` con 0 cicli)</span><span class="sxs-lookup"><span data-stu-id="c5e11-150">12:00:00 AM, 1/1/0001 (corresponding to a the .NET Frameworks `System.DateTime` with 0 ticks)</span></span>|  
  
 <span data-ttu-id="c5e11-151">Un elemento presente, ma vuoto, viene interpretato come se il relativo valore fosse una stringa Null e non quello predefinito.</span><span class="sxs-lookup"><span data-stu-id="c5e11-151">An element that is present but empty is interpreted as having a value of a null string, not the default value.</span></span>  
  
### <a name="inherited-defaults"></a><span data-ttu-id="c5e11-152">Valori predefiniti ereditati</span><span class="sxs-lookup"><span data-stu-id="c5e11-152">Inherited Defaults</span></span>  
 <span data-ttu-id="c5e11-153">Alcune proprietà specificate per un oggetto forniscono i valori predefiniti per la stessa proprietà in oggetti figlio o discendenti.</span><span class="sxs-lookup"><span data-stu-id="c5e11-153">Some properties that are specified on an object provide default values for the same property on child or descendant objects.</span></span> <span data-ttu-id="c5e11-154">`Cube.StorageMode` fornisce ad esempio il valore predefinito per `Partition.StorageMode`.</span><span class="sxs-lookup"><span data-stu-id="c5e11-154">For example, `Cube.StorageMode` provides the default value for `Partition.StorageMode`.</span></span> <span data-ttu-id="c5e11-155">Le regole che Analysis Services applica ai valori predefiniti ereditati sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5e11-155">The rules that Analysis Services applies for inherited default values are as follows:</span></span>  
  
-   <span data-ttu-id="c5e11-156">Quando in XML la proprietà per l'oggetto figlio è Null, per impostazione predefinita viene utilizzato il valore ereditato.</span><span class="sxs-lookup"><span data-stu-id="c5e11-156">When the property for the child object is null in the XML, its value defaults to the inherited value.</span></span> <span data-ttu-id="c5e11-157">Se tuttavia si esegue una query relativa al valore nel server, viene restituito il valore Null dell'elemento XML.</span><span class="sxs-lookup"><span data-stu-id="c5e11-157">However, if you query the value from the server, the server returns the null value of the XML element.</span></span>  
  
-   <span data-ttu-id="c5e11-158">Non è possibile determinare a livello di programmazione se la proprietà di un oggetto figlio è stata impostata direttamente su tale oggetto oppure se è stata ereditata.</span><span class="sxs-lookup"><span data-stu-id="c5e11-158">It is not possible to determine programmatically whether the property of a child object has been set directly on the child object or inherited.</span></span>  
  
 <span data-ttu-id="c5e11-159">Per alcuni elementi sono specificati valori predefiniti che si applicano quando l'elemento è mancante.</span><span class="sxs-lookup"><span data-stu-id="c5e11-159">Some elements have defined defaults that apply when the element is missing.</span></span> <span data-ttu-id="c5e11-160">Gli elementi `Dimension` nel frammento XML seguente, ad esempio, sono equivalenti anche se un elemento `Dimension` contiene un elemento `Visible`, mentre l'altro elemento `Dimension` non lo contiene.</span><span class="sxs-lookup"><span data-stu-id="c5e11-160">For example, the `Dimension` elements in the following XML fragment are equivalent even though one `Dimension` element contains a `Visible` element, but the other `Dimension` element does not.</span></span>  
  
 `<Dimension>`  
  
 `<Name>Product</Name>`  
  
 `</Dimension>`  
  
 `<Dimension>`  
  
 `<Name>Product</ Name>`  
  
 `<Visible>true</Visible>`  
  
 `</Dimension>`  
  
 <span data-ttu-id="c5e11-161">Per ulteriori informazioni sui valori predefiniti ereditati, vedere [oggetti ASSL e caratteristiche degli](assl-objects-and-object-characteristics.md)oggetti.</span><span class="sxs-lookup"><span data-stu-id="c5e11-161">For more information on inherited defaults, see [ASSL Objects and Object Characteristics](assl-objects-and-object-characteristics.md).</span></span>  
  
  
