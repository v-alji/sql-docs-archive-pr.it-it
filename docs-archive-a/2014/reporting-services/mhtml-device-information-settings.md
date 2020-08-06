---
title: Impostazioni relative alle informazioni sul dispositivo MHTML | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- device information settings [Reporting Services], MHTML rendering
- MHTML [Reporting Services]
ms.assetid: 60b85dd8-b4fb-4ad9-be6a-e7c89ac076fe
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 076a0179871775984799fc8ce5366a220f812867
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635455"
---
# <a name="mhtml-device-information-settings"></a><span data-ttu-id="0f456-102">Impostazioni relative alle informazioni sul dispositivo MHTML</span><span class="sxs-lookup"><span data-stu-id="0f456-102">MHTML Device Information Settings</span></span>
  <span data-ttu-id="0f456-103">Nella tabella seguente sono elencate le impostazioni relative alle informazioni sul dispositivo per il rendering dei report in formato MHTML (archivio Web).</span><span class="sxs-lookup"><span data-stu-id="0f456-103">The following table lists the device information settings for rendering reports in Web archive (MHTML) format.</span></span>  
  
|<span data-ttu-id="0f456-104">Impostazione</span><span class="sxs-lookup"><span data-stu-id="0f456-104">Setting</span></span>|<span data-ttu-id="0f456-105">valore</span><span class="sxs-lookup"><span data-stu-id="0f456-105">Value</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="0f456-106">**JavaScript**</span><span class="sxs-lookup"><span data-stu-id="0f456-106">**JavaScript**</span></span>|<span data-ttu-id="0f456-107">Indica se JavaScript è supportato nel report visualizzabile.</span><span class="sxs-lookup"><span data-stu-id="0f456-107">Indicates whether JavaScript is supported in the rendered report.</span></span>|  
|<span data-ttu-id="0f456-108">**OutlookCompat**</span><span class="sxs-lookup"><span data-stu-id="0f456-108">**OutlookCompat**</span></span>|<span data-ttu-id="0f456-109">Indica se eseguire il rendering con metadati aggiuntivi che comportano una visualizzazione migliore del report in Outlook,</span><span class="sxs-lookup"><span data-stu-id="0f456-109">Indicates whether to render with extra metadata that makes the report look better in Outlook.</span></span> <span data-ttu-id="0f456-110">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="0f456-110">The default value is `true`.</span></span>|  
|<span data-ttu-id="0f456-111">**Frammento MHTML**</span><span class="sxs-lookup"><span data-stu-id="0f456-111">**MHTML Fragment**</span></span>|<span data-ttu-id="0f456-112">Indica se viene creato un frammento MHTML al posto di un documento MHTML completo.</span><span class="sxs-lookup"><span data-stu-id="0f456-112">Indicates whether an MHTML fragment is created in place of a full MHTML document.</span></span> <span data-ttu-id="0f456-113">Un frammento MHTML include il contenuto del report in un elemento TABLE e omette gli elementi HTML e BODY.</span><span class="sxs-lookup"><span data-stu-id="0f456-113">An MHTML fragment includes the report content in a TABLE element and omits the HTML and BODY elements.</span></span> <span data-ttu-id="0f456-114">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="0f456-114">The default value is `false`.</span></span>|  
|<span data-ttu-id="0f456-115">**DataVisualizationFitSizing**</span><span class="sxs-lookup"><span data-stu-id="0f456-115">**DataVisualizationFitSizing**</span></span>|<span data-ttu-id="0f456-116">Indica il comportamento di adattamento della visualizzazione dei dati all'interno di una tablix.</span><span class="sxs-lookup"><span data-stu-id="0f456-116">Indicates data visualization fit behavior when inside a tablix.</span></span> <span data-ttu-id="0f456-117">Sono inclusi grafici, misuratori e mappe.</span><span class="sxs-lookup"><span data-stu-id="0f456-117">This includes chart, gauge, and map.</span></span><br /><br /> <span data-ttu-id="0f456-118">I valori possibili sono **Approssimato** ed **Esatto**.</span><span class="sxs-lookup"><span data-stu-id="0f456-118">The possible values are **Approximate** and **Exact**.</span></span><br /><br /> <span data-ttu-id="0f456-119">Il valore predefinito è **Approssimato**.</span><span class="sxs-lookup"><span data-stu-id="0f456-119">The default value is **Approximate**.</span></span> <span data-ttu-id="0f456-120">Se l'impostazione viene rimossa dal file **rsreportserver.config** il comportamento predefinito è **Esatto**.</span><span class="sxs-lookup"><span data-stu-id="0f456-120">If the setting is removed from the **rsreportserver.config** file then the default behavior is **Exact**.</span></span><br /><br /> <span data-ttu-id="0f456-121">L'abilitazione del ridimensionamento **Esatto** può avere impatto sulle prestazioni perché l'elaborazione per determinare la dimensione esatta potrebbe impiegare più molto tempo di un adattamento approssimativo.</span><span class="sxs-lookup"><span data-stu-id="0f456-121">Enabling **Exact** may have performance impact because the processing to determine the exact size may take longer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0f456-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f456-122">See Also</span></span>  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 <span data-ttu-id="0f456-123">[Passaggio delle impostazioni relative alle informazioni sul dispositivo alle estensioni per il rendering](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="0f456-123">[Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span></span>  
 <span data-ttu-id="0f456-124">[Personalizzare i parametri di estensione per il rendering in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="0f456-124">[Customize Rendering Extension Parameters in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="0f456-125">Riferimento tecnico &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0f456-125">Technical Reference &#40;SSRS&#41;</span></span>](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
