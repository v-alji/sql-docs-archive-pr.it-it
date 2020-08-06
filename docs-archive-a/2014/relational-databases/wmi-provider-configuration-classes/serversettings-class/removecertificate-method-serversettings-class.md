---
title: Metodo RemoveCertificate (classe ServerSettings) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- RemoveCertificate Method (ServerSettings Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- RemoveCertificate method
ms.assetid: 9ffdbc39-93f5-48fb-859a-86a3ad545827
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 00731fab5c4bdec61848df93829dd5013a7454f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712916"
---
# <a name="removecertificate-method-serversettings-class"></a><span data-ttu-id="f279e-102">Metodo RemoveCertificate (classe ServerSettings)</span><span class="sxs-lookup"><span data-stu-id="f279e-102">RemoveCertificate Method (ServerSettings Class)</span></span>
  <span data-ttu-id="f279e-103">Rimuove il certificato di sicurezza corrente dall'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f279e-103">Removes the current security certificate from the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f279e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f279e-104">Syntax</span></span>  
  
```  
  
object  
.RemoveCertificate()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="f279e-105">Parti</span><span class="sxs-lookup"><span data-stu-id="f279e-105">Parts</span></span>  
 <span data-ttu-id="f279e-106">*object*</span><span class="sxs-lookup"><span data-stu-id="f279e-106">*object*</span></span>  
 <span data-ttu-id="f279e-107">Oggetto della [classe ServerSettings](serversettings-class.md) che rappresenta le impostazioni del server in un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f279e-107">A [ServerSettings Class](serversettings-class.md) object that represents the server settings on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="f279e-108">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f279e-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="f279e-109">Valore u`int32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="f279e-109">A u`int32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f279e-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f279e-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f279e-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f279e-111">See Also</span></span>  
 <span data-ttu-id="f279e-112">[Configurazione di protocolli di rete server e di librerie di rete](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="f279e-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
