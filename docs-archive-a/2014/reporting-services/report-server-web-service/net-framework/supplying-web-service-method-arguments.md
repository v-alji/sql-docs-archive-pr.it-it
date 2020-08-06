---
title: Impostazione degli argomenti dei metodi del servizio Web | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Report Server Web service, methods
- Web service [Reporting Services], methods
- methods [Reporting Services], arguments
- XML Web service [Reporting Services], methods
ms.assetid: f7b9ca05-fc4c-4b30-8e5d-172dd0f4a832
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3ef5188934628589751fe92d1839da0efb265766
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723371"
---
# <a name="supplying-web-service-method-arguments"></a><span data-ttu-id="8199e-102">Impostazione degli argomenti dei metodi del servizio Web</span><span class="sxs-lookup"><span data-stu-id="8199e-102">Supplying Web Service Method Arguments</span></span>
  <span data-ttu-id="8199e-103">Un metodo del servizio Web ReportServer invia una richiesta al servizio a un URL specifico utilizzando SOAP tramite HTTP.</span><span class="sxs-lookup"><span data-stu-id="8199e-103">A Report Server Web service method sends a request to the service at a given URL using SOAP over HTTP.</span></span> <span data-ttu-id="8199e-104">Il servizio riceve la richiesta, la elabora e restituisce una risposta.</span><span class="sxs-lookup"><span data-stu-id="8199e-104">The service receives the request, processes it, and then returns a response.</span></span> <span data-ttu-id="8199e-105">Queste richieste e risposte hanno il formato di documenti XML.</span><span class="sxs-lookup"><span data-stu-id="8199e-105">These requests and responses are in the form of XML documents.</span></span>  
  
## <a name="optional-parameters"></a><span data-ttu-id="8199e-106">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="8199e-106">Optional Parameters</span></span>  
 <span data-ttu-id="8199e-107">In alcuni casi, un metodo del servizio Web può avere parametri di input facoltativi.</span><span class="sxs-lookup"><span data-stu-id="8199e-107">In some cases, a Web service method can have optional input parameters.</span></span> <span data-ttu-id="8199e-108">Anche se un parametro di input per un metodo del servizio Web è facoltativo, è comunque necessario includerlo e impostare il relativo valore su `null` (`Nothing` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="8199e-108">Even if an input parameter for a Web service method is optional, you must still include it and set the parameter value to `null` (`Nothing` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span></span> <span data-ttu-id="8199e-109">Impostando il valore di un parametro su `null` si imposta il valore dell'elemento per tale parametro nella richiesta SOAP su `null`.</span><span class="sxs-lookup"><span data-stu-id="8199e-109">Setting a parameter value to `null` sets the element value for that parameter in the SOAP request to `null`.</span></span>  
  
 <span data-ttu-id="8199e-110">Nell'esempio seguente viene utilizzato il metodo <xref:ReportService2010.ReportingService2010.CreateFolder%2A> per creare una nuova cartella denominata Product Sales nella cartella Sales.</span><span class="sxs-lookup"><span data-stu-id="8199e-110">The following example uses the <xref:ReportService2010.ReportingService2010.CreateFolder%2A> method to create a new folder named Product Sales in the Sales folder.</span></span> <span data-ttu-id="8199e-111">Fornendo un valore `null` per le proprietà della cartella, non vengono fornite proprietà specifiche dell'utente per la cartella:</span><span class="sxs-lookup"><span data-stu-id="8199e-111">By supplying a `null` value for the folder properties, no user-specific properties are supplied for the folder:</span></span>  
  
```  
// C#  
rs.CreateFolder("Product Sales", "/Sales", null);  
```  
  
## <a name="complex-data-types"></a><span data-ttu-id="8199e-112">Tipi di dati complessi</span><span class="sxs-lookup"><span data-stu-id="8199e-112">Complex Data Types</span></span>  
 <span data-ttu-id="8199e-113">La classe principale del servizio Web ReportServer è <xref:ReportService2010.ReportingService2010> e viene utilizzata per richiamare le operazioni SOAP o i metodi Web della classe proxy.</span><span class="sxs-lookup"><span data-stu-id="8199e-113">The core class of the Report Server Web service is <xref:ReportService2010.ReportingService2010>, which you use to invoke the SOAP operations or Web methods of the proxy class.</span></span> <span data-ttu-id="8199e-114">Per supportare questa classe e i relativi metodi, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] include tipi di dati complessi definiti dall'utente specifici dei parametri di input e output dei metodi del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="8199e-114">To support this class and its methods, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] includes user-defined, complex data types that are specific to the input and output parameters of the Web service methods.</span></span> <span data-ttu-id="8199e-115">Questi tipi di dati complessi fanno parte della classe proxy generata, che è possibile usare quando si sviluppa nell' [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] ambiente.</span><span class="sxs-lookup"><span data-stu-id="8199e-115">These complex data types are part of the generated proxy class, which you can use when developing in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] environment.</span></span>  
  
 <span data-ttu-id="8199e-116">Quando si genera una classe proxy, i tipi di dati complessi definiti nel file WSDL vengono rappresentati dalle classi proxy, che includono proprietà che corrispondono ai vari elementi SOAP dei tipi di dati complessi.</span><span class="sxs-lookup"><span data-stu-id="8199e-116">When you generate a proxy class, the complex data types that are defined in the WSDL file are represented by the classes of the proxy, which include properties that correspond to the various SOAP elements of the complex data types.</span></span> <span data-ttu-id="8199e-117">Le sequenze di questi tipi di dati diventano matrici di oggetti che è possibile enumerare nel codice.</span><span class="sxs-lookup"><span data-stu-id="8199e-117">Sequences of these data types become arrays of objects that you can enumerate through in your code.</span></span> <span data-ttu-id="8199e-118">In questo modo, non è più necessario utilizzare direttamente le strutture XML inviate nei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="8199e-118">This eliminates the need to work directly with the XML structures sent in SOAP messages.</span></span> <span data-ttu-id="8199e-119">La conversione viene gestita da [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8199e-119">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] handles that translation for you.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8199e-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8199e-120">See Also</span></span>  
 <span data-ttu-id="8199e-121">[Compilazione di applicazioni tramite servizio Web e .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="8199e-121">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="8199e-122">[Servizio Web ReportServer](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="8199e-122">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 [<span data-ttu-id="8199e-123">Riferimento tecnico &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8199e-123">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
