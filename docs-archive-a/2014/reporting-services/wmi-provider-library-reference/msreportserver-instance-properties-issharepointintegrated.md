---
title: Proprietà IsSharePointIntegrated (MSReportServer_Instance WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- IsSharePointIntegrated property
ms.assetid: e21d00ad-5d9a-4290-8d74-7eeeda39e1ed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d0c92ebe586d37053b47f90ca98c31b3068a7b91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627600"
---
# <a name="issharepointintegrated-property-wmi-msreportserver_instance"></a><span data-ttu-id="4d85d-102">Proprietà IsSharePointIntegrated (MSReportServer_Instance WMI)</span><span class="sxs-lookup"><span data-stu-id="4d85d-102">IsSharePointIntegrated Property (WMI MSReportServer_Instance)</span></span>
  <span data-ttu-id="4d85d-103">Viene specificato se il server di report è in modalità integrata SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4d85d-103">Specifies whether the report server is in SharePoint integrated mode.</span></span> <span data-ttu-id="4d85d-104">A partire da [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], questa proprietà restituisce sempre `False` poiché in modalità SharePoint, le istanze [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] sono servizi condivisi SharePoint e non vengono controllate dai provider WMI.</span><span class="sxs-lookup"><span data-stu-id="4d85d-104">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], this property always returns `False` because in SharePoint mode, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instances are SharePoint shared services and are not controlled by WMI providers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d85d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4d85d-105">Syntax</span></span>  
  
```vb  
Public Dim IsSharePointIntegrated As Boolean  
```  
  
```csharp  
public Boolean IsSharePointIntegrated;  
```  
  
## <a name="property-values"></a><span data-ttu-id="4d85d-106">Valori della proprietà</span><span class="sxs-lookup"><span data-stu-id="4d85d-106">Property Values</span></span>  
 <span data-ttu-id="4d85d-107">Valore `Boolean` che indica se il server di report è in modalità integrata SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4d85d-107">A `Boolean` value that indicates whether the report server is in SharePoint integrated mode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d85d-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4d85d-108">Requirements</span></span>  
 <span data-ttu-id="4d85d-109">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d85d-109">**Namespace:** [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d85d-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d85d-110">See Also</span></span>  
 <span data-ttu-id="4d85d-111">[Membri di MSReportServer_Instance](msreportserver-instance-members.md) </span><span class="sxs-lookup"><span data-stu-id="4d85d-111">[MSReportServer_Instance Members](msreportserver-instance-members.md) </span></span>  
 [<span data-ttu-id="4d85d-112">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="4d85d-112">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
  
