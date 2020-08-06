---
title: Metodo GetCurrentCertificate (classe SecurityCertificate) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- GetCurrentCertificate Method (SecurityCertificate Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- GetCurrentCertificate method
ms.assetid: 987a2671-1801-45c4-93e6-29f883c58720
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ab96b2e2a8fabf9e9ccce647e54be1983fe40ca0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712956"
---
# <a name="getcurrentcertificate-method-securitycertificate-class"></a><span data-ttu-id="32fb6-102">Metodo GetCurrentCertificate (classe SecurityCertificate)</span><span class="sxs-lookup"><span data-stu-id="32fb6-102">GetCurrentCertificate Method (SecurityCertificate Class)</span></span>
  <span data-ttu-id="32fb6-103">Ottiene il certificato di sicurezza corrente.</span><span class="sxs-lookup"><span data-stu-id="32fb6-103">Gets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32fb6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="32fb6-104">Syntax</span></span>  
  
```  
  
object  
.GetCurrentCertificate(  
SHA , SQLInstance  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="32fb6-105">Parti</span><span class="sxs-lookup"><span data-stu-id="32fb6-105">Parts</span></span>  
 <span data-ttu-id="32fb6-106">*object*</span><span class="sxs-lookup"><span data-stu-id="32fb6-106">*object*</span></span>  
 <span data-ttu-id="32fb6-107">Oggetto della [classe SecurityCertificate](securitycertificate-class.md) che rappresenta un certificato di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="32fb6-107">A [SecurityCertificate Class](securitycertificate-class.md) object that represents a security certificate.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="32fb6-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="32fb6-108">Parameters</span></span>  
  
|<span data-ttu-id="32fb6-109">Parametro</span><span class="sxs-lookup"><span data-stu-id="32fb6-109">Parameter</span></span>|<span data-ttu-id="32fb6-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="32fb6-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="32fb6-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="32fb6-111">*SHA*</span></span>|<span data-ttu-id="32fb6-112">Valore string (parametro di output) che specifica l'identificazione digitale SHA del certificato di sicurezza corrente dopo il completamento del metodo.</span><span class="sxs-lookup"><span data-stu-id="32fb6-112">A string value (output parameter) that specifies the current security certificate SHA thumbprint after the method completes.</span></span>|  
|<span data-ttu-id="32fb6-113">*SQLInstance*</span><span class="sxs-lookup"><span data-stu-id="32fb6-113">*SQLInstance*</span></span>|<span data-ttu-id="32fb6-114">Valore string che specifica l'istanza per la quale viene richiesto il certificato.</span><span class="sxs-lookup"><span data-stu-id="32fb6-114">A string value that specifies the instance for which the certificate is required.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="32fb6-115">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="32fb6-115">Property Value/Return Value</span></span>  
 <span data-ttu-id="32fb6-116">Valore `uint32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="32fb6-116">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32fb6-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="32fb6-117">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32fb6-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32fb6-118">See Also</span></span>  
 <span data-ttu-id="32fb6-119">[Configurazione di protocolli di rete server e di librerie di rete](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="32fb6-119">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
