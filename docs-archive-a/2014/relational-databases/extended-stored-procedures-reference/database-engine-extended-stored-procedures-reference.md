---
title: Guida di riferimento per i programmatori delle stored procedure estese | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
topic_type:
- apiref
- apinav
helpviewer_keywords:
- extended stored procedures [SQL Server], listed
ms.assetid: 4e9d0374-0927-4f17-bab9-2215b1b8fea8
author: rothja
ms.author: jroth
ms.openlocfilehash: f3b1beade751cd7a7407f3c33eb7f8ae58c9fd4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637324"
---
# <a name="extended-stored-procedures-programmer39s-reference"></a><span data-ttu-id="9dbeb-102">Informazioni di riferimento sul programmatore di stored procedure estese&#39;s</span><span class="sxs-lookup"><span data-stu-id="9dbeb-102">Extended Stored Procedures Programmer&#39;s Reference</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="9dbeb-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="9dbeb-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="9dbeb-104">L' [!INCLUDE[msCoName](../../includes/msconame-md.md)] API stored procedure estesa, inclusa in precedenza in Open Data Services, fornisce un'Application Programming Interface basata su server (API) per l'estensione della [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] funzionalità.</span><span class="sxs-lookup"><span data-stu-id="9dbeb-104">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Extended Stored Procedure API, previously part of Open Data Services, provides a server-based application programming interface (API) for extending [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] functionality.</span></span> <span data-ttu-id="9dbeb-105">L'API è costituita dalle macro e dalle funzioni C e C++ utilizzate per compilare applicazioni.</span><span class="sxs-lookup"><span data-stu-id="9dbeb-105">The API consists of C and C++ functions and macros used to build applications.</span></span>  
  
 <span data-ttu-id="9dbeb-106">Con la comparsa delle più recenti e avanzate tecnologie, ad esempio l'integrazione con CLR, la necessità di ricorrere alle stored procedure estese è stata ampiamente soppiantata.</span><span class="sxs-lookup"><span data-stu-id="9dbeb-106">With the emergence of newer and more powerful technologies such as CLR integration, the need for extended stored procedures has largely been replaced.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9dbeb-107">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="9dbeb-107">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="9dbeb-108">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="9dbeb-108">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9dbeb-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="9dbeb-109">In This Section</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="9dbeb-110">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="9dbeb-110">Data Types</span></span>](srv-pfield-extended-stored-procedure-api.md)|  
|[<span data-ttu-id="9dbeb-111">srv_alloc</span><span class="sxs-lookup"><span data-stu-id="9dbeb-111">srv_alloc</span></span>](srv-alloc-extended-stored-procedure-api.md)||  
|[<span data-ttu-id="9dbeb-112">srv_convert</span><span class="sxs-lookup"><span data-stu-id="9dbeb-112">srv_convert</span></span>](srv-pfieldex-extended-stored-procedure-api.md)|  
|[<span data-ttu-id="9dbeb-113">srv_describe</span><span class="sxs-lookup"><span data-stu-id="9dbeb-113">srv_describe</span></span>](srv-rpcdb-extended-stored-procedure-api.md)|  
|[<span data-ttu-id="9dbeb-114">srv_getbindtoken</span><span class="sxs-lookup"><span data-stu-id="9dbeb-114">srv_getbindtoken</span></span>](srv-rpcname-extended-stored-procedure-api.md)|  
|[<span data-ttu-id="9dbeb-115">srv_got_attention</span><span class="sxs-lookup"><span data-stu-id="9dbeb-115">srv_got_attention</span></span>](srv-rpcnumber-extended-stored-procedure-api.md)|  
||[<span data-ttu-id="9dbeb-116">srv_rpcoptions</span><span class="sxs-lookup"><span data-stu-id="9dbeb-116">srv_rpcoptions</span></span>](srv-rpcoptions-extended-stored-procedure-api.md)|  
|[<span data-ttu-id="9dbeb-117">srv_message_handler</span><span class="sxs-lookup"><span data-stu-id="9dbeb-117">srv_message_handler</span></span>](srv-rpcowner-extended-stored-procedure-api.md)|  
|[<span data-ttu-id="9dbeb-118">srv_paramdata</span><span class="sxs-lookup"><span data-stu-id="9dbeb-118">srv_paramdata</span></span>](srv-rpcparams-extended-stored-procedure-api.md)|  
|[<span data-ttu-id="9dbeb-119">srv_paraminfo</span><span class="sxs-lookup"><span data-stu-id="9dbeb-119">srv_paraminfo</span></span>](srv-senddone-extended-stored-procedure-api.md)|  
|[<span data-ttu-id="9dbeb-120">srv_paramlen</span><span class="sxs-lookup"><span data-stu-id="9dbeb-120">srv_paramlen</span></span>](srv-sendmsg-extended-stored-procedure-api.md)|  
|[<span data-ttu-id="9dbeb-121">srv_parammaxlen</span><span class="sxs-lookup"><span data-stu-id="9dbeb-121">srv_parammaxlen</span></span>](srv-sendrow-extended-stored-procedure-api.md)|  
|[<span data-ttu-id="9dbeb-122">srv_paramname</span><span class="sxs-lookup"><span data-stu-id="9dbeb-122">srv_paramname</span></span>](srv-setcoldata-extended-stored-procedure-api.md)|  
|[<span data-ttu-id="9dbeb-123">srv_paramnumber</span><span class="sxs-lookup"><span data-stu-id="9dbeb-123">srv_paramnumber</span></span>](srv-setcollen-extended-stored-procedure-api.md)|  
|[<span data-ttu-id="9dbeb-124">srv_paramset</span><span class="sxs-lookup"><span data-stu-id="9dbeb-124">srv_paramset</span></span>](srv-setutype-extended-stored-procedure-api.md)|  
|[<span data-ttu-id="9dbeb-125">srv_paramsetoutput</span><span class="sxs-lookup"><span data-stu-id="9dbeb-125">srv_paramsetoutput</span></span>](srv-willconvert-extended-stored-procedure-api.md)|  
|[<span data-ttu-id="9dbeb-126">srv_paramstatus</span><span class="sxs-lookup"><span data-stu-id="9dbeb-126">srv_paramstatus</span></span>](srv-wsendmsg-extended-stored-procedure-api.md)|  
|[<span data-ttu-id="9dbeb-127">srv_paramtype</span><span class="sxs-lookup"><span data-stu-id="9dbeb-127">srv_paramtype</span></span>](srv-paramtype-extended-stored-procedure-api.md)||  
  
  
