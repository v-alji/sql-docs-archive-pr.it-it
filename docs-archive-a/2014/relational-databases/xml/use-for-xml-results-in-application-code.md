---
title: Usare i risultati di query FOR XML nel codice di un'applicazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, application code usage
- XML [SQL Server], FOR XML clause
- ASP.NET [SQL Server]
- .NET Framework [SQL Server], FOR XML data
- ADO [SQL Server]
- XML data islands [SQL Server]
- data islands [SQL Server]
ms.assetid: 41ae67bd-ece9-49ea-8062-c8d658ab4154
author: rothja
ms.author: jroth
ms.openlocfilehash: 3cabe7e65cb53a28a370615ed84e38ba2b8db44c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636596"
---
# <a name="use-for-xml-results-in-application-code"></a><span data-ttu-id="89195-102">Utilizzare i risultati di query FOR XML nel codice di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="89195-102">Use FOR XML Results in Application Code</span></span>
  <span data-ttu-id="89195-103">L'utilizzo delle clausole FOR XML nelle query SQL consente di recuperare e inoltre di eseguire il cast dei risultati delle query come dati XML.</span><span class="sxs-lookup"><span data-stu-id="89195-103">By using FOR XML clauses with SQL queries, you can retrieve and even cast query results as XML data.</span></span> <span data-ttu-id="89195-104">Se i risultati di una query FOR XML possono essere utilizzati nel codice XML dell'applicazione, è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="89195-104">This functionality allows you to do the following when FOR XML query results can be used in XML application code:</span></span>  
  
-   <span data-ttu-id="89195-105">Eseguire query nelle tabelle SQL per le istanze di valori di [Dati XML &#40;SQL Server&#41;](xml-data-sql-server.md)</span><span class="sxs-lookup"><span data-stu-id="89195-105">Query SQL tables for instances of [XML Data &#40;SQL Server&#41;](xml-data-sql-server.md) values</span></span>  
  
-   <span data-ttu-id="89195-106">Applicare la [Direttiva TYPE in query FOR XML](type-directive-in-for-xml-queries.md) per restituire il risultato di query che contengono dati di testo o di tipo image in formato XML.</span><span class="sxs-lookup"><span data-stu-id="89195-106">Apply the [TYPE Directive in FOR XML Queries](type-directive-in-for-xml-queries.md) to return the result of queries that contain text or image typed data as XML</span></span>  
  
 <span data-ttu-id="89195-107">In questo argomento vengono forniti esempi di questi approcci.</span><span class="sxs-lookup"><span data-stu-id="89195-107">This topic provides examples that demonstrate these approaches.</span></span>  
  
## <a name="retrieving-for-xml-data-with-ado-and-xml-data-islands"></a><span data-ttu-id="89195-108">Recupero dei dati di query FOR XML con ADO e isole di dati XML</span><span class="sxs-lookup"><span data-stu-id="89195-108">Retrieving FOR XML Data with ADO and XML Data Islands</span></span>  
 <span data-ttu-id="89195-109">Quando si utilizzano le query FOR XML, è possibile inserire i risultati nell'oggetto ADO `Stream` o in altri oggetti che supportano l'interfaccia COM `IStream`, ad esempio gli oggetti ASP (Active Server Pages) `Request` e `Response`.</span><span class="sxs-lookup"><span data-stu-id="89195-109">The ADO `Stream` object or other objects that support the COM `IStream` interface, such as the Active Server Pages (ASP) `Request` and `Response` objects, can be used to contain the results when you are working with FOR XML queries.</span></span>  
  
 <span data-ttu-id="89195-110">Ad esempio, il codice ASP seguente mostra i risultati di una query eseguita sulla colonna con tipo di dati `xml` Demographics della tabella Sales.Store del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="89195-110">For example, the following ASP code shows the results of querying an `xml` data type column, Demographics, in the Sales.Store table of the AdventureWorks sample database.</span></span> <span data-ttu-id="89195-111">La query cerca specificatamente il valore dell'istanza della colonna relativo alla riga in cui CustomerID è uguale a 3.</span><span class="sxs-lookup"><span data-stu-id="89195-111">Specifically, the query looks for the instance value of this column for the row where the CustomerID is equal to 3.</span></span>  
  
```  
<!-- BeginRecordAndStreamVBS -->  
<%@ LANGUAGE = VBScript %>  
<!-- %  Option Explicit      % -->  
<!-- 'Request.ServerVariables("SERVER_NAME") & ";" & _ -->  
<HTML>  
<HEAD>  
<META NAME="GENERATOR" Content="Microsoft Developer Studio"/>  
<META HTTP-EQUIV="Content-Type" content="text/html"; charset="iso-8859-1">  
<TITLE>FOR XML Query Example</TITLE>  
<STYLE>  
   BODY  
   {  
      FONT-FAMILY: Tahoma;  
      FONT-SIZE: 8pt;  
      OVERFLOW: auto  
   }  
   H3  
   {  
      FONT-FAMILY: Tahoma;  
      FONT-SIZE: 8pt;  
      OVERFLOW: auto  
   }  
</STYLE>  
  
<!-- #include file="adovbs.inc" -->  
<%  
   Response.Write "<H3>Server-side processing</H3>"  
   Response.Write "Page Generated @ " & Now() & "<BR/>"  
   Dim adoConn  
   Set adoConn = Server.CreateObject("ADODB.Connection")  
   Dim sConn  
   sConn = "Provider=SQLOLEDB;Data Source=(local);" & _  
            "Initial Catalog=AdventureWorks;Integrated Security=SSPI;"  
   Response.write "Connect String = " & sConn & "<BR/>"  
   adoConn.ConnectionString = sConn  
   adoConn.CursorLocation = adUseClient  
   adoConn.Open  
   Response.write "ADO Version = " & adoConn.Version & "<BR/>"  
   Response.write "adoConn.State = " & adoConn.State & "<BR/>"  
   Dim adoCmd  
   Set adoCmd = Server.CreateObject("ADODB.Command")  
   Set adoCmd.ActiveConnection = adoConn  
   Dim sQuery  
   sQuery = "<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql'><sql:query>SELECT Demographics from Sales.Store WHERE CustomerID = 3 FOR XML AUTO</sql:query></ROOT>"  
   Response.write "Query String = " & sQuery & "<BR/>"  
   Dim adoStreamQuery  
   Set adoStreamQuery = Server.CreateObject("ADODB.Stream")  
   adoStreamQuery.Open  
   adoStreamQuery.WriteText sQuery, adWriteChar  
   adoStreamQuery.Position = 0  
   adoCmd.CommandStream = adoStreamQuery  
   adoCmd.Dialect = "{5D531CB2-E6Ed-11D2-B252-00C04F681B71}"  
   Response.write "Pushing XML to client for processing "  & "<BR/>"  
   adoCmd.Properties("Output Stream") = Response  
   Response.write "<XML ID='MyDataIsle'>"  
   adoCmd.Execute , , 1024  
   Response.write "</XML>"  
%>  
<SCRIPT language="VBScript" For="window" Event="onload">  
   Dim xmlDoc  
   Set xmlDoc = MyDataIsle.XMLDocument  
   Dim root  
   Set root = xmlDoc.documentElement.childNodes.Item(0).childNodes.Item(0).childNodes.Item(0)  
   For each child in root.childNodes  
      dim OutputXML  
      OutputXML = document.all("log").innerHTML  
      document.all("log").innerHTML = OutputXML & "<LI><B>" & child.nodeName &  ":</B>  " & child.Text  & "</LI>"  
   Next  
   MsgBox xmlDoc.xml  
</SCRIPT>  
</HEAD>  
<BODY>  
   <H3>Client-side processing of XML Document MyDataIsle</H3>  
   <UL id=log>  
   </UL>  
</BODY>  
</HTML>  
<!-- EndRecordAndStreamVBS -->  
```  
  
 <span data-ttu-id="89195-112">Questa pagina ASP di esempio contiene codice VBScript sul lato server che utilizza ADO per eseguire la query FOR XML e restituire i risultati XML in un'isola di dati XML, MyDataIsle.</span><span class="sxs-lookup"><span data-stu-id="89195-112">This example ASP page contains server-side VBScript that uses ADO to execute the FOR XML query and return the XML results in an XML data island, MyDataIsle.</span></span> <span data-ttu-id="89195-113">L'isola di dati XML viene quindi restituita nel browser per un'ulteriore elaborazione sul lato client,</span><span class="sxs-lookup"><span data-stu-id="89195-113">This XML data island is then returned in the browser for additional client-side processing.</span></span> <span data-ttu-id="89195-114">durante la quale viene utilizzato codice VBScript aggiuntivo per elaborare il contenuto dell'isola di dati XML.</span><span class="sxs-lookup"><span data-stu-id="89195-114">Additional client-side VBScript code is then used to process the contents of the XML data island.</span></span> <span data-ttu-id="89195-115">Il processo viene eseguito prima di visualizzare il contenuto come parte del DHTML risultante e di aprire una finestra di messaggio in cui è visualizzato il contenuto pre-elaborato dell'isola di dati XML.</span><span class="sxs-lookup"><span data-stu-id="89195-115">This process is performed before displaying the contents as part of the resultant DHTML and opening a message box to show the preprocessed contents of the XML data island.</span></span>  
  
#### <a name="to-test-this-example"></a><span data-ttu-id="89195-116">Per testare l'esempio</span><span class="sxs-lookup"><span data-stu-id="89195-116">To test this example</span></span>  
  
1.  <span data-ttu-id="89195-117">Verificare che IIS e il database di esempio AdventureWorks per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] siano installati.</span><span class="sxs-lookup"><span data-stu-id="89195-117">Verify that IIS is installed and that the AdventureWorks sample database for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been installed.</span></span>  
  
     <span data-ttu-id="89195-118">Per eseguire l'esempio, è necessario che sia installato Internet Information Services (IIS) 5.0 o versioni successive e che sia attivato il supporto ASP.</span><span class="sxs-lookup"><span data-stu-id="89195-118">This example requires that Internet Information Services (IIS) version 5.0, or later versions, are installed with ASP support enabled.</span></span> <span data-ttu-id="89195-119">È inoltre necessario installare il database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="89195-119">Also, the AdventureWorks sample database has to be installed.</span></span>  
  
2.  <span data-ttu-id="89195-120">Copiare il codice di esempio fornito in precedenza e incollarlo nell'editor XML o di testo in uso.</span><span class="sxs-lookup"><span data-stu-id="89195-120">Copy the code example that was previously provided and paste it into the XML or text editor that you use.</span></span> <span data-ttu-id="89195-121">Salvare il file come RetrieveResults.asp nella directory radice utilizzata per IIS,</span><span class="sxs-lookup"><span data-stu-id="89195-121">Save the file as RetrieveResults.asp in the root directory that is used for IIS.</span></span> <span data-ttu-id="89195-122">che in genere è C:Inetpub\wwwroot.</span><span class="sxs-lookup"><span data-stu-id="89195-122">Typically, this is C:Inetpub\wwwroot.</span></span>  
  
3.  <span data-ttu-id="89195-123">Aprire la pagina ASP in una finestra del browser specificando l'URL seguente.</span><span class="sxs-lookup"><span data-stu-id="89195-123">Open the ASP page in a browser window by using the following URL.</span></span> <span data-ttu-id="89195-124">Sostituire innanzitutto 'MyServer' con "localhost" o con il nome effettivo del server in cui sono installati [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e IIS.</span><span class="sxs-lookup"><span data-stu-id="89195-124">First, replace 'MyServer' with either "localhost" or the actual name of the server where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and IIS are installed.</span></span>  
  
    ```  
    http://MyServer/RetrieveResults.asp  
    ```  
  
 <span data-ttu-id="89195-125">I risultati visualizzati per la pagina HTML creata saranno simili all'output di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="89195-125">The generated HTML page results that appear will be similar to the following sample output:</span></span>  
  
##### <a name="server-side-processing"></a><span data-ttu-id="89195-126">Elaborazione sul lato server</span><span class="sxs-lookup"><span data-stu-id="89195-126">Server-side processing</span></span>  
 <span data-ttu-id="89195-127">Page Generated \@ 3/11/2006 3:36:02 PM</span><span class="sxs-lookup"><span data-stu-id="89195-127">Page Generated \@ 3/11/2006 3:36:02 PM</span></span>  
  
 <span data-ttu-id="89195-128">Connect String = Provider=SQLOLEDB;Data Source=MyServer;Initial Catalog=AdventureWorks;Integrated Security=SSPI;</span><span class="sxs-lookup"><span data-stu-id="89195-128">Connect String = Provider=SQLOLEDB;Data Source=MyServer;Initial Catalog=AdventureWorks;Integrated Security=SSPI;</span></span>  
  
 <span data-ttu-id="89195-129">ADO Version = 2.8</span><span class="sxs-lookup"><span data-stu-id="89195-129">ADO Version = 2.8</span></span>  
  
 <span data-ttu-id="89195-130">adoConn.State = 1</span><span class="sxs-lookup"><span data-stu-id="89195-130">adoConn.State = 1</span></span>  
  
 <span data-ttu-id="89195-131">Query String = SELECT Demographics from Sales.Store WHERE CustomerID = 3 FOR XML AUTO</span><span class="sxs-lookup"><span data-stu-id="89195-131">Query String = SELECT Demographics from Sales.Store WHERE CustomerID = 3 FOR XML AUTO</span></span>  
  
 <span data-ttu-id="89195-132">Pushing XML to client for processing</span><span class="sxs-lookup"><span data-stu-id="89195-132">Pushing XML to client for processing</span></span>  
  
##### <a name="client-side-processing-of-xml-document-mydataisle"></a><span data-ttu-id="89195-133">Elaborazione sul lato client del documento XML MyDataIsle</span><span class="sxs-lookup"><span data-stu-id="89195-133">Client-side processing of XML Document MyDataIsle</span></span>  
  
-   <span data-ttu-id="89195-134">**AnnualSales:** 1500000</span><span class="sxs-lookup"><span data-stu-id="89195-134">**AnnualSales:** 1500000</span></span>  
  
-   <span data-ttu-id="89195-135">**AnnualRevenue:** 150000</span><span class="sxs-lookup"><span data-stu-id="89195-135">**AnnualRevenue:** 150000</span></span>  
  
-   <span data-ttu-id="89195-136">**BankName:** Primary International</span><span class="sxs-lookup"><span data-stu-id="89195-136">**BankName:** Primary International</span></span>  
  
-   <span data-ttu-id="89195-137">**BusinessType:** OS</span><span class="sxs-lookup"><span data-stu-id="89195-137">**BusinessType:** OS</span></span>  
  
-   <span data-ttu-id="89195-138">**YearOpened:** 1974</span><span class="sxs-lookup"><span data-stu-id="89195-138">**YearOpened:** 1974</span></span>  
  
-   <span data-ttu-id="89195-139">**Specialty:** Strada</span><span class="sxs-lookup"><span data-stu-id="89195-139">**Specialty:** Road</span></span>  
  
-   <span data-ttu-id="89195-140">**SquareFeet:** 38000</span><span class="sxs-lookup"><span data-stu-id="89195-140">**SquareFeet:** 38000</span></span>  
  
-   <span data-ttu-id="89195-141">**Brands:** 3</span><span class="sxs-lookup"><span data-stu-id="89195-141">**Brands:** 3</span></span>  
  
-   <span data-ttu-id="89195-142">**Internet:** DSL</span><span class="sxs-lookup"><span data-stu-id="89195-142">**Internet:** DSL</span></span>  
  
-   <span data-ttu-id="89195-143">**NumberEmployees:** 40</span><span class="sxs-lookup"><span data-stu-id="89195-143">**NumberEmployees:** 40</span></span>  
  
 <span data-ttu-id="89195-144">Nella finestra di messaggio VBScript verrà visualizzato il contenuto originale non filtrato dell'isola di dati XML seguente, restituito dai risultati della query FOR XML.</span><span class="sxs-lookup"><span data-stu-id="89195-144">The VBScript message box will then show the following original, unfiltered XML data island contents that were returned by the FOR XML query results.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Sales.Store>  
    <Demographics>  
      <StoreSurvey xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/StoreSurvey">  
        <AnnualSales>1500000</AnnualSales>  
        <AnnualRevenue>150000</AnnualRevenue>  
        <BankName>Primary International</BankName>  
        <BusinessType>OS</BusinessType>  
        <YearOpened>1974</YearOpened>  
        <Specialty>Road</Specialty>  
        <SquareFeet>38000</SquareFeet>  
        <Brands>3</Brands>  
        <Internet>DSL</Internet>  
        <NumberEmployees>40</NumberEmployees>  
      </StoreSurvey>  
    </Demographics>  
  </Sales.Store>  
</ROOT>  
```  
  
## <a name="retrieving-for-xml-data-with-aspnet-and-the-net-framework"></a><span data-ttu-id="89195-145">Recupero dei dati di query FOR XML con ASP.NET e .NET Framework</span><span class="sxs-lookup"><span data-stu-id="89195-145">Retrieving FOR XML Data with ASP.NET and the .NET Framework</span></span>  
 <span data-ttu-id="89195-146">Come nell'esempio precedente, il codice ASP.NET seguente mostra i risultati di una query eseguita sulla colonna con tipo di dati `xml` Demographics della tabella Sales.Store del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="89195-146">As in the previous example, the following ASP.NET code shows the results of querying an `xml` data type column, Demographics, in the Sales.Store table of the AdventureWorks sample database.</span></span> <span data-ttu-id="89195-147">Come nell'esempio precedente, la query cerca il valore dell'istanza della colonna relativo alla riga in cui CustomerID è uguale a 3.</span><span class="sxs-lookup"><span data-stu-id="89195-147">As in the previous example, the query looks for the instance value of this column for the row where the CustomerID is equal to 3.</span></span>  
  
 <span data-ttu-id="89195-148">Nell'esempio, per la restituzione e il rendering dei risultati della query FOR XML vengono utilizzate le API gestite di Microsoft .NET Framework seguenti:</span><span class="sxs-lookup"><span data-stu-id="89195-148">In this example, the following Microsoft .NET Framework managed APIs are used to accomplish the return and rendering of the FOR XML query results:</span></span>  
  
1.  <span data-ttu-id="89195-149">`SqlConnection` consente di stabilire una connessione a SQL Server, basata sul contenuto di una variabile stringa di connessione specificata, strConn.</span><span class="sxs-lookup"><span data-stu-id="89195-149">`SqlConnection` is used to open a connection to SQL Server, based on the contents of a specified connection string variable, strConn.</span></span>  
  
2.  <span data-ttu-id="89195-150">`SqlDataAdapter` funge quindi da adattatore dati e consente di eseguire la query FOR XML utilizzando la connessione SQL e una stringa di query SQL specificata.</span><span class="sxs-lookup"><span data-stu-id="89195-150">`SqlDataAdapter` is then used as the data adapter and it uses the SQL connection and a specified SQL query string to execute the FOR XML query.</span></span>  
  
3.  <span data-ttu-id="89195-151">Dopo avere eseguito la query, viene chiamato il metodo `SqlDataAdapter.Fill`, che viene quindi passato a un'istanza di un `DataSet,` MyDataSet, per riempire il set di dati con l'output della query FOR XML.</span><span class="sxs-lookup"><span data-stu-id="89195-151">After the query has executed, the `SqlDataAdapter.Fill` method is then called and passed an instance of a `DataSet,` MyDataSet, in order to fill the data set with the output of the FOR XML query.</span></span>  
  
4.  <span data-ttu-id="89195-152">Viene quindi chiamato il metodo `DataSet.GetXml` per restituire i risultati della query come una stringa visualizzabile nella pagina HTML generata dal server.</span><span class="sxs-lookup"><span data-stu-id="89195-152">The `DataSet.GetXml` method is then called to return the query results as a string that can be displayed in the server-generated HTML page.</span></span>  
  
    ```  
    <%@ Page Language="VB" %>  
    <HTML>  
    <HEAD>  
    <TITLE>FOR XML Query Example</TITLE>  
    <STYLE>  
       BODY  
       {  
          FONT-FAMILY: Tahoma;  
          FONT-SIZE: 8pt;  
          OVERFLOW: auto  
       }  
       H3  
       {  
          FONT-FAMILY: Tahoma;  
          FONT-SIZE: 8pt;  
          OVERFLOW: auto  
       }  
    </STYLE>  
    </HEAD>  
    <BODY>  
    <%  
    Dim s as String  
    s = "<H3>Server-side processing</H3>" & _  
        "Page Generated @ " & Now() & "<BR/>"  
  
    Dim SQL As String   
    SQL = "SELECT Demographics from Sales.Store WHERE CustomerID = 3 FOR XML AUTO"  
  
    Dim strConn As String   
    strConn = "Server=(local);Database=AdventureWorks;Integrated Security=SSPI;"  
  
    Dim MySqlConn As New System.Data.SqlClient.SqlConnection(strConn)  
    Dim MySqlAdapter As New System.Data.SqlClient.SqlDataAdapter(SQL,MySqlConn)  
    Dim MyDataSet As New System.Data.DataSet  
  
    MySqlConn.Open()  
    s = s & "<P>SqlConnection opened.</P>"   
  
    MySqlAdapter.Fill(MyDataSet)  
    s = s & "<P>" & MyDataSet.GetXml  & "</P>"  
  
    MySqlConn.Close()  
    s = s & "<P>SqlConnection closed.</P>"   
  
    Message.InnerHtml=s  
    %>  
    <SPAN id="Message" runat=server />  
    </BODY>  
    </HTML>  
    ```  
  
#### <a name="to-test-this-example"></a><span data-ttu-id="89195-153">Per testare l'esempio</span><span class="sxs-lookup"><span data-stu-id="89195-153">To test this example</span></span>  
  
1.  <span data-ttu-id="89195-154">Verificare che IIS e il database di esempio AdventureWorks per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] siano installati.</span><span class="sxs-lookup"><span data-stu-id="89195-154">Verify that IIS is installed and that the AdventureWorks sample database for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been installed.</span></span>  
  
     <span data-ttu-id="89195-155">Per eseguire l'esempio, è necessario che sia installato Internet Information Services (IIS) 5.0 o versioni successive e che sia attivato il supporto ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="89195-155">This example requires that Internet Information Services (IIS) version 5.0, or later versions, are installed with ASP.NET support enabled.</span></span> <span data-ttu-id="89195-156">È inoltre necessario installare il database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="89195-156">Also, the AdventureWorks sample database has to be installed.</span></span>  
  
2.  <span data-ttu-id="89195-157">Copiare il codice fornito in precedenza e incollarlo nell'editor XML o di testo in uso.</span><span class="sxs-lookup"><span data-stu-id="89195-157">Copy the code that was previously provided and paste it into the XML or text editor that you use.</span></span> <span data-ttu-id="89195-158">Salvare il file come RetrieveResults.aspx nella directory radice utilizzata per IIS,</span><span class="sxs-lookup"><span data-stu-id="89195-158">Save the file as RetrieveResults.aspx in the root directory used for IIS.</span></span> <span data-ttu-id="89195-159">che in genere è C:Inetpub\wwwroot.</span><span class="sxs-lookup"><span data-stu-id="89195-159">Typically, this is C:Inetpub\wwwroot.</span></span>  
  
3.  <span data-ttu-id="89195-160">Aprire la pagina ASP.NET in una finestra del browser specificando l'URL seguente.</span><span class="sxs-lookup"><span data-stu-id="89195-160">Open the ASP.NET page in a browser window using the following URL.</span></span> <span data-ttu-id="89195-161">Sostituire innanzitutto 'MyServer' con "localhost" o con il nome effettivo del server in cui sono installati [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e IIS.</span><span class="sxs-lookup"><span data-stu-id="89195-161">First, replace 'MyServer' with either "localhost" or the actual name of the server where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and IIS are installed.</span></span>  
  
    ```  
    http://MyServer/RetrieveResults.aspx  
    ```  
  
 <span data-ttu-id="89195-162">I risultati visualizzati per la pagina HTML creata saranno simili all'output di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="89195-162">The generated HTML page results that appear will be similar to the following sample output:</span></span>  
  
##### <a name="server-side-processing"></a><span data-ttu-id="89195-163">Elaborazione sul lato server</span><span class="sxs-lookup"><span data-stu-id="89195-163">Server-side processing</span></span>  
  
```  
Page Generated @ 3/11/2006 3:36:02 PM  
  
SqlConnection opened.  
  
<Sales.Store><Demographics><StoreSurvey xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/StoreSurvey"><AnnualSales>1500000</AnnualSales><AnnualRevenue>150000</AnnualRevenue><BankName>Primary International</BankName><BusinessType>OS</BusinessType><YearOpened>1974</YearOpened><Specialty>Road</Specialty><SquareFeet>38000</SquareFeet><Brands>3</Brands><Internet>DSL</Internet><NumberEmployees>40</NumberEmployees></StoreSurvey></Demographics></Sales.Store>  
  
SqlConnection closed.  
```  
  
> [!NOTE]  
>  <span data-ttu-id="89195-164">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `xml` supporto del tipo di dati consente di richiedere che il risultato di una query for XML venga restituito come `xml` tipo di dati, anziché come dati tipizzati stringa o immagine, specificando la [direttiva Type](type-directive-in-for-xml-queries.md).</span><span class="sxs-lookup"><span data-stu-id="89195-164">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]`xml` data type support lets you request that the result of a FOR XML query be returned as `xml` data type, instead of as string or image typed data, by specifying the [TYPE directive](type-directive-in-for-xml-queries.md).</span></span> <span data-ttu-id="89195-165">L'uso della direttiva TYPE nelle query FOR XML consente di ottenere l'accesso a livello di programmazione ai risultati FOR XML, in modo analogo a quanto illustrato in [Utilizzo di dati XML nelle applicazioni](use-xml-data-in-applications.md).</span><span class="sxs-lookup"><span data-stu-id="89195-165">When the TYPE directive is used in FOR XML queries, it provides programmatic access to the FOR XML results similar to that shown in [Use XML Data in Applications](use-xml-data-in-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89195-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89195-166">See Also</span></span>  
 [<span data-ttu-id="89195-167">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="89195-167">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
