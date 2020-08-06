---
title: Using the Setting Class for a Delivery Extension (Uso della classe Setting per un'estensione per il recapito) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery extensions [Reporting Services], report information
- Report class
ms.assetid: 1145ac63-eafd-452a-82af-16f85b1676dd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a3f750c2383253636db255cbe9f1ce0ee676a9d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638282"
---
# <a name="using-the-report-class-for-a-delivery-extension"></a><span data-ttu-id="c12d8-102">Utilizzo della classe Report per un'estensione per il recapito</span><span class="sxs-lookup"><span data-stu-id="c12d8-102">Using the Report Class for a Delivery Extension</span></span>
  <span data-ttu-id="c12d8-103">La classe <xref:Microsoft.ReportingServices.Interfaces.Report> rappresenta un report nel database del server di report.</span><span class="sxs-lookup"><span data-stu-id="c12d8-103">The <xref:Microsoft.ReportingServices.Interfaces.Report> class represents a report in the report server database.</span></span> <span data-ttu-id="c12d8-104">Qualsiasi sottoscrizione è associata a un report specifico.</span><span class="sxs-lookup"><span data-stu-id="c12d8-104">Any subscription is associated with a specific report.</span></span> <span data-ttu-id="c12d8-105">Il report è incluso nella notifica.</span><span class="sxs-lookup"><span data-stu-id="c12d8-105">The report is contained in the notification.</span></span> <span data-ttu-id="c12d8-106">L'estensione per il recapito può utilizzare l'oggetto <xref:Microsoft.ReportingServices.Interfaces.Report> incluso nella notifica per eseguire il rendering del report.</span><span class="sxs-lookup"><span data-stu-id="c12d8-106">Your delivery extension can use the <xref:Microsoft.ReportingServices.Interfaces.Report> object that is part of the notification to render the report.</span></span> <span data-ttu-id="c12d8-107">L'oggetto <xref:Microsoft.ReportingServices.Interfaces.Report> contiene inoltre proprietà specifiche del report, ad esempio l'URL del report nel server di report e il nome del report.</span><span class="sxs-lookup"><span data-stu-id="c12d8-107">The <xref:Microsoft.ReportingServices.Interfaces.Report> object also contains report-specific properties, such as the URL to the report on the report server and the name of the report.</span></span> <span data-ttu-id="c12d8-108">Tutte queste proprietà possono essere utilizzate come parte del provider di recapito.</span><span class="sxs-lookup"><span data-stu-id="c12d8-108">These properties can all be used as part of your delivery provider.</span></span>  
  
 <span data-ttu-id="c12d8-109">Per il rendering di un report, è possibile utilizzare il metodo <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> della classe <xref:Microsoft.ReportingServices.Interfaces.Report>.</span><span class="sxs-lookup"><span data-stu-id="c12d8-109">The <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> method of the <xref:Microsoft.ReportingServices.Interfaces.Report> class can be used to render a report.</span></span> <span data-ttu-id="c12d8-110">Il metodo <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> restituisce una matrice di uno o più oggetti <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> che comprendono un singolo report visualizzabile.</span><span class="sxs-lookup"><span data-stu-id="c12d8-110">The <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> method returns an array of one or more <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> objects that together comprise a single rendered report.</span></span> <span data-ttu-id="c12d8-111">Il primo oggetto <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> è il report visualizzabile.</span><span class="sxs-lookup"><span data-stu-id="c12d8-111">The first <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object is the rendered report.</span></span> <span data-ttu-id="c12d8-112">Tutti gli altri oggetti <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> sono risorse che devono essere recapitate insieme ai dati del report (ad esempio, un file HTML e le immagini associate).</span><span class="sxs-lookup"><span data-stu-id="c12d8-112">Any other <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> objects are resources that must be delivered along with the report data (for example, an HTML file and associated images).</span></span> <span data-ttu-id="c12d8-113">Le estensioni per il rendering a flusso singolo (IMAGE, PDF, MHTML ed Excel) restituiscono solo un oggetto <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> nella matrice.</span><span class="sxs-lookup"><span data-stu-id="c12d8-113">Rendering extensions that are single-stream rendering extensions (IMAGE, PDF, MHTML, and Excel) return only one <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object in the array.</span></span>  
  
 <span data-ttu-id="c12d8-114">L'oggetto <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> che contiene il flusso del report può essere incluso come parte di un recapito.</span><span class="sxs-lookup"><span data-stu-id="c12d8-114">The <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object, which contains the report stream, can be included as part of a delivery.</span></span>  
  
 <span data-ttu-id="c12d8-115">Per un esempio su come usare la classe <xref:Microsoft.ReportingServices.Interfaces.Report>, vedere [Esempi del prodotto SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889)</span><span class="sxs-lookup"><span data-stu-id="c12d8-115">For an example of how to use the <xref:Microsoft.ReportingServices.Interfaces.Report> class, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c12d8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c12d8-116">See Also</span></span>  
 <span data-ttu-id="c12d8-117">[Implementazione di un'estensione per il recapito](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="c12d8-117">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 <span data-ttu-id="c12d8-118">[Libreria di estensioni di Reporting Services](../reporting-services-extension-library.md) </span><span class="sxs-lookup"><span data-stu-id="c12d8-118">[Reporting Services Extension Library](../reporting-services-extension-library.md) </span></span>  
 [<span data-ttu-id="c12d8-119">Uso della classe RenderedOutputFile per un'estensione per il recapito</span><span class="sxs-lookup"><span data-stu-id="c12d8-119">Using the RenderedOutputFile Class for a Delivery Extension</span></span>](using-the-renderedoutputfile-class-for-a-delivery-extension.md)  
  
  
