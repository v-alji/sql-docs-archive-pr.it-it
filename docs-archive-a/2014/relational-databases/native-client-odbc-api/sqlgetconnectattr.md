---
title: SQLGetConnectAttr | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetConnectAttr function
ms.assetid: 26e4e69a-44fd-45e3-b47a-ae39184f041b
author: rothja
ms.author: jroth
ms.openlocfilehash: f82a0fb71103e811b36280f9722c160791023e44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623255"
---
# <a name="sqlgetconnectattr"></a><span data-ttu-id="8d3e3-102">SQLGetConnectAttr</span><span class="sxs-lookup"><span data-stu-id="8d3e3-102">SQLGetConnectAttr</span></span>
  <span data-ttu-id="8d3e3-103">Il driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client definisce gli attributi di connessione specifici del driver.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver defines driver-specific connection attributes.</span></span> <span data-ttu-id="8d3e3-104">Alcuni degli attributi sono disponibili per `SQLGetConnectAttr` e la funzione viene utilizzata per segnalare le impostazioni correnti.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-104">Some of the attributes are available to `SQLGetConnectAttr`, and the function is used to report their current settings.</span></span> <span data-ttu-id="8d3e3-105">I valori restituiti per questi attributi non sono garantiti finché non viene stabilita una connessione o se l'attributo non è stato impostato tramite [SQLSetConnectAttr](sqlsetconnectattr.md).</span><span class="sxs-lookup"><span data-stu-id="8d3e3-105">The values reported for these attributes are not guaranteed until after a connection has been made or the attribute has been set using [SQLSetConnectAttr](sqlsetconnectattr.md).</span></span>  
  
 <span data-ttu-id="8d3e3-106">In questo argomento sono elencati gli attributi di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-106">This topic lists the read only attributes.</span></span> <span data-ttu-id="8d3e3-107">Per informazioni sugli altri [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] attributi di connessione specifici del driver ODBC di Native client, vedere [SQLSetConnectAttr](sqlsetconnectattr.md).</span><span class="sxs-lookup"><span data-stu-id="8d3e3-107">For information about the other [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver-specific connection attributes, see [SQLSetConnectAttr](sqlsetconnectattr.md).</span></span>  
  
## <a name="sql_copt_ss_connection_dead"></a><span data-ttu-id="8d3e3-108">SQL_COPT_SS_CONNECTION_DEAD</span><span class="sxs-lookup"><span data-stu-id="8d3e3-108">SQL_COPT_SS_CONNECTION_DEAD</span></span>  
 <span data-ttu-id="8d3e3-109">L'attributo SQL_COPT_SS_CONNECTION_DEAD consente di segnalare lo stato di una connessione a un server.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-109">The SQL_COPT_SS_CONNECTION_DEAD attribute reports the state of a connection to a server.</span></span> <span data-ttu-id="8d3e3-110">Il driver esegue query sulla rete al fine di individuare lo stato corrente della connessione.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-110">The driver queries the network for the current state of the connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8d3e3-111">L'attributo di connessione ODBC standard SQL_COPT_SS_CONNECTION_DEAD restituisce lo stato più recente della connessione.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-111">The standard ODBC connection attribute SQL_ATTR_CONNECTION_DEAD returns the most recent state of the connection.</span></span> <span data-ttu-id="8d3e3-112">Tale stato potrebbe non essere quello corrente.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-112">This might not be the current connection state.</span></span>  
  
|<span data-ttu-id="8d3e3-113">Valore</span><span class="sxs-lookup"><span data-stu-id="8d3e3-113">Value</span></span>|<span data-ttu-id="8d3e3-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8d3e3-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8d3e3-115">SQL_CD_TRUE</span><span class="sxs-lookup"><span data-stu-id="8d3e3-115">SQL_CD_TRUE</span></span>|<span data-ttu-id="8d3e3-116">La connessione al server è stata persa.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-116">The connection to the server has been lost.</span></span>|  
|<span data-ttu-id="8d3e3-117">SQL_CD_FALSE</span><span class="sxs-lookup"><span data-stu-id="8d3e3-117">SQL_CD_FALSE</span></span>|<span data-ttu-id="8d3e3-118">La connessione è aperta e disponibile per l'elaborazione di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-118">The connection is open and available for statement processing.</span></span>|  
  
## <a name="sql_copt_ss_client_connection_id"></a><span data-ttu-id="8d3e3-119">SQL_COPT_SS_CLIENT_CONNECTION_ID</span><span class="sxs-lookup"><span data-stu-id="8d3e3-119">SQL_COPT_SS_CLIENT_CONNECTION_ID</span></span>  
 <span data-ttu-id="8d3e3-120">L'attributo SQL_COPT_SS_CLIENT_CONNECTION_ID consente di recuperare l'ID di connessione client che può essere utilizzato per individuare:</span><span class="sxs-lookup"><span data-stu-id="8d3e3-120">The SQL_COPT_SS_CLIENT_CONNECTION_ID attribute retrieves the client connection ID, which can then be used to locate:</span></span>  
  
-   <span data-ttu-id="8d3e3-121">Informazioni di diagnostica nel registro XEvents, se abilitato.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-121">Diagnostic information in the XEvents log, when enabled.</span></span>  
  
-   <span data-ttu-id="8d3e3-122">Informazioni sull'errore di connessione nel buffer circolare della connessione.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-122">Connection error information in the connection ring buffer.</span></span>  
  
-   <span data-ttu-id="8d3e3-123">Informazioni di diagnostica nei registri di traccia di accesso ai dati, se abilitati.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-123">Diagnostic information in the data access tracing logs, when enabled.</span></span>  
  
 <span data-ttu-id="8d3e3-124">Per ulteriori informazioni, vedere [accesso alle informazioni di diagnostica nel log degli eventi estesi](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span><span class="sxs-lookup"><span data-stu-id="8d3e3-124">For more information, see [Accessing Diagnostic Information in the Extended Events Log](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span></span>  
  
|<span data-ttu-id="8d3e3-125">Valore</span><span class="sxs-lookup"><span data-stu-id="8d3e3-125">Value</span></span>|<span data-ttu-id="8d3e3-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8d3e3-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8d3e3-127">SQL_ERROR</span><span class="sxs-lookup"><span data-stu-id="8d3e3-127">SQL_ERROR</span></span>|<span data-ttu-id="8d3e3-128">Connessione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-128">The connection failed.</span></span>|  
|<span data-ttu-id="8d3e3-129">SQL_SUCCESS</span><span class="sxs-lookup"><span data-stu-id="8d3e3-129">SQL_SUCCESS</span></span>|<span data-ttu-id="8d3e3-130">Connessione attivata.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-130">The connection succeeded.</span></span> <span data-ttu-id="8d3e3-131">L'ID di connessione client verrà trovato nel buffer di output.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-131">The client connection ID will be found in the output buffer.</span></span>|  
  
## <a name="sql_copt_ss_perf_data"></a><span data-ttu-id="8d3e3-132">SQL_COPT_SS_PERF_DATA</span><span class="sxs-lookup"><span data-stu-id="8d3e3-132">SQL_COPT_SS_PERF_DATA</span></span>  
 <span data-ttu-id="8d3e3-133">Tramite l'attributo SQL_COPT_SS_PERF_DATA viene restituito un puntatore a una struttura SQLPERF contenente le statistiche correnti sulle prestazioni del driver.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-133">The SQL_COPT_SS_PERF_DATA attribute returns a pointer to a SQLPERF structure containing the current driver performance statistics.</span></span> <span data-ttu-id="8d3e3-134">`SQLGetConnectAttr`restituisce NULL se la registrazione delle prestazioni non è abilitata.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-134">`SQLGetConnectAttr` will return NULL if performance logging is not enabled.</span></span> <span data-ttu-id="8d3e3-135">Le statistiche nella struttura SQLPERF non vengono aggiornate in modo dinamico dal driver.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-135">The statistics in the SQLPERF structure are not dynamically updated by the driver.</span></span> <span data-ttu-id="8d3e3-136">Chiamare `SQLGetConnectAttr` ogni volta che è necessario aggiornare le statistiche sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-136">Call `SQLGetConnectAttr` each time the performance statistics need to be refreshed.</span></span>  
  
|<span data-ttu-id="8d3e3-137">Valore</span><span class="sxs-lookup"><span data-stu-id="8d3e3-137">Value</span></span>|<span data-ttu-id="8d3e3-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8d3e3-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8d3e3-139">NULL</span><span class="sxs-lookup"><span data-stu-id="8d3e3-139">NULL</span></span>|<span data-ttu-id="8d3e3-140">La registrazione delle prestazioni non è abilitata.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-140">Performance logging is not enabled.</span></span>|  
|<span data-ttu-id="8d3e3-141">Qualsiasi altro valore</span><span class="sxs-lookup"><span data-stu-id="8d3e3-141">Any other value</span></span>|<span data-ttu-id="8d3e3-142">Puntatore a una struttura SQLPERF.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-142">A pointer to a SQLPERF structure.</span></span>|  
  
## <a name="sql_copt_ss_perf_query"></a><span data-ttu-id="8d3e3-143">SQL_COPT_SS_PERF_QUERY</span><span class="sxs-lookup"><span data-stu-id="8d3e3-143">SQL_COPT_SS_PERF_QUERY</span></span>  
 <span data-ttu-id="8d3e3-144">L'attributo SQL_COPT_SS_PERF_QUERY restituisce TRUE se è abilitata la registrazione di query con esecuzione prolungata.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-144">The SQL_COPT_SS_PERF_QUERY attribute returns TRUE if logging of long running queries is enabled.</span></span> <span data-ttu-id="8d3e3-145">La richiesta restituisce FALSE se la registrazione delle query non è attiva.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-145">The request returns FALSE if query logging is not active.</span></span>  
  
## <a name="sql_copt_ss_user_data"></a><span data-ttu-id="8d3e3-146">SQL_COPT_SS_USER_DATA</span><span class="sxs-lookup"><span data-stu-id="8d3e3-146">SQL_COPT_SS_USER_DATA</span></span>  
 <span data-ttu-id="8d3e3-147">L'attributo SQL_COPT_SS_USER_DATA recupera il puntatore ai dati utente.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-147">The SQL_COPT_SS_USER_DATA attribute retrieves the user-data pointer.</span></span> <span data-ttu-id="8d3e3-148">I dati utente vengono archiviati nella memoria del client e registrati per singola connessione.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-148">User data is stored in client-owned memory and recorded per connection.</span></span> <span data-ttu-id="8d3e3-149">Se il puntatore ai dati utente SQL_UD_NOTSET non è stato impostato, viene restituito un puntatore NULL.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-149">If the user-data pointer has not been set, SQL_UD_NOTSET, a NULL pointer, is returned.</span></span>  
  
|<span data-ttu-id="8d3e3-150">Valore</span><span class="sxs-lookup"><span data-stu-id="8d3e3-150">Value</span></span>|<span data-ttu-id="8d3e3-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8d3e3-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8d3e3-152">SQL_UD_NOTSET</span><span class="sxs-lookup"><span data-stu-id="8d3e3-152">SQL_UD_NOTSET</span></span>|<span data-ttu-id="8d3e3-153">Non è impostato alcun puntatore ai dati utente.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-153">No user-data pointer is set.</span></span>|  
|<span data-ttu-id="8d3e3-154">Qualsiasi altro valore</span><span class="sxs-lookup"><span data-stu-id="8d3e3-154">Any other value</span></span>|<span data-ttu-id="8d3e3-155">Puntatore ai dati utente.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-155">A pointer to the user data.</span></span>|  
  
## <a name="sqlgetconnectattr-support-for-service-principal-names-spns"></a><span data-ttu-id="8d3e3-156">Supporto di SQLSetConnectAttr per i nomi SPN (Service Principal Names)</span><span class="sxs-lookup"><span data-stu-id="8d3e3-156">SQLGetConnectAttr Support for Service Principal Names (SPNs)</span></span>  
 <span data-ttu-id="8d3e3-157">È possibile utilizzare SQLGetConnectAttr per eseguire una query sul valore dei nuovi attributi di connessione SQL_COPT_SS_SERVER_SPN, SQL_COPT_SS_FAILOVER_PARTNER_SPN, SQL_COPT_SS_MUTUALLY_AUTHENTICATED e SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-157">SQLGetConnectAttr can be used to query the value of the new connection attributes SQL_COPT_SS_SERVER_SPN, SQL_COPT_SS_FAILOVER_PARTNER_SPN, SQL_COPT_SS_MUTUALLY_AUTHENTICATED, and SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD.</span></span> <span data-ttu-id="8d3e3-158">È anche possibile usare SQLGetConnectOption per eseguire una query su questi valori.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-158">(SQLGetConnectOption can also be used to query these values.)</span></span>  
  
 <span data-ttu-id="8d3e3-159">SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD è disponibile solo per connessioni aperte che utilizzano l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="8d3e3-159">SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD is only available for open connections that use Windows Authentication.</span></span>  
  
 <span data-ttu-id="8d3e3-160">Se non è stato impostato SQL_COPT_SS_SERVER_SPN o SQL_COPT_SS_FAILOVER_PARTNER, viene restituito il valore predefinito (una stringa vuota).</span><span class="sxs-lookup"><span data-stu-id="8d3e3-160">If SQL_COPT_SS_SERVER_SPN or SQL_COPT_SS_FAILOVER_PARTNER has not been set, the default value (an empty string) is returned.</span></span>  
  
 <span data-ttu-id="8d3e3-161">Per ulteriori informazioni sui nomi SPN, vedere [nomi dell'entità servizio &#40;spn&#41; nelle connessioni Client &#40;ODBC&#41;](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="8d3e3-161">For more information about SPNs, see [Service Principal Names &#40;SPNs&#41; in Client Connections &#40;ODBC&#41;](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d3e3-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d3e3-162">See Also</span></span>  
 <span data-ttu-id="8d3e3-163">[SQLGetConnectAttr (funzione)](https://go.microsoft.com/fwlink/?LinkId=59347) </span><span class="sxs-lookup"><span data-stu-id="8d3e3-163">[SQLGetConnectAttr Function](https://go.microsoft.com/fwlink/?LinkId=59347) </span></span>  
 <span data-ttu-id="8d3e3-164">[Dettagli di implementazione dell'API ODBC](odbc-api-implementation-details.md) </span><span class="sxs-lookup"><span data-stu-id="8d3e3-164">[ODBC API Implementation Details](odbc-api-implementation-details.md) </span></span>  
 <span data-ttu-id="8d3e3-165">[IMPOSTA QUOTED_IDENTIFIER &#40;&#41;Transact-SQL](/sql/t-sql/statements/set-quoted-identifier-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8d3e3-165">[SET QUOTED_IDENTIFIER &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-quoted-identifier-transact-sql) </span></span>  
 <span data-ttu-id="8d3e3-166">[SET ANSI_NULLS &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8d3e3-166">[SET ANSI_NULLS &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql) </span></span>  
 <span data-ttu-id="8d3e3-167">[SET ANSI_PADDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-padding-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8d3e3-167">[SET ANSI_PADDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-padding-transact-sql) </span></span>  
 [<span data-ttu-id="8d3e3-168">SET ANSI_WARNINGS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8d3e3-168">SET ANSI_WARNINGS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-ansi-warnings-transact-sql)  
  
  
