---
title: Metodo SetCurrentCertificate (classe ServerSettings) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetCurrentCertificate Method (ServerSettings Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetCurrentCertificate method
ms.assetid: f9c6e172-11be-42de-b19b-a5b3436e84da
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 7071937a7d7e601597fe008187448bb16a5a15ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715116"
---
# <a name="setcurrentcertificate-method-serversettings-class"></a><span data-ttu-id="50e29-102">Metodo SetCurrentCertificate (classe ServerSettings)</span><span class="sxs-lookup"><span data-stu-id="50e29-102">SetCurrentCertificate Method (ServerSettings Class)</span></span>
  <span data-ttu-id="50e29-103">Imposta il certificato di sicurezza corrente.</span><span class="sxs-lookup"><span data-stu-id="50e29-103">Sets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50e29-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="50e29-104">Syntax</span></span>  
  
```  
  
object  
.SetCurrentCertificate(  
SHA  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="50e29-105">Parti</span><span class="sxs-lookup"><span data-stu-id="50e29-105">Parts</span></span>  
 <span data-ttu-id="50e29-106">*object*</span><span class="sxs-lookup"><span data-stu-id="50e29-106">*object*</span></span>  
 <span data-ttu-id="50e29-107">Oggetto [ServerSettings Class] ServerSettings-class.md) che rappresenta l'impostazione del server in un'istanza di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="50e29-107">A [ServerSettings Class]serversettings-class.md) object that represents the server setting on an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="50e29-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="50e29-108">Parameters</span></span>  
  
|<span data-ttu-id="50e29-109">Parametro</span><span class="sxs-lookup"><span data-stu-id="50e29-109">Parameter</span></span>|<span data-ttu-id="50e29-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50e29-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="50e29-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="50e29-111">*SHA*</span></span>|<span data-ttu-id="50e29-112">Valore string che specifica il certificato di sicurezza corrente.</span><span class="sxs-lookup"><span data-stu-id="50e29-112">A string value that specifies the current security certificate.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="50e29-113">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="50e29-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="50e29-114">Valore `uint32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="50e29-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50e29-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="50e29-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50e29-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50e29-116">See Also</span></span>  
 <span data-ttu-id="50e29-117">[Configurazione di protocolli di rete server e di librerie di rete](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="50e29-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
