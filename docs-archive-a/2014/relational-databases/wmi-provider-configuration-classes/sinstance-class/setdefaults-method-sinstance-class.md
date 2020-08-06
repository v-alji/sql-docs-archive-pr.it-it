---
title: Metodo sedefaults (classe SInstance) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDefaults Method (SInstance Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDefaults method
ms.assetid: dc3c6a85-0711-4688-bf4f-91168c57af28
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: c581834d3c97bed622d16fbb35e48704f8679531
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712911"
---
# <a name="setdefaults-method-sinstance-class"></a><span data-ttu-id="018e2-102">Metodo SetDefaults (classe SInstance)</span><span class="sxs-lookup"><span data-stu-id="018e2-102">SetDefaults Method (SInstance Class)</span></span>
  <span data-ttu-id="018e2-103">Imposta tutti i valori predefiniti per l'istanza di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] con l'opzione per sovrascrivere i dati esistenti.</span><span class="sxs-lookup"><span data-stu-id="018e2-103">Sets all the default values for the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with the option to overwrite existing data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="018e2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="018e2-104">Syntax</span></span>  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="018e2-105">Parti</span><span class="sxs-lookup"><span data-stu-id="018e2-105">Parts</span></span>  
 <span data-ttu-id="018e2-106">*object*</span><span class="sxs-lookup"><span data-stu-id="018e2-106">*object*</span></span>  
 <span data-ttu-id="018e2-107">Oggetto della [classe SInstance](sinstance-class.md) che rappresenta un'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="018e2-107">An [SInstance Class](sinstance-class.md) object that represents a server instance.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="018e2-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="018e2-108">Parameters</span></span>  
  
|<span data-ttu-id="018e2-109">Parametro</span><span class="sxs-lookup"><span data-stu-id="018e2-109">Parameter</span></span>|<span data-ttu-id="018e2-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="018e2-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="018e2-111">*OverwriteAll*</span><span class="sxs-lookup"><span data-stu-id="018e2-111">*OverwriteAll*</span></span>|<span data-ttu-id="018e2-112">Valore booleano che specifica se sovrascrivere i valori esistenti nell'istanza del client di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. `true` per sovrascrivere i dati esistenti; `false` se i dati esistenti non devono essere sovrascritti.</span><span class="sxs-lookup"><span data-stu-id="018e2-112">A Boolean value that specifies whether to overwrite existing value on the instance of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client: `true` if existing data is overwritten, or `false` if existing data is not overwritten.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="018e2-113">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="018e2-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="018e2-114">Valore `uint32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="018e2-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="018e2-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="018e2-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="018e2-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="018e2-116">See Also</span></span>  
 <span data-ttu-id="018e2-117">[Configurazione di protocolli di rete server e di librerie di rete](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="018e2-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
