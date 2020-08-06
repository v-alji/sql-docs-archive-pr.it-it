---
title: Metodo RemoveSSLCertificateBindings (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- RemoveSSLCertificateBindings method
ms.assetid: b8b484c9-04c4-4ae9-980e-67bbe5aa8481
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d42d17d9c92f2e100a7800e607536ff6c7eab891
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720939"
---
# <a name="removesslcertificatebindings-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="da90a-102">Metodo RemoveSSLCertificateBindings (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="da90a-102">RemoveSSLCertificateBindings Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="da90a-103">Rimuove un'associazione certificato SSL.</span><span class="sxs-lookup"><span data-stu-id="da90a-103">Removes an SSL Certificate binding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da90a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="da90a-104">Syntax</span></span>  
  
```vb  
Public Sub RemoveSSLCertificateBinding(ByVal Application As String, _  
    ByVal CertificateHash As String, ByVal IPAddress As String, _  
    ByVal Port As Int32, ByVal Lcid As Int32, _  
    ByRef [Error] As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void RemoveSSLCertificateBindings(string Application,  
    string CertificateHash, string IPAddress, Int32 Port, Int32 Lcid,  
    out string Error, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da90a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="da90a-105">Parameters</span></span>  
 <span data-ttu-id="da90a-106">*Applicazione*</span><span class="sxs-lookup"><span data-stu-id="da90a-106">*Application*</span></span>  
 <span data-ttu-id="da90a-107">Nome dell'applicazione per la quale l'associazione certificato deve essere rimossa.</span><span class="sxs-lookup"><span data-stu-id="da90a-107">The name of application for which the certificate binding should be removed.</span></span>  
  
 <span data-ttu-id="da90a-108">*CertificateHash*</span><span class="sxs-lookup"><span data-stu-id="da90a-108">*CertificateHash*</span></span>  
 <span data-ttu-id="da90a-109">Hash per il certificato.</span><span class="sxs-lookup"><span data-stu-id="da90a-109">The hash for the certificate.</span></span>  
  
 <span data-ttu-id="da90a-110">*IPAddress*</span><span class="sxs-lookup"><span data-stu-id="da90a-110">*IPAddress*</span></span>  
 <span data-ttu-id="da90a-111">Indirizzo IP per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="da90a-111">The IP address for the application.</span></span>  
  
 <span data-ttu-id="da90a-112">*Porta*</span><span class="sxs-lookup"><span data-stu-id="da90a-112">*Port*</span></span>  
 <span data-ttu-id="da90a-113">Porta SSL associata all'associazione.</span><span class="sxs-lookup"><span data-stu-id="da90a-113">The SSL port associated with the binding.</span></span>  
  
 <span data-ttu-id="da90a-114">*lcid*</span><span class="sxs-lookup"><span data-stu-id="da90a-114">*lcid*</span></span>  
 <span data-ttu-id="da90a-115">Impostazioni locali da utilizzare per i messaggi di errore restituiti.</span><span class="sxs-lookup"><span data-stu-id="da90a-115">The locale to use for the error messages that are returned.</span></span>  
  
 <span data-ttu-id="da90a-116">*Error (Errore) (Error (Errore)e)*</span><span class="sxs-lookup"><span data-stu-id="da90a-116">*Error*</span></span>  
 <span data-ttu-id="da90a-117">[out] Descrizione dell'errore che si è verificato.</span><span class="sxs-lookup"><span data-stu-id="da90a-117">[out] The description of the error that occurred.</span></span>  
  
 <span data-ttu-id="da90a-118">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="da90a-118">*HRESULT*</span></span>  
 <span data-ttu-id="da90a-119">[out] Valore che indica se la chiamata ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="da90a-119">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="da90a-120">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="da90a-120">Return Value</span></span>  
 <span data-ttu-id="da90a-121">Restituisce un *HRESULT* che indica l'esito positivo o negativo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="da90a-121">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="da90a-122">Il valore 0 indica l'esito positivo della chiamata al metodo, mentre un codice di errore ne indica l'esito negativo.</span><span class="sxs-lookup"><span data-stu-id="da90a-122">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da90a-123">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="da90a-123">Remarks</span></span>  
 <span data-ttu-id="da90a-124">Questo metodo rimuove l'associazione specifica dal file rsreportserver.config e facoltativamente da HTTP.SYS.</span><span class="sxs-lookup"><span data-stu-id="da90a-124">This method removes the specific binding from the rsreportserver.config file and optionally HTTP.SYS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da90a-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="da90a-125">Requirements</span></span>  
 <span data-ttu-id="da90a-126">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da90a-126">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da90a-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da90a-127">See Also</span></span>  
 [<span data-ttu-id="da90a-128">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="da90a-128">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
