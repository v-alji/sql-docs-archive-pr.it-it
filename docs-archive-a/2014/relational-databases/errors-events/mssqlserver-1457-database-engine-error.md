---
title: MSSQLSERVER_1457 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1457 (Database Engine error)
ms.assetid: 28434ba1-b033-4866-ab41-111fccef45a2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c30ee6149c95d93bdaf1d2877f5fe1871a575ec1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636168"
---
# <a name="mssqlserver_1457"></a><span data-ttu-id="4590f-102">MSSQLSERVER_1457</span><span class="sxs-lookup"><span data-stu-id="4590f-102">MSSQLSERVER_1457</span></span>
    
## <a name="details"></a><span data-ttu-id="4590f-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="4590f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4590f-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="4590f-104">Product Name</span></span>|<span data-ttu-id="4590f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4590f-105">SQL Server</span></span>|  
|<span data-ttu-id="4590f-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="4590f-106">Event ID</span></span>|<span data-ttu-id="4590f-107">1457</span><span class="sxs-lookup"><span data-stu-id="4590f-107">1457</span></span>|  
|<span data-ttu-id="4590f-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="4590f-108">Event Source</span></span>|<span data-ttu-id="4590f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4590f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4590f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="4590f-110">Component</span></span>|<span data-ttu-id="4590f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4590f-111">SQLEngine</span></span>|  
|<span data-ttu-id="4590f-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="4590f-112">Symbolic Name</span></span>|<span data-ttu-id="4590f-113">DBM_PAGE_UNDO_PENDING</span><span class="sxs-lookup"><span data-stu-id="4590f-113">DBM_PAGE_UNDO_PENDING</span></span>|  
|<span data-ttu-id="4590f-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="4590f-114">Message Text</span></span>|<span data-ttu-id="4590f-115">La sincronizzazione del database mirror '%.\*ls' è stata interrotta, lasciando il database in uno stato inconsistente.</span><span class="sxs-lookup"><span data-stu-id="4590f-115">Synchronization of the mirror database, '%.\*ls', was interrupted, leaving the database in an inconsistent state.</span></span> <span data-ttu-id="4590f-116">Comando ALTER DATABASE non riuscito.</span><span class="sxs-lookup"><span data-stu-id="4590f-116">The ALTER DATABASE command failed.</span></span> <span data-ttu-id="4590f-117">Verificare che il database mirror sia nuovamente attivo e online, quindi riconnettere l'istanza del server mirror e consentire al database mirror di completare la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="4590f-117">Ensure that the mirror database is back up and online, and then reconnect the mirror server instance and allow the mirror database to finish synchronizing.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4590f-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="4590f-118">Explanation</span></span>  
 <span data-ttu-id="4590f-119">Questo messaggio indica che l'istruzione ALTER DATABASE *nome_database* SET PARTNER OFF non è stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="4590f-119">This messages indicates that the ALTER DATABASE *database_name* SET PARTNER OFF statement has failed.</span></span> <span data-ttu-id="4590f-120">Il tentativo non riuscito di rimuovere il mirroring del database ha interrotto la sincronizzazione del database mirror.</span><span class="sxs-lookup"><span data-stu-id="4590f-120">The failed attempt to remove database mirroring interrupted synchronization of the mirror database.</span></span> <span data-ttu-id="4590f-121">Il database si trova in uno stato inconsistente.</span><span class="sxs-lookup"><span data-stu-id="4590f-121">The database is in an inconsistent state.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4590f-122">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="4590f-122">User Action</span></span>  
 <span data-ttu-id="4590f-123">Per risolvere il problema, è possibile eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4590f-123">To resolve this error, you can take either of the following actions:</span></span>  
  
-   <span data-ttu-id="4590f-124">Ripristinare il contatto tra il server mirror e il server principale per consentire la sincronizzazione del database mirror.</span><span class="sxs-lookup"><span data-stu-id="4590f-124">Restore contact between the mirror server and the principal server to allow for the mirror database to synchronize.</span></span>  
  
-   <span data-ttu-id="4590f-125">Eliminare il database mirror.</span><span class="sxs-lookup"><span data-stu-id="4590f-125">Drop the mirror database.</span></span>  
  
     <span data-ttu-id="4590f-126">Dopo aver eliminato il database mirror, sarà possibile crearne uno nuovo dai backup.</span><span class="sxs-lookup"><span data-stu-id="4590f-126">After you drop the mirror database, you can create a new mirror database from backups.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4590f-127">È possibile eliminare il database mirror quando il mirroring è ancora abilitato solo dopo un'istruzione SET PARTNER OFF non riuscita.</span><span class="sxs-lookup"><span data-stu-id="4590f-127">You can drop the mirror database when mirroring is still enabled only after a failed SET PARTNER OFF statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4590f-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4590f-128">See Also</span></span>  
 <span data-ttu-id="4590f-129">[Mirroring del database &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4590f-129">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="4590f-130">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4590f-130">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="4590f-131">[Impostazione del mirroring del database &#40;SQL Server&#41;](../../database-engine/database-mirroring/setting-up-database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4590f-131">[Setting Up Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/setting-up-database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="4590f-132">[Rimozione del mirroring del database &#40;SQL Server&#41;](../../database-engine/database-mirroring/removing-database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4590f-132">[Removing Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/removing-database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="4590f-133">Preparazione di un database mirror per il mirroring &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4590f-133">Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md)  
  
  
