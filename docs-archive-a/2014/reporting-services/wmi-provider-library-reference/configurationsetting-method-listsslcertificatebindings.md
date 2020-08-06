---
title: Metodo ListSSLCertificateBindings (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ListSSLCertificateBindings method
ms.assetid: d12d280c-9b6f-47a8-bcd9-34cde31c8886
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 56b19a138dc95b94a20183909dd444c90b158b26
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627607"
---
# <a name="listsslcertificatebindings-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="8857c-102">Metodo ListSSLCertificateBindings (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="8857c-102">ListSSLCertificateBindings Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="8857c-103">Restituisce un elenco dei certificati SSL installati presenti nel computer.</span><span class="sxs-lookup"><span data-stu-id="8857c-103">Returns a list of installed SSL certificates on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8857c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8857c-104">Syntax</span></span>  
  
```vb  
Public Sub ListSSLCertificateBindings(ByVal LCID As Int32, ByRef Application() As String, _  
    ByRef CertificateHash() As String, ByRef IPAddresses() As String, ByRef Port() As Int32, _  
    ByRef Errors() As String, ByRef Length As Int32, _  
    ByRef HRESULT As Int32)  
```  
  
```csharp  
public void ListSSLCertificateBindings(Int32 Lcid, out string[] Application,   
    out string[] CertificateHash,out string[] IPAddress,   
    out Int32[] Port, out string Errors,   
    out Int32 length, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8857c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8857c-105">Parameters</span></span>  
 <span data-ttu-id="8857c-106">*LCID*</span><span class="sxs-lookup"><span data-stu-id="8857c-106">*LCID*</span></span>  
 <span data-ttu-id="8857c-107">Impostazioni locali da utilizzare per i messaggi di errore restituiti.</span><span class="sxs-lookup"><span data-stu-id="8857c-107">The locale to use for the error messages that are returned.</span></span>  
  
 <span data-ttu-id="8857c-108">*Application[]*</span><span class="sxs-lookup"><span data-stu-id="8857c-108">*Application[]*</span></span>  
 <span data-ttu-id="8857c-109">[out] Applicazioni che dispongono di associazioni certificato.</span><span class="sxs-lookup"><span data-stu-id="8857c-109">[out] The applications that have certificate bindings.</span></span>  
  
 <span data-ttu-id="8857c-110">*CertificateHash[]*</span><span class="sxs-lookup"><span data-stu-id="8857c-110">*CertificateHash[]*</span></span>  
 <span data-ttu-id="8857c-111">[out] Hash per i certificati.</span><span class="sxs-lookup"><span data-stu-id="8857c-111">[out] The hashes for the certificates.</span></span>  
  
 <span data-ttu-id="8857c-112">*IPAddress[]*</span><span class="sxs-lookup"><span data-stu-id="8857c-112">*IPAddress[]*</span></span>  
 <span data-ttu-id="8857c-113">[out] Indirizzo IP per le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8857c-113">[out] The IP address for the applications.</span></span>  
  
 <span data-ttu-id="8857c-114">*Port[]*</span><span class="sxs-lookup"><span data-stu-id="8857c-114">*Port[]*</span></span>  
 <span data-ttu-id="8857c-115">[out] Numero di porta archiviato nell'associazione in rsreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="8857c-115">[out] The port number stored in the binding in rsreportserver.config.</span></span>  
  
 <span data-ttu-id="8857c-116">*Errors[]*</span><span class="sxs-lookup"><span data-stu-id="8857c-116">*Errors[]*</span></span>  
 <span data-ttu-id="8857c-117">[out] Descrizioni degli errori che si sono verificati.</span><span class="sxs-lookup"><span data-stu-id="8857c-117">[out] The descriptions for errors that occurred.</span></span>  
  
 <span data-ttu-id="8857c-118">*Lunghezza*</span><span class="sxs-lookup"><span data-stu-id="8857c-118">*Length*</span></span>  
 <span data-ttu-id="8857c-119">[out] Lunghezza della matrice restituita dal metodo.</span><span class="sxs-lookup"><span data-stu-id="8857c-119">[out] The length of the array returned by the method.</span></span>  
  
 <span data-ttu-id="8857c-120">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="8857c-120">*HRESULT*</span></span>  
 <span data-ttu-id="8857c-121">[out] Valore che indica se la chiamata ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="8857c-121">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8857c-122">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8857c-122">Return Value</span></span>  
 <span data-ttu-id="8857c-123">Restituisce un *HRESULT* che indica l'esito positivo o negativo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="8857c-123">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="8857c-124">Un valore pari a 0 indica l'esito positivo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="8857c-124">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="8857c-125">Un valore diverso da zero indica che si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="8857c-125">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8857c-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8857c-126">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8857c-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8857c-127">Requirements</span></span>  
 <span data-ttu-id="8857c-128">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8857c-128">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8857c-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8857c-129">See Also</span></span>  
 [<span data-ttu-id="8857c-130">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="8857c-130">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
