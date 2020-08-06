---
title: Metodo sedefaults (classe CInstance) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDefaults Method (CInstance Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDefaults method
ms.assetid: ed9e99c2-3e28-4ee8-bc20-61ca05984973
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 5e589796f973592d7f9f549bffbbf8dfbe49cc27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623087"
---
# <a name="setdefaults-method-cinstance-class"></a><span data-ttu-id="5393a-102">Metodo SetDefaults (classe CInstance)</span><span class="sxs-lookup"><span data-stu-id="5393a-102">SetDefaults Method (CInstance Class)</span></span>
  <span data-ttu-id="5393a-103">Imposta tutti i valori predefiniti per l'istanza del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client con l'opzione per sovrascrivere i dati esistenti.</span><span class="sxs-lookup"><span data-stu-id="5393a-103">Sets all the default values for the instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client with the option to overwrite existing data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5393a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5393a-104">Syntax</span></span>  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="5393a-105">Parti</span><span class="sxs-lookup"><span data-stu-id="5393a-105">Parts</span></span>  
 <span data-ttu-id="5393a-106">*object*</span><span class="sxs-lookup"><span data-stu-id="5393a-106">*object*</span></span>  
 <span data-ttu-id="5393a-107">Oggetto della [classe CInstance](cinstance-class.md) che rappresenta un'istanza del client di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5393a-107">A [CInstance Class](cinstance-class.md) object that represents a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client instance.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="5393a-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="5393a-108">Parameters</span></span>  
  
|<span data-ttu-id="5393a-109">Parametro</span><span class="sxs-lookup"><span data-stu-id="5393a-109">Parameter</span></span>|<span data-ttu-id="5393a-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5393a-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5393a-111">*OverwriteAll*</span><span class="sxs-lookup"><span data-stu-id="5393a-111">*OverwriteAll*</span></span>|<span data-ttu-id="5393a-112">Valore booleano che specifica se sovrascrivere i valori esistenti nell'istanza del client di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. `true` per sovrascrivere i dati esistenti; `false` se i dati esistenti non devono essere sovrascritti.</span><span class="sxs-lookup"><span data-stu-id="5393a-112">A Boolean value that specifies whether to overwrite existing values on the instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client: `true` to overwrite existing data, or `false` if existing data is not to be overwritten.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="5393a-113">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5393a-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="5393a-114">Valore `uint32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="5393a-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5393a-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5393a-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5393a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5393a-116">See Also</span></span>  
 [<span data-ttu-id="5393a-117">Configurazione di protocolli client</span><span class="sxs-lookup"><span data-stu-id="5393a-117">Configure Client Protocols</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
