---
title: Metodo ListSSLCertificates (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ListSSLCertificates method
ms.assetid: 88cd0936-b202-4ab8-90f2-d9c3f66d37f4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6a5ced8371817adc44bbbc89400dc83e0dfccef0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627604"
---
# <a name="listsslcertificates-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="65144-102">Metodo ListSSLCertificates (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="65144-102">ListSSLCertificates Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="65144-103">Restituisce un elenco dei certificati presenti nel computer del server di report.</span><span class="sxs-lookup"><span data-stu-id="65144-103">Returns a list of certificates on the report server computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65144-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="65144-104">Syntax</span></span>  
  
```vb  
Public Sub CreateSSLCertificateBinding (ByRef CertificateHash() as String, _  
    ByRef CertName() as String, ByRef HostName() as String, ByRef Length as Int32, _   
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void ListSSLCertificates(out string[] CertificateHash,   
    out string[] CertName, out string[] Hostname, out Int32 length,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65144-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="65144-105">Parameters</span></span>  
 <span data-ttu-id="65144-106">*CertificateHash[]*</span><span class="sxs-lookup"><span data-stu-id="65144-106">*CertificateHash[]*</span></span>  
 <span data-ttu-id="65144-107">[out] Hash del certificato.</span><span class="sxs-lookup"><span data-stu-id="65144-107">[out] The certificate hashes.</span></span>  
  
 <span data-ttu-id="65144-108">*CertName[]*</span><span class="sxs-lookup"><span data-stu-id="65144-108">*CertName[]*</span></span>  
 <span data-ttu-id="65144-109">[out] Nomi del certificato.</span><span class="sxs-lookup"><span data-stu-id="65144-109">[out] Names of the certificate.</span></span>  
  
 <span data-ttu-id="65144-110">*HostName[]*</span><span class="sxs-lookup"><span data-stu-id="65144-110">*HostName[]*</span></span>  
 <span data-ttu-id="65144-111">[out] Nomi host per i certificati.</span><span class="sxs-lookup"><span data-stu-id="65144-111">[out] The host names for the certificates.</span></span>  
  
 <span data-ttu-id="65144-112">*Lunghezza*</span><span class="sxs-lookup"><span data-stu-id="65144-112">*Length*</span></span>  
 <span data-ttu-id="65144-113">[out] Rappresenta la lunghezza delle matrici *CertificateHash*, *CertName* e *HostName* .</span><span class="sxs-lookup"><span data-stu-id="65144-113">[out] Represents the length of the *CertificateHash*, *CertName* and *HostName* arrays.</span></span>  
  
 <span data-ttu-id="65144-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="65144-114">*HRESULT*</span></span>  
 <span data-ttu-id="65144-115">[out] Valore che indica se la chiamata ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="65144-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65144-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="65144-116">Return Value</span></span>  
 <span data-ttu-id="65144-117">Restituisce un *HRESULT* che indica l'esito positivo o negativo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="65144-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="65144-118">Il valore 0 indica l'esito positivo della chiamata al metodo, mentre un codice di errore ne indica l'esito negativo.</span><span class="sxs-lookup"><span data-stu-id="65144-118">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65144-119">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="65144-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65144-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="65144-120">Requirements</span></span>  
 <span data-ttu-id="65144-121">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65144-121">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65144-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65144-122">See Also</span></span>  
 [<span data-ttu-id="65144-123">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="65144-123">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
