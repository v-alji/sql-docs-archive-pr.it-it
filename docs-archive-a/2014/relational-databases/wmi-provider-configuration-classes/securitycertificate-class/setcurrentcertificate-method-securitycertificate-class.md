---
title: Metodo SetCurrentCertificate (classe SecurityCertificate) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetCurrentCertificate Method (SecurityCertificate Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetCurrentCertificate method
ms.assetid: 04b1a76a-932d-4824-8506-e346afe7554e
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4c7065946c858b775e319578eb67c2b7186338f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626607"
---
# <a name="setcurrentcertificate-method-securitycertificate-class"></a><span data-ttu-id="e6bb9-102">Metodo SetCurrentCertificate (classe SecurityCertificate)</span><span class="sxs-lookup"><span data-stu-id="e6bb9-102">SetCurrentCertificate Method (SecurityCertificate Class)</span></span>
  <span data-ttu-id="e6bb9-103">Imposta il certificato di sicurezza corrente.</span><span class="sxs-lookup"><span data-stu-id="e6bb9-103">Sets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6bb9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e6bb9-104">Syntax</span></span>  
  
```  
  
object  
.SetCurrentCertificate(  
SHA , SQLInstance  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="e6bb9-105">Parti</span><span class="sxs-lookup"><span data-stu-id="e6bb9-105">Parts</span></span>  
 <span data-ttu-id="e6bb9-106">*object*</span><span class="sxs-lookup"><span data-stu-id="e6bb9-106">*object*</span></span>  
 <span data-ttu-id="e6bb9-107">Oggetto [SecurityCertificate Class] SecurityCertificate-class.md) che rappresenta un certificato di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e6bb9-107">A [SecurityCertificate Class]securitycertificate-class.md) object that represents a security certificate.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="e6bb9-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="e6bb9-108">Parameters</span></span>  
  
|<span data-ttu-id="e6bb9-109">Parametro</span><span class="sxs-lookup"><span data-stu-id="e6bb9-109">Parameter</span></span>|<span data-ttu-id="e6bb9-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6bb9-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e6bb9-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="e6bb9-111">*SHA*</span></span>|<span data-ttu-id="e6bb9-112">Valore string che specifica l'identificazione digitale dell'algoritmo hash di protezione (SHA, Secure Hash Algorithm) per il certificato di sicurezza richiesto.</span><span class="sxs-lookup"><span data-stu-id="e6bb9-112">A string value that specifies the secure hash algorithm (SHA) thumbprint for the required security certificate.</span></span>|  
|<span data-ttu-id="e6bb9-113">*SQLInstance*</span><span class="sxs-lookup"><span data-stu-id="e6bb9-113">*SQLInstance*</span></span>|<span data-ttu-id="e6bb9-114">Valore string che specifica l'istanza per la quale viene richiesto il certificato.</span><span class="sxs-lookup"><span data-stu-id="e6bb9-114">A string value that specifies the instance for which the certificate is required.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="e6bb9-115">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e6bb9-115">Property Value/Return Value</span></span>  
 <span data-ttu-id="e6bb9-116">Valore uint32 che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="e6bb9-116">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6bb9-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e6bb9-117">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6bb9-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6bb9-118">See Also</span></span>  
 <span data-ttu-id="e6bb9-119">[Configurazione di protocolli di rete server e di librerie di rete](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="e6bb9-119">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
