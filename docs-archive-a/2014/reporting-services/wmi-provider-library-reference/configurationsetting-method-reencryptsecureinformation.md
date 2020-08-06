---
title: Metodo ReencryptSecureInformation (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- ReencryptSecureInformation (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- ReencryptSecureInformation method
ms.assetid: 8a487497-c207-45b2-8c92-87c58cc68716
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1a0c657b69d624df8895ae4d5a6d12277b011b24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635411"
---
# <a name="reencryptsecureinformation-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="1607c-102">Metodo ReencryptSecureInformation (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="1607c-102">ReencryptSecureInformation Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="1607c-103">Genera una nuova chiave di crittografia e la utilizza per crittografare nuovamente tutte le informazioni protette contenute nel catalogo.</span><span class="sxs-lookup"><span data-stu-id="1607c-103">Generates a new encryption key and re-encrypts all secure information in the catalog using this new key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1607c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1607c-104">Syntax</span></span>  
  
```vb  
Public Sub ReencryptSecureInformation(ByRef HRESULT as Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void ReencryptSecureInformation (out Int32 HRESULT, out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1607c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1607c-105">Parameters</span></span>  
 <span data-ttu-id="1607c-106">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="1607c-106">*HRESULT*</span></span>  
 <span data-ttu-id="1607c-107">[out] Valore che indica se la chiamata ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="1607c-107">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="1607c-108">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="1607c-108">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="1607c-109">[out] Matrice di stringhe che contiene errori aggiuntivi restituiti dalla chiamata.</span><span class="sxs-lookup"><span data-stu-id="1607c-109">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1607c-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1607c-110">Return Value</span></span>  
 <span data-ttu-id="1607c-111">Restituisce un *HRESULT* che indica l'esito positivo o negativo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="1607c-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="1607c-112">Un valore pari a 0 indica l'esito positivo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="1607c-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="1607c-113">Un valore diverso da zero indica che si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="1607c-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1607c-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1607c-114">Remarks</span></span>  
 <span data-ttu-id="1607c-115">Il metodo ReencryptSecureInformation consente all'amministratore di sostituire la chiave di crittografia esistente con una nuova chiave.</span><span class="sxs-lookup"><span data-stu-id="1607c-115">The ReencryptSecureInformation method allows the administrator to replace the existing encryption key with a new key.</span></span>  
  
 <span data-ttu-id="1607c-116">Quando viene richiamato questo metodo, il server di report genera una nuova chiave di crittografia e scorre tutto il contenuto crittografato per crittografarlo nuovamente con la nuova chiave di crittografia.</span><span class="sxs-lookup"><span data-stu-id="1607c-116">When this method is invoked, the report server generates a new encryption key and iterates through all encrypted content to re-encrypt it with the new encryption key.</span></span>  
  
 <span data-ttu-id="1607c-117">Le estensioni per il recapito possono archiviare informazioni protette nelle relative strutture delle impostazioni per il recapito.</span><span class="sxs-lookup"><span data-stu-id="1607c-117">Delivery extensions can store secured information in their delivery settings structures.</span></span> <span data-ttu-id="1607c-118">Quando viene chiamato ReencryptSecureInformation, il server di report carica ciascuna sottoscrizione e l'estensione per il recapito corrispondente per crittografare nuovamente le informazioni archiviate nelle impostazioni associate.</span><span class="sxs-lookup"><span data-stu-id="1607c-118">When ReencryptSecureInformation is called, the report server loads each subscription and the corresponding delivery extension to re-encrypt information stored in the associated settings.</span></span>  
  
 <span data-ttu-id="1607c-119">Se questo metodo viene eseguito in un computer in una distribuzione con scalabilità orizzontale, ciascun computer nella distribuzione dovrà essere inizializzato nuovamente.</span><span class="sxs-lookup"><span data-stu-id="1607c-119">If this method is run on a computer in a scale-out deployment, each computer in the scale-out deployment will need to be initialized again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1607c-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1607c-120">Requirements</span></span>  
 <span data-ttu-id="1607c-121">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1607c-121">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1607c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1607c-122">See Also</span></span>  
 [<span data-ttu-id="1607c-123">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="1607c-123">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
