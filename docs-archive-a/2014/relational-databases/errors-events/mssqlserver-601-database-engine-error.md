---
title: MSSQLSERVER_601 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "601"
helpviewer_keywords:
- 601 (Database Engine error)
ms.assetid: 2039cc0a-9a43-4369-a04a-935e384388b6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 459a983d72a91e628e8cc33636d3abd81998f1d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637364"
---
# <a name="mssqlserver_601"></a><span data-ttu-id="8584a-102">MSSQLSERVER_601</span><span class="sxs-lookup"><span data-stu-id="8584a-102">MSSQLSERVER_601</span></span>
    
## <a name="details"></a><span data-ttu-id="8584a-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="8584a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8584a-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="8584a-104">Product Name</span></span>|<span data-ttu-id="8584a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8584a-105">SQL Server</span></span>|  
|<span data-ttu-id="8584a-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="8584a-106">Event ID</span></span>|<span data-ttu-id="8584a-107">601</span><span class="sxs-lookup"><span data-stu-id="8584a-107">601</span></span>|  
|<span data-ttu-id="8584a-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="8584a-108">Event Source</span></span>|<span data-ttu-id="8584a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8584a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8584a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="8584a-110">Component</span></span>|<span data-ttu-id="8584a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8584a-111">SQLEngine</span></span>|  
|<span data-ttu-id="8584a-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="8584a-112">Symbolic Name</span></span>||  
|<span data-ttu-id="8584a-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="8584a-113">Message Text</span></span>|<span data-ttu-id="8584a-114">A causa di uno spostamento di dati, non è possibile continuare l'analisi tramite NOLOCK.</span><span class="sxs-lookup"><span data-stu-id="8584a-114">Could not continue scan with NOLOCK due to data movement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8584a-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="8584a-115">Explanation</span></span>  
 <span data-ttu-id="8584a-116">Il [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] non è in grado di continuare l'esecuzione della query perché sta tentando di leggere dati che sono stati aggiornati o eliminati da un'altra transazione.</span><span class="sxs-lookup"><span data-stu-id="8584a-116">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] cannot continue executing the query because it is trying to read data that was updated or deleted by another transaction.</span></span> <span data-ttu-id="8584a-117">La query sta utilizzando l'hint di blocco NOLOCK o il livello di isolamento della transazione READ UNCOMMITTED.</span><span class="sxs-lookup"><span data-stu-id="8584a-117">The query is using either the NOLOCK locking hint or the READ UNCOMMITTED transaction isolation level.</span></span>  
  
 <span data-ttu-id="8584a-118">L'accesso a dati in corso di modifica da parte di un'altra transazione viene in genere negato perché i dati risultano bloccati.</span><span class="sxs-lookup"><span data-stu-id="8584a-118">Typically, access to data that is being changed by another transaction is denied because of locks put on the data.</span></span> <span data-ttu-id="8584a-119">L'hint di blocco NOLOCK e il livello di isolamento della transazione READ UNCOMMITTED consentono tuttavia a una query di leggere dati bloccati da un'altra transazione.</span><span class="sxs-lookup"><span data-stu-id="8584a-119">However, the NOLOCK locking hint and READ UNCOMMITTED transaction isolation level let a query read data that is locked by another transaction.</span></span> <span data-ttu-id="8584a-120">Tale lettura è definita lettura dirty perché consente la lettura di valori di cui non è ancora stato eseguito il commit e che sono soggetti a modifica.</span><span class="sxs-lookup"><span data-stu-id="8584a-120">This is referred to as a dirty read because you can read values that have not yet been committed and that are subject to change.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8584a-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="8584a-121">User Action</span></span>  
 <span data-ttu-id="8584a-122">L'errore annulla la query.</span><span class="sxs-lookup"><span data-stu-id="8584a-122">This error cancels the query.</span></span> <span data-ttu-id="8584a-123">Eseguire nuovamente la query o rimuovere l'hint di blocco NOLOCK.</span><span class="sxs-lookup"><span data-stu-id="8584a-123">Either resubmit the query or remove the NOLOCK locking hint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8584a-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8584a-124">See Also</span></span>  
 <span data-ttu-id="8584a-125">[MSSQLSERVER_605](mssqlserver-605-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="8584a-125">[MSSQLSERVER_605](mssqlserver-605-database-engine-error.md) </span></span>  
 <span data-ttu-id="8584a-126">[Hint di tabella &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table) </span><span class="sxs-lookup"><span data-stu-id="8584a-126">[Table Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table) </span></span>  
 <span data-ttu-id="8584a-127">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8584a-127">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="8584a-128">SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8584a-128">SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql)  
  
  
