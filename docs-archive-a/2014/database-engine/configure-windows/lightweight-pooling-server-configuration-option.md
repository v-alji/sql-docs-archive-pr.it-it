---
title: Opzione di configurazione del server lightweight pooling | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- default lightweight pooling
- decreasing overhead
- lightweight pooling option
- system overhead [SQL Server]
- performance [SQL Server], lightweight pooling
- context switching [SQL Server], lightweight pooling option
- excessive context switching [SQL Server]
- reducing overhead
- overhead [SQL Server]
ms.assetid: 2dc11b61-d065-4126-8e00-acf40390f9fb
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 549ff7451a31b48459b5a290b94ad406c3768a91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629606"
---
# <a name="lightweight-pooling-server-configuration-option"></a><span data-ttu-id="6331e-102">Opzione di configurazione del server lightweight pooling</span><span class="sxs-lookup"><span data-stu-id="6331e-102">lightweight pooling Server Configuration Option</span></span>
  <span data-ttu-id="6331e-103">L'opzione **lightweight pooling** consente di ridurre l'overhead del sistema associato a un'eccessiva attività di scambio del contesto che talvolta si riscontra negli ambienti SMP (multiprocessori simmetrici, Symmetric Multiprocessor).</span><span class="sxs-lookup"><span data-stu-id="6331e-103">Use the **lightweight pooling** option to provide a means of reducing the system overhead associated with the excessive context switching sometimes seen in symmetric multiprocessing (SMP) environments.</span></span> <span data-ttu-id="6331e-104">Quando si verifica un'eccessiva attività di cambio del contesto, l'opzione lightweight pooling può assicurare una migliore velocità effettiva eseguendo direttamente il cambio del contesto e quindi riducendo le transizioni utente/kernel ring.</span><span class="sxs-lookup"><span data-stu-id="6331e-104">When excessive context switching is present, lightweight pooling can provide better throughput by performing the context switching inline, thus helping to reduce user/kernel ring transitions.</span></span>  
  
 <span data-ttu-id="6331e-105">La modalità fiber viene utilizzata in situazioni specifiche in cui il cambio di contesto dei thread di lavoro UMS costituisce un collo di bottiglia critico per le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="6331e-105">Fiber mode is intended for certain situations in which the context switching of the UMS workers are the critical bottleneck in performance.</span></span> <span data-ttu-id="6331e-106">Poiché questa situazione è poco frequente, la modalità fiber consente raramente di ottimizzare le prestazioni o la scalabilità in un sistema tipico.</span><span class="sxs-lookup"><span data-stu-id="6331e-106">Because this is rare, fiber mode rarely enhances performance or scalability on the typical system.</span></span> <span data-ttu-id="6331e-107">I miglioramenti apportati al cambio di contesto in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] hanno anche ridotto la necessità di usare la modalità fiber.</span><span class="sxs-lookup"><span data-stu-id="6331e-107">Improved context switching in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] has also reduced the need for fiber mode.</span></span> <span data-ttu-id="6331e-108">Si consiglia di non utilizzare la modalità fiber per la pianificazione dell'operazione di routine.</span><span class="sxs-lookup"><span data-stu-id="6331e-108">We do not recommend that you use fiber mode scheduling for routine operation.</span></span> <span data-ttu-id="6331e-109">in quanto la modalità può ridurre le prestazioni eliminando i normali vantaggi del cambio del contesto e perché alcuni componenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che utilizzano TLS (Thread Local Storage) oppure oggetti di proprietà del thread, ad esempio mutex (un tipo di oggetto del kernel di Win32), non funzionano correttamente in modalità fiber.</span><span class="sxs-lookup"><span data-stu-id="6331e-109">This is because it can decrease performance by inhibiting the regular benefits of context switching, and because some components of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that use Thread Local Storage (TLS) or thread-owned objects, such as mutexes (a type of Win32 kernel object), cannot function correctly in fiber mode.</span></span>  
  
 <span data-ttu-id="6331e-110">Se si imposta l'opzione **lightweight pooling** su 1, in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene attivata la pianificazione in modalità fiber.</span><span class="sxs-lookup"><span data-stu-id="6331e-110">Setting **lightweight pooling** to 1 causes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to switch to fiber mode scheduling.</span></span> <span data-ttu-id="6331e-111">Il valore predefinito dell'opzione è 0.</span><span class="sxs-lookup"><span data-stu-id="6331e-111">The default value for this option is 0.</span></span>  
  
 <span data-ttu-id="6331e-112">L'opzione **lightweight pooling** è un'opzione avanzata.</span><span class="sxs-lookup"><span data-stu-id="6331e-112">The **lightweight pooling** option is an advanced option.</span></span> <span data-ttu-id="6331e-113">Se si utilizza la stored procedure di sistema **sp_configure** per modificare l'impostazione, è possibile modificare **lightweight pooling** solo quando il valore di **show advanced options** è impostato su 1.</span><span class="sxs-lookup"><span data-stu-id="6331e-113">If you are using the **sp_configure** system stored procedure to change the setting, you can change **lightweight pooling** only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="6331e-114">L'impostazione diventa effettiva dopo il riavvio del server.</span><span class="sxs-lookup"><span data-stu-id="6331e-114">The setting takes effect after the server is restarted.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6331e-115">Il lightweight pooling non è supportato per [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 2000 e [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows XP.</span><span class="sxs-lookup"><span data-stu-id="6331e-115">Lightweight pooling is not supported for [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 2000 and [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows XP.</span></span> [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] <span data-ttu-id="6331e-116">fornisce supporto completo per il lightweight pooling.</span><span class="sxs-lookup"><span data-stu-id="6331e-116">provides full support for lightweight pooling.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6331e-117">L'esecuzione di CLR (Common Language Runtime) non è supportata nell'ambito dell'opzione lightweight pooling.</span><span class="sxs-lookup"><span data-stu-id="6331e-117">Common language runtime (CLR) execution is not supported under lightweight pooling.</span></span> <span data-ttu-id="6331e-118">Disabilitare una delle due opzioni tra "clr enabled" e "lightweight pooling".</span><span class="sxs-lookup"><span data-stu-id="6331e-118">Disable one of two options: "clr enabled" or "lightweight pooling".</span></span> <span data-ttu-id="6331e-119">Le caratteristiche che si basano su CLR e che non funzionano correttamente in modalità fiber includono il tipo di dati hierarchy, la replica e la gestione basata su criteri.</span><span class="sxs-lookup"><span data-stu-id="6331e-119">Features that rely upon CLR and that do not work properly in fiber mode include the hierarchy data type, replication, and Policy-Based Management.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6331e-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6331e-120">See Also</span></span>  
 <span data-ttu-id="6331e-121">[Opzione di configurazione del server clr enabled](clr-enabled-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="6331e-121">[clr enabled Server Configuration Option](clr-enabled-server-configuration-option.md) </span></span>  
 <span data-ttu-id="6331e-122">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6331e-122">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="6331e-123">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6331e-123">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="6331e-124">Opzione di configurazione del server clr enabled</span><span class="sxs-lookup"><span data-stu-id="6331e-124">clr enabled Server Configuration Option</span></span>](clr-enabled-server-configuration-option.md)  
  
  
