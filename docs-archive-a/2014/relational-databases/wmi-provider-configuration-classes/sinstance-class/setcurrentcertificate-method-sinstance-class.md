---
title: Metodo SetCurrentCertificate (classe SInstance) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetCurrentCertificate Method (SInstance Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetCurrentCertificate method
ms.assetid: 7349fb87-b973-4160-a2be-cab73abf5b31
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 44e65ab30659cacca09e63a94a1f3596a182dda5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712915"
---
# <a name="setcurrentcertificate-method-sinstance-class"></a><span data-ttu-id="e75fd-102">Metodo SetCurrentCertificate (classe SInstance)</span><span class="sxs-lookup"><span data-stu-id="e75fd-102">SetCurrentCertificate Method (SInstance Class)</span></span>
  <span data-ttu-id="e75fd-103">Imposta il certificato di sicurezza corrente.</span><span class="sxs-lookup"><span data-stu-id="e75fd-103">Sets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e75fd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e75fd-104">Syntax</span></span>  
  
```  
  
object  
.SetCurrentCertificate(  
SHA  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="e75fd-105">Parti</span><span class="sxs-lookup"><span data-stu-id="e75fd-105">Parts</span></span>  
 <span data-ttu-id="e75fd-106">*object*</span><span class="sxs-lookup"><span data-stu-id="e75fd-106">*object*</span></span>  
 <span data-ttu-id="e75fd-107">Oggetto della [classe SInstance](sinstance-class.md) che rappresenta l'impostazione del server in un'istanza di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e75fd-107">An [SInstance Class](sinstance-class.md) object that represents the server setting on an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="e75fd-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="e75fd-108">Parameters</span></span>  
  
|<span data-ttu-id="e75fd-109">Parametro</span><span class="sxs-lookup"><span data-stu-id="e75fd-109">Parameter</span></span>|<span data-ttu-id="e75fd-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e75fd-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e75fd-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="e75fd-111">*SHA*</span></span>|<span data-ttu-id="e75fd-112">Valore string che specifica il certificato di sicurezza corrente.</span><span class="sxs-lookup"><span data-stu-id="e75fd-112">A string value that specifies the current security certificate.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="e75fd-113">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e75fd-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="e75fd-114">Valore `uint32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="e75fd-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e75fd-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e75fd-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e75fd-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e75fd-116">See Also</span></span>  
 <span data-ttu-id="e75fd-117">[Configurazione di protocolli di rete server e di librerie di rete](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="e75fd-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
