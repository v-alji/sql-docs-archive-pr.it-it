---
title: Sintassi di base della clausola FOR XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- BINARY BASE64 directive
- ROOT directive
- FOR XML clause, BINARY BASE64 directive
- FOR XML clause, syntax
- FOR XML clause, ROOT directive
ms.assetid: df19ecbf-d28e-4e9c-aaa3-700f8bbd3be4
author: rothja
ms.author: jroth
ms.openlocfilehash: dc0410e7a54674673f64442d8a3cf9476d250033
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623953"
---
# <a name="basic-syntax-of-the-for-xml-clause"></a><span data-ttu-id="a5ad3-102">Sintassi di base della clausola FOR XML</span><span class="sxs-lookup"><span data-stu-id="a5ad3-102">Basic Syntax of the FOR XML Clause</span></span>
  <span data-ttu-id="a5ad3-103">La modalità FOR XML può essere RAW, AUTO, EXPLICIT o PATH.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-103">The FOR XML mode can be RAW, AUTO, EXPLICIT, or PATH.</span></span> <span data-ttu-id="a5ad3-104">Tale modalità determina la forma della struttura XML risultante.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-104">It determines the shape of the resulting XML.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a5ad3-105">La direttiva XMLDATA all'opzione FOR XML è deprecata.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-105">The XMLDATA directive to the FOR XML option is deprecated.</span></span> <span data-ttu-id="a5ad3-106">Utilizzare la generazione XSD in caso di modalità RAW e AUTO.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-106">Use XSD generation in the case of RAW and AUTO modes.</span></span> <span data-ttu-id="a5ad3-107">Non sono disponibili sostituzioni per la direttiva XMLDATA in modalità EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-107">There is no replacement for the XMLDATA directive in EXPLICT mode.</span></span> [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
 <span data-ttu-id="a5ad3-108">Di seguito è riportata la sintassi di base descritta nella [clausola for (Transact-SQL)](/sql/t-sql/queries/select-for-clause-transact-sql):</span><span class="sxs-lookup"><span data-stu-id="a5ad3-108">Following is the basic syntax that is described in [FOR Clause (Transact-SQL)](/sql/t-sql/queries/select-for-clause-transact-sql):</span></span>  
  
```  
[ FOR { BROWSE | <XML> } ]  
<XML> ::=  
XML   
    {   
      { RAW [ ('ElementName') ] | AUTO }   
        [   
           <CommonDirectives>   
           [ , { XMLDATA | XMLSCHEMA [ ('TargetNameSpaceURI') ]} ]   
           [ , ELEMENTS [ XSINIL | ABSENT ]   
        ]  
      | EXPLICIT   
        [   
           <CommonDirectives>   
           [ , XMLDATA ]   
        ]  
      | PATH [ ('ElementName') ]   
        [   
           <CommonDirectives>   
           [ , ELEMENTS [ XSINIL | ABSENT ] ]  
        ]  
     }   
  
 <CommonDirectives> ::=   
   [ , BINARY BASE64 ]  
   [ , TYPE ]  
   [ , ROOT [ ('RootName') ] ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="a5ad3-109">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a5ad3-109">Arguments</span></span>  
 <span data-ttu-id="a5ad3-110">RAW[('*ElementName*')]</span><span class="sxs-lookup"><span data-stu-id="a5ad3-110">RAW[('*ElementName*')]</span></span>  
 <span data-ttu-id="a5ad3-111">Converte ogni riga del set dei risultati della query in un elemento XML con l'identificatore generico, \<row />, come tag dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-111">Takes the query result and transforms each row in the result set into an XML element that has a generic identifier, \<row />, as the element tag.</span></span> <span data-ttu-id="a5ad3-112">È possibile specificare facoltativamente il nome dell'elemento riga quando si utilizza questa direttiva.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-112">You can optionally specify a name for the row element when you use this directive.</span></span> <span data-ttu-id="a5ad3-113">La struttura XML risultante utilizzerà il valore *ElementName* specificato come elemento riga generato per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-113">The resulting XML will use the specified *ElementName* as the row element generated for each row.</span></span> <span data-ttu-id="a5ad3-114">Per altre informazioni, vedere [Usare la modalità RAW con FOR XML](use-raw-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a5ad3-114">For more information, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="a5ad3-115">AUTO</span><span class="sxs-lookup"><span data-stu-id="a5ad3-115">AUTO</span></span>  
 <span data-ttu-id="a5ad3-116">Restituisce i risultati della query in un semplice albero XML nidificato.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-116">Returns query results in a simple, nested XML tree.</span></span> <span data-ttu-id="a5ad3-117">Ogni tabella nella clausola FROM, per cui è specificata almeno una colonna nella clausola SELECT, viene rappresentata come elemento XML.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-117">Each table in the FROM clause for which at least one column is listed in the SELECT clause is represented as an XML element.</span></span> <span data-ttu-id="a5ad3-118">Le colonne elencate nella clausola SELECT vengono mappate agli attributi di elemento appropriati.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-118">The columns listed in the SELECT clause are mapped to the appropriate element attributes.</span></span> <span data-ttu-id="a5ad3-119">Per altre informazioni, vedere [Usare la modalità AUTO con FOR XML](use-auto-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a5ad3-119">For more information, see [Use AUTO Mode with FOR XML](use-auto-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="a5ad3-120">EXPLICIT</span><span class="sxs-lookup"><span data-stu-id="a5ad3-120">EXPLICIT</span></span>  
 <span data-ttu-id="a5ad3-121">Specifica che la forma dell'albero XML risultante viene definita in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-121">Specifies that the shape of the resulting XML tree is defined explicitly.</span></span> <span data-ttu-id="a5ad3-122">Con questa modalità è tuttavia necessario che le query siano scritte in modo che le informazioni aggiuntive sulla nidificazione desiderata vengano specificate in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-122">By using this mode, queries must be written in a particular way so additional information about the nesting you want is specified explicitly.</span></span> <span data-ttu-id="a5ad3-123">Per altre informazioni, vedere [Usare la modalità EXPLICIT con FOR XML](use-explicit-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a5ad3-123">For more information, see [Use EXPLICIT Mode with FOR XML](use-explicit-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="a5ad3-124">PATH</span><span class="sxs-lookup"><span data-stu-id="a5ad3-124">PATH</span></span>  
 <span data-ttu-id="a5ad3-125">Consente di combinare facilmente elementi e attributi, nonché di introdurre una nidificazione aggiuntiva per rappresentare proprietà complesse.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-125">Provides a simpler way to mix elements and attributes, and to introduce additional nesting for representing complex properties.</span></span> <span data-ttu-id="a5ad3-126">È possibile utilizzare le query in modalità FOR XML EXPLICIT per costruire questo tipo di struttura XML da un set di righe, ma la modalità PATH costituisce un'alternativa più semplice.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-126">You can use FOR XML EXPLICIT mode queries to construct this kind of XML from a rowset, but the PATH mode provides a simpler alternative to the possibly cumbersome EXPLICIT mode queries.</span></span> <span data-ttu-id="a5ad3-127">La modalità PATH, insieme alla possibilità di scrivere query FOR XML nidificate e alla direttiva TYPE per restituire istanze di tipo **xml** , consente di formulare più facilmente le query.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-127">PATH mode, together with the ability to write nested FOR XML queries and the TYPE directive to return **xml** type instances, allows you to write queries with less complexity.</span></span> <span data-ttu-id="a5ad3-128">e rappresenta un'alternativa alla scrittura della maggior parte delle query in modalità EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-128">It provides an alternative to writing most EXPLICIT mode queries.</span></span> <span data-ttu-id="a5ad3-129">Per impostazione predefinita, la modalità PATH genera un wrapper dell'elemento \<row> per ogni riga nel set dei risultati.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-129">By default, PATH mode generates a \<row> element wrapper for each row in the result set.</span></span> <span data-ttu-id="a5ad3-130">È possibile specificare facoltativamente il nome di un elemento.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-130">You can optionally specify an element name.</span></span> <span data-ttu-id="a5ad3-131">In tal caso, il nome specificato viene utilizzato come nome dell'elemento wrapper.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-131">If you do, the specified name is used as the wrapper element name.</span></span> <span data-ttu-id="a5ad3-132">Se si specifica una stringa vuota (FOR XML PATH ('')), non viene generato alcun elemento wrapper.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-132">If you provide an empty string (FOR XML PATH ('')), no wrapper element is generated.</span></span> <span data-ttu-id="a5ad3-133">Per altre informazioni, vedere [Usare la modalità PATH con FOR XML](use-path-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a5ad3-133">For more information, see [Use PATH Mode with FOR XML](use-path-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="a5ad3-134">XMLDATA</span><span class="sxs-lookup"><span data-stu-id="a5ad3-134">XMLDATA</span></span>  
 <span data-ttu-id="a5ad3-135">Specifica che deve essere restituito uno schema XDR (XML-Data Reduced) inline.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-135">Specifies that an inline XML-Data Reduced (XDR) schema should be returned.</span></span> <span data-ttu-id="a5ad3-136">Lo schema viene aggiunto all'inizio del documento come schema inline.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-136">The schema is prepended to the document as an inline schema.</span></span> <span data-ttu-id="a5ad3-137">Per un esempio funzionante, vedere [Usare la modalità RAW con FOR XML](use-raw-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a5ad3-137">For a working sample, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="a5ad3-138">XMLSCHEMA</span><span class="sxs-lookup"><span data-stu-id="a5ad3-138">XMLSCHEMA</span></span>  
 <span data-ttu-id="a5ad3-139">Restituisce XML Schema W3C (XSD) inline.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-139">Returns an inline W3C XML Schema (XSD).</span></span> <span data-ttu-id="a5ad3-140">È possibile specificare facoltativamente un URI dello spazio dei nomi di destinazione quando si specifica questa direttiva.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-140">You can optionally specify a target namespace URI when specifying this directive.</span></span> <span data-ttu-id="a5ad3-141">In tal modo, viene restituito lo spazio dei nomi specificato nello schema.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-141">This returns the specified namespace in the schema.</span></span> <span data-ttu-id="a5ad3-142">Per altre informazioni, vedere [Generare uno schema XSD inline](generate-an-inline-xsd-schema.md).</span><span class="sxs-lookup"><span data-stu-id="a5ad3-142">For more information, see [Generate an Inline XSD Schema](generate-an-inline-xsd-schema.md).</span></span> <span data-ttu-id="a5ad3-143">Per un esempio funzionante, vedere [Usare la modalità RAW con FOR XML](use-raw-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a5ad3-143">For a working sample, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="a5ad3-144">ELEMENTS</span><span class="sxs-lookup"><span data-stu-id="a5ad3-144">ELEMENTS</span></span>  
 <span data-ttu-id="a5ad3-145">Se si specifica l'opzione ELEMENTS, le colonne vengono restituite come sottoelementi.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-145">If the ELEMENTS option is specified, the columns are returned as subelements.</span></span> <span data-ttu-id="a5ad3-146">In caso contrario, vengono mappate ad attributi XML.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-146">Otherwise, they are mapped to XML attributes.</span></span> <span data-ttu-id="a5ad3-147">Questa opzione è supportata solo con le modalità RAW, AUTO e PATH.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-147">This option is supported in RAW, AUTO, and PATH modes only.</span></span> <span data-ttu-id="a5ad3-148">È possibile specificare facoltativamente XSINIL o ABSENT quando si utilizza questa direttiva.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-148">You can optionally specify XSINIL or ABSENT when you use this directive.</span></span> <span data-ttu-id="a5ad3-149">XSINIL specifica la creazione di un elemento con attributo **xsi:nil** impostato su True per i valori di colonna NULL.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-149">XSINIL specifies that an element that has an **xsi:nil** attribute set to True be created for NULL column values.</span></span> <span data-ttu-id="a5ad3-150">Per impostazione predefinita o quando si specifica ABSENT insieme a ELEMENTS, non viene creato alcun elemento per i valori NULL.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-150">By default or when ABSENT is specified together with ELEMENTS, no elements are created for NULL values.</span></span> <span data-ttu-id="a5ad3-151">Per un esempio funzionante, vedere [Usare la modalità RAW con FOR XML](use-raw-mode-with-for-xml.md) e [Usare la modalità AUTO con FOR XML](use-auto-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a5ad3-151">For a working sample, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md) and [Use AUTO Mode with FOR XML](use-auto-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="a5ad3-152">BINARY BASE64</span><span class="sxs-lookup"><span data-stu-id="a5ad3-152">BINARY BASE64</span></span>  
 <span data-ttu-id="a5ad3-153">Se si specifica l'opzione BINARY Base64, gli eventuali dati binari restituiti dalla query vengono rappresentanti nel formato con codifica Base64.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-153">If the BINARY Base64 option is specified, any binary data returned by the query is represented in base64-encoded format.</span></span> <span data-ttu-id="a5ad3-154">Per recuperare dati binari in modalità RAW ed EXPLICIT, è necessario specificare questa opzione.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-154">To retrieve binary data by using RAW and EXPLICIT mode, this option must be specified.</span></span> <span data-ttu-id="a5ad3-155">In modalità AUTO, i dati binari vengono restituiti come riferimento per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-155">In AUTO mode, binary data is returned as a reference by default.</span></span> <span data-ttu-id="a5ad3-156">Per un esempio funzionante, vedere [Usare la modalità RAW con FOR XML](use-raw-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a5ad3-156">For a working sample, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="a5ad3-157">TYPE</span><span class="sxs-lookup"><span data-stu-id="a5ad3-157">TYPE</span></span>  
 <span data-ttu-id="a5ad3-158">Specifica che la query restituisce i risultati come dati di tipo **xml** .</span><span class="sxs-lookup"><span data-stu-id="a5ad3-158">Specifies that the query returns the results as the **xml** type.</span></span> <span data-ttu-id="a5ad3-159">Per altre informazioni, vedere [Direttiva TYPE nelle query FOR XML](type-directive-in-for-xml-queries.md).</span><span class="sxs-lookup"><span data-stu-id="a5ad3-159">For more information, see [TYPE Directive in FOR XML Queries](type-directive-in-for-xml-queries.md).</span></span>  
  
 <span data-ttu-id="a5ad3-160">ROOT [('*RootName*')]</span><span class="sxs-lookup"><span data-stu-id="a5ad3-160">ROOT [('*RootName*')]</span></span>  
 <span data-ttu-id="a5ad3-161">Specifica l'aggiunta di un singolo elemento principale alla struttura XML risultante.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-161">Specifies that a single, top-level element be added to the resulting XML.</span></span> <span data-ttu-id="a5ad3-162">È possibile specificare facoltativamente il nome dell'elemento radice da generare.</span><span class="sxs-lookup"><span data-stu-id="a5ad3-162">You can optionally specify the root element name to generate.</span></span> <span data-ttu-id="a5ad3-163">Il valore predefinito è "root".</span><span class="sxs-lookup"><span data-stu-id="a5ad3-163">The default value is "root".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5ad3-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5ad3-164">See Also</span></span>  
 <span data-ttu-id="a5ad3-165">[Utilizzo della modalità RAW con FOR XML](use-raw-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="a5ad3-165">[Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="a5ad3-166">[Utilizzo della modalità AUTO con FOR XML](use-auto-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="a5ad3-166">[Use AUTO Mode with FOR XML](use-auto-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="a5ad3-167">[Utilizzo della modalità EXPLICIT con FOR XML](use-explicit-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="a5ad3-167">[Use EXPLICIT Mode with FOR XML](use-explicit-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="a5ad3-168">[Utilizzare la modalità PATH con FOR XML](use-path-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="a5ad3-168">[Use PATH Mode with FOR XML](use-path-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="a5ad3-169">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a5ad3-169">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="a5ad3-170">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a5ad3-170">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
