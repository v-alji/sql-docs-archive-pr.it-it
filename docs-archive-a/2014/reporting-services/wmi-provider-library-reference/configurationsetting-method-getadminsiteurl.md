---
title: Metodo GetAdminSiteUrl (WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- GetAdminSiteUrl method
ms.assetid: fbc5bf3c-120c-4aec-a4f2-f5391bd415f6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cae1a6f7e363ddce8c47c00eb5ef25fc832e59c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627620"
---
# <a name="getadminsiteurl-method-wmi"></a><span data-ttu-id="e5be5-102">Metodo GetAdminSiteUrl (WMI)</span><span class="sxs-lookup"><span data-stu-id="e5be5-102">GetAdminSiteUrl Method (WMI)</span></span>
  <span data-ttu-id="e5be5-103">Ottiene l'URL assoluto per il sito Web di Amministrazione centrale per la farm di Microsoft [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)]o [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] con la quale il server di report è integrato.</span><span class="sxs-lookup"><span data-stu-id="e5be5-103">Gets the absolute URL for the Central Administration Web site for the Microsoft [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)], or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] farm that the report server is integrated with.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5be5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e5be5-104">Syntax</span></span>  
  
```vb  
Public Sub GetAdminSiteUrl(ByRef AdminSiteUrl as String, _  
ByRef HRESULT as Int32)  
```  
  
```csharp  
public void GetAdminSiteUrl(out string AdminSiteUrl, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5be5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e5be5-105">Parameters</span></span>  
 <span data-ttu-id="e5be5-106">*AdminSiteUrl*</span><span class="sxs-lookup"><span data-stu-id="e5be5-106">*AdminSiteUrl*</span></span>  
 <span data-ttu-id="e5be5-107">[out] Stringa che contiene l'URL assoluto per il sito Web di Amministrazione centrale per la farm di SharePoint con la quale il server di report è integrato.</span><span class="sxs-lookup"><span data-stu-id="e5be5-107">[out] A string that contains the absolute URL for the Central Administration Web site for the SharePoint farm that the report server is integrated with.</span></span>  
  
 <span data-ttu-id="e5be5-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="e5be5-108">*HRESULT*</span></span>  
 <span data-ttu-id="e5be5-109">[out] Valore che indica se la chiamata ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="e5be5-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5be5-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e5be5-110">Return Value</span></span>  
 <span data-ttu-id="e5be5-111">Restituisce un *HRESULT* che indica l'esito positivo o negativo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="e5be5-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="e5be5-112">Un valore pari a 0 indica l'esito positivo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="e5be5-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="e5be5-113">Un valore diverso da zero indica che si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="e5be5-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5be5-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e5be5-114">Requirements</span></span>  
 <span data-ttu-id="e5be5-115">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5be5-115">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5be5-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5be5-116">See Also</span></span>  
 [<span data-ttu-id="e5be5-117">Metodi di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="e5be5-117">MSReportServer_ConfigurationSetting Methods</span></span>](msreportserver-configurationsetting-methods.md)  
  
  
