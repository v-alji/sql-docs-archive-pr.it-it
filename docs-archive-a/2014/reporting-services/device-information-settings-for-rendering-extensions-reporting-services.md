---
title: Impostazioni relative alle informazioni sul dispositivo per le estensioni per il rendering (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 947b0ee1-bb35-4b4e-9527-dc501566e7d1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f15e27e01cd43bafda3aede3deca7729f2c89756
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719661"
---
# <a name="device-information-settings-for-rendering-extensions-reporting-services"></a><span data-ttu-id="2f114-102">Impostazioni relative alle informazioni sul dispositivo per le estensioni per il rendering (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="2f114-102">Device Information Settings for Rendering Extensions (Reporting Services)</span></span>
  <span data-ttu-id="2f114-103">In [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]le impostazioni relative alle informazioni sul dispositivo vengono usate per passare i parametri di rendering a un'estensione per il rendering.</span><span class="sxs-lookup"><span data-stu-id="2f114-103">In [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], device information settings are used to pass rendering parameters to a rendering extension.</span></span> <span data-ttu-id="2f114-104">Ogni estensione per il rendering accetta un set specifico di impostazioni.</span><span class="sxs-lookup"><span data-stu-id="2f114-104">Each rendering extension accepts a specific set of settings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2f114-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="2f114-105">In This Section</span></span>  
  
|<span data-ttu-id="2f114-106">Argomento</span><span class="sxs-lookup"><span data-stu-id="2f114-106">Topic</span></span>|<span data-ttu-id="2f114-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2f114-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="2f114-108">Impostazioni relative alle informazioni sul dispositivo ATOM</span><span class="sxs-lookup"><span data-stu-id="2f114-108">ATOM Device Information Settings</span></span>](../../2014/reporting-services/atom-device-information-settings.md)|<span data-ttu-id="2f114-109">Descrive le impostazioni relative alle informazioni sul dispositivo associate all'output del rendering conforme a Atom.</span><span class="sxs-lookup"><span data-stu-id="2f114-109">Describes the device information settings that are associated with Atom compliant rendering output.</span></span>|  
|[<span data-ttu-id="2f114-110">Impostazioni relative alle informazioni sul dispositivo CSV</span><span class="sxs-lookup"><span data-stu-id="2f114-110">CSV Device Information Settings</span></span>](csv-device-information-settings.md)|<span data-ttu-id="2f114-111">Descrive le impostazioni relative alle informazioni sul dispositivo associate all'output del rendering CSV.</span><span class="sxs-lookup"><span data-stu-id="2f114-111">Describes the device information settings that are associated with CSV rendering output.</span></span>|  
|[<span data-ttu-id="2f114-112">Impostazioni relative alle informazioni sul dispositivo Excel</span><span class="sxs-lookup"><span data-stu-id="2f114-112">Excel Device Information Settings</span></span>](excel-device-information-settings.md)|<span data-ttu-id="2f114-113">Descrive le impostazioni relative alle informazioni sul dispositivo associate all'output del rendering Excel.</span><span class="sxs-lookup"><span data-stu-id="2f114-113">Describes the device information settings that are associated with Excel rendering output.</span></span>|  
|[<span data-ttu-id="2f114-114">Impostazioni relative alle informazioni sul dispositivo Word</span><span class="sxs-lookup"><span data-stu-id="2f114-114">Word Device Information Settings</span></span>](word-device-information-settings.md)|<span data-ttu-id="2f114-115">Descrive le impostazioni delle informazioni sul dispositivo associate all'output del rendering Word.</span><span class="sxs-lookup"><span data-stu-id="2f114-115">Describes the device information settings that are associated with Word rendering output.</span></span>|  
|[<span data-ttu-id="2f114-116">Impostazioni relative alle informazioni sul dispositivo HTML</span><span class="sxs-lookup"><span data-stu-id="2f114-116">HTML Device Information Settings</span></span>](html-device-information-settings.md)|<span data-ttu-id="2f114-117">Descrive le impostazioni relative alle informazioni sul dispositivo associate all'output del rendering HTML.</span><span class="sxs-lookup"><span data-stu-id="2f114-117">Describes the device information settings that are associated with HTML rendering output.</span></span>|  
|[<span data-ttu-id="2f114-118">Impostazioni relative alle informazioni sul dispositivo di acquisizione immagini</span><span class="sxs-lookup"><span data-stu-id="2f114-118">Image Device Information Settings</span></span>](image-device-information-settings.md)|<span data-ttu-id="2f114-119">Descrive le impostazioni relative alle informazioni sul dispositivo associate all'output del rendering IMAGE.</span><span class="sxs-lookup"><span data-stu-id="2f114-119">Describes the device information settings that are associated with IMAGE rendering output.</span></span>|  
|[<span data-ttu-id="2f114-120">Impostazioni relative alle informazioni sul dispositivo MHTML</span><span class="sxs-lookup"><span data-stu-id="2f114-120">MHTML Device Information Settings</span></span>](mhtml-device-information-settings.md)|<span data-ttu-id="2f114-121">Descrive le impostazioni relative alle informazioni sul dispositivo associate all'output del rendering MHTML.</span><span class="sxs-lookup"><span data-stu-id="2f114-121">Describes the device information settings that are associated with MHTML rendering output.</span></span>|  
|[<span data-ttu-id="2f114-122">Impostazioni relative alle informazioni sul dispositivo PDF</span><span class="sxs-lookup"><span data-stu-id="2f114-122">PDF Device Information Settings</span></span>](pdf-device-information-settings.md)|<span data-ttu-id="2f114-123">Descrive le impostazioni relative alle informazioni sul dispositivo associate all'output del rendering PDF.</span><span class="sxs-lookup"><span data-stu-id="2f114-123">Describes the device information settings that are associated with PDF rendering output.</span></span>|  
|[<span data-ttu-id="2f114-124">Impostazioni relative alle informazioni sul dispositivo XML</span><span class="sxs-lookup"><span data-stu-id="2f114-124">XML Device Information Settings</span></span>](xml-device-information-settings.md)|<span data-ttu-id="2f114-125">Descrive le impostazioni relative alle informazioni sul dispositivo associate all'output del rendering XML.</span><span class="sxs-lookup"><span data-stu-id="2f114-125">Describes the device information settings that are associated with XML rendering output.</span></span>|  
|[<span data-ttu-id="2f114-126">Impostazioni relative alle informazioni sul dispositivo RGDI</span><span class="sxs-lookup"><span data-stu-id="2f114-126">RGDI Device Information Settings</span></span>](rgdi-device-information-settings.md)|<span data-ttu-id="2f114-127">Descrive le impostazioni relative alle informazioni sul dispositivo associate all'output del rendering RGDI.</span><span class="sxs-lookup"><span data-stu-id="2f114-127">Describes the device information settings that are associated with RGDI rendering output.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2f114-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f114-128">See Also</span></span>  
 [<span data-ttu-id="2f114-129">Personalizzare i parametri di estensione per il rendering in RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="2f114-129">Customize Rendering Extension Parameters in RSReportServer.Config</span></span>](customize-rendering-extension-parameters-in-rsreportserver-config.md)  
  
  
