---
title: Formattazione XML sul lato client (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- FOR XML clause, formatting
- middle tier XML formatting [SQLXML]
- client-side XML formatting
- client-side-xml attribute
ms.assetid: 9630a21d-a93b-4d3b-8a25-c4b32399f993
author: rothja
ms.author: jroth
ms.openlocfilehash: bf4a680d79a25d24ebdf779b41fd3be5a5d6a605
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630415"
---
# <a name="client-side-xml-formatting-sqlxml-40"></a><span data-ttu-id="98b7b-102">Formattazione XML sul lato client (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="98b7b-102">Client-side XML Formatting (SQLXML 4.0)</span></span>
  <span data-ttu-id="98b7b-103">Questo argomento fornisce informazioni sulla formattazione XML sul lato client.</span><span class="sxs-lookup"><span data-stu-id="98b7b-103">This topic provides information about client-side XML formatting.</span></span> <span data-ttu-id="98b7b-104">Per formattazione sul lato client si intende la formattazione di dati XML nel livello intermedio.</span><span class="sxs-lookup"><span data-stu-id="98b7b-104">Client-side formatting refers to the formatting of XML on the middle tier.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98b7b-105">In questo argomento vengono fornite informazioni aggiuntive sull'utilizzo della clausola FOR XML sul lato client, con cui si suppone che l'utente disponga già di una certa familiarità.</span><span class="sxs-lookup"><span data-stu-id="98b7b-105">This topic provides additional information about using the FOR XML clause on the client side, and assumes you are already familiar with the FOR XML clause.</span></span> <span data-ttu-id="98b7b-106">Per ulteriori informazioni su FOR XML, vedere [costruzione di codice XML mediante for XML](../../xml/for-xml-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="98b7b-106">For more information about FOR XML, see [Constructing XML Using FOR XML](../../xml/for-xml-sql-server.md).</span></span>  
  
 <span data-ttu-id="98b7b-107">**Importante** Per utilizzare la funzionalità FOR XML sul lato client con il nuovo `xml` tipo di dati, i client devono utilizzare sempre il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provider di dati native client (SQLNCLI11) anziché il provider SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="98b7b-107">**Important** To use client-side FOR XML functionality with the new `xml` data type, clients should always use the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) data provider instead of the SQLOLEDB provider.</span></span> <span data-ttu-id="98b7b-108">SQLNCLI11 rappresenta la versione più recente del provider di SQL Server ed è in grado di riconoscere completamente i tipi di dati introdotti in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98b7b-108">SQLNCLI11 is the latest version of the SQL Server provider and fully understands data types introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="98b7b-109">Il comportamento per FOR XML sul lato client con il provider SQLOLEDB prevede la gestione dei tipi di dati `xml` come stringhe.</span><span class="sxs-lookup"><span data-stu-id="98b7b-109">The behavior for client side FOR XML with the SQLOLEDB provider will treat `xml` data types as strings.</span></span>  
  
## <a name="formatting-xml-documents-on-the-client-side"></a><span data-ttu-id="98b7b-110">Formattazione di documenti XML sul lato client</span><span class="sxs-lookup"><span data-stu-id="98b7b-110">Formatting XML Documents on the Client Side</span></span>  
 <span data-ttu-id="98b7b-111">Quando un'applicazione client esegue la query</span><span class="sxs-lookup"><span data-stu-id="98b7b-111">When a client application executes the following query:</span></span>  
  
```  
SELECT FirstName, LastName  
FROM   Person.Contact  
FOR XML RAW  
```  
  
 <span data-ttu-id="98b7b-112">Solo la parte seguente della query viene inviata al server:</span><span class="sxs-lookup"><span data-stu-id="98b7b-112">...only this part of the query is sent to the server:</span></span>  
  
```  
SELECT FirstName, LastName  
FROM   Person.Contact  
```  
  
 <span data-ttu-id="98b7b-113">Il server esegue la query e restituisce un set di righe, che contiene FirstName e LastName, al client.</span><span class="sxs-lookup"><span data-stu-id="98b7b-113">The server executes the query and returns a rowset (which contains FirstName and LastNamecolumns) to the client.</span></span> <span data-ttu-id="98b7b-114">Il livello intermedio applica quindi la trasformazione FOR XML al set di righe e restituisce la formattazione XML al client.</span><span class="sxs-lookup"><span data-stu-id="98b7b-114">The middle tier then applies the FOR XML transformation to the rowset and returns XML formatting to the client.</span></span>  
  
 <span data-ttu-id="98b7b-115">Analogamente, quando si esegue una query XPath il server restituisce il set di righe al client e la trasformazione FOR XML EXPLICIT viene applicata al set di righe nel client, generando la formattazione XML desiderata.</span><span class="sxs-lookup"><span data-stu-id="98b7b-115">Similarly, when you execute an XPath query, the server returns the rowset to the client and the FOR XML EXPLICIT transformation is applied to the rowset on the client, generating the desired XML formatting.</span></span>  
  
 <span data-ttu-id="98b7b-116">Nella tabella seguente vengono illustrate le modalità che è possibile specificare con la clausola FOR XML sul lato client.</span><span class="sxs-lookup"><span data-stu-id="98b7b-116">The following table shows the modes you can specify with client-side FOR XML.</span></span>  
  
|<span data-ttu-id="98b7b-117">Modalità FOR XML sul lato client</span><span class="sxs-lookup"><span data-stu-id="98b7b-117">Client-side FOR XML mode</span></span>|<span data-ttu-id="98b7b-118">Commento</span><span class="sxs-lookup"><span data-stu-id="98b7b-118">Comment</span></span>|  
|-------------------------------|-------------|  
|<span data-ttu-id="98b7b-119">RAW</span><span class="sxs-lookup"><span data-stu-id="98b7b-119">RAW</span></span>|<span data-ttu-id="98b7b-120">Produce risultati identici se specificata in FOR XML sul lato client o sul lato server.</span><span class="sxs-lookup"><span data-stu-id="98b7b-120">Produces identical results when specified in client-side or server-side FOR XML.</span></span>|  
|<span data-ttu-id="98b7b-121">NESTED</span><span class="sxs-lookup"><span data-stu-id="98b7b-121">NESTED</span></span>|<span data-ttu-id="98b7b-122">È simile alla modalità FOR XML AUTO sul lato server.</span><span class="sxs-lookup"><span data-stu-id="98b7b-122">Is similar to FOR XML AUTO mode on the server-side.</span></span>|  
|<span data-ttu-id="98b7b-123">EXPLICIT</span><span class="sxs-lookup"><span data-stu-id="98b7b-123">EXPLICIT</span></span>|<span data-ttu-id="98b7b-124">È simile alla modalità FOR XML EXPLICIT sul lato server.</span><span class="sxs-lookup"><span data-stu-id="98b7b-124">Is similar to server-side FOR XML EXPLICIT mode.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="98b7b-125">Se si specifica la modalità AUTO e si richiede la formattazione XML sul lato client, l'intera query viene inviata al server, ovvero la formattazione XML viene eseguita nel server.</span><span class="sxs-lookup"><span data-stu-id="98b7b-125">If you specify AUTO mode and request client-side XML formatting, the entire query is sent to the server; that is, XML formatting occurs on the server.</span></span> <span data-ttu-id="98b7b-126">Benché ciò avvenga per motivi di praticità, si noti che la modalità NESTED restituisce nomi di tabella di base nel documento XML generato.</span><span class="sxs-lookup"><span data-stu-id="98b7b-126">This is done for convenience, but note that the NESTED mode returns base table names as element names in the XML document that is generated.</span></span> <span data-ttu-id="98b7b-127">È possibile che alcune delle applicazioni scritte richiedano nomi di tabella di base.</span><span class="sxs-lookup"><span data-stu-id="98b7b-127">Some of the applications you write might require base table names.</span></span> <span data-ttu-id="98b7b-128">È possibile, ad esempio, eseguire una stored procedure e caricare i dati risultanti in un set di dati (in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework) e quindi generare in seguito un Diffgram per aggiornare i dati nelle tabelle.</span><span class="sxs-lookup"><span data-stu-id="98b7b-128">For example, you might execute a stored procedure and load the resulting data in a Dataset (in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework), and then later generate a DiffGram to update data in the tables.</span></span> <span data-ttu-id="98b7b-129">In tal caso, sarà necessario disporre delle informazioni sulla tabella di base e utilizzare la modalità NESTED.</span><span class="sxs-lookup"><span data-stu-id="98b7b-129">In such a case, you would need the base table information and you would have to use the NESTED mode.</span></span>  
  
## <a name="benefits-of-client-side-xml-formatting"></a><span data-ttu-id="98b7b-130">Vantaggi della formattazione XML sul lato client</span><span class="sxs-lookup"><span data-stu-id="98b7b-130">Benefits of Client-side XML formatting</span></span>  
 <span data-ttu-id="98b7b-131">Gli elementi seguenti costituiscono alcuni dei vantaggi della formattazione XML nel client.</span><span class="sxs-lookup"><span data-stu-id="98b7b-131">The following are some benefits of formatting XML on the client.</span></span>  
  
### <a name="if-you-have-stored-procedures-on-the-server-that-return-a-single-rowset-you-can-request-client-side-for-xml-transformation-to-generate-an-xml"></a><span data-ttu-id="98b7b-132">Se nel server sono disponibili stored procedure che restituiscono un singolo set di righe, è possibile richiedere la trasformazione FOR XML sul lato client per generare un documento XML.</span><span class="sxs-lookup"><span data-stu-id="98b7b-132">If you have stored procedures on the server that return a single rowset, you can request client-side FOR XML transformation to generate an XML.</span></span>  
 <span data-ttu-id="98b7b-133">Si consideri, ad esempio, la stored procedure seguente.</span><span class="sxs-lookup"><span data-stu-id="98b7b-133">For example, consider the following stored procedure.</span></span> <span data-ttu-id="98b7b-134">La procedura restituisce i nomi e i cognomi dei dipendenti inclusi nella tabella Person.Contact del database AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="98b7b-134">This procedure returns the first and last names of employees from the Person.Contact table in the AdventureWorks database:</span></span>  
  
```  
IF EXISTS (SELECT name FROM sysobjects  
   WHERE name = 'GetContacts' AND type = 'P')  
   DROP PROCEDURE GetContacts  
GO  
CREATE PROCEDURE GetContacts  
AS  
    SELECT   FirstName, LastName  
    FROM     Person.Contact  
```  
  
 <span data-ttu-id="98b7b-135">Il modello XML di esempio seguente esegue la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="98b7b-135">The following sample XML template executes the stored procedure.</span></span> <span data-ttu-id="98b7b-136">La clausola FOR XML viene specificata dopo il nome della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="98b7b-136">The FOR XML clause is specified after the stored procedure name.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="1">  
    EXEC GetContacts FOR XML NESTED  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="98b7b-137">Poiché l'attributo **client-side-xml** è impostato su 1 (true) nel modello, il stored procedure viene eseguito sul server e il set di righe a due colonne restituito dal server viene trasformato in XML nel livello intermedio e restituito al client.</span><span class="sxs-lookup"><span data-stu-id="98b7b-137">Because the **client-side-xml** attribute is set to 1 (true) in the template, the stored procedure is executed on the server and the two-column rowset that is returned by the server is transformed into XML on the middle tier and returned to the client.</span></span> <span data-ttu-id="98b7b-138">Di seguito viene fornito solo un risultato parziale.</span><span class="sxs-lookup"><span data-stu-id="98b7b-138">(Only a partial result is shown here.)</span></span>  
  
```  
 <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact FirstName="Gustavo" LastName="Achong" />   
  <Person.Contact FirstName="Catherine" LastName="Abel" />  
</ROOT>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="98b7b-139">Quando si utilizza il Provider SQLXMLOLEDB o le classi gestite SQLXML, è possibile utilizzare la proprietà `ClientSideXml` per richiedere formattazione XML sul lato client.</span><span class="sxs-lookup"><span data-stu-id="98b7b-139">When you are using the SQLXMLOLEDB Provider or SQLXML Managed Classes, you can use the `ClientSideXml` property to request client-side XML formatting.</span></span>  
  
### <a name="the-workload-is-more-balanced"></a><span data-ttu-id="98b7b-140">Il carico di lavoro risulta più bilanciato.</span><span class="sxs-lookup"><span data-stu-id="98b7b-140">The workload is more balanced.</span></span>  
 <span data-ttu-id="98b7b-141">Poiché il client esegue la formattazione XML, il carico di lavoro viene bilanciato tra il server e il client, liberando il server per l'esecuzione di altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="98b7b-141">Because the client does the XML formatting, the workload is balanced between the server and client, freeing the server to do other things.</span></span>  
  
## <a name="supporting-client-side-xml-formatting"></a><span data-ttu-id="98b7b-142">Supporto della formattazione XML sul lato client</span><span class="sxs-lookup"><span data-stu-id="98b7b-142">Supporting Client-side XML Formatting</span></span>  
 <span data-ttu-id="98b7b-143">Per supportare la funzionalità di formattazione XML sul lato client, SQLXML fornisce gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="98b7b-143">To support the client-side XML formatting functionality, SQLXML provides:</span></span>  
  
-   <span data-ttu-id="98b7b-144">provider SQLXMLOLEDB</span><span class="sxs-lookup"><span data-stu-id="98b7b-144">SQLXMLOLEDB Provider</span></span>  
  
-   <span data-ttu-id="98b7b-145">classi gestite SQLXML</span><span class="sxs-lookup"><span data-stu-id="98b7b-145">SQLXML Managed Classes</span></span>  
  
-   <span data-ttu-id="98b7b-146">Supporto avanzato per modelli XML</span><span class="sxs-lookup"><span data-stu-id="98b7b-146">Enhanced XML template support</span></span>  
  
-   <span data-ttu-id="98b7b-147">Proprietà SqlXmlCommand. ClientSideXml</span><span class="sxs-lookup"><span data-stu-id="98b7b-147">SqlXmlCommand.ClientSideXml property</span></span>  
  
     <span data-ttu-id="98b7b-148">È possibile specificare formattazione sul lato client impostando su true questa proprietà per le classi gestite SQLXML.</span><span class="sxs-lookup"><span data-stu-id="98b7b-148">You can specify client-side formatting by setting this property of the SQLXML managed classes to true.</span></span>  
  
## <a name="enhanced-xml-template-support"></a><span data-ttu-id="98b7b-149">Supporto avanzato per modelli XML</span><span class="sxs-lookup"><span data-stu-id="98b7b-149">Enhanced XML Template Support</span></span>  
 <span data-ttu-id="98b7b-150">A partire da [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] , il modello XML in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] è stato migliorato con l'aggiunta dell'attributo **client-side-xml** .</span><span class="sxs-lookup"><span data-stu-id="98b7b-150">Beginning with [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], the XML template in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] has been enhanced with the addition of the **client-side-xml** attribute.</span></span> <span data-ttu-id="98b7b-151">Se questo attributo è impostato su true, i dati XML vengono formattati nel client.</span><span class="sxs-lookup"><span data-stu-id="98b7b-151">If this attribute is set to true, XML is formatted on the client.</span></span> <span data-ttu-id="98b7b-152">Si noti che questo attributo di modello è identico in funzionalità alla proprietà ClientSideXML specifica del provider SQLXMLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="98b7b-152">Note that this template attribute is identical in functionality to the SQLXMLOLEDB Provider-specific ClientSideXML property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98b7b-153">Se si esegue un modello XML in un'applicazione ADO che utilizza il provider SQLXMLOLEDB e si specifica sia l'attributo **client-side-xml** nel modello che la proprietà ClientSideXML del provider, il valore specificato nel modello avrà la precedenza.</span><span class="sxs-lookup"><span data-stu-id="98b7b-153">If you execute an XML template in an ADO application that is using the SQLXMLOLEDB Provider, and you specify both the **client-side-xml** attribute in the template and the provider ClientSideXML property, the value specified in the template takes precedence.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98b7b-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98b7b-154">See Also</span></span>  
 <span data-ttu-id="98b7b-155">[Architettura della formattazione XML sul lato client e sul lato server &#40;SQLXML 4,0&#41;](server-side-xml-formatting-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="98b7b-155">[Architecture of Client-side and Server-side XML Formatting &#40;SQLXML 4.0&#41;](server-side-xml-formatting-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="98b7b-156">[FOR XML &#40;SQL Server&#41;](../../xml/for-xml-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="98b7b-156">[FOR XML &#40;SQL Server&#41;](../../xml/for-xml-sql-server.md) </span></span>  
 <span data-ttu-id="98b7b-157">[Considerazioni sulla sicurezza per XML &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/for-xml-security-considerations-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="98b7b-157">[FOR XML Security Considerations &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/for-xml-security-considerations-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="98b7b-158">[Supporto del tipo di dati XML in SQLXML 4,0](../xml-data-type-support-in-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="98b7b-158">[xml Data Type Support in SQLXML 4.0](../xml-data-type-support-in-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="98b7b-159">[Classi gestite SQLXML](../../sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-4-0-net-framework-support-managed-classes.md) </span><span class="sxs-lookup"><span data-stu-id="98b7b-159">[SQLXML Managed Classes](../../sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-4-0-net-framework-support-managed-classes.md) </span></span>  
 <span data-ttu-id="98b7b-160">[Formattazione XML sul lato client e sul lato server &#40;SQLXML 4,0&#41;](client-side-vs-server-side-xml-formatting-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="98b7b-160">[Client-side vs. Server-side XML Formatting &#40;SQLXML 4.0&#41;](client-side-vs-server-side-xml-formatting-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="98b7b-161">[Oggetto SqlXmlCommand &#40;classi gestite SQLXML&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-managed-classes-sqlxmlcommand-object.md) </span><span class="sxs-lookup"><span data-stu-id="98b7b-161">[SqlXmlCommand Object &#40;SQLXML Managed Classes&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-managed-classes-sqlxmlcommand-object.md) </span></span>  
 [<span data-ttu-id="98b7b-162">Dati XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="98b7b-162">XML Data &#40;SQL Server&#41;</span></span>](../../xml/xml-data-sql-server.md)  
  
  
