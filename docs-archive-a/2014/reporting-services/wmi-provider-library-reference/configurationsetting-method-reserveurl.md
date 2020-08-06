---
title: Metodo ReserveURL (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ReservedURL method
ms.assetid: b9008a62-3edd-4f8a-99f2-7598c2133899
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 95a58938ada19b4e49f094e3d8d01b241f1a4286
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722395"
---
# <a name="reserveurl-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="03dcc-102">Metodo ReserveURL (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="03dcc-102">ReserveURL Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="03dcc-103">Aggiunge una prenotazione URL per un'applicazione specifica.</span><span class="sxs-lookup"><span data-stu-id="03dcc-103">Adds a URL reservation for a given application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03dcc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="03dcc-104">Syntax</span></span>  
  
```vb  
Public Sub ReserveURL(Application as String, _  
    UrlString as String, Lcid as Int32, _   
    ByRef [Error] as String, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void ReserveURL(string Application, string UrlString, int Lcid,   
    out string error, out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03dcc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="03dcc-105">Parameters</span></span>  
 <span data-ttu-id="03dcc-106">*Applicazione*</span><span class="sxs-lookup"><span data-stu-id="03dcc-106">*Application*</span></span>  
 <span data-ttu-id="03dcc-107">Nome dell'applicazione per la quale riservare l'URL.</span><span class="sxs-lookup"><span data-stu-id="03dcc-107">The name of application to reserve the URL for.</span></span>  
  
 <span data-ttu-id="03dcc-108">*URLString*</span><span class="sxs-lookup"><span data-stu-id="03dcc-108">*URLString*</span></span>  
 <span data-ttu-id="03dcc-109">URL per la prenotazione.</span><span class="sxs-lookup"><span data-stu-id="03dcc-109">The URL for the reservation.</span></span>  
  
 <span data-ttu-id="03dcc-110">*lcid*</span><span class="sxs-lookup"><span data-stu-id="03dcc-110">*lcid*</span></span>  
 <span data-ttu-id="03dcc-111">Impostazioni locali da utilizzare per i messaggi di errore restituiti.</span><span class="sxs-lookup"><span data-stu-id="03dcc-111">The locale to use for the error messages returned.</span></span>  
  
 <span data-ttu-id="03dcc-112">*Error (Errore) (Error (Errore)e)*</span><span class="sxs-lookup"><span data-stu-id="03dcc-112">*Error*</span></span>  
 <span data-ttu-id="03dcc-113">[out] Descrizione dell'errore che si è verificato.</span><span class="sxs-lookup"><span data-stu-id="03dcc-113">[out] The description of the error that occurred.</span></span>  
  
 <span data-ttu-id="03dcc-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="03dcc-114">*HRESULT*</span></span>  
 <span data-ttu-id="03dcc-115">[out] Valore che indica se la chiamata ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="03dcc-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="03dcc-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="03dcc-116">Return Value</span></span>  
 <span data-ttu-id="03dcc-117">Restituisce un *HRESULT* che indica l'esito positivo o negativo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="03dcc-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="03dcc-118">Il valore 0 indica l'esito positivo della chiamata al metodo, mentre un codice di errore ne indica l'esito negativo.</span><span class="sxs-lookup"><span data-stu-id="03dcc-118">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03dcc-119">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="03dcc-119">Remarks</span></span>  
 <span data-ttu-id="03dcc-120">*UrlString* non include il nome della directory virtuale.</span><span class="sxs-lookup"><span data-stu-id="03dcc-120">*UrlString* does not include the virtual directory name.</span></span> <span data-ttu-id="03dcc-121">A tal fine, viene fornito il metodo [SetVirtualDirectory](configurationsetting-method-setvirtualdirectory.md) .</span><span class="sxs-lookup"><span data-stu-id="03dcc-121">The [SetVirtualDirectory](configurationsetting-method-setvirtualdirectory.md) method is provided for that purpose.</span></span>  
  
 <span data-ttu-id="03dcc-122">Le prenotazioni URL vengono create per l'account del servizio Windows corrente.</span><span class="sxs-lookup"><span data-stu-id="03dcc-122">URL reservations are created for the current windows service account.</span></span> <span data-ttu-id="03dcc-123">La modifica dell'account del servizio Windows richiede l'aggiornamento manuale di tutte le prenotazioni URL.</span><span class="sxs-lookup"><span data-stu-id="03dcc-123">Changing the windows service account requires updating all the URL reservations manually.</span></span>  
  
 <span data-ttu-id="03dcc-124">Questo metodo causa l'esecuzione dell'operazione di riciclo pesante da parte di tutti i domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="03dcc-124">This method causes all application domains to hard recycle.</span></span> <span data-ttu-id="03dcc-125">Una volta completata l'operazione, i domini applicazione vengono riavviati.</span><span class="sxs-lookup"><span data-stu-id="03dcc-125">Application domains are restarted after this operation is complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03dcc-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="03dcc-126">Requirements</span></span>  
 <span data-ttu-id="03dcc-127">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03dcc-127">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03dcc-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03dcc-128">See Also</span></span>  
 [<span data-ttu-id="03dcc-129">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="03dcc-129">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
