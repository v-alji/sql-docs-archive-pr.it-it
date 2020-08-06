---
title: srv_paramtype (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramtype
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramtype
ms.assetid: badc6d36-8a87-42b5-b28c-9c4f5ded8552
author: rothja
ms.author: jroth
ms.openlocfilehash: 0c4b4006f8214670e3bd2bddfbaabe917fb9d778
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626098"
---
# <a name="srv_paramtype-extended-stored-procedure-api"></a><span data-ttu-id="704cc-102">srv_paramtype (API delle stored procedure estese)</span><span class="sxs-lookup"><span data-stu-id="704cc-102">srv_paramtype (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="704cc-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="704cc-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="704cc-104">Restituisce il tipo di dati di un parametro di chiamata a una stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="704cc-104">Returns the data type of a remote stored procedure call parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="704cc-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="704cc-105">Syntax</span></span>  
  
```  
  
int srv_paramtype (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="704cc-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="704cc-106">Arguments</span></span>  
 <span data-ttu-id="704cc-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="704cc-107">*srvproc*</span></span>  
 <span data-ttu-id="704cc-108">Puntatore alla struttura SRV_PROC che rappresenta l'handle di una determinata connessione client. In questo caso, l'handle che ha ricevuto la chiamata alla stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="704cc-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="704cc-109">La struttura contiene informazioni utilizzate dalla libreria dell'API Stored procedure estesa per gestire le comunicazioni e i dati tra l'applicazione e il client.</span><span class="sxs-lookup"><span data-stu-id="704cc-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="704cc-110">*n*</span><span class="sxs-lookup"><span data-stu-id="704cc-110">*n*</span></span>  
 <span data-ttu-id="704cc-111">Indica il numero del parametro.</span><span class="sxs-lookup"><span data-stu-id="704cc-111">Indicates the number of the parameter.</span></span> <span data-ttu-id="704cc-112">Il primo parametro è 1.</span><span class="sxs-lookup"><span data-stu-id="704cc-112">The first parameter is 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="704cc-113">Restituisce</span><span class="sxs-lookup"><span data-stu-id="704cc-113">Returns</span></span>  
 <span data-ttu-id="704cc-114">Un valore di token per il tipo di dati del parametro.</span><span class="sxs-lookup"><span data-stu-id="704cc-114">A token value for the data type of the parameter.</span></span> <span data-ttu-id="704cc-115">Per informazioni sui tipi di dati, vedere [Tipi di dati &#40;API Stored procedure estesa&#41;](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="704cc-115">For information about data types, see [Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span> <span data-ttu-id="704cc-116">Se non è presente nessun parametro *n* o nessuna stored procedure remota, restituisce -1.</span><span class="sxs-lookup"><span data-stu-id="704cc-116">If there is no *n*th parameter or if there is no remote stored procedure, it returns - 1.</span></span>  
  
 <span data-ttu-id="704cc-117">Questa funzione restituisce i valori seguenti, se il parametro è uno dei [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="704cc-117">This function returns the following values, if the parameter is one of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] data types.</span></span>  
  
|<span data-ttu-id="704cc-118">Nuovi tipi di dati</span><span class="sxs-lookup"><span data-stu-id="704cc-118">New data types</span></span>|<span data-ttu-id="704cc-119">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="704cc-119">Return value</span></span>|  
|--------------------|------------------|  
|`BITN`|<span data-ttu-id="704cc-120">SRVBIT</span><span class="sxs-lookup"><span data-stu-id="704cc-120">SRVBIT</span></span>|  
|`BIGVARCHAR`|<span data-ttu-id="704cc-121">VARCHAR</span><span class="sxs-lookup"><span data-stu-id="704cc-121">VARCHAR</span></span>|  
|`BIGCHAR`|<span data-ttu-id="704cc-122">CHAR</span><span class="sxs-lookup"><span data-stu-id="704cc-122">CHAR</span></span>|  
|`BIGBINARY`|<span data-ttu-id="704cc-123">BINARY</span><span class="sxs-lookup"><span data-stu-id="704cc-123">BINARY</span></span>|  
|`BIGVARBINARY`|<span data-ttu-id="704cc-124">VARBINARY</span><span class="sxs-lookup"><span data-stu-id="704cc-124">VARBINARY</span></span>|  
|`NCHAR`|<span data-ttu-id="704cc-125">CHAR</span><span class="sxs-lookup"><span data-stu-id="704cc-125">CHAR</span></span>|  
|`NVARCHAR`|<span data-ttu-id="704cc-126">VARCHAR</span><span class="sxs-lookup"><span data-stu-id="704cc-126">VARCHAR</span></span>|  
|`NTEXT`|<span data-ttu-id="704cc-127">-1</span><span class="sxs-lookup"><span data-stu-id="704cc-127">-1</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="704cc-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="704cc-128">Remarks</span></span>  
 <span data-ttu-id="704cc-129">Quando viene effettuata una chiamata a una stored procedure remota con parametri, tali parametri possono essere passati per nome o per posizione (senza nome).</span><span class="sxs-lookup"><span data-stu-id="704cc-129">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="704cc-130">Se invece viene effettuata con alcuni parametri passati per nome e altri passati per posizione, si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="704cc-130">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="704cc-131">Il gestore SRV_RPC viene ancora chiamato, ma sembra che non siano presenti parametri e **srv_rpcparams** restituisce 0.</span><span class="sxs-lookup"><span data-stu-id="704cc-131">The SRV_RPC handler is still called, but it appears as if there were no parameters and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="704cc-132">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="704cc-132">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="704cc-133">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="704cc-133">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="704cc-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="704cc-134">See Also</span></span>  
 <span data-ttu-id="704cc-135">[srv_paraminfo &#40;API stored procedure estesa&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="704cc-135">[srv_paraminfo &#40;Extended Stored Procedure API&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="704cc-136">srv_rpcparams &#40;API delle stored procedure estese&#41;</span><span class="sxs-lookup"><span data-stu-id="704cc-136">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
