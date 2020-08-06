---
title: Specificare l'URL dell'endpoint quando si aggiunge o si modifica una replica di disponibilità (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- endpoints [SQL Server], AlwaysOn Availability Groups
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], endpoint
- Endpoint URLs (HADR)
ms.assetid: d7520c13-a8ee-4ddc-9e9a-54cd3d27ef1c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: da1eb2bacd4d5a2f7d0b2a623343f62b5e89597d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724979"
---
# <a name="specify-the-endpoint-url-when-adding-or-modifying-an-availability-replica-sql-server"></a><span data-ttu-id="72f7f-102">Specifica dell'URL dell'endpoint quando si aggiunge o si modifica una replica di disponibilità (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="72f7f-102">Specify the Endpoint URL When Adding or Modifying an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="72f7f-103">Per ospitare una replica di disponibilità per un gruppo di disponibilità, un'istanza del server deve possedere un endpoint del mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="72f7f-103">To host an availability replica for an availability group, a server instance must possess a database mirroring endpoint.</span></span> <span data-ttu-id="72f7f-104">L'istanza del server utilizza questo endpoint per rimanere in attesa dei messaggi [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] dalle repliche di disponibilità ospitate da altre istanze del server.</span><span class="sxs-lookup"><span data-stu-id="72f7f-104">The server instance uses this endpoint to listen for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] messages from availability replicas hosted by other server instances.</span></span> <span data-ttu-id="72f7f-105">Per definire una replica di disponibilità per un gruppo di disponibilità, è necessario specificare l'URL dell'endpoint dell'istanza del server che ospiterà la replica.</span><span class="sxs-lookup"><span data-stu-id="72f7f-105">To define an availability replica for an availability group, you must specify the endpoint URL of the server instance that will host the replica.</span></span> <span data-ttu-id="72f7f-106">L'*URL dell'endpoint* identifica il protocollo di trasporto dell'endpoint del mirroring del database (TCP), l'indirizzo di sistema dell'istanza del server e il numero di porta associato all'endpoint.</span><span class="sxs-lookup"><span data-stu-id="72f7f-106">The *endpoint URL* identifies the transport protocol of the database mirroring endpoint-TCP, the system address of the server instance, and the port number associated with the endpoint.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="72f7f-107">Il termine "URL dell'endpoint" è sinonimo del termine "indirizzo di rete server" utilizzato dall'interfaccia utente del mirroring del database e dalla documentazione.</span><span class="sxs-lookup"><span data-stu-id="72f7f-107">The term "endpoint URL" is synonymous with the term "server network address" used by the database mirroring user interface and documentation.</span></span>  
  
-   [<span data-ttu-id="72f7f-108">Sintassi per un URL dell'endpoint</span><span class="sxs-lookup"><span data-stu-id="72f7f-108">Syntax for an Endpoint URL</span></span>](#SyntaxOfURL)  
  
-   [<span data-ttu-id="72f7f-109">Individuazione del nome di dominio completo di un sistema</span><span class="sxs-lookup"><span data-stu-id="72f7f-109">Finding the Fully Qualified Domain Name of A System</span></span>](#Finding_FQDN)  
  
-   [<span data-ttu-id="72f7f-110">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="72f7f-110">Related Tasks</span></span>](#RelatedTasks)  
  
-   [<span data-ttu-id="72f7f-111">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="72f7f-111">Related Content</span></span>](#RelatedContent)  
  
##  <a name="syntax-for-an-endpoint-url"></a><a name="SyntaxOfURL"></a> <span data-ttu-id="72f7f-112">Sintassi per un URL dell'endpoint</span><span class="sxs-lookup"><span data-stu-id="72f7f-112">Syntax for an Endpoint URL</span></span>  
 <span data-ttu-id="72f7f-113">La sintassi per un URL dell'endpoint è la seguente:</span><span class="sxs-lookup"><span data-stu-id="72f7f-113">The syntax for an endpoint URL is of the form:</span></span>  
  
 <span data-ttu-id="72f7f-114">TCP<strong>://</strong> *\<system-address>* <strong>:</strong> *\<port>*</span><span class="sxs-lookup"><span data-stu-id="72f7f-114">TCP<strong>://</strong>*\<system-address>*<strong>:</strong>*\<port>*</span></span>  
  
 <span data-ttu-id="72f7f-115">dove</span><span class="sxs-lookup"><span data-stu-id="72f7f-115">where</span></span>  
  
-   <span data-ttu-id="72f7f-116">*\<system-address>* è una stringa che identifica in modo univoco il computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="72f7f-116">*\<system-address>* is a string that unambiguously identifies the target computer system.</span></span> <span data-ttu-id="72f7f-117">In genere, l'indirizzo del server è un nome di sistema, se i sistemi si trovano nello stesso dominio, un nome di dominio completo o un indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="72f7f-117">Typically, the server address is a system name (if the systems are in the same domain), a fully qualified domain name, or an IP address:</span></span>  
  
    -   <span data-ttu-id="72f7f-118">Poiché i nodi del cluster WSFC (Windows Server Failover Clustering) si trovano nello stesso dominio, è possibile utilizzare il nome del computer, ad esempio `SYSTEM46`.</span><span class="sxs-lookup"><span data-stu-id="72f7f-118">Because the nodes of Windows Server Failover Clustering (WSFC) cluster are the same domain, you can use the name of the computer system; for example, `SYSTEM46`.</span></span>  
  
    -   <span data-ttu-id="72f7f-119">Per utilizzare un indirizzo IP, è necessario che esso sia univoco nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="72f7f-119">To use an IP address, it must be unique in your environment.</span></span> <span data-ttu-id="72f7f-120">È consigliabile utilizzare un indirizzo IP solo se è statico.</span><span class="sxs-lookup"><span data-stu-id="72f7f-120">We recommend that you use an IP address only if it is static.</span></span> <span data-ttu-id="72f7f-121">L'indirizzo IP può essere IP versione 4 (IPv4) o IP versione 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="72f7f-121">The IP address can be IP Version 4 (IPv4) or IP Version 6 (IPv6).</span></span> <span data-ttu-id="72f7f-122">Un indirizzo IPv6 deve essere racchiuso tra parentesi quadre, ad esempio **[** _<indirizzo_IPv6>_ **]** .</span><span class="sxs-lookup"><span data-stu-id="72f7f-122">An IPv6 address must be enclosed within square brackets, for example: **[**_<IPv6_address>_**]**.</span></span>  
  
         <span data-ttu-id="72f7f-123">Per individuare l'indirizzo IP di un sistema, al prompt dei comandi di Windows immettere il comando **ipconfig** .</span><span class="sxs-lookup"><span data-stu-id="72f7f-123">To learn the IP address of a system, at the Windows command prompt, enter the **ipconfig** command.</span></span>  
  
    -   <span data-ttu-id="72f7f-124">Il funzionamento del nome di dominio completo è garantito.</span><span class="sxs-lookup"><span data-stu-id="72f7f-124">The fully qualified domain name is guaranteed to work.</span></span> <span data-ttu-id="72f7f-125">Il nome di dominio completo è costituito da una stringa di indirizzo definita a livello locale che accetta forme diverse a seconda della posizione.</span><span class="sxs-lookup"><span data-stu-id="72f7f-125">This is a locally defined address string that takes different forms in different places.</span></span> <span data-ttu-id="72f7f-126">Spesso ma non sempre, un nome di dominio completo è un nome composto che include un nome computer e una serie di segmenti di dominio separati da virgole, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="72f7f-126">Often, but not always, a fully qualified domain name is a compound name that includes the computer name and a series of period-separated domain segments of the form:</span></span>  
  
         <span data-ttu-id="72f7f-127">_nome_computer_ **.**</span><span class="sxs-lookup"><span data-stu-id="72f7f-127">_computer_name_ **.**</span></span> <span data-ttu-id="72f7f-128">_segmento_dominio_[... **.** _segmento_dominio_]</span><span class="sxs-lookup"><span data-stu-id="72f7f-128">_domain_segment_[...**.**_domain_segment_]</span></span>  
  
         <span data-ttu-id="72f7f-129">dove *nome_computer*è il nome di rete del computer che esegue l'istanza del server e *segmento_dominio*[... **.** _segmento_dominio_] è la parte rimanente delle informazioni sul dominio del server, ad esempio: `localinfo.corp.Adventure-Works.com`.</span><span class="sxs-lookup"><span data-stu-id="72f7f-129">where *computer_name i*s the network name of the computer running the server instance, and *domain_segment*[...**.**_domain_segment_] is the remaining domain information of the server; for example: `localinfo.corp.Adventure-Works.com`.</span></span>  
  
         <span data-ttu-id="72f7f-130">Il contenuto e il numero dei segmenti di dominio sono determinati all'interno della società o dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="72f7f-130">The content and number of domain segments are determined within the company or organization.</span></span> <span data-ttu-id="72f7f-131">Per ulteriori informazioni, vedere [Individuazione del nome di dominio completo](#Finding_FQDN), più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="72f7f-131">For more information, see [Finding the Fully Qualified Domain Name](#Finding_FQDN), later in this topic.</span></span>  
  
-   <span data-ttu-id="72f7f-132">*\<port>* è il numero di porta usato dall'endpoint del mirroring dell'istanza del server partner.</span><span class="sxs-lookup"><span data-stu-id="72f7f-132">*\<port>* is the port number used by the mirroring endpoint of the partner server instance.</span></span>  
  
     <span data-ttu-id="72f7f-133">Un endpoint del mirroring del database può utilizzare qualsiasi porta disponibile nel computer.</span><span class="sxs-lookup"><span data-stu-id="72f7f-133">A database mirroring endpoint can use any available port on the computer system.</span></span> <span data-ttu-id="72f7f-134">Ogni numero di porta deve essere associato a un solo endpoint e ogni endpoint a una singola istanza del server. In questo modo, istanze del server diverse sullo stesso server restano in attesa su endpoint diversi con porte diverse.</span><span class="sxs-lookup"><span data-stu-id="72f7f-134">Each port number must be associated with only one endpoint, and each endpoint is associated with a single server instance; thus, different server instances on the same server listen on different endpoints with different ports.</span></span> <span data-ttu-id="72f7f-135">Pertanto, la porta specificata nell'URL dell'endpoint quando si specifica una replica di disponibilità indirizzerà sempre i messaggi in arrivo all'istanza del server il cui endpoint è associato a tale porta.</span><span class="sxs-lookup"><span data-stu-id="72f7f-135">Therefore, the port you specify in the endpoint URL when you specify an availability replica will always direct incoming messages to the server instance whose endpoint is associated with that port.</span></span>  
  
     <span data-ttu-id="72f7f-136">Nell'URL dell'endpoint solo il numero della porta identifica l'istanza del server associata all'endpoint del mirroring del database nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="72f7f-136">IIn the endpoint URL, only the number of the port identifies the server instance that is associated with the mirroring endpoint on the target computer.</span></span> <span data-ttu-id="72f7f-137">Nella figura seguente vengono illustrati gli URL dell'endpoint di due istanze del server su un unico computer.</span><span class="sxs-lookup"><span data-stu-id="72f7f-137">The following figure illustrates the endpoint URLs of two server instances on a single computer.</span></span> <span data-ttu-id="72f7f-138">L'istanza predefinita utilizza la porta `7022` , mentre l'istanza denominata utilizza la porta `7033`.</span><span class="sxs-lookup"><span data-stu-id="72f7f-138">The default instance uses port `7022` and the named instance uses port `7033`.</span></span> <span data-ttu-id="72f7f-139">L'URL dell'endpoint di queste due istanze del server sono rispettivamente `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7022` e `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7033`.</span><span class="sxs-lookup"><span data-stu-id="72f7f-139">The endpoint URL for these two server instances are, respectively: `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7022` and `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7033`.</span></span> <span data-ttu-id="72f7f-140">Si noti che l'indirizzo non include il nome dell'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="72f7f-140">Note that the address does not contain the name of the server instance.</span></span>  
  
     <span data-ttu-id="72f7f-141">![Indirizzi di rete del server per un'istanza predefinita](../../media/dbm-2-instances-ports-1-system.gif "Indirizzi di rete del server per un'istanza predefinita")</span><span class="sxs-lookup"><span data-stu-id="72f7f-141">![Server network addresses of a default instance](../../media/dbm-2-instances-ports-1-system.gif "Server network addresses of a default instance")</span></span>  
  
     <span data-ttu-id="72f7f-142">Per individuare la porta attualmente associata all'endpoint di mirroring del database per un'istanza del server, utilizzare l'istruzione [!INCLUDE[tsql](../../../includes/tsql-md.md)] seguente:</span><span class="sxs-lookup"><span data-stu-id="72f7f-142">To identify the port currently associated with database mirroring endpoint of a server instance, use the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement:</span></span>  
  
    ```sql
    SELECT type_desc, port FROM sys.TCP_endpoints  
    ```  
  
     <span data-ttu-id="72f7f-143">Individuare la riga il cui valore **type_desc** è "DATABASE_MIRRORING" e usare il numero di porta corrispondente.</span><span class="sxs-lookup"><span data-stu-id="72f7f-143">Find the row whose **type_desc** value is "DATABASE_MIRRORING," and use the corresponding port number.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="72f7f-144">Esempi</span><span class="sxs-lookup"><span data-stu-id="72f7f-144">Examples</span></span>  
  
#### <a name="a-using-a-system-name"></a><span data-ttu-id="72f7f-145">R.</span><span class="sxs-lookup"><span data-stu-id="72f7f-145">A.</span></span> <span data-ttu-id="72f7f-146">Utilizzo di un nome di sistema</span><span class="sxs-lookup"><span data-stu-id="72f7f-146">Using a system name</span></span>  
 <span data-ttu-id="72f7f-147">L'URL dell'endpoint seguente specifica un nome di sistema, `SYSTEM46`, e la porta `7022`.</span><span class="sxs-lookup"><span data-stu-id="72f7f-147">The following endpoint URL specifies a system name, `SYSTEM46`, and port `7022`.</span></span>  
  
 `TCP://SYSTEM46:7022`  
  
#### <a name="b-using-a-fully-qualified-domain-name"></a><span data-ttu-id="72f7f-148">B.</span><span class="sxs-lookup"><span data-stu-id="72f7f-148">B.</span></span> <span data-ttu-id="72f7f-149">Utilizzo di un nome di dominio completo</span><span class="sxs-lookup"><span data-stu-id="72f7f-149">Using a fully qualified domain name</span></span>  
 <span data-ttu-id="72f7f-150">L'URL dell'endpoint seguente specifica un nome di dominio completo, `DBSERVER8.manufacturing.Adventure-Works.com`, e la porta `7024`.</span><span class="sxs-lookup"><span data-stu-id="72f7f-150">The following endpoint URL specifies a fully qualified domain name, `DBSERVER8.manufacturing.Adventure-Works.com`, and port `7024`.</span></span>  
  
 `TCP://DBSERVER8.manufacturing.Adventure-Works.com:7024`  
  
#### <a name="c-using-ipv4"></a><span data-ttu-id="72f7f-151">C.</span><span class="sxs-lookup"><span data-stu-id="72f7f-151">C.</span></span> <span data-ttu-id="72f7f-152">Utilizzo di IPv4</span><span class="sxs-lookup"><span data-stu-id="72f7f-152">Using IPv4</span></span>  
 <span data-ttu-id="72f7f-153">L'URL dell'endpoint seguente specifica un indirizzo IPv4, `10.193.9.134`, e la porta `7023`.</span><span class="sxs-lookup"><span data-stu-id="72f7f-153">The following endpoint URL specifies an IPv4 address, `10.193.9.134`, and port `7023`.</span></span>  
  
 `TCP://10.193.9.134:7023`  
  
#### <a name="d-using-ipv6"></a><span data-ttu-id="72f7f-154">D.</span><span class="sxs-lookup"><span data-stu-id="72f7f-154">D.</span></span> <span data-ttu-id="72f7f-155">Utilizzo di IPv6</span><span class="sxs-lookup"><span data-stu-id="72f7f-155">Using IPv6</span></span>  
 <span data-ttu-id="72f7f-156">L'URL dell'endpoint seguente include un indirizzo IPv6, `2001:4898:23:1002:20f:1fff:feff:b3a3`, e la porta `7022`.</span><span class="sxs-lookup"><span data-stu-id="72f7f-156">The following endpoint URL contains an IPv6 address, `2001:4898:23:1002:20f:1fff:feff:b3a3`, and port `7022`.</span></span>  
  
 `TCP://[2001:4898:23:1002:20f:1fff:feff:b3a3]:7022`  
  
##  <a name="finding-the-fully-qualified-domain-name-of-a-system"></a><a name="Finding_FQDN"></a> <span data-ttu-id="72f7f-157">Individuazione del nome di dominio completo di un sistema</span><span class="sxs-lookup"><span data-stu-id="72f7f-157">Finding the Fully Qualified Domain Name of A System</span></span>  
 <span data-ttu-id="72f7f-158">Per individuare il nome di dominio completo di un sistema, al prompt dei comandi di Windows immettere:</span><span class="sxs-lookup"><span data-stu-id="72f7f-158">To find the fully qualified domain name of a system, at the Windows command prompt on that system, enter:</span></span>  
  
 <span data-ttu-id="72f7f-159">**IPCONFIG /ALL**</span><span class="sxs-lookup"><span data-stu-id="72f7f-159">**IPCONFIG /ALL**</span></span>  
  
 <span data-ttu-id="72f7f-160">Per ottenere il nome di dominio completo, concatenare i valori di *<host_name>* e *<Primary_Dns_Suffix>* come riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="72f7f-160">To form the fully qualified domain name, concatenate the values of *<host_name>* and *<Primary_Dns_Suffix>* as follows:</span></span>  
  
 <span data-ttu-id="72f7f-161">_<host_name>_ **.**</span><span class="sxs-lookup"><span data-stu-id="72f7f-161">_<host_name>_ **.**</span></span> <span data-ttu-id="72f7f-162">_<Primary_Dns_Suffix>_</span><span class="sxs-lookup"><span data-stu-id="72f7f-162">_<Primary_Dns_Suffix>_</span></span>  
  
 <span data-ttu-id="72f7f-163">Ad esempio, la configurazione IP</span><span class="sxs-lookup"><span data-stu-id="72f7f-163">For example, the IP configuration</span></span>  
  
 `Host Name  .  .  .  .  .  .  : MYSERVER`  
  
 `Primary Dns Suffix  .  .  .  : mydomain.Adventure-Works.com`  
  
 <span data-ttu-id="72f7f-164">corrisponde al nome di dominio completo seguente:</span><span class="sxs-lookup"><span data-stu-id="72f7f-164">equates to the following fully qualified domain name:</span></span>  
  
 `MYSERVER.mydomain.Adventure-Works.com`  
  
> [!NOTE]  
>  <span data-ttu-id="72f7f-165">Per ulteriori informazioni su un nome di dominio completo, consultare l'amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="72f7f-165">If you need more information about a fully qualified domain name, see your system administrator.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="72f7f-166">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="72f7f-166">Related Tasks</span></span>  
 <span data-ttu-id="72f7f-167">**Per configurare un endpoint del mirroring del database**</span><span class="sxs-lookup"><span data-stu-id="72f7f-167">**To Configure a Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="72f7f-168">Creazione di un endpoint del mirroring del database per Gruppi di disponibilità AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="72f7f-168">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="72f7f-169">Creare un endpoint del mirroring del database per l'autenticazione Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="72f7f-169">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="72f7f-170">Utilizzare certificati per un endpoint del mirroring del database &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="72f7f-170">Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/use-certificates-for-a-database-mirroring-endpoint-transact-sql.md)  
  
    -   [<span data-ttu-id="72f7f-171">Impostazione dell'endpoint del mirroring del database per l'utilizzo di certificati per le connessioni in uscita &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="72f7f-171">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-outbound-connections.md)  
  
    -   [<span data-ttu-id="72f7f-172">Impostazione dell'endpoint del mirroring del database per l'utilizzo di certificati per le connessioni in ingresso &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="72f7f-172">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="72f7f-173">Specificare un indirizzo di rete del server &#40;Mirroring del database&#41;</span><span class="sxs-lookup"><span data-stu-id="72f7f-173">Specify a Server Network Address &#40;Database Mirroring&#41;</span></span>](../../database-mirroring/specify-a-server-network-address-database-mirroring.md)  
  
-   [<span data-ttu-id="72f7f-174">Risolvere i problemi di Gruppi di disponibilità AlwaysOn &#40;di configurazione SQL Server eliminati&#41;</span><span class="sxs-lookup"><span data-stu-id="72f7f-174">Troubleshoot AlwaysOn Availability Groups Configuration &#40;SQL Server&#41;deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
 <span data-ttu-id="72f7f-175">**Per visualizzare informazioni sull'endpoint del mirroring del database**</span><span class="sxs-lookup"><span data-stu-id="72f7f-175">**To View Information About the Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="72f7f-176">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="72f7f-176">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql)  
  
 <span data-ttu-id="72f7f-177">**Per aggiungere una replica di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="72f7f-177">**To add an availability replica**</span></span>  
  
-   [<span data-ttu-id="72f7f-178">Aggiungere una replica secondaria a un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="72f7f-178">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="72f7f-179">Creare un join di una replica secondaria a un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="72f7f-179">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="72f7f-180">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="72f7f-180">Related Content</span></span>  
  
-   [<span data-ttu-id="72f7f-181">Pagina relativa alla guida alle soluzioni AlwaysOn di Microsoft SQL Server per la disponibilità elevata e il ripristino di emergenza</span><span class="sxs-lookup"><span data-stu-id="72f7f-181">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
## <a name="see-also"></a><span data-ttu-id="72f7f-182">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72f7f-182">See Also</span></span>  
 <span data-ttu-id="72f7f-183">[Creazione e configurazione di gruppi di disponibilità &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="72f7f-183">[Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="72f7f-184">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="72f7f-184">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="72f7f-185">CREATE ENDPOINT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="72f7f-185">CREATE ENDPOINT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-endpoint-transact-sql)  
