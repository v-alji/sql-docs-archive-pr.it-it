---
title: srv_alloc (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_alloc
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_alloc
ms.assetid: 91505c59-a273-452f-b71d-5e8205c21863
author: rothja
ms.author: jroth
ms.openlocfilehash: 7b372c1b43987e5bebd1fb82e995dc6d262455ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626102"
---
# <a name="srv_alloc-extended-stored-procedure-api"></a><span data-ttu-id="39b92-102">srv_alloc (API delle stored procedure estese)</span><span class="sxs-lookup"><span data-stu-id="39b92-102">srv_alloc (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="39b92-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="39b92-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="39b92-104">Alloca memoria dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="39b92-104">Allocates memory dynamically.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39b92-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39b92-105">Syntax</span></span>  
  
```  
  
void * srv_alloc ( DBINT  
size  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="39b92-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="39b92-106">Arguments</span></span>  
 <span data-ttu-id="39b92-107">*size*</span><span class="sxs-lookup"><span data-stu-id="39b92-107">*size*</span></span>  
 <span data-ttu-id="39b92-108">Specifica il numero di byte da allocare.</span><span class="sxs-lookup"><span data-stu-id="39b92-108">Specifies the number of bytes to allocate.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="39b92-109">Restituisce</span><span class="sxs-lookup"><span data-stu-id="39b92-109">Returns</span></span>  
 <span data-ttu-id="39b92-110">Un puntatore al nuovo spazio allocato.</span><span class="sxs-lookup"><span data-stu-id="39b92-110">A pointer to the newly allocated space.</span></span> <span data-ttu-id="39b92-111">Se i byte di *size* non possono essere allocati, viene restituito un puntatore Null.</span><span class="sxs-lookup"><span data-stu-id="39b92-111">If *size* bytes cannot be allocated, a null pointer is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39b92-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="39b92-112">Remarks</span></span>  
 <span data-ttu-id="39b92-113">La funzione **srv_alloc** è equivalente alla funzione **GlobalAlloc** dell'API [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="39b92-113">The **srv_alloc** function is equivalent to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows API  **GlobalAlloc** function.</span></span> <span data-ttu-id="39b92-114">Normali funzioni di gestione della memoria di runtime del linguaggio C dell'API Windows possono essere utilizzate in un'applicazione API di stored procedure estese.</span><span class="sxs-lookup"><span data-stu-id="39b92-114">Normal Windows API C run-time memory management functions can be used in an Extended Stored Procedure API application.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="39b92-115">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="39b92-115">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="39b92-116">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="39b92-116">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
