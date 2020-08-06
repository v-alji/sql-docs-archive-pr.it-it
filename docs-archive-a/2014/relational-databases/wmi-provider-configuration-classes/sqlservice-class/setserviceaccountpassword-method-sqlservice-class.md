---
title: Metodo SetServiceAccountPassword (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetServiceAccountPassword Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetServiceAccountPassword method
ms.assetid: e577a1ac-985c-4799-bb38-9393efc3def2
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: e7a83a6d3686b2ec2df98ae79b4c9d3347f621ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712875"
---
# <a name="setserviceaccountpassword-method-sqlservice-class"></a><span data-ttu-id="ed53f-102">Metodo SetServiceAccountPassword (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="ed53f-102">SetServiceAccountPassword Method (SqlService Class)</span></span>
  <span data-ttu-id="ed53f-103">Modifica la password per l'account con cui è in esecuzione il servizio a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="ed53f-103">Modifies the password for the account that the referenced service runs under.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed53f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ed53f-104">Syntax</span></span>  
  
```  
  
object  
.SetServiceAccountPassword(  
AccountOldPassword , ServiceStartPassword  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="ed53f-105">Parti</span><span class="sxs-lookup"><span data-stu-id="ed53f-105">Parts</span></span>  
 <span data-ttu-id="ed53f-106">*object*</span><span class="sxs-lookup"><span data-stu-id="ed53f-106">*object*</span></span>  
 <span data-ttu-id="ed53f-107">Oggetto della [classe SqlService](sqlservice-class.md) che rappresenta il servizio.</span><span class="sxs-lookup"><span data-stu-id="ed53f-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="ed53f-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="ed53f-108">Parameters</span></span>  
 <span data-ttu-id="ed53f-109">*AccountOldPassword*</span><span class="sxs-lookup"><span data-stu-id="ed53f-109">*AccountOldPassword*</span></span>  
 <span data-ttu-id="ed53f-110">Valore string che specifica la password esistente per l'account.</span><span class="sxs-lookup"><span data-stu-id="ed53f-110">A string value that specifies the existing password for the account.</span></span>  
  
 <span data-ttu-id="ed53f-111">*ServiceStartPassword*</span><span class="sxs-lookup"><span data-stu-id="ed53f-111">*ServiceStartPassword*</span></span>  
 <span data-ttu-id="ed53f-112">Valore string che specifica la nuova password per l'account.</span><span class="sxs-lookup"><span data-stu-id="ed53f-112">A string value that specifies the new password for the account.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="ed53f-113">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ed53f-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="ed53f-114">Valore `uint32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="ed53f-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed53f-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ed53f-115">Remarks</span></span>  
  
