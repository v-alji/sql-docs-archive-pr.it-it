---
title: MSSQLSERVER_3156 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3156 (Database Engine error)
ms.assetid: 345d8ed4-177e-4ec3-bab3-25d30000e323
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 25b5a037012a6d6b47b91e763a49cfb67b89f43c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628730"
---
# <a name="mssqlserver_3156"></a><span data-ttu-id="3ebeb-102">MSSQLSERVER_3156</span><span class="sxs-lookup"><span data-stu-id="3ebeb-102">MSSQLSERVER_3156</span></span>
    
## <a name="details"></a><span data-ttu-id="3ebeb-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3ebeb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3ebeb-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="3ebeb-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="3ebeb-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="3ebeb-105">Event ID</span></span>|<span data-ttu-id="3ebeb-106">3156</span><span class="sxs-lookup"><span data-stu-id="3ebeb-106">3156</span></span>|  
|<span data-ttu-id="3ebeb-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="3ebeb-107">Event Source</span></span>|<span data-ttu-id="3ebeb-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3ebeb-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3ebeb-109">Componente</span><span class="sxs-lookup"><span data-stu-id="3ebeb-109">Component</span></span>|<span data-ttu-id="3ebeb-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3ebeb-110">SQLEngine</span></span>|  
|<span data-ttu-id="3ebeb-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="3ebeb-111">Symbolic Name</span></span>|<span data-ttu-id="3ebeb-112">LDDB_CANT_WRITE</span><span class="sxs-lookup"><span data-stu-id="3ebeb-112">LDDB_CANT_WRITE</span></span>|  
|<span data-ttu-id="3ebeb-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="3ebeb-113">Message Text</span></span>|<span data-ttu-id="3ebeb-114">Impossibile ripristinare il file '%ls' in '%ls'.</span><span class="sxs-lookup"><span data-stu-id="3ebeb-114">File '%ls' cannot be restored to '%ls'.</span></span> <span data-ttu-id="3ebeb-115">Utilizzare WITH MOVE per identificare un percorso valido per il file.</span><span class="sxs-lookup"><span data-stu-id="3ebeb-115">Use WITH MOVE to identify a valid location for the file.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3ebeb-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="3ebeb-116">Explanation</span></span>  
 <span data-ttu-id="3ebeb-117">Questo messaggio generico identifica i nomi file logici o fisici dei file di cui è non stato possibile eseguire il ripristino a causa di un problema relativo al percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="3ebeb-117">This general message identifies the logical or physical file names of files that could not be restored because of a problem with the specified location.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="3ebeb-118">Possibili cause</span><span class="sxs-lookup"><span data-stu-id="3ebeb-118">Possible Causes</span></span>  
 <span data-ttu-id="3ebeb-119">Tra le cause possibili sono incluse le seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ebeb-119">The possible causes include the following:</span></span>  
  
-   <span data-ttu-id="3ebeb-120">Potrebbe essere necessario l'accesso alla directory di Windows specificata.</span><span class="sxs-lookup"><span data-stu-id="3ebeb-120">You might need access to the specified Windows directory.</span></span>  
  
-   <span data-ttu-id="3ebeb-121">Il percorso potrebbe essere stato digitato in modo non corretto oppure è possibile che il percorso specificato non esista.</span><span class="sxs-lookup"><span data-stu-id="3ebeb-121">You might have mistyped the path or specified a path that does not exist.</span></span>  
  
-   <span data-ttu-id="3ebeb-122">Il nome file potrebbe essere utilizzato da un file che non può essere sovrascritto.</span><span class="sxs-lookup"><span data-stu-id="3ebeb-122">The file name might be being used by a file that cannot be overwritten.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3ebeb-123">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="3ebeb-123">User Action</span></span>  
 <span data-ttu-id="3ebeb-124">Esaminare i log degli errori alla ricerca di altri messaggi contenenti ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="3ebeb-124">Look at the error logs for other messages that provide more details.</span></span>  
  
 <span data-ttu-id="3ebeb-125">Correggere il problema relativo al percorso specificato, ad esempio concedendo l'accesso, oppure utilizzare l'opzione WITH MOVE nell'istruzione RESTORE per rilocare il file.</span><span class="sxs-lookup"><span data-stu-id="3ebeb-125">Correct the problem with the specified location, for example, by granting access, or use the WITH MOVE option in your RESTORE statement to relocate the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ebeb-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ebeb-126">See Also</span></span>  
 <span data-ttu-id="3ebeb-127">[Ripristinare un database in una nuova posizione &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3ebeb-127">[Restore a Database to a New Location &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="3ebeb-128">[Ripristinare i file in un nuovo percorso &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3ebeb-128">[Restore Files to a New Location &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span></span>  
 [<span data-ttu-id="3ebeb-129">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3ebeb-129">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
