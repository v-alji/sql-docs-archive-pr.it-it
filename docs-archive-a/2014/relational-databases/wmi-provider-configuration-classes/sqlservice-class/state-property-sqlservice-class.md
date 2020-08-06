---
title: Proprietà state (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- State Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- State property
ms.assetid: 9e09f419-947c-4d4b-9a49-2d3396c847cd
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: a7456113d9ec4444507d1057892a65adf241992f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717603"
---
# <a name="state-property-sqlservice-class"></a><span data-ttu-id="a1c00-102">Proprietà State (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="a1c00-102">State Property (SqlService Class)</span></span>
  <span data-ttu-id="a1c00-103">Ottiene o imposta lo stato corrente del servizio.</span><span class="sxs-lookup"><span data-stu-id="a1c00-103">Gets or sets the current state of the service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1c00-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a1c00-104">Syntax</span></span>  
  
```  
  
object  
.State [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="a1c00-105">Parti</span><span class="sxs-lookup"><span data-stu-id="a1c00-105">Parts</span></span>  
 <span data-ttu-id="a1c00-106">*object*</span><span class="sxs-lookup"><span data-stu-id="a1c00-106">*object*</span></span>  
 <span data-ttu-id="a1c00-107">Oggetto della [classe SqlService](sqlservice-class.md) che rappresenta il servizio.</span><span class="sxs-lookup"><span data-stu-id="a1c00-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="a1c00-108">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a1c00-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="a1c00-109">Valore uint32 che specifica lo stato del servizio.</span><span class="sxs-lookup"><span data-stu-id="a1c00-109">A uint32 value that specifies the state of the service.</span></span>  
  
 <span data-ttu-id="a1c00-110">I valori possibili sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="a1c00-110">Values can be one of the following.</span></span>  
  
 <span data-ttu-id="a1c00-111">1</span><span class="sxs-lookup"><span data-stu-id="a1c00-111">1</span></span>  
 <span data-ttu-id="a1c00-112">Arrestato.</span><span class="sxs-lookup"><span data-stu-id="a1c00-112">Stopped.</span></span> <span data-ttu-id="a1c00-113">Il servizio è stato arrestato.</span><span class="sxs-lookup"><span data-stu-id="a1c00-113">The service is stopped.</span></span>  
  
 <span data-ttu-id="a1c00-114">2</span><span class="sxs-lookup"><span data-stu-id="a1c00-114">2</span></span>  
 <span data-ttu-id="a1c00-115">In attesa dell'avvio.</span><span class="sxs-lookup"><span data-stu-id="a1c00-115">Start Pending.</span></span> <span data-ttu-id="a1c00-116">Il servizio è in attesa di essere avviato.</span><span class="sxs-lookup"><span data-stu-id="a1c00-116">The service is waiting to start.</span></span>  
  
 <span data-ttu-id="a1c00-117">3</span><span class="sxs-lookup"><span data-stu-id="a1c00-117">3</span></span>  
 <span data-ttu-id="a1c00-118">In attesa dell'arresto.</span><span class="sxs-lookup"><span data-stu-id="a1c00-118">Stop Pending.</span></span> <span data-ttu-id="a1c00-119">Il servizio è in attesa di essere arrestato.</span><span class="sxs-lookup"><span data-stu-id="a1c00-119">The service is waiting to stop.</span></span>  
  
 <span data-ttu-id="a1c00-120">4</span><span class="sxs-lookup"><span data-stu-id="a1c00-120">4</span></span>  
 <span data-ttu-id="a1c00-121">In esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a1c00-121">Running.</span></span> <span data-ttu-id="a1c00-122">Il servizio è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a1c00-122">The service is running.</span></span>  
  
 <span data-ttu-id="a1c00-123">5</span><span class="sxs-lookup"><span data-stu-id="a1c00-123">5</span></span>  
 <span data-ttu-id="a1c00-124">In attesa della ripresa.</span><span class="sxs-lookup"><span data-stu-id="a1c00-124">Continue Pending.</span></span> <span data-ttu-id="a1c00-125">Il servizio è in attesa di essere ripreso.</span><span class="sxs-lookup"><span data-stu-id="a1c00-125">The service is waiting to continue.</span></span>  
  
 <span data-ttu-id="a1c00-126">6</span><span class="sxs-lookup"><span data-stu-id="a1c00-126">6</span></span>  
 <span data-ttu-id="a1c00-127">In attesa della sospensione.</span><span class="sxs-lookup"><span data-stu-id="a1c00-127">Pause Pending.</span></span> <span data-ttu-id="a1c00-128">Il servizio è in attesa di essere sospeso.</span><span class="sxs-lookup"><span data-stu-id="a1c00-128">The service is waiting to pause.</span></span>  
  
 <span data-ttu-id="a1c00-129">7</span><span class="sxs-lookup"><span data-stu-id="a1c00-129">7</span></span>  
 <span data-ttu-id="a1c00-130">(sospeso)</span><span class="sxs-lookup"><span data-stu-id="a1c00-130">Paused.</span></span> <span data-ttu-id="a1c00-131">Il servizio è in pausa.</span><span class="sxs-lookup"><span data-stu-id="a1c00-131">The service is paused.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1c00-132">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a1c00-132">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1c00-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1c00-133">See Also</span></span>  
 <span data-ttu-id="a1c00-134">[Avvio e arresto di servizi](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="a1c00-134">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
