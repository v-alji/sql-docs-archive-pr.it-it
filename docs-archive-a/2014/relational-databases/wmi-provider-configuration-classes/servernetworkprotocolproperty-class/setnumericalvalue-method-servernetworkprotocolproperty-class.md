---
title: Metodo SetNumericalValue (classe ServerNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetNumericalValue Method (ServerNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetNumericalValue method
ms.assetid: b3b4bce8-9d9e-4ccb-a223-0454281353b0
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f5a4b8d6819dae11abe4cc097f0e423c23d909e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628560"
---
# <a name="setnumericalvalue-method-servernetworkprotocolproperty-class"></a><span data-ttu-id="d7d4a-102">Metodo SetNumericalValue (classe ServerNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="d7d4a-102">SetNumericalValue Method (ServerNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="d7d4a-103">Imposta il valore numerico della proprietà a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="d7d4a-103">Sets the numeric value of the referenced property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7d4a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d7d4a-104">Syntax</span></span>  
  
```  
  
object  
.SetNumericalValue(  
NumValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="d7d4a-105">Parti</span><span class="sxs-lookup"><span data-stu-id="d7d4a-105">Parts</span></span>  
 <span data-ttu-id="d7d4a-106">*object*</span><span class="sxs-lookup"><span data-stu-id="d7d4a-106">*object*</span></span>  
 <span data-ttu-id="d7d4a-107">Oggetto [ServerNetworkProtocolProperty Class] ServerNetworkProtocolProperty-class.md) che rappresenta un attributo del protocollo di rete nell'istanza di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d7d4a-107">A [ServerNetworkProtocolProperty Class]servernetworkprotocolproperty-class.md) object that represents an attribute of the network protocol on the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="d7d4a-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="d7d4a-108">Parameters</span></span>  
  
|<span data-ttu-id="d7d4a-109">Parametro</span><span class="sxs-lookup"><span data-stu-id="d7d4a-109">Parameter</span></span>|<span data-ttu-id="d7d4a-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7d4a-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d7d4a-111">*NumValue*</span><span class="sxs-lookup"><span data-stu-id="d7d4a-111">*NumValue*</span></span>|<span data-ttu-id="d7d4a-112">Valore `uint32` che specifica il nuovo valore della proprietà corrente.</span><span class="sxs-lookup"><span data-stu-id="d7d4a-112">A `uint32` value that specifies the new value of the current property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d7d4a-113">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d7d4a-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="d7d4a-114">Valore `uint32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="d7d4a-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7d4a-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d7d4a-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7d4a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7d4a-116">See Also</span></span>  
 <span data-ttu-id="d7d4a-117">[Configurazione di protocolli di rete server e di librerie di rete](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="d7d4a-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
