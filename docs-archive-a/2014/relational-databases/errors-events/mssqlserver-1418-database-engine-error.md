---
title: MSSQLSERVER_1418 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1418 (Database Engine error)
ms.assetid: 6e9c7241-0201-44e0-9f8b-b3c4e293f0f6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1fcac03f044aacce5e907824862eb589c97a07d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718204"
---
# <a name="mssqlserver_1418"></a><span data-ttu-id="1938d-102">MSSQLSERVER_1418</span><span class="sxs-lookup"><span data-stu-id="1938d-102">MSSQLSERVER_1418</span></span>
    
## <a name="details"></a><span data-ttu-id="1938d-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="1938d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1938d-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="1938d-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="1938d-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="1938d-105">Event ID</span></span>|<span data-ttu-id="1938d-106">1418</span><span class="sxs-lookup"><span data-stu-id="1938d-106">1418</span></span>|  
|<span data-ttu-id="1938d-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="1938d-107">Event Source</span></span>|<span data-ttu-id="1938d-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1938d-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1938d-109">Componente</span><span class="sxs-lookup"><span data-stu-id="1938d-109">Component</span></span>|<span data-ttu-id="1938d-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1938d-110">SQLEngine</span></span>|  
|<span data-ttu-id="1938d-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="1938d-111">Symbolic Name</span></span>|<span data-ttu-id="1938d-112">DBM_PARTNERNOTFOUND</span><span class="sxs-lookup"><span data-stu-id="1938d-112">DBM_PARTNERNOTFOUND</span></span>|  
|<span data-ttu-id="1938d-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="1938d-113">Message Text</span></span>|<span data-ttu-id="1938d-114">L'indirizzo di rete del server "%.\*ls" non è raggiungibile o non esiste.</span><span class="sxs-lookup"><span data-stu-id="1938d-114">The server network address "%.\*ls" can not be reached or does not exist.</span></span> <span data-ttu-id="1938d-115">Controllare il nome dell'indirizzo di rete e verificare che le porte degli endpoint locale e remoto siano operative.</span><span class="sxs-lookup"><span data-stu-id="1938d-115">Check the network address name and that the ports for the local and remote endpoints are operational.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1938d-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="1938d-116">Explanation</span></span>  
 <span data-ttu-id="1938d-117">L'endpoint di rete del server non ha risposto perché l'indirizzo di rete del server specificato non è raggiungibile o non esiste.</span><span class="sxs-lookup"><span data-stu-id="1938d-117">The server network endpoint did not respond because the specified server network address cannot be reached or does not exist.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1938d-118">Per impostazione predefinita, tutte le porte vengono bloccate dal sistema operativo [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1938d-118">By default, [!INCLUDE[msCoName](../../includes/msconame-md.md)] operating system blocks all ports.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1938d-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="1938d-119">User Action</span></span>  
 <span data-ttu-id="1938d-120">Verificare il nome dell'indirizzo di rete ed eseguire nuovamente il comando.</span><span class="sxs-lookup"><span data-stu-id="1938d-120">Verify the network address name and reissue the command.</span></span>  
  
 <span data-ttu-id="1938d-121">È possibile che sia necessario intervenire su entrambi i partner.</span><span class="sxs-lookup"><span data-stu-id="1938d-121">Corrective action might be required on both partners.</span></span> <span data-ttu-id="1938d-122">Se ad esempio questo messaggio viene generato mentre si sta tentando di eseguire l'istruzione SET PARTNER nell'istanza del server principale, il messaggio potrebbe implicare che è necessario intervenire solo nell'istanza del server mirror.</span><span class="sxs-lookup"><span data-stu-id="1938d-122">For example, if this message is raised when you are trying to run SET PARTNER on the principal server instance, the message might imply that you only have to take corrective action on the mirror server instance.</span></span> <span data-ttu-id="1938d-123">È possibile tuttavia che l'intervento sia richiesto su entrambi i partner.</span><span class="sxs-lookup"><span data-stu-id="1938d-123">However, corrective actions might be required on both partners.</span></span>  
  
### <a name="additional-corrective-actions"></a><span data-ttu-id="1938d-124">Interventi di correzione aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="1938d-124">Additional Corrective Actions</span></span>  
  
-   <span data-ttu-id="1938d-125">Verificare che il database mirror sia pronto per il mirroring.</span><span class="sxs-lookup"><span data-stu-id="1938d-125">Make sure that the mirror database is ready for mirroring.</span></span>  
  
-   <span data-ttu-id="1938d-126">Verificare che il nome e la porta dell'istanza del server mirror siano corretti.</span><span class="sxs-lookup"><span data-stu-id="1938d-126">Make sure that the name and port of the mirror server instance are correct.</span></span>  
  
-   <span data-ttu-id="1938d-127">Verificare che l'istanza del server mirror di destinazione non sia protetta da un firewall.</span><span class="sxs-lookup"><span data-stu-id="1938d-127">Make sure that the destination mirror server instance is not behind a firewall.</span></span>  
  
-   <span data-ttu-id="1938d-128">Verificare che l'istanza del server principale non sia protetta da un firewall.</span><span class="sxs-lookup"><span data-stu-id="1938d-128">Make sure that the principal server instance is not behind a firewall.</span></span>  
  
-   <span data-ttu-id="1938d-129">Verificare che gli endpoint siano stati avviati sui partner usando la colonna **state** o **state_desc** della vista del catalogo **sys.database_mirroring_endpoints**.</span><span class="sxs-lookup"><span data-stu-id="1938d-129">Verify that the endpoints are started on the partners by using the **state** or **state_desc** column the of the **sys.database_mirroring_endpoints** catalog view.</span></span> <span data-ttu-id="1938d-130">Se uno degli endpoint non è stato avviato, eseguire un'istruzione ALTER ENDPOINT per avviarlo.</span><span class="sxs-lookup"><span data-stu-id="1938d-130">If either endpoint is not started, execute an ALTER ENDPOINT statement to start it.</span></span>  
  
-   <span data-ttu-id="1938d-131">Verificare che l'istanza del server principale sia in attesa sulla porta assegnata al relativo endpoint del mirroring del database e che l'istanza del server mirror sia in attesa sulla relativa porta.</span><span class="sxs-lookup"><span data-stu-id="1938d-131">Make sure that the principal server instance is listening on the port assigned to its database mirroring endpoint and that and the mirror server instance is listening on its port.</span></span> <span data-ttu-id="1938d-132">Per ulteriori informazioni, vedere "Verifica della disponibilità delle porte" di seguito in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="1938d-132">For more information, see "Verifying Port Availability," later in this topic.</span></span> <span data-ttu-id="1938d-133">Se il partner non è in attesa sulla porta assegnata, modificare l'impostazione dell'endpoint del mirroring del database affinché sia in attesa su una porta diversa.</span><span class="sxs-lookup"><span data-stu-id="1938d-133">If a partner is not listening on its assigned port, modify the database mirroring endpoint to listen on a different port.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="1938d-134">Impostazioni di sicurezza configurate in modo non corretto possono generare un messaggio di errore generico relativo all'impostazione.</span><span class="sxs-lookup"><span data-stu-id="1938d-134">Improperly configured security can cause a general setup error message.</span></span> <span data-ttu-id="1938d-135">L'istanza del server rimuove in genere la richiesta di connessione non valida senza alcuna risposta.</span><span class="sxs-lookup"><span data-stu-id="1938d-135">Typically, the server instance drops the bad connection request without responding.</span></span> <span data-ttu-id="1938d-136">Le cause di un errore di configurazione o sicurezza, dal punto di vista del chiamante, possono essere molteplici, ad esempio un database mirror inesistente o in uno stato non valido, autorizzazioni non corrette e così via.</span><span class="sxs-lookup"><span data-stu-id="1938d-136">To the caller, a security-configuration error could appear to have occurred for a variety of other reasons, such as the mirror database in a bad state or does not exist, incorrect permissions, and so on.</span></span>  
  
### <a name="using-the-error-log-file-for-diagnosis"></a><span data-ttu-id="1938d-137">Utilizzo del file del log degli errori per la diagnosi</span><span class="sxs-lookup"><span data-stu-id="1938d-137">Using the Error Log File for Diagnosis</span></span>  
 <span data-ttu-id="1938d-138">In alcuni casi, per eseguire analisi approfondite sono disponibili solo i file del log degli errori.</span><span class="sxs-lookup"><span data-stu-id="1938d-138">In some cases, only error log files are available for investigation.</span></span> <span data-ttu-id="1938d-139">In tali circostanze, verificare se il log degli errori contiene il messaggio di errore 26023 per la porta TCP dell'endpoint del mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="1938d-139">In these cases, determine whether the error log contains error message 26023 for the TCP port of the database mirroring endpoint.</span></span> <span data-ttu-id="1938d-140">Questo errore, con livello di gravità 16, può indicare che l'endpoint del mirroring del database non è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="1938d-140">This error, which is severity 16, might indicate that the database mirroring endpoint is not started.</span></span> <span data-ttu-id="1938d-141">È possibile che il messaggio venga visualizzato anche se nella vista del catalogo **sys.database_mirroring_endpoints** l'endpoint risulta avviato.</span><span class="sxs-lookup"><span data-stu-id="1938d-141">This message can occur even if **sys.database_mirroring_endpoints** shows the endpoint state as started.</span></span>  
  
 <span data-ttu-id="1938d-142">Dopo aver risolto tutti i problemi riscontrati, eseguire nuovamente l'istruzione ALTER DATABASE *nome_database* SET PARTNER nel server principale.</span><span class="sxs-lookup"><span data-stu-id="1938d-142">After resolving any issues that you encounter, rerun the ALTER DATABASE *database_name* SET PARTNER statement on the principal server.</span></span>  
  
### <a name="verifying-port-availability"></a><span data-ttu-id="1938d-143">Verifica della disponibilità delle porte</span><span class="sxs-lookup"><span data-stu-id="1938d-143">Verifying Port Availability</span></span>  
 <span data-ttu-id="1938d-144">Quando si configura la rete per una sessione di mirroring del database, verificare che l'endpoint del mirroring del database di ogni istanza del server venga utilizzato solo dal processo di mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="1938d-144">When you are configuring the network for a database mirroring session, make sure the database mirroring endpoint of each server instance is used by only the database mirroring process.</span></span> <span data-ttu-id="1938d-145">Se un altro processo è in attesa sulla porta assegnata a un endpoint del mirroring del database, i processi di mirroring del database delle altre istanze del server non potranno stabilire una connessione all'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1938d-145">If another process is listening on the port assigned to a database mirroring endpoint, the database mirroring processes of the other server instances cannot connect to the endpoint.</span></span>  
  
 <span data-ttu-id="1938d-146">Per visualizzare tutte le porte su cui è in attesa un server Windows, usare l'utilità della riga di comando **netstat**.</span><span class="sxs-lookup"><span data-stu-id="1938d-146">To display all the ports on which a Windows-based server is listening, use the **netstat** command-prompt utility.</span></span> <span data-ttu-id="1938d-147">La sintassi di **netstat** dipende dalla versione del sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="1938d-147">The syntax for **netstat** depends on the version of the Windows operating system.</span></span> <span data-ttu-id="1938d-148">Per ulteriori informazioni, consultare la documentazione del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1938d-148">For more information, see the operating system documentation.</span></span>  
  
#### <a name="windows-server-2003-service-pack-1-sp1"></a><span data-ttu-id="1938d-149">Windows Server 2003 Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="1938d-149">Windows Server 2003 Service Pack 1 (SP1)</span></span>  
 <span data-ttu-id="1938d-150">Per elencare le porte di attesa e i processi che mantengono aperte tali porte, digitare il comando seguente al prompt dei comandi di Windows:</span><span class="sxs-lookup"><span data-stu-id="1938d-150">To list listening ports and the processes that have those ports opened, enter the following command at the Windows command prompt:</span></span>  
  
 <span data-ttu-id="1938d-151">**netstat -abn**</span><span class="sxs-lookup"><span data-stu-id="1938d-151">**netstat -abn**</span></span>  
  
#### <a name="windows-server-2003-pre-sp1"></a><span data-ttu-id="1938d-152">Windows Server 2003 (versioni precedenti a SP1)</span><span class="sxs-lookup"><span data-stu-id="1938d-152">Windows Server 2003 (pre-SP1)</span></span>  
 <span data-ttu-id="1938d-153">Per identificare le porte di attesa e i processi che mantengono aperte tali porte, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="1938d-153">To identify the listening ports and the processes that have those ports opened, follow these steps:</span></span>  
  
1.  <span data-ttu-id="1938d-154">Ottenere l'ID del processo.</span><span class="sxs-lookup"><span data-stu-id="1938d-154">Obtain the process ID.</span></span>  
  
     <span data-ttu-id="1938d-155">Per individuare l'ID del processo di un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], connettersi a tale istanza e utilizzare l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente:</span><span class="sxs-lookup"><span data-stu-id="1938d-155">To learn the process ID of an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], connect to that instance and use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    SELECT SERVERPROPERTY('ProcessID')   
    ```  
  
     <span data-ttu-id="1938d-156">Per ulteriori informazioni, vedere "SERVERPROPERTY (Transact-SQL)" nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1938d-156">For more information, see "SERVERPROPERTY (Transact-SQL)" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="1938d-157">Associare l'ID del processo all'output del comando **netstat** seguente:</span><span class="sxs-lookup"><span data-stu-id="1938d-157">Match the process ID with the output of the following **netstat** command:</span></span>  
  
     <span data-ttu-id="1938d-158">**netstat -ano**</span><span class="sxs-lookup"><span data-stu-id="1938d-158">**netstat -ano**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1938d-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1938d-159">See Also</span></span>  
 <span data-ttu-id="1938d-160">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1938d-160">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="1938d-161">[Endpoint del mirroring del database &#40;SQL Server&#41;](../../database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1938d-161">[The Database Mirroring Endpoint &#40;SQL Server&#41;](../../database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="1938d-162">[Preparazione di un database mirror per il mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1938d-162">[Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="1938d-163">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1938d-163">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span></span>  
 <span data-ttu-id="1938d-164">[Specificare un indirizzo di rete del server &#40;Mirroring del database&#41;](../../database-engine/database-mirroring/specify-a-server-network-address-database-mirroring.md) </span><span class="sxs-lookup"><span data-stu-id="1938d-164">[Specify a Server Network Address &#40;Database Mirroring&#41;](../../database-engine/database-mirroring/specify-a-server-network-address-database-mirroring.md) </span></span>  
 <span data-ttu-id="1938d-165">[sys.database_mirroring_endpoints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1938d-165">[sys.database_mirroring_endpoints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql) </span></span>  
 [<span data-ttu-id="1938d-166">Risolvere i problemi relativi alla configurazione del mirroring del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1938d-166">Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/troubleshoot-database-mirroring-configuration-sql-server.md)  
  
  
