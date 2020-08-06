---
title: Proprietà RSWindowsExtendedProtectionScenario (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5ac7ab80-9adf-4f65-abfa-fedf53b082b5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 84e14d056cc0352b0d1d85bc12c9c873a1b89ced
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719409"
---
# <a name="rswindowsextendedprotectionscenario-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="d22f5-102">Proprietà RSWindowsExtendedProtectionScenario (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="d22f5-102">RSWindowsExtendedProtectionScenario Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="d22f5-103">Restituisce un valore stringa che indica lo scenario di protezione estesa consentito dalla configurazione del server di report.</span><span class="sxs-lookup"><span data-stu-id="d22f5-103">Returns a string value that indicates the extended protection scenario the report server is configured to allow.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d22f5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d22f5-104">Syntax</span></span>  
  
```vb  
Public Dim RSWindowsExtendedProtectionScenario As String  
```  
  
```csharp  
public string RSWindowsExtendedProtectionScenario;  
```  
  
## <a name="remarks"></a><span data-ttu-id="d22f5-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d22f5-105">Remarks</span></span>  
 <span data-ttu-id="d22f5-106">Restituisce un valore stringa che indica lo scenario di protezione estesa consentito dalla configurazione del server di report.</span><span class="sxs-lookup"><span data-stu-id="d22f5-106">Returns a string value that indicates the extended protection scenario the report server is configured to allow.</span></span> <span data-ttu-id="d22f5-107">Se il server di report a cui è connesso il provider WMI non supporta la protezione estesa, viene restituita una stringa vuota ("").</span><span class="sxs-lookup"><span data-stu-id="d22f5-107">If the report server that the WMI provider is connected to does not support extended protection, "" (empty string) is returned.</span></span>  
  
 <span data-ttu-id="d22f5-108">Nell'elenco seguente sono indicati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="d22f5-108">The following list shows valid values:</span></span>  
  
 `"Any | Proxy | Direct"`  
  
## <a name="example-code"></a><span data-ttu-id="d22f5-109">Codice di esempio</span><span class="sxs-lookup"><span data-stu-id="d22f5-109">Example Code</span></span>  
 [<span data-ttu-id="d22f5-110">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="d22f5-110">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="see-also"></a><span data-ttu-id="d22f5-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d22f5-111">See Also</span></span>  
 <span data-ttu-id="d22f5-112">[Proprietà RSWindowsExtendedProtectionLevel &#40;MSReportServer_ConfigurationSetting WMI&#41;](rswindowsextendedprotectionlevel-property.md) </span><span class="sxs-lookup"><span data-stu-id="d22f5-112">[RSWindowsExtendedProtectionLevel Property &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionlevel-property.md) </span></span>  
 <span data-ttu-id="d22f5-113">[Metodo SetExtendedProtectionSettings &#40;MSReportServer_ConfigurationSetting WMI&#41;](configurationsetting-method-setextendedprotectionsettings.md) </span><span class="sxs-lookup"><span data-stu-id="d22f5-113">[SetExtendedProtectionSettings Method &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setextendedprotectionsettings.md) </span></span>  
 <span data-ttu-id="d22f5-114">[Protezione estesa per l'autenticazione con Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="d22f5-114">[Extended Protection for Authentication with Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span></span>  
 [<span data-ttu-id="d22f5-115">File di configurazione RSReportServer</span><span class="sxs-lookup"><span data-stu-id="d22f5-115">RSReportServer Configuration File</span></span>](../report-server/rsreportserver-config-configuration-file.md)  
  
  
