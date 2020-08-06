---
title: Proprietà ErrorControl (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ErrorControl Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ErrorControl property
ms.assetid: cbb1e0fa-5bfc-4b1b-a6ed-f7d5cfad4d73
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 73c726af514f2880484cf927282fc0e007f07e2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722632"
---
# <a name="errorcontrol-property-sqlservice-class"></a><span data-ttu-id="dc2e7-102">Proprietà ErrorControl (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="dc2e7-102">ErrorControl Property (SqlService Class)</span></span>
  <span data-ttu-id="dc2e7-103">Ottiene o imposta la gravità dell'errore se il servizio non viene avviato durante l'avvio del computer.</span><span class="sxs-lookup"><span data-stu-id="dc2e7-103">Gets or sets the severity of the error if the service fails to start during startup.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc2e7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dc2e7-104">Syntax</span></span>  
  
```  
  
object  
.ErrorControl [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="dc2e7-105">Parti</span><span class="sxs-lookup"><span data-stu-id="dc2e7-105">Parts</span></span>  
 <span data-ttu-id="dc2e7-106">*object*</span><span class="sxs-lookup"><span data-stu-id="dc2e7-106">*object*</span></span>  
 <span data-ttu-id="dc2e7-107">Oggetto della [classe SqlService](sqlservice-class.md) che rappresenta il servizio.</span><span class="sxs-lookup"><span data-stu-id="dc2e7-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="dc2e7-108">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="dc2e7-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="dc2e7-109">Valore string che specifica la gravità dell'errore riportato se il servizio non viene avviato durante l'avvio del computer.</span><span class="sxs-lookup"><span data-stu-id="dc2e7-109">A string value that specifies the error severity reported if the service fails during startup.</span></span> <span data-ttu-id="dc2e7-110">Nella tabella seguente sono illustrati i possibili valori.</span><span class="sxs-lookup"><span data-stu-id="dc2e7-110">The following table shows the possible values.</span></span>  
  
 <span data-ttu-id="dc2e7-111">Ignora</span><span class="sxs-lookup"><span data-stu-id="dc2e7-111">Ignore</span></span>  
 <span data-ttu-id="dc2e7-112">L'utente non viene notificato.</span><span class="sxs-lookup"><span data-stu-id="dc2e7-112">User is not notified.</span></span>  
  
 <span data-ttu-id="dc2e7-113">Normale</span><span class="sxs-lookup"><span data-stu-id="dc2e7-113">Normal</span></span>  
 <span data-ttu-id="dc2e7-114">L'utente viene notificato.</span><span class="sxs-lookup"><span data-stu-id="dc2e7-114">User is notified.</span></span>  
  
 <span data-ttu-id="dc2e7-115">Severe</span><span class="sxs-lookup"><span data-stu-id="dc2e7-115">Severe</span></span>  
 <span data-ttu-id="dc2e7-116">Il sistema viene riavviato con l'ultima configurazione valida nota.</span><span class="sxs-lookup"><span data-stu-id="dc2e7-116">System is restarted with the last-known-good configuration.</span></span>  
  
 <span data-ttu-id="dc2e7-117">Critico</span><span class="sxs-lookup"><span data-stu-id="dc2e7-117">Critical</span></span>  
 <span data-ttu-id="dc2e7-118">Il sistema tenta un riavvio con una configurazione valida.</span><span class="sxs-lookup"><span data-stu-id="dc2e7-118">System attempts to restart with a good configuration.</span></span>  
  
 <span data-ttu-id="dc2e7-119">Unknown</span><span class="sxs-lookup"><span data-stu-id="dc2e7-119">Unknown</span></span>  
 <span data-ttu-id="dc2e7-120">La gravità è sconosciuta.</span><span class="sxs-lookup"><span data-stu-id="dc2e7-120">The severity is unknown.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc2e7-121">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="dc2e7-121">Remarks</span></span>  
 <span data-ttu-id="dc2e7-122">Il valore indica l'azione intrapresa dal programma di avvio in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="dc2e7-122">The value indicates the action taken by the startup program if a failure occurs.</span></span> <span data-ttu-id="dc2e7-123">Tutti gli errori vengono registrati dal computer.</span><span class="sxs-lookup"><span data-stu-id="dc2e7-123">All errors are logged by the computer system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc2e7-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc2e7-124">See Also</span></span>  
 <span data-ttu-id="dc2e7-125">[Avvio e arresto di servizi](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="dc2e7-125">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
