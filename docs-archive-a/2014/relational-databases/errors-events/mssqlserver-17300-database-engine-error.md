---
title: MSSQLSERVER_17300 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17300 (Database Engine error)
ms.assetid: c1d6bfb6-28af-4df6-8087-25807602d282
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2f77e39c71901166085d011d6d00f9a4a379bece
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713224"
---
# <a name="mssqlserver_17300"></a><span data-ttu-id="2a12b-102">MSSQLSERVER_17300</span><span class="sxs-lookup"><span data-stu-id="2a12b-102">MSSQLSERVER_17300</span></span>
    
## <a name="details"></a><span data-ttu-id="2a12b-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="2a12b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2a12b-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="2a12b-104">Product Name</span></span>|<span data-ttu-id="2a12b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2a12b-105">SQL Server</span></span>|  
|<span data-ttu-id="2a12b-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="2a12b-106">Event ID</span></span>|<span data-ttu-id="2a12b-107">17300</span><span class="sxs-lookup"><span data-stu-id="2a12b-107">17300</span></span>|  
|<span data-ttu-id="2a12b-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="2a12b-108">Event Source</span></span>|<span data-ttu-id="2a12b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2a12b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2a12b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="2a12b-110">Component</span></span>|<span data-ttu-id="2a12b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2a12b-111">SQLEngine</span></span>|  
|<span data-ttu-id="2a12b-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="2a12b-112">Symbolic Name</span></span>|<span data-ttu-id="2a12b-113">PROC_OUT_OF_SYSTASK_SESSIONS</span><span class="sxs-lookup"><span data-stu-id="2a12b-113">PROC_OUT_OF_SYSTASK_SESSIONS</span></span>|  
|<span data-ttu-id="2a12b-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="2a12b-114">Message Text</span></span>|<span data-ttu-id="2a12b-115">Impossibile eseguire una nuova attività di sistema. Memoria insufficiente o numero di sessioni configurate maggiore del numero massimo consentito nel server.</span><span class="sxs-lookup"><span data-stu-id="2a12b-115">SQL Server was unable to run a new system task, either because there is insufficient memory or the number of configured sessions exceeds the maximum allowed in the server.</span></span> <span data-ttu-id="2a12b-116">Verificare che la memoria del server sia adeguata.</span><span class="sxs-lookup"><span data-stu-id="2a12b-116">Verify that the server has adequate memory.</span></span> <span data-ttu-id="2a12b-117">Per controllare il numero massimo di connessioni utente consentite, eseguire sp_configure con l'opzione 'user connections'.</span><span class="sxs-lookup"><span data-stu-id="2a12b-117">Use sp_configure with option 'user connections' to check the maximum number of user connections allowed.</span></span> <span data-ttu-id="2a12b-118">Per controllare il numero di sessioni, inclusi i processi utente, eseguire sys.dm_exec_sessions.</span><span class="sxs-lookup"><span data-stu-id="2a12b-118">Use sys.dm_exec_sessions to check the current number of sessions, including user processes.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2a12b-119">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="2a12b-119">Explanation</span></span>  
 <span data-ttu-id="2a12b-120">Il tentativo di eseguire una nuova attività di sistema non è riuscito a causa di un problema di memoria insufficiente o perché è stato superato il numero di sessioni configurate nel server.</span><span class="sxs-lookup"><span data-stu-id="2a12b-120">An attempt to run a new system task failed because of insufficient memory or because the number of configured sessions in the server was exceeded.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2a12b-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="2a12b-121">User Action</span></span>  
 <span data-ttu-id="2a12b-122">Verificare che la memoria del server sia sufficiente.</span><span class="sxs-lookup"><span data-stu-id="2a12b-122">Verify that the server has enough memory.</span></span> <span data-ttu-id="2a12b-123">Verificare il numero corrente di attività di sistema che utilizzano sys.dm_exec_sessions e il valore configurato di connessioni utente massime mediante sp_configure.</span><span class="sxs-lookup"><span data-stu-id="2a12b-123">Verify the current number of system tasks by using sys.dm_exec_sessions, and verify the configured value of maximum user connections by using sp_configure.</span></span>  
  
 <span data-ttu-id="2a12b-124">Eseguire le attività seguenti in modo appropriato:</span><span class="sxs-lookup"><span data-stu-id="2a12b-124">Perform the following tasks as appropriate:</span></span>  
  
-   <span data-ttu-id="2a12b-125">Aggiungere una quantità maggiore di memoria al server.</span><span class="sxs-lookup"><span data-stu-id="2a12b-125">Add more memory to the server.</span></span>  
  
-   <span data-ttu-id="2a12b-126">Terminare uno o più sessioni.</span><span class="sxs-lookup"><span data-stu-id="2a12b-126">Terminate one or more sessions.</span></span>  
  
-   <span data-ttu-id="2a12b-127">Aumentare il numero massimo di connessioni utente consentite sul server.</span><span class="sxs-lookup"><span data-stu-id="2a12b-127">Increase the maximum number of user connections allowed on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a12b-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a12b-128">See Also</span></span>  
 <span data-ttu-id="2a12b-129">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2a12b-129">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="2a12b-130">[Opzioni di configurazione del server &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2a12b-130">[Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="2a12b-131">[sys.dm_exec_sessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2a12b-131">[sys.dm_exec_sessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) </span></span>  
 <span data-ttu-id="2a12b-132">[Configurare l'opzione di configurazione del server user connections](../../database-engine/configure-windows/configure-the-user-connections-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="2a12b-132">[Configure the user connections Server Configuration Option](../../database-engine/configure-windows/configure-the-user-connections-server-configuration-option.md) </span></span>  
 [<span data-ttu-id="2a12b-133">KILL &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2a12b-133">KILL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/kill-transact-sql)  
  
  
