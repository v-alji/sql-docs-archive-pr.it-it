---
title: Impostazioni relative alle informazioni sul dispositivo Word | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Word [Reporting Services]
- device information settings [Reporting Services], Word
ms.assetid: 28146498-fae7-4b13-b47f-6ec05aa8e057
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ddd145c5073003a8dc189e3ed9b1bbb25dc11d09
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623762"
---
# <a name="word-device-information-settings"></a><span data-ttu-id="b8522-102">Impostazioni relative alle informazioni sul dispositivo Word</span><span class="sxs-lookup"><span data-stu-id="b8522-102">Word Device Information Settings</span></span>
  <span data-ttu-id="b8522-103">Nella tabella seguente sono elencate le impostazioni relative alle informazioni sul dispositivo per il rendering nel formato [!INCLUDE[ofprword](../includes/ofprword-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b8522-103">The following table lists the device information settings for rendering in [!INCLUDE[ofprword](../includes/ofprword-md.md)] format.</span></span>  
  
|<span data-ttu-id="b8522-104">Impostazione</span><span class="sxs-lookup"><span data-stu-id="b8522-104">Setting</span></span>|<span data-ttu-id="b8522-105">valore</span><span class="sxs-lookup"><span data-stu-id="b8522-105">Value</span></span>|  
|-------------|-----------|  
|`AutoFit`|<span data-ttu-id="b8522-106">`False`.</span><span class="sxs-lookup"><span data-stu-id="b8522-106">`False`.</span></span> <span data-ttu-id="b8522-107">L'impostazione di AutoFit è `false` in qualsiasi tabella di Word.</span><span class="sxs-lookup"><span data-stu-id="b8522-107">AutoFit is set to `false` set on any Word table.</span></span><br /><br /> <span data-ttu-id="b8522-108">`True`.</span><span class="sxs-lookup"><span data-stu-id="b8522-108">`True`.</span></span> <span data-ttu-id="b8522-109">L'impostazione di AutoFit è `true` in tutte le tabelle di Word.</span><span class="sxs-lookup"><span data-stu-id="b8522-109">AutoFit is set to `true` on every Word table.</span></span><br /><br /> <span data-ttu-id="b8522-110">`Never`.</span><span class="sxs-lookup"><span data-stu-id="b8522-110">`Never`.</span></span> <span data-ttu-id="b8522-111">I valori di AutoFit non sono impostati in alcuna tabella di Word e viene applicato il comportamento predefinito di Word.</span><span class="sxs-lookup"><span data-stu-id="b8522-111">AutoFit values are not set on any Word table and behavior reverts to the Word default.</span></span><br /><br /> <span data-ttu-id="b8522-112">`Default`.</span><span class="sxs-lookup"><span data-stu-id="b8522-112">`Default`.</span></span> <span data-ttu-id="b8522-113">AutoFit è impostata per le tabelle più strette rispetto all'area di disegno fisica (larghezza fisica della pagina esclusi i margini) per la pagina logica.</span><span class="sxs-lookup"><span data-stu-id="b8522-113">AutoFit is set on tables that are narrower than the physical drawing area (physical page width excluding margins) per logical page.</span></span>|  
|`ExpandToggles`|<span data-ttu-id="b8522-114">Indica se per tutti gli elementi che possono essere attivati o disattivati deve venire eseguito il rendering nello stato completamente espanso.</span><span class="sxs-lookup"><span data-stu-id="b8522-114">Indicates whether all items that can be toggled should render in their fully-expanded state.</span></span> <span data-ttu-id="b8522-115">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="b8522-115">The default value is `false`.</span></span>|  
|`FixedPageWidth`|<span data-ttu-id="b8522-116">Indica se la larghezza della pagina scritta nel file DOC aumenta in base alla larghezza della pagina più larga nel corpo del report.</span><span class="sxs-lookup"><span data-stu-id="b8522-116">Indicates whether the Page Width written to the DOC file will grow to accommodate the width of the largest page in the Report Body.</span></span> <span data-ttu-id="b8522-117">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="b8522-117">The default value is `false`.</span></span>|  
|<span data-ttu-id="b8522-118">**OmitHyperlinks**</span><span class="sxs-lookup"><span data-stu-id="b8522-118">**OmitHyperlinks**</span></span>|<span data-ttu-id="b8522-119">Indica se l'azione collegamento ipertestuale deve essere omessa in tutti gli elementi in cui è impostata.</span><span class="sxs-lookup"><span data-stu-id="b8522-119">Indicates whether to omit the Hyperlink action on all items where it is set.</span></span> <span data-ttu-id="b8522-120">Il valore predefinito è `false`</span><span class="sxs-lookup"><span data-stu-id="b8522-120">The default value is `false`</span></span>|  
|`OmitDrillthroughs`|<span data-ttu-id="b8522-121">Indica se l'azione drill-through deve essere omessa in tutti gli elementi in cui è impostata.</span><span class="sxs-lookup"><span data-stu-id="b8522-121">Indicates whether to omit the Drillthrough action on all items where it is set.</span></span> <span data-ttu-id="b8522-122">Il valore predefinito è `false`</span><span class="sxs-lookup"><span data-stu-id="b8522-122">The default value is `false`</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b8522-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8522-123">See Also</span></span>  
 <span data-ttu-id="b8522-124">[Passaggio delle impostazioni delle informazioni sul dispositivo alle estensioni per il rendering](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="b8522-124">[Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span></span>  
 <span data-ttu-id="b8522-125">[Personalizzare i parametri di estensione per il rendering in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="b8522-125">[Customize Rendering Extension Parameters in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="b8522-126">Riferimento tecnico &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b8522-126">Technical Reference &#40;SSRS&#41;</span></span>](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
