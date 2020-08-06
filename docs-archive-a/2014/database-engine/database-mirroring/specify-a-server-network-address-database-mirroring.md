---
title: Specificare un indirizzo di rete del server (mirroring del database) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- database mirroring [SQL Server], endpoint
- endpoints [SQL Server], database mirroring
- server network addresses [SQL Server]
ms.assetid: a64d4b6b-9016-4f1e-a310-b1df181dd0c6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5c7db7ee6d321229205248059ce09a86f1da101f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629586"
---
# <a name="specify-a-server-network-address-database-mirroring"></a><span data-ttu-id="20935-102">Specificare un indirizzo di rete del server (Mirroring del database)</span><span class="sxs-lookup"><span data-stu-id="20935-102">Specify a Server Network Address (Database Mirroring)</span></span>
  <span data-ttu-id="20935-103">Per impostare una sessione di mirroring del database, è necessario un indirizzo di rete del server per ogni istanza del server.</span><span class="sxs-lookup"><span data-stu-id="20935-103">Setting up a database mirroring session requires a server network address for each of the server instances.</span></span> <span data-ttu-id="20935-104">Tale indirizzo deve identificare in maniera univoca l'istanza includendo un indirizzo di sistema e il numero di porta su cui l'istanza è in attesa.</span><span class="sxs-lookup"><span data-stu-id="20935-104">The server network address of a server instance must unambiguously identify the instance by providing a system address and the number of the port on which the instance is listening.</span></span>  
  
 <span data-ttu-id="20935-105">Per poter specificare una porta in un indirizzo di rete del server, è necessario che l'endpoint del mirroring del database sia disponibile sull'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="20935-105">Before you can specify a port in a server network address, the database mirroring endpoint must exist on the server instance.</span></span> <span data-ttu-id="20935-106">Per altre informazioni, vedere [Creare un endpoint del mirroring del database per l'autenticazione Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="20935-106">For more information, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
  
  
##  <a name="syntax-for-a-server-network-address"></a><a name="Syntax"></a> <span data-ttu-id="20935-107">Sintassi per un indirizzo di rete del server</span><span class="sxs-lookup"><span data-stu-id="20935-107">Syntax for a Server Network Address</span></span>  
 <span data-ttu-id="20935-108">La sintassi per un indirizzo di rete del server presenta la struttura seguente:</span><span class="sxs-lookup"><span data-stu-id="20935-108">The syntax for a server network address is of the form:</span></span>  
  
 <span data-ttu-id="20935-109">TCP<strong>://</strong> *\<system-address>* <strong> :<strong>*\<port>*</span><span class="sxs-lookup"><span data-stu-id="20935-109">TCP<strong>://</strong>*\<system-address>*<strong>:<strong>*\<port>*</span></span> 
  
 <span data-ttu-id="20935-110">dove</span><span class="sxs-lookup"><span data-stu-id="20935-110">where</span></span>  
  
-   <span data-ttu-id="20935-111">*\<system-address>* è una stringa che identifica in modo univoco il computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="20935-111">*\<system-address>* is a string that unambiguously identifies the destination computer system.</span></span> <span data-ttu-id="20935-112">In genere, l'indirizzo del server è un nome di sistema, se i sistemi si trovano nello stesso dominio, un nome di dominio completo o un indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="20935-112">Typically, the server address is a system name (if the systems are in the same domain), a fully qualified domain name, or an IP address:</span></span>  
  
    -   <span data-ttu-id="20935-113">Se i sistemi si trovano nello stesso dominio, è possibile utilizzare il nome del computer, ad esempio `SYSTEM46`.</span><span class="sxs-lookup"><span data-stu-id="20935-113">If the systems are the same domain, you can use the name of the computer system; for example, `SYSTEM46`.</span></span>  
  
    -   <span data-ttu-id="20935-114">Per utilizzare un indirizzo IP, è necessario che esso sia univoco nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="20935-114">To use an IP address, it must be unique in your environment.</span></span> <span data-ttu-id="20935-115">È consigliabile utilizzare un indirizzo IP solo se è statico.</span><span class="sxs-lookup"><span data-stu-id="20935-115">We recommend that you use an IP address only if it is static.</span></span> <span data-ttu-id="20935-116">L'indirizzo IP può essere IP versione 4 (IPv4) o IP versione 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="20935-116">The IP address can be IP Version 4 (IPv4) or IP Version 6 (IPv6).</span></span> <span data-ttu-id="20935-117">Un indirizzo IPv6 deve essere racchiuso tra parentesi quadre, ad esempio **[** _<indirizzo_IPv6>_ **]** .</span><span class="sxs-lookup"><span data-stu-id="20935-117">An IPv6 address must be enclosed within square brackets, for example: **[**_<IPv6_address>_**]**.</span></span>  
  
         <span data-ttu-id="20935-118">Per individuare l'indirizzo IP di un sistema, al prompt dei comandi di Windows immettere il comando **ipconfig** .</span><span class="sxs-lookup"><span data-stu-id="20935-118">To learn the IP address of a system, at the Windows command prompt, enter the **ipconfig** command.</span></span>  
  
    -   <span data-ttu-id="20935-119">Il funzionamento del nome di dominio completo è garantito.</span><span class="sxs-lookup"><span data-stu-id="20935-119">The fully qualified domain name is guaranteed to work.</span></span> <span data-ttu-id="20935-120">Il nome di dominio completo è costituito da una stringa di indirizzo definita a livello locale con forme diverse a seconda della sua posizione.</span><span class="sxs-lookup"><span data-stu-id="20935-120">This is a locally defined address string that different forms in different places.</span></span> <span data-ttu-id="20935-121">Spesso ma non sempre, un nome di dominio completo è un nome composto che include un nome computer e una serie di segmenti di dominio separati da virgole, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="20935-121">Often, but not always, a fully qualified domain name is a compound name that includes the computer name and a series of period-separated domain segments of the form:</span></span>  
  
         <span data-ttu-id="20935-122">_nome_computer_ **.**</span><span class="sxs-lookup"><span data-stu-id="20935-122">_computer_name_ **.**</span></span> <span data-ttu-id="20935-123">_segmento_dominio_[... **.** _segmento_dominio_]</span><span class="sxs-lookup"><span data-stu-id="20935-123">_domain_segment_[...**.**_domain_segment_]</span></span>  
  
         <span data-ttu-id="20935-124">dove *nome_computer*è il nome di rete del computer che esegue l'istanza del server e *segmento_dominio*[... **.** _segmento_dominio_] è la parte rimanente delle informazioni sul dominio del server, ad esempio: `localinfo.corp.Adventure-Works.com`.</span><span class="sxs-lookup"><span data-stu-id="20935-124">where *computer_name i*s the network name of the computer running the server instance, and *domain_segment*[...**.**_domain_segment_] is the remaining domain information of the server; for example: `localinfo.corp.Adventure-Works.com`.</span></span>  
  
         <span data-ttu-id="20935-125">Il contenuto e il numero dei segmenti di dominio sono determinati all'interno della società o dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="20935-125">The content and number of domain segments are determined within the company or organization.</span></span> <span data-ttu-id="20935-126">Se non si conosce il nome di dominio completo del server, consultare l'amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="20935-126">If you do not know the fully qualified domain name for your server, see your system administrator.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="20935-127">Per informazioni sull'individuazione di un nome di dominio completo, vedere "Individuazione del nome di dominio completo" di seguito in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="20935-127">For information about how to find a fully qualified domain name, see "Finding the Fully Qualified Domain Name," later in this topic.</span></span>  
  
-   <span data-ttu-id="20935-128">*\<port>* è il numero di porta usato dall'endpoint del mirroring dell'istanza del server partner.</span><span class="sxs-lookup"><span data-stu-id="20935-128">*\<port>* is the port number used by the mirroring endpoint of the partner server instance.</span></span> <span data-ttu-id="20935-129">Per informazioni su come specificare un endpoint, vedere [Creare un endpoint del mirroring del database per l'autenticazione Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="20935-129">For information about specifying an endpoint, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
     <span data-ttu-id="20935-130">Un endpoint del mirroring del database può utilizzare qualsiasi porta disponibile nel computer.</span><span class="sxs-lookup"><span data-stu-id="20935-130">A database mirroring endpoint can use any available port on the computer system.</span></span> <span data-ttu-id="20935-131">Ogni numero di porta su un sistema di computer deve essere associato a un solo endpoint e ogni endpoint a una singola istanza del server. In questo modo, istanze del server diverse sullo stesso server restano in attesa su endpoint diversi con porte diverse.</span><span class="sxs-lookup"><span data-stu-id="20935-131">Each port number on a computer system must be associated with only one endpoint, and each endpoint is associated with a single server instance; thus, different server instances on the same server listen on different endpoints with different ports.</span></span> <span data-ttu-id="20935-132">Pertanto, la parte specificata nell'indirizzo di rete del server quando si imposta una sessione di mirroring del database dirigerà la sessione sempre all'istanza del server il cui endpoint è associato a tale porta.</span><span class="sxs-lookup"><span data-stu-id="20935-132">Therefore, the port you specify in the server network address when you set up a database mirroring session will always direct the session to the server instance whose endpoint is associated with that port.</span></span>  
  
     <span data-ttu-id="20935-133">Nell'indirizzo di rete del server di un'istanza del server, solo il numero della porta associata al relativo endpoint del mirroring distingue l'istanza dalle altre sul computer.</span><span class="sxs-lookup"><span data-stu-id="20935-133">In the server network address of a server instance, only the number of the port associated with its mirroring endpoint distinguishes that instance from any other instances on the computer.</span></span> <span data-ttu-id="20935-134">Nella figura seguente vengono illustrati gli indirizzi di rete del server di due istanze del server su un unico computer.</span><span class="sxs-lookup"><span data-stu-id="20935-134">The following figure illustrates the server network addresses of two server instances on a single computer.</span></span> <span data-ttu-id="20935-135">L'istanza predefinita utilizza la porta `7022` , mentre l'istanza denominata utilizza la porta `7033`.</span><span class="sxs-lookup"><span data-stu-id="20935-135">The default instance uses port `7022` and the named instance uses port `7033`.</span></span> <span data-ttu-id="20935-136">Gli indirizzi di rete di queste due istanze del server sono rispettivamente `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7022` e `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7033`.</span><span class="sxs-lookup"><span data-stu-id="20935-136">The server network address for these two server instances are, respectively: `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7022` and `TCP://MYSYSTEM.Adventure-works.MyDomain.com:7033`.</span></span> <span data-ttu-id="20935-137">Si noti che l'indirizzo non include il nome dell'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="20935-137">Note that the address does not contain the name of the server instance.</span></span>  
  
     <span data-ttu-id="20935-138">![Indirizzi di rete del server per un'istanza predefinita](../media/dbm-2-instances-ports-1-system.gif "Indirizzi di rete del server per un'istanza predefinita")</span><span class="sxs-lookup"><span data-stu-id="20935-138">![Server network addresses of a default instance](../media/dbm-2-instances-ports-1-system.gif "Server network addresses of a default instance")</span></span>  
  
     <span data-ttu-id="20935-139">Per individuare la porta attualmente associata all'endpoint di mirroring del database per un'istanza del server, utilizzare l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente:</span><span class="sxs-lookup"><span data-stu-id="20935-139">To identify the port currently associated with database mirroring endpoint of a server instance, use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    SELECT type_desc, port FROM sys.tcp_endpoints  
    ```  
  
     <span data-ttu-id="20935-140">Individuare la riga il cui valore **type_desc** è "DATABASE_MIRRORING" e usare il numero di porta corrispondente.</span><span class="sxs-lookup"><span data-stu-id="20935-140">Find the row whose **type_desc** value is "DATABASE_MIRRORING," and use the corresponding port number.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="20935-141">Esempi</span><span class="sxs-lookup"><span data-stu-id="20935-141">Examples</span></span>  
  
#### <a name="a-using-a-system-name"></a><span data-ttu-id="20935-142">R.</span><span class="sxs-lookup"><span data-stu-id="20935-142">A.</span></span> <span data-ttu-id="20935-143">Utilizzo di un nome di sistema</span><span class="sxs-lookup"><span data-stu-id="20935-143">Using a system name</span></span>  
 <span data-ttu-id="20935-144">L'indirizzo di rete del server seguente specifica un nome di sistema, `SYSTEM46`, e la porta `7022`.</span><span class="sxs-lookup"><span data-stu-id="20935-144">The following server network address specifies a system name, `SYSTEM46`, and port `7022`.</span></span>  
  
```  
ALTER DATABASE AdventureWorks SET PARTNER ='tcp://SYSTEM46:7022';  
```  
  
#### <a name="b-using-a-fully-qualified-domain-name"></a><span data-ttu-id="20935-145">B.</span><span class="sxs-lookup"><span data-stu-id="20935-145">B.</span></span> <span data-ttu-id="20935-146">Utilizzo di un nome di dominio completo</span><span class="sxs-lookup"><span data-stu-id="20935-146">Using a fully qualified domain name</span></span>  
 <span data-ttu-id="20935-147">L'indirizzo di rete del server seguente specifica un nome di dominio completo, `DBSERVER8.manufacturing.Adventure-Works.com`, e la porta `7024`.</span><span class="sxs-lookup"><span data-stu-id="20935-147">The following server network address specifies a fully qualified domain name, `DBSERVER8.manufacturing.Adventure-Works.com`, and port `7024`.</span></span>  
  
```  
ALTER DATABASE AdventureWorks SET PARTNER ='tcp://DBSERVER8.manufacturing.Adventure-Works.com:7024';  
```  
  
#### <a name="c-using-ipv4"></a><span data-ttu-id="20935-148">C.</span><span class="sxs-lookup"><span data-stu-id="20935-148">C.</span></span> <span data-ttu-id="20935-149">Utilizzo di IPv4</span><span class="sxs-lookup"><span data-stu-id="20935-149">Using IPv4</span></span>  
 <span data-ttu-id="20935-150">L'indirizzo di rete del server seguente specifica un indirizzo IPv4, `10.193.9.134`, e la porta `7023`.</span><span class="sxs-lookup"><span data-stu-id="20935-150">The following server network address specifies an IPv4 address, `10.193.9.134`, and port `7023`.</span></span>  
  
```  
ALTER DATABASE AdventureWorks SET PARTNER ='tcp://10.193.9.134:7023';  
```  
  
#### <a name="d-using-ipv6"></a><span data-ttu-id="20935-151">D.</span><span class="sxs-lookup"><span data-stu-id="20935-151">D.</span></span> <span data-ttu-id="20935-152">Utilizzo di IPv6</span><span class="sxs-lookup"><span data-stu-id="20935-152">Using IPv6</span></span>  
 <span data-ttu-id="20935-153">L'indirizzo di rete del server seguente include un indirizzo IPv6, `2001:4898:23:1002:20f:1fff:feff:b3a3`, e la porta `7022`.</span><span class="sxs-lookup"><span data-stu-id="20935-153">The following server network address contains an IPv6 address, `2001:4898:23:1002:20f:1fff:feff:b3a3`, and port `7022`.</span></span>  
  
```  
ALTER DATABASE AdventureWorks SET PARTNER ='tcp://[2001:4898:23:1002:20f:1fff:feff:b3a3]:7022';  
```  
  
## <a name="finding-the-fully-qualified-domain-name"></a><span data-ttu-id="20935-154">Individuazione del nome di dominio completo</span><span class="sxs-lookup"><span data-stu-id="20935-154">Finding the Fully Qualified Domain Name</span></span>  
 <span data-ttu-id="20935-155">Per individuare il nome di dominio completo di un sistema, al prompt dei comandi di Windows immettere:</span><span class="sxs-lookup"><span data-stu-id="20935-155">To find the fully qualified domain name of a system, at the Windows command prompt on that system, enter:</span></span>  
  
 <span data-ttu-id="20935-156">**IPCONFIG /ALL**</span><span class="sxs-lookup"><span data-stu-id="20935-156">**IPCONFIG /ALL**</span></span>  
  
 <span data-ttu-id="20935-157">Per ottenere il nome di dominio completo, concatenare i valori di *<host_name>* e *<Primary_Dns_Suffix>* come riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="20935-157">To form the fully qualified domain name, concatenate the values of *<host_name>* and *<Primary_Dns_Suffix>* as follows:</span></span>  
  
 <span data-ttu-id="20935-158">_<host_name>_ **.**</span><span class="sxs-lookup"><span data-stu-id="20935-158">_<host_name>_ **.**</span></span> <span data-ttu-id="20935-159">_<Primary_Dns_Suffix>_</span><span class="sxs-lookup"><span data-stu-id="20935-159">_<Primary_Dns_Suffix>_</span></span>  
  
 <span data-ttu-id="20935-160">Ad esempio, la configurazione IP</span><span class="sxs-lookup"><span data-stu-id="20935-160">For example, the IP configuration</span></span>  
  
 `Host Name  .  .  .  .  .  .  : MYSERVER`  
  
 `Primary Dns Suffix  .  .  .  : mydomain.Adventure-Works.com`  
  
 <span data-ttu-id="20935-161">corrisponde al nome di dominio completo seguente:</span><span class="sxs-lookup"><span data-stu-id="20935-161">equates to the following fully qualified domain name:</span></span>  
  
 `MYSERVER.mydomain.Adventure-Works.com`  
  
##  <a name="examples"></a><a name="Examples"></a> <span data-ttu-id="20935-162">Esempi</span><span class="sxs-lookup"><span data-stu-id="20935-162">Examples</span></span>  
 <span data-ttu-id="20935-163">Nell'esempio seguente viene illustrato l'indirizzo di rete del server per un'istanza del server in un computer denominato `REMOTESYSTEM3` in un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="20935-163">The following example shows the server network address for a server instance on a computer system named `REMOTESYSTEM3` in another domain.</span></span> <span data-ttu-id="20935-164">Il nome di dominio è `NORTHWEST.ADVENTURE-WORKS.COM`e la porta dell'endpoint del mirroring del database è `7025`.</span><span class="sxs-lookup"><span data-stu-id="20935-164">The domain information is `NORTHWEST.ADVENTURE-WORKS.COM`, and the port of the database mirroring endpoint is `7025`.</span></span> <span data-ttu-id="20935-165">Considerati questi componenti di esempio, l'indirizzo di rete del server è:</span><span class="sxs-lookup"><span data-stu-id="20935-165">Given these example components, the server network address is.</span></span>  
  
 `TCP://REMOTESYSTEM3.NORTHWEST.ADVENTURE-WORKS.COM:7025`  
  
 <span data-ttu-id="20935-166">Nell'esempio seguente viene indicato l'indirizzo di rete del server per un'istanza del server in un computer denominato `DBSERVER1`.</span><span class="sxs-lookup"><span data-stu-id="20935-166">The following example shows the server network address for a server instance on a computer system named `DBSERVER1`.</span></span> <span data-ttu-id="20935-167">Questo sistema si trova nel dominio locale ed è identificato in maniera univoca mediante il nome del sistema.</span><span class="sxs-lookup"><span data-stu-id="20935-167">This system is in the local domain and is unambiguously identified by its system name.</span></span> <span data-ttu-id="20935-168">La porta dell'endpoint del mirroring del database è `7022`.</span><span class="sxs-lookup"><span data-stu-id="20935-168">The port of the database mirroring endpoint is `7022`.</span></span>  
  
 `TCP://DBSERVER1:7022`  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="20935-169">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="20935-169">Related Tasks</span></span>  
  
-   [<span data-ttu-id="20935-170">Creare un endpoint del mirroring del database per l'autenticazione Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="20935-170">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="20935-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20935-171">See Also</span></span>  
 <span data-ttu-id="20935-172">[Mirroring del database &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="20935-172">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="20935-173">Endpoint del mirroring del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="20935-173">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](the-database-mirroring-endpoint-sql-server.md)  
  
  
