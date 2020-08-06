---
title: Metodo SetServiceAccount (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetServiceAccount Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetServiceAccount method
ms.assetid: d5782892-e9d8-4d48-92af-b3afe9610f84
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 6087a531802a7752ea794a44147c79fb7c3fa3ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712872"
---
# <a name="setserviceaccount-method-sqlservice-class"></a><span data-ttu-id="47fa0-102">Metodo SetServiceAccount (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="47fa0-102">SetServiceAccount Method (SqlService Class)</span></span>
  <span data-ttu-id="47fa0-103">Tenta di modificare il nome utente e la password con cui è in esecuzione l'istanza del servizio.</span><span class="sxs-lookup"><span data-stu-id="47fa0-103">Attempts to change the user name and password that the service instance runs under.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47fa0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="47fa0-104">Syntax</span></span>  
  
```  
  
object  
.SetServiceAccount(  
ServiceStartName , ServiceStartPassword  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="47fa0-105">Parti</span><span class="sxs-lookup"><span data-stu-id="47fa0-105">Parts</span></span>  
 <span data-ttu-id="47fa0-106">*object*</span><span class="sxs-lookup"><span data-stu-id="47fa0-106">*object*</span></span>  
 <span data-ttu-id="47fa0-107">Oggetto della [classe SqlService](sqlservice-class.md) che rappresenta il servizio.</span><span class="sxs-lookup"><span data-stu-id="47fa0-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="47fa0-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="47fa0-108">Parameters</span></span>  
 <span data-ttu-id="47fa0-109">*ServiceStartName*</span><span class="sxs-lookup"><span data-stu-id="47fa0-109">*ServiceStartName*</span></span>  
 <span data-ttu-id="47fa0-110">Valore string che specifica il nome dell'account con cui è in esecuzione il servizio.</span><span class="sxs-lookup"><span data-stu-id="47fa0-110">A string value that specifies the account name that the service runs under.</span></span> <span data-ttu-id="47fa0-111">A seconda del tipo di servizio, il nome dell'account potrebbe essere nel formato NomeDominio\NomeUtente.</span><span class="sxs-lookup"><span data-stu-id="47fa0-111">Depending on the service type, the account name might be in the form of DomainName\Username.</span></span> <span data-ttu-id="47fa0-112">Durante l'esecuzione il processo del servizio viene registrato utilizzando uno di due formati:</span><span class="sxs-lookup"><span data-stu-id="47fa0-112">When it runs, the service process will be logged using one of two forms:</span></span>  
  
-   <span data-ttu-id="47fa0-113">Se l'account appartiene al dominio predefinito, è possibile specificare \Nomeutente.</span><span class="sxs-lookup"><span data-stu-id="47fa0-113">If the account belongs to the built-in domain, \Username can be specified.</span></span>  
  
-   <span data-ttu-id="47fa0-114">Se viene specificato NULL, il servizio verrà connesso come account **LocalSystem** .</span><span class="sxs-lookup"><span data-stu-id="47fa0-114">If NULL is specified, the service will be logged on as the **LocalSystem** account.</span></span>  
  
 <span data-ttu-id="47fa0-115">Per i driver a livello di sistema o del kernel, *StartName* contiene il nome dell'oggetto del driver, \FileSystem\Rdr o \Driver\Xns, usato dal sistema di i/O per caricare il driver di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="47fa0-115">For kernel or system-level drivers, *StartName* contains the driver object name, either \FileSystem\Rdr or \Driver\Xns, which the I/O system uses to load the device driver.</span></span> <span data-ttu-id="47fa0-116">Se viene specificato NULL, il driver viene eseguito con un nome dell'oggetto predefinito creato dal sistema I/O in base sul nome del servizio, ad esempio DWDOM\Admin.</span><span class="sxs-lookup"><span data-stu-id="47fa0-116">If NULL is specified, the driver runs with a default object name created by the I/O system based on the service name, for example, DWDOM\Admin.</span></span>  
  
 <span data-ttu-id="47fa0-117">*ServiceStartPassword*</span><span class="sxs-lookup"><span data-stu-id="47fa0-117">*ServiceStartPassword*</span></span>  
 <span data-ttu-id="47fa0-118">Valore stringa che specifica la password per il nome dell'account nel parametro *StartName* .</span><span class="sxs-lookup"><span data-stu-id="47fa0-118">A string value that specifies the password for the account name in the *StartName* parameter.</span></span> <span data-ttu-id="47fa0-119">Specificare NULL se non si modifica la password.</span><span class="sxs-lookup"><span data-stu-id="47fa0-119">Specify NULL if you are not changing the password.</span></span> <span data-ttu-id="47fa0-120">Specificare una stringa vuota se il servizio non dispone di password.</span><span class="sxs-lookup"><span data-stu-id="47fa0-120">Specify an empty string if the service has no password.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="47fa0-121">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="47fa0-121">Property Value/Return Value</span></span>  
 <span data-ttu-id="47fa0-122">Valore `uint32` che è 0 se il servizio è stato modificato correttamente 0 1 se la richiesta non è supportata.</span><span class="sxs-lookup"><span data-stu-id="47fa0-122">A `uint32` value, which is 0 if the service was successfully modified or 1 if the request is not supported.</span></span> <span data-ttu-id="47fa0-123">Qualsiasi altro numero indica un errore.</span><span class="sxs-lookup"><span data-stu-id="47fa0-123">Any other number indicates an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47fa0-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="47fa0-124">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47fa0-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47fa0-125">See Also</span></span>  
 <span data-ttu-id="47fa0-126">[Avvio e arresto di servizi](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="47fa0-126">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
