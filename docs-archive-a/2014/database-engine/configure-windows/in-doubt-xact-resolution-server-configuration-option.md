---
title: Opzione di configurazione del server in-doubt xact resolution | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- distributed transactions [SQL Server], unresolved transactions
- unresolved transactions
- in-doubt xact resolution option
ms.assetid: 3426fd32-cad2-4f2f-8ca9-e0296cc12703
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6b8db57ef2a4ee85d65e8c25de28ff7ada7994e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713504"
---
# <a name="in-doubt-xact-resolution-server-configuration-option"></a><span data-ttu-id="cf50c-102">Opzione di configurazione del server in-doubt xact resolution</span><span class="sxs-lookup"><span data-stu-id="cf50c-102">in-doubt xact resolution Server Configuration Option</span></span>
  <span data-ttu-id="cf50c-103">L'opzione **in-doubt xact resolution** consente di controllare il risultato predefinito delle transazioni che non possono essere risolte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC).</span><span class="sxs-lookup"><span data-stu-id="cf50c-103">Use the **in-doubt xact resolution** option to control the default outcome of transactions that the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) is unable to resolve.</span></span> <span data-ttu-id="cf50c-104">L'impossibilità di risolvere le transazioni potrebbe essere dovuta al tempo di inattività di MS DTC oppure a un risultato sconosciuto della transazione al momento del recupero.</span><span class="sxs-lookup"><span data-stu-id="cf50c-104">Inability to resolve transactions may be related to the MS DTC down time or an unknown transaction outcome at the time of recovery.</span></span>  
  
 <span data-ttu-id="cf50c-105">Nella tabella seguente vengono descritti i possibili valori del risultato della risoluzione di una transazione in dubbio.</span><span class="sxs-lookup"><span data-stu-id="cf50c-105">The following table lists the possible outcome values for resolving an in-doubt transaction.</span></span>  
  
|<span data-ttu-id="cf50c-106">Valore risultato</span><span class="sxs-lookup"><span data-stu-id="cf50c-106">Outcome value</span></span>|<span data-ttu-id="cf50c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cf50c-107">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="cf50c-108">0</span><span class="sxs-lookup"><span data-stu-id="cf50c-108">0</span></span>|<span data-ttu-id="cf50c-109">No presumption (nessuna presupposizione).</span><span class="sxs-lookup"><span data-stu-id="cf50c-109">No presumption.</span></span> <span data-ttu-id="cf50c-110">L'operazione di recupero ha esito negativo se tramite MS DTC non è possibile risolvere alcuna transazione in dubbio.</span><span class="sxs-lookup"><span data-stu-id="cf50c-110">Recovery fails if MS DTC cannot resolve any in-doubt transactions.</span></span>|  
|<span data-ttu-id="cf50c-111">1</span><span class="sxs-lookup"><span data-stu-id="cf50c-111">1</span></span>|<span data-ttu-id="cf50c-112">Presume commit (presupposizione commit).</span><span class="sxs-lookup"><span data-stu-id="cf50c-112">Presume commit.</span></span> <span data-ttu-id="cf50c-113">Si presuppone il commit di qualsiasi transazione in dubbio MS DTC.</span><span class="sxs-lookup"><span data-stu-id="cf50c-113">Any MS DTC in-doubt transactions are presumed to have committed.</span></span>|  
|<span data-ttu-id="cf50c-114">2</span><span class="sxs-lookup"><span data-stu-id="cf50c-114">2</span></span>|<span data-ttu-id="cf50c-115">Presume abort (presupposizione interruzione).</span><span class="sxs-lookup"><span data-stu-id="cf50c-115">Presume abort.</span></span> <span data-ttu-id="cf50c-116">Si presuppone l'interruzione di qualsiasi transazione in dubbio MS DTC.</span><span class="sxs-lookup"><span data-stu-id="cf50c-116">Any MS DTC in-doubt transactions are presumed to have aborted.</span></span>|  
  
 <span data-ttu-id="cf50c-117">Per ridurre al minimo la possibilità di tempi di inattività prolungati, un amministratore può configurare questa opzione per presupporre il commit o l'interruzione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="cf50c-117">To minimize the possibility of extended down time, an administrator might choose to configure this option either to presume commit or presume abort, as shown in the following example.</span></span>  
  
```  
sp_configure 'show advanced options', 1  
GO  
RECONFIGURE  
GO  
sp_configure 'in-doubt xact resolution', 2 -- presume abort  
GO  
RECONFIGURE  
GO  
sp_configure 'show advanced options', 0  
GO  
RECONFIGURE  
GO  
  
```  
  
 <span data-ttu-id="cf50c-118">In alternativa, è possibile lasciare l'opzione predefinita, no presumption, e consentire il verificarsi dell'errore dell'operazione di recupero per essere a conoscenza di un errore DTC, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="cf50c-118">Alternatively, the administrator might want to leave the default (no presumption) and allow recovery to fail in order to be made aware of a DTC failure, as shown in the following example.</span></span>  
  
```  
sp_configure 'show advanced options', 1  
GO  
RECONFIGURE  
GO  
sp_configure 'in-doubt xact resolution', 1 -- presume commit  
GO  
reconfigure  
GO  
ALTER DATABASE pubs SET ONLINE -- run recovery again  
GO  
sp_configure 'in-doubt xact resolution', 0 -- back to no assumptions  
GO  
sp_configure 'show advanced options', 0  
GO  
RECONFIGURE  
GO  
  
```  
  
 <span data-ttu-id="cf50c-119">**in-doubt xact resolution** è un'opzione avanzata.</span><span class="sxs-lookup"><span data-stu-id="cf50c-119">The **in-doubt xact resolution** option is an advanced option.</span></span> <span data-ttu-id="cf50c-120">Se si usa la stored procedure di sistema **sp_configure** per modificare l'impostazione, è possibile modificare **in-doubt xact resolution** solo quando il valore di **show advanced options** è impostato su 1.</span><span class="sxs-lookup"><span data-stu-id="cf50c-120">If you are using the **sp_configure** system stored procedure to change the setting, you can change **in-doubt xact resolution** only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="cf50c-121">L'impostazione diventa effettiva immediatamente e non richiede il riavvio del server.</span><span class="sxs-lookup"><span data-stu-id="cf50c-121">The setting takes effect immediately without a server restart.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cf50c-122">Impostando questa opzione in modo coerente in tutte le istanze di [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] coinvolte in qualsiasi transazione distribuita, è possibile evitare inconsistenze dei dati.</span><span class="sxs-lookup"><span data-stu-id="cf50c-122">Consistent configuration of this option across all [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances involved in any distributed transactions will help avoid data inconsistencies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf50c-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf50c-123">See Also</span></span>  
 <span data-ttu-id="cf50c-124">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cf50c-124">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="cf50c-125">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cf50c-125">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="cf50c-126">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cf50c-126">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
