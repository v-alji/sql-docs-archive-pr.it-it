---
title: MSSQLSERVER_3181 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3181 (Database Engine error)
ms.assetid: e6d2e716-5263-477c-ad0e-7bcbfef4c1f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f18509d9a18ba8be1f4e40c93bff5abfcae3d69c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628725"
---
# <a name="mssqlserver_3181"></a><span data-ttu-id="23064-102">MSSQLSERVER_3181</span><span class="sxs-lookup"><span data-stu-id="23064-102">MSSQLSERVER_3181</span></span>
    
## <a name="details"></a><span data-ttu-id="23064-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="23064-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="23064-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="23064-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="23064-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="23064-105">Event ID</span></span>|<span data-ttu-id="23064-106">3181</span><span class="sxs-lookup"><span data-stu-id="23064-106">3181</span></span>|  
|<span data-ttu-id="23064-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="23064-107">Event Source</span></span>|<span data-ttu-id="23064-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="23064-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="23064-109">Componente</span><span class="sxs-lookup"><span data-stu-id="23064-109">Component</span></span>|<span data-ttu-id="23064-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="23064-110">SQLEngine</span></span>|  
|<span data-ttu-id="23064-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="23064-111">Symbolic Name</span></span>|<span data-ttu-id="23064-112">LDDB_STORAGE_VERIFY</span><span class="sxs-lookup"><span data-stu-id="23064-112">LDDB_STORAGE_VERIFY</span></span>|  
|<span data-ttu-id="23064-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="23064-113">Message Text</span></span>|<span data-ttu-id="23064-114">Durante il tentativo di ripristinare questo backup potrebbero verificarsi problemi relativi allo spazio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="23064-114">Attempting to restore this backup may encounter storage space problems.</span></span> <span data-ttu-id="23064-115">Ulteriori informazioni verranno fornite nei successivi messaggi.</span><span class="sxs-lookup"><span data-stu-id="23064-115">Subsequent messages will provide details.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="23064-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="23064-116">Explanation</span></span>  
 <span data-ttu-id="23064-117">Con l'istruzione RESTORE VERIFYONLY viene controllato lo spazio di archiviazione disponibile sul disco in cui il database deve essere ripristinato.</span><span class="sxs-lookup"><span data-stu-id="23064-117">The RESTORE VERIFYONLY statement checks the available storage space on the disk to which the database is to be restored.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="23064-118">Possibili cause</span><span class="sxs-lookup"><span data-stu-id="23064-118">Possible Causes</span></span>  
 <span data-ttu-id="23064-119">È possibile che lo spazio disponibile su disco sia insufficiente per il ripristino del backup verificato.</span><span class="sxs-lookup"><span data-stu-id="23064-119">The available disk space may be insufficient to restore the backup being verified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="23064-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="23064-120">User Action</span></span>  
 <span data-ttu-id="23064-121">Ripristinare il backup in una posizione con spazio su disco sufficiente oppure aumentare lo spazio sul disco.</span><span class="sxs-lookup"><span data-stu-id="23064-121">Restore the backup to a location with sufficient disk space, or provide more space on the disk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23064-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23064-122">See Also</span></span>  
 <span data-ttu-id="23064-123">[Ripristinare un database in una nuova posizione &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="23064-123">[Restore a Database to a New Location &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="23064-124">[Ripristinare i file in un nuovo percorso &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="23064-124">[Restore Files to a New Location &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="23064-125">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="23064-125">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="23064-126">RESTORE VERIFYONLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="23064-126">RESTORE VERIFYONLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql)  
  
  
