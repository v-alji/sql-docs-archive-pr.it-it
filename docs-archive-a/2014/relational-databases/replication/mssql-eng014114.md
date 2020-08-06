---
title: MSSQL_ENG014114 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014114 error
ms.assetid: f5f04590-e1c6-40d8-ab2b-98c791a0fc44
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3ba2a1fde59f55eecbfeeec46555567cde964f8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623183"
---
# <a name="mssql_eng014114"></a><span data-ttu-id="9009e-102">MSSQL_ENG014114</span><span class="sxs-lookup"><span data-stu-id="9009e-102">MSSQL_ENG014114</span></span>
    
## <a name="message-details"></a><span data-ttu-id="9009e-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="9009e-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9009e-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="9009e-104">Product Name</span></span>|<span data-ttu-id="9009e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9009e-105">SQL Server</span></span>|  
|<span data-ttu-id="9009e-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="9009e-106">Event ID</span></span>|<span data-ttu-id="9009e-107">14114</span><span class="sxs-lookup"><span data-stu-id="9009e-107">14114</span></span>|  
|<span data-ttu-id="9009e-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="9009e-108">Event Source</span></span>|<span data-ttu-id="9009e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9009e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9009e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="9009e-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="9009e-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="9009e-111">Symbolic Name</span></span>||  
|<span data-ttu-id="9009e-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="9009e-112">Message Text</span></span>|<span data-ttu-id="9009e-113">'%s' non è configurato come server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9009e-113">'%s' is not configured as a Distributor.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9009e-114">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="9009e-114">Explanation</span></span>  
 <span data-ttu-id="9009e-115">Se nel messaggio di errore viene specificata una particolare istanza, diversa da 'null', l'istanza specificata non è stata configurata correttamente per essere riconosciuta come server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9009e-115">If the error message specifies a particular instance, rather than 'null', the instance specified has not been properly configured to be recognized as a Distributor.</span></span>  
  
 <span data-ttu-id="9009e-116">Se nel messaggio viene specificato 'null' come server di distribuzione, non è presente alcuna voce del server locale nel database **master** oppure la voce non è corretta (probabilmente il computer è stato rinominato).</span><span class="sxs-lookup"><span data-stu-id="9009e-116">If the message specifies 'null' as a Distributor, there is no entry for the local server in **master** database, or the entry is incorrect (perhaps because the computer was renamed).</span></span> <span data-ttu-id="9009e-117">La replica prevede che tutti i server di una topologia vengano registrati utilizzando il nome del computer con il nome di un'istanza opzionale (nel caso di un'istanza cluster il nome del server virtuale [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con il nome dell'istanza opzionale).</span><span class="sxs-lookup"><span data-stu-id="9009e-117">Replication expects all servers in a topology to be registered using the computer name with an optional instance name (in the case of a clustered instance, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] virtual server name with the optional instance name).</span></span> <span data-ttu-id="9009e-118">Per un corretto funzionamento della replica il valore restituito da `SELECT @@SERVERNAME` per ogni server nella topologia deve far corrispondere al nome dell'istanza opzionale il nome del computer o il nome del server virtuale.</span><span class="sxs-lookup"><span data-stu-id="9009e-118">For replication to function properly, the value returned by `SELECT @@SERVERNAME` for each server in the topology should match the computer name or virtual server name with the optional instance name.</span></span>  
  
 <span data-ttu-id="9009e-119">Non sarà possibile eseguire la replica, se una qualsiasi delle istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene registrata utilizzando l'indirizzo IP o il nome di dominio completo (FQDN, Fully Qualified Domain Name).</span><span class="sxs-lookup"><span data-stu-id="9009e-119">Replication is not supported if you have registered any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances by IP address or by Fully Qualified Domain Name (FQDN).</span></span> <span data-ttu-id="9009e-120">Se durante la configurazione della replica una delle istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è stata registrata utilizzando l'indirizzo IP o il nome di dominio completo in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , è possibile che venga generato questo errore.</span><span class="sxs-lookup"><span data-stu-id="9009e-120">If you had any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances registered by IP address or by FQDN in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] when you configured replication, this error could be raised.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9009e-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="9009e-121">User Action</span></span>  
 <span data-ttu-id="9009e-122">Se nel messaggio di errore viene specificata una particolare istanza, configurare il server come server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9009e-122">If the error message specifies a particular instance, configure the server as a Distributor.</span></span> <span data-ttu-id="9009e-123">Per altre informazioni, vedere [Configure Distribution](configure-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="9009e-123">For more information, see [Configure Distribution](configure-distribution.md).</span></span>  
  
 <span data-ttu-id="9009e-124">Se nel messaggio non viene specificata una particolare istanza ('null'), verificare che l'istanza del server di distribuzione sia registrata correttamente.</span><span class="sxs-lookup"><span data-stu-id="9009e-124">If the message does not specify a particular instance ('null'), verify that the Distributor instance is registered properly.</span></span> <span data-ttu-id="9009e-125">Se il nome di rete del computer e il nome dell'istanza di SQL Server sono diversi, procedere in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="9009e-125">If the network name of the computer and the name of the SQL Server instance differ, either:</span></span>  
  
-   <span data-ttu-id="9009e-126">Aggiungere il nome dell'istanza di SQL Server come nome di rete valido.</span><span class="sxs-lookup"><span data-stu-id="9009e-126">Add the SQL Server instance name as a valid network name.</span></span> <span data-ttu-id="9009e-127">Uno dei metodi disponibili per impostare un nome di rete alternativo consiste nell'aggiungerlo al file hosts locale.</span><span class="sxs-lookup"><span data-stu-id="9009e-127">One method to set an alternative network name is to add it to the local hosts file.</span></span> <span data-ttu-id="9009e-128">Il file hosts locale è disponibile per impostazione predefinita nella cartella WINDOWS\system32\drivers\etc o WINNT\system32\drivers\etc. Per ulteriori informazioni, vedere la documentazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="9009e-128">The local hosts file is located by default at WINDOWS\system32\drivers\etc or WINNT\system32\drivers\etc. For more information, see the Windows documentation.</span></span>  
  
     <span data-ttu-id="9009e-129">Ad esempio, se il nome del computer è comp1, l'indirizzo IP del computer è 10.193.17.129 e il nome dell'istanza è inst1/instname, aggiungere la voce seguente al file hosts:</span><span class="sxs-lookup"><span data-stu-id="9009e-129">For example, if the computer name is comp1 and the computer has an IP address of 10.193.17.129, and the instance name is inst1/instname, add the following entry to the hosts file:</span></span>  
  
     <span data-ttu-id="9009e-130">10.193.17.129 inst1</span><span class="sxs-lookup"><span data-stu-id="9009e-130">10.193.17.129 inst1</span></span>  
  
-   <span data-ttu-id="9009e-131">Disabilitare la distribuzione, registrare l'istanza e quindi riattivare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9009e-131">Disable distribution, register the instance, and then reestablish distribution.</span></span> <span data-ttu-id="9009e-132">Se il valore di @@SERVERNAME non è corretto per un'istanza non cluster, eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="9009e-132">If the value of @@SERVERNAME is not correct for a nonclustered instance, follow these steps:</span></span>  
  
    ```  
    sp_dropserver '<old_name>', 'droplogins'  
    go  
    sp_addserver '<new_name>', 'local'  
    go  
    ```  
  
     <span data-ttu-id="9009e-133">Dopo l'esecuzione della stored procedure [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql), è necessario riavviare il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per rendere effettiva la modifica apportata a @@SERVERNAME.</span><span class="sxs-lookup"><span data-stu-id="9009e-133">After you execute the [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql) stored procedure, you must restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service for the change to @@SERVERNAME to take effect.</span></span>  
  
     <span data-ttu-id="9009e-134">Se il valore di @@SERVERNAME non è corretto per un'istanza cluster, è necessario modificare il nome tramite Amministrazione cluster.</span><span class="sxs-lookup"><span data-stu-id="9009e-134">If the value of @@SERVERNAME is not correct for a clustered instance, you must change the name using Cluster Administrator.</span></span> <span data-ttu-id="9009e-135">Per altre informazioni, vedere [Istanze del cluster di failover Always On (SQL Server)](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9009e-135">For more information, see [AlwaysOn Failover Cluster Instances (SQL Server)](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9009e-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9009e-136">See Also</span></span>  
 [<span data-ttu-id="9009e-137">Guida di riferimento a errori ed eventi &#40;replica&#41;</span><span class="sxs-lookup"><span data-stu-id="9009e-137">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
