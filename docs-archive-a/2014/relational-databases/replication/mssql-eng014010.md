---
title: MSSQL_ENG014010 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014010 error
ms.assetid: 6ea84f2f-e7a2-4028-9ea9-af0d2eba660e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c3d989eb7ae78562fb77d9896545539ba4ca3c7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624067"
---
# <a name="mssql_eng014010"></a><span data-ttu-id="a7783-102">MSSQL_ENG014010</span><span class="sxs-lookup"><span data-stu-id="a7783-102">MSSQL_ENG014010</span></span>
    
## <a name="message-details"></a><span data-ttu-id="a7783-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="a7783-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a7783-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="a7783-104">Product Name</span></span>|<span data-ttu-id="a7783-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a7783-105">SQL Server</span></span>|  
|<span data-ttu-id="a7783-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="a7783-106">Event ID</span></span>|<span data-ttu-id="a7783-107">14010</span><span class="sxs-lookup"><span data-stu-id="a7783-107">14010</span></span>|  
|<span data-ttu-id="a7783-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="a7783-108">Event Source</span></span>|<span data-ttu-id="a7783-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a7783-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a7783-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a7783-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="a7783-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="a7783-111">Symbolic Name</span></span>||  
|<span data-ttu-id="a7783-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="a7783-112">Message Text</span></span>|<span data-ttu-id="a7783-113">Il server '%s' non è definito come server di sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="a7783-113">The server '%s' is not defined as a subscription server.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a7783-114">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="a7783-114">Explanation</span></span>  
 <span data-ttu-id="a7783-115">La replica prevede che tutti i server di una topologia vengano registrati utilizzando il nome del computer con il nome di un'istanza opzionale (nel caso di un'istanza cluster il nome del server virtuale [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con il nome dell'istanza opzionale).</span><span class="sxs-lookup"><span data-stu-id="a7783-115">Replication expects all servers in a topology to be registered using the computer name with an optional instance name (in the case of a clustered instance, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] virtual server name with the optional instance name).</span></span> <span data-ttu-id="a7783-116">Per un corretto funzionamento della replica il valore restituito da `SELECT @@SERVERNAME` per ogni server nella topologia deve far corrispondere al nome dell'istanza opzionale il nome del computer o il nome del server virtuale.</span><span class="sxs-lookup"><span data-stu-id="a7783-116">For replication to function properly, the value returned by `SELECT @@SERVERNAME` for each server in the topology should match the computer name or virtual server name with the optional instance name.</span></span>  
  
 <span data-ttu-id="a7783-117">Non sarà possibile eseguire la replica, se una qualsiasi delle istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene registrata utilizzando l'indirizzo IP o il nome di dominio completo (FQDN, Fully Qualified Domain Name).</span><span class="sxs-lookup"><span data-stu-id="a7783-117">Replication is not supported if you have registered any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances by IP address or by Fully Qualified Domain Name (FQDN).</span></span> <span data-ttu-id="a7783-118">Se al momento della configurazione della replica tali istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sono state registrate per indirizzo IP o per nome completo dominio in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , è possibile che l'errore venga generato.</span><span class="sxs-lookup"><span data-stu-id="a7783-118">If you have any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances registered by IP address or by FQDN in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] when you configured replication, this error could be raised.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a7783-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="a7783-119">User Action</span></span>  
 <span data-ttu-id="a7783-120">Verificare che tutte le istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nella topologia siano state registrate correttamente.</span><span class="sxs-lookup"><span data-stu-id="a7783-120">Verify that all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances in the topology are registered properly.</span></span> <span data-ttu-id="a7783-121">Se il nome di rete del computer e il nome dell'istanza di SQL Server sono diversi, procedere in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a7783-121">If the network name of the computer and the name of the SQL Server instance differ, either:</span></span>  
  
-   <span data-ttu-id="a7783-122">Aggiungere il nome dell'istanza di SQL Server come nome di rete valido.</span><span class="sxs-lookup"><span data-stu-id="a7783-122">Add the SQL Server instance name as a valid network name.</span></span> <span data-ttu-id="a7783-123">Uno dei metodi disponibili per impostare un nome di rete alternativo consiste nell'aggiungerlo al file hosts locale.</span><span class="sxs-lookup"><span data-stu-id="a7783-123">One method to set an alternative network name is to add it to the local hosts file.</span></span> <span data-ttu-id="a7783-124">Il file hosts locale è disponibile per impostazione predefinita nella cartella WINDOWS\system32\drivers\etc o WINNT\system32\drivers\etc. Per ulteriori informazioni, vedere la documentazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="a7783-124">The local hosts file is located by default at WINDOWS\system32\drivers\etc or WINNT\system32\drivers\etc. For more information, see the Windows documentation.</span></span>  
  
     <span data-ttu-id="a7783-125">Ad esempio, se il nome del computer è comp1, l'indirizzo IP del computer è 10.193.17.129 e il nome dell'istanza è inst1/instname, aggiungere la voce seguente al file hosts:</span><span class="sxs-lookup"><span data-stu-id="a7783-125">For example, if the computer name is comp1 and the computer has an IP address of 10.193.17.129, and the instance name is inst1/instname, add the following entry to the hosts file:</span></span>  
  
     <span data-ttu-id="a7783-126">10.193.17.129 inst1</span><span class="sxs-lookup"><span data-stu-id="a7783-126">10.193.17.129 inst1</span></span>  
  
-   <span data-ttu-id="a7783-127">Rimuovere la replica, registrare ogni istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , quindi ristabilire la replica.</span><span class="sxs-lookup"><span data-stu-id="a7783-127">Remove replication, register each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, and then reestablish replication.</span></span> <span data-ttu-id="a7783-128">Se il valore di @@SERVERNAME non è corretto per un'istanza non cluster, eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="a7783-128">If the value of @@SERVERNAME is not correct for a nonclustered instance, follow these steps:</span></span>  
  
    ```  
    sp_dropserver '<old_name>', 'droplogins'  
    go  
    sp_addserver '<new_name>', 'local'  
    go  
    ```  
  
     <span data-ttu-id="a7783-129">Dopo l'esecuzione della stored procedure [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql), è necessario riavviare il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per rendere effettiva la modifica apportata a @@SERVERNAME.</span><span class="sxs-lookup"><span data-stu-id="a7783-129">After you execute the [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql) stored procedure, you must restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service for the change to @@SERVERNAME to take effect.</span></span>  
  
     <span data-ttu-id="a7783-130">Se il valore di @@SERVERNAME non è corretto per un'istanza cluster, è necessario modificare il nome tramite Amministrazione cluster.</span><span class="sxs-lookup"><span data-stu-id="a7783-130">If the value of @@SERVERNAME is not correct for a clustered instance, you must change the name using Cluster Administrator.</span></span> <span data-ttu-id="a7783-131">Per altre informazioni, vedere [Istanze del cluster di failover Always On &#40;SQL Server&#41;](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a7783-131">For more information, see [AlwaysOn Failover Cluster Instances &#40;SQL Server&#41;](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7783-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7783-132">See Also</span></span>  
 <span data-ttu-id="a7783-133">[@@SERVERNAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/servername-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a7783-133">[@@SERVERNAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/servername-transact-sql) </span></span>  
 [<span data-ttu-id="a7783-134">Guida di riferimento a errori ed eventi &#40;replica&#41;</span><span class="sxs-lookup"><span data-stu-id="a7783-134">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
