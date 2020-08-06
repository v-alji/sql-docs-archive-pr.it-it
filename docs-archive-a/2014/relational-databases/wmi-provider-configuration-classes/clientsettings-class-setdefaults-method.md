---
title: Metodo sedefaults (classe ClientSettings) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDefaults Method (ClientSettings Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDefaults method
ms.assetid: 056508f3-a5c8-467c-a196-dc1ef1f5178f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b6985ebfa4a9145dd3474cec31f32cdab9c11cdc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637106"
---
# <a name="setdefaults-method-clientsettings-class"></a><span data-ttu-id="ad914-102">Metodo SetDefaults (classe ClientSettings)</span><span class="sxs-lookup"><span data-stu-id="ad914-102">SetDefaults Method (ClientSettings Class)</span></span>
  <span data-ttu-id="ad914-103">Imposta tutti i valori predefiniti per l'istanza del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client con l'opzione per sovrascrivere i dati esistenti.</span><span class="sxs-lookup"><span data-stu-id="ad914-103">Sets all the default values for the instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client with the option to overwrite existing data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad914-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ad914-104">Syntax</span></span>  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="ad914-105">Parti</span><span class="sxs-lookup"><span data-stu-id="ad914-105">Parts</span></span>  
 <span data-ttu-id="ad914-106">*object*</span><span class="sxs-lookup"><span data-stu-id="ad914-106">*object*</span></span>  
 <span data-ttu-id="ad914-107">Oggetto `ClientSettings` che rappresenta un'istanza del client di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad914-107">A `ClientSettings` object that represents a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client instance.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="ad914-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="ad914-108">Parameters</span></span>  
  
|<span data-ttu-id="ad914-109">Parametro</span><span class="sxs-lookup"><span data-stu-id="ad914-109">Parameter</span></span>|<span data-ttu-id="ad914-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad914-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ad914-111">*OverwriteAll*</span><span class="sxs-lookup"><span data-stu-id="ad914-111">*OverwriteAll*</span></span>|<span data-ttu-id="ad914-112">Un valore booleano che specifica se sovrascrivere valori esistenti sull'istanza del client [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ad914-112">A Boolean value that specifies whether to overwrite existing values on the instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client.</span></span> <span data-ttu-id="ad914-113">`true` per sovrascrivere dati esistenti; `false` se non devono essere sovrascritti dati esistenti.</span><span class="sxs-lookup"><span data-stu-id="ad914-113">`true` to overwrite existing data; `false` if existing data is not to be overwritten.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="ad914-114">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ad914-114">Property Value/Return Value</span></span>  
 <span data-ttu-id="ad914-115">Valore `uint32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="ad914-115">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad914-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ad914-116">Remarks</span></span>  
  
