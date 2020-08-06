---
title: Sintassi di query XML per i dati del report XML (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- namespaces [Reporting Services]
- data processing extensions [Reporting Services], data sources
- xmldp [Reporting Services]
- XML [Reporting Services], data retrieval
ms.assetid: d203886f-faa1-4a02-88f5-dd4c217181ef
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62dde2b3ab18b5edb5c3786d39173fea3a0854ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623811"
---
# <a name="xml-query-syntax-for-xml-report-data-ssrs"></a><span data-ttu-id="14bc6-102">Sintassi di query XML per i dati del report XML (SSRS)</span><span class="sxs-lookup"><span data-stu-id="14bc6-102">XML Query Syntax for XML Report Data (SSRS)</span></span>
  <span data-ttu-id="14bc6-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]è possibile creare set di dati per origini dati XML.</span><span class="sxs-lookup"><span data-stu-id="14bc6-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can create datasets for XML data sources.</span></span> <span data-ttu-id="14bc6-104">Dopo aver definito un'origine dati, è possibile creare una query per il set di dati.</span><span class="sxs-lookup"><span data-stu-id="14bc6-104">After you define a data source, you create a query for the dataset.</span></span> <span data-ttu-id="14bc6-105">In base al tipo di dati XML a cui punta l'origine dei dati, è possibile creare la query del set di dati includendo un elemento `Query` XML o un percorso di elemento.</span><span class="sxs-lookup"><span data-stu-id="14bc6-105">Depending on the type of XML data pointed to by the data source, you create the dataset query by including an XML `Query` or an element path.</span></span> <span data-ttu-id="14bc6-106">Un XML `Query` inizia con un **\<Query>** tag e include spazi dei nomi ed elementi XML che variano a seconda dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="14bc6-106">An XML `Query` starts with a **\<Query>** tag and includes namespaces and XML elements that vary depending on the data source.</span></span> <span data-ttu-id="14bc6-107">Un percorso di elemento è indipendente dallo spazio dei nomi e specifica i nodi e gli attributi dei nodi dei dati XML sottostanti da utilizzare tramite una sintassi di tipo XPath.</span><span class="sxs-lookup"><span data-stu-id="14bc6-107">An element path is namespace-independent and specifies which nodes and node attributes to use from the underlying XML data with an XPath-like syntax.</span></span> <span data-ttu-id="14bc6-108">Per altre informazioni sui percorsi di elementi, vedere [Sintassi del percorso di elemento per i dati del report XML &#40;SSRS&#41;](report-data-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="14bc6-108">For more information about element paths, see [Element Path Syntax for XML Report Data &#40;SSRS&#41;](report-data-ssrs.md).</span></span>  
  
 <span data-ttu-id="14bc6-109">È possibile creare un'origine dei dati XML per i tipi di dati XML seguenti:</span><span class="sxs-lookup"><span data-stu-id="14bc6-109">You can create an XML data source for the following types of XML data:</span></span>  
  
-   <span data-ttu-id="14bc6-110">Documenti XML a cui punta un URL tramite il protocollo HTTP</span><span class="sxs-lookup"><span data-stu-id="14bc6-110">Xml documents pointed to by a URL using http protocol</span></span>  
  
-   <span data-ttu-id="14bc6-111">Endpoint del servizio Web che restituiscono dati XML</span><span class="sxs-lookup"><span data-stu-id="14bc6-111">Web service endpoints that return XML data</span></span>  
  
-   <span data-ttu-id="14bc6-112">Dati XML incorporati</span><span class="sxs-lookup"><span data-stu-id="14bc6-112">Embedded XML data</span></span>  
  
 <span data-ttu-id="14bc6-113">La modalità utilizzata per specificare un elemento `Query` XML o un percorso di elemento dipende dal tipo di dati XML.</span><span class="sxs-lookup"><span data-stu-id="14bc6-113">How you specify an XML `Query` or an element path depends on the type of XML data.</span></span>  
  
 <span data-ttu-id="14bc6-114">Per un documento XML, l'elemento `Query` XML è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="14bc6-114">For an XML document, the XML `Query` is optional.</span></span> <span data-ttu-id="14bc6-115">Se viene incluso, può contenere un elemento `ElementPath` XML facoltativo.</span><span class="sxs-lookup"><span data-stu-id="14bc6-115">If it is included, it can contain an optional XML `ElementPath`.</span></span> <span data-ttu-id="14bc6-116">Per il valore dell'elemento `ElementPath` XML viene utilizzata la sintassi del percorso di elemento.</span><span class="sxs-lookup"><span data-stu-id="14bc6-116">The value of the XML `ElementPath` uses the element path syntax.</span></span> <span data-ttu-id="14bc6-117">Gli elementi `Query` XML ed `ElementPath` XML vengono inclusi per consentire l'elaborazione corretta degli spazi dei nomi quando richiesto dai dati XML dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="14bc6-117">You include the XML `Query` and XML `ElementPath` to process namespaces correctly when it is needed by the XML data from the data source.</span></span>  
  
 <span data-ttu-id="14bc6-118">Per un endpoint del servizio Web a cui punta un URL della stringa di connessione, l'elemento `Query` definisce l'azione SOAP o il metodo del servizio Web oppure entrambi.</span><span class="sxs-lookup"><span data-stu-id="14bc6-118">For a Web service endpoint pointed to by a connection string URL, the XML `Query` defines either the Web service method, the SOAP action, or both.</span></span> <span data-ttu-id="14bc6-119">Tramite il provider di dati XML viene creata una richiesta del servizio Web per recuperare i dati XML da utilizzare per il report.</span><span class="sxs-lookup"><span data-stu-id="14bc6-119">The XML data provider creates a Web service request that retrieves XML data to use for the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14bc6-120">Quando uno spazio dei nomi del servizio Web contiene una barra (`/)`, includere sia il metodo del servizio Web che l'azione SOAP, per consentire all'estensione per l'elaborazione dati XML di derivare lo spazio dei nomi in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="14bc6-120">When a Web service namespace includes a forward slash (`/)` character, include both the Web service method and the SOAP action so that the XML data processing extension can derive the namespace correctly.</span></span>  
  
 <span data-ttu-id="14bc6-121">Per un documento XML incorporato, l'elemento `Query` XML definisce i dati XML incorporati da utilizzare, include gli spazi dei nomi facoltativi e contiene un elemento `ElementPath` XML facoltativo.</span><span class="sxs-lookup"><span data-stu-id="14bc6-121">For an embedded XML document, the XML `Query` defines the embedded XML data to use, includes optional namespaces, and contains an optional XML `ElementPath`..</span></span>  
  
## <a name="specifying-query-parameters-for-xml-data"></a><span data-ttu-id="14bc6-122">Impostazione di parametri di query per dati XML</span><span class="sxs-lookup"><span data-stu-id="14bc6-122">Specifying Query Parameters for XML Data</span></span>  
 <span data-ttu-id="14bc6-123">È possibile specificare parametri di query per documenti XML.</span><span class="sxs-lookup"><span data-stu-id="14bc6-123">You can specify query parameters for XML documents.</span></span>  
  
-   <span data-ttu-id="14bc6-124">Per le richieste di URL, i parametri di query vengono inclusi come parametri URL standard.</span><span class="sxs-lookup"><span data-stu-id="14bc6-124">For URL requests, the query parameters are included as standard URL parameters.</span></span>  
  
-   <span data-ttu-id="14bc6-125">Per le richieste del servizio Web, i parametri di query vengono passati al metodo del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="14bc6-125">For Web service requests, query parameters are passed to the Web service method.</span></span> <span data-ttu-id="14bc6-126">Per definire un parametro di query, usare la pagina **Parametri** della finestra di dialogo **Proprietà set di dati** .</span><span class="sxs-lookup"><span data-stu-id="14bc6-126">To define a query parameter, use the **Parameters** page of the **Dataset Properties** dialog box.</span></span> <span data-ttu-id="14bc6-127">Per altre informazioni, vedere [Finestra di dialogo Proprietà set di dati, Parametri](dataset-properties-dialog-box-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="14bc6-127">For more information, see [Dataset Properties Dialog Box, Parameters](dataset-properties-dialog-box-parameters.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="14bc6-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="14bc6-128">Example</span></span>  
 <span data-ttu-id="14bc6-129">Negli esempi della tabella seguente viene illustrato come recuperare i dati dal servizio Web ReportServer, da un documento XML e dai dati XML incorporati.</span><span class="sxs-lookup"><span data-stu-id="14bc6-129">The examples in the following table illustrate how to retrieve data from the Report Server Web service, an XML document, and embedded XML data.</span></span>  
  
|<span data-ttu-id="14bc6-130">Origine dei dati XML</span><span class="sxs-lookup"><span data-stu-id="14bc6-130">XML data source</span></span>|<span data-ttu-id="14bc6-131">Esempio di query</span><span class="sxs-lookup"><span data-stu-id="14bc6-131">Query example</span></span>|  
|---------------------|-------------------|  
|<span data-ttu-id="14bc6-132">Dati XML del servizio Web dal metodo ListChildren .</span><span class="sxs-lookup"><span data-stu-id="14bc6-132">Web service XML data from ListChildren method.</span></span>|`<Query>`<br /><br /> `<Method Name="ListChildren" Namespace="https://schemas.microsoft.com/sqlserver/2005/06/30/reporting/reportingservices" />`<br /><br /> `</Query>`|  
|<span data-ttu-id="14bc6-133">Dati XML del servizio Web tramite SoapAction.</span><span class="sxs-lookup"><span data-stu-id="14bc6-133">Web service XML data from SoapAction.</span></span>|`<Query xmlns=namespace>`<br /><br /> `<SoapAction>http://schemas/microsoft.com/sqlserver/2005/03/23/reporting/reportingservices/ListChildren</SoapAction>`<br /><br /> `</Query>`|  
|<span data-ttu-id="14bc6-134">Documento XML o dati XML incorporati che utilizzano spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="14bc6-134">XML Document or embedded XML data that uses namespaces.</span></span><br /><br /> <span data-ttu-id="14bc6-135">Elemento Query specificando gli spazi dei nomi per un percorso di elemento.</span><span class="sxs-lookup"><span data-stu-id="14bc6-135">Query element specifying namespaces for an element path.</span></span>|`<Query xmlns:es="https://schemas.microsoft.com/StandardSchemas/ExtendedSales">`<br /><br /> `<ElementPath>/Customers/Customer/Orders/Order/es:LineItems/es:LineItem</ElementPath>`<br /><br /> `</Query>`|  
|<span data-ttu-id="14bc6-136">Documento XML incorporato.</span><span class="sxs-lookup"><span data-stu-id="14bc6-136">Embedded XML document.</span></span>|`<Query>`<br /><br /> `<XmlData>`<br /><br /> `<Customers>`<br /><br /> `<Customer ID="1">Bobby</Customer>`<br /><br /> `</Customers>`<br /><br /> `</XmlData>`<br /><br /> `<ElementPath>Customer {@}</ElementPath>`<br /><br /> `</Query>`|  
|<span data-ttu-id="14bc6-137">Documento XML che utilizza valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="14bc6-137">XML document that uses default.</span></span>|<span data-ttu-id="14bc6-138">*Nessuna query*.</span><span class="sxs-lookup"><span data-stu-id="14bc6-138">*No query*.</span></span><br /><br /> <span data-ttu-id="14bc6-139">Il percorso viene derivato dal documento XML stesso ed è indipendente dallo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="14bc6-139">The element path is derived from the XML document itself and is namespace-independent.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="14bc6-140">Nel primo esempio di servizio Web è riportato il contenuto del server di report che usa il metodo <xref:ReportService2006.ReportingService2006.ListChildren%2A> .</span><span class="sxs-lookup"><span data-stu-id="14bc6-140">The first Web service example lists the contents of the report server that uses the <xref:ReportService2006.ReportingService2006.ListChildren%2A> method.</span></span> <span data-ttu-id="14bc6-141">Per eseguire questa query, è necessario creare una nuova origine dati e impostare la stringa di connessione su http://localhost/reportserver/reportservice2006.asmx.</span><span class="sxs-lookup"><span data-stu-id="14bc6-141">To run this query, you must create a new data source and set the connection string to http://localhost/reportserver/reportservice2006.asmx.</span></span> <span data-ttu-id="14bc6-142">Il metodo <xref:ReportService2006.ReportingService2006.ListChildren%2A> accetta due parametri, ovvero `Item` e `Recursive`.</span><span class="sxs-lookup"><span data-stu-id="14bc6-142">The <xref:ReportService2006.ReportingService2006.ListChildren%2A> method takes two parameters: `Item` and `Recursive`.</span></span> <span data-ttu-id="14bc6-143">Impostare il valore predefinito di `Item` su `/` e quello di `Recursive` su `1`.</span><span class="sxs-lookup"><span data-stu-id="14bc6-143">Set the default value for `Item` to `/` and `Recursive` to `1`.</span></span>  
  
## <a name="specifying-namespaces"></a><span data-ttu-id="14bc6-144">Definizione degli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="14bc6-144">Specifying Namespaces</span></span>  
 <span data-ttu-id="14bc6-145">Utilizzare l'elemento `Query` XML per specificare gli spazi dei nomi utilizzati nei dati XML dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="14bc6-145">Use the XML `Query` element to specify the namespaces that are used in the XML data from the data source.</span></span> <span data-ttu-id="14bc6-146">Nella query XML seguente viene utilizzato lo spazio dei nomi `sales`.</span><span class="sxs-lookup"><span data-stu-id="14bc6-146">The following XML query uses the namespace `sales`.</span></span> <span data-ttu-id="14bc6-147">Nei nodi `ElementPath` XML per `sales:LineItems` e `sales:LineItem` viene utilizzato lo spazio dei nomi `sales`.</span><span class="sxs-lookup"><span data-stu-id="14bc6-147">The XML `ElementPath` nodes for `sales:LineItems` and `sales:LineItem` use the namespace `sales`.</span></span>  
  
```  
<Query xmlns:sales=  
"https://schemas.microsoft.com/StandardSchemas/ExtendedSales">  
   <SoapAction>  
      https://schemas.microsoft.com/SalesWebService/ListOrders   
   </SoapAction>  
   <ElementPath>  
      Customers/Customer/Orders/Order/sales:LineItems/sales:LineItem  
   </ElementPath>  
</Query>  
```  
  
 <span data-ttu-id="14bc6-148">Per specificare lo spazio dei nomi del provider di dati, affinché lo spazio dei nomi predefinito rimanga vuoto, utilizzare `xmldp`,</span><span class="sxs-lookup"><span data-stu-id="14bc6-148">To specify the data provider namespace so that the default namespace remains empty, use `xmldp`.</span></span> <span data-ttu-id="14bc6-149">come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="14bc6-149">This is shown in the following example.</span></span>  
  
### <a name="example"></a><span data-ttu-id="14bc6-150">Esempio</span><span class="sxs-lookup"><span data-stu-id="14bc6-150">Example</span></span>  
 <span data-ttu-id="14bc6-151">Negli esempi seguenti viene utilizzato il documento XML DPNamespace.xml, illustrato dopo la tabella.</span><span class="sxs-lookup"><span data-stu-id="14bc6-151">The following examples use the XML document DPNamespace.xml, which is provided for illustration after the table.</span></span> <span data-ttu-id="14bc6-152">Nella tabella sono illustrati due esempi di sintassi ElementPath XML che include i prefissi degli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="14bc6-152">This table shows two examples of XML ElementPath syntax that includes namespace prefixes.</span></span>  
  
|<span data-ttu-id="14bc6-153">Elemento Query XML</span><span class="sxs-lookup"><span data-stu-id="14bc6-153">XML Query Element</span></span>|<span data-ttu-id="14bc6-154">Campi risultanti nel set di dati</span><span class="sxs-lookup"><span data-stu-id="14bc6-154">Resulting fields in the dataset</span></span>|  
|-----------------------|-------------------------------------|  
|\<Query/>|<span data-ttu-id="14bc6-155">Valore A: `https://schemas.microsoft.com/..` .</span><span class="sxs-lookup"><span data-stu-id="14bc6-155">Value A: `https://schemas.microsoft.com/..`.</span></span><br /><br /> <span data-ttu-id="14bc6-156">Valore B: `https://schemas.microsoft.com/..` .</span><span class="sxs-lookup"><span data-stu-id="14bc6-156">Value B: `https://schemas.microsoft.com/..`.</span></span><br /><br /> <span data-ttu-id="14bc6-157">Valore C: `https://schemas.microsoft.com/.` ..</span><span class="sxs-lookup"><span data-stu-id="14bc6-157">Value C: `https://schemas.microsoft.com/.`..</span></span>|  
|\<xmldp:Query xmlns:xmldp="https://schemas.microsoft.com/sqlserver/2005/02/reporting/XmlDPQuery" xmlns:ns="https://schemas.microsoft.com/..."><br /><br /> <span data-ttu-id="14bc6-158">\<xmldp:ElementPath>Radice {} /NS: element2/node\</xmldp:ElementPath></span><span class="sxs-lookup"><span data-stu-id="14bc6-158">\<xmldp:ElementPath>Root {}/ns:Element2/Node\</xmldp:ElementPath></span></span><br /><br /> \</xmldp:Query>|<span data-ttu-id="14bc6-159">Value D</span><span class="sxs-lookup"><span data-stu-id="14bc6-159">Value D</span></span><br /><br /> <span data-ttu-id="14bc6-160">Value E</span><span class="sxs-lookup"><span data-stu-id="14bc6-160">Value E</span></span><br /><br /> <span data-ttu-id="14bc6-161">Value F</span><span class="sxs-lookup"><span data-stu-id="14bc6-161">Value F</span></span>|  
  
#### <a name="xml-document-dpnamespacexml"></a><span data-ttu-id="14bc6-162">Documento XML: DPNamespace.xml</span><span class="sxs-lookup"><span data-stu-id="14bc6-162">XML document: DPNamespace.xml</span></span>  
 <span data-ttu-id="14bc6-163">È possibile copiare il codice XML seguente e salvarlo in un URL disponibile per Progettazione report, per l'uso come origine dati XML, ad esempio, http://localhost/DPNamespace.xml.</span><span class="sxs-lookup"><span data-stu-id="14bc6-163">You can copy this XML and save it to a URL available for Report Designer to use as an XML data source: for example, http://localhost/DPNamespace.xml.</span></span>  
  
```  
<Root xmlns:ns="https://schemas.microsoft.com/...">  
   <ns:Element1>  
      <Node>Value A</Node>  
      <Node>Value B</Node>  
      <Node>Value C</Node>  
   </ns:Element1>  
   <ns:Element2>  
      <Node>Value D</Node>  
      <Node>Value E</Node>  
      <Node>Value F</Node>  
   </ns:Element2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="14bc6-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14bc6-164">See Also</span></span>  
 <span data-ttu-id="14bc6-165">[Tipo di connessione XML &#40;SSRS&#41;](xml-connection-type-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="14bc6-165">[XML Connection Type &#40;SSRS&#41;](xml-connection-type-ssrs.md) </span></span>  
 [<span data-ttu-id="14bc6-166">Esercitazioni su Reporting Services &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="14bc6-166">Reporting Services Tutorials &#40;SSRS&#41;</span></span>](../reporting-services-tutorials-ssrs.md)  
  
  
