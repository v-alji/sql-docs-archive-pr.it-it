---
title: MSSQLSERVER_3176 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3176 (Database Engine error)
ms.assetid: 4be24c64-2d52-4cb4-b4d7-36efbe4555b6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 64e1a836995fe8738bb5c2ff0cb4de10d84d1f29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628726"
---
# <a name="mssqlserver_3176"></a><span data-ttu-id="05e8d-102">MSSQLSERVER_3176</span><span class="sxs-lookup"><span data-stu-id="05e8d-102">MSSQLSERVER_3176</span></span>
    
## <a name="details"></a><span data-ttu-id="05e8d-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="05e8d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="05e8d-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="05e8d-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="05e8d-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="05e8d-105">Event ID</span></span>|<span data-ttu-id="05e8d-106">3176</span><span class="sxs-lookup"><span data-stu-id="05e8d-106">3176</span></span>|  
|<span data-ttu-id="05e8d-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="05e8d-107">Event Source</span></span>|<span data-ttu-id="05e8d-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="05e8d-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="05e8d-109">Componente</span><span class="sxs-lookup"><span data-stu-id="05e8d-109">Component</span></span>|<span data-ttu-id="05e8d-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="05e8d-110">SQLEngine</span></span>|  
|<span data-ttu-id="05e8d-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="05e8d-111">Symbolic Name</span></span>|<span data-ttu-id="05e8d-112">LDDB_FILE_CLAIM</span><span class="sxs-lookup"><span data-stu-id="05e8d-112">LDDB_FILE_CLAIM</span></span>|  
|<span data-ttu-id="05e8d-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="05e8d-113">Message Text</span></span>|<span data-ttu-id="05e8d-114">Il file '%ls' è richiesto da '%ls'(%d) e '%ls'(%d).</span><span class="sxs-lookup"><span data-stu-id="05e8d-114">File '%ls' is claimed by '%ls'(%d) and '%ls'(%d).</span></span> <span data-ttu-id="05e8d-115">Per rilocare uno o più file è possibile utilizzare la clausola WITH MOVE.</span><span class="sxs-lookup"><span data-stu-id="05e8d-115">The WITH MOVE clause can be used to relocate one or more files.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="05e8d-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="05e8d-116">Explanation</span></span>  
 <span data-ttu-id="05e8d-117">Viene tentato l'utilizzo di un file per più scopi.</span><span class="sxs-lookup"><span data-stu-id="05e8d-117">Attempting to use a file for more than one purpose.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="05e8d-118">Possibili cause</span><span class="sxs-lookup"><span data-stu-id="05e8d-118">Possible Causes</span></span>  
 <span data-ttu-id="05e8d-119">Il nome file viene già utilizzato da un altro database.</span><span class="sxs-lookup"><span data-stu-id="05e8d-119">Another database is already using the file name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="05e8d-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="05e8d-120">User Action</span></span>  
 <span data-ttu-id="05e8d-121">Ripristinare i file di database in un altro percorso.</span><span class="sxs-lookup"><span data-stu-id="05e8d-121">Restore the database files to a different location.</span></span> <span data-ttu-id="05e8d-122">In un'istruzione RESTORE, utilizzare una clausola WITH MOVE per spostare ogni file.</span><span class="sxs-lookup"><span data-stu-id="05e8d-122">In a RESTORE statement, use a WITH MOVE clause to move each file.</span></span> <span data-ttu-id="05e8d-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] modificare i percorsi dei file nella griglia **Ripristina file di database come** nella pagina Opzioni della finestra di dialogo **Ripristina database**.</span><span class="sxs-lookup"><span data-stu-id="05e8d-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], change the file locations in the **Restore the database files as** grid of the **Restore Database Options** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05e8d-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05e8d-124">See Also</span></span>  
 <span data-ttu-id="05e8d-125">[Ripristinare un database in una nuova posizione &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="05e8d-125">[Restore a Database to a New Location &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="05e8d-126">[Ripristinare i file in un nuovo percorso &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="05e8d-126">[Restore Files to a New Location &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span></span>  
 [<span data-ttu-id="05e8d-127">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="05e8d-127">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
