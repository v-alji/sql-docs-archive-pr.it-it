---
title: Origine OData | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.ODATASOURCE.F1
ms.assetid: cc9003c9-638e-432b-867e-e949d50cec90
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 98b14ef034597f6098f70386ca41c1b90be86500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724819"
---
# <a name="odata-source"></a><span data-ttu-id="19a5b-102">Origine OData</span><span class="sxs-lookup"><span data-stu-id="19a5b-102">OData Source</span></span>
  <span data-ttu-id="19a5b-103">Utilizzare il componente di origine OData in un pacchetto SSIS per utilizzare i dati dai servizi Protocollo OData (Open Data).</span><span class="sxs-lookup"><span data-stu-id="19a5b-103">You use the OData Source component in an SSIS package to consume data from Open Data Protocol (OData) services.</span></span> <span data-ttu-id="19a5b-104">Il componente supporta i formati dati JSON e ATOM, nonché i protocolli v3 e v2 OData.</span><span class="sxs-lookup"><span data-stu-id="19a5b-104">The component supports the OData v2 and v3 protocols, as well as the ATOM and JSON data formats.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="19a5b-105">L'origine OData può essere utilizzata per eseguire letture da elenchi SharePoint.</span><span class="sxs-lookup"><span data-stu-id="19a5b-105">The OData Source can be used to read from SharePoint lists.</span></span> <span data-ttu-id="19a5b-106">Per visualizzare tutti gli elenchi nel server SharePoint, usare l'URL seguente: http:// \<server> /_vti_bin/listdata.svc.</span><span class="sxs-lookup"><span data-stu-id="19a5b-106">To see all lists on your SharePoint server, use the following URL: http://\<server>/_vti_bin/ListData.svc.</span></span> <span data-ttu-id="19a5b-107">Per ulteriori informazioni sulle convenzioni per l'URL di SharePoint, vedere la pagina relativa all' [interfaccia REST di SharePoint Foundation](https://msdn.microsoft.com/library/ff521587.aspx).</span><span class="sxs-lookup"><span data-stu-id="19a5b-107">For more information about SharePoint URL conventions, see [SharePoint Foundation REST Interface](https://msdn.microsoft.com/library/ff521587.aspx).</span></span>  
  
## <a name="odata-format"></a><span data-ttu-id="19a5b-108">Formato OData</span><span class="sxs-lookup"><span data-stu-id="19a5b-108">OData Format</span></span>  
 <span data-ttu-id="19a5b-109">I risultati restituiti dalla maggior parte dei servizi OData sono in più formati.</span><span class="sxs-lookup"><span data-stu-id="19a5b-109">Most OData services return results in multiple formats.</span></span> <span data-ttu-id="19a5b-110">È possibile specificare il formato del set di risultati utilizzando l'opzione query $format.</span><span class="sxs-lookup"><span data-stu-id="19a5b-110">You can specify the format of the result set by using the $format query option.</span></span> <span data-ttu-id="19a5b-111">I formati quali JSON e JSON Light sono più efficienti di ATOM/XML e possono garantire prestazioni migliori quando si trasferiscono grandi quantità di dati.</span><span class="sxs-lookup"><span data-stu-id="19a5b-111">Formats such as JSON and JSON Light are more efficient than ATOM/XML, and may give you better performance when transferring large amounts of data.</span></span> <span data-ttu-id="19a5b-112">Nella tabella seguente vengono forniti i risultati dei test di esempio.</span><span class="sxs-lookup"><span data-stu-id="19a5b-112">The following table provides results from sample tests.</span></span> <span data-ttu-id="19a5b-113">Come si può notare, si verifica un miglioramento delle prestazioni del 30-53% quando si passa dal formato ATOM a JSON e un miglioramento del 67% quando si passa da ATOM al nuovo formato JSON Light, disponibile in WCF Data Services 5.1.</span><span class="sxs-lookup"><span data-stu-id="19a5b-113">As you can see, there was a 30-53% performance gain when switching from ATOM to JSON and 67% performance gain when switching from ATOM to the new JSON light format (available in WCF Data Services 5.1).</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="19a5b-114">Righe</span><span class="sxs-lookup"><span data-stu-id="19a5b-114">Rows</span></span>|<span data-ttu-id="19a5b-115">ATOM</span><span class="sxs-lookup"><span data-stu-id="19a5b-115">ATOM</span></span>|<span data-ttu-id="19a5b-116">JSON</span><span class="sxs-lookup"><span data-stu-id="19a5b-116">JSON</span></span>|<span data-ttu-id="19a5b-117">JSON (Light)</span><span class="sxs-lookup"><span data-stu-id="19a5b-117">JSON (Light)</span></span>|  
|<span data-ttu-id="19a5b-118">10000</span><span class="sxs-lookup"><span data-stu-id="19a5b-118">10000</span></span>|<span data-ttu-id="19a5b-119">113 secondi</span><span class="sxs-lookup"><span data-stu-id="19a5b-119">113 seconds</span></span>|<span data-ttu-id="19a5b-120">74 secondi</span><span class="sxs-lookup"><span data-stu-id="19a5b-120">74 seconds</span></span>|<span data-ttu-id="19a5b-121">68 secondi</span><span class="sxs-lookup"><span data-stu-id="19a5b-121">68 seconds</span></span>|  
|<span data-ttu-id="19a5b-122">1000000</span><span class="sxs-lookup"><span data-stu-id="19a5b-122">1000000</span></span>|<span data-ttu-id="19a5b-123">1110 secondi</span><span class="sxs-lookup"><span data-stu-id="19a5b-123">1110 seconds</span></span>|<span data-ttu-id="19a5b-124">853 secondi</span><span class="sxs-lookup"><span data-stu-id="19a5b-124">853 seconds</span></span>|<span data-ttu-id="19a5b-125">665 secondi</span><span class="sxs-lookup"><span data-stu-id="19a5b-125">665 seconds</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="19a5b-126">Con l'origine SSIS OData viene utilizzato ODataLib 5.5.0 per analizzare i feed OData ed è possibile leggere tutti i formati supportati da questa libreria.</span><span class="sxs-lookup"><span data-stu-id="19a5b-126">The SSIS OData Source uses ODataLib 5.5.0 to parse OData feeds and it can read all formats supported by this library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="19a5b-127">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="19a5b-127">In This Section</span></span>  
  
-   [<span data-ttu-id="19a5b-128">Installare e disinstallare il componente di origine OData</span><span class="sxs-lookup"><span data-stu-id="19a5b-128">Install and Uninstall OData Source Component</span></span>](../install-and-uninstall-odata-source-component.md)  
  
-   [<span data-ttu-id="19a5b-129">Esercitazione: uso dell'origine OData &#91;SSIS&#93;</span><span class="sxs-lookup"><span data-stu-id="19a5b-129">Tutorial: Using the OData Source &#91;SSIS&#93;</span></span>](tutorial-using-the-odata-source.md)  
  
-   [<span data-ttu-id="19a5b-130">Modificare la query di origine OData in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="19a5b-130">Modify OData Source Query at Runtime</span></span>](modify-odata-source-query-at-runtime.md)  
  
-   [<span data-ttu-id="19a5b-131">Editor origine OData &#40;pagina Connessione &#41;</span><span class="sxs-lookup"><span data-stu-id="19a5b-131">OData Source Editor &#40;Connection Page&#41;</span></span>](../odata-source-editor-connection-page.md)  
  
-   [<span data-ttu-id="19a5b-132">Editor origine OData &#40;pagina Colonne&#41;</span><span class="sxs-lookup"><span data-stu-id="19a5b-132">OData Source Editor &#40;Columns Page&#41;</span></span>](../odata-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="19a5b-133">Editor origine OData &#40;pagina Output degli errori&#41;</span><span class="sxs-lookup"><span data-stu-id="19a5b-133">OData Source Editor &#40;Error Output Page&#41;</span></span>](../odata-source-editor-error-output-page.md)  
  
-   [<span data-ttu-id="19a5b-134">Proprietà dell'origine OData</span><span class="sxs-lookup"><span data-stu-id="19a5b-134">OData Source Properties</span></span>](odata-source-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="19a5b-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19a5b-135">See Also</span></span>  
 [<span data-ttu-id="19a5b-136">Gestione connessione OData</span><span class="sxs-lookup"><span data-stu-id="19a5b-136">OData Connection Manager</span></span>](../connection-manager/odata-connection-manager.md)  
  
  
