---
title: Metodo SetNumericalValue (classe SqlServiceAdvancedProperty) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetNumericalValue Method (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetNumericalValue method
ms.assetid: 950ed1e8-0538-4db4-807c-a2c36f43cf6b
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: db823938d77f4e2c67284cae0f11faca12aba6d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722619"
---
# <a name="setnumericalvalue-method-sqlserviceadvancedproperty-class"></a><span data-ttu-id="b36a6-102">Metodo SetNumericalValue (classe SqlServiceAdvancedProperty)</span><span class="sxs-lookup"><span data-stu-id="b36a6-102">SetNumericalValue Method (SqlServiceAdvancedProperty Class)</span></span>
  <span data-ttu-id="b36a6-103">Imposta il valore numerico di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="b36a6-103">Sets the numeric value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b36a6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b36a6-104">Syntax</span></span>  
  
```  
  
object  
.SetNumericalValue(  
NumValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="b36a6-105">Parti</span><span class="sxs-lookup"><span data-stu-id="b36a6-105">Parts</span></span>  
 <span data-ttu-id="b36a6-106">*object*</span><span class="sxs-lookup"><span data-stu-id="b36a6-106">*object*</span></span>  
 <span data-ttu-id="b36a6-107">Oggetto della [classe SqlServiceAdvancedProperty](sqlserviceadvancedproperty-class.md) che rappresenta una proprietà avanzata.</span><span class="sxs-lookup"><span data-stu-id="b36a6-107">A [SqlServiceAdvancedProperty Class](sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="b36a6-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="b36a6-108">Parameters</span></span>  
  
|<span data-ttu-id="b36a6-109">Parametro</span><span class="sxs-lookup"><span data-stu-id="b36a6-109">Parameter</span></span>|<span data-ttu-id="b36a6-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b36a6-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b36a6-111">*NumValue*</span><span class="sxs-lookup"><span data-stu-id="b36a6-111">*NumValue*</span></span>|<span data-ttu-id="b36a6-112">Valore `uint32` che specifica il valore della proprietà avanzata.</span><span class="sxs-lookup"><span data-stu-id="b36a6-112">A `uint32` value that specifies the value of the advanced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="b36a6-113">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b36a6-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="b36a6-114">Valore `uint32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="b36a6-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b36a6-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b36a6-115">Remarks</span></span>  
 <span data-ttu-id="b36a6-116">Il tipo di valore della proprietà deve essere numerico per potere impostare la proprietà su un valore numerico.</span><span class="sxs-lookup"><span data-stu-id="b36a6-116">The property value type must be numeric to be able to set the property to a numeric value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b36a6-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b36a6-117">See Also</span></span>  
 <span data-ttu-id="b36a6-118">[Avvio e arresto di servizi](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="b36a6-118">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
