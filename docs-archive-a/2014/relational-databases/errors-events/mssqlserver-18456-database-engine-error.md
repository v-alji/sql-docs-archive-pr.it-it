---
title: MSSQLSERVER_18456 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 18456 (Database Engine error)
ms.assetid: c417631d-be1f-42e0-8844-9f92c77e11f7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f5addb6bfb9d056d9f1796749ae629d4150102a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715351"
---
# <a name="mssqlserver_18456"></a><span data-ttu-id="69655-102">MSSQLSERVER_18456</span><span class="sxs-lookup"><span data-stu-id="69655-102">MSSQLSERVER_18456</span></span>
    
## <a name="details"></a><span data-ttu-id="69655-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="69655-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="69655-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="69655-104">Product Name</span></span>|<span data-ttu-id="69655-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="69655-105">SQL Server</span></span>|  
|<span data-ttu-id="69655-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="69655-106">Event ID</span></span>|<span data-ttu-id="69655-107">18456</span><span class="sxs-lookup"><span data-stu-id="69655-107">18456</span></span>|  
|<span data-ttu-id="69655-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="69655-108">Event Source</span></span>|<span data-ttu-id="69655-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="69655-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="69655-110">Componente</span><span class="sxs-lookup"><span data-stu-id="69655-110">Component</span></span>|<span data-ttu-id="69655-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="69655-111">SQLEngine</span></span>|  
|<span data-ttu-id="69655-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="69655-112">Symbolic Name</span></span>|<span data-ttu-id="69655-113">LOGON_FAILED</span><span class="sxs-lookup"><span data-stu-id="69655-113">LOGON_FAILED</span></span>|  
|<span data-ttu-id="69655-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="69655-114">Message Text</span></span>|<span data-ttu-id="69655-115">Accesso non riuscito per l'utente '%.\*ls'.%.\*ls</span><span class="sxs-lookup"><span data-stu-id="69655-115">Login failed for user '%.\*ls'.%.\*ls</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="69655-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="69655-116">Explanation</span></span>  
 <span data-ttu-id="69655-117">Quando un tentativo di connessione viene rifiutato a causa di un errore di autenticazione dovuto a una password o un nome utente errato, al client viene restituito un messaggio simile al seguente:  "Accesso non riuscito per l'utente '<nome_utente>'</span><span class="sxs-lookup"><span data-stu-id="69655-117">When a connection attempt is rejected because of an authentication failure that involves a bad password or user name, a message similar to the following is returned to the client:  "Login failed for user '<user_name>'.</span></span> <span data-ttu-id="69655-118">(Microsoft SQL Server, Errore: 18456)".</span><span class="sxs-lookup"><span data-stu-id="69655-118">(Microsoft SQL Server, Error: 18456)".</span></span>  
  
 <span data-ttu-id="69655-119">Al client vengono restituite informazioni aggiuntive tra cui le seguenti:</span><span class="sxs-lookup"><span data-stu-id="69655-119">Additional information returned to the client includes the following:</span></span>  
  
 <span data-ttu-id="69655-120">"Accesso non riuscito per l'utente '<nome_utente>'</span><span class="sxs-lookup"><span data-stu-id="69655-120">"Login failed for user '<user_name>'.</span></span> <span data-ttu-id="69655-121">(provider di dati SqlClient .Net)"</span><span class="sxs-lookup"><span data-stu-id="69655-121">(.Net SqlClient Data Provider)"</span></span>  
  
 -----------------------------\-  
  
 <span data-ttu-id="69655-122">"Nome server: <nome_computer>"</span><span class="sxs-lookup"><span data-stu-id="69655-122">"Server Name: <computer_name>"</span></span>  
  
 <span data-ttu-id="69655-123">"Numero errore: 18456"</span><span class="sxs-lookup"><span data-stu-id="69655-123">"Error Number: 18456"</span></span>  
  
 <span data-ttu-id="69655-124">"Gravità: 14"</span><span class="sxs-lookup"><span data-stu-id="69655-124">"Severity: 14"</span></span>  
  
 <span data-ttu-id="69655-125">"Stato: 1"</span><span class="sxs-lookup"><span data-stu-id="69655-125">"State: 1"</span></span>  
  
 <span data-ttu-id="69655-126">"Numero riga: 65536"</span><span class="sxs-lookup"><span data-stu-id="69655-126">"Line Number: 65536"</span></span>  
  
 <span data-ttu-id="69655-127">Può essere inoltre restituito il messaggio seguente:</span><span class="sxs-lookup"><span data-stu-id="69655-127">The following message might also be returned:</span></span>  
  
 <span data-ttu-id="69655-128">"Messaggio 18456, livello 14, stato 1, server <nome_computer>, riga 1"</span><span class="sxs-lookup"><span data-stu-id="69655-128">"Msg 18456, Level 14, State 1, Server <computer_name>, Line 1"</span></span>  
  
 <span data-ttu-id="69655-129">"Accesso non riuscito per l'utente '<nome_utente>'".</span><span class="sxs-lookup"><span data-stu-id="69655-129">"Login failed for user '<user_name>'."</span></span>  
  
## <a name="additional-error-information"></a><span data-ttu-id="69655-130">Informazioni aggiuntive sull'errore</span><span class="sxs-lookup"><span data-stu-id="69655-130">Additional Error Information</span></span>  
 <span data-ttu-id="69655-131">Per aumentare il livello di sicurezza, il messaggio di errore restituito al client nasconde deliberatamente la natura dell'errore di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="69655-131">To increase security, the error message that is returned to the client deliberately hides the nature of the authentication error.</span></span> <span data-ttu-id="69655-132">Tuttavia, nel log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per ogni errore viene indicato lo stato corrispondente tramite cui viene eseguito il mapping alla condizione di errore di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="69655-132">However, in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, a corresponding error contains an error state that maps to an authentication failure condition.</span></span> <span data-ttu-id="69655-133">Confrontare lo stato di errore restituito con l'elenco seguente per determinare il motivo dell'errore di accesso.</span><span class="sxs-lookup"><span data-stu-id="69655-133">Compare the error state to the following list to determine the reason for the login failure.</span></span>  
  
|<span data-ttu-id="69655-134">State</span><span class="sxs-lookup"><span data-stu-id="69655-134">State</span></span>|<span data-ttu-id="69655-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="69655-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="69655-136">1</span><span class="sxs-lookup"><span data-stu-id="69655-136">1</span></span>|<span data-ttu-id="69655-137">Non sono disponibili informazioni sull'errore.</span><span class="sxs-lookup"><span data-stu-id="69655-137">Error information is not available.</span></span> <span data-ttu-id="69655-138">Questo stato in genere indica che non si dispone dell'autorizzazione a ricevere i dettagli dell'errore.</span><span class="sxs-lookup"><span data-stu-id="69655-138">This state usually means you do not have permission to receive the error details.</span></span> <span data-ttu-id="69655-139">Per ulteriori informazioni, contattare l'amministratore di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69655-139">Contact your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administrator for more information.</span></span>|  
|<span data-ttu-id="69655-140">2</span><span class="sxs-lookup"><span data-stu-id="69655-140">2</span></span>|<span data-ttu-id="69655-141">L'ID utente non è valido.</span><span class="sxs-lookup"><span data-stu-id="69655-141">User ID is not valid.</span></span>|  
|<span data-ttu-id="69655-142">5</span><span class="sxs-lookup"><span data-stu-id="69655-142">5</span></span>|<span data-ttu-id="69655-143">L'ID utente non è valido.</span><span class="sxs-lookup"><span data-stu-id="69655-143">User ID is not valid.</span></span>|  
|<span data-ttu-id="69655-144">6</span><span class="sxs-lookup"><span data-stu-id="69655-144">6</span></span>|<span data-ttu-id="69655-145">Si è tentato di utilizzare un account di accesso di Windows con l'autenticazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="69655-145">An attempt was made to use a Windows login name with SQL Server Authentication.</span></span>|  
|<span data-ttu-id="69655-146">7</span><span class="sxs-lookup"><span data-stu-id="69655-146">7</span></span>|<span data-ttu-id="69655-147">L'account di accesso è disabilitato e la password non è corretta.</span><span class="sxs-lookup"><span data-stu-id="69655-147">Login is disabled, and the password is incorrect.</span></span>|  
|<span data-ttu-id="69655-148">8</span><span class="sxs-lookup"><span data-stu-id="69655-148">8</span></span>|<span data-ttu-id="69655-149">La password non è corretta.</span><span class="sxs-lookup"><span data-stu-id="69655-149">The password is incorrect.</span></span>|  
|<span data-ttu-id="69655-150">9</span><span class="sxs-lookup"><span data-stu-id="69655-150">9</span></span>|<span data-ttu-id="69655-151">La password non è valida.</span><span class="sxs-lookup"><span data-stu-id="69655-151">Password is not valid.</span></span>|  
|<span data-ttu-id="69655-152">11</span><span class="sxs-lookup"><span data-stu-id="69655-152">11</span></span>|<span data-ttu-id="69655-153">L'account di accesso è valido, ma l'accesso al server ha avuto esito negativo.</span><span class="sxs-lookup"><span data-stu-id="69655-153">Login is valid, but server access failed.</span></span> <span data-ttu-id="69655-154">Una possibile causa di questo errore è quando l'utente di Windows dispone dell'accesso a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] come un membro del gruppo Administrators locale, ma Windows non fornisce le credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="69655-154">One possible cause of this error is when the Windows user has access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as a member of the local administrators group, but Windows is not providing administrator credentials.</span></span> <span data-ttu-id="69655-155">Per connettersi, avviare il programma di connessione usando l'opzione **Esegui come amministratore** e quindi aggiungere l'utente di Windows a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] come accesso specifico.</span><span class="sxs-lookup"><span data-stu-id="69655-155">To connect, start the connecting program using the **Run as administrator** option, and then add the Windows user to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as a specific login.</span></span>|  
|<span data-ttu-id="69655-156">12</span><span class="sxs-lookup"><span data-stu-id="69655-156">12</span></span>|<span data-ttu-id="69655-157">L'account di accesso è valido, ma l'accesso al server ha avuto esito negativo.</span><span class="sxs-lookup"><span data-stu-id="69655-157">Login is valid login, but server access failed.</span></span>|  
|<span data-ttu-id="69655-158">18</span><span class="sxs-lookup"><span data-stu-id="69655-158">18</span></span>|<span data-ttu-id="69655-159">È necessario modificare la password.</span><span class="sxs-lookup"><span data-stu-id="69655-159">Password must be changed.</span></span>|  
  
 <span data-ttu-id="69655-160">Esistono altri stati di errore che indicano un errore di elaborazione interno non previsto.</span><span class="sxs-lookup"><span data-stu-id="69655-160">Other error states exist and signify an unexpected internal processing error.</span></span>  
  
 <span data-ttu-id="69655-161">**Possibile causa insolita aggiuntiva**</span><span class="sxs-lookup"><span data-stu-id="69655-161">**An additional unusual possible cause**</span></span>  
  
 <span data-ttu-id="69655-162">Il motivo dell'errore **Tentativo di accesso tramite l'autenticazione di SQL Server non riuscito. Il server è configurato solo per l'autenticazione di Windows.**</span><span class="sxs-lookup"><span data-stu-id="69655-162">The error reason **An attempt to login using SQL authentication failed. Server is configured for Windows authentication only.**</span></span> <span data-ttu-id="69655-163">può essere restituito nelle situazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="69655-163">can be returned in the following situations.</span></span>  
  
-   <span data-ttu-id="69655-164">Quando il server è configurato per l'autenticazione in modalità mista, in una connessione ODBC viene utilizzato il protocollo TCP e tramite la connessione non viene specificato in modo esplicito che in essa deve essere utilizzata una connessione trusted.</span><span class="sxs-lookup"><span data-stu-id="69655-164">When the server is configured for mixed mode authentication, and an ODBC connection uses the TCP protocol, and the connection does not explicitly specify that the connection should use a trusted connection.</span></span>  
  
-   <span data-ttu-id="69655-165">Quando il server è configurato per l'autenticazione in modalità mista, in una connessione ODBC vengono utilizzate named pipe, le credenziali utilizzate dal client per aprire la named pipe vengono utilizzate per rappresentare automaticamente l'utente e tramite la connessione non viene specificato in modo esplicito che in essa deve essere utilizzata una connessione trusted.</span><span class="sxs-lookup"><span data-stu-id="69655-165">When the server is configured for mixed mode authentication, and an ODBC connection uses named pipes, and the credentials the client used to open the named pipe are used to automatically impersonate the user, and the connection does not explicitly specify that the connection should use a trusted connection.</span></span>  
  
 <span data-ttu-id="69655-166">Per risolvere questo problema, includere `TRUSTED_CONNECTION = TRUE` nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="69655-166">To resolve this issue, include `TRUSTED_CONNECTION = TRUE` in the connection string.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="69655-167">Esempi</span><span class="sxs-lookup"><span data-stu-id="69655-167">Examples</span></span>  
 <span data-ttu-id="69655-168">In questo esempio, lo stato dell'errore di autenticazione è 8 e</span><span class="sxs-lookup"><span data-stu-id="69655-168">In this example, the authentication error state is 8.</span></span> <span data-ttu-id="69655-169">indica che la password non è corretta.</span><span class="sxs-lookup"><span data-stu-id="69655-169">This indicates that the password is incorrect.</span></span>  
  
|<span data-ttu-id="69655-170">Data</span><span class="sxs-lookup"><span data-stu-id="69655-170">Date</span></span>|<span data-ttu-id="69655-171">Source (Sorgente)</span><span class="sxs-lookup"><span data-stu-id="69655-171">Source</span></span>|<span data-ttu-id="69655-172">Message</span><span class="sxs-lookup"><span data-stu-id="69655-172">Message</span></span>|  
|----------|------------|-------------|  
|<span data-ttu-id="69655-173">2007-12-05 20:12:56.34</span><span class="sxs-lookup"><span data-stu-id="69655-173">2007-12-05 20:12:56.34</span></span>|<span data-ttu-id="69655-174">Accesso</span><span class="sxs-lookup"><span data-stu-id="69655-174">Logon</span></span>|<span data-ttu-id="69655-175">Errore: 18456, Gravità: 14, Stato: 8.</span><span class="sxs-lookup"><span data-stu-id="69655-175">Error: 18456, Severity: 14, State: 8.</span></span>|  
|<span data-ttu-id="69655-176">2007-12-05 20:12:56.34</span><span class="sxs-lookup"><span data-stu-id="69655-176">2007-12-05 20:12:56.34</span></span>|<span data-ttu-id="69655-177">Accesso</span><span class="sxs-lookup"><span data-stu-id="69655-177">Logon</span></span>|<span data-ttu-id="69655-178">Accesso non riuscito per l'utente '<nome_utente>'.</span><span class="sxs-lookup"><span data-stu-id="69655-178">Login failed for user '<user_name>'.</span></span> <span data-ttu-id="69655-179">[CLIENT: \<ip address>]</span><span class="sxs-lookup"><span data-stu-id="69655-179">[CLIENT: \<ip address>]</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="69655-180">Se durante l'installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si usa la modalità Autenticazione di Windows e successivamente si passa alla modalità Autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e di Windows, l'account di accesso **sa** verrà inizialmente disabilitato.</span><span class="sxs-lookup"><span data-stu-id="69655-180">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed using Windows Authentication mode and is later changed to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows Authentication mode, the **sa** login is initially disabled.</span></span> <span data-ttu-id="69655-181">Ciò determina l'errore di stato 7: "Accesso non riuscito per l'utente 'sa'". Per abilitare l'account di accesso **sa**, vedere [Modifica della modalità di autenticazione del server](../../database-engine/configure-windows/change-server-authentication-mode.md).</span><span class="sxs-lookup"><span data-stu-id="69655-181">This causes the state 7 error: "Login failed for user 'sa'." To enable the **sa** login, see [Change Server Authentication Mode](../../database-engine/configure-windows/change-server-authentication-mode.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="69655-182">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="69655-182">User Action</span></span>  
 <span data-ttu-id="69655-183">Se si sta tentando di effettuare la connessione mediante l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], verificare che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sia configurato in modalità Autenticazione mista.</span><span class="sxs-lookup"><span data-stu-id="69655-183">If you are trying to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, verify that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured in Mixed Authentication Mode.</span></span>  
  
 <span data-ttu-id="69655-184">Se si sta tentando di effettuare la connessione mediante l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , verificare che l'account di accesso a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] esista e che non contenga errori di ortografia.</span><span class="sxs-lookup"><span data-stu-id="69655-184">If you are trying to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, verify that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login exists and that you have spelled it properly.</span></span>  
  
 <span data-ttu-id="69655-185">Se si sta tentando di effettuare la connessione mediante l'autenticazione di Windows, verificare di essere connessi al dominio corretto.</span><span class="sxs-lookup"><span data-stu-id="69655-185">If you are trying to connect using Windows Authentication, verify that you are properly logged into the correct domain.</span></span>  
  
 <span data-ttu-id="69655-186">Se l'errore indica lo stato 1, contattare l'amministratore di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69655-186">If your error indicates state 1, contact your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administrator.</span></span>  
  
 <span data-ttu-id="69655-187">Se si tenta di eseguire la connessione usando le credenziali di amministratore, avviare l'applicazione usando l'opzione **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="69655-187">If you are trying to connect using your administrator credentials, start you application by using the **Run as Administrator** option.</span></span> <span data-ttu-id="69655-188">Dopo aver stabilito la connessione, aggiungere l'utente di Windows come singolo account di accesso.</span><span class="sxs-lookup"><span data-stu-id="69655-188">When connected, add your Windows user as an individual login.</span></span>  
  
 <span data-ttu-id="69655-189">Se il [!INCLUDE[ssDE](../../includes/ssde-md.md)] supporta i database indipendenti, verificare che l'account di accesso non sia stato eliminato dopo la migrazione a un utente del database indipendente.</span><span class="sxs-lookup"><span data-stu-id="69655-189">If the [!INCLUDE[ssDE](../../includes/ssde-md.md)] supports contained databases, confirm that the login was not deleted after migration to a contained database user.</span></span>  
  
 <span data-ttu-id="69655-190">Quando ci si connette in locale a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], le connessioni da servizi in esecuzione con **NT AUTHORITY\NETWORK SERVICE** devono essere autenticate usando computer con nomi di dominio completi.</span><span class="sxs-lookup"><span data-stu-id="69655-190">When connecting locally to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], connections from services running under **NT AUTHORITY\NETWORK SERVICE** must authenticate using the computers fully qualified domain name.</span></span> <span data-ttu-id="69655-191">Per altre informazioni, vedere [Procedura: Usare l'account del servizio di rete per accedere alle risorse in ASP.NET](https://msdn.microsoft.com/library/ff647402.aspx)</span><span class="sxs-lookup"><span data-stu-id="69655-191">For more information, see [How To: Use the Network Service Account to Access Resources in ASP.NET](https://msdn.microsoft.com/library/ff647402.aspx)</span></span>  
  
  
