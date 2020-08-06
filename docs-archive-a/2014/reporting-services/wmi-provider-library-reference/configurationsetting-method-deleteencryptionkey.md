---
title: Metodo DeleteEncryptionKey (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DeleteEncryptionKey (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DeleteEncryptionKey method
ms.assetid: ed2f25b6-6a63-468d-9279-a577ca01b096
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0e302659615bd620b3b0ed802b83aafc4e9506d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627626"
---
# <a name="deleteencryptionkey-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="77640-102">Metodo DeleteEncryptionKey (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="77640-102">DeleteEncryptionKey Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="77640-103">Elimina le chiavi di crittografia dal database del server di report.</span><span class="sxs-lookup"><span data-stu-id="77640-103">Deletes the encryption keys from the report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77640-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="77640-104">Syntax</span></span>  
  
```vb  
Public Sub DeleteEncryptionKeys(ByVal InstallationID As String, _  
    ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void DeleteEncryptionKeys(string InstallationID, out Int32 HRESULT,   
    out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77640-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="77640-105">Parameters</span></span>  
 <span data-ttu-id="77640-106">*InstallationID*</span><span class="sxs-lookup"><span data-stu-id="77640-106">*InstallationID*</span></span>  
 <span data-ttu-id="77640-107">ID di installazione di un server di report che è presente nella tabella delle chiavi del database del server di report.</span><span class="sxs-lookup"><span data-stu-id="77640-107">The installation ID of a report server that is in the keys table of the report server database.</span></span>  
  
 <span data-ttu-id="77640-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="77640-108">*HRESULT*</span></span>  
 <span data-ttu-id="77640-109">[out] Valore che indica se la chiamata ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="77640-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="77640-110">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="77640-110">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="77640-111">[out] Matrice di stringhe che contiene errori aggiuntivi restituiti dalla chiamata.</span><span class="sxs-lookup"><span data-stu-id="77640-111">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="77640-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="77640-112">Return Value</span></span>  
 <span data-ttu-id="77640-113">Restituisce un valore HRESULT che indica l'esito positivo o negativo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="77640-113">Returns an HRESULT indicating success or failure of the method call.</span></span> <span data-ttu-id="77640-114">Un valore pari a 0 indica l'esito positivo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="77640-114">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="77640-115">Un valore diverso da zero indica che si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="77640-115">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77640-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="77640-116">Remarks</span></span>  
 <span data-ttu-id="77640-117">Il metodo *DeleteEncryptionKey* elimina dalla tabella delle chiavi le voci relative ai server di report che dispongono dell'accesso alle informazioni protette nel database del server di report.</span><span class="sxs-lookup"><span data-stu-id="77640-117">The *DeleteEncryptionKey* method deletes entries from the keys table for any report servers that have access to the secure information in the report server database.</span></span> <span data-ttu-id="77640-118">Se il parametro *InstallationID* specificato non corrisponde a un ID di installazione nel database, il metodo restituisce un errore.</span><span class="sxs-lookup"><span data-stu-id="77640-118">If the *InstallationID* parameter specified does not correspond to an installation ID in the database, the method returns an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77640-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="77640-119">Requirements</span></span>  
 <span data-ttu-id="77640-120">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77640-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77640-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77640-121">See Also</span></span>  
 [<span data-ttu-id="77640-122">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="77640-122">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
