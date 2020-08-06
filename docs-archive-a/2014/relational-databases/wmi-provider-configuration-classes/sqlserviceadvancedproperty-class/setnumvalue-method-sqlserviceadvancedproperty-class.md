---
title: Metodo SetNumValue (classe SqlServiceAdvancedProperty) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetNumValue Method (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetNumValue method
ms.assetid: a5e1056b-0b75-4ad6-99c1-89246010d815
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 01388855a27dcf14754f677a42c13f8d29cbaacc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717579"
---
# <a name="setnumvalue-method-sqlserviceadvancedproperty-class"></a><span data-ttu-id="0aa07-102">Metodo SetNumValue (classe SqlServiceAdvancedProperty)</span><span class="sxs-lookup"><span data-stu-id="0aa07-102">SetNumValue Method (SqlServiceAdvancedProperty Class)</span></span>
  <span data-ttu-id="0aa07-103">Imposta il valore numerico di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="0aa07-103">Sets the numeric value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0aa07-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0aa07-104">Syntax</span></span>  
  
```  
  
object  
.SetNumValue(  
NumValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="0aa07-105">Parti</span><span class="sxs-lookup"><span data-stu-id="0aa07-105">Parts</span></span>  
 <span data-ttu-id="0aa07-106">*object*</span><span class="sxs-lookup"><span data-stu-id="0aa07-106">*object*</span></span>  
 <span data-ttu-id="0aa07-107">Oggetto della [classe SqlServiceAdvancedProperty](sqlserviceadvancedproperty-class.md) che rappresenta una proprietà avanzata.</span><span class="sxs-lookup"><span data-stu-id="0aa07-107">A [SqlServiceAdvancedProperty Class](sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="0aa07-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="0aa07-108">Parameters</span></span>  
  
|<span data-ttu-id="0aa07-109">Parametro</span><span class="sxs-lookup"><span data-stu-id="0aa07-109">Parameter</span></span>|<span data-ttu-id="0aa07-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0aa07-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0aa07-111">*NumValue*</span><span class="sxs-lookup"><span data-stu-id="0aa07-111">*NumValue*</span></span>|<span data-ttu-id="0aa07-112">Valore `uint32` che specifica il valore della proprietà avanzata.</span><span class="sxs-lookup"><span data-stu-id="0aa07-112">A `uint32` value that specifies the value of the advanced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="0aa07-113">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0aa07-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="0aa07-114">Valore `uint32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="0aa07-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0aa07-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0aa07-115">Remarks</span></span>  
 <span data-ttu-id="0aa07-116">Il tipo di valore della proprietà deve essere numerico per potere impostare la proprietà su un valore numerico.</span><span class="sxs-lookup"><span data-stu-id="0aa07-116">The property value type must be numeric to be able to set the property to a numeric value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0aa07-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0aa07-117">See Also</span></span>  
 <span data-ttu-id="0aa07-118">[Avvio e arresto di servizi](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="0aa07-118">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
