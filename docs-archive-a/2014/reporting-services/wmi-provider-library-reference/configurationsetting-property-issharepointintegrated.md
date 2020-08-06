---
title: Proprietà IsSharePointIntegrated (WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- IsSharePointIntegrated property
ms.assetid: c548fed8-5e04-4faf-8b10-b37c86178056
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a1f3f38c23546ddf4dfb52c2a3af7c122af10cbd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635410"
---
# <a name="issharepointintegrated-property-wmi"></a><span data-ttu-id="a411d-102">Proprietà IsSharePointIntegrated (WMI)</span><span class="sxs-lookup"><span data-stu-id="a411d-102">IsSharePointIntegrated Property (WMI)</span></span>
  <span data-ttu-id="a411d-103">Viene specificato se il server di report è in modalità integrata SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a411d-103">Specifies whether the report server is in SharePoint integrated mode.</span></span> <span data-ttu-id="a411d-104">A partire da [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], questa proprietà restituisce sempre `False` poiché in modalità SharePoint, le istanze [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] sono servizi condivisi SharePoint e non vengono controllate dai provider WMI.</span><span class="sxs-lookup"><span data-stu-id="a411d-104">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], this property always returns `False` because in SharePoint mode, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instances are SharePoint shared services and are not controlled by WMI providers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a411d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a411d-105">Syntax</span></span>  
  
```vb  
Public Dim IsSharePointIntegrated As Boolean  
```  
  
```csharp  
public Boolean IsSharePointIntegrated;  
```  
  
## <a name="property-values"></a><span data-ttu-id="a411d-106">Valori della proprietà</span><span class="sxs-lookup"><span data-stu-id="a411d-106">Property Values</span></span>  
 <span data-ttu-id="a411d-107">Oggetto `Boolean` che indica se il server di report è in modalità integrata SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a411d-107">A `Boolean` object that indicates whether the report server is in SharePoint integrated mode.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="a411d-108">Codice di esempio</span><span class="sxs-lookup"><span data-stu-id="a411d-108">Example Code</span></span>  
 [<span data-ttu-id="a411d-109">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="a411d-109">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a><span data-ttu-id="a411d-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a411d-110">Requirements</span></span>  
 <span data-ttu-id="a411d-111">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a411d-111">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a411d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a411d-112">See Also</span></span>  
 [<span data-ttu-id="a411d-113">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="a411d-113">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
