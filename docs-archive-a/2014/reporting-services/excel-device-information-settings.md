---
title: Impostazioni relative alle informazioni sul dispositivo Excel | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- device information settings [Reporting Services], Excel rendering
- Excel [Reporting Services], rendering
ms.assetid: bb5f3566-f033-4470-be87-1f52fb7a4ab6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d71c83195c8f91984bbbce95bd00402928fdb36e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719613"
---
# <a name="excel-device-information-settings"></a><span data-ttu-id="12552-102">Impostazioni relative alle informazioni sul dispositivo Excel</span><span class="sxs-lookup"><span data-stu-id="12552-102">Excel Device Information Settings</span></span>
  <span data-ttu-id="12552-103">Nella tabella seguente sono elencate le impostazioni relative alle informazioni sul dispositivo per il rendering nel formato [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="12552-103">The following table lists the device information settings for rendering in [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] format.</span></span>  
  
|<span data-ttu-id="12552-104">Impostazione</span><span class="sxs-lookup"><span data-stu-id="12552-104">Setting</span></span>|<span data-ttu-id="12552-105">valore</span><span class="sxs-lookup"><span data-stu-id="12552-105">Value</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="12552-106">**OmitDocumentMap**</span><span class="sxs-lookup"><span data-stu-id="12552-106">**OmitDocumentMap**</span></span>|<span data-ttu-id="12552-107">Indica se omettere la mappa documento per i report che la supportano.</span><span class="sxs-lookup"><span data-stu-id="12552-107">Indicates whether to omit the document map for reports that support it.</span></span> <span data-ttu-id="12552-108">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="12552-108">The default value is `false`.</span></span>|  
|<span data-ttu-id="12552-109">**OmitFormulas**</span><span class="sxs-lookup"><span data-stu-id="12552-109">**OmitFormulas**</span></span>|<span data-ttu-id="12552-110">Indica se omettere le formule dal report visualizzabile.</span><span class="sxs-lookup"><span data-stu-id="12552-110">Indicates whether to omit formulas from the rendered report.</span></span> <span data-ttu-id="12552-111">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="12552-111">The default value is `false`.</span></span>|  
|<span data-ttu-id="12552-112">`SimplePageHeade`rs</span><span class="sxs-lookup"><span data-stu-id="12552-112">`SimplePageHeade`rs</span></span>|<span data-ttu-id="12552-113">Indica se viene eseguito il rendering dell'intestazione di pagina del report nell'intestazione di pagina di Excel.</span><span class="sxs-lookup"><span data-stu-id="12552-113">Indicates whether the page header of the report is rendered to the Excel page header.</span></span> <span data-ttu-id="12552-114">Il valore `false` indica che il rendering dell'intestazione di pagina viene eseguito nella prima riga del foglio di lavoro.</span><span class="sxs-lookup"><span data-stu-id="12552-114">A value of `false` indicates that the page header is rendered to the first row of the worksheet.</span></span> <span data-ttu-id="12552-115">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="12552-115">The default value is `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="12552-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12552-116">See Also</span></span>  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 <span data-ttu-id="12552-117">[Passaggio delle impostazioni delle informazioni sul dispositivo alle estensioni per il rendering](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="12552-117">[Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span></span>  
 <span data-ttu-id="12552-118">[Personalizzare i parametri di estensione per il rendering in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="12552-118">[Customize Rendering Extension Parameters in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="12552-119">Riferimento tecnico &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="12552-119">Technical Reference &#40;SSRS&#41;</span></span>](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
