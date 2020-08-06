---
title: Agente di lettura coda repliche | Microsoft Docs
ms.custom: ''
ms.date: 10/29/2018
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- agents [SQL Server replication], Queue Reader Agent
- command prompt [SQL Server replication]
- Queue Reader Agent, parameter reference
- Queue Reader Agent, executables
ms.assetid: 8e227793-11f6-47c6-99dc-ffc282f5d4bf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 854c425db3fbaa346dab5eb2c41bd58cf03f65c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624660"
---
# <a name="replication-queue-reader-agent"></a><span data-ttu-id="6522d-102">Agente di lettura coda repliche</span><span class="sxs-lookup"><span data-stu-id="6522d-102">Replication Queue Reader Agent</span></span>
  <span data-ttu-id="6522d-103">L'agente di lettura coda repliche è un eseguibile che consente di leggere i messaggi archiviati in una coda [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Message Queue e di applicare tali messaggi al server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="6522d-103">The Replication Queue Reader Agent is an executable that reads messages stored in a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] queue or a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Message Queue and then applies those messages to the Publisher.</span></span> <span data-ttu-id="6522d-104">L'agente di lettura coda viene utilizzato con le pubblicazioni snapshot e transazionali che consentono l'aggiornamento in coda.</span><span class="sxs-lookup"><span data-stu-id="6522d-104">Queue Reader Agent is used with snapshot and transactional publications that allow queued updating.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6522d-105">I parametri possono essere specificati in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="6522d-105">Parameters can be specified in any order.</span></span> <span data-ttu-id="6522d-106">Quando i parametri facoltativi non vengono specificati, vengono utilizzati i valori predefiniti basati sul profilo agente predefinito.</span><span class="sxs-lookup"><span data-stu-id="6522d-106">When optional parameters are not specified, predefined values based on the default agent profile are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6522d-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6522d-107">Syntax</span></span>  
  
```  
  
      qrdrsvc [-?]  
[-Continuous]  
[-DefinitionFiledefinition_file]  
[-Distributorserver_name[\instance_name]]  
[-DistributionDBdistribution_database]  
[-DistributorLogindistributor_login]  
[-DistributorPassworddistributor_password]  
[-DistributorSecurityMode [0|1]]  
[-EncryptionLevel [0|1|2]]  
[-HistoryVerboseLevel [0|1|2|3]]  
[-LoginTimeOutlogin_time_out_seconds]  
[-Outputoutput_path_and_file_name]  
[-OutputVerboseLevel [0|1|2]]  
[-PollingIntervalpolling_interval]  
[-PublisherFailoverPartnerserver_name[\instance_name] ]  
[-ProfileNameagent_profile_name]  
[-QueryTimeOutquery_time_out_seconds]  
[-ResolverState [1|2|3]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="6522d-108">Argomenti</span><span class="sxs-lookup"><span data-stu-id="6522d-108">Arguments</span></span>  
 <span data-ttu-id="6522d-109">**-?**</span><span class="sxs-lookup"><span data-stu-id="6522d-109">**-?**</span></span>  
 <span data-ttu-id="6522d-110">Visualizza le informazioni sull'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="6522d-110">Displays usage information.</span></span>  
  
 <span data-ttu-id="6522d-111">**-Continuous**</span><span class="sxs-lookup"><span data-stu-id="6522d-111">**-Continuous**</span></span>  
 <span data-ttu-id="6522d-112">Specifica se l'agente tenta di elaborare continuamente le transazioni in coda.</span><span class="sxs-lookup"><span data-stu-id="6522d-112">Specifies whether the agent attempts to process queued transactions continuously.</span></span> <span data-ttu-id="6522d-113">Se è specificato, l'agente continua l'esecuzione anche se non vi sono transazioni in coda in sospeso in alcuno dei Sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="6522d-113">If specified, the agent continues execution even if there are no queued transactions pending from any of the subscribers.</span></span>  
  
 <span data-ttu-id="6522d-114">**-DefinitionFile** _def_path_and_file_name_</span><span class="sxs-lookup"><span data-stu-id="6522d-114">**-DefinitionFile** _def_path_and_file_name_</span></span>  
 <span data-ttu-id="6522d-115">Percorso del file di definizione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="6522d-115">Is the path of the agent definition file.</span></span> <span data-ttu-id="6522d-116">Un file di definizione dell'agente contiene argomenti della riga di comando per l'agente.</span><span class="sxs-lookup"><span data-stu-id="6522d-116">An agent definition file contains command-line arguments for the agent.</span></span> <span data-ttu-id="6522d-117">Il contenuto del file viene analizzato come file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="6522d-117">The content of the file is parsed as an executable file.</span></span> <span data-ttu-id="6522d-118">Utilizzare virgolette doppie (") per specificare valori dell'argomento contenenti caratteri arbitrari.</span><span class="sxs-lookup"><span data-stu-id="6522d-118">Use double quotation marks (") to specify argument values containing arbitrary characters.</span></span>  
  
 <span data-ttu-id="6522d-119">**-Distributor** _server_name_[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="6522d-119">**-Distributor** _server_name_[**\\**_instance_name_]</span></span>  
 <span data-ttu-id="6522d-120">Nome del database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6522d-120">Is the Distributor name.</span></span> <span data-ttu-id="6522d-121">Specificare *server_name* per l'istanza predefinita di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in tale server.</span><span class="sxs-lookup"><span data-stu-id="6522d-121">Specify *server_name* for the default instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on that server.</span></span> <span data-ttu-id="6522d-122">Specificare *server_name*\\*instance_name* per un'istanza denominata di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in tale server.</span><span class="sxs-lookup"><span data-stu-id="6522d-122">Specify *server_name*\\*instance_name* for a named instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on that server.</span></span> <span data-ttu-id="6522d-123">Se non specificato, per impostazione predefinita viene utilizzato il nome dell'istanza predefinita di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="6522d-123">If not specified, the name defaults to the name of the default instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on the local computer.</span></span>  
  
 <span data-ttu-id="6522d-124">**-DistributionDB** _distribution_database_</span><span class="sxs-lookup"><span data-stu-id="6522d-124">**-DistributionDB** _distribution_database_</span></span>  
 <span data-ttu-id="6522d-125">Database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6522d-125">Is the distribution database.</span></span>  
  
 <span data-ttu-id="6522d-126">**-DistributorLogin** _distributor_login_</span><span class="sxs-lookup"><span data-stu-id="6522d-126">**-DistributorLogin** _distributor_login_</span></span>  
 <span data-ttu-id="6522d-127">Nome dell'account di accesso del database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6522d-127">Is the Distributor login name.</span></span>  
  
 <span data-ttu-id="6522d-128">**-DistributorPassword** _distributor_password_</span><span class="sxs-lookup"><span data-stu-id="6522d-128">**-DistributorPassword** _distributor_password_</span></span>  
 <span data-ttu-id="6522d-129">Password del database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6522d-129">Is the Distributor password.</span></span>  
  
 <span data-ttu-id="6522d-130">**-DistributorSecurityMode** [ **0**| **1**]</span><span class="sxs-lookup"><span data-stu-id="6522d-130">**-DistributorSecurityMode** [ **0**| **1**]</span></span>  
 <span data-ttu-id="6522d-131">Specifica la modalità di sicurezza del database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6522d-131">Specifies the security mode of the Distributor.</span></span> <span data-ttu-id="6522d-132">Un valore **0** indica la modalità di autenticazione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (impostazione predefinita), mentre un valore **1** indica la modalità di autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="6522d-132">A value of **0** indicates [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication Mode (default), and a value of **1** indicates Windows Authentication Mode.</span></span>  
  
 <span data-ttu-id="6522d-133">**-EncryptionLevel** [ **0** | **1** | **2** ]</span><span class="sxs-lookup"><span data-stu-id="6522d-133">**-EncryptionLevel** [ **0** | **1** | **2** ]</span></span>  
 <span data-ttu-id="6522d-134">Livello di crittografia SSL (Secure Sockets Layer) utilizzato dall'agente di lettura coda quando vengono stabilite le connessioni.</span><span class="sxs-lookup"><span data-stu-id="6522d-134">Is the level of Secure Sockets Layer (SSL) encryption used by the Queue Reader Agent when making connections.</span></span>  
  
|<span data-ttu-id="6522d-135">Valore di EncryptionLevel</span><span class="sxs-lookup"><span data-stu-id="6522d-135">EncryptionLevel value</span></span>|<span data-ttu-id="6522d-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6522d-136">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="6522d-137">**0**</span><span class="sxs-lookup"><span data-stu-id="6522d-137">**0**</span></span>|<span data-ttu-id="6522d-138">Specifica che SSL non viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="6522d-138">Specifies that SSL is not used.</span></span>|  
|<span data-ttu-id="6522d-139">**1**</span><span class="sxs-lookup"><span data-stu-id="6522d-139">**1**</span></span>|<span data-ttu-id="6522d-140">Specifica che SSL viene utilizzato, ma l'agente non verifica che il certificato server SSL sia firmato da un'autorità emittente attendibile.</span><span class="sxs-lookup"><span data-stu-id="6522d-140">Specifies that SSL is used, but the agent does not verify that the SSL server certificate is signed by a trusted issuer.</span></span>|  
|<span data-ttu-id="6522d-141">**2**</span><span class="sxs-lookup"><span data-stu-id="6522d-141">**2**</span></span>|<span data-ttu-id="6522d-142">Specifica che SSL viene utilizzato e che il certificato viene verificato.</span><span class="sxs-lookup"><span data-stu-id="6522d-142">Specifies that SSL is used, and that the certificate is verified.</span></span>|  

 > [!NOTE]  
 >  <span data-ttu-id="6522d-143">Un certificato SSL valido è definito con un nome di dominio completo del Server SQL.</span><span class="sxs-lookup"><span data-stu-id="6522d-143">A valid SSL certificate is defined with a fully qualified domain name of the SQL Server.</span></span> <span data-ttu-id="6522d-144">Affinché l'agente possa connettersi correttamente quando si imposta - EncryptionLevel su 2, creare un alias nel Server SQL locale.</span><span class="sxs-lookup"><span data-stu-id="6522d-144">In order for the agent to connect successfully when setting -EncryptionLevel to 2, create an alias on the local SQL Server.</span></span> <span data-ttu-id="6522d-145">Il parametro 'Nome alias' deve corrispondere al nome del server e il parametro 'Server' deve essere impostato sul nome completo dell'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6522d-145">The 'Alias Name' parameter should be the server name and the 'Server' parameter should be set to the fully qualified name of the SQL Server.</span></span>
  
 <span data-ttu-id="6522d-146">Per ulteriori informazioni, vedere [replica di SQL Server sicurezza](../security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="6522d-146">For more information, see [SQL Server Replication Security](../security/view-and-modify-replication-security-settings.md).</span></span>  
  
 <span data-ttu-id="6522d-147">**-HistoryVerboseLevel** [ **0**| **1**| **2**| **3**]</span><span class="sxs-lookup"><span data-stu-id="6522d-147">**-HistoryVerboseLevel** [ **0**| **1**| **2**| **3**]</span></span>  
 <span data-ttu-id="6522d-148">Specifica la quantità di cronologia registrata durante un'operazione dell'agente di lettura coda.</span><span class="sxs-lookup"><span data-stu-id="6522d-148">Specifies the amount of history logged during a queue reader operation.</span></span> <span data-ttu-id="6522d-149">Per ridurre al minimo l'effetto della registrazione della cronologia sulle prestazioni, selezionare **1**.</span><span class="sxs-lookup"><span data-stu-id="6522d-149">You can minimize the effect of history logging on performance by selecting **1**.</span></span>  
  
|<span data-ttu-id="6522d-150">Valore di HistoryVerboseLevel</span><span class="sxs-lookup"><span data-stu-id="6522d-150">HistoryVerboseLevel value</span></span>|<span data-ttu-id="6522d-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6522d-151">Description</span></span>|  
|-------------------------------|-----------------|  
|<span data-ttu-id="6522d-152">**0**</span><span class="sxs-lookup"><span data-stu-id="6522d-152">**0**</span></span>|<span data-ttu-id="6522d-153">Nessuna registrazione della cronologia (opzione non consigliata).</span><span class="sxs-lookup"><span data-stu-id="6522d-153">No history logging (not recommended).</span></span>|  
|<span data-ttu-id="6522d-154">**1**</span><span class="sxs-lookup"><span data-stu-id="6522d-154">**1**</span></span>|<span data-ttu-id="6522d-155">Valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="6522d-155">Default.</span></span> <span data-ttu-id="6522d-156">Aggiorna sempre un messaggio di cronologia precedente con lo stesso stato (avvio, avanzamento, esito positivo e così via).</span><span class="sxs-lookup"><span data-stu-id="6522d-156">Always update a previous history message of the same status (startup, progress, success, and so on).</span></span> <span data-ttu-id="6522d-157">Se non è presente un record precedente con lo stesso stato, inserisce un nuovo record.</span><span class="sxs-lookup"><span data-stu-id="6522d-157">If no previous record with the same status exists, insert a new record.</span></span>|  
|<span data-ttu-id="6522d-158">**2**</span><span class="sxs-lookup"><span data-stu-id="6522d-158">**2**</span></span>|<span data-ttu-id="6522d-159">Inserisce nuovi record della cronologia, inclusi record per messaggi inattivi o messaggi di processo con esecuzione prolungata.</span><span class="sxs-lookup"><span data-stu-id="6522d-159">Insert new history records, including idle messages or long-running job messages.</span></span>|  
|<span data-ttu-id="6522d-160">**3**</span><span class="sxs-lookup"><span data-stu-id="6522d-160">**3**</span></span>|<span data-ttu-id="6522d-161">Inserisce nuovi record della cronologia che includono informazioni aggiuntive che potrebbero essere utili per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="6522d-161">Insert new history records that include additional details that may be useful for troubleshooting.</span></span>|  
  
 <span data-ttu-id="6522d-162">**-LoginTimeOut** _login_time_out_seconds_</span><span class="sxs-lookup"><span data-stu-id="6522d-162">**-LoginTimeOut** _login_time_out_seconds_</span></span>  
 <span data-ttu-id="6522d-163">Numero di secondi prima del timeout di accesso. Il valore predefinito è 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="6522d-163">Is the number of seconds before the login times out. The default is 15 seconds.</span></span>  
  
 <span data-ttu-id="6522d-164">**-Output** _output_path_and_file_name_</span><span class="sxs-lookup"><span data-stu-id="6522d-164">**-Output** _output_path_and_file_name_</span></span>  
 <span data-ttu-id="6522d-165">Percorso del file di output dell'agente.</span><span class="sxs-lookup"><span data-stu-id="6522d-165">Is the path of the agent output file.</span></span> <span data-ttu-id="6522d-166">Se non viene specificato il nome file, l'output viene inviato alla console.</span><span class="sxs-lookup"><span data-stu-id="6522d-166">If the file name is not provided, the output is sent to the console.</span></span> <span data-ttu-id="6522d-167">Se il nome file specificato esiste già, l'output viene aggiunto al file.</span><span class="sxs-lookup"><span data-stu-id="6522d-167">If the specified file name exists, the output is appended to the file.</span></span>  
  
 <span data-ttu-id="6522d-168">**-OutputVerboseLevel** [ **0**| **1**| **2**]</span><span class="sxs-lookup"><span data-stu-id="6522d-168">**-OutputVerboseLevel** [ **0**| **1**| **2**]</span></span>  
 <span data-ttu-id="6522d-169">Specifica se l'output deve essere dettagliato.</span><span class="sxs-lookup"><span data-stu-id="6522d-169">Specifies whether the output should be verbose.</span></span> <span data-ttu-id="6522d-170">Se il livello di dettaglio è **0**, vengono stampati solo i messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="6522d-170">If the verbose level is **0**, only error messages are printed.</span></span> <span data-ttu-id="6522d-171">Se il livello di dettaglio è **1**, vengono stampati tutti i messaggi di report di stato.</span><span class="sxs-lookup"><span data-stu-id="6522d-171">If the verbose level is **1**, all the progress report messages are printed.</span></span> <span data-ttu-id="6522d-172">Se il livello di dettaglio è **2** (impostazione predefinita), vengono stampati tutti i messaggi di errore e i messaggi di report di stato. Questa opzione è utile per l'esecuzione del debug.</span><span class="sxs-lookup"><span data-stu-id="6522d-172">If the verbose level is **2** (default), all error messages and progress report messages are printed, which is useful for debugging.</span></span>  
  
 <span data-ttu-id="6522d-173">**-PollingInterval** _polling_interval_</span><span class="sxs-lookup"><span data-stu-id="6522d-173">**-PollingInterval** _polling_interval_</span></span>  
 <span data-ttu-id="6522d-174">Rilevante solo per sottoscrizioni aggiornabili che utilizzano code basate su [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6522d-174">Is relevant only for updating subscriptions that use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] based queues.</span></span> <span data-ttu-id="6522d-175">Specifica la frequenza, in secondi, di polling della coda [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] per le transazioni in coda in sospeso.</span><span class="sxs-lookup"><span data-stu-id="6522d-175">Specifies how often, in seconds, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] queue is polled for pending queued transactions.</span></span> <span data-ttu-id="6522d-176">Il valore può essere compreso tra 0 e 240 secondi.</span><span class="sxs-lookup"><span data-stu-id="6522d-176">The value can be between 0 and 240 seconds.</span></span> <span data-ttu-id="6522d-177">Il valore predefinito è 5 secondi.</span><span class="sxs-lookup"><span data-stu-id="6522d-177">The default is 5 seconds.</span></span>  
  
 <span data-ttu-id="6522d-178">**-PublisherFailoverPartner** _server_name_[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="6522d-178">**-PublisherFailoverPartner** _server_name_[**\\**_instance_name_]</span></span>  
 <span data-ttu-id="6522d-179">Specifica l'istanza del partner di failover di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] che partecipa in una sessione di mirroring del database con il database di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="6522d-179">Specifies the failover partner instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] participating in a database mirroring session with the publication database.</span></span> <span data-ttu-id="6522d-180">Per altre informazioni, vedere [Mirroring e replica del database &#40;SQL Server&#41;](../../../database-engine/database-mirroring/database-mirroring-and-replication-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6522d-180">For more information, see [Database Mirroring and Replication &#40;SQL Server&#41;](../../../database-engine/database-mirroring/database-mirroring-and-replication-sql-server.md).</span></span>  
  
 <span data-ttu-id="6522d-181">**-ProfileName** _agent_profile_name_</span><span class="sxs-lookup"><span data-stu-id="6522d-181">**-ProfileName** _agent_profile_name_</span></span>  
 <span data-ttu-id="6522d-182">Nome di un profilo agente utilizzato per fornire un set di valori predefiniti all'agente.</span><span class="sxs-lookup"><span data-stu-id="6522d-182">Is the name of an agent profile used to supply a set of default values to the agent.</span></span> <span data-ttu-id="6522d-183">Per altre informazioni, vedere [Profili degli agenti di replica](replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="6522d-183">For information, see [Replication Agent Profiles](replication-agent-profiles.md).</span></span>  
  
 <span data-ttu-id="6522d-184">**-QueryTimeOut** _query_time_out_seconds_</span><span class="sxs-lookup"><span data-stu-id="6522d-184">**-QueryTimeOut** _query_time_out_seconds_</span></span>  
 <span data-ttu-id="6522d-185">Numero di secondi prima del timeout delle query. Il valore predefinito è 1800 secondi.</span><span class="sxs-lookup"><span data-stu-id="6522d-185">Is the number of seconds before the query times out. The default is 1800 seconds.</span></span>  
  
 <span data-ttu-id="6522d-186">**-ResolverState** [ **1**| **2**| **3**]</span><span class="sxs-lookup"><span data-stu-id="6522d-186">**-ResolverState** [ **1**| **2**| **3**]</span></span>  
 <span data-ttu-id="6522d-187">Specifica in che modo vengono risolti i conflitti degli aggiornamenti in coda.</span><span class="sxs-lookup"><span data-stu-id="6522d-187">Specifies how queued updating conflicts are resolved.</span></span> <span data-ttu-id="6522d-188">Un valore **1** indica che il conflitto viene vinto dal server di pubblicazione e che verrà eseguito il rollback della transazione in coda in conflitto corrente nel server di pubblicazione e nel Sottoscrittore di aggiornamento di origine. L'elaborazione delle transazioni in coda successive continuerà.</span><span class="sxs-lookup"><span data-stu-id="6522d-188">A value of **1** indicates the Publisher wins the conflict, and the current conflicting queued transaction will be rolled back on the Publisher and the originating updating Subscriber; the processing of subsequent queued transactions will continue.</span></span> <span data-ttu-id="6522d-189">Un valore **2** indica che il conflitto viene vinto dal Sottoscrittore e che la transazione in coda sostituirà i valori nel server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="6522d-189">A value of **2** indicates the Subscriber wins the conflict, and the queued transaction will override the values on the Publisher.</span></span> <span data-ttu-id="6522d-190">Un valore **3** indica che qualsiasi conflitto comporterà la reinizializzazione del Sottoscrittore. Il conflitto viene vinto dal server di pubblicazione, l'elaborazione delle transazioni in coda successive verrà interrotta e la sottoscrizione verrà reinizializzata.</span><span class="sxs-lookup"><span data-stu-id="6522d-190">A value of **3** indicates that any conflict will result in Subscriber re-initialization; the Publisher wins the conflict, processing of subsequent queued transactions will be terminated, and the subscription will be reinitialized.</span></span> <span data-ttu-id="6522d-191">L'impostazione predefinita è **1** per le pubblicazioni transazionali e **3** per le pubblicazioni snapshot.</span><span class="sxs-lookup"><span data-stu-id="6522d-191">The default setting is **1** for transactional publications and **3** for snapshot publications.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6522d-192">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6522d-192">Remarks</span></span>  
 <span data-ttu-id="6522d-193">Per avviare l'agente di lettura coda, eseguire **qrdrsvc.exe** dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="6522d-193">To start the Queue Reader Agent, execute **qrdrsvc.exe** from the command prompt.</span></span> <span data-ttu-id="6522d-194">Per informazioni, vedere [File eseguibili dell'Agente di replica](../concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="6522d-194">For information, see [Replication Agent Executables](../concepts/replication-agent-executables-concepts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6522d-195">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6522d-195">See Also</span></span>  
 [<span data-ttu-id="6522d-196">Amministrazione dell'agente di replica</span><span class="sxs-lookup"><span data-stu-id="6522d-196">Replication Agent Administration</span></span>](replication-agent-administration.md)  
  
  
