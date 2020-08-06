---
title: Metodo SetBoolValue (classe SqlServiceAdvancedProperty) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- SetBoolValue Method (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetBoolValue method
ms.assetid: 5252b439-fce5-446a-8e57-99e3054bee69
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f0c7142d6f192e94e9850b3c1a8a9481dc15a222
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713968"
---
# <a name="setboolvalue-method-sqlserviceadvancedproperty-class"></a><span data-ttu-id="b1af5-102">Metodo SetBoolValue (classe SqlServiceAdvancedProperty)</span><span class="sxs-lookup"><span data-stu-id="b1af5-102">SetBoolValue Method (SqlServiceAdvancedProperty Class)</span></span>
  <span data-ttu-id="b1af5-103">Imposta il valore booleano di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="b1af5-103">Sets the Boolean value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1af5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b1af5-104">Syntax</span></span>  
  
```  
  
object  
.SetBoolValue [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="b1af5-105">Parti</span><span class="sxs-lookup"><span data-stu-id="b1af5-105">Parts</span></span>  
 <span data-ttu-id="b1af5-106">*object*</span><span class="sxs-lookup"><span data-stu-id="b1af5-106">*object*</span></span>  
 <span data-ttu-id="b1af5-107">Oggetto della [classe SqlServiceAdvancedProperty](../wmi-provider-configuration-classes/sqlserviceadvancedproperty-class/sqlserviceadvancedproperty-class.md) che rappresenta una proprietà avanzata.</span><span class="sxs-lookup"><span data-stu-id="b1af5-107">A [SqlServiceAdvancedProperty Class](../wmi-provider-configuration-classes/sqlserviceadvancedproperty-class/sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="b1af5-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="b1af5-108">Parameters</span></span>  
  
|<span data-ttu-id="b1af5-109">Parametro</span><span class="sxs-lookup"><span data-stu-id="b1af5-109">Parameter</span></span>|<span data-ttu-id="b1af5-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b1af5-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b1af5-111">*BoolValue*</span><span class="sxs-lookup"><span data-stu-id="b1af5-111">*BoolValue*</span></span>|<span data-ttu-id="b1af5-112">Valore booleano che specifica il valore della proprietà avanzata.</span><span class="sxs-lookup"><span data-stu-id="b1af5-112">A Boolean value that specifies the value of the advanced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="b1af5-113">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b1af5-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="b1af5-114">Valore `uint32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="b1af5-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1af5-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b1af5-115">Remarks</span></span>  
 <span data-ttu-id="b1af5-116">Il tipo di valore della proprietà deve essere booleano per impostare la proprietà su un valore booleano.</span><span class="sxs-lookup"><span data-stu-id="b1af5-116">The property value type must be Boolean to set the property to a Boolean value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1af5-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1af5-117">See Also</span></span>  
 <span data-ttu-id="b1af5-118">[Avvio e arresto di servizi](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="b1af5-118">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
