---
title: Metodo sedefaults (classe ServerSettings) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDefaults Method (ServerSettings Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDefaults method
ms.assetid: 76e4cfab-4b15-4da4-bb2f-8aac6f927f79
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 93dd2eee5a395d4d7463ebf9b85530fcf82d1888
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715112"
---
# <a name="setdefaults-method-serversettings-class"></a><span data-ttu-id="e4cd5-102">Metodo SetDefaults (classe ServerSettings)</span><span class="sxs-lookup"><span data-stu-id="e4cd5-102">SetDefaults Method (ServerSettings Class)</span></span>
  <span data-ttu-id="e4cd5-103">Imposta tutti i valori predefiniti per l'istanza di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] con l'opzione per sovrascrivere i dati esistenti.</span><span class="sxs-lookup"><span data-stu-id="e4cd5-103">Sets all the default values for the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with the option to overwrite existing data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4cd5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e4cd5-104">Syntax</span></span>  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="e4cd5-105">Parti</span><span class="sxs-lookup"><span data-stu-id="e4cd5-105">Parts</span></span>  
 <span data-ttu-id="e4cd5-106">*object*</span><span class="sxs-lookup"><span data-stu-id="e4cd5-106">*object*</span></span>  
 <span data-ttu-id="e4cd5-107">Oggetto della [classe ServerSettings](serversettings-class.md) che rappresenta un' [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] istanza del client.</span><span class="sxs-lookup"><span data-stu-id="e4cd5-107">A [ServerSettings Class](serversettings-class.md) object that represents a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client instance.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="e4cd5-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="e4cd5-108">Parameters</span></span>  
  
|<span data-ttu-id="e4cd5-109">Parametro</span><span class="sxs-lookup"><span data-stu-id="e4cd5-109">Parameter</span></span>|<span data-ttu-id="e4cd5-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e4cd5-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e4cd5-111">*OverwriteAll*</span><span class="sxs-lookup"><span data-stu-id="e4cd5-111">*OverwriteAll*</span></span>|<span data-ttu-id="e4cd5-112">Valore booleano che specifica se sovrascrivere i valori esistenti nell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. `true` per sovrascrivere i dati esistenti; `false` se i dati esistenti non devono essere sovrascritti.</span><span class="sxs-lookup"><span data-stu-id="e4cd5-112">A Boolean value that specifies whether to overwrite existing values on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]: `true` to overwrite existing data, or `false` if existing data is not to be overwritten.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="e4cd5-113">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e4cd5-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="e4cd5-114">Valore u`int32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="e4cd5-114">A u`int32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4cd5-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e4cd5-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4cd5-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4cd5-116">See Also</span></span>  
 <span data-ttu-id="e4cd5-117">[Configurazione di protocolli di rete server e di librerie di rete](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="e4cd5-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
