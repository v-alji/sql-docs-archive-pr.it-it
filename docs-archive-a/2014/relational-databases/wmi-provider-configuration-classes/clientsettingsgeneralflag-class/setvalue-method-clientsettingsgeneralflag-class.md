---
title: Metodo SetValue (classe ClientSettingsGeneralFlag) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetValue Method (ClientSettingsGeneralFlag Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetValue method
ms.assetid: 34443689-a0e0-4668-a811-17532c6fd271
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: fffa44bd8743f96a43ca4d1787d8d2afaad5e6cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712980"
---
# <a name="setvalue-method-clientsettingsgeneralflag-class"></a><span data-ttu-id="f0eee-102">Metodo SetValue (classe ClientSettingsGeneralFlag)</span><span class="sxs-lookup"><span data-stu-id="f0eee-102">SetValue Method (ClientSettingsGeneralFlag Class)</span></span>
  <span data-ttu-id="f0eee-103">Imposta tutti i valori del flag a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="f0eee-103">Sets all the values of the referenced flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0eee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f0eee-104">Syntax</span></span>  
  
```  
  
object  
.SetValue(  
Value  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="f0eee-105">Parti</span><span class="sxs-lookup"><span data-stu-id="f0eee-105">Parts</span></span>  
 <span data-ttu-id="f0eee-106">*object*</span><span class="sxs-lookup"><span data-stu-id="f0eee-106">*object*</span></span>  
 <span data-ttu-id="f0eee-107">Oggetto della [classe ClientSettingsGeneralFlag](clientsettingsgeneralflag-class.md) che rappresenta un flag generale per le impostazioni del server.</span><span class="sxs-lookup"><span data-stu-id="f0eee-107">A [ClientSettingsGeneralFlag Class](clientsettingsgeneralflag-class.md) object that represents a general flag for the server settings.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="f0eee-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="f0eee-108">Parameters</span></span>  
  
|<span data-ttu-id="f0eee-109">Parametro</span><span class="sxs-lookup"><span data-stu-id="f0eee-109">Parameter</span></span>|<span data-ttu-id="f0eee-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f0eee-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f0eee-111">*Valore*</span><span class="sxs-lookup"><span data-stu-id="f0eee-111">*Value*</span></span>|<span data-ttu-id="f0eee-112">Valore booleano che specifica il valore del flag.</span><span class="sxs-lookup"><span data-stu-id="f0eee-112">A Boolean value that specifies the value of the flag.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="f0eee-113">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f0eee-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="f0eee-114">Valore `uint32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="f0eee-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0eee-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f0eee-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0eee-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0eee-116">See Also</span></span>  
 [<span data-ttu-id="f0eee-117">Configurazione di protocolli client</span><span class="sxs-lookup"><span data-stu-id="f0eee-117">Configure Client Protocols</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
