---
title: Using Reporting Services SOAP Headers (Uso di intestazioni SOAP di Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], SOAP
- Report Server Web service, SOAP
- SOAP headers [Reporting Services]
- SOAP [Reporting Services], headers
- XML Web service [Reporting Services], SOAP
ms.assetid: 306d2c06-a25a-40f8-8a35-13dd32e8841e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f48be183398d4d441b5781c9f9467178c3011e32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717370"
---
# <a name="using-reporting-services-soap-headers"></a><span data-ttu-id="dfc4b-102">Utilizzo di intestazioni SOAP di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="dfc4b-102">Using Reporting Services SOAP Headers</span></span>
  <span data-ttu-id="dfc4b-103">La comunicazione con un metodo di servizio Web utilizzando SOAP segue un formato standard.</span><span class="sxs-lookup"><span data-stu-id="dfc4b-103">Communication with a Web service method using SOAP follows a standard format.</span></span> <span data-ttu-id="dfc4b-104">Fanno parte di questo formato i dati codificati in un documento XML.</span><span class="sxs-lookup"><span data-stu-id="dfc4b-104">Part of this format is the data that is encoded in an XML document.</span></span> <span data-ttu-id="dfc4b-105">Il documento XML è costituito da un elemento **Envelope** radice che a sua volta è costituito da un elemento **Body** obbligatorio e da un elemento **Header** facoltativo.</span><span class="sxs-lookup"><span data-stu-id="dfc4b-105">The XML document consists of a root **Envelope** element, which in turn consists of a required **Body** element and an optional **Header** element.</span></span> <span data-ttu-id="dfc4b-106">L'elemento **Body** contiene i dati specifici del messaggio.</span><span class="sxs-lookup"><span data-stu-id="dfc4b-106">The **Body** element contains the data specific to the message.</span></span> <span data-ttu-id="dfc4b-107">L'elemento **Header** facoltativo può contenere informazioni aggiuntive non direttamente correlate al messaggio specifico.</span><span class="sxs-lookup"><span data-stu-id="dfc4b-107">The optional **Header** element can contain additional information not directly related to the particular message.</span></span> <span data-ttu-id="dfc4b-108">Ogni elemento figlio dell'elemento**Header** è definito intestazione SOAP.</span><span class="sxs-lookup"><span data-stu-id="dfc4b-108">Each child element of the **Header** element is called a SOAP header.</span></span>  
  
 <span data-ttu-id="dfc4b-109">Sebbene le intestazioni SOAP possano includere dati correlati al messaggio, contengono in genere informazioni elaborate dall'infrastruttura del server Web.</span><span class="sxs-lookup"><span data-stu-id="dfc4b-109">Although the SOAP headers can contain data related to the message, they typically contain information processed by the Web server infrastructure.</span></span>  
  
 <span data-ttu-id="dfc4b-110">l servizio Web ReportServer definisce diverse classi da utilizzare nell'intestazione SOAP, ovvero <xref:ReportService2005.BatchHeader>, <xref:ReportService2010.ItemNamespaceHeader>, <xref:ReportService2010.ServerInfoHeader>, <xref:ReportService2010.TrustedUserHeader> e <xref:ReportExecution2005.ExecutionHeader>.</span><span class="sxs-lookup"><span data-stu-id="dfc4b-110">The Report Server Web services define several classes for use in the SOAP header: <xref:ReportService2005.BatchHeader>, <xref:ReportService2010.ItemNamespaceHeader>, <xref:ReportService2010.ServerInfoHeader>, <xref:ReportService2010.TrustedUserHeader>, and <xref:ReportExecution2005.ExecutionHeader>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dfc4b-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="dfc4b-111">In This Section</span></span>  
  
|<span data-ttu-id="dfc4b-112">Argomento</span><span class="sxs-lookup"><span data-stu-id="dfc4b-112">Topic</span></span>|<span data-ttu-id="dfc4b-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dfc4b-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="dfc4b-114">Metodi di invio in batch</span><span class="sxs-lookup"><span data-stu-id="dfc4b-114">Batching Methods</span></span>](batching-methods.md)|<span data-ttu-id="dfc4b-115">Descrive come unire in batch più operazioni in una singola transazione utilizzando <xref:ReportService2005.BatchHeader>.</span><span class="sxs-lookup"><span data-stu-id="dfc4b-115">Describes how to batch multiple operations into a single transaction using <xref:ReportService2005.BatchHeader>.</span></span>|  
|[<span data-ttu-id="dfc4b-116">Identificazione dello stato di esecuzione</span><span class="sxs-lookup"><span data-stu-id="dfc4b-116">Identifying Execution State</span></span>](identifying-execution-state.md)|<span data-ttu-id="dfc4b-117">Descrive come gestire lo stato della sessione in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] tramite **SessionHeader**.</span><span class="sxs-lookup"><span data-stu-id="dfc4b-117">Describes how to manage session state in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] using **SessionHeader**.</span></span>|  
|[<span data-ttu-id="dfc4b-118">Impostazione dello spazio dei nomi degli elementi per il metodo GetProperties</span><span class="sxs-lookup"><span data-stu-id="dfc4b-118">Setting the Item Namespace for the GetProperties Method</span></span>](setting-the-item-namespace-for-the-getproperties-method.md)|<span data-ttu-id="dfc4b-119">Descrive come recuperare le proprietà in base al percorso o all'ID di un elemento tramite il metodo <xref:ReportService2010.ReportingService2010.GetProperties%2A> e l'intestazione SOAP <xref:ReportService2010.ItemNamespaceHeader>.</span><span class="sxs-lookup"><span data-stu-id="dfc4b-119">Describes how to retrieve properties based on either the path or the ID of an item by using the <xref:ReportService2010.ReportingService2010.GetProperties%2A> method and the <xref:ReportService2010.ItemNamespaceHeader> SOAP header.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dfc4b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dfc4b-120">See Also</span></span>  
 <span data-ttu-id="dfc4b-121">[Compilazione di applicazioni tramite servizio Web e .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="dfc4b-121">[Building Applications Using the Web Service and the .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="dfc4b-122">Riferimento tecnico &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="dfc4b-122">Technical Reference &#40;SSRS&#41;</span></span>](../technical-reference-ssrs.md)  
  
  
