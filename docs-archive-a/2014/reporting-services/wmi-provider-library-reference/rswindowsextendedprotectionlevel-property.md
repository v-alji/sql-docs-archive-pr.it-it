---
title: Proprietà RSWindowsExtendedProtectionLevel (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 162ffe86-69c3-49d2-b9ed-49d097c05551
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 02ff3bad42ae25adf6cfa563944d89bac2c600e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627599"
---
# <a name="rswindowsextendedprotectionlevel-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="af95c-102">Proprietà RSWindowsExtendedProtectionLevel (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="af95c-102">RSWindowsExtendedProtectionLevel Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="af95c-103">Restituisce un valore stringa che indica il livello di protezione supportato dalla configurazione del server di report.</span><span class="sxs-lookup"><span data-stu-id="af95c-103">Returns a string value that indicates the level of protection the report server is configured to support.</span></span> <span data-ttu-id="af95c-104">Questa proprietà è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="af95c-104">This property is read-only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af95c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="af95c-105">Syntax</span></span>  
  
```vb  
Public Dim RSWindowsExtendedProtectionLevel As String  
```  
  
```csharp  
public string RSWindowsExtendedProtectionLevel;  
```  
  
## <a name="remarks"></a><span data-ttu-id="af95c-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="af95c-106">Remarks</span></span>  
 <span data-ttu-id="af95c-107">Restituisce un valore stringa che indica il livello di protezione supportato dalla configurazione del server di report.</span><span class="sxs-lookup"><span data-stu-id="af95c-107">Returns a string value that indicates the level of protection the report server is configured to support.</span></span> <span data-ttu-id="af95c-108">Se il server di report a cui è connesso il provider WMI non supporta la protezione estesa, viene restituita una stringa vuota ("").</span><span class="sxs-lookup"><span data-stu-id="af95c-108">If the report server that the WMI provider is connected to does not support extended protection, "" (empty string) is returned.</span></span> <span data-ttu-id="af95c-109">Nell'elenco seguente sono indicati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="af95c-109">The following list shows valid values:</span></span>  
  
 `"Off" | "Allow" | "Require"`  
  
## <a name="example-code"></a><span data-ttu-id="af95c-110">Codice di esempio</span><span class="sxs-lookup"><span data-stu-id="af95c-110">Example Code</span></span>  
 [<span data-ttu-id="af95c-111">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="af95c-111">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="see-also"></a><span data-ttu-id="af95c-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af95c-112">See Also</span></span>  
 <span data-ttu-id="af95c-113">[Proprietà RSWindowsExtendedProtectionScenario &#40;MSReportServer_ConfigurationSetting WMI&#41;](rswindowsextendedprotectionscenario-property.md) </span><span class="sxs-lookup"><span data-stu-id="af95c-113">[RSWindowsExtendedProtectionScenario Property &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionscenario-property.md) </span></span>  
 <span data-ttu-id="af95c-114">[Metodo SetExtendedProtectionSettings &#40;MSReportServer_ConfigurationSetting WMI&#41;](configurationsetting-method-setextendedprotectionsettings.md) </span><span class="sxs-lookup"><span data-stu-id="af95c-114">[SetExtendedProtectionSettings Method &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setextendedprotectionsettings.md) </span></span>  
 <span data-ttu-id="af95c-115">[Protezione estesa per l'autenticazione con Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="af95c-115">[Extended Protection for Authentication with Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span></span>  
 [<span data-ttu-id="af95c-116">File di configurazione RSReportServer</span><span class="sxs-lookup"><span data-stu-id="af95c-116">RSReportServer Configuration File</span></span>](../report-server/rsreportserver-config-configuration-file.md)  
  
  
