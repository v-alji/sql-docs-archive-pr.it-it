---
title: Metodo SetExtendedProtectionSettings (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2d8e7232-42f4-41b6-98eb-c856f6c85d8c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ee937747b74bcf8d53012721b4be5bfca04185df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722380"
---
# <a name="setextendedprotectionsettings-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="e12b2-102">Metodo SetExtendedProtectionSettings (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="e12b2-102">SetExtendedProtectionSettings Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="e12b2-103">Il metodo SetExtendedProtectionSettings viene usato per impostare le proprietà RSWindowsExtendedProtectionLevel e RSWindowsExtendedProtectionScenario nel file di configurazione RSReportServer.config di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e12b2-103">The SetExtendedProtectionSettings method is used to set the RSWindowsExtendedProtectionLevel and the RSWindowsExtendedProtectionScenario properties in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] configuration file RSReportServer.config.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e12b2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e12b2-104">Syntax</span></span>  
  
```vb  
Public Sub SetExtendedProtectionSettings( _  
        ByVal ExtendedProtectionLevel As String, _  
        ByVal ExtendedProtectionScenario As String, _  
        ByRef Warnings() As String, _  
        ByRef Length As Int32, _  
        ByRef HRESULT As Int32)  
```  
  
```csharp  
public void SetExtendedProtectionSettings(  
            string ExtendedProtectionLevel,  
            string ExtendedProtectionScenario,  
            out string[] Warnings,  
            out Int32 Length,  
            out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e12b2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e12b2-105">Parameters</span></span>  
 <span data-ttu-id="e12b2-106">*ExtendedProtectionLevel*</span><span class="sxs-lookup"><span data-stu-id="e12b2-106">*ExtendedProtectionLevel*</span></span>  
 <span data-ttu-id="e12b2-107">Imposta RSWindowsExtendedProtectionLevel nel file RSRreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="e12b2-107">Sets the RSWindowsExtendedProtectionLevel in the RSRreportserver.config file.</span></span> <span data-ttu-id="e12b2-108">Il valore obbligatorio non supporta la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="e12b2-108">The required value is not case sensitive.</span></span>  
  
 <span data-ttu-id="e12b2-109">Nell'elenco seguente sono indicati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="e12b2-109">The following list shows valid values:</span></span>  
  
 `"Off | Allow | Require"`  
  
 <span data-ttu-id="e12b2-110">*ExtendedProtectionScenario*</span><span class="sxs-lookup"><span data-stu-id="e12b2-110">*ExtendedProtectionScenario*</span></span>  
 <span data-ttu-id="e12b2-111">Imposta RSWindowsExtendedProtectionScenario nel file RSReportserver.config.</span><span class="sxs-lookup"><span data-stu-id="e12b2-111">Sets the RSWindowsExtendedProtectionScenario in the RSReportserver.config file.</span></span> <span data-ttu-id="e12b2-112">Il valore obbligatorio non supporta la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="e12b2-112">The required value is not case sensitive.</span></span>  
  
 <span data-ttu-id="e12b2-113">Nell'elenco seguente sono indicati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="e12b2-113">The following list shows valid values:</span></span>  
  
 `"Any" | "Proxy" | "Direct"`  
  
## <a name="remarks"></a><span data-ttu-id="e12b2-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e12b2-114">Remarks</span></span>  
 <span data-ttu-id="e12b2-115">Le proprietà RSWindowsExtendedProtectionLevel e RSWindowsExtendedProtectionScenario si applicano quando i tipi di autenticazione nel file RSReportServer.config includono RSWindowNTLM, RSWindowsNegotiate o RSWindowsKerberos.</span><span class="sxs-lookup"><span data-stu-id="e12b2-115">The RSWindowsExtendedProtectionLevel and the RSWindowsExtendedProtectionScenario properties apply when the AuthenticationTypes in the RSReportServer.config file include RSWindowNTLM, RSWindowsNegotiate, or RSWindowsKerberos.</span></span> <span data-ttu-id="e12b2-116">L'impostazione di queste proprietà ha effetto sulla modalità di autenticazione degli utenti e del software client nel server di report.</span><span class="sxs-lookup"><span data-stu-id="e12b2-116">Setting these properties affects how users and client software authenticate with a report server.</span></span> <span data-ttu-id="e12b2-117">Prima di impostare ExtendedProtectionLevel su `Allow` o su `Require` è consigliabile leggere la documentazione relativa alla protezione estesa.</span><span class="sxs-lookup"><span data-stu-id="e12b2-117">It is recommended that you read the documentation for extended protection before setting ExtendedProtectionLevel to either `Allow` or `Require`.</span></span>  
  
 <span data-ttu-id="e12b2-118">Per impostare ExtendedProtectionLevel, è necessario che l'utente sia un membro del gruppo BUILTIN\Administrators nel server di report.</span><span class="sxs-lookup"><span data-stu-id="e12b2-118">To set the ExtendedProtectionLevel, the user must be a member of the BUILTIN\Administrators group on the report server.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e12b2-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e12b2-119">Requirements</span></span>  
 <span data-ttu-id="e12b2-120">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e12b2-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e12b2-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e12b2-121">See Also</span></span>  
 <span data-ttu-id="e12b2-122">[Proprietà RSWindowsExtendedProtectionScenario &#40;MSReportServer_ConfigurationSetting WMI&#41;](rswindowsextendedprotectionscenario-property.md) </span><span class="sxs-lookup"><span data-stu-id="e12b2-122">[RSWindowsExtendedProtectionScenario Property &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionscenario-property.md) </span></span>  
 <span data-ttu-id="e12b2-123">[Proprietà RSWindowsExtendedProtectionLevel &#40;MSReportServer_ConfigurationSetting WMI&#41;](rswindowsextendedprotectionlevel-property.md) </span><span class="sxs-lookup"><span data-stu-id="e12b2-123">[RSWindowsExtendedProtectionLevel Property &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionlevel-property.md) </span></span>  
 <span data-ttu-id="e12b2-124">[Protezione estesa per l'autenticazione con Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="e12b2-124">[Extended Protection for Authentication with Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span></span>  
 [<span data-ttu-id="e12b2-125">File di configurazione RSReportServer</span><span class="sxs-lookup"><span data-stu-id="e12b2-125">RSReportServer Configuration File</span></span>](../report-server/rsreportserver-config-configuration-file.md)  
  
  
