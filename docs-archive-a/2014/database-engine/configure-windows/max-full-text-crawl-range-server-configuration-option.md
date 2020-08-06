---
title: Opzione di configurazione del server max full-text crawl range | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- crawls [full-text search]
- max full-text crawl range option
ms.assetid: a49de86b-0891-4dcd-89c0-ead30aab00e0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e1dbd9e44518b6e849a06a76e21fc605172fd2ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712368"
---
# <a name="max-full-text-crawl-range-server-configuration-option"></a><span data-ttu-id="24c1f-102">Opzione di configurazione del server max full-text crawl range</span><span class="sxs-lookup"><span data-stu-id="24c1f-102">max full-text crawl range Server Configuration Option</span></span>
  <span data-ttu-id="24c1f-103">L'opzione **max full-text crawl range** consente di ottimizzare l'utilizzo della CPU, migliorando quindi le prestazioni della ricerca per indicizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="24c1f-103">Use the **max full-text crawl range** option to optimize CPU utilization, which improves crawl performance during a full crawl.</span></span> <span data-ttu-id="24c1f-104">L'opzione consente di specificare il numero di partizioni usate da [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] durante una ricerca per indicizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="24c1f-104">Using this option, you can specify the number of partitions that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should use during a full index crawl.</span></span> <span data-ttu-id="24c1f-105">Se, ad esempio, sono presenti più CPU il cui utilizzo non è ottimizzato, è possibile aumentare il valore massimo dell'opzione.</span><span class="sxs-lookup"><span data-stu-id="24c1f-105">For example, if there are many CPUs and their utilization is not optimal, you can increase the maximum value of this option.</span></span> <span data-ttu-id="24c1f-106">Oltre a questa opzione, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizza diversi altri elementi, ad esempio il numero di righe nella tabella e il numero di CPU, per determinare il numero effettivo di partizioni utilizzate.</span><span class="sxs-lookup"><span data-stu-id="24c1f-106">In addition to this option, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses a number of other factors, such as the number of rows in the table and the number of CPUs, to determine the actual number of partitions used.</span></span>  
  
 <span data-ttu-id="24c1f-107">Il valore predefinito per questa opzione è 4, il valore minimo è 1 e il valore massimo è 256.</span><span class="sxs-lookup"><span data-stu-id="24c1f-107">The default value of this option is 4; the minimum value is 1, and the maximum value is 256.</span></span> <span data-ttu-id="24c1f-108">Le modifiche apportate a questa opzione influiscono solo sulle ricerche per indicizzazione successive.</span><span class="sxs-lookup"><span data-stu-id="24c1f-108">Changes made to this option affect only subsequent crawls.</span></span> <span data-ttu-id="24c1f-109">Le ricerche per indicizzazione in corso non sono interessate da una modifica apportata all'impostazione dell'opzione.</span><span class="sxs-lookup"><span data-stu-id="24c1f-109">Crawls in process will not be affected by a change in this option setting.</span></span>  
  
 <span data-ttu-id="24c1f-110">L'opzione **max full-text crawl range** è un'opzione avanzata.</span><span class="sxs-lookup"><span data-stu-id="24c1f-110">The **max full-text crawl range** option is an advanced option.</span></span> <span data-ttu-id="24c1f-111">Se si usa la stored procedure di sistema **sp_configure** per modificare l'impostazione, è possibile modificare **max full-text crawl range** solo quando il valore di **show advanced options** è impostato su 1.</span><span class="sxs-lookup"><span data-stu-id="24c1f-111">If you are using the **sp_configure** system stored procedure to change the setting, you can change **max full-text crawl range** only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="24c1f-112">L'impostazione diventa effettiva immediatamente e non richiede il riavvio del server.</span><span class="sxs-lookup"><span data-stu-id="24c1f-112">The setting takes effect immediately without a server restart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24c1f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24c1f-113">See Also</span></span>  
 <span data-ttu-id="24c1f-114">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="24c1f-114">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="24c1f-115">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="24c1f-115">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="24c1f-116">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="24c1f-116">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
