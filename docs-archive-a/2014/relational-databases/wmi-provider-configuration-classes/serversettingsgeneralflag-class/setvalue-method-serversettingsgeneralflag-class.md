---
title: Metodo SetValue (classe ServerSettingsGeneralFlag) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetValue Method (ServerSettingsGeneralFlag Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetValue method
ms.assetid: a889feac-c0e0-4635-b506-843863d86967
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 74c4c189b72b7a469794e0828faf062a88cdf46f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726808"
---
# <a name="setvalue-method-serversettingsgeneralflag-class"></a><span data-ttu-id="021e3-102">Metodo SetValue (classe ServerSettingsGeneralFlag)</span><span class="sxs-lookup"><span data-stu-id="021e3-102">SetValue Method (ServerSettingsGeneralFlag Class)</span></span>
  <span data-ttu-id="021e3-103">Imposta tutti i valori del flag a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="021e3-103">Sets all the values of the referenced flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="021e3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="021e3-104">Syntax</span></span>  
  
```  
  
object  
.SetValue(  
Value  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="021e3-105">Parti</span><span class="sxs-lookup"><span data-stu-id="021e3-105">Parts</span></span>  
 <span data-ttu-id="021e3-106">*object*</span><span class="sxs-lookup"><span data-stu-id="021e3-106">*object*</span></span>  
 <span data-ttu-id="021e3-107">Oggetto della [classe ServerSettingsGeneralFlag](serversettingsgeneralflag-class.md) che rappresenta un flag generale per le impostazioni del server.</span><span class="sxs-lookup"><span data-stu-id="021e3-107">A [ServerSettingsGeneralFlag Class](serversettingsgeneralflag-class.md) object that represents a general flag for the server settings.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="021e3-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="021e3-108">Parameters</span></span>  
  
|<span data-ttu-id="021e3-109">Parametro</span><span class="sxs-lookup"><span data-stu-id="021e3-109">Parameter</span></span>|<span data-ttu-id="021e3-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="021e3-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="021e3-111">*Valore*</span><span class="sxs-lookup"><span data-stu-id="021e3-111">*Value*</span></span>|<span data-ttu-id="021e3-112">Valore booleano che specifica il valore del flag.</span><span class="sxs-lookup"><span data-stu-id="021e3-112">A Boolean value that specifies the value of the flag.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="021e3-113">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="021e3-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="021e3-114">Valore `uint32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="021e3-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="021e3-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="021e3-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="021e3-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="021e3-116">See Also</span></span>  
 <span data-ttu-id="021e3-117">[Configurazione di protocolli di rete server e di librerie di rete](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="021e3-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
