---
title: MSSQL_ENG021286 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021286 error
ms.assetid: b63620b7-1c6d-46f7-90ea-3a8e99af8de4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 592c788b563046e5949217c94006de2d4755f049
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714180"
---
# <a name="mssql_eng021286"></a><span data-ttu-id="77b0c-102">MSSQL_ENG021286</span><span class="sxs-lookup"><span data-stu-id="77b0c-102">MSSQL_ENG021286</span></span>
    
## <a name="message-details"></a><span data-ttu-id="77b0c-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="77b0c-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="77b0c-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="77b0c-104">Product Name</span></span>|<span data-ttu-id="77b0c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="77b0c-105">SQL Server</span></span>|  
|<span data-ttu-id="77b0c-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="77b0c-106">Event ID</span></span>|<span data-ttu-id="77b0c-107">21286</span><span class="sxs-lookup"><span data-stu-id="77b0c-107">21286</span></span>|  
|<span data-ttu-id="77b0c-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="77b0c-108">Event Source</span></span>|<span data-ttu-id="77b0c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="77b0c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="77b0c-110">Componente</span><span class="sxs-lookup"><span data-stu-id="77b0c-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="77b0c-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="77b0c-111">Symbolic Name</span></span>||  
|<span data-ttu-id="77b0c-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="77b0c-112">Message Text</span></span>|<span data-ttu-id="77b0c-113">La tabella dei conflitti '%s' non esiste.</span><span class="sxs-lookup"><span data-stu-id="77b0c-113">Conflict table '%s' does not exist.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="77b0c-114">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="77b0c-114">Explanation</span></span>  
 <span data-ttu-id="77b0c-115">Questo errore si verifica se la tabella dei conflitti relativa a un articolo elencato in [sysmergearticles &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/sysmergearticles-transact-sql) in realtà non esiste.</span><span class="sxs-lookup"><span data-stu-id="77b0c-115">This error is raised if the conflict table for an article listed in [sysmergearticles &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/sysmergearticles-transact-sql) does not actually exist.</span></span> <span data-ttu-id="77b0c-116">Questo errore può verificarsi quando si tenta di aggiungere o di eliminare una colonna da una tabella pubblicata per la replica di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="77b0c-116">The error can occur when you attempt to add a column to or drop a column from a table published for merge replication.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="77b0c-117">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="77b0c-117">User Action</span></span>  
 <span data-ttu-id="77b0c-118">Eseguire [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) sul database con la tabella dei conflitti mancante per verificare che non siano presenti problemi di coerenza dei dati.</span><span class="sxs-lookup"><span data-stu-id="77b0c-118">Execute [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database with the missing conflict table to verify there are no data consistency issues.</span></span>  
  
 <span data-ttu-id="77b0c-119">Se in un Sottoscrittore manca la tabella dei conflitti, eliminare la sottoscrizione e ricrearla.</span><span class="sxs-lookup"><span data-stu-id="77b0c-119">If the conflict table is missing on a Subscriber, drop the subscription and recreate it.</span></span> <span data-ttu-id="77b0c-120">Se in un server di pubblicazione manca la tabella dei conflitti, eliminare tutte le sottoscrizioni, eliminare la pubblicazione e quindi ricreare la pubblicazione e tutte le sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="77b0c-120">If the conflict table is missing on a Publisher, drop all subscriptions, drop the publication, and then recreate the publication and all subscriptions.</span></span> <span data-ttu-id="77b0c-121">Per altre informazioni, vedere [Pubblicare dati e oggetti di database](publish/publish-data-and-database-objects.md) e [Sottoscrivere le pubblicazioni](subscribe-to-publications.md).</span><span class="sxs-lookup"><span data-stu-id="77b0c-121">For more information, see [Publish Data and Database Objects](publish/publish-data-and-database-objects.md) and [Subscribe to Publications](subscribe-to-publications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77b0c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77b0c-122">See Also</span></span>  
 [<span data-ttu-id="77b0c-123">Guida di riferimento a errori ed eventi &#40;replica&#41;</span><span class="sxs-lookup"><span data-stu-id="77b0c-123">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
