---
title: Rinominare un computer che ospita un'istanza autonoma di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- remote login errors [SQL Server]
- standalone computer names [SQL Server]
- names [SQL Server], standalone instances of SQL Server
- renaming standalone instances of SQL Server
- sysservers system table
- removing remote logins
- deleting remote logins
- dropping remote logins
ms.assetid: bbaf1445-b8a2-4ebf-babe-17d8cf20b037
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 079348921900a7cbf880027433280253df1a9e30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724087"
---
# <a name="rename-a-computer-that-hosts-a-stand-alone-instance-of-sql-server"></a><span data-ttu-id="6527c-102">Rinominare un computer che ospita un'istanza autonoma di SQL Server</span><span class="sxs-lookup"><span data-stu-id="6527c-102">Rename a Computer that Hosts a Stand-Alone Instance of SQL Server</span></span>
  <span data-ttu-id="6527c-103">Quando si modifica il nome del computer in cui è in esecuzione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], il nuovo nome viene riconosciuto durante l'avvio di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6527c-103">When you change the name of the computer that is running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the new name is recognized during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startup.</span></span> <span data-ttu-id="6527c-104">Non è necessario eseguire nuovamente il programma di installazione per reimpostare il nome del computer.</span><span class="sxs-lookup"><span data-stu-id="6527c-104">You do not have to run Setup again to reset the computer name.</span></span> <span data-ttu-id="6527c-105">Utilizzare invece la procedura riportata di seguito per aggiornare i metadati di sistema archiviati in sys.servers e restituiti dalla funzione di sistema @@SERVERNAME .</span><span class="sxs-lookup"><span data-stu-id="6527c-105">Instead, use the following steps to update system metadata that is stored in sys.servers and reported by the system function @@SERVERNAME.</span></span> <span data-ttu-id="6527c-106">Aggiornare i metadati di sistema in modo da riflettere le modifiche apportate al nome del computer per le connessioni remote e le applicazioni che utilizzano @@SERVERNAME o che eseguono query sul nome del server da sys.servers.</span><span class="sxs-lookup"><span data-stu-id="6527c-106">Update system metadata to reflect computer name changes for remote connections and applications that use @@SERVERNAME, or that query the server name from sys.servers.</span></span>  
  
 <span data-ttu-id="6527c-107">La procedura seguente non può essere utilizzata per rinominare un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)],</span><span class="sxs-lookup"><span data-stu-id="6527c-107">The following steps cannot be used to rename an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6527c-108">ma solo per rinominare la parte del nome di istanza corrispondente al nome del computer.</span><span class="sxs-lookup"><span data-stu-id="6527c-108">They can be used only to rename the part of the instance name that corresponds to the computer name.</span></span> <span data-ttu-id="6527c-109">Ad esempio, è possibile modificare il nome di un computer denominato MB1 che ospita un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] denominata Instance1 trasformandolo in MB2.</span><span class="sxs-lookup"><span data-stu-id="6527c-109">For example, you can change a computer named MB1 that hosts an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] named Instance1 to another name, such as MB2.</span></span> <span data-ttu-id="6527c-110">La parte del nome che si riferisce all'istanza, ovvero Instance1, rimarrà tuttavia invariata.</span><span class="sxs-lookup"><span data-stu-id="6527c-110">However, the instance part of the name, Instance1, will remain unchanged.</span></span> <span data-ttu-id="6527c-111">In questo esempio \\\\*ComputerName*\\*InstanceName* verrebbe trasformato da \\\MB1\Instance1 in \\\MB2\Instance1.</span><span class="sxs-lookup"><span data-stu-id="6527c-111">In this example, the \\\\*ComputerName*\\*InstanceName* would be changed from \\\MB1\Instance1 to \\\MB2\Instance1.</span></span>  
  
 <span data-ttu-id="6527c-112">**Prima di iniziare**</span><span class="sxs-lookup"><span data-stu-id="6527c-112">**Before you begin**</span></span>  
  
 <span data-ttu-id="6527c-113">Prima di iniziare il processo di ridenominazione, esaminare le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6527c-113">Before you begin the renaming process, review the following information:</span></span>  
  
-   <span data-ttu-id="6527c-114">Se un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fa parte di un cluster di failover di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , il processo di ridenominazione del computer è diverso da quello previsto per un computer che ospita un'istanza autonoma.</span><span class="sxs-lookup"><span data-stu-id="6527c-114">When an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is part of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, the computer renaming process differs from a computer that hosts a stand-alone instance.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6527c-115">non supporta la ridenominazione dei computer interessati dalla replica, a meno che non si usi il log shipping con replica.</span><span class="sxs-lookup"><span data-stu-id="6527c-115">does not support renaming computers that are involved in replication, except when you use log shipping with replication.</span></span> <span data-ttu-id="6527c-116">Il computer secondario nel log shipping può essere rinominato in caso di perdita definitiva del computer primario.</span><span class="sxs-lookup"><span data-stu-id="6527c-116">The secondary computer in log shipping can be renamed if the primary computer is permanently lost.</span></span> <span data-ttu-id="6527c-117">Per altre informazioni, vedere [Log shipping e replica &#40;SQL Server&#41;](../log-shipping/log-shipping-and-replication-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6527c-117">For more information, see [Log Shipping and Replication &#40;SQL Server&#41;](../log-shipping/log-shipping-and-replication-sql-server.md).</span></span>  
  
-   <span data-ttu-id="6527c-118">Quando si rinomina un computer configurato per l'utilizzo di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] potrebbe non essere disponibile in seguito alla modifica del nome del computer.</span><span class="sxs-lookup"><span data-stu-id="6527c-118">When you rename a computer that is configured to use [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] might not be available after the computer name change.</span></span> <span data-ttu-id="6527c-119">Per altre informazioni, vedere [Rinominare un computer del server di report](../../reporting-services/report-server/rename-a-report-server-computer.md).</span><span class="sxs-lookup"><span data-stu-id="6527c-119">For more information, see [Rename a Report Server Computer](../../reporting-services/report-server/rename-a-report-server-computer.md).</span></span>  
  
-   <span data-ttu-id="6527c-120">Quando si rinomina un computer configurato per l'utilizzo del mirroring del database, è necessario disabilitare il mirroring del database prima dell'operazione di ridenominazione.</span><span class="sxs-lookup"><span data-stu-id="6527c-120">When you rename a computer that is configured to use database mirroring, you must turn off database mirroring before the renaming operation.</span></span> <span data-ttu-id="6527c-121">Riattivare quindi il mirroring del database con il nuovo nome del computer.</span><span class="sxs-lookup"><span data-stu-id="6527c-121">Then, re-establish database mirroring with the new computer name.</span></span> <span data-ttu-id="6527c-122">I metadati per il mirroring del database non verranno aggiornati automaticamente per riflettere il nuovo nome del computer.</span><span class="sxs-lookup"><span data-stu-id="6527c-122">Metadata for database mirroring will not be updated automatically to reflect the new computer name.</span></span> <span data-ttu-id="6527c-123">Per aggiornare i metadati di sistema, utilizzare la procedura indicata di seguito:</span><span class="sxs-lookup"><span data-stu-id="6527c-123">Use the following steps to update system metadata.</span></span>  
  
-   <span data-ttu-id="6527c-124">Gli utenti che si connettono a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tramite un gruppo di Windows che utilizza un riferimento specificato a livello di codice al nome del computer potrebbero non essere in grado di connettersi a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6527c-124">Users who connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] through a Windows group that uses a hard-coded reference to the computer name might not be able to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6527c-125">Questo problema può verificarsi in seguito alla ridenominazione se il gruppo di Windows specifica il nome del computer precedente.</span><span class="sxs-lookup"><span data-stu-id="6527c-125">This can occur after the rename if the Windows group specifies the old computer name.</span></span> <span data-ttu-id="6527c-126">Per garantire che tale gruppo di Windows consenta la connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dopo l'operazione di ridenominazione, aggiornarlo in modo che specifichi il nuovo nome del computer.</span><span class="sxs-lookup"><span data-stu-id="6527c-126">To ensure that such Windows groups have [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connectivity following the renaming operation, update the Windows group to specify the new computer name.</span></span>  
  
 <span data-ttu-id="6527c-127">È possibile connettersi a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzando il nuovo nome del computer in seguito al riavvio di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6527c-127">You can connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using the new computer name after you have restarted [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6527c-128">Per garantire che @@SERVERNAME restituisca il nome aggiornato dell'istanza del server locale, è consigliabile eseguire manualmente la procedura descritta di seguito valida per il proprio scenario.</span><span class="sxs-lookup"><span data-stu-id="6527c-128">To ensure that @@SERVERNAME returns the updated name of the local server instance, you should manually run the following procedure that applies to your scenario.</span></span> <span data-ttu-id="6527c-129">La procedura varia a seconda che si aggiorni un computer che ospita un'istanza predefinita o un'istanza denominata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6527c-129">The procedure you use depends on whether you are updating a computer that hosts a default or named instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="to-rename-a-computer-that-hosts-a-stand-alone-instance-of-ssnoversion"></a><span data-ttu-id="6527c-130">Per rinominare un computer che ospita un'istanza autonoma di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6527c-130">To rename a computer that hosts a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="6527c-131">Per un computer rinominato che ospita un'istanza predefinita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], eseguire le procedure riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="6527c-131">For a renamed computer that hosts a default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], run the following procedures:</span></span>  
  
    ```  
    sp_dropserver <old_name>;  
    GO  
    sp_addserver <new_name>, local;  
    GO  
    ```  
  
     <span data-ttu-id="6527c-132">Riavviare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6527c-132">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="6527c-133">Per un computer rinominato che ospita un'istanza denominata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], eseguire le procedure riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="6527c-133">For a renamed computer that hosts a named instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], run the following procedures:</span></span>  
  
    ```  
    sp_dropserver <old_name\instancename>;  
    GO  
    sp_addserver <new_name\instancename>, local;  
    GO  
    ```  
  
     <span data-ttu-id="6527c-134">Riavviare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6527c-134">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="after-the-renaming-operation"></a><span data-ttu-id="6527c-135">Al termine dell'operazione di ridenominazione</span><span class="sxs-lookup"><span data-stu-id="6527c-135">After the Renaming Operation</span></span>  
 <span data-ttu-id="6527c-136">In seguito alla ridenominazione di un computer, tutte le connessioni che utilizzavano il nome precedente devono essere eseguite utilizzando il nuovo nome.</span><span class="sxs-lookup"><span data-stu-id="6527c-136">After a computer has been renamed, any connections that used the old computer name must connect by using the new name.</span></span>  
  
#### <a name="to-verify-that-the-renaming-operation-has-completed-successfully"></a><span data-ttu-id="6527c-137">Per verificare il corretto completamento dell'operazione di ridenominazione</span><span class="sxs-lookup"><span data-stu-id="6527c-137">To verify that the renaming operation has completed successfully</span></span>  
  
-   <span data-ttu-id="6527c-138">Selezionare le informazioni da @@SERVERNAME o sys.servers.</span><span class="sxs-lookup"><span data-stu-id="6527c-138">Select information from either @@SERVERNAME or sys.servers.</span></span> <span data-ttu-id="6527c-139">La funzione @@SERVERNAME restituirà il nuovo nome e la tabella sys.servers includerà il nuovo nome.</span><span class="sxs-lookup"><span data-stu-id="6527c-139">The @@SERVERNAME function will return the new name, and the sys.servers table will show the new name.</span></span> <span data-ttu-id="6527c-140">L'esempio di seguito mostra l'uso di @@SERVERNAME .</span><span class="sxs-lookup"><span data-stu-id="6527c-140">The following example shows the use of @@SERVERNAME.</span></span>  
  
    ```  
    SELECT @@SERVERNAME AS 'Server Name';  
    ```  
  
## <a name="additional-considerations"></a><span data-ttu-id="6527c-141">Ulteriori considerazioni</span><span class="sxs-lookup"><span data-stu-id="6527c-141">Additional Considerations</span></span>  
 <span data-ttu-id="6527c-142">**Account di accesso remoto** : se il computer dispone di account di accesso remoto, l'esecuzione di **sp_dropserver** può generare un errore simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="6527c-142">**Remote Logins** - If the computer has any remote logins, running **sp_dropserver** might generate an error similar to the following:</span></span>  
  
 `Server: Msg 15190, Level 16, State 1, Procedure sp_dropserver, Line 44 There are still remote logins for the server 'SERVER1'.`  
  
 <span data-ttu-id="6527c-143">Per risolvere l'errore, è necessario eliminare gli account di accesso remoto per tale server.</span><span class="sxs-lookup"><span data-stu-id="6527c-143">To resolve the error, you must drop remote logins for this server.</span></span>  
  
#### <a name="to-drop-remote-logins"></a><span data-ttu-id="6527c-144">Per eliminare gli account di accesso remoto</span><span class="sxs-lookup"><span data-stu-id="6527c-144">To drop remote logins</span></span>  
  
-   <span data-ttu-id="6527c-145">Per un'istanza predefinita, eseguire le procedure seguenti:</span><span class="sxs-lookup"><span data-stu-id="6527c-145">For a default instance, run the following procedure:</span></span>  
  
    ```  
    sp_dropremotelogin old_name;  
    GO  
    ```  
  
-   <span data-ttu-id="6527c-146">Per un'istanza denominata, eseguire le procedure seguenti:</span><span class="sxs-lookup"><span data-stu-id="6527c-146">For a named instance, run the following procedure:</span></span>  
  
    ```  
    sp_dropremotelogin old_name\instancename;  
    GO  
    ```  
  
 <span data-ttu-id="6527c-147">**Configurazioni del server collegato** : le configurazioni del server collegato saranno interessate dall'operazione di ridenominazione del computer.</span><span class="sxs-lookup"><span data-stu-id="6527c-147">**Linked Server Configurations** - Linked server configurations will be affected by the computer renaming operation.</span></span> <span data-ttu-id="6527c-148">Utilizzare `sp_addlinkedserver` o `sp_setnetname` per aggiornare i riferimenti del nome del computer.</span><span class="sxs-lookup"><span data-stu-id="6527c-148">Use `sp_addlinkedserver` or `sp_setnetname` to update computer name references.</span></span> <span data-ttu-id="6527c-149">Per altre informazioni, vedere [sp_addlinkedserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql) oo [sp_setnetname &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-setnetname-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6527c-149">For more information, see the [sp_addlinkedserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql) or [sp_setnetname &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-setnetname-transact-sql).</span></span>  
  
 <span data-ttu-id="6527c-150">**Nomi alias per i client**: gli alias per i client che usano named pipe verranno interessati dall'operazione di ridenominazione del computer.</span><span class="sxs-lookup"><span data-stu-id="6527c-150">**Client Alias Names** - Client aliases that use named pipes will be affected by the computer renaming operation.</span></span> <span data-ttu-id="6527c-151">Se ad esempio è stato creato un alias "PROD_SRVR" per puntare a SRVR1 e viene utilizzato il protocollo Named Pipes, il nome pipe sarà simile al seguente: `\\SRVR1\pipe\sql\query`.</span><span class="sxs-lookup"><span data-stu-id="6527c-151">For example, if an alias "PROD_SRVR" was created to point to SRVR1 and uses the named pipes protocol, the pipe name will look like `\\SRVR1\pipe\sql\query`.</span></span> <span data-ttu-id="6527c-152">Dopo la ridenominazione del computer, il percorso di named pipe non sarà più valido.</span><span class="sxs-lookup"><span data-stu-id="6527c-152">After the computer is renamed, the path of the named pipe will no longer be valid and.</span></span> <span data-ttu-id="6527c-153">Per altre informazioni sulle named pipe, vedere l'argomento [Creazione di una stringa di connessione valida tramite named pipe](https://go.microsoft.com/fwlink/?LinkId=111063).</span><span class="sxs-lookup"><span data-stu-id="6527c-153">For more information about named pipes, see the [Creating a Valid Connection String Using Named Pipes](https://go.microsoft.com/fwlink/?LinkId=111063).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6527c-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6527c-154">See Also</span></span>  
 [<span data-ttu-id="6527c-155">Installare SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="6527c-155">Install SQL Server 2014</span></span>](../../database-engine/install-windows/install-sql-server.md)  
  
  
