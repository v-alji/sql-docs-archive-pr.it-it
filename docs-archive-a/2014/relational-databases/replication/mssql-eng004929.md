---
title: MSSQL_ENG004929 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG004929 error
ms.assetid: 1d9b1d88-1fbf-4089-b392-687d3b0220ca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b202b28eabe1feb1ed180bda0d58d2e84c7d10d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624072"
---
# <a name="mssql_eng004929"></a><span data-ttu-id="af543-102">MSSQL_ENG004929</span><span class="sxs-lookup"><span data-stu-id="af543-102">MSSQL_ENG004929</span></span>
    
## <a name="message-details"></a><span data-ttu-id="af543-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="af543-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="af543-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="af543-104">Product Name</span></span>|<span data-ttu-id="af543-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="af543-105">SQL Server</span></span>|  
|<span data-ttu-id="af543-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="af543-106">Event ID</span></span>|<span data-ttu-id="af543-107">4929</span><span class="sxs-lookup"><span data-stu-id="af543-107">4929</span></span>|  
|<span data-ttu-id="af543-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="af543-108">Event Source</span></span>|<span data-ttu-id="af543-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="af543-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="af543-110">Componente</span><span class="sxs-lookup"><span data-stu-id="af543-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="af543-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="af543-111">Symbolic Name</span></span>||  
|<span data-ttu-id="af543-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="af543-112">Message Text</span></span>|<span data-ttu-id="af543-113">Impossibile modificare %S_MSG '%.\*ls' perché è in corso di pubblicazione per la replica.</span><span class="sxs-lookup"><span data-stu-id="af543-113">Cannot alter the %S_MSG '%.\*ls' because it is being published for replication.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="af543-114">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="af543-114">Explanation</span></span>  
 <span data-ttu-id="af543-115">Questo errore si verifica in genere quando si tenta di eliminare il vincolo di chiave primaria di una tabella pubblicata per la replica transazionale.</span><span class="sxs-lookup"><span data-stu-id="af543-115">This error typically occurs if you attempt to drop the primary key constraint on a table that is published for transactional replication.</span></span> <span data-ttu-id="af543-116">Nella replica transazionale è necessaria una chiave primaria per ogni tabella pubblicata, pertanto il vincolo non può essere eliminato.</span><span class="sxs-lookup"><span data-stu-id="af543-116">Transactional replication requires a primary key for each published table; therefore the constraint cannot be dropped.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="af543-117">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="af543-117">User Action</span></span>  
 <span data-ttu-id="af543-118">Per eliminare il vincolo, eliminare innanzitutto l'articolo associato alla tabella.</span><span class="sxs-lookup"><span data-stu-id="af543-118">To drop the constraint, first drop the article associated with the table.</span></span> <span data-ttu-id="af543-119">Per altre informazioni, vedere [Aggiungere ed eliminare articoli in pubblicazioni esistenti](publish/add-articles-to-and-drop-articles-from-existing-publications.md).</span><span class="sxs-lookup"><span data-stu-id="af543-119">For more information, see [Add Articles to and Drop Articles from Existing Publications](publish/add-articles-to-and-drop-articles-from-existing-publications.md).</span></span> <span data-ttu-id="af543-120">Se questo errore si verifica in un database non replicato, eseguire [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) per verificare che gli oggetti nel database non siano contrassegnati come replicati.</span><span class="sxs-lookup"><span data-stu-id="af543-120">If this error occurs in a database that is not replicated, execute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to ensure objects in the database are not marked as replicated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af543-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af543-121">See Also</span></span>  
 [<span data-ttu-id="af543-122">Guida di riferimento a errori ed eventi &#40;replica&#41;</span><span class="sxs-lookup"><span data-stu-id="af543-122">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
