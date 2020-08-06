---
title: Specificare metaproprietà in OPENXML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- overflow in XML document [SQL Server]
- metaproperties [XML in SQL Server]
- unconsumed data
- extracting information of XML nodes [SQL Server]
- OPENXML statement, metaproperties
ms.assetid: 29bfd1c6-3f9a-43c4-924a-53d438e442f4
author: rothja
ms.author: jroth
ms.openlocfilehash: c52d1162aa495deff8a0fde314fdcde0735d9c2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719751"
---
# <a name="specify-metaproperties-in-openxml"></a><span data-ttu-id="375a7-102">Impostazione di metaproprietà in OPENXML</span><span class="sxs-lookup"><span data-stu-id="375a7-102">Specify Metaproperties in OPENXML</span></span>
  <span data-ttu-id="375a7-103">Gli attributi delle metaproprietà in un documento XML sono attributi che descrivono le proprietà di un elemento XML (elemento, attributo o qualsiasi altro nodo DOM).</span><span class="sxs-lookup"><span data-stu-id="375a7-103">Metaproperty attributes in an XML document are attributes that describe the properties of an XML item, such as element, attribute, or any other DOM node.</span></span> <span data-ttu-id="375a7-104">Tali attributi non sono fisicamente presenti nel testo del documento XML,</span><span class="sxs-lookup"><span data-stu-id="375a7-104">These attributes do not physically exist in the XML document text.</span></span> <span data-ttu-id="375a7-105">tuttavia OPENXML fornisce tali metaproprietà per tutti gli elementi XML.</span><span class="sxs-lookup"><span data-stu-id="375a7-105">However, OPENXML provides these metaproperties for all the XML items.</span></span> <span data-ttu-id="375a7-106">Queste metaproprietà consentono di estrarre informazioni, ad esempio la posizione locale o le informazioni sullo spazio dei nomi, dei nodi XML,</span><span class="sxs-lookup"><span data-stu-id="375a7-106">These metaproperties allow you to extract information, such as local positioning and namespace information, of XML nodes.</span></span> <span data-ttu-id="375a7-107">ovvero informazioni più dettagliate rispetto a quelle disponibili nella rappresentazione testuale.</span><span class="sxs-lookup"><span data-stu-id="375a7-107">This information provides you with more details than are apparent in the textual representation.</span></span>  
  
 <span data-ttu-id="375a7-108">Per eseguire il mapping le metaproprietà alle colonne del set di righe, è possibile specificare il parametro *ColPattern* in un'istruzione OPENXML.</span><span class="sxs-lookup"><span data-stu-id="375a7-108">You can map these metaproperties to the rowset columns in an OPENXML statement by using the *ColPattern* parameter.</span></span> <span data-ttu-id="375a7-109">Le colonne conterranno i valori delle metaproprietà alle quali è stato eseguito il mapping.</span><span class="sxs-lookup"><span data-stu-id="375a7-109">The columns will contain the values of the metaproperties to which they are mapped.</span></span> <span data-ttu-id="375a7-110">Per informazioni sulla sintassi di OPENXML, vedere [OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="375a7-110">For more information about the syntax of OPENXML, see [OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql).</span></span>  
  
 <span data-ttu-id="375a7-111">Per accedere agli attributi delle metaproprietà, è possibile utilizzare uno spazio dei nomi specifico di SQL Server,</span><span class="sxs-lookup"><span data-stu-id="375a7-111">To access the metaproperty attributes, a namespace that is specific to SQL Server is provided.</span></span> <span data-ttu-id="375a7-112">Questo spazio dei nomi, **urn:schemas-microsoft-com:xml-metaprop** consente all'utente di accedere agli attributi delle metaproprietà.</span><span class="sxs-lookup"><span data-stu-id="375a7-112">This namespace, **urn:schemas-microsoft-com:xml-metaprop** allows the user to access the metaproperty attributes.</span></span> <span data-ttu-id="375a7-113">Se il risultato di una query OPENXML viene restituito nel formato tabella edge, in tale tabella sarà inclusa una colonna per ogni attributo della metaproprietà, a eccezione della metaproprietà **xmltext** .</span><span class="sxs-lookup"><span data-stu-id="375a7-113">If the result of an OPENXML query is returned in an edge table format, the edge table contains one column for each metaproperty attribute, except the **xmltext** metaproperty.</span></span>  
  
 <span data-ttu-id="375a7-114">Alcuni attributi delle metaproprietà vengono utilizzati per attività di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="375a7-114">Some of the metaproperty attributes are used for processing purposes.</span></span> <span data-ttu-id="375a7-115">Ad esempio, l'attributo della metaproprietà **xmltext** consente di gestire l'overflow.</span><span class="sxs-lookup"><span data-stu-id="375a7-115">For example, the **xmltext** metaproperty attribute is used for overflow handling.</span></span> <span data-ttu-id="375a7-116">La gestione dell'overflow implica la gestione dei dati non utilizzati e non elaborati del documento.</span><span class="sxs-lookup"><span data-stu-id="375a7-116">Overflow handling refers to the unconsumed, unprocessed data in the document.</span></span> <span data-ttu-id="375a7-117">Una delle colonne del set di righe generato da OPENXML può essere identificata come la colonna di overflow.</span><span class="sxs-lookup"><span data-stu-id="375a7-117">One of the columns in the rowset that is generated by OPENXML can be identified as the overflow column.</span></span> <span data-ttu-id="375a7-118">A tale scopo, è possibile eseguirne il mapping alla metaproprietà **xmltext** usando il parametro *ColPattern* .</span><span class="sxs-lookup"><span data-stu-id="375a7-118">You do this by mapping it to the **xmltext** metaproperty by using the *ColPattern* parameter.</span></span> <span data-ttu-id="375a7-119">Nella colonna verranno inseriti i dati di overflow</span><span class="sxs-lookup"><span data-stu-id="375a7-119">The column then receives the overflow data.</span></span> <span data-ttu-id="375a7-120">e il parametro *flags* determinerà se la colonna includerà solo i dati non utilizzati oppure tutti i dati.</span><span class="sxs-lookup"><span data-stu-id="375a7-120">The *flags* parameter determines whether the column contains everything or only the unconsumed data.</span></span>  
  
 <span data-ttu-id="375a7-121">Nella tabella seguente sono elencati gli attributi delle metaproprietà per ogni elemento XML analizzato.</span><span class="sxs-lookup"><span data-stu-id="375a7-121">The following table lists the metaproperty attributes that each parsed XML element possesses.</span></span> <span data-ttu-id="375a7-122">Per accedere a tali attributi, è necessario usare lo spazio dei nomi **urn:schemas-microsoft-com:xml-metaprop**.</span><span class="sxs-lookup"><span data-stu-id="375a7-122">These metaproperty attributes can be accessed by using the namespace **urn:schemas-microsoft-com:xml-metaprop**.</span></span> <span data-ttu-id="375a7-123">Qualsiasi valore impostato dall'utente direttamente nel documento XML tramite queste metaproprietà verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="375a7-123">Any value that the user sets directly in the XML document by using these metaproperties is ignored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="375a7-124">Non è possibile fare riferimento a queste metaproprietà nelle strutture di navigazione XPath.</span><span class="sxs-lookup"><span data-stu-id="375a7-124">You cannot reference these metaproperties in any XPath navigation.</span></span>  
  
|<span data-ttu-id="375a7-125">Attributo della metaproprietà</span><span class="sxs-lookup"><span data-stu-id="375a7-125">Metaproperty attribute</span></span>|<span data-ttu-id="375a7-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="375a7-126">Description</span></span>|  
|----------------------------|-----------------|  
|<span data-ttu-id="375a7-127">**\@mp:id**</span><span class="sxs-lookup"><span data-stu-id="375a7-127">**\@mp:id**</span></span>|<span data-ttu-id="375a7-128">Restituisce un identificatore del nodo DOM generato dal sistema e valido a livello globale per il documento.</span><span class="sxs-lookup"><span data-stu-id="375a7-128">Provides a system-generated, document-wide identifier of the DOM node.</span></span> <span data-ttu-id="375a7-129">Se il documento non viene nuovamente analizzato, questo ID fa riferimento allo stesso nodo XML.</span><span class="sxs-lookup"><span data-stu-id="375a7-129">As long as the document is not reparsed, this ID refers to the same XML node.</span></span><br /><br /> <span data-ttu-id="375a7-130">Un ID XML **0** indica che l'elemento è un elemento radice.</span><span class="sxs-lookup"><span data-stu-id="375a7-130">An XML ID of **0** indicates that the element is a root element.</span></span> <span data-ttu-id="375a7-131">Il relativo ID XML padre è NULL.</span><span class="sxs-lookup"><span data-stu-id="375a7-131">Its parent XML ID is NULL.</span></span>|  
|<span data-ttu-id="375a7-132">**\@mp:localname**</span><span class="sxs-lookup"><span data-stu-id="375a7-132">**\@mp:localname**</span></span>|<span data-ttu-id="375a7-133">Archivia la parte locale del nome del nodo.</span><span class="sxs-lookup"><span data-stu-id="375a7-133">Stores the local part of the name of the node.</span></span> <span data-ttu-id="375a7-134">Viene utilizzato insieme a un prefisso e a un URI dello spazio dei nomi per definire i nodi di elementi o attributi.</span><span class="sxs-lookup"><span data-stu-id="375a7-134">It is used with a prefix and a namespace URI to name element or attribute nodes.</span></span>|  
|<span data-ttu-id="375a7-135">**\@mp:namespaceuri**</span><span class="sxs-lookup"><span data-stu-id="375a7-135">**\@mp:namespaceuri**</span></span>|<span data-ttu-id="375a7-136">Restituisce l'URI dello spazio dei nomi dell'elemento corrente.</span><span class="sxs-lookup"><span data-stu-id="375a7-136">Provides the namespace URI of the current element.</span></span> <span data-ttu-id="375a7-137">Se il valore di questo attributo è NULL, non sono presenti spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="375a7-137">If the value of this attribute is NULL, no namespace is present</span></span>|  
|<span data-ttu-id="375a7-138">**\@mp:prefix**</span><span class="sxs-lookup"><span data-stu-id="375a7-138">**\@mp:prefix**</span></span>|<span data-ttu-id="375a7-139">Archivia il prefisso dello spazio dei nomi del nome dell'elemento corrente.</span><span class="sxs-lookup"><span data-stu-id="375a7-139">Stores the namespace prefix of the current element name.</span></span><br /><br /> <span data-ttu-id="375a7-140">Se non è presente alcun prefisso (NULL) e viene specificato un URI, indica che lo spazio dei nomi specificato è lo spazio dei nomi predefinito.</span><span class="sxs-lookup"><span data-stu-id="375a7-140">If no prefix is present (NULL) and a URI is given, it indicates that the specified namespace is the default namespace.</span></span> <span data-ttu-id="375a7-141">Se non viene specificato alcun URI, non verranno associati spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="375a7-141">If no URI is given, no namespace is attached.</span></span>|  
|<span data-ttu-id="375a7-142">**\@mp:prev**</span><span class="sxs-lookup"><span data-stu-id="375a7-142">**\@mp:prev**</span></span>|<span data-ttu-id="375a7-143">Archivia l'elemento di pari livello precedente in un nodo</span><span class="sxs-lookup"><span data-stu-id="375a7-143">Stores the previous sibling relative to a node.</span></span> <span data-ttu-id="375a7-144">e fornisce informazioni sull'ordinamento degli elementi nel documento.</span><span class="sxs-lookup"><span data-stu-id="375a7-144">This provides information about the ordering of elements in the document.</span></span><br /><br /> <span data-ttu-id="375a7-145">**\@mp:prev** contiene l'ID XML dell'elemento di pari livello precedente con lo stesso elemento padre.</span><span class="sxs-lookup"><span data-stu-id="375a7-145">**\@mp:prev** contains the XML ID of the previous sibling that has the same parent element.</span></span> <span data-ttu-id="375a7-146">Se un elemento si trova all'inizio dell'elenco di elementi di pari livello, **\@mp:prev** è NULL.</span><span class="sxs-lookup"><span data-stu-id="375a7-146">If an element is at the front of the sibling list, **\@mp:prev** is NULL.</span></span>|  
|<span data-ttu-id="375a7-147">**\@mp:xmltext**</span><span class="sxs-lookup"><span data-stu-id="375a7-147">**\@mp:xmltext**</span></span>|<span data-ttu-id="375a7-148">Utilizzato per attività di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="375a7-148">Used for processing purposes.</span></span> <span data-ttu-id="375a7-149">Rappresenta la serializzazione testuale dell'elemento e dei relativi attributi nonché dei sottoelementi, come vengono utilizzati nella gestione dell'overflow di OPENXML.</span><span class="sxs-lookup"><span data-stu-id="375a7-149">It is the textual serialization of the element and its attributes, and also the subelements, as used in the overflow handling of OPENXML.</span></span>|  
  
 <span data-ttu-id="375a7-150">Nella tabella seguente vengono illustrate le proprietà padre aggiuntive che consentono di recuperare le informazioni relative alla gerarchia.</span><span class="sxs-lookup"><span data-stu-id="375a7-150">This table shows the additional parent properties that are provided and which allow you to retrieve information about the hierarchy.</span></span>  
  
|<span data-ttu-id="375a7-151">Attributo della metaproprietà padre</span><span class="sxs-lookup"><span data-stu-id="375a7-151">Parent metaproperty attribute</span></span>|<span data-ttu-id="375a7-152">Descrizione</span><span class="sxs-lookup"><span data-stu-id="375a7-152">Description</span></span>|  
|-----------------------------------|-----------------|  
|<span data-ttu-id="375a7-153">**\@mp:parentid**</span><span class="sxs-lookup"><span data-stu-id="375a7-153">**\@mp:parentid**</span></span>|<span data-ttu-id="375a7-154">Corrisponde a **../\@mp:id**</span><span class="sxs-lookup"><span data-stu-id="375a7-154">Corresponds to **../\@mp:id**</span></span>|  
|<span data-ttu-id="375a7-155">**\@mp:parentlocalname**</span><span class="sxs-lookup"><span data-stu-id="375a7-155">**\@mp:parentlocalname**</span></span>|<span data-ttu-id="375a7-156">Corrisponde a **../\@mp:localname**</span><span class="sxs-lookup"><span data-stu-id="375a7-156">Corresponds to **../\@mp:localname**</span></span>|  
|<span data-ttu-id="375a7-157">**\@mp:parentnamespacerui**</span><span class="sxs-lookup"><span data-stu-id="375a7-157">**\@mp:parentnamespacerui**</span></span>|<span data-ttu-id="375a7-158">Corrisponde a **../\@mp:namespaceuri**</span><span class="sxs-lookup"><span data-stu-id="375a7-158">Corresponds to **../\@mp:namespaceuri**</span></span>|  
|<span data-ttu-id="375a7-159">**\@mp:parentprefix**</span><span class="sxs-lookup"><span data-stu-id="375a7-159">**\@mp:parentprefix**</span></span>|<span data-ttu-id="375a7-160">Corrisponde a **../\@mp:prefix**</span><span class="sxs-lookup"><span data-stu-id="375a7-160">Corresponds to **../\@mp:prefix**</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="375a7-161">Esempi</span><span class="sxs-lookup"><span data-stu-id="375a7-161">Examples</span></span>  
 <span data-ttu-id="375a7-162">Negli esempi seguenti viene illustrato l'utilizzo di OPENXML per visualizzare i set di righe in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="375a7-162">The following examples illustrate how OPENXML is used to create different rowset views.</span></span>  
  
### <a name="a-mapping-the-openxml-rowset-columns-to-the-metaproperties"></a><span data-ttu-id="375a7-163">R.</span><span class="sxs-lookup"><span data-stu-id="375a7-163">A.</span></span> <span data-ttu-id="375a7-164">Mapping tra le colonne del set di righe OPENXML e le metaproprietà</span><span class="sxs-lookup"><span data-stu-id="375a7-164">Mapping the OPENXML rowset columns to the metaproperties</span></span>  
 <span data-ttu-id="375a7-165">In questo esempio, l'istruzione OPENXML viene utilizzata per visualizzare il documento XML di esempio come un set di righe.</span><span class="sxs-lookup"><span data-stu-id="375a7-165">This example uses OPENXML to create a rowset view of the sample XML document.</span></span> <span data-ttu-id="375a7-166">In particolare, viene illustrato come eseguire il mapping di più attributi delle metaproprietà alle colonne del set di righe in un'istruzione OPENXML usando il parametro *ColPattern* .</span><span class="sxs-lookup"><span data-stu-id="375a7-166">Specifically, it shows how the various metaproperty attributes can be mapped to rowset columns in an OPENXML statement by using the *ColPattern* parameter.</span></span>  
  
 <span data-ttu-id="375a7-167">Nell'istruzione OPENXML si noti quanto segue:</span><span class="sxs-lookup"><span data-stu-id="375a7-167">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="375a7-168">La colonna **id** viene mappata all'attributo della metaproprietà **\@mp:id** a indicare che la colonna contiene l'ID XML univoco generato dal sistema dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="375a7-168">The **id** column is mapped to the **\@mp:id** metaproperty attribute and indicates that the column contains the system-generated unique XML ID of the element.</span></span>  
  
-   <span data-ttu-id="375a7-169">La colonna **parent** viene mappata a **\@mp:parentid** a indicare che la colonna contiene l'ID XML del padre dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="375a7-169">The **parent** column is mapped to **\@mp:parentid** and indicates that the column contains the XML ID of the parent of the element.</span></span>  
  
-   <span data-ttu-id="375a7-170">La colonna **parentLocalName** viene mappata a **\@mp:parentlocalname** a indicare che la colonna contiene il nome locale del padre.</span><span class="sxs-lookup"><span data-stu-id="375a7-170">The **parentLocalName** column is mapped to **\@mp:parentlocalname** and indicates that the column contains the local name of the parent.</span></span>  
  
 <span data-ttu-id="375a7-171">L'istruzione SELECT restituisce quindi il set di righe fornito da OPENXML:</span><span class="sxs-lookup"><span data-stu-id="375a7-171">The SELECT statement then returns the rowset that is provided by OPENXML:</span></span>  
  
```  
DECLARE @idoc int  
DECLARE @doc nvarchar(1000)  
-- Sample XML document  
SET @doc = N'<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very satisfied</Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue white red">  
          <Urgency>Important</Urgency>  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @idoc OUTPUT, @doc  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@idoc, '/root/Customer/Order', 9)  
      WITH (id int '@mp:id',   
            oid char(5),   
            date datetime,   
            amount real,   
            parentIDNo int '@mp:parentid',   
            parentLocalName varchar(40) '@mp:parentlocalname')  
EXEC sp_xml_removedocument @idoc  
```  
  
 <span data-ttu-id="375a7-172">Risultato:</span><span class="sxs-lookup"><span data-stu-id="375a7-172">This is the result:</span></span>  
  
```  
id   oid         date                amount    parentIDNo  parentLocalName    
--- ------- ---------------------- ---------- ------------ ---------------  
6    O1    1996-01-20 00:00:00.000     3.5         2        Customer  
10   O2    1997-04-30 00:00:00.000     13.4        2        Customer  
19   O3    1999-07-14 00:00:00.000     100.0       15       Customer  
25   O4    1996-01-20 00:00:00.000     10000.0     15       Customer  
```  
  
### <a name="b-retrieving-the-whole-xml-document"></a><span data-ttu-id="375a7-173">B.</span><span class="sxs-lookup"><span data-stu-id="375a7-173">B.</span></span> <span data-ttu-id="375a7-174">Recupero dell'intero documento XML</span><span class="sxs-lookup"><span data-stu-id="375a7-174">Retrieving the whole XML document</span></span>  
 <span data-ttu-id="375a7-175">In questo esempio, l'istruzione OPENXML visualizza il documento XML di esempio come un set di righe a una colonna.</span><span class="sxs-lookup"><span data-stu-id="375a7-175">In this example, OPENXML is used to create a one-column rowset view of the sample XML document.</span></span> <span data-ttu-id="375a7-176">Viene eseguito il mapping della colonna, **Col1**, alla metaproprietà **xmltext** e diventa una colonna di overflow,</span><span class="sxs-lookup"><span data-stu-id="375a7-176">This column, **Col1**, is mapped to the **xmltext** metaproperty and becomes an overflow column.</span></span> <span data-ttu-id="375a7-177">pertanto vi verranno inseriti i dati non utilizzati</span><span class="sxs-lookup"><span data-stu-id="375a7-177">As a result, the column receives the unconsumed data.</span></span> <span data-ttu-id="375a7-178">che in questo caso sono rappresentati dall'intero documento.</span><span class="sxs-lookup"><span data-stu-id="375a7-178">In this case, it is the whole document.</span></span>  
  
 <span data-ttu-id="375a7-179">L'istruzione SELECT restituisce quindi l'intero set di righe.</span><span class="sxs-lookup"><span data-stu-id="375a7-179">The SELECT statement then returns the complete rowset.</span></span>  
  
```  
DECLARE @idoc int  
DECLARE @doc nvarchar(1000)  
SET @doc = N'<?xml version="1.0"?>  
<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very   
             satisfied</Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue   
             white red">  
     <MyTag>Testing to see if all the subelements are returned</MyTag>  
          <Urgency>Important</Urgency>  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @idoc OUTPUT, @doc  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@idoc, '/')  
   WITH (Col1 ntext '@mp:xmltext')  
```  
  
 <span data-ttu-id="375a7-180">Per recuperare l'intero documento senza la dichiarazione XML, è possibile specificare la query nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="375a7-180">To retrieve the whole document without the XML declaration, the query can be specified as shown in the following:</span></span>  
  
```  
SELECT *  
FROM OPENXML (@idoc, '/root')  
   WITH (Col1 ntext '@mp:xmltext')  
EXEC sp_xml_removedocument @idoc  
```  
  
 <span data-ttu-id="375a7-181">La query restituisce l'elemento radice insieme al relativo nome, nonché i dati contenuti in tale elemento.</span><span class="sxs-lookup"><span data-stu-id="375a7-181">The query returns the root element that has the name root and the data that is contained by the root element</span></span>  
  
### <a name="c-specifying-the-xmltext-metaproperty-to-retrieve-the-unconsumed-data-in-a-column"></a><span data-ttu-id="375a7-182">C.</span><span class="sxs-lookup"><span data-stu-id="375a7-182">C.</span></span> <span data-ttu-id="375a7-183">Impostazione della metaproprietà xmltext per il recupero dei dati non utilizzati in una colonna</span><span class="sxs-lookup"><span data-stu-id="375a7-183">Specifying the xmltext metaproperty to retrieve the unconsumed data in a column</span></span>  
 <span data-ttu-id="375a7-184">In questo esempio, l'istruzione OPENXML viene utilizzata per visualizzare il documento XML di esempio come un set di righe.</span><span class="sxs-lookup"><span data-stu-id="375a7-184">This example uses OPENXML to create a rowset view of the sample XML document.</span></span> <span data-ttu-id="375a7-185">L'esempio descrive inoltre come recuperare i dati XML non utilizzati tramite il mapping tra l'attributo della metaproprietà **xmltext** e una colonna del set di righe nell'istruzione OPENXML.</span><span class="sxs-lookup"><span data-stu-id="375a7-185">The example shows how to retrieve unconsumed XML data by mapping the **xmltext** metaproperty attribute to a rowset column in OPENXML.</span></span>  
  
 <span data-ttu-id="375a7-186">La colonna **comment** viene identificata come colonna di overflow tramite il mapping alla metaproprietà **\@mp:xmltext**.</span><span class="sxs-lookup"><span data-stu-id="375a7-186">The **comment** column is identified as the overflow column by mapping it to the **\@mp:xmltext** metaproperty.</span></span> <span data-ttu-id="375a7-187">Il parametro *flags* viene impostato su **9** (XML_ATTRIBUTE e XML_NOCOPY),</span><span class="sxs-lookup"><span data-stu-id="375a7-187">The *flags* parameter is set to **9** (XML_ATTRIBUTE and XML_NOCOPY).</span></span> <span data-ttu-id="375a7-188">per indicare che il mapping è **incentrato sugli attributi** e che nella colonna di overflow verranno copiati solo i dati non utilizzati.</span><span class="sxs-lookup"><span data-stu-id="375a7-188">This indicates **attribute-centric** mapping and indicates that only the unconsumed data should be copied to the overflow column.</span></span>  
  
 <span data-ttu-id="375a7-189">L'istruzione SELECT restituisce quindi il set di righe definito dall'istruzione OPENXML.</span><span class="sxs-lookup"><span data-stu-id="375a7-189">The SELECT statement then returns the rowset provided by OPENXML.</span></span>  
  
 <span data-ttu-id="375a7-190">In questo esempio, la metaproprietà **\@mp:parentlocalname** viene impostata per la colonna **ParentLocalName** nel set di righe generato dall'istruzione OPENXML.</span><span class="sxs-lookup"><span data-stu-id="375a7-190">In this example, the **\@mp:parentlocalname** metaproperty is set for a column, **ParentLocalName**, in the rowset generated by OPENXML.</span></span> <span data-ttu-id="375a7-191">Questa colonna includerà pertanto il nome locale dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="375a7-191">As a result, this column contains the local name of the parent element.</span></span>  
  
 <span data-ttu-id="375a7-192">Nel set di righe vengono definite altre due colonne, **parent** e **comment**.</span><span class="sxs-lookup"><span data-stu-id="375a7-192">Two additional columns are specified in the rowset, **parent** and **comment**.</span></span> <span data-ttu-id="375a7-193">La colonna **parent** viene mappata a **\@mp:parentid** a indicare che la colonna contiene l'ID XML dell'elemento padre dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="375a7-193">The **parent** column is mapped to **\@mp:parentid** and indicates that the column contains the XML ID of the parent element of the element.</span></span> <span data-ttu-id="375a7-194">La colonna comment viene definita come colonna di overflow tramite il mapping alla metaproprietà **\@mp:xmltext**.</span><span class="sxs-lookup"><span data-stu-id="375a7-194">The comment column is identified as the overflow column by mapping it to the **\@mp:xmltext** metaproperty.</span></span>  
  
```  
DECLARE @idoc int  
DECLARE @doc nvarchar(1000)  
-- sample XML document  
SET @doc = N'<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very satisfied</Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue white red">  
          <Urgency>Important</Urgency>  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>  
'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @idoc OUTPUT, @doc  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@idoc, '/root/Customer/Order', 9)  
      WITH (oid char(5),   
            date datetime,  
            comment ntext '@mp:xmltext')  
EXEC sp_xml_removedocument @idoc  
```  
  
 <span data-ttu-id="375a7-195">Di seguito è riportato il risultato.</span><span class="sxs-lookup"><span data-stu-id="375a7-195">This is the result.</span></span> <span data-ttu-id="375a7-196">Poiché le colonne oid e date sono già utilizzate, non sono riportate nella colonna di overflow.</span><span class="sxs-lookup"><span data-stu-id="375a7-196">Because the oid columns and date columns are already consumed, they do not appear in the overflow column.</span></span>  
  
```  
oid   date                        comment                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            
----- --------------------------- ----------------------------------------  
O1    1996-01-20 00:00:00.000     <Order amount="3.5"/>  
O2    1997-04-30 00:00:00.000     <Order amount="13.4">Customer was very   
                                   satisfied</Order>  
O3    1999-07-14 00:00:00.000     <Order amount="100" note="Wrap it blue   
                                   white red"><Urgency>   
                                   Important</Urgency></Order>  
O4    1996-01-20 00:00:00.000     <Order amount="10000"/>  
```  
  
## <a name="see-also"></a><span data-ttu-id="375a7-197">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="375a7-197">See Also</span></span>  
 <span data-ttu-id="375a7-198">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="375a7-198">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span></span>  
 [<span data-ttu-id="375a7-199">OPENXML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="375a7-199">OPENXML &#40;SQL Server&#41;</span></span>](../xml/openxml-sql-server.md)  
  
  
