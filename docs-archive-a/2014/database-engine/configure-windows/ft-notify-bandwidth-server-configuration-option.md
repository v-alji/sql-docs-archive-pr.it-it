---
title: Opzione di configurazione del server ft notify bandwidth | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- ft notify bandwidth opion
- small memory buffers
- memory [SQL Server], buffers
ms.assetid: 9ca284c5-f3e0-4a67-a132-fff376ff0ffe
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: dc5839f699d55edf86c5e3e3f0eb001089a0a5dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723067"
---
# <a name="ft-notify-bandwidth-server-configuration-option"></a><span data-ttu-id="9ed35-102">Opzione di configurazione del server ft notify bandwidth</span><span class="sxs-lookup"><span data-stu-id="9ed35-102">ft notify bandwidth Server Configuration Option</span></span>
  <span data-ttu-id="9ed35-103">L'opzione **ft notify bandwidth** consente di specificare la dimensione massima consentita per il pool di buffer di memoria di piccole dimensioni,</span><span class="sxs-lookup"><span data-stu-id="9ed35-103">Use the **ft notify bandwidth** option to specify the size to which the pool of small memory buffers can grow.</span></span> <span data-ttu-id="9ed35-104">ovvero dei buffer di memoria di 64 KB.</span><span class="sxs-lookup"><span data-stu-id="9ed35-104">Small memory buffers are 64 kilobytes (KB) in size.</span></span> <span data-ttu-id="9ed35-105">Il valore del parametro *max* specifica il numero massimo di buffer che deve essere gestito in un pool di buffer di piccole dimensioni con lo strumento di gestione della memoria del servizio full-text.</span><span class="sxs-lookup"><span data-stu-id="9ed35-105">The *max* parameter value specifies the maximum number of buffers that the full-text memory manager should maintain in a small buffer pool.</span></span> <span data-ttu-id="9ed35-106">Se il `max` valore è zero, non esiste alcun limite massimo per il numero di buffer che possono trovarsi in un pool di buffer di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="9ed35-106">If the `max` value is zero, then there is no upper limit to the number of buffers that can be in a small buffer pool.</span></span>  
  
 <span data-ttu-id="9ed35-107">Il parametro **min** specifica il numero minimo di buffer di memoria che deve essere gestito nel pool di buffer di memoria di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="9ed35-107">The **min** parameter specifies the minimum number of memory buffers that must be maintained in the pool of small memory buffers.</span></span> <span data-ttu-id="9ed35-108">In seguito alla richiesta dello strumento di gestione della memoria di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], tutti i pool di buffer in eccesso vengono rilasciati, ma viene mantenuto il numero minimo di buffer.</span><span class="sxs-lookup"><span data-stu-id="9ed35-108">Upon request from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory manager, all extra buffer pools will be released but this minimum number of buffers will be maintained.</span></span> <span data-ttu-id="9ed35-109">Tuttavia, se il valore **min** è uguale a zero, vengono rilasciati tutti i buffer di memoria.</span><span class="sxs-lookup"><span data-stu-id="9ed35-109">If, however, the **min** value specified is zero, then all memory buffers are released.</span></span>  
  
 <span data-ttu-id="9ed35-110">In determinati casi il numero di buffer allocati risulta inferiore al valore specificato nel parametro **min** .</span><span class="sxs-lookup"><span data-stu-id="9ed35-110">Under certain circumstances the number of buffers currently allocated is less than the value specified by the **min** parameter.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9ed35-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ed35-111">See Also</span></span>  
 <span data-ttu-id="9ed35-112">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9ed35-112">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="9ed35-113">[Opzione di configurazione del server ft crawl bandwidth](ft-crawl-bandwidth-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="9ed35-113">[ft crawl bandwidth Server Configuration Option](ft-crawl-bandwidth-server-configuration-option.md) </span></span>  
 [<span data-ttu-id="9ed35-114">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9ed35-114">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
