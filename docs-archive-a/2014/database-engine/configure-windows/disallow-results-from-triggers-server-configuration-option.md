---
title: Opzione di configurazione del server disallow results from triggers | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- triggers [SQL Server], result sets
- result sets [SQL Server], triggers
- disallow results from triggers option
ms.assetid: 47149073-307d-47a5-b7d2-66a737d3231d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f162a6e06706561d861bfc54a1ae4027f2c3466e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711027"
---
# <a name="disallow-results-from-triggers-server-configuration-option"></a><span data-ttu-id="22a8b-102">Impostazione di configurazione del server disallow results from triggers</span><span class="sxs-lookup"><span data-stu-id="22a8b-102">disallow results from triggers Server Configuration Option</span></span>
  <span data-ttu-id="22a8b-103">L'opzione **Disallow Results From Triggers** consente di specificare se i trigger debbano o meno restituire set di risultati.</span><span class="sxs-lookup"><span data-stu-id="22a8b-103">Use the **disallow results from triggers** option to control whether triggers return result sets.</span></span> <span data-ttu-id="22a8b-104">I trigger che restituiscono set di risultati possono provocare comportamenti imprevisti nelle applicazioni che non sono state progettate per il loro utilizzo.</span><span class="sxs-lookup"><span data-stu-id="22a8b-104">Triggers that return result sets may cause unexpected behavior in applications that are not designed to work with them.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextDontUse](../../includes/ssnotedepnextdontuse-md.md)] <span data-ttu-id="22a8b-105">È consigliabile impostare questo valore su 1.</span><span class="sxs-lookup"><span data-stu-id="22a8b-105">We recommend that you set this value to 1.</span></span>  
  
 <span data-ttu-id="22a8b-106">Se il valore è 1, l'opzione **Disallow Results From Triggers** è impostata su ON.</span><span class="sxs-lookup"><span data-stu-id="22a8b-106">When set to 1, the **disallow results from triggers** option is set to ON.</span></span> <span data-ttu-id="22a8b-107">L'impostazione predefinita per questa opzione è 0 (OFF).</span><span class="sxs-lookup"><span data-stu-id="22a8b-107">The default setting for this option is 0 (OFF).</span></span> <span data-ttu-id="22a8b-108">Se l'opzione è impostata su 1 (ON), qualsiasi tentativo da parte di un trigger di restituire un set di risultati ha esito negativo e l'utente riceve il messaggio di errore seguente:</span><span class="sxs-lookup"><span data-stu-id="22a8b-108">If this option is set to 1 (ON), any attempt by a trigger to return a result set fails, and the user receives the following error message:</span></span>  
  
 <span data-ttu-id="22a8b-109">"Msg 524, Livello 16, Stato 1, Procedura \<Procedure Name>, Riga \<Line#></span><span class="sxs-lookup"><span data-stu-id="22a8b-109">"Msg 524, Level 16, State 1, Procedure \<Procedure Name>, Line \<Line#></span></span>  
  
 <span data-ttu-id="22a8b-110">"Un trigger ha restituito un set di risultati e l'opzione del server 'disallow_results_from_triggers' è impostata su true".</span><span class="sxs-lookup"><span data-stu-id="22a8b-110">"A trigger returned a resultset and the server option 'disallow_results_from_triggers' is true."</span></span>  
  
 <span data-ttu-id="22a8b-111">L'opzione **disallow results from triggers** viene applicata a livello di istanza di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e determina il comportamento di tutti i trigger esistenti nell'istanza.</span><span class="sxs-lookup"><span data-stu-id="22a8b-111">The **disallow results from triggers** option is applied at the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance level, and it will determine behavior for all existing triggers within the instance.</span></span>  
  
 <span data-ttu-id="22a8b-112">**Disallow Results From Triggers** è un'opzione avanzata.</span><span class="sxs-lookup"><span data-stu-id="22a8b-112">The **disallow results from triggers** option is an advanced option.</span></span> <span data-ttu-id="22a8b-113">Se per modificare l'impostazione si usa la stored procedure di sistema **sp_configure** , sarà possibile modificare Disallow Results From Triggers solo quando il valore di **Show Advanced Options** è impostato su 1.</span><span class="sxs-lookup"><span data-stu-id="22a8b-113">If you are using the **sp_configure** system stored procedure to change the setting, you can change disallow results from triggers only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="22a8b-114">L'impostazione diventa effettiva immediatamente e non richiede il riavvio del server.</span><span class="sxs-lookup"><span data-stu-id="22a8b-114">The setting takes effect immediately without a server restart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22a8b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22a8b-115">See Also</span></span>  
 <span data-ttu-id="22a8b-116">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="22a8b-116">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="22a8b-117">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="22a8b-117">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="22a8b-118">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="22a8b-118">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
