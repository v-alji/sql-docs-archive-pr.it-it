---
title: Metodo SetStringValue (classe SqlServiceAdvancedProperty) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStringValue Method (SqlServiceAdvancedProperty Class )
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStringValue method
ms.assetid: a02d05f6-1072-4709-9ecc-e23e51c8c898
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d7939c6af677ac77b9d8005571406315905bfd65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717574"
---
# <a name="setstringvalue-method-sqlserviceadvancedproperty-class-"></a><span data-ttu-id="c37d6-102">Metodo SetStringValue (classe SqlServiceAdvancedProperty)</span><span class="sxs-lookup"><span data-stu-id="c37d6-102">SetStringValue Method (SqlServiceAdvancedProperty Class )</span></span>
  <span data-ttu-id="c37d6-103">Imposta il valore string di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="c37d6-103">Sets the string value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c37d6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c37d6-104">Syntax</span></span>  
  
```  
  
object  
.SetStringValue(  
StrValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="c37d6-105">Parti</span><span class="sxs-lookup"><span data-stu-id="c37d6-105">Parts</span></span>  
 <span data-ttu-id="c37d6-106">*object*</span><span class="sxs-lookup"><span data-stu-id="c37d6-106">*object*</span></span>  
 <span data-ttu-id="c37d6-107">Oggetto della [classe SqlServiceAdvancedProperty](sqlserviceadvancedproperty-class.md) che rappresenta una proprietà avanzata.</span><span class="sxs-lookup"><span data-stu-id="c37d6-107">A [SqlServiceAdvancedProperty Class](sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="c37d6-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="c37d6-108">Parameters</span></span>  
  
|<span data-ttu-id="c37d6-109">Parametro</span><span class="sxs-lookup"><span data-stu-id="c37d6-109">Parameter</span></span>|<span data-ttu-id="c37d6-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c37d6-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c37d6-111">*StrValue*</span><span class="sxs-lookup"><span data-stu-id="c37d6-111">*StrValue*</span></span>|<span data-ttu-id="c37d6-112">Valore string che specifica il valore della proprietà avanzata.</span><span class="sxs-lookup"><span data-stu-id="c37d6-112">A string value that specifies the value of the advanced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="c37d6-113">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c37d6-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="c37d6-114">Valore `uint32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="c37d6-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c37d6-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c37d6-115">Remarks</span></span>  
 <span data-ttu-id="c37d6-116">Il tipo di valore della proprietà deve essere `string` per potere impostare la proprietà su un valore string.</span><span class="sxs-lookup"><span data-stu-id="c37d6-116">The property value type must be `string` to be able to set the property to a string value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c37d6-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c37d6-117">See Also</span></span>  
 <span data-ttu-id="c37d6-118">[Avvio e arresto di servizi](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c37d6-118">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
