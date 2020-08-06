---
title: Metodo SetSecureConnectionLevel (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetSecureConnectionLevel (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetSecureConnectionLevel method
ms.assetid: 0fac7d5e-2670-4657-9439-331e7d93babb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4361f09eb38b3e5650b68ae6f86b7f2266bbf1a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722375"
---
# <a name="setsecureconnectionlevel-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="ad246-102">Metodo SetSecureConnectionLevel (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="ad246-102">SetSecureConnectionLevel Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="ad246-103">Imposta il livello di connessione protetta del server di report.</span><span class="sxs-lookup"><span data-stu-id="ad246-103">Sets the secure connection level of the report server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad246-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ad246-104">Syntax</span></span>  
  
```vb  
Public Sub SetSecureConnectionLevel(Level as Integer, _  
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetSecureConnectionLevel(Int32 Level,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad246-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ad246-105">Parameters</span></span>  
 <span data-ttu-id="ad246-106">*Level*</span><span class="sxs-lookup"><span data-stu-id="ad246-106">*Level*</span></span>  
 <span data-ttu-id="ad246-107">Valore intero che rappresenta un livello di connessione protetta.</span><span class="sxs-lookup"><span data-stu-id="ad246-107">An integer value representing a secure connection level.</span></span>  
  
 <span data-ttu-id="ad246-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="ad246-108">*HRESULT*</span></span>  
 <span data-ttu-id="ad246-109">[out] Valore che indica se la chiamata ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="ad246-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ad246-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ad246-110">Return Value</span></span>  
 <span data-ttu-id="ad246-111">Restituisce un *HRESULT* che indica l'esito positivo o negativo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="ad246-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="ad246-112">Un valore pari a 0 indica l'esito positivo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="ad246-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="ad246-113">Un valore diverso da zero indica che si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="ad246-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad246-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ad246-114">Remarks</span></span>  
 <span data-ttu-id="ad246-115">Quando viene chiamata, la proprietà SecureConnectionLevel del server di report è impostata sul valore specificato.</span><span class="sxs-lookup"><span data-stu-id="ad246-115">When called, the report server SecureConnectionLevel property is set to the value specified.</span></span> <span data-ttu-id="ad246-116">Il valore 0 indica che SSL è disattivato.</span><span class="sxs-lookup"><span data-stu-id="ad246-116">A value of 0 indicates that SSL is turned off.</span></span> <span data-ttu-id="ad246-117">Il valore maggiore di o pari a 1 indica che SSL è abilitato.</span><span class="sxs-lookup"><span data-stu-id="ad246-117">A value greater than or equal to 1 indicates that SSL is turned on.</span></span>  
  
-   <span data-ttu-id="ad246-118">Quando il valore è impostato, l'elemento SecureConnectionLevel nel file di configurazione del server di report viene modificato e l' `URLRoot` elemento nel file di configurazione viene impostato per utilizzare "https://" Se il *livello* specificato è maggiore o uguale a 1 oppure "http://" Se il *livello* specificato è 0.</span><span class="sxs-lookup"><span data-stu-id="ad246-118">When the value is set, the SecureConnectionLevel element in the report server configuration file is changed, and the `URLRoot` element in the configuration file is set to use "https://" if the specified *Level* is greater than or equal to 1, or "http://" if the specified *Level* is 0.</span></span>  
  
 <span data-ttu-id="ad246-119">In [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]SecureConnectionLevel diventa un'opzione di attivazione/disattivazione. Il valore predefinito è 0.</span><span class="sxs-lookup"><span data-stu-id="ad246-119">In [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], SecureConnectionLevel is made an on/off switch, default value is 0.</span></span> <span data-ttu-id="ad246-120">Per qualsiasi valore maggiore o uguale a 1 passato tramite l'API del metodo SetSecureConnectionLevel, SSL viene considerato abilitato e la proprietà di configurazione SecureConnectionLevel viene impostata di conseguenza nel file rsreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="ad246-120">For any value greater than or equal to 1 passed through SetSecureConnectionLevel method API, SSL is considered on and the configuration property SecureConnectionLevel is set accordingly in the rsreportserver.config file.</span></span> <span data-ttu-id="ad246-121">I valori 2 e 3 sono ancora consentiti per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="ad246-121">Values of 2 and 3 are still allowed for backward compatibility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad246-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ad246-122">Requirements</span></span>  
 <span data-ttu-id="ad246-123">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad246-123">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad246-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad246-124">See Also</span></span>  
 [<span data-ttu-id="ad246-125">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="ad246-125">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
