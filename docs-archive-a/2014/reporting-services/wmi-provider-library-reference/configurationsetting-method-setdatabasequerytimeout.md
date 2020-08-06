---
title: Metodo SetDatabaseQueryTimeout (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetDatabaseQueryTimeout (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDatabaseQueryTimeout method
ms.assetid: bd2809e5-7848-45b3-a502-b04fc698b646
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7ab6b5bf27eca5e9d6d083d03af48c0ab71b4dd2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722379"
---
# <a name="setdatabasequerytimeout-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="867f9-102">Metodo SetDatabaseQueryTimeout (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="867f9-102">SetDatabaseQueryTimeout Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="867f9-103">Specifica il valore di timeout predefinito per le query sul database del server di report.</span><span class="sxs-lookup"><span data-stu-id="867f9-103">Specifies the default time-out value for report server database queries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="867f9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="867f9-104">Syntax</span></span>  
  
```vb  
Public Sub SetDatabaseQueryTimeout(LogonTimeout as Int32, _  
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetDatabaseQueryTimeout (Int32 LogonTimeout,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="867f9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="867f9-105">Parameters</span></span>  
 <span data-ttu-id="867f9-106">*LogonTimeout*</span><span class="sxs-lookup"><span data-stu-id="867f9-106">*LogonTimeout*</span></span>  
 <span data-ttu-id="867f9-107">Valore di timeout predefinito, espresso in secondi, per le query sul database del server di report.</span><span class="sxs-lookup"><span data-stu-id="867f9-107">The default timeout value, in seconds, for report server database queries.</span></span>  
  
 <span data-ttu-id="867f9-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="867f9-108">*HRESULT*</span></span>  
 <span data-ttu-id="867f9-109">[out] Valore che indica se la chiamata ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="867f9-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="867f9-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="867f9-110">Return Value</span></span>  
 <span data-ttu-id="867f9-111">Restituisce un *HRESULT* che indica l'esito positivo o negativo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="867f9-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="867f9-112">Un valore pari a 0 indica l'esito positivo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="867f9-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="867f9-113">Un valore diverso da zero indica che si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="867f9-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="867f9-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="867f9-114">Requirements</span></span>  
 <span data-ttu-id="867f9-115">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="867f9-115">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="867f9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="867f9-116">See Also</span></span>  
 [<span data-ttu-id="867f9-117">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="867f9-117">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
