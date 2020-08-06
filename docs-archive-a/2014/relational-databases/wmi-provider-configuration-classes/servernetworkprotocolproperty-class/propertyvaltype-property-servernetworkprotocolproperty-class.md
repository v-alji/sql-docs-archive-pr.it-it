---
title: Proprietà PropertyValType (classe ServerNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- PropertyValType Property (ServerNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- PropertyValType property
ms.assetid: fbd42e8e-0642-4a19-b3c8-6ce88345145f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: be6c42fbaa36080ec8144d95abb045a3b4328057
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723635"
---
# <a name="propertyvaltype-property-servernetworkprotocolproperty-class"></a><span data-ttu-id="23121-102">Proprietà PropertyValType (classe ServerNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="23121-102">PropertyValType Property (ServerNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="23121-103">Ottiene il tipo di dati del valore archiviato nella proprietà a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="23121-103">Gets the data type of the value stored in the referenced property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23121-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="23121-104">Syntax</span></span>  
  
```  
  
object  
.PropertyValType [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="23121-105">Parti</span><span class="sxs-lookup"><span data-stu-id="23121-105">Parts</span></span>  
 <span data-ttu-id="23121-106">*object*</span><span class="sxs-lookup"><span data-stu-id="23121-106">*object*</span></span>  
 <span data-ttu-id="23121-107">Oggetto della [classe ServerNetworkProtocolProperty](servernetworkprotocolproperty-class.md) che rappresenta un attributo del protocollo di rete nell'istanza di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23121-107">A [ServerNetworkProtocolProperty Class](servernetworkprotocolproperty-class.md) object that represents an attribute of the network protocol on the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="23121-108">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="23121-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="23121-109">Valore `uint32` che specifica il tipo di dati del valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="23121-109">A `uint32` value that specifies the data type of the property value.</span></span> <span data-ttu-id="23121-110">Viene restituito 0 per un valore string e 1 per un tipo numerico.</span><span class="sxs-lookup"><span data-stu-id="23121-110">It returns 0 for a string value and 1 for a numerical type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23121-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="23121-111">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23121-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23121-112">See Also</span></span>  
 <span data-ttu-id="23121-113">[Configurazione di protocolli di rete server e di librerie di rete](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="23121-113">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
