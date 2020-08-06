---
title: Metodo CreateSSLCertificateBinding (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- CreateSSLCertificateBinding
ms.assetid: 407d50e4-0a55-43cb-8ddf-2d82714071b1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8b9a5f9394d655f7b0592ea688a46f3ac2b9c153
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627635"
---
# <a name="createsslcertificatebinding-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="1e819-102">Metodo CreateSSLCertificateBinding (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="1e819-102">CreateSSLCertificateBinding Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="1e819-103">Crea un'associazione certificato SSL.</span><span class="sxs-lookup"><span data-stu-id="1e819-103">Creates an SSL Certificate binding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e819-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1e819-104">Syntax</span></span>  
  
```vb  
Public Sub CreateSSLCertificateBinding(ByVal Application As String, _  
    ByVal CertificateHash As String, ByVal IPAddress As String, _  
    ByVal Port As Int32, ByVal lcid As Int32, _  
    ByRef [Error] As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void CreateSSLCertificateBinding(string application,   
    string certificateHash, string IPAddress, int Port,   
    int lcid, out string error, out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e819-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1e819-105">Parameters</span></span>  
 <span data-ttu-id="1e819-106">*Applicazione*</span><span class="sxs-lookup"><span data-stu-id="1e819-106">*Application*</span></span>  
 <span data-ttu-id="1e819-107">Nome dell'applicazione per la quale l'associazione certificato deve essere creata.</span><span class="sxs-lookup"><span data-stu-id="1e819-107">The name of application that the certificate binding should be created for.</span></span>  
  
 <span data-ttu-id="1e819-108">*CertificateHash*</span><span class="sxs-lookup"><span data-stu-id="1e819-108">*CertificateHash*</span></span>  
 <span data-ttu-id="1e819-109">Hash per il certificato.</span><span class="sxs-lookup"><span data-stu-id="1e819-109">The hash for the certificate.</span></span>  
  
 <span data-ttu-id="1e819-110">*IPAddress*</span><span class="sxs-lookup"><span data-stu-id="1e819-110">*IPAddress*</span></span>  
 <span data-ttu-id="1e819-111">Indirizzo IP per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1e819-111">The IP address for the application.</span></span>  
  
 <span data-ttu-id="1e819-112">*Porta*</span><span class="sxs-lookup"><span data-stu-id="1e819-112">*Port*</span></span>  
 <span data-ttu-id="1e819-113">Porta SSL associata all'associazione.</span><span class="sxs-lookup"><span data-stu-id="1e819-113">The SSL port associated with the binding.</span></span>  
  
 <span data-ttu-id="1e819-114">*LCID*</span><span class="sxs-lookup"><span data-stu-id="1e819-114">*Lcid*</span></span>  
 <span data-ttu-id="1e819-115">Impostazioni locali da utilizzare per i messaggi di errore restituiti.</span><span class="sxs-lookup"><span data-stu-id="1e819-115">The locale to use for the error messages returned.</span></span>  
  
 <span data-ttu-id="1e819-116">*Error (Errore) (Error (Errore)e)*</span><span class="sxs-lookup"><span data-stu-id="1e819-116">*Error*</span></span>  
 <span data-ttu-id="1e819-117">[out] Descrizione degli errori che si sono verificati.</span><span class="sxs-lookup"><span data-stu-id="1e819-117">[out] The description of the errors that occurred.</span></span>  
  
 <span data-ttu-id="1e819-118">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="1e819-118">*HRESULT*</span></span>  
 <span data-ttu-id="1e819-119">[out] Valore che indica se la chiamata ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="1e819-119">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1e819-120">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1e819-120">Return Value</span></span>  
 <span data-ttu-id="1e819-121">Restituisce un *HRESULT* che indica l'esito positivo o negativo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="1e819-121">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="1e819-122">Il valore 0 indica l'esito positivo della chiamata al metodo, mentre un codice di errore ne indica l'esito negativo.</span><span class="sxs-lookup"><span data-stu-id="1e819-122">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e819-123">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1e819-123">Remarks</span></span>  
 <span data-ttu-id="1e819-124">Questo metodo aggiunge un'associazione a rsreportserver.config per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1e819-124">This method adds a binding to rsreportserver.config for the application.</span></span> <span data-ttu-id="1e819-125">Se in HTTP.SYS non esiste già un'associazione, questa viene creata.</span><span class="sxs-lookup"><span data-stu-id="1e819-125">If a binding does not already exist in HTTP.SYS, it is created there.</span></span>  
  
 <span data-ttu-id="1e819-126">Prima di creare l'associazione, la chiamata al metodo esamina le prenotazioni dell'URL affinché l'applicazione specificata determini se l'associazione certificato SSL è valida.</span><span class="sxs-lookup"><span data-stu-id="1e819-126">Before creating the binding, the method call examines the Url Reservations for the specified application to determine if the SSL Certificate Binding is valid.</span></span>  
  
 <span data-ttu-id="1e819-127">Le condizioni seguenti vengono convalidate e possono causare errori:</span><span class="sxs-lookup"><span data-stu-id="1e819-127">The following conditions are validated and can result in errors:</span></span>  
  
1.  <span data-ttu-id="1e819-128">Il certificato non esiste.</span><span class="sxs-lookup"><span data-stu-id="1e819-128">Certificate does not exist.</span></span>  
  
2.  <span data-ttu-id="1e819-129">Il valore IPAddress specificato non corrisponde al valore IPAddress di questo computer.</span><span class="sxs-lookup"><span data-stu-id="1e819-129">The IPAddress specified does not correspond to an IPAddress of this computer.</span></span>  
  
3.  <span data-ttu-id="1e819-130">Il valore IPAddress specificato è un IPAddress DHCP (che cambia periodicamente). Usare invece l'indirizzo IP con caratteri jolly (0.0.0.0).</span><span class="sxs-lookup"><span data-stu-id="1e819-130">The IPAddress specified is a DHCP IPAddress (changes periodically) - use the Wildcard IP address instead (0.0.0.0).</span></span>  
  
4.  <span data-ttu-id="1e819-131">Il valore IPAddress specificato non corrisponde all'indirizzo IP di una prenotazione URL E non esiste né un carattere jolly né la prenotazione URL del nome host.</span><span class="sxs-lookup"><span data-stu-id="1e819-131">IPAddress specified does not match the IP address of a URL reservations AND neither a wildcard or host name URL reservation exist.</span></span>  
  
5.  <span data-ttu-id="1e819-132">Esiste una prenotazione URL che specifica un nome host, ma il nome host non corrisponde al nome host del certificato.</span><span class="sxs-lookup"><span data-stu-id="1e819-132">A URL reservation that specifies a host name exists, but the host name does not match the certificate host name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e819-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1e819-133">Requirements</span></span>  
 <span data-ttu-id="1e819-134">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e819-134">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e819-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e819-135">See Also</span></span>  
 [<span data-ttu-id="1e819-136">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="1e819-136">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
