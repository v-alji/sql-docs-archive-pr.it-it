---
title: Metodo SetServiceState (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetServiceState (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetServiceState method
ms.assetid: 9e1ee42d-b388-4929-89c7-8741b956c3be
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 70b4a29b3379fc1d312af42a1f5b1296ee35dcf3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722364"
---
# <a name="setservicestate-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="17f97-102">Metodo SetServiceState (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="17f97-102">SetServiceState Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="17f97-103">Attiva e disattiva i servizi Windows ReportServer e Web ReportServer.</span><span class="sxs-lookup"><span data-stu-id="17f97-103">Turns the Report Server Windows and Web services on and off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17f97-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="17f97-104">Syntax</span></span>  
  
```vb  
Public Sub SetServiceState(ByVal EnableWindowsService As Boolean, _  
    ByVal EnableWebService As Boolean, ByVal EnableReportManager As Boolean, _  
    ByRef HRESULT As Int32)  
```  
  
```csharp  
public void SetSecureConnectionLevel(Boolean EnableWindowsService,  
    Boolean EnableWebService, Boolean EnableReportManager, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17f97-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="17f97-105">Parameters</span></span>  
 <span data-ttu-id="17f97-106">*EnableWindowsService*</span><span class="sxs-lookup"><span data-stu-id="17f97-106">*EnableWindowsService*</span></span>  
 <span data-ttu-id="17f97-107">Valore `Boolean` che indica lo stato del servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="17f97-107">A `Boolean` value indicating the state of the Windows service.</span></span> <span data-ttu-id="17f97-108">Un valore `true` avvia il servizio Windows ReportServer; un valore `false` arresta il servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="17f97-108">A value of `true` starts the Report Server Windows service; a value of `false` stops the Windows service.</span></span>  
  
 <span data-ttu-id="17f97-109">*EnableWebService*</span><span class="sxs-lookup"><span data-stu-id="17f97-109">*EnableWebService*</span></span>  
 <span data-ttu-id="17f97-110">Valore `Boolean` che indica lo stato del servizio Web [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17f97-110">A `Boolean` value indicating the state of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Web service.</span></span> <span data-ttu-id="17f97-111">Un valore `true` avvia il servizio Web ReportServer; un valore `false` arresta il servizio Web.</span><span class="sxs-lookup"><span data-stu-id="17f97-111">A value of `true` starts the Report Server Web service; a value of `false` stops the Web service</span></span>  
  
 <span data-ttu-id="17f97-112">*EnableReportManager*</span><span class="sxs-lookup"><span data-stu-id="17f97-112">*EnableReportManager*</span></span>  
 <span data-ttu-id="17f97-113">Valore `Boolean` che indica lo stato desiderato per Gestione report.</span><span class="sxs-lookup"><span data-stu-id="17f97-113">A `Boolean` value indicating the desired state of the Report manager.</span></span>  
  
 <span data-ttu-id="17f97-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="17f97-114">*HRESULT*</span></span>  
 <span data-ttu-id="17f97-115">[out] Valore che indica se la chiamata ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="17f97-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="17f97-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="17f97-116">Return Value</span></span>  
 <span data-ttu-id="17f97-117">Restituisce un *HRESULT* che indica l'esito positivo o negativo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="17f97-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="17f97-118">Un valore pari a 0 indica l'esito positivo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="17f97-118">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="17f97-119">Un valore diverso da zero indica che si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="17f97-119">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17f97-120">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="17f97-120">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17f97-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="17f97-121">Requirements</span></span>  
 <span data-ttu-id="17f97-122">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17f97-122">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17f97-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17f97-123">See Also</span></span>  
 [<span data-ttu-id="17f97-124">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="17f97-124">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
