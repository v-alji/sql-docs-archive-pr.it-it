---
title: Proprietà server (pagina Processori) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.serverproperties.processor.f1
ms.assetid: cc1581a2-492b-41f0-bda5-17909b65c4f7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c4d241f01de7ac961832e77bb09483cff275deb6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629592"
---
# <a name="server-properties-processors-page"></a><span data-ttu-id="521a4-102">Proprietà server (pagina Processori)</span><span class="sxs-lookup"><span data-stu-id="521a4-102">Server Properties (Processors Page)</span></span>
  <span data-ttu-id="521a4-103">Utilizzare questa pagina per visualizzare o modificare le opzioni del processore.</span><span class="sxs-lookup"><span data-stu-id="521a4-103">Use this page to view or modify your processor options.</span></span> <span data-ttu-id="521a4-104">Le impostazioni Affinità processori sono abilitate solo se sono installati più processori.</span><span class="sxs-lookup"><span data-stu-id="521a4-104">Processor affinity settings are only enabled when more than one processor is installed.</span></span>  
  
## <a name="options"></a><span data-ttu-id="521a4-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="521a4-105">Options</span></span>  
 <span data-ttu-id="521a4-106">**Affinità processori**</span><span class="sxs-lookup"><span data-stu-id="521a4-106">**Processor Affinity**</span></span>  
 <span data-ttu-id="521a4-107">Consente di assegnare i processori a thread specifici, in modo da eliminare i ricaricamenti dei processori e ridurre la migrazione dei thread tra i processori.</span><span class="sxs-lookup"><span data-stu-id="521a4-107">Assigns processors to specific threads to eliminating processor reloads and reduce thread migration across processors.</span></span> <span data-ttu-id="521a4-108">Per altre informazioni, vedere [Opzione di configurazione del server affinity mask](affinity-mask-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="521a4-108">For more information, see [affinity mask Server Configuration Option](affinity-mask-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="521a4-109">**Affinità I/O**</span><span class="sxs-lookup"><span data-stu-id="521a4-109">**I/O Affinity**</span></span>  
 <span data-ttu-id="521a4-110">Associa l'I/O su disco di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a un determinato subset di CPU.</span><span class="sxs-lookup"><span data-stu-id="521a4-110">Binds [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disk I/Os to a specified subset of CPUs.</span></span> <span data-ttu-id="521a4-111">Per altre informazioni, vedere [Opzione di configurazione del server affinity I/O mask](affinity-input-output-mask-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="521a4-111">For more information, see [affinity Input-Output mask Server Configuration Option](affinity-input-output-mask-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="521a4-112">**Imposta automaticamente maschera di affinità processori per tutti i processori**</span><span class="sxs-lookup"><span data-stu-id="521a4-112">**Automatically set processor affinity mask for all processors**</span></span>  
 <span data-ttu-id="521a4-113">Consente a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di impostare l'affinità processori.</span><span class="sxs-lookup"><span data-stu-id="521a4-113">Allows [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to set the processor affinity.</span></span>  
  
 <span data-ttu-id="521a4-114">**Imposta automaticamente maschera di affinità di I/O per tutti i processori**</span><span class="sxs-lookup"><span data-stu-id="521a4-114">**Automatically set I/O affinity mask for all processors**</span></span>  
 <span data-ttu-id="521a4-115">Consente a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di impostare l'affinità di I/O.</span><span class="sxs-lookup"><span data-stu-id="521a4-115">Allows [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to set the I/O affinity.</span></span>  
  
 <span data-ttu-id="521a4-116">**Numero massimo thread di lavoro**</span><span class="sxs-lookup"><span data-stu-id="521a4-116">**Maximum worker threads**</span></span>  
 <span data-ttu-id="521a4-117">Il valore 0 consente a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di impostare dinamicamente il numero di thread di lavoro.</span><span class="sxs-lookup"><span data-stu-id="521a4-117">0 allows [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to dynamically set the number of worker threads.</span></span> <span data-ttu-id="521a4-118">Si tratta dell'impostazione ottimale per la maggior parte dei sistemi.</span><span class="sxs-lookup"><span data-stu-id="521a4-118">This setting is best for most systems.</span></span> <span data-ttu-id="521a4-119">A seconda della configurazione di sistema, è tuttavia possibile che l'impostazione di questa opzione su un valore specifico migliori le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="521a4-119">However, depending on your system configuration, setting this option to a specific value sometimes improves performance.</span></span> <span data-ttu-id="521a4-120">Per altre informazioni, vedere [Configurare l'opzione di configurazione del server max worker threads](configure-the-max-worker-threads-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="521a4-120">For more information, see [Configure the max worker threads Server Configuration Option](configure-the-max-worker-threads-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="521a4-121">**Aumenta priorità di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="521a4-121">**Boost SQL Server priority**</span></span>  
 <span data-ttu-id="521a4-122">Consente di specificare se eseguire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con una priorità di pianificazione di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows maggiore rispetto agli altri processi in esecuzione nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="521a4-122">Specifies whether [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should run at a higher [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows scheduling priority than other processes on the same computer.</span></span> <span data-ttu-id="521a4-123">Per altre informazioni, vedere [Configurare l'opzione di configurazione del server priority boost](configure-the-priority-boost-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="521a4-123">For more information, see [Configure the priority boost Server Configuration Option](configure-the-priority-boost-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="521a4-124">**Usa fiber Windows (lightweight pooling)**</span><span class="sxs-lookup"><span data-stu-id="521a4-124">**Use Windows fibers (lightweight pooling)**</span></span>  
 <span data-ttu-id="521a4-125">Consente di utilizzare i fiber Windows anziché i thread per il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="521a4-125">Use Windows fibers instead of threads for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="521a4-126">Si noti che l'opzione è disponibile solo in Windows 2003 Server Edition.</span><span class="sxs-lookup"><span data-stu-id="521a4-126">Note that this is only available in Windows 2003 Server Edition.</span></span> <span data-ttu-id="521a4-127">Per altre informazioni, vedere [lightweight pooling Server Configuration Option](lightweight-pooling-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="521a4-127">For more information, see [lightweight pooling Server Configuration Option](lightweight-pooling-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="521a4-128">**Valori configurati**</span><span class="sxs-lookup"><span data-stu-id="521a4-128">**Configured Values**</span></span>  
 <span data-ttu-id="521a4-129">Consente di visualizzare i valori configurati per le opzioni nel riquadro.</span><span class="sxs-lookup"><span data-stu-id="521a4-129">Displays the configured values for the options on this pane.</span></span> <span data-ttu-id="521a4-130">Se si modificano i valori, fare clic su **Valori correnti** per verificare se le modifiche sono diventate effettive.</span><span class="sxs-lookup"><span data-stu-id="521a4-130">If you change these values, click **Running Values** to see whether the changes have taken effect.</span></span> <span data-ttu-id="521a4-131">In caso contrario, l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deve essere prima riavviata.</span><span class="sxs-lookup"><span data-stu-id="521a4-131">If they have not, the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be restarted first.</span></span>  
  
 <span data-ttu-id="521a4-132">**Valori correnti**</span><span class="sxs-lookup"><span data-stu-id="521a4-132">**Running Values**</span></span>  
 <span data-ttu-id="521a4-133">Consente di visualizzare i valori correnti per le opzioni contenute nel riquadro.</span><span class="sxs-lookup"><span data-stu-id="521a4-133">View the currently running values for the options on this pane.</span></span> <span data-ttu-id="521a4-134">I valori sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="521a4-134">These values are read-only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="521a4-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="521a4-135">See Also</span></span>  
 [<span data-ttu-id="521a4-136">Opzioni di configurazione del server &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="521a4-136">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
