---
title: MSSQLSERVER_1204 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1204 (Database Engine error)
ms.assetid: de6ece78-79de-484d-9224-ca0f7645815f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7ca03c19552b88e391d2de053193a70531571ece
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627786"
---
# <a name="mssqlserver_1204"></a><span data-ttu-id="80884-102">MSSQLSERVER_1204</span><span class="sxs-lookup"><span data-stu-id="80884-102">MSSQLSERVER_1204</span></span>
    
## <a name="details"></a><span data-ttu-id="80884-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="80884-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="80884-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="80884-104">Product Name</span></span>|<span data-ttu-id="80884-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="80884-105">SQL Server</span></span>|  
|<span data-ttu-id="80884-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="80884-106">Event ID</span></span>|<span data-ttu-id="80884-107">1204</span><span class="sxs-lookup"><span data-stu-id="80884-107">1204</span></span>|  
|<span data-ttu-id="80884-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="80884-108">Event Source</span></span>|<span data-ttu-id="80884-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="80884-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="80884-110">Componente</span><span class="sxs-lookup"><span data-stu-id="80884-110">Component</span></span>|<span data-ttu-id="80884-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="80884-111">SQLEngine</span></span>|  
|<span data-ttu-id="80884-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="80884-112">Symbolic Name</span></span>|<span data-ttu-id="80884-113">LK_OUTOF</span><span class="sxs-lookup"><span data-stu-id="80884-113">LK_OUTOF</span></span>|  
|<span data-ttu-id="80884-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="80884-114">Message Text</span></span>|<span data-ttu-id="80884-115">In questo momento l'istanza del Motore di database di SQL Server non è in grado di ottenere una risorsa LOCK.</span><span class="sxs-lookup"><span data-stu-id="80884-115">The instance of the SQL Server Database Engine cannot obtain a LOCK resource at this time.</span></span> <span data-ttu-id="80884-116">Eseguire nuovamente l'istruzione quando è presente un minor numero di utenti attivi.</span><span class="sxs-lookup"><span data-stu-id="80884-116">Rerun your statement when there are fewer active users.</span></span> <span data-ttu-id="80884-117">Chiedere all'amministratore del database di controllare la configurazione di memoria e di blocco per l'istanza o di verificare la presenza di transazioni con esecuzione prolungata.</span><span class="sxs-lookup"><span data-stu-id="80884-117">Ask the database administrator to check the lock and memory configuration for this instance, or to check for long-running transactions.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="80884-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="80884-118">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="80884-119">non è in grado di ottenere una risorsa di blocco.</span><span class="sxs-lookup"><span data-stu-id="80884-119">cannot obtain a lock resource.</span></span> <span data-ttu-id="80884-120">L'errore può essere causato da uno dei motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="80884-120">This can be caused by either of the following reasons:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="80884-121">non è in grado di allocare ulteriore memoria dal sistema operativo perché questa è già usata da altri processi oppure perché è stata configurata l'opzione **Max Server Memory** per il server in uso.</span><span class="sxs-lookup"><span data-stu-id="80884-121">cannot allocate more memory from the operating system, either because other processes are using it, or because the server is operating with the **max server memory** option configured.</span></span>  
  
-   <span data-ttu-id="80884-122">In Gestione blocchi non viene utilizzato più del 60 percento della memoria disponibile per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80884-122">The lock manager will not use more than 60 percent of the memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="80884-123">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="80884-123">User Action</span></span>  
 <span data-ttu-id="80884-124">Se si sospetta che il motivo dell'errore sia l'impossibilità di SQL Server di allocare memoria sufficiente, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="80884-124">If you suspect that SQL Server cannot allocate sufficient memory, try the following:</span></span>  
  
-   <span data-ttu-id="80884-125">Se le risorse vengono utilizzate da altre applicazioni oltre a SQL Server, provare ad arrestarne l'esecuzione o a eseguirle in un server distinto.</span><span class="sxs-lookup"><span data-stu-id="80884-125">If applications besides SQL Server are consuming resources, try stopping these applications or consider running them on a separate server.</span></span> <span data-ttu-id="80884-126">In questo modo verrà rilasciata memoria da altri processi di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="80884-126">This will remove release memory from other processes for SQL Server.</span></span>  
  
-   <span data-ttu-id="80884-127">Se è stata configurata l'opzione max server memory, aumentarne il valore impostato.</span><span class="sxs-lookup"><span data-stu-id="80884-127">If you have configured max server memory, increase max server memory setting.</span></span>  
  
 <span data-ttu-id="80884-128">Se si sospetta che in Gestione blocchi sia stata utilizzata la massima quantità di memoria disponibile, individuare la transazione che mantiene la maggior parte dei blocchi e interromperla.</span><span class="sxs-lookup"><span data-stu-id="80884-128">If you suspect that the lock manager has used the maximum amount of available memory identify the transaction that is holding the most locks and terminate it.</span></span> <span data-ttu-id="80884-129">Lo script seguente consente di individuare la transazione che presenta più blocchi:</span><span class="sxs-lookup"><span data-stu-id="80884-129">The following script will identify the transaction with the most locks:</span></span>  
  
```  
SELECT request_session_id, COUNT (*) num_locks  
FROM sys.dm_tran_locks  
GROUP BY request_session_id   
ORDER BY count (*) DESC  
```  
  
 <span data-ttu-id="80884-130">Individuare l'ID di sessione più elevato e interrompere la transazione corrispondente tramite il comando KILL.</span><span class="sxs-lookup"><span data-stu-id="80884-130">Take the highest session id, and terminate it using the KILL command.</span></span>  
  
  
