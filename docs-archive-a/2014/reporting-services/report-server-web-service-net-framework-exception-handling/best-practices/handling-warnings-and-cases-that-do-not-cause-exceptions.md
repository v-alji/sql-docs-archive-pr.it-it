---
title: Gestione di avvisi e casi che non causano eccezioni | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- exceptions [Reporting Services], warnings that don't cause
- warnings [Reporting Services]
ms.assetid: 475c0713-6265-44e7-9ebc-ebdd1b89e0af
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 88d3daf63cf5f04975a2941d0634f357ce81456c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717381"
---
# <a name="handling-warnings-and-cases-that-do-not-cause-exceptions"></a><span data-ttu-id="bf9e7-102">Gestione di avvisi e casi che non provocano eccezioni</span><span class="sxs-lookup"><span data-stu-id="bf9e7-102">Handling Warnings and Cases That Do Not Cause Exceptions</span></span>
  <span data-ttu-id="bf9e7-103">In [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] non vengono generate eccezioni per gli avvisi e per determinati errori.</span><span class="sxs-lookup"><span data-stu-id="bf9e7-103">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] does not throw exceptions for warnings and certain errors.</span></span> <span data-ttu-id="bf9e7-104">Quando, ad esempio, si utilizza il metodo <xref:ReportService2010.ReportingService2010.CreateCatalogItem%2A> per pubblicare un nuovo report in un server di report, gli avvisi vengono restituiti come matrice di oggetti <xref:ReportService2010.Warning>.</span><span class="sxs-lookup"><span data-stu-id="bf9e7-104">For example, when you use the <xref:ReportService2010.ReportingService2010.CreateCatalogItem%2A> method to publish a new report to a report server, any warnings that occur are returned as an array of <xref:ReportService2010.Warning> objects.</span></span> <span data-ttu-id="bf9e7-105">Questi avvisi devono essere gestiti e visualizzati in modo che sia possibile eseguire l'azione appropriata.</span><span class="sxs-lookup"><span data-stu-id="bf9e7-105">These warnings should be handled and displayed so that appropriate action can be taken.</span></span>  
  
```vb  
Try  
   rs.CreateCatalogItem(name, parentFolder, False, definition, Nothing, warnings)  
  
   If Not (warnings.Length = 0) Then  
      Dim warning As Warning  
      For Each warning In warnings  
         Console.WriteLine(warning.Message)  
      Next warning  
   Else  
      Console.WriteLine("Report {0} created successfully with no warnings", name)  
   End If  
  
Catch ex As SoapException  
   Console.WriteLine(ex.Detail("Message").InnerXml)  
End Try  
```  
  
```csharp  
try  
{  
   rs.CreateCatalogItem("Report", name, parentFolder, false, definition, null, out warnings);  
  
   if (warnings.Length != 0)  
   {  
      foreach (Warning warning in warnings)  
      {  
         Console.WriteLine(warning.Message);  
      }  
   }  
   else  
      Console.WriteLine("Report {0} created successfully with no warnings", name);  
}  
  
catch (SoapException ex)  
{  
   Console.WriteLine(ex.Detail["Message"].InnerXml);  
}  
```  
  
 <span data-ttu-id="bf9e7-106">Un altro modo per gestire gli errori consiste nel valutare i valori restituiti di determinati metodi.</span><span class="sxs-lookup"><span data-stu-id="bf9e7-106">Another way to handle errors is to evaluate the return values of certain methods.</span></span> <span data-ttu-id="bf9e7-107">È ad esempio possibile utilizzare il metodo <xref:ReportService2010.ReportingService2010.FindItems%2A> per cercare elementi specifici nel database del server di report.</span><span class="sxs-lookup"><span data-stu-id="bf9e7-107">For example, the <xref:ReportService2010.ReportingService2010.FindItems%2A> method can be used to search for specific items in the report server database.</span></span> <span data-ttu-id="bf9e7-108">Se non vengono trovati elementi corrispondenti ai criteri di ricerca, viene restituita una matrice Null di oggetti <xref:ReportService2010.CatalogItem>.</span><span class="sxs-lookup"><span data-stu-id="bf9e7-108">If no items are found that match the search criteria, a null array of <xref:ReportService2010.CatalogItem> objects is returned.</span></span> <span data-ttu-id="bf9e7-109">È necessario valutare la matrice, verificare la presenza di `null` e comunicare all'utente se non sono stati trovati elementi.</span><span class="sxs-lookup"><span data-stu-id="bf9e7-109">You should evaluate the array, check for `null`, and let the user know if no items were found.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf9e7-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf9e7-110">See Also</span></span>  
 <xref:ReportService2010.CatalogItem>   
 <span data-ttu-id="bf9e7-111">[Introduzione alla gestione delle eccezioni in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="bf9e7-111">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="bf9e7-112">Classe SoapException di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="bf9e7-112">Reporting Services SoapException Class</span></span>](../soapexception-class/reporting-services-soapexception-class.md)  
  
  
