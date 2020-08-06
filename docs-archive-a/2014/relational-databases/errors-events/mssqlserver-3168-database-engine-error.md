---
title: MSSQLSERVER_3168 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3168 (Database Engine error)
ms.assetid: 991111d9-1eb3-43e9-9333-a75a775c3200
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 764f456653365c085e9f756a749910bbd03b4259
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628729"
---
# <a name="mssqlserver_3168"></a><span data-ttu-id="73e9c-102">MSSQLSERVER_3168</span><span class="sxs-lookup"><span data-stu-id="73e9c-102">MSSQLSERVER_3168</span></span>
    
## <a name="details"></a><span data-ttu-id="73e9c-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="73e9c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="73e9c-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="73e9c-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="73e9c-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="73e9c-105">Event ID</span></span>|<span data-ttu-id="73e9c-106">3168</span><span class="sxs-lookup"><span data-stu-id="73e9c-106">3168</span></span>|  
|<span data-ttu-id="73e9c-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="73e9c-107">Event Source</span></span>|<span data-ttu-id="73e9c-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="73e9c-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="73e9c-109">Componente</span><span class="sxs-lookup"><span data-stu-id="73e9c-109">Component</span></span>|<span data-ttu-id="73e9c-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="73e9c-110">SQLEngine</span></span>|  
|<span data-ttu-id="73e9c-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="73e9c-111">Symbolic Name</span></span>|<span data-ttu-id="73e9c-112">LDDB_SYSTEMWRONGVER</span><span class="sxs-lookup"><span data-stu-id="73e9c-112">LDDB_SYSTEMWRONGVER</span></span>|  
|<span data-ttu-id="73e9c-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="73e9c-113">Message Text</span></span>|<span data-ttu-id="73e9c-114">Impossibile ripristinare il backup del database di sistema nel dispositivo %ls perché è stato creato da una versione del server (%ls) diversa da quella del server in uso (%ls).</span><span class="sxs-lookup"><span data-stu-id="73e9c-114">The backup of the system database on the device %ls cannot be restored because it was created by a different version of the server (%ls) than this server (%ls).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="73e9c-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="73e9c-115">Explanation</span></span>  
 <span data-ttu-id="73e9c-116">Non è possibile ripristinare un backup di un database di sistema (**master**, **model** o **msdb**) in una build del server diversa rispetto alla build in cui il backup è stato originariamente eseguito.</span><span class="sxs-lookup"><span data-stu-id="73e9c-116">You cannot restore a backup of a system database (**master**, **model**, or **msdb**) on a server build that differs from the build on which the backup was originally performed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73e9c-117">L'installazione di un Service Pack o una build di hotfix modifica il numero di build del server. Le build del server sono sempre incrementali.</span><span class="sxs-lookup"><span data-stu-id="73e9c-117">Installing a service pack or a hotfix build changes the server build number, and server builds are always incremental.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="73e9c-118">Possibili cause</span><span class="sxs-lookup"><span data-stu-id="73e9c-118">Possible Causes</span></span>  
 <span data-ttu-id="73e9c-119">Lo schema di database per i database di sistema potrebbe essere stato modificato nelle diverse build del server.</span><span class="sxs-lookup"><span data-stu-id="73e9c-119">The database schema for system databases may be changed across server builds.</span></span> <span data-ttu-id="73e9c-120">Per verificare che una modifica dello schema non causi inconsistenze, l'istruzione RESTORE confronta il numero di build del server nel file di backup con il numero di build del server in cui si tenta di ripristinare il backup.</span><span class="sxs-lookup"><span data-stu-id="73e9c-120">To make sure that a schema change does not cause inconsistencies, the RESTORE statement compares the server build number on the backup file to the build number of the server on which you are trying to restore the backup.</span></span> <span data-ttu-id="73e9c-121">In caso di build diverse, l'istruzione visualizza il messaggio di errore 3168 e l'operazione di ripristino viene terminata in modo anomalo.</span><span class="sxs-lookup"><span data-stu-id="73e9c-121">If the builds are different, the statement issues the 3168 error message, and the restore operation terminates abnormally.</span></span>  
  
 <span data-ttu-id="73e9c-122">Questo problema potrebbe verificarsi ad esempio negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="73e9c-122">Some scenarios in which this problem may occur include the following:</span></span>  
  
-   <span data-ttu-id="73e9c-123">Un utente tenta di ripristinare un database di sistema sul server A da un backup eseguito sul server B. I server A e B sono basati su build diverse.</span><span class="sxs-lookup"><span data-stu-id="73e9c-123">A user tries to restore a system database on Server A from a backup taken on Server B. Servers A and B are on different server builds.</span></span> <span data-ttu-id="73e9c-124">Il server A potrebbe ad esempio utilizzare la build della versione originale e il server B potrebbe utilizzare una build del Service Pack 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="73e9c-124">For example, Server A might be on the original release version build and Server B might be on a service pack 1 (SP1) build.</span></span>  
  
-   <span data-ttu-id="73e9c-125">Un utente tenta di ripristinare un database di sistema da un backup eseguito sullo stesso server.</span><span class="sxs-lookup"><span data-stu-id="73e9c-125">A user tries to restore a system database from a backup taken on the same server.</span></span> <span data-ttu-id="73e9c-126">Al momento del backup, tuttavia, sul server era in esecuzione una build diversa.</span><span class="sxs-lookup"><span data-stu-id="73e9c-126">However, the server was running a different build when the backup occurred.</span></span> <span data-ttu-id="73e9c-127">Dall'esecuzione del backup, il server è stato aggiornato.</span><span class="sxs-lookup"><span data-stu-id="73e9c-127">That is, the server was upgraded since the backup was performed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="73e9c-128">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="73e9c-128">User Action</span></span>  
 <span data-ttu-id="73e9c-129">Questa situazione influisce sul processo di ripristino, che verrà utilizzato solo come ultima risorsa.</span><span class="sxs-lookup"><span data-stu-id="73e9c-129">The restore process in this situation is fairly involved, and used only as a last resort.</span></span> <span data-ttu-id="73e9c-130">Per altre informazioni, vedere "[Non è possibile ripristinare i backup di database di sistema a una build diversa di SQL Server](https://support.microsoft.com/kb/264474)".</span><span class="sxs-lookup"><span data-stu-id="73e9c-130">For more information, see"[You cannot restore system database backups to a different build of SQL Server](https://support.microsoft.com/kb/264474)".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73e9c-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73e9c-131">See Also</span></span>  
 [<span data-ttu-id="73e9c-132">Backup e ripristino di database di sistema &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="73e9c-132">Back Up and Restore of System Databases &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md)  
  
  
