---
title: Metodo RestoreEncryptionKey (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- RestoreEncryptionKey (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- RestoreEncryptionKey method
ms.assetid: 37e949f5-15af-4858-848a-f482ee94fcd9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e67478541bab615a6d441ae273ed3385a8654203
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722392"
---
# <a name="restoreencryptionkey-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="538c9-102">Metodo RestoreEncryptionKey (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="538c9-102">RestoreEncryptionKey Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="538c9-103">Riapplica la chiave di crittografia specificata al database del server di report.</span><span class="sxs-lookup"><span data-stu-id="538c9-103">Reapplies the specified encryption key to the report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="538c9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="538c9-104">Syntax</span></span>  
  
```vb  
Public Sub RestoreEncryptionKey(ByRef KeyFile() As Integer, _  
    ByRef Length As Int32, ByVal Password As String, _  
    ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void RestoreEncryptionKey(out Byte[] KeyFile, out Int32 Length,   
            string Password, out Int32 HRESULT, out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="538c9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="538c9-105">Parameters</span></span>  
 <span data-ttu-id="538c9-106">*KeyFile[]*</span><span class="sxs-lookup"><span data-stu-id="538c9-106">*KeyFile[]*</span></span>  
 <span data-ttu-id="538c9-107">[out] Matrice che contiene la chiave di crittografia crittografata.</span><span class="sxs-lookup"><span data-stu-id="538c9-107">[out] An array containing the encrypted encryption key.</span></span>  
  
 <span data-ttu-id="538c9-108">*Lunghezza*</span><span class="sxs-lookup"><span data-stu-id="538c9-108">*Length*</span></span>  
 <span data-ttu-id="538c9-109">[out] Lunghezza della matrice restituita dal metodo.</span><span class="sxs-lookup"><span data-stu-id="538c9-109">[out] The length of the array returned by the method.</span></span>  
  
 <span data-ttu-id="538c9-110">*Password*</span><span class="sxs-lookup"><span data-stu-id="538c9-110">*Password*</span></span>  
 <span data-ttu-id="538c9-111">Stringa utilizzata per crittografare la chiave di crittografia.</span><span class="sxs-lookup"><span data-stu-id="538c9-111">A string used to encrypt the encryption key.</span></span>  
  
 <span data-ttu-id="538c9-112">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="538c9-112">*HRESULT*</span></span>  
 <span data-ttu-id="538c9-113">[out] Valore che indica se la chiamata ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="538c9-113">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="538c9-114">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="538c9-114">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="538c9-115">[out] Matrice di stringhe che contiene errori aggiuntivi restituiti dalla chiamata.</span><span class="sxs-lookup"><span data-stu-id="538c9-115">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="538c9-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="538c9-116">Return Value</span></span>  
 <span data-ttu-id="538c9-117">Restituisce un *HRESULT* che indica l'esito positivo o negativo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="538c9-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="538c9-118">Un valore pari a 0 indica l'esito positivo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="538c9-118">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="538c9-119">Un valore diverso da zero indica che si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="538c9-119">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="538c9-120">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="538c9-120">Remarks</span></span>  
 <span data-ttu-id="538c9-121">Se nel database del server di report esiste già una voce per il server di report , viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="538c9-121">If an entry already exists for the report server in the report server database, it is deleted.</span></span> <span data-ttu-id="538c9-122">La nuova voce viene quindi creata usando la chiave di crittografia specificata e la chiave pubblica del server di report.</span><span class="sxs-lookup"><span data-stu-id="538c9-122">The new entry is then created using the specified encryption key and the report server's public key.</span></span>  
  
 <span data-ttu-id="538c9-123">Il metodo è più efficace se viene chiamato dopo il metodo [DeleteEncryptionKey](configurationsetting-method-deleteencryptionkey.md) , che svuota l'elenco delle chiavi di crittografia.</span><span class="sxs-lookup"><span data-stu-id="538c9-123">The method is most effective when called after the [DeleteEncryptionKey](configurationsetting-method-deleteencryptionkey.md) method, which clears the list of encryption keys.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="538c9-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="538c9-124">Requirements</span></span>  
 <span data-ttu-id="538c9-125">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="538c9-125">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="538c9-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="538c9-126">See Also</span></span>  
 [<span data-ttu-id="538c9-127">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="538c9-127">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
