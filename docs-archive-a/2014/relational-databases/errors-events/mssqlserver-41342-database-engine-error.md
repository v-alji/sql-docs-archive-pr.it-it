---
title: MSSQLSERVER_41342 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41342 (Database Engine error)
ms.assetid: 28270d98-c543-4e7d-b40c-2200e38dce1c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c0269322b30cee88e5ba3d50b6d391464b735f54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635084"
---
# <a name="mssqlserver_41342"></a><span data-ttu-id="76870-102">MSSQLSERVER_41342</span><span class="sxs-lookup"><span data-stu-id="76870-102">MSSQLSERVER_41342</span></span>
    
## <a name="details"></a><span data-ttu-id="76870-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="76870-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="76870-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="76870-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="76870-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="76870-105">Event ID</span></span>|<span data-ttu-id="76870-106">41342</span><span class="sxs-lookup"><span data-stu-id="76870-106">41342</span></span>|  
|<span data-ttu-id="76870-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="76870-107">Event Source</span></span>|<span data-ttu-id="76870-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="76870-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="76870-109">Componente</span><span class="sxs-lookup"><span data-stu-id="76870-109">Component</span></span>|<span data-ttu-id="76870-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="76870-110">SQLEngine</span></span>|  
|<span data-ttu-id="76870-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="76870-111">Symbolic Name</span></span>|<span data-ttu-id="76870-112">HK_HW_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="76870-112">HK_HW_NOT_SUPPORTED</span></span>|  
|<span data-ttu-id="76870-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="76870-113">Message Text</span></span>|<span data-ttu-id="76870-114">Il modello del processore del sistema non supporta la creazione di *costrutto*.</span><span class="sxs-lookup"><span data-stu-id="76870-114">The model of the processor on the system does not support creating *construct*.</span></span> <span data-ttu-id="76870-115">Questo errore si verifica in genere nei processori meno recenti.</span><span class="sxs-lookup"><span data-stu-id="76870-115">This error typically occurs with older processors.</span></span> <span data-ttu-id="76870-116">Per informazioni sui modelli supportati, vedere la documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76870-116">See [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online for information on supported models.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="76870-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="76870-117">Explanation</span></span>  
 <span data-ttu-id="76870-118">Per le tabelle con ottimizzazione per la memoria è richiesto un modello di processore che supporta le operazioni di scambio e confronto atomiche su valori a 128 bit, che richiedono l'istruzione di assembly CMPXCHG16B.</span><span class="sxs-lookup"><span data-stu-id="76870-118">Memory-optimized tables require a processor model that supports atomic compare-and-exchange operations on 128-bit values, which require the assembly instruction CMPXCHG16B.</span></span> <span data-ttu-id="76870-119">Alcuni modelli di processore AMD meno recenti non supportano l'istruzione CMPXCHG16B.</span><span class="sxs-lookup"><span data-stu-id="76870-119">Certain older AMD processor models do not support the CMPXCHG16B instruction.</span></span> <span data-ttu-id="76870-120">Inoltre, alcuni ambienti di virtualizzazione non consentono l'utilizzo di questa istruzione per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="76870-120">Also, certain virtualization environments do not enable this instruction by default.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="76870-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="76870-121">User Action</span></span>  
 <span data-ttu-id="76870-122">Aggiornare il processore.</span><span class="sxs-lookup"><span data-stu-id="76870-122">Upgrade your processor.</span></span> <span data-ttu-id="76870-123">Se il processore supporta l'istruzione e si sta eseguendo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in una macchina virtuale, modificare la configurazione per supportare l'istruzione CMPXCHG16B.</span><span class="sxs-lookup"><span data-stu-id="76870-123">If your processor supports the instruction and you are running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in a virtual machine, change the configuration to support the instruction CMPXCHG16B.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76870-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76870-124">See Also</span></span>  
 [<span data-ttu-id="76870-125">OLTP in memoria &#40;ottimizzazione per la memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="76870-125">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
