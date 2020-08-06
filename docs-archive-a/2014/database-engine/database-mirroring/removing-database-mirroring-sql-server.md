---
title: Rimozione di mirroring del database (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], removing
- stopping database mirroring [SQL Server]
- removing database mirroring [SQL Server]
ms.assetid: 40c72091-8f03-4037-8b55-5e95309fe145
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8044fcef9d9f9bfc1fb41c1faa17b76c827da5a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716751"
---
# <a name="removing-database-mirroring-sql-server"></a><span data-ttu-id="0e6f1-102">Rimozione di mirroring del database (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0e6f1-102">Removing Database Mirroring (SQL Server)</span></span>
  <span data-ttu-id="0e6f1-103">Il proprietario del database può arrestare manualmente una sessione di mirroring del database in qualsiasi momento in uno dei partner.</span><span class="sxs-lookup"><span data-stu-id="0e6f1-103">The database owner can manually stop a database mirroring session at any time, at either partner.</span></span>  
  
## <a name="impact-of-removing-mirroring"></a><span data-ttu-id="0e6f1-104">Impatto della rimozione del mirroring</span><span class="sxs-lookup"><span data-stu-id="0e6f1-104">Impact of Removing Mirroring</span></span>  
 <span data-ttu-id="0e6f1-105">Quando il mirroring viene rimosso, si verificano le situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0e6f1-105">When mirroring is removed, the following occurs:</span></span>  
  
-   <span data-ttu-id="0e6f1-106">La relazione, se presente, tra i partner e tra ogni partner e il server di controllo del mirroring viene interrotta in modo permanente.</span><span class="sxs-lookup"><span data-stu-id="0e6f1-106">The relationship between the partners and between each partner and the witness breaks permanently, if any relationship exists.</span></span>  
  
     <span data-ttu-id="0e6f1-107">Se al momento dell'interruzione della sessione è in corso la comunicazione tra i partner, la relazione viene immediatamente arrestata in entrambi i computer.</span><span class="sxs-lookup"><span data-stu-id="0e6f1-107">If the partners are communicating with each other when the session is stopped, their relationship is immediately broken on both computers.</span></span> <span data-ttu-id="0e6f1-108">Se i partner non stanno comunicando, ovvero il database è in stato DISCONNECTED al momento dell'arresto, la relazione viene immediatamente interrotta nel partner in cui è stato arrestato il mirroring. Quando l'altro partner tenta di riconnettersi, individua che la sessione di mirroring del database è stata terminata.</span><span class="sxs-lookup"><span data-stu-id="0e6f1-108">If the partners are not communicating (the database is in a DISCONNECTED state at the time of stopping), the relationship is broken immediately on the partner from which mirroring is stopped; when the other partner tries to reconnect, it discovers that the database mirroring session has ended.</span></span>  
  
-   <span data-ttu-id="0e6f1-109">Le informazioni sulla sessione di mirroring vengono eliminate, diversamente da ciò che si verifica nel caso di sospensione di una sessione.</span><span class="sxs-lookup"><span data-stu-id="0e6f1-109">Information about the mirroring session is dropped, unlike when pausing a session.</span></span> <span data-ttu-id="0e6f1-110">Il mirroring viene rimosso sia nel database principale, sia nel database mirror.</span><span class="sxs-lookup"><span data-stu-id="0e6f1-110">Mirroring is removed on both the principal database and the mirror database.</span></span> <span data-ttu-id="0e6f1-111">In **sys.databases** la colonna **mirroring_state** e tutte le altre colonne di mirroring vengono impostate su NULL.</span><span class="sxs-lookup"><span data-stu-id="0e6f1-111">In **sys.databases**, the **mirroring_state** column and all other mirroring columns are set to NULL.</span></span> <span data-ttu-id="0e6f1-112">Per altre informazioni, vedere [sys.database_mirroring &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0e6f1-112">For more information, see [sys.database_mirroring &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql).</span></span>  
  
-   <span data-ttu-id="0e6f1-113">Viene mantenuta ogni istanza del server partner con una copia distinta del database.</span><span class="sxs-lookup"><span data-stu-id="0e6f1-113">Each partner server instance is left with a separate copy of the database.</span></span>  
  
-   <span data-ttu-id="0e6f1-114">Il database mirror viene lasciato nello stato RESTORING (vedere la colonna **state** di **sys.databases**), poiché è stato creato tramite RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="0e6f1-114">The mirror database is left in the RESTORING state (see the **state** column of **sys.databases**), because the mirror database was created by using RESTORE WITH NORECOVERY.</span></span> <span data-ttu-id="0e6f1-115">A questo punto, è possibile eliminare il database mirror precedente o recuperarlo tramite WITH RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="0e6f1-115">At this point, you can drop the former mirror database or restore it using WITH RECOVERY.</span></span> <span data-ttu-id="0e6f1-116">Il database recuperato presenterà alcune divergenze rispetto al database principale precedente, in quanto tramite il recupero viene avviato un nuovo fork di recupero.</span><span class="sxs-lookup"><span data-stu-id="0e6f1-116">When you recover the database, it will have diverged from the former principal database because the recovery starts a new recovery fork.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0e6f1-117">Per proseguire il mirroring dopo avere arrestato una sessione, è necessario stabilire una nuova sessione di mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="0e6f1-117">To continue mirroring after stopping a session, you must establish a new database mirroring session.</span></span> <span data-ttu-id="0e6f1-118">Se dopo l'arresto del mirroring è stato creato un backup del log, è necessario applicarlo al database mirror prima di riavviare il mirroring.</span><span class="sxs-lookup"><span data-stu-id="0e6f1-118">If you create a log backup after stopping mirroring, you must apply it to the mirror database before restarting mirroring.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="0e6f1-119">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="0e6f1-119">Related Tasks</span></span>  
 <span data-ttu-id="0e6f1-120">**Per rimuovere il mirroring del database**</span><span class="sxs-lookup"><span data-stu-id="0e6f1-120">**To remove database mirroring**</span></span>  
  
-   [<span data-ttu-id="0e6f1-121">Rimuovere il mirroring del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0e6f1-121">Remove Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
 <span data-ttu-id="0e6f1-122">**Per avviare il mirroring del database**</span><span class="sxs-lookup"><span data-stu-id="0e6f1-122">**To start database mirroring**</span></span>  
  
-   [<span data-ttu-id="0e6f1-123">Stabilire una sessione di mirroring del database tramite autenticazione di Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0e6f1-123">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="0e6f1-124">Stabilire una sessione di mirroring del database tramite autenticazione di Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0e6f1-124">Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](database-mirroring-establish-session-windows-authentication.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="0e6f1-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e6f1-125">See Also</span></span>  
 <span data-ttu-id="0e6f1-126">[Mirroring del database di ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="0e6f1-126">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="0e6f1-127">[Mirroring del database &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0e6f1-127">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="0e6f1-128">[Sospensione e ripresa del mirroring del database &#40;SQL Server&#41;](pausing-and-resuming-database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0e6f1-128">[Pausing and Resuming Database Mirroring &#40;SQL Server&#41;](pausing-and-resuming-database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="0e6f1-129">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0e6f1-129">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
