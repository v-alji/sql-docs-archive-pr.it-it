---
title: Usare query FOR XML annidate in ASP.NET | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, nested FOR XML queries
- queries [XML in SQL Server], ASP.NET and
- nested FOR XML queries in ASP.NET
- ASP.NET [SQL Server]
ms.assetid: 691ac7dd-afc5-4760-932c-2b1dcd9394ed
author: rothja
ms.author: jroth
ms.openlocfilehash: 1218b4ad46f0d21d42ba480d68b29d7c39b03ea2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625256"
---
# <a name="use-nested-for-xml-queries-in-aspnet"></a><span data-ttu-id="b1ba8-102">Utilizzo di query FOR XML nidificate in ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b1ba8-102">Use Nested FOR XML Queries in ASP.NET</span></span>
  <span data-ttu-id="b1ba8-103">In questo esempio, l'applicazione ASP.NET consente di restituire il valore XML in un browser mediante l'esecuzione di una stored procedure in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b1ba8-103">In this example, an ASP.NET application returns XML to a browser by executing a stored procedure in SQL Server.</span></span> <span data-ttu-id="b1ba8-104">La stored procedure consente di generare un valore XML tramite query nidificate.</span><span class="sxs-lookup"><span data-stu-id="b1ba8-104">The stored procedure generates XML using nested queries.</span></span> <span data-ttu-id="b1ba8-105">Un'istruzione SELECT simile è illustrata nell'argomento [Generazione di elementi di pari livello tramite query nidificate in modalità AUTO](generate-siblings-with-a-nested-auto-mode-query.md).</span><span class="sxs-lookup"><span data-stu-id="b1ba8-105">A similar SELECT statement is shown in the topic [Generating Siblings by Using a Nested AUTO Mode Query](generate-siblings-with-a-nested-auto-mode-query.md).</span></span> <span data-ttu-id="b1ba8-106">In questo esempio viene indicata la modalità per utilizzare query FOR XML nidificate per generare un valore XML incentrato sugli attributi in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1ba8-106">This example demonstrates one way to use nested FOR XML queries to generate element-centric XML in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1ba8-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="b1ba8-107">Example</span></span>  
  
```  
CREATE PROC GetSalesOrderInfo AS  
SELECT   
      (SELECT top 2 SalesOrderID, SalesPersonID, CustomerID,  
         (select top 3 SalesOrderID, ProductID, OrderQty, UnitPrice  
           from Sales.SalesOrderDetail  
            WHERE  SalesOrderDetail.SalesOrderID = SalesOrderHeader.SalesOrderID  
            FOR XML AUTO, TYPE)  
      FROM  Sales.SalesOrderHeader  
        WHERE SalesOrderHeader.SalesOrderID = SalesOrder.SalesOrderID  
      for xml auto, type),  
        (SELECT *   
         FROM  (SELECT SalesPersonID, EmployeeID  
              FROM Sales.SalesPerson, HumanResources.Employee  
              WHERE SalesPerson.SalesPersonID = Employee.EmployeeID) As SalesPerson  
         WHERE  SalesPerson.SalesPersonID = SalesOrder.SalesPersonID  
       FOR XML AUTO, TYPE, ELEMENTS)  
FROM (SELECT SalesOrderHeader.SalesOrderID, SalesOrderHeader.SalesPersonID  
      FROM Sales.SalesOrderHeader, Sales.SalesPerson  
      WHERE SalesOrderHeader.SalesPersonID = SalesPerson.SalesPersonID  
     ) as SalesOrder  
ORDER BY SalesOrder.SalesOrderID  
FOR XML AUTO, TYPE  
GO  
```  
  
 <span data-ttu-id="b1ba8-108">L'applicazione aspx è riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="b1ba8-108">This is the .aspx application.</span></span> <span data-ttu-id="b1ba8-109">Viene eseguita la stored procedure e restituito il valore XML nel browser:</span><span class="sxs-lookup"><span data-stu-id="b1ba8-109">It executes the stored procedure and returns XML in the browser:</span></span>  
  
```  
<%@LANGUAGE=C# Debug=true %>  
<%@import Namespace="System.Xml"%>  
<%@import namespace="System.Data.SqlClient" %><%  
Response.Expires = -1;  
Response.ContentType = "text/xml";  
%>  
  
<%  
using(System.Data.SqlClient.SqlConnection c = new System.Data.SqlClient.SqlConnection("Data Source=server;Database=AdventureWorks;Integrated Security=SSPI;"))  
using(System.Data.SqlClient.SqlCommand cmd = c.CreateCommand())  
{  
   cmd.CommandText = "GetSalesOrderInfo";  
   cmd.CommandType = CommandType.StoredProcedure;  
   cmd.Connection.Open();  
   System.Xml.XmlReader r = cmd.ExecuteXmlReader();  
   System.Xml.XmlTextWriter w = new System.Xml.XmlTextWriter(Response.Output);  
   w.WriteStartElement("Root");  
   r.MoveToContent();  
   while(! r.EOF)  
   {  
      w.WriteNode(r, true);  
   }  
   w.WriteEndElement();  
   w.Flush();  
}  
%>  
```  
  
##### <a name="to-test-the-application"></a><span data-ttu-id="b1ba8-110">Per testare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="b1ba8-110">To test the application</span></span>  
  
1.  <span data-ttu-id="b1ba8-111">Creare la stored procedure nel database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b1ba8-111">Create the stored procedure in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="b1ba8-112">Salvare l'applicazione aspx nella directory c:\inetpub\wwwroot (GetSalesOrderInfo.aspx).</span><span class="sxs-lookup"><span data-stu-id="b1ba8-112">Save the .aspx application in the c:\inetpub\wwwroot directory (GetSalesOrderInfo.aspx).</span></span>  
  
3.  <span data-ttu-id="b1ba8-113">Eseguire l'applicazione ( http://server/GetSalesOrderInfo.aspx) .</span><span class="sxs-lookup"><span data-stu-id="b1ba8-113">Execute the application (http://server/GetSalesOrderInfo.aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1ba8-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1ba8-114">See Also</span></span>  
 [<span data-ttu-id="b1ba8-115">Utilizzo di query FOR XML nidificate</span><span class="sxs-lookup"><span data-stu-id="b1ba8-115">Use Nested FOR XML Queries</span></span>](use-nested-for-xml-queries.md)  
  
  
