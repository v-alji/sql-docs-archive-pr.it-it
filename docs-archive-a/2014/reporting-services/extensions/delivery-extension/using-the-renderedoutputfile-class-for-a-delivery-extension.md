---
title: Using the RenderedOutputFile Class for a Delivery Extension (Uso della classe RenderedOutputFile per un'estensione per il recapito) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- RenderedOutputFile class
- data streams [Reporting Services]
- delivery extensions [Reporting Services], data streams
ms.assetid: 8b591801-42d5-49fa-b710-bf7e6917accf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1dcbf250a367326e5cad528384e533a9ac9d945b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638285"
---
# <a name="using-the-renderedoutputfile-class-for-a-delivery-extension"></a><span data-ttu-id="6aba8-102">Utilizzo della classe RenderedOutputFile per un'estensione per il recapito</span><span class="sxs-lookup"><span data-stu-id="6aba8-102">Using the RenderedOutputFile Class for a Delivery Extension</span></span>
  <span data-ttu-id="6aba8-103">La classe <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> rappresenta un flusso di dati e le informazioni sulle proprietà associate al flusso.</span><span class="sxs-lookup"><span data-stu-id="6aba8-103">The <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> class represents a data stream and information about the data stream's associated properties.</span></span> <span data-ttu-id="6aba8-104">La proprietà **Data** della classe <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> viene usata per rappresentare un report visualizzabile o una risorsa del report come un oggetto **Stream**.</span><span class="sxs-lookup"><span data-stu-id="6aba8-104">The **Data** property of the <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> class is used to represent a rendered report or report resource as a **Stream** object.</span></span>  
  
 <span data-ttu-id="6aba8-105">Il metodo <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> dell'oggetto **Report** restituisce una matrice di uno o più oggetti <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> che insieme costituiscono un singolo report visualizzabile.</span><span class="sxs-lookup"><span data-stu-id="6aba8-105">The <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> method of the **Report** object returns an array of one or more <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> objects that together constitute a single rendered report.</span></span> <span data-ttu-id="6aba8-106">Il primo oggetto <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> è il report visualizzabile.</span><span class="sxs-lookup"><span data-stu-id="6aba8-106">The first <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object is the rendered report.</span></span> <span data-ttu-id="6aba8-107">Tutti gli altri oggetti <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> sono risorse che devono essere recapitate insieme ai dati del report (ad esempio, un file HTML e le immagini associate).</span><span class="sxs-lookup"><span data-stu-id="6aba8-107">Any other <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> objects are resources that must be delivered along with the report data (for example, an HTML file and associated images).</span></span> <span data-ttu-id="6aba8-108">Le estensioni per il rendering a flusso singolo (IMAGE, PDF, MHTML ed EXCEL) restituiscono solo un oggetto <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> nella matrice.</span><span class="sxs-lookup"><span data-stu-id="6aba8-108">Rendering extensions that are single-stream rendering extensions (IMAGE, PDF, MHTML, and EXCEL) return only one <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object in the array.</span></span>  
  
 <span data-ttu-id="6aba8-109">Per un esempio su come usare la classe <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile>, vedere [ Esempi del prodotto Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="6aba8-109">For an example of how to use the <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> class, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aba8-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6aba8-110">See Also</span></span>  
 <span data-ttu-id="6aba8-111">[Implementazione di un'estensione per il recapito](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="6aba8-111">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="6aba8-112">Libreria di estensioni di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="6aba8-112">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
