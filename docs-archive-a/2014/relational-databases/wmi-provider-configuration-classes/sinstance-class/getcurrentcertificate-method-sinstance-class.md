---
title: Metodo GetCurrentCertificate (classe SInstance) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- GetCurrentCertificate Method (SInstance Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- GetCurrentCertificate method
ms.assetid: 9d2b72df-cb21-414a-abef-917f13d4de62
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 47838190e3791e01f8482e3fb064a9dca3a764af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638306"
---
# <a name="getcurrentcertificate-method-sinstance-class"></a><span data-ttu-id="98da1-102">Metodo GetCurrentCertificate (classe SInstance)</span><span class="sxs-lookup"><span data-stu-id="98da1-102">GetCurrentCertificate Method (SInstance Class)</span></span>
  <span data-ttu-id="98da1-103">Ottiene il certificato di sicurezza corrente.</span><span class="sxs-lookup"><span data-stu-id="98da1-103">Gets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98da1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="98da1-104">Syntax</span></span>  
  
```  
  
object  
.GetCurrentCertificate(  
SHA  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="98da1-105">Parti</span><span class="sxs-lookup"><span data-stu-id="98da1-105">Parts</span></span>  
 <span data-ttu-id="98da1-106">*object*</span><span class="sxs-lookup"><span data-stu-id="98da1-106">*object*</span></span>  
 <span data-ttu-id="98da1-107">Oggetto della [classe SInstance](sinstance-class.md) che rappresenta le impostazioni del server in un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98da1-107">An [SInstance Class](sinstance-class.md) object that represents the server settings on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="98da1-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="98da1-108">Parameters</span></span>  
  
|<span data-ttu-id="98da1-109">Parametro</span><span class="sxs-lookup"><span data-stu-id="98da1-109">Parameter</span></span>|<span data-ttu-id="98da1-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="98da1-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="98da1-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="98da1-111">*SHA*</span></span>|<span data-ttu-id="98da1-112">Valore oggetto stringa (parametro di output) che specifica il certificato di sicurezza corrente dopo il completamento del metodo.</span><span class="sxs-lookup"><span data-stu-id="98da1-112">A string object value (output parameter) that specifies the current security certificate after the method completes.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="98da1-113">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="98da1-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="98da1-114">Valore `uint32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="98da1-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98da1-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="98da1-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98da1-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98da1-116">See Also</span></span>  
 <span data-ttu-id="98da1-117">[Configurazione di protocolli di rete server e di librerie di rete](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="98da1-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
