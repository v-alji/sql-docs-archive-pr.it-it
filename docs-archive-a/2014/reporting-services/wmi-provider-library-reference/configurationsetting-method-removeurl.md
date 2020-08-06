---
title: Metodo RemoveURL (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- RemoveURL method
ms.assetid: 3d98bd97-e152-48ce-ab1c-bd2c4f8b7fe9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3a32989e8ce8986b785e829d8cc7fcf58fbbf240
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629715"
---
# <a name="removeurl-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="27ca5-102">Metodo RemoveURL (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="27ca5-102">RemoveURL Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="27ca5-103">Rimuove un URL riservato per il server di report.</span><span class="sxs-lookup"><span data-stu-id="27ca5-103">Removes a URL reserved for the report server.</span></span> <span data-ttu-id="27ca5-104">Se è necessario rimuovere più URL, devono essere rimossi uno per volta chiamando questa API.</span><span class="sxs-lookup"><span data-stu-id="27ca5-104">If there are multiple URLs that need to be removed, this must be done one by one calling this API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27ca5-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="27ca5-105">Syntax</span></span>  
  
```vb  
Public Sub RemoveURL(ByVal Application As String, _  
    ByVal UrlString As String, ByVal Lcid As Int32, _  
    ByRef [Error] As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void RemoveURL(string Application, string UrlString, int Lcid,   
    out string Error, out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27ca5-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="27ca5-106">Parameters</span></span>  
 <span data-ttu-id="27ca5-107">*Applicazione*</span><span class="sxs-lookup"><span data-stu-id="27ca5-107">*Application*</span></span>  
 <span data-ttu-id="27ca5-108">Nome dell'applicazione per cui rimuovere la prenotazione.</span><span class="sxs-lookup"><span data-stu-id="27ca5-108">The name of application for which to remove the reservation.</span></span>  
  
 <span data-ttu-id="27ca5-109">*URLString*</span><span class="sxs-lookup"><span data-stu-id="27ca5-109">*URLString*</span></span>  
 <span data-ttu-id="27ca5-110">URL per la prenotazione.</span><span class="sxs-lookup"><span data-stu-id="27ca5-110">The URL for the reservation.</span></span>  
  
 <span data-ttu-id="27ca5-111">*lcid*</span><span class="sxs-lookup"><span data-stu-id="27ca5-111">*lcid*</span></span>  
 <span data-ttu-id="27ca5-112">Impostazioni locali da utilizzare per i messaggi di errore restituiti.</span><span class="sxs-lookup"><span data-stu-id="27ca5-112">The locale to use for the error messages returned.</span></span>  
  
 <span data-ttu-id="27ca5-113">*Error (Errore) (Error (Errore)e)*</span><span class="sxs-lookup"><span data-stu-id="27ca5-113">*Error*</span></span>  
 <span data-ttu-id="27ca5-114">[out] Descrizione dell'errore che si è verificato.</span><span class="sxs-lookup"><span data-stu-id="27ca5-114">[out] The description of the error that occurred.</span></span>  
  
 <span data-ttu-id="27ca5-115">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="27ca5-115">*HRESULT*</span></span>  
 <span data-ttu-id="27ca5-116">[out] Valore che indica se la chiamata ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="27ca5-116">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27ca5-117">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="27ca5-117">Return Value</span></span>  
 <span data-ttu-id="27ca5-118">Restituisce un *HRESULT* che indica l'esito positivo o negativo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="27ca5-118">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="27ca5-119">Il valore 0 indica l'esito positivo della chiamata al metodo, mentre un codice di errore ne indica l'esito negativo.</span><span class="sxs-lookup"><span data-stu-id="27ca5-119">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27ca5-120">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="27ca5-120">Remarks</span></span>  
 <span data-ttu-id="27ca5-121">*UrlString* non include il nome della directory virtuale. A tale scopo è disponibile il [metodo SetVirtualDirectory &#40;MSReportServer_ConfigurationSetting WMI&#41;](configurationsetting-method-setvirtualdirectory.md).</span><span class="sxs-lookup"><span data-stu-id="27ca5-121">*UrlString* does not include the Virtual Directory name - the [SetVirtualDirectory Method &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setvirtualdirectory.md) method is provided for that purpose.</span></span>  
  
 <span data-ttu-id="27ca5-122">Prima di chiamare il metodo [ReserveURL](configurationsetting-method-reserveurl.md) , è necessario specificare un valore per la proprietà di configurazione VirtualDirectory relativa al parametro *Applicazione* .</span><span class="sxs-lookup"><span data-stu-id="27ca5-122">Before calling the [ReserveURL](configurationsetting-method-reserveurl.md) method, you must supply a value for the VirtualDirectory configuration property for the *Application* parameter.</span></span> <span data-ttu-id="27ca5-123">Usare il [Metodo SetVirtualDirectory &#40;MSReportServer_ConfigurationSetting WMI&#41;](configurationsetting-method-setvirtualdirectory.md) per impostare la proprietà VirtualDirectory.</span><span class="sxs-lookup"><span data-stu-id="27ca5-123">Use the [SetVirtualDirectory Method &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setvirtualdirectory.md) method to set the VirtualDirectory property.</span></span>  
  
 <span data-ttu-id="27ca5-124">Se [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] ha reso disponibile un Certificato SSL e nessun altro URL lo richiede, il certificato verrà rimosso.</span><span class="sxs-lookup"><span data-stu-id="27ca5-124">If an SSL Certificate was provisioned by [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and no other URLs need it, it is removed.</span></span>  
  
 <span data-ttu-id="27ca5-125">Tramite questo metodo tutti i domini di applicazione non relativi alla configurazione eseguono un riciclo pesante e si arrestano durante questa operazione; una volta completata l'operazione, i domini di applicazione vengono riavviati.</span><span class="sxs-lookup"><span data-stu-id="27ca5-125">This method causes all non-configuration app domains to hard recycle and stop during this operation; app domains are restarted after this operation complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27ca5-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="27ca5-126">Requirements</span></span>  
 <span data-ttu-id="27ca5-127">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27ca5-127">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27ca5-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27ca5-128">See Also</span></span>  
 [<span data-ttu-id="27ca5-129">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="27ca5-129">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
