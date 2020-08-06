---
title: Proprietà StartMode (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- StartMode Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- StartMode property
ms.assetid: c0c2c7f8-d4ae-44f2-ad8e-aecfcb7c2878
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: bafffcc3c8f82f69896d0a22e9b0a9060e04cd10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717621"
---
# <a name="startmode-property-sqlservice-class"></a><span data-ttu-id="d4b00-102">Proprietà StartMode (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="d4b00-102">StartMode Property (SqlService Class)</span></span>
  <span data-ttu-id="d4b00-103">Ottiene la modalità di avvio del servizio.</span><span class="sxs-lookup"><span data-stu-id="d4b00-103">Gets the start mode of the service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4b00-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d4b00-104">Syntax</span></span>  
  
```  
  
object  
.StartMode [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="d4b00-105">Parti</span><span class="sxs-lookup"><span data-stu-id="d4b00-105">Parts</span></span>  
 <span data-ttu-id="d4b00-106">*object*</span><span class="sxs-lookup"><span data-stu-id="d4b00-106">*object*</span></span>  
 <span data-ttu-id="d4b00-107">Oggetto della [classe SqlService](sqlservice-class.md) che rappresenta il servizio.</span><span class="sxs-lookup"><span data-stu-id="d4b00-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d4b00-108">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d4b00-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="d4b00-109">Valore uint32 che specifica la modalità del servizio.</span><span class="sxs-lookup"><span data-stu-id="d4b00-109">A uint32 value that specifies the mode of the service.</span></span>  
  
 <span data-ttu-id="d4b00-110">I valori possibili sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4b00-110">Values can be one of the following.</span></span>  
  
 <span data-ttu-id="d4b00-111">Avvio</span><span class="sxs-lookup"><span data-stu-id="d4b00-111">Boot</span></span>  
 <span data-ttu-id="d4b00-112">Valore = 0.</span><span class="sxs-lookup"><span data-stu-id="d4b00-112">Value = 0.</span></span> <span data-ttu-id="d4b00-113">Servizio avviato dal caricatore del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="d4b00-113">Service started by the operating system loader.</span></span> <span data-ttu-id="d4b00-114">Questa opzione è valida solo per i servizi del driver.</span><span class="sxs-lookup"><span data-stu-id="d4b00-114">This option is valid only for driver services.</span></span>  
  
 <span data-ttu-id="d4b00-115">System</span><span class="sxs-lookup"><span data-stu-id="d4b00-115">System</span></span>  
 <span data-ttu-id="d4b00-116">Valore = 1.</span><span class="sxs-lookup"><span data-stu-id="d4b00-116">Value = 1.</span></span> <span data-ttu-id="d4b00-117">Servizio avviato dal metodo `IoInitSystem`.</span><span class="sxs-lookup"><span data-stu-id="d4b00-117">Service started by the `IoInitSystem` method.</span></span> <span data-ttu-id="d4b00-118">Questa opzione è valida solo per i servizi del driver.</span><span class="sxs-lookup"><span data-stu-id="d4b00-118">This option is valid only for driver services.</span></span>  
  
 <span data-ttu-id="d4b00-119">Automatico</span><span class="sxs-lookup"><span data-stu-id="d4b00-119">Automatic</span></span>  
 <span data-ttu-id="d4b00-120">Valore = 2.</span><span class="sxs-lookup"><span data-stu-id="d4b00-120">Value = 2.</span></span> <span data-ttu-id="d4b00-121">Servizio da avviare automaticamente da Gestione controllo servizi durante l'avvio del sistema.</span><span class="sxs-lookup"><span data-stu-id="d4b00-121">Service to be started automatically by the service control manager during system startup.</span></span>  
  
 <span data-ttu-id="d4b00-122">Manuale</span><span class="sxs-lookup"><span data-stu-id="d4b00-122">Manual</span></span>  
 <span data-ttu-id="d4b00-123">Valore = 3.</span><span class="sxs-lookup"><span data-stu-id="d4b00-123">Value = 3.</span></span> <span data-ttu-id="d4b00-124">Servizio da avviare da Gestione computer quando un processo chiama il metodo `StartService`.</span><span class="sxs-lookup"><span data-stu-id="d4b00-124">Service to be started by the Computer Manager when a process calls the `StartService` method.</span></span>  
  
 <span data-ttu-id="d4b00-125">Disabled</span><span class="sxs-lookup"><span data-stu-id="d4b00-125">Disabled</span></span>  
 <span data-ttu-id="d4b00-126">Valore = 4.</span><span class="sxs-lookup"><span data-stu-id="d4b00-126">Value = 4.</span></span> <span data-ttu-id="d4b00-127">Impossibile avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="d4b00-127">Service cannot be started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4b00-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d4b00-128">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4b00-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4b00-129">See Also</span></span>  
 <span data-ttu-id="d4b00-130">[Avvio e arresto di servizi](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="d4b00-130">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
