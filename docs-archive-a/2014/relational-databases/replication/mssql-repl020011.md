---
title: MSSQL_REPL020011 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_REPL020011 error
ms.assetid: f72072d7-bbb6-48ad-ac88-afa74aeb4d58
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 646f25740ebb007f8d04a89690d3b712781efcc8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721348"
---
# <a name="mssql_repl020011"></a><span data-ttu-id="06e8f-102">MSSQL_REPL020011</span><span class="sxs-lookup"><span data-stu-id="06e8f-102">MSSQL_REPL020011</span></span>
    
## <a name="message-details"></a><span data-ttu-id="06e8f-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="06e8f-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="06e8f-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="06e8f-104">Product Name</span></span>|<span data-ttu-id="06e8f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="06e8f-105">SQL Server</span></span>|  
|<span data-ttu-id="06e8f-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="06e8f-106">Event ID</span></span>|<span data-ttu-id="06e8f-107">20011</span><span class="sxs-lookup"><span data-stu-id="06e8f-107">20011</span></span>|  
|<span data-ttu-id="06e8f-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="06e8f-108">Event Source</span></span>|<span data-ttu-id="06e8f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="06e8f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="06e8f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="06e8f-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="06e8f-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="06e8f-111">Symbolic Name</span></span>||  
|<span data-ttu-id="06e8f-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="06e8f-112">Message Text</span></span>|<span data-ttu-id="06e8f-113">Impossibile eseguire '%1' in '%2'.</span><span class="sxs-lookup"><span data-stu-id="06e8f-113">The process could not execute '%1' on '%2'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="06e8f-114">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="06e8f-114">Explanation</span></span>  
 <span data-ttu-id="06e8f-115">Questo errore può essere generato in varie circostanze durante l'elaborazione di repliche transazionali, ad esempio quando l'agente di lettura log esegue **sp_replcmds** (Impossibile eseguire 'sp_replcmds' in \<ServerName>) o **sp_repldone** (Impossibile eseguire 'sp_repldone' in \<ServerName>).</span><span class="sxs-lookup"><span data-stu-id="06e8f-115">This error can be raised in a number of circumstances during transactional replication processing, such as when the Log Reader Agent executes **sp_replcmds** (The process could not execute 'sp_replcmds' on \<ServerName>) or **sp_repldone** (The process could not execute 'sp_repldone' on \<ServerName>).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="06e8f-116">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="06e8f-116">User Action</span></span>  
 <span data-ttu-id="06e8f-117">Se l'errore viene generato in un database che è appena stato ripristinato da un backup, verificare di aver eseguito i passaggi descritti nella documentazione relativa al backup e al ripristino e di aver eseguito **sp_replrestart** , se appropriato.</span><span class="sxs-lookup"><span data-stu-id="06e8f-117">If this error is raised in a database that you have just restored from a backup, ensure you have followed the steps outlined in the backup and restore documentation, including executing **sp_replrestart** if appropriate.</span></span> <span data-ttu-id="06e8f-118">Per altre informazioni, vedere [Strategie per il backup e il ripristino della replica snapshot e della replica transazionale](administration/strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="06e8f-118">For more information, see [Strategies for Backing Up and Restoring Snapshot and Transactional Replication](administration/strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md).</span></span>  
  
 <span data-ttu-id="06e8f-119">Si tratta di un errore di elaborazione interna. Se viene generato in circostanze diverse dal ripristino, in genere indica che è necessario rimuovere o riconfigurare la replica.</span><span class="sxs-lookup"><span data-stu-id="06e8f-119">This error is an internal processing error and if it is raised in circumstances other than a restore, it typically indicates that replication must be removed and reconfigured.</span></span> <span data-ttu-id="06e8f-120">Se non è possibile rimuovere la replica, rivolgersi al supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="06e8f-120">If you cannot remove replication, contact customer support for assistance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06e8f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06e8f-121">See Also</span></span>  
 <span data-ttu-id="06e8f-122">[Guida di riferimento a errori ed eventi &#40;replica&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="06e8f-122">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="06e8f-123">[sp_replcmds &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replcmds-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="06e8f-123">[sp_replcmds &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replcmds-transact-sql) </span></span>  
 [<span data-ttu-id="06e8f-124">sp_repldone &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="06e8f-124">sp_repldone &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-repldone-transact-sql)  
  
  
