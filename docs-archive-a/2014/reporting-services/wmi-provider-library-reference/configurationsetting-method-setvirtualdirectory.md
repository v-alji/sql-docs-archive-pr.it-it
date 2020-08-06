---
title: Metodo SetVirtualDirectory (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- SetVirtualDirectory method
ms.assetid: 1a25cb1d-38d5-401a-970b-87b642a780e4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7f45181f3f6a791f5cb64a7519285b6d2a87dd36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722360"
---
# <a name="setvirtualdirectory-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="572f2-102">Metodo SetVirtualDirectory (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="572f2-102">SetVirtualDirectory Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="572f2-103">Imposta il nome della directory virtuale di una determinata applicazione.</span><span class="sxs-lookup"><span data-stu-id="572f2-103">Sets the name of the virtual directory for a given application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="572f2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="572f2-104">Syntax</span></span>  
  
```vb  
Public Sub SetVirtualDirectory(ByVal Application As String, _  
    ByVal VirtualDirectory As String, ByVal lcid As Int32, _  
    ByRef [Error] As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void SetVirtualDirectory(string Application, string VirtualDirectory,   
       int Lcid,out string Error, out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="572f2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="572f2-105">Parameters</span></span>  
 <span data-ttu-id="572f2-106">*Applicazione*</span><span class="sxs-lookup"><span data-stu-id="572f2-106">*Application*</span></span>  
 <span data-ttu-id="572f2-107">Nome dell'applicazione per cui impostare la directory virtuale.</span><span class="sxs-lookup"><span data-stu-id="572f2-107">The name of application for which to set the virtual directory.</span></span>  
  
 <span data-ttu-id="572f2-108">*VirtualDirectory*</span><span class="sxs-lookup"><span data-stu-id="572f2-108">*VirtualDirectory*</span></span>  
 <span data-ttu-id="572f2-109">Nome della directory virtuale.</span><span class="sxs-lookup"><span data-stu-id="572f2-109">The name of the virtual directory.</span></span>  
  
 <span data-ttu-id="572f2-110">*lcid*</span><span class="sxs-lookup"><span data-stu-id="572f2-110">*lcid*</span></span>  
 <span data-ttu-id="572f2-111">ID impostazioni locali della directory virtuale.</span><span class="sxs-lookup"><span data-stu-id="572f2-111">The locale id for the virtual directory.</span></span>  
  
 <span data-ttu-id="572f2-112">*Error (Errore) (Error (Errore)e)*</span><span class="sxs-lookup"><span data-stu-id="572f2-112">*Error*</span></span>  
 <span data-ttu-id="572f2-113">[out] Descrizione dell'errore che si è verificato.</span><span class="sxs-lookup"><span data-stu-id="572f2-113">[out] The description of the error that occurred.</span></span>  
  
 <span data-ttu-id="572f2-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="572f2-114">*HRESULT*</span></span>  
 <span data-ttu-id="572f2-115">[out] Valore che indica se la chiamata ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="572f2-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="572f2-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="572f2-116">Return Value</span></span>  
 <span data-ttu-id="572f2-117">Restituisce un *HRESULT* che indica l'esito positivo o negativo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="572f2-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="572f2-118">Il valore 0 indica l'esito positivo della chiamata al metodo, mentre un codice di errore ne indica l'esito negativo.</span><span class="sxs-lookup"><span data-stu-id="572f2-118">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="572f2-119">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="572f2-119">Remarks</span></span>  
 <span data-ttu-id="572f2-120">Un'applicazione può disporre di un solo nome della directory virtuale per tutte le prenotazioni URL.</span><span class="sxs-lookup"><span data-stu-id="572f2-120">An application can have only one virtual directory name for all URL reservations.</span></span>  
  
 <span data-ttu-id="572f2-121">VirtualDirectory deve essere conforme alle convenzioni di denominazione per le directory virtuali.</span><span class="sxs-lookup"><span data-stu-id="572f2-121">VirtualDirectory must conform to naming conventions for virtual directories.</span></span> <span data-ttu-id="572f2-122">VirtualDirectory non deve essere stringa vuota o spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="572f2-122">VirtualDirectory must not be empty string or blank.</span></span>  
  
 <span data-ttu-id="572f2-123">Aggiorna il valore dell'elemento \Configuration\URLReservations\Application\VirtualDirectory.</span><span class="sxs-lookup"><span data-stu-id="572f2-123">Updates the value of the \Configuration\URLReservations\Application\VirtualDirectory element.</span></span> <span data-ttu-id="572f2-124">Ha esito positivo anche se non è stata ancora creata alcuna prenotazione URL.</span><span class="sxs-lookup"><span data-stu-id="572f2-124">Succeeds even if no URL reservations have been created yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="572f2-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="572f2-125">Requirements</span></span>  
 <span data-ttu-id="572f2-126">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="572f2-126">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="572f2-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="572f2-127">See Also</span></span>  
 [<span data-ttu-id="572f2-128">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="572f2-128">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
