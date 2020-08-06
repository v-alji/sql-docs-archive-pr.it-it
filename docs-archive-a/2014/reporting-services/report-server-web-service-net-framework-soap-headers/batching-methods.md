---
title: Metodi di invio in batch | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- methods [Reporting Services], batches
- BatchHeader SOAP header
- Web service [Reporting Services], methods
- Report Server Web service, batching
- batches [Reporting Services]
- XML Web service [Reporting Services], methods
- locking [Reporting Services]
- multiple Web service methods
ms.assetid: 86435534-c9fe-4b49-b88c-7fb6d21976b0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c778da186fdbbfaed17b9635d9ca7309a369552b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636548"
---
# <a name="batching-methods"></a><span data-ttu-id="d77b8-102">Metodi di invio in batch</span><span class="sxs-lookup"><span data-stu-id="d77b8-102">Batching Methods</span></span>
  <span data-ttu-id="d77b8-103">L'utilizzo di intestazioni SOAP in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] consente di includere più metodi del servizio Web in una singola operazione.</span><span class="sxs-lookup"><span data-stu-id="d77b8-103">The use of SOAP headers in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] enables you to include multiple Web service methods in a single operation.</span></span> <span data-ttu-id="d77b8-104">I metodi vengono eseguiti nell'ambito di un'unica transazione di database, nell'ordine con cui vengono chiamati.</span><span class="sxs-lookup"><span data-stu-id="d77b8-104">Methods run within the scope of a single database transaction, in the order in which they are called.</span></span>  
  
 <span data-ttu-id="d77b8-105">La possibilità di eseguire il rollback rappresenta un vantaggio dell'utilizzo di operazioni batch con più metodi.</span><span class="sxs-lookup"><span data-stu-id="d77b8-105">Rollback is one advantage of using multiple-method batch operations.</span></span> <span data-ttu-id="d77b8-106">Se si verifica un errore in alcune delle chiamate ai metodi mentre un batch è in esecuzione, il server di report arresta l'esecuzione del batch ed esegue il rollback di qualsiasi operazione precedente.</span><span class="sxs-lookup"><span data-stu-id="d77b8-106">If an error occurs on any of the method calls while a batch is running, the report server stops running the batch and rolls back any previous operations.</span></span> <span data-ttu-id="d77b8-107">Questo è utile quando una chiamata al metodo dipende dal corretto completamento delle altre chiamate ai metodi nel batch.</span><span class="sxs-lookup"><span data-stu-id="d77b8-107">This is useful when a method call depends on the successful completion of other method calls in that batch.</span></span>  
  
 <span data-ttu-id="d77b8-108">Il servizio Web non fornisce una semantica di blocco per le operazioni batch con più metodi.</span><span class="sxs-lookup"><span data-stu-id="d77b8-108">The Web service does not provide locking semantics for multiple-method batch operations.</span></span> <span data-ttu-id="d77b8-109">Le righe nel database del server di report non vengono bloccate per l'aggiornamento fino a quando il messaggio non viene inviato al server e non viene chiamato il comando Execute.</span><span class="sxs-lookup"><span data-stu-id="d77b8-109">Rows in the report server database are not locked for updating until the message is sent to the server and the Execute command is called.</span></span>  
  
 <span data-ttu-id="d77b8-110">Non vengono inoltre eseguiti controlli della concorrenza per garantire che il database non sia stato modificato dopo l'ultima lettura dei dati.</span><span class="sxs-lookup"><span data-stu-id="d77b8-110">There are also no concurrency controls to guarantee that the database has not changed since the data was last read.</span></span> <span data-ttu-id="d77b8-111">Se due client modificano lo stesso elemento, l'ultimo aggiornamento ha esito positivo se i parametri sono ancora validi (ad esempio se l'elemento non è stato rinominato).</span><span class="sxs-lookup"><span data-stu-id="d77b8-111">If two clients modify the same item, the last update succeeds if the parameters are still valid (for example, the item has not been renamed).</span></span>  
  
 <span data-ttu-id="d77b8-112">Nell'esempio seguente il metodo <xref:ReportService2005.ReportingService2005.CreateFolder%2A> viene chiamato tre volte e queste chiamate vengono eseguite come singolo batch.</span><span class="sxs-lookup"><span data-stu-id="d77b8-112">The following example calls the <xref:ReportService2005.ReportingService2005.CreateFolder%2A> method three times and runs these calls as a single batch.</span></span> <span data-ttu-id="d77b8-113">Se una delle chiamate a <xref:ReportService2005.ReportingService2005.CreateFolder%2A> ha esito negativo, l'intero batch viene annullato.</span><span class="sxs-lookup"><span data-stu-id="d77b8-113">If any of the calls to <xref:ReportService2005.ReportingService2005.CreateFolder%2A> fail, the entire batch is canceled.</span></span>  
  
```vb  
Imports System  
Imports System.Web.Services.Protocols  
Imports myNamespace.MyReferenceName  
  
Class Sample  
    Sub Main(args() As String)  
        Dim rs As New ReportingService2005()  
        rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
      ' Set the base Web service URL of the source server  
      rs.Url = "http://<Server Name>/reportserver/ReportService2005.asmx"  
  
        Dim bh As New BatchHeader()  
  
        bh.BatchId = service.CreateBatch()  
        rs.BatchHeaderValue = bh  
        rs.CreateFolder("New Folder1", "/", Nothing)  
        rs.CreateFolder("New Folder2", "/", Nothing)  
        rs.CreateFolder("New Folder3", "/", Nothing)  
  
        Console.WriteLine("Creating folders...")  
        rs.BatchHeaderValue = bh  
        rs.ExecuteBatch()  
        Console.WriteLine("Folders created successfully.")  
  
        rs.BatchHeaderValue = Nothing  
    End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Web.Services.Protocols;   
using myNamespace.MyReferenceName;  
  
class Sample  
{  
    static void Main(string[] args)  
    {  
        ReportingService2005 rs = new ReportingService2005();  
        rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
      // Set the base Web service URL of the source server  
      rs.Url = "http://<Server Name>/reportserver/ReportService2005.asmx"  
  
        BatchHeader bh = new BatchHeader();  
  
        bh1.BatchID = service.CreateBatch();  
        rs.BatchHeaderValue = bh;  
        rs.CreateFolder("New Folder1", "/", null);  
        rs.CreateFolder("New Folder2", "/", null);  
        rs.CreateFolder("New Folder3", "/", null);  
  
        Console.WriteLine("Creating folders...");  
        rs.BatchHeaderValue = bh1;  
        rs.ExecuteBatch();  
        Console.WriteLine("Folders created successfully.");  
  
        rs.BatchHeaderValue = null;  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="d77b8-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d77b8-114">See Also</span></span>  
 <xref:ReportService2005.ReportingService2005.CancelBatch%2A>   
 <xref:ReportService2005.ReportingService2005.CreateBatch%2A>   
 <span data-ttu-id="d77b8-115">[Riferimento tecnico &#40;SSRS&#41;](../technical-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d77b8-115">[Technical Reference &#40;SSRS&#41;](../technical-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="d77b8-116">Utilizzo di intestazioni SOAP di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d77b8-116">Using Reporting Services SOAP Headers</span></span>](using-reporting-services-soap-headers.md)  
  
  
