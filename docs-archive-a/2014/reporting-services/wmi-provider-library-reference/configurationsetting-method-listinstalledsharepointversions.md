---
title: Metodo ListInstalledSharePointVersions (WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ListInstalledSharePointVersions method
ms.assetid: 8f0a5e9f-23f1-41e5-9a90-dfec19ef1df7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f0ceee23876461cf31cbd265ea39ae015ddcbc49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627618"
---
# <a name="listinstalledsharepointversions-method-wmi"></a><span data-ttu-id="d4a15-102">Metodo ListInstalledSharePointVersions (WMI)</span><span class="sxs-lookup"><span data-stu-id="d4a15-102">ListInstalledSharePointVersions Method (WMI)</span></span>
  <span data-ttu-id="d4a15-103">Restituisce un set di token che rappresentano le versioni di Microsoft [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)]o [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] installate nello stesso computer del server di report.</span><span class="sxs-lookup"><span data-stu-id="d4a15-103">Returns a set of tokens that represent the versions of Microsoft [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)], or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] that are installed on the same computer as the report server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4a15-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d4a15-104">Syntax</span></span>  
  
```vb  
Public Sub ListInstalledSharePointVersions(ByRef VersionTokens() _  
    As String, ByRef Length As Int32, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void ListReportServersInDatabase (out string[] VersionTokens,   
    out Int32 Length, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4a15-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d4a15-105">Parameters</span></span>  
 <span data-ttu-id="d4a15-106">*VersionTokens[]*</span><span class="sxs-lookup"><span data-stu-id="d4a15-106">*VersionTokens[]*</span></span>  
 <span data-ttu-id="d4a15-107">[out] Matrice che contiene i token che rappresentano la versione di un prodotto o di una tecnologia SharePoint compatibile con il server di report installato.</span><span class="sxs-lookup"><span data-stu-id="d4a15-107">[out] An array that contains the tokens that represent the version of a SharePoint product or technology that is compatible with the installed report server.</span></span>  
  
 <span data-ttu-id="d4a15-108">*Lunghezza*</span><span class="sxs-lookup"><span data-stu-id="d4a15-108">*Length*</span></span>  
 <span data-ttu-id="d4a15-109">[out] Lunghezza della matrice dei token di versione.</span><span class="sxs-lookup"><span data-stu-id="d4a15-109">[out] The length of the version tokens array.</span></span>  
  
 <span data-ttu-id="d4a15-110">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="d4a15-110">*HRESULT*</span></span>  
 <span data-ttu-id="d4a15-111">[out] Valore che indica se la chiamata ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="d4a15-111">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4a15-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d4a15-112">Return Value</span></span>  
 <span data-ttu-id="d4a15-113">Restituisce un *HRESULT* che indica l'esito positivo o negativo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="d4a15-113">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="d4a15-114">Un valore pari a 0 indica l'esito positivo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="d4a15-114">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="d4a15-115">Un valore diverso da zero indica che si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="d4a15-115">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4a15-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d4a15-116">Remarks</span></span>  
 <span data-ttu-id="d4a15-117">Ogni token restituito rappresenta una versione di [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] o [!INCLUDE[SPF2010](../../includes/spf2010-md.md)] compatibile con il server di report attualmente installato.</span><span class="sxs-lookup"><span data-stu-id="d4a15-117">Each token that is returned represents a version of [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] or [!INCLUDE[SPF2010](../../includes/spf2010-md.md)] that is compatible with the currently installed report server.</span></span> <span data-ttu-id="d4a15-118">Se una particolare versione di SharePoint è compatibile con le versioni di SharePoint precedenti, vengono restituiti token per ogni versione di SharePoint compatibile.</span><span class="sxs-lookup"><span data-stu-id="d4a15-118">If a particular version of SharePoint is compatible with previous SharePoint versions, tokens for each compatible SharePoint version are returned.</span></span>  
  
 <span data-ttu-id="d4a15-119">Di seguito è riportata una tabella dei token di SharePoint restituiti.</span><span class="sxs-lookup"><span data-stu-id="d4a15-119">The following is a table of the SharePoint tokens that are returned.</span></span>  
  
|<span data-ttu-id="d4a15-120">**Token di versione**</span><span class="sxs-lookup"><span data-stu-id="d4a15-120">**Version Tokens**</span></span>|<span data-ttu-id="d4a15-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="d4a15-121">**Description**</span></span>|  
|------------------------|---------------------|  
|<span data-ttu-id="d4a15-122">WSS_V2_Compatible</span><span class="sxs-lookup"><span data-stu-id="d4a15-122">WSS_V2_Compatible</span></span>|<span data-ttu-id="d4a15-123">È installata una versione di [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)]o [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] compatibile con [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] 2.0.</span><span class="sxs-lookup"><span data-stu-id="d4a15-123">A [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)], or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] installation is installed that is compatible with [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] 2.0.</span></span>|  
|<span data-ttu-id="d4a15-124">WSS_V3_Compatible</span><span class="sxs-lookup"><span data-stu-id="d4a15-124">WSS_V3_Compatible</span></span>|<span data-ttu-id="d4a15-125">È installata una versione di [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)]o [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] compatibile con [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] 3.0.</span><span class="sxs-lookup"><span data-stu-id="d4a15-125">A [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)], or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] installation is installed that is compatible with [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] 3.0.</span></span>|  
|<span data-ttu-id="d4a15-126">WSS_V4_Compatible</span><span class="sxs-lookup"><span data-stu-id="d4a15-126">WSS_V4_Compatible</span></span>|<span data-ttu-id="d4a15-127">È installata una versione di [!INCLUDE[SPF2010](../../includes/spf2010-md.md)] o [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] compatibile con Office 14.</span><span class="sxs-lookup"><span data-stu-id="d4a15-127">A [!INCLUDE[SPF2010](../../includes/spf2010-md.md)] or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] installation is installed that is compatible with Office 14.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d4a15-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d4a15-128">Requirements</span></span>  
 <span data-ttu-id="d4a15-129">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4a15-129">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4a15-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4a15-130">See Also</span></span>  
 [<span data-ttu-id="d4a15-131">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="d4a15-131">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
