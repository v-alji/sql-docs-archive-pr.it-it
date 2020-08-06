---
title: MSSQL_ENG014117 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014117 error
ms.assetid: e5906a76-9511-4c47-8826-8c765b58a39d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e4694aacc7d1f5ee31f4ff54d8cdd4256b48f713
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623184"
---
# <a name="mssql_eng014117"></a><span data-ttu-id="bd7f2-102">MSSQL_ENG014117</span><span class="sxs-lookup"><span data-stu-id="bd7f2-102">MSSQL_ENG014117</span></span>
    
## <a name="message-details"></a><span data-ttu-id="bd7f2-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="bd7f2-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bd7f2-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="bd7f2-104">Product Name</span></span>|<span data-ttu-id="bd7f2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bd7f2-105">SQL Server</span></span>|  
|<span data-ttu-id="bd7f2-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="bd7f2-106">Event ID</span></span>|<span data-ttu-id="bd7f2-107">14117</span><span class="sxs-lookup"><span data-stu-id="bd7f2-107">14117</span></span>|  
|<span data-ttu-id="bd7f2-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="bd7f2-108">Event Source</span></span>|<span data-ttu-id="bd7f2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bd7f2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bd7f2-110">Componente</span><span class="sxs-lookup"><span data-stu-id="bd7f2-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="bd7f2-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="bd7f2-111">Symbolic Name</span></span>||  
|<span data-ttu-id="bd7f2-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="bd7f2-112">Message Text</span></span>|<span data-ttu-id="bd7f2-113">'%s' non è configurato come database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="bd7f2-113">'%s' is not configured as a distribution database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bd7f2-114">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="bd7f2-114">Explanation</span></span>  
 <span data-ttu-id="bd7f2-115">Questo errore si può verificare in presenza di una o entrambe le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd7f2-115">This error can occur if one or both of the following are true:</span></span>  
  
-   <span data-ttu-id="bd7f2-116">La voce per il database di distribuzione specificato non è presente in **msdb..MSdistributiondbs**.</span><span class="sxs-lookup"><span data-stu-id="bd7f2-116">The entry for the specified distribution database is missing from **msdb..MSdistributiondbs**.</span></span>  
  
-   <span data-ttu-id="bd7f2-117">Nel database **master** non è presente una voce per il server locale oppure la voce contenuta non è corretta.</span><span class="sxs-lookup"><span data-stu-id="bd7f2-117">There is not an entry for the local server in the **master** database, or the entry that is there is incorrect.</span></span>  
  
     <span data-ttu-id="bd7f2-118">La replica prevede che tutti i server di una topologia vengano registrati utilizzando il nome del computer con il nome di un'istanza opzionale (nel caso di un'istanza cluster il nome del server virtuale [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con il nome dell'istanza opzionale).</span><span class="sxs-lookup"><span data-stu-id="bd7f2-118">Replication expects all servers in a topology to be registered using the computer name with an optional instance name (in the case of a clustered instance, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] virtual server name with the optional instance name).</span></span> <span data-ttu-id="bd7f2-119">Per un corretto funzionamento della replica il valore restituito da `SELECT @@SERVERNAME` per ogni server nella topologia deve far corrispondere al nome dell'istanza opzionale il nome del computer o il nome del server virtuale.</span><span class="sxs-lookup"><span data-stu-id="bd7f2-119">For replication to function properly, the value returned by `SELECT @@SERVERNAME` for each server in the topology should match the computer name or virtual server name with the optional instance name.</span></span>  
  
     <span data-ttu-id="bd7f2-120">Non sarà possibile eseguire la replica, se una qualsiasi delle istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene registrata utilizzando l'indirizzo IP o il nome di dominio completo (FQDN, Fully Qualified Domain Name).</span><span class="sxs-lookup"><span data-stu-id="bd7f2-120">Replication is not supported if you have registered any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances by IP address or by Fully Qualified Domain Name (FQDN).</span></span> <span data-ttu-id="bd7f2-121">Se durante la configurazione della replica una delle istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è stata registrata utilizzando l'indirizzo IP o il nome di dominio completo in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , è possibile che venga generato questo errore.</span><span class="sxs-lookup"><span data-stu-id="bd7f2-121">If you had any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances registered by IP address or by FQDN in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] when you configured replication, this error could be raised.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bd7f2-122">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="bd7f2-122">User Action</span></span>  
 <span data-ttu-id="bd7f2-123">Verificare la corretta registrazione dell'istanza del server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="bd7f2-123">Verify that the Distributor instance is registered properly.</span></span> <span data-ttu-id="bd7f2-124">Se il nome di rete del computer e il nome dell'istanza di SQL Server sono diversi, procedere in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd7f2-124">If the network name of the computer and the name of the SQL Server instance differ, either:</span></span>  
  
-   <span data-ttu-id="bd7f2-125">Aggiungere il nome dell'istanza di SQL Server come nome di rete valido.</span><span class="sxs-lookup"><span data-stu-id="bd7f2-125">Add the SQL Server instance name as a valid network name.</span></span> <span data-ttu-id="bd7f2-126">Uno dei metodi disponibili per impostare un nome di rete alternativo consiste nell'aggiungerlo al file hosts locale.</span><span class="sxs-lookup"><span data-stu-id="bd7f2-126">One method to set an alternative network name is to add it to the local hosts file.</span></span> <span data-ttu-id="bd7f2-127">Il file hosts locale è disponibile per impostazione predefinita nella cartella WINDOWS\system32\drivers\etc o WINNT\system32\drivers\etc. Per ulteriori informazioni, vedere la documentazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="bd7f2-127">The local hosts file is located by default at WINDOWS\system32\drivers\etc or WINNT\system32\drivers\etc. For more information, see the Windows documentation.</span></span>  
  
     <span data-ttu-id="bd7f2-128">Ad esempio, se il nome del computer è comp1, l'indirizzo IP del computer è 10.193.17.129 e il nome dell'istanza è inst1/instname, aggiungere la voce seguente al file hosts:</span><span class="sxs-lookup"><span data-stu-id="bd7f2-128">For example, if the computer name is comp1 and the computer has an IP address of 10.193.17.129, and the instance name is inst1/instname, add the following entry to the hosts file:</span></span>  
  
     <span data-ttu-id="bd7f2-129">10.193.17.129 inst1</span><span class="sxs-lookup"><span data-stu-id="bd7f2-129">10.193.17.129 inst1</span></span>  
  
-   <span data-ttu-id="bd7f2-130">Disabilitare la distribuzione, registrare l'istanza e quindi riattivare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="bd7f2-130">Disable distribution, register the instance, and then reestablish distribution.</span></span> <span data-ttu-id="bd7f2-131">Se il valore di @@SERVERNAME non è corretto per un'istanza non cluster, eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="bd7f2-131">If the value of @@SERVERNAME is not correct for a nonclustered instance, follow these steps:</span></span>  
  
    ```  
    sp_dropserver '<old_name>', 'droplogins'  
    go  
    sp_addserver '<new_name>', 'local'  
    go  
    ```  
  
     <span data-ttu-id="bd7f2-132">Dopo l'esecuzione della stored procedure [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql), è necessario riavviare il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per rendere effettiva la modifica apportata a @@SERVERNAME.</span><span class="sxs-lookup"><span data-stu-id="bd7f2-132">After you execute the [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql) stored procedure, you must restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service for the change to @@SERVERNAME to take effect.</span></span>  
  
     <span data-ttu-id="bd7f2-133">Se il valore di @@SERVERNAME non è corretto per un'istanza cluster, è necessario modificare il nome tramite Amministrazione cluster.</span><span class="sxs-lookup"><span data-stu-id="bd7f2-133">If the value of @@SERVERNAME is not correct for a clustered instance, you must change the name using Cluster Administrator.</span></span> <span data-ttu-id="bd7f2-134">Per altre informazioni, vedere [Istanze del cluster di failover Always On (SQL Server)](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bd7f2-134">For more information, see [AlwaysOn Failover Cluster Instances (SQL Server)](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span></span>  
  
 <span data-ttu-id="bd7f2-135">Dopo la verifica della corretta registrazione dell'istanza del server di distribuzione, verificare che il database di distribuzione sia elencato in **msdb..MSdistributiondbs**.</span><span class="sxs-lookup"><span data-stu-id="bd7f2-135">After verifying that the Distributor instance is registered properly, verify that the distribution database is listed in **msdb..MSdistributiondbs**.</span></span> <span data-ttu-id="bd7f2-136">In caso contrario:</span><span class="sxs-lookup"><span data-stu-id="bd7f2-136">If it is not listed:</span></span>  
  
1.  <span data-ttu-id="bd7f2-137">Inserire nello script la configurazione di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="bd7f2-137">Script out the distribution configuration.</span></span> <span data-ttu-id="bd7f2-138">Per altre informazioni, vedere [Scripting Replication](scripting-replication.md).</span><span class="sxs-lookup"><span data-stu-id="bd7f2-138">For more information, see [Scripting Replication](scripting-replication.md).</span></span>  
  
2.  <span data-ttu-id="bd7f2-139">Disabilitare la distribuzione e quindi attivarla nuovamente.</span><span class="sxs-lookup"><span data-stu-id="bd7f2-139">Disable distribution and then re-enable it.</span></span> <span data-ttu-id="bd7f2-140">Per altre informazioni, vedere [Configure Distribution](configure-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="bd7f2-140">For more information, see [Configure Distribution](configure-distribution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd7f2-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd7f2-141">See Also</span></span>  
 [<span data-ttu-id="bd7f2-142">Guida di riferimento a errori ed eventi &#40;replica&#41;</span><span class="sxs-lookup"><span data-stu-id="bd7f2-142">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
