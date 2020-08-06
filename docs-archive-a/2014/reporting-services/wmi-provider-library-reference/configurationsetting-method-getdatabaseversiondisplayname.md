---
title: Metodo GetDatabaseVersionDisplayName (WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- GetDatabaseVersionDisplayName method
ms.assetid: e1286424-7043-4f12-a7ad-1cf69e81baa4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8b39ce39a4f26964c148631c903869b0234e2b9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627619"
---
# <a name="getdatabaseversiondisplayname-method-wmi"></a><span data-ttu-id="0afeb-102">Metodo GetDatabaseVersionDisplayName (WMI)</span><span class="sxs-lookup"><span data-stu-id="0afeb-102">GetDatabaseVersionDisplayName Method (WMI)</span></span>
  <span data-ttu-id="0afeb-103">Ottiene il nome visualizzato di una stringa di versione di un database del server di report specifico.</span><span class="sxs-lookup"><span data-stu-id="0afeb-103">Gets the display name for a given report server database version string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0afeb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0afeb-104">Syntax</span></span>  
  
```vb  
Public Sub GetDatabaseVersionDisplayName(Version As String, DisplayName As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void GetDatabaseVersionDisplayName(string Version, string DisplayName, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0afeb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0afeb-105">Parameters</span></span>  
 <span data-ttu-id="0afeb-106">*Version*</span><span class="sxs-lookup"><span data-stu-id="0afeb-106">*Version*</span></span>  
 <span data-ttu-id="0afeb-107">Stringa che contiene la stringa di versione per un database del server di report.</span><span class="sxs-lookup"><span data-stu-id="0afeb-107">A string that contains the version string for a report server database.</span></span>  
  
 <span data-ttu-id="0afeb-108">*DisplayName*</span><span class="sxs-lookup"><span data-stu-id="0afeb-108">*DisplayName*</span></span>  
 <span data-ttu-id="0afeb-109">[out] Stringa che contiene il nome visualizzato che corrisponde alla versione fornita.</span><span class="sxs-lookup"><span data-stu-id="0afeb-109">[out] A string that contains the display name that corresponds to the version supplied.</span></span>  
  
 <span data-ttu-id="0afeb-110">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="0afeb-110">*HRESULT*</span></span>  
 <span data-ttu-id="0afeb-111">[out] Valore che indica se la chiamata ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="0afeb-111">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0afeb-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0afeb-112">Remarks</span></span>  
 <span data-ttu-id="0afeb-113">Nella tabella seguente viene mostrato il mapping dalla versione del database alla stringa visualizzata.</span><span class="sxs-lookup"><span data-stu-id="0afeb-113">The following table shows the mapping from database version to display string.</span></span>  
  
|<span data-ttu-id="0afeb-114">**Versione**</span><span class="sxs-lookup"><span data-stu-id="0afeb-114">**Release**</span></span>|`Version`|<span data-ttu-id="0afeb-115">**Nome visualizzato**</span><span class="sxs-lookup"><span data-stu-id="0afeb-115">**Display Name**</span></span>|  
|-----------------|-----------------|----------------------|  
|<span data-ttu-id="0afeb-116">RS 2005 SP2</span><span class="sxs-lookup"><span data-stu-id="0afeb-116">RS 2005 SP2</span></span>|<span data-ttu-id="0afeb-117">@DBVersion = 'C.0.8.54'</span><span class="sxs-lookup"><span data-stu-id="0afeb-117">@DBVersion = 'C.0.8.54'</span></span>|<span data-ttu-id="0afeb-118">SQL Server 2005 SP2</span><span class="sxs-lookup"><span data-stu-id="0afeb-118">SQL Server 2005 SP2</span></span>|  
|<span data-ttu-id="0afeb-119">RS 2005 SP1</span><span class="sxs-lookup"><span data-stu-id="0afeb-119">RS 2005 SP1</span></span>|<span data-ttu-id="0afeb-120">@DBVersion = 'C.0.8.43'</span><span class="sxs-lookup"><span data-stu-id="0afeb-120">@DBVersion = 'C.0.8.43'</span></span>|<span data-ttu-id="0afeb-121">SQL Server 2005 SP1</span><span class="sxs-lookup"><span data-stu-id="0afeb-121">SQL Server 2005 SP1</span></span>|  
|<span data-ttu-id="0afeb-122">RS 2005 RTM</span><span class="sxs-lookup"><span data-stu-id="0afeb-122">RS 2005 RTM</span></span>|<span data-ttu-id="0afeb-123">@DBVersion = 'C.0.8.40'</span><span class="sxs-lookup"><span data-stu-id="0afeb-123">@DBVersion = 'C.0.8.40'</span></span>|<span data-ttu-id="0afeb-124">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="0afeb-124">SQL Server 2005</span></span>|  
|<span data-ttu-id="0afeb-125">RS 2000 SP2</span><span class="sxs-lookup"><span data-stu-id="0afeb-125">RS 2000 SP2</span></span>|<span data-ttu-id="0afeb-126">@DBVersion = 'C.0.6.54'</span><span class="sxs-lookup"><span data-stu-id="0afeb-126">@DBVersion = 'C.0.6.54'</span></span>|<span data-ttu-id="0afeb-127">SQL Server 2000 SP2</span><span class="sxs-lookup"><span data-stu-id="0afeb-127">SQL Server 2000 SP2</span></span>|  
|<span data-ttu-id="0afeb-128">RS 2000 SP1</span><span class="sxs-lookup"><span data-stu-id="0afeb-128">RS 2000 SP1</span></span>|<span data-ttu-id="0afeb-129">@DBVersion = 'C.0.6.51'</span><span class="sxs-lookup"><span data-stu-id="0afeb-129">@DBVersion = 'C.0.6.51'</span></span>|<span data-ttu-id="0afeb-130">SQL Server 2000 SP1</span><span class="sxs-lookup"><span data-stu-id="0afeb-130">SQL Server 2000 SP1</span></span>|  
|<span data-ttu-id="0afeb-131">RS 2000 RTM</span><span class="sxs-lookup"><span data-stu-id="0afeb-131">RS 2000 RTM</span></span>|<span data-ttu-id="0afeb-132">@DBVersion = 'C.0.6.43'</span><span class="sxs-lookup"><span data-stu-id="0afeb-132">@DBVersion = 'C.0.6.43'</span></span>|<span data-ttu-id="0afeb-133">SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="0afeb-133">SQL Server 2000</span></span>|  
|<span data-ttu-id="0afeb-134">Hotfix</span><span class="sxs-lookup"><span data-stu-id="0afeb-134">Hotfix</span></span>||<span data-ttu-id="0afeb-135">Versione applicabile più vicina</span><span class="sxs-lookup"><span data-stu-id="0afeb-135">Closest applicable version</span></span>|  
  
 <span data-ttu-id="0afeb-136">Per un valore di *Version* antecedente a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2000 viene restituito un valore HRESULT di ACT_E_BAD_VERSION.</span><span class="sxs-lookup"><span data-stu-id="0afeb-136">For a *Version* prior to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2000 an HRESULT of ACT_E_BAD_VERSION is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0afeb-137">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0afeb-137">Return Value</span></span>  
 <span data-ttu-id="0afeb-138">Restituisce un *HRESULT* che indica l'esito positivo o negativo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="0afeb-138">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="0afeb-139">Un valore pari a 0 indica l'esito positivo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="0afeb-139">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="0afeb-140">Un valore diverso da zero indica che si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="0afeb-140">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0afeb-141">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0afeb-141">Requirements</span></span>  
 <span data-ttu-id="0afeb-142">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0afeb-142">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0afeb-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0afeb-143">See Also</span></span>  
 [<span data-ttu-id="0afeb-144">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="0afeb-144">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
