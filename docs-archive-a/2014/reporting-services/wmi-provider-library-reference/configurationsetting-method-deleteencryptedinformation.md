---
title: Metodo DeleteEncryptedInformation (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DeleteEncryptedInformation (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DeleteEncryptedInformation method
ms.assetid: c14ed187-bdd9-4304-88e3-72072f03c21b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d00dc3e90816cd04c84f124cdc3d25a9ac122bba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627633"
---
# <a name="deleteencryptedinformation-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="a3613-102">Metodo DeleteEncryptedInformation (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="a3613-102">DeleteEncryptedInformation Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="a3613-103">Elimina le informazioni crittografate dal database del server di report.</span><span class="sxs-lookup"><span data-stu-id="a3613-103">Deletes the encrypted information from the report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3613-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a3613-104">Syntax</span></span>  
  
```vb  
Public Sub DeleteEncryptedInformation(ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void DeleteEncryptedInformation(out Int32 HRESULT, out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3613-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a3613-105">Parameters</span></span>  
 <span data-ttu-id="a3613-106">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="a3613-106">*HRESULT*</span></span>  
 <span data-ttu-id="a3613-107">[out] Valore che indica se la chiamata ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="a3613-107">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="a3613-108">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="a3613-108">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="a3613-109">[out] Matrice di stringhe che contiene errori aggiuntivi restituiti dalla chiamata.</span><span class="sxs-lookup"><span data-stu-id="a3613-109">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3613-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a3613-110">Return Value</span></span>  
 <span data-ttu-id="a3613-111">Restituisce un *HRESULT* che indica l'esito positivo o negativo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="a3613-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="a3613-112">Un valore pari a 0 indica l'esito positivo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="a3613-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="a3613-113">Un valore diverso da zero indica che si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="a3613-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3613-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a3613-114">Remarks</span></span>  
 <span data-ttu-id="a3613-115">Quando viene richiamato questo metodo, i seguenti dati vengono eliminati:</span><span class="sxs-lookup"><span data-stu-id="a3613-115">When this method is invoked, the following data is deleted:</span></span>  
  
-   <span data-ttu-id="a3613-116">Informazioni sulle origini dati crittografate, tra cui nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="a3613-116">Data source information that is encrypted, including user name and password.</span></span>  
  
-   <span data-ttu-id="a3613-117">Dati della sottoscrizione crittografati tramite le interfacce dell'estensione per il recapito.</span><span class="sxs-lookup"><span data-stu-id="a3613-117">Subscription data that is encrypted using the delivery extension interfaces.</span></span>  
  
-   <span data-ttu-id="a3613-118">Tutte le informazioni della tabella delle chiavi nel database del server di report.</span><span class="sxs-lookup"><span data-stu-id="a3613-118">All the information from the keys table in the report server database.</span></span>  
  
 <span data-ttu-id="a3613-119">Una volta richiamato questo metodo, l'utente deve inizializzare ogni computer che utilizza il database del server di report.</span><span class="sxs-lookup"><span data-stu-id="a3613-119">After this method is invoked, the user must initialize each computer that uses the report server database.</span></span>  
  
 <span data-ttu-id="a3613-120">La chiamata al metodo DeleteEncryptedInformation non influisce sul file di configurazione del server di report.</span><span class="sxs-lookup"><span data-stu-id="a3613-120">Calling the DeleteEncryptedInformation method does not affect the report server configuration file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3613-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a3613-121">Requirements</span></span>  
 <span data-ttu-id="a3613-122">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3613-122">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3613-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3613-123">See Also</span></span>  
 [<span data-ttu-id="a3613-124">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="a3613-124">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
