---
title: Using the Detail Property to Handle Specific Errors | (Uso della proprietà Detail per la gestione di errori specifici) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- exceptions [Reporting Services], Detail property
- Detail property
- InnerText property
ms.assetid: 4392633d-b46b-41e6-bc12-efb64e166704
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4f8ac62dc381d8f665a44fc0897ba1f4215aa8e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719536"
---
# <a name="using-the-detail-property-to-handle-specific-errors"></a><span data-ttu-id="9d51e-102">Utilizzo della proprietà Detail per la gestione di errori specifici</span><span class="sxs-lookup"><span data-stu-id="9d51e-102">Using the Detail Property to Handle Specific Errors</span></span>
  <span data-ttu-id="9d51e-103">Per classificare ulteriormente le eccezioni, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] restituisce informazioni aggiuntive sull'errore nella proprietà **InnerText** degli elementi figlio nella proprietà **Detail** dell'eccezione SOAP.</span><span class="sxs-lookup"><span data-stu-id="9d51e-103">To further classify exceptions, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] returns additional error information in the **InnerText** property of the child elements in the SOAP exception's **Detail** property.</span></span> <span data-ttu-id="9d51e-104">Poiché la proprietà **Detail** è un oggetto **XmlNode**, è possibile accedere al testo interno dell'elemento figlio **Message** usando il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="9d51e-104">Because the **Detail** property is an **XmlNode** object, you can access the inner text of the **Message** child element using the following code.</span></span>  
  
 <span data-ttu-id="9d51e-105">Per un elenco di tutti gli elementi figlio disponibili inclusi nella proprietà **Detail**, vedere [Detail Property](../soapexception-class/detail-property.md).</span><span class="sxs-lookup"><span data-stu-id="9d51e-105">For a list of all of the available child elements contained in the **Detail** property, see [Detail Property](../soapexception-class/detail-property.md).</span></span> <span data-ttu-id="9d51e-106">Per ulteriori informazioni, vedere la sezione relativa alla proprietà Detail nella [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] documentazione di SDK.</span><span class="sxs-lookup"><span data-stu-id="9d51e-106">For more information, see "Detail Property" in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
```vb  
Try  
' Code for accessing the report server  
Catch ex As SoapException  
   ' The exception is a SOAP exception, so use  
   ' the Detail property's Message element.  
   Console.WriteLine(ex.Detail("Message").InnerXml)  
End Try  
```  
  
```csharp  
try  
{  
   // Code for accessing the report server  
}  
catch (SoapException ex)  
{  
   // The exception is a SOAP exception, so use  
   // the Detail property's Message element.  
   Console.WriteLine(ex.Detail["Message"].InnerXml);  
}  
```  
  
```vb  
Try  
' Code for accessing the report server  
Catch ex As SoapException  
   If ex.Detail("ErrorCode").InnerXml = "rsInvalidItemName" Then  
   End If ' Perform an action based on the specific error code  
End Try  
```  
  
```csharp  
try  
{  
   // Code for accessing the report server  
}  
catch (SoapException ex)  
{  
   if (ex.Detail["ErrorCode"].InnerXml == "rsInvalidItemName")  
   {  
      // Perform an action based on the specific error code  
   }  
}  
```  
  
 <span data-ttu-id="9d51e-107">Tramite la riga di codice seguente viene scritto il codice di errore specifico restituito nell'eccezione SOAP alla console.</span><span class="sxs-lookup"><span data-stu-id="9d51e-107">The following line of code writes the specific error code being returned in the SOAP Exception to the console.</span></span> <span data-ttu-id="9d51e-108">È anche possibile valutare il codice di errore ed eseguire azioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="9d51e-108">You could also evaluate the error code and perform specific actions.</span></span>  
  
```vb  
Console.WriteLine(ex.Detail("ErrorCode").InnerXml)  
```  
  
```csharp  
Console.WriteLine(ex.Detail["ErrorCode"].InnerXml);  
```  
  
## <a name="see-also"></a><span data-ttu-id="9d51e-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d51e-109">See Also</span></span>  
 <span data-ttu-id="9d51e-110">[Introduzione alla gestione delle eccezioni in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="9d51e-110">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 <span data-ttu-id="9d51e-111">[Reporting Services classe SoapException](../soapexception-class/reporting-services-soapexception-class.md) </span><span class="sxs-lookup"><span data-stu-id="9d51e-111">[Reporting Services SoapException Class](../soapexception-class/reporting-services-soapexception-class.md) </span></span>  
 [<span data-ttu-id="9d51e-112">Tabella degli errori SoapException</span><span class="sxs-lookup"><span data-stu-id="9d51e-112">SoapException Errors Table</span></span>](../soapexception-class/soapexception-errors-table.md)  
  
  
