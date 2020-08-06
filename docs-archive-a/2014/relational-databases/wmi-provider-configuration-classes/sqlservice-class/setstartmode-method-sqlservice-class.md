---
title: Metodo SetStartMode (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStartMode Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStartMode method
ms.assetid: f6f198b4-f9a4-468c-8977-76462ef06e61
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: a9b7310623f526d7b106485ed9681df3aa100129
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623957"
---
# <a name="setstartmode-method-sqlservice-class"></a><span data-ttu-id="fa6c3-102">Metodo SetStartMode (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="fa6c3-102">SetStartMode Method (SqlService Class)</span></span>
  <span data-ttu-id="fa6c3-103">Modifica la modalità di avvio dell'istanza del servizio.</span><span class="sxs-lookup"><span data-stu-id="fa6c3-103">Modifies the start mode of the service instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa6c3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fa6c3-104">Syntax</span></span>  
  
```  
  
object  
.SetStartMode(  
StartMode  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="fa6c3-105">Parti</span><span class="sxs-lookup"><span data-stu-id="fa6c3-105">Parts</span></span>  
 <span data-ttu-id="fa6c3-106">*object*</span><span class="sxs-lookup"><span data-stu-id="fa6c3-106">*object*</span></span>  
 <span data-ttu-id="fa6c3-107">Oggetto della [classe SqlService](sqlservice-class.md) che rappresenta il servizio.</span><span class="sxs-lookup"><span data-stu-id="fa6c3-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="fa6c3-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="fa6c3-108">Parameters</span></span>  
 <span data-ttu-id="fa6c3-109">*Modalità avvio*</span><span class="sxs-lookup"><span data-stu-id="fa6c3-109">*StartMode*</span></span>  
 <span data-ttu-id="fa6c3-110">Valore `uint32` che specifica la modalità di avvio dell'istanza del servizio.</span><span class="sxs-lookup"><span data-stu-id="fa6c3-110">A `uint32` value that specifies the start mode of the service instance.</span></span>  
  
 <span data-ttu-id="fa6c3-111">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="fa6c3-111">The valid values are as follows:</span></span>  
  
 <span data-ttu-id="fa6c3-112">Valore = 0.</span><span class="sxs-lookup"><span data-stu-id="fa6c3-112">Value = 0.</span></span> <span data-ttu-id="fa6c3-113">Boot: driver di dispositivo avviato dal caricatore del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="fa6c3-113">Boot - Device driver started by the operating system loader.</span></span> <span data-ttu-id="fa6c3-114">Questo valore è valido solo per i servizi del driver.</span><span class="sxs-lookup"><span data-stu-id="fa6c3-114">This value is valid only for driver services.</span></span>  
  
 <span data-ttu-id="fa6c3-115">Valore = 1.</span><span class="sxs-lookup"><span data-stu-id="fa6c3-115">Value = 1.</span></span> <span data-ttu-id="fa6c3-116">System: driver di dispositivo avviato dal metodo `IoInitSystem`.</span><span class="sxs-lookup"><span data-stu-id="fa6c3-116">System - Device driver started by the `IoInitSystem` method.</span></span> <span data-ttu-id="fa6c3-117">Questo valore è valido solo per i servizi del driver.</span><span class="sxs-lookup"><span data-stu-id="fa6c3-117">This value is valid only for driver services.</span></span>  
  
 <span data-ttu-id="fa6c3-118">Valore = 2.</span><span class="sxs-lookup"><span data-stu-id="fa6c3-118">Value = 2.</span></span> <span data-ttu-id="fa6c3-119">Automatic: servizio da avviare automaticamente da Gestione controllo servizi durante l'avvio del sistema.</span><span class="sxs-lookup"><span data-stu-id="fa6c3-119">Automatic - Service to be started automatically by the service control manager during system startup.</span></span>  
  
 <span data-ttu-id="fa6c3-120">Valore = 3.</span><span class="sxs-lookup"><span data-stu-id="fa6c3-120">Value = 3.</span></span> <span data-ttu-id="fa6c3-121">Manual: servizio da avviare da Gestione computer quando un processo chiama il metodo `StartService`.</span><span class="sxs-lookup"><span data-stu-id="fa6c3-121">Manual - Service to be started by the Computer Manager when a process calls the `StartService` method.</span></span>  
  
 <span data-ttu-id="fa6c3-122">Valore = 4.</span><span class="sxs-lookup"><span data-stu-id="fa6c3-122">Value = 4.</span></span> <span data-ttu-id="fa6c3-123">Disabled: impossibile avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="fa6c3-123">Disabled - Service can no longer be started.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="fa6c3-124">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fa6c3-124">Property Value/Return Value</span></span>  
 <span data-ttu-id="fa6c3-125">Valore `uint32` che è 0 se il servizio è stato modificato correttamente 0 1 se la richiesta non è supportata.</span><span class="sxs-lookup"><span data-stu-id="fa6c3-125">A `uint32` value, which is 0 if the service was successfully modified or 1 if the request is not supported.</span></span> <span data-ttu-id="fa6c3-126">Qualsiasi altro numero indica un errore.</span><span class="sxs-lookup"><span data-stu-id="fa6c3-126">Any other number indicates an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa6c3-127">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fa6c3-127">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa6c3-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa6c3-128">See Also</span></span>  
 <span data-ttu-id="fa6c3-129">[Avvio e arresto di servizi](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="fa6c3-129">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
