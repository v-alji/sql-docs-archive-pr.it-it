---
title: Metodo SetStringValue (classe ServerNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStringValue Method (ServerNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStringValue method
ms.assetid: 0911df30-55f7-4fca-a1fb-01d2c91c1467
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8eb4a27d700d801e3ca94362663c6d7feaa7dc86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712943"
---
# <a name="setstringvalue-method-servernetworkprotocolproperty-class"></a><span data-ttu-id="329d4-102">Metodo SetStringValue (classe ServerNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="329d4-102">SetStringValue Method (ServerNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="329d4-103">Imposta il valore string della proprietà a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="329d4-103">Sets the string value of the referenced property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="329d4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="329d4-104">Syntax</span></span>  
  
```  
  
object  
.SetStringValue(  
StrValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="329d4-105">Parti</span><span class="sxs-lookup"><span data-stu-id="329d4-105">Parts</span></span>  
 <span data-ttu-id="329d4-106">*object*</span><span class="sxs-lookup"><span data-stu-id="329d4-106">*object*</span></span>  
 <span data-ttu-id="329d4-107">Oggetto della [classe ServerNetworkProtocolProperty](servernetworkprotocolproperty-class.md) che rappresenta un attributo del protocollo di rete nell'istanza di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="329d4-107">A [ServerNetworkProtocolProperty Class](servernetworkprotocolproperty-class.md) object that represents an attribute of the network protocol on the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="329d4-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="329d4-108">Parameters</span></span>  
  
|<span data-ttu-id="329d4-109">Parametro</span><span class="sxs-lookup"><span data-stu-id="329d4-109">Parameter</span></span>|<span data-ttu-id="329d4-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="329d4-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="329d4-111">*StrValue*</span><span class="sxs-lookup"><span data-stu-id="329d4-111">*StrValue*</span></span>|<span data-ttu-id="329d4-112">Valore string che specifica il nuovo valore della proprietà corrente.</span><span class="sxs-lookup"><span data-stu-id="329d4-112">A string value that specifies the new value of the current property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="329d4-113">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="329d4-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="329d4-114">Valore `uint32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="329d4-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="329d4-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="329d4-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="329d4-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="329d4-116">See Also</span></span>  
 <span data-ttu-id="329d4-117">[Configurazione di protocolli di rete server e di librerie di rete](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="329d4-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
