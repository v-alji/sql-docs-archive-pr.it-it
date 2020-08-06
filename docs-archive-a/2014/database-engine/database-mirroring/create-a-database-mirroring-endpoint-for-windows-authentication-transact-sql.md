---
title: Creare un endpoint del mirroring del database per l'autenticazione Windows (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- database mirroring [SQL Server], endpoint
- endpoints [SQL Server], database mirroring
- Windows authentication [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: baf1a4b1-6790-4275-b261-490bca33bdb9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5558bc5684f2eb9053c935543db0c05d6225daf7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626280"
---
# <a name="create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql"></a><span data-ttu-id="12991-102">Creare un endpoint del mirroring del database per l'autenticazione Windows (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="12991-102">Create a Database Mirroring Endpoint for Windows Authentication (Transact-SQL)</span></span>
  <span data-ttu-id="12991-103">In questo argomento si illustra come creare un endpoint del mirroring del database in cui si utilizza l'autenticazione di Windows in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12991-103">This topic describes how to create a database mirroring endpoint that uses Windows Authentication in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="12991-104">Per supportare il mirroring del database o [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] , per ogni istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è necessario un endpoint del mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="12991-104">To support database mirroring or [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] each instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requires a database mirroring endpoint.</span></span> <span data-ttu-id="12991-105">In un'istanza del server può essere incluso uno solo di questo tipo di endpoint, che a sua volta dispone di una sola porta.</span><span class="sxs-lookup"><span data-stu-id="12991-105">A server instance can have only one database mirroring endpoint, which has a single port.</span></span> <span data-ttu-id="12991-106">Un endpoint del mirroring del database può utilizzare qualsiasi porta disponibile nel sistema locale al momento della creazione dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="12991-106">A database mirroring endpoint can use any port that is available on the local system when the endpoint is created.</span></span> <span data-ttu-id="12991-107">Tutte le sessioni di mirroring del database in un'istanza del server sono in attesa su quella porta, che viene utilizzata anche per tutte le connessioni in ingresso per il mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="12991-107">All database mirroring sessions on a server instance listen on that port, and all incoming connections for database mirroring use that port.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="12991-108">Se un endpoint del mirroring del database è presente e già in uso, è consigliabile utilizzare quello.</span><span class="sxs-lookup"><span data-stu-id="12991-108">If a database mirroring endpoint exists and is already in use, we recommend that you use that endpoint.</span></span> <span data-ttu-id="12991-109">L'eliminazione di un endpoint in uso determina la chiusura delle sessioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="12991-109">Dropping an in-use endpoint disrupts existing sessions.</span></span>  
  
 <span data-ttu-id="12991-110">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="12991-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="12991-111">**Prima di iniziare:**  [Sicurezza](#Security)</span><span class="sxs-lookup"><span data-stu-id="12991-111">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="12991-112">**Per creare un endpoint del mirroring del database usando:**  [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="12991-112">**To create a database mirroring endpoint, using:**  [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="12991-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="12991-113">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="12991-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="12991-114">Security</span></span>  
 <span data-ttu-id="12991-115">I metodi di autenticazione e crittografia dell'istanza del server sono stabiliti dall'amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="12991-115">The authentication and encryption methods of the server instance are established by the system administrator.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="12991-116">L'algoritmo RC4 è deprecato.</span><span class="sxs-lookup"><span data-stu-id="12991-116">The RC4 algorithm is deprecated.</span></span> [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="12991-117">È consigliabile utilizzare AES.</span><span class="sxs-lookup"><span data-stu-id="12991-117">We recommend that you use AES.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="12991-118">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="12991-118">Permissions</span></span>  
 <span data-ttu-id="12991-119">È richiesta l'autorizzazione CREATE ENDPOINT o l'appartenenza al ruolo predefinito del server sysadmin.</span><span class="sxs-lookup"><span data-stu-id="12991-119">Requires CREATE ENDPOINT permission, or membership in the sysadmin fixed server role.</span></span> <span data-ttu-id="12991-120">Per altre informazioni, vedere [GRANT - autorizzazioni per endpoint &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="12991-120">For more information, see [GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="12991-121">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="12991-121">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-database-mirroring-endpoint-that-uses-windows-authentication"></a><span data-ttu-id="12991-122">Per creare un endpoint del mirroring del database in cui viene utilizzata l'autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="12991-122">To Create a Database Mirroring Endpoint That Uses Windows Authentication</span></span>  
  
1.  <span data-ttu-id="12991-123">Connettersi all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in cui si desidera creare un endpoint del mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="12991-123">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on which you want to create a database mirroring endpoint.</span></span>  
  
2.  <span data-ttu-id="12991-124">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="12991-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="12991-125">Per determinare se esiste già un endpoint del mirroring del database, utilizzare l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="12991-125">Determine if a database mirroring endpoint already exists by using the following statement:</span></span>  
  
    ```sql
    SELECT name, role_desc, state_desc FROM sys.database_mirroring_endpoints;
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="12991-126">Se per l'istanza del server esiste già un endpoint del mirroring, utilizzarlo per tutte le altre sessioni stabilite nell'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="12991-126">If a database mirroring endpoint already exists for the server instance, use that endpoint for any other sessions you establish on the server instance.</span></span>  
  
4.  <span data-ttu-id="12991-127">Per creare un endpoint utilizzabile con l'autenticazione di Windows, eseguire un'istruzione Transact-SQL CREATE ENDPOINT,</span><span class="sxs-lookup"><span data-stu-id="12991-127">To use Transact-SQL to create an endpoint to use with Windows Authentication, use a CREATE ENDPOINT statement.</span></span> <span data-ttu-id="12991-128">Il formato generale dell'istruzione è il seguente:</span><span class="sxs-lookup"><span data-stu-id="12991-128">The statement takes the following general form:</span></span>  
  
     <span data-ttu-id="12991-129">CREATE ENDPOINT *\<endpointName>*</span><span class="sxs-lookup"><span data-stu-id="12991-129">CREATE ENDPOINT *\<endpointName>*</span></span>  
  
     <span data-ttu-id="12991-130">STATE=STARTED</span><span class="sxs-lookup"><span data-stu-id="12991-130">STATE=STARTED</span></span>  
  
     <span data-ttu-id="12991-131">AS TCP ( LISTENER_PORT = *\<listenerPortList>* )</span><span class="sxs-lookup"><span data-stu-id="12991-131">AS TCP ( LISTENER_PORT = *\<listenerPortList>* )</span></span>  
  
     <span data-ttu-id="12991-132">FOR DATABASE_MIRRORING</span><span class="sxs-lookup"><span data-stu-id="12991-132">FOR DATABASE_MIRRORING</span></span>  
  
     <span data-ttu-id="12991-133">(</span><span class="sxs-lookup"><span data-stu-id="12991-133">(</span></span>  
  
     <span data-ttu-id="12991-134">[ AUTHENTICATION = **WINDOWS** [ *\<authorizationMethod>* ]</span><span class="sxs-lookup"><span data-stu-id="12991-134">[ AUTHENTICATION = **WINDOWS** [ *\<authorizationMethod>* ]</span></span>  
  
     <span data-ttu-id="12991-135">]</span><span class="sxs-lookup"><span data-stu-id="12991-135">]</span></span>  
  
     <span data-ttu-id="12991-136">[ [ **,** ] ENCRYPTION = **REQUIRED**</span><span class="sxs-lookup"><span data-stu-id="12991-136">[ [**,**] ENCRYPTION = **REQUIRED**</span></span>  
  
     <span data-ttu-id="12991-137">[ ALGORITHM { *\<algorithm>* } ]</span><span class="sxs-lookup"><span data-stu-id="12991-137">[ ALGORITHM { *\<algorithm>* } ]</span></span>  
  
     <span data-ttu-id="12991-138">]</span><span class="sxs-lookup"><span data-stu-id="12991-138">]</span></span>  
  
     <span data-ttu-id="12991-139">[ **,** ] ROLE = *\<role>*</span><span class="sxs-lookup"><span data-stu-id="12991-139">[**,**] ROLE = *\<role>*</span></span>  
  
     <span data-ttu-id="12991-140">)</span><span class="sxs-lookup"><span data-stu-id="12991-140">)</span></span>  
  
     <span data-ttu-id="12991-141">dove</span><span class="sxs-lookup"><span data-stu-id="12991-141">where</span></span>  
  
    -   <span data-ttu-id="12991-142">*\<endpointName>* è un nome univoco per l'endpoint del mirroring del database dell'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="12991-142">*\<endpointName>* is a unique name for the database mirroring endpoint of the server instance.</span></span>  
  
    -   <span data-ttu-id="12991-143">STARTED indica che l'endpoint deve essere avviato e deve rimanere in attesa delle connessioni.</span><span class="sxs-lookup"><span data-stu-id="12991-143">STARTED specifies that the endpoint is to be started and to begin listening for connections.</span></span> <span data-ttu-id="12991-144">Lo stato di un endpoint del mirroring del database creato è in genere STARTED.</span><span class="sxs-lookup"><span data-stu-id="12991-144">A database mirroring endpoint typically is created in the STARTED state.</span></span> <span data-ttu-id="12991-145">In alternativa, è possibile avviare una sessione nello stato STOPPED (impostazione predefinita) o DISABLED.</span><span class="sxs-lookup"><span data-stu-id="12991-145">Alternatively, you can start a session in a STOPPED state (the default) or DISABLED state.</span></span>  
  
    -   <span data-ttu-id="12991-146">*\<listenerPortList>* è un singolo numero di porta (*nnn*) su cui si vuole che il server riceva i messaggi di mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="12991-146">*\<listenerPortList>* is a single port number (*nnnn*) on which you want the server to listen for database mirroring messages.</span></span> <span data-ttu-id="12991-147">È consentito solo il protocollo TCP. Tutti gli altri protocolli restituiranno un errore.</span><span class="sxs-lookup"><span data-stu-id="12991-147">Only TCP is allowed; specifying any other protocol causes an error.</span></span>  
  
         <span data-ttu-id="12991-148">È possibile utilizzare un numero di porta una sola volta per ciascun computer.</span><span class="sxs-lookup"><span data-stu-id="12991-148">A port number can be used only once per computer system.</span></span> <span data-ttu-id="12991-149">Un endpoint del mirroring del database può utilizzare qualsiasi porta disponibile nel sistema locale al momento della creazione dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="12991-149">A database mirroring endpoint can use any port that is available on the local system when the endpoint is created.</span></span> <span data-ttu-id="12991-150">Per identificare le porte attualmente utilizzate dagli endpoint TCP nel sistema, utilizzare l'istruzione Transact-SQL seguente:</span><span class="sxs-lookup"><span data-stu-id="12991-150">To identify the ports currently being used by TCP endpoints on the system, use the following Transact-SQL statement:</span></span>  
  
        ```  
        SELECT name, port FROM sys.tcp_endpoints;  
        ```  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="12991-151">In ogni istanza del server è necessaria un'unica porta di attesa univoca.</span><span class="sxs-lookup"><span data-stu-id="12991-151">Each server instance requires one and only one unique listener port.</span></span>  
  
    -   <span data-ttu-id="12991-152">Per l'autenticazione di Windows, l'opzione AUTHENTICATION è facoltativa, a meno che non si desideri che l'endpoint utilizzi solo NTLM o Kerberos per autenticare connessioni.</span><span class="sxs-lookup"><span data-stu-id="12991-152">For Windows Authentication, the AUTHENTICATION option is optional, unless you want the endpoint to use only NTLM or Kerberos to authenticate connections.</span></span> <span data-ttu-id="12991-153">*\<authorizationMethod>* specifica uno dei metodi seguenti usato per autenticare le connessioni: NTLM, KERBEROS o NEGOTIATE.</span><span class="sxs-lookup"><span data-stu-id="12991-153">*\<authorizationMethod>* specifies the method used to authenticate connections as one of the following: NTLM, KERBEROS, or NEGOTIATE.</span></span> <span data-ttu-id="12991-154">Con il metodo predefinito NEGOTIATE l'endpoint utilizzerà il protocollo di negoziazione di Windows per scegliere tra NTLM e Kerberos.</span><span class="sxs-lookup"><span data-stu-id="12991-154">The default, NEGOTIATE, causes the endpoint to use the Windows negotiation protocol to choose either NTLM or Kerberos.</span></span> <span data-ttu-id="12991-155">La negoziazione consente di utilizzare le connessioni con o senza autenticazione, a seconda del livello di autenticazione dell'endpoint opposto.</span><span class="sxs-lookup"><span data-stu-id="12991-155">Negotiation enables connections with or without authentication, depending on the authentication level of the opposite endpoint.</span></span>  
  
    -   <span data-ttu-id="12991-156">Per impostazione predefinita, ENCRYPTION è impostato su REQUIRED,</span><span class="sxs-lookup"><span data-stu-id="12991-156">ENCRYPTION is set to REQUIRED by default.</span></span> <span data-ttu-id="12991-157">pertanto verrà utilizzata la crittografia per tutte le connessioni a questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="12991-157">This means that all connections to this endpoint must use encryption.</span></span> <span data-ttu-id="12991-158">È tuttavia possibile disabilitare la crittografia o renderla facoltativa in un endpoint.</span><span class="sxs-lookup"><span data-stu-id="12991-158">However, you can disable encryption or make it optional on an endpoint.</span></span> <span data-ttu-id="12991-159">Sono disponibili le alternative seguenti:</span><span class="sxs-lookup"><span data-stu-id="12991-159">The alternatives are as follows:</span></span>  
  
        |<span data-ttu-id="12991-160">valore</span><span class="sxs-lookup"><span data-stu-id="12991-160">Value</span></span>|<span data-ttu-id="12991-161">Definizione</span><span class="sxs-lookup"><span data-stu-id="12991-161">Definition</span></span>|  
        |-----------|----------------|  
        |<span data-ttu-id="12991-162">DISABLED</span><span class="sxs-lookup"><span data-stu-id="12991-162">DISABLED</span></span>|<span data-ttu-id="12991-163">Specifica che i dati inviati tramite una connessione non vengano crittografati.</span><span class="sxs-lookup"><span data-stu-id="12991-163">Specifies that data sent over a connection is not encrypted.</span></span>|  
        |<span data-ttu-id="12991-164">SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="12991-164">SUPPORTED</span></span>|<span data-ttu-id="12991-165">Specifica che i dati vengano crittografati solo se per l'endpoint opposto è stato specificato SUPPORTED o REQUIRED.</span><span class="sxs-lookup"><span data-stu-id="12991-165">Specifies that the data is encrypted only if the opposite endpoint specifies either SUPPORTED or REQUIRED.</span></span>|  
        |<span data-ttu-id="12991-166">REQUIRED</span><span class="sxs-lookup"><span data-stu-id="12991-166">REQUIRED</span></span>|<span data-ttu-id="12991-167">Specifica che i dati inviati tramite una connessione devono essere crittografati.</span><span class="sxs-lookup"><span data-stu-id="12991-167">Specifies that data sent over a connection must be encrypted.</span></span>|  
  
         <span data-ttu-id="12991-168">Se è necessaria la crittografia per un endpoint, ENCRYPTION deve essere impostato su SUPPORTED o REQUIRED nell'altro endpoint.</span><span class="sxs-lookup"><span data-stu-id="12991-168">If an endpoint requires encryption, the other endpoint must have ENCRYPTION set to either SUPPORTED or REQUIRED.</span></span>  
  
    -   <span data-ttu-id="12991-169">*\<algorithm>* consente di specificare gli standard di crittografia per l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="12991-169">*\<algorithm>* provides the option of specifying the encryption standards for the endpoint.</span></span> <span data-ttu-id="12991-170">Il valore di *\<algorithm>* può essere uno degli algoritmi o delle combinazioni di algoritmi seguenti: RC4, AES, AES RC4 o RC4 AES.</span><span class="sxs-lookup"><span data-stu-id="12991-170">The value of *\<algorithm>* can be one following algorithms or combinations of algorithms: RC4, AES, AES RC4, or RC4 AES.</span></span>  
  
         <span data-ttu-id="12991-171">AES RC4 indica che questo endpoint negozierà l'algoritmo di crittografia, dando la preferenza a quello AES.</span><span class="sxs-lookup"><span data-stu-id="12991-171">AES RC4 specifies that this endpoint will negotiate for the encryption algorithm, giving preference to the AES algorithm.</span></span> <span data-ttu-id="12991-172">RC4 AES indica che questo endpoint negozierà l'algoritmo di crittografia, dando la preferenza all'algoritmo RC4.</span><span class="sxs-lookup"><span data-stu-id="12991-172">RC4 AES specifies that this endpoint will negotiate for the encryption algorithm, giving preference to the RC4 algorithm.</span></span> <span data-ttu-id="12991-173">Se i due endpoint specificano entrambi gli algoritmi, ma con un ordine diverso, l'algoritmo verrà definito dall'endpoint che accetta la connessione.</span><span class="sxs-lookup"><span data-stu-id="12991-173">If both endpoints specify both algorithms but in different orders, the endpoint accepting the connection wins.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="12991-174">L'algoritmo RC4 è deprecato.</span><span class="sxs-lookup"><span data-stu-id="12991-174">The RC4 algorithm is deprecated.</span></span> [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="12991-175">È consigliabile utilizzare AES.</span><span class="sxs-lookup"><span data-stu-id="12991-175">We recommend that you use AES.</span></span>  
  
    -   <span data-ttu-id="12991-176">*\<role>* definisce i ruoli eseguibili tramite il server.</span><span class="sxs-lookup"><span data-stu-id="12991-176">*\<role>* defines the role or roles that the server can perform.</span></span> <span data-ttu-id="12991-177">Il valore di ROLE deve essere specificato.</span><span class="sxs-lookup"><span data-stu-id="12991-177">Specifying ROLE is required.</span></span> <span data-ttu-id="12991-178">Tuttavia, il ruolo dell'endpoint è rilevante solo per il mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="12991-178">However, the role of the endpoint is relevant only for database mirroring.</span></span> <span data-ttu-id="12991-179">Per [!INCLUDE[ssHADR](../../includes/sshadr-md.md)], viene ignorato il ruolo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="12991-179">For [!INCLUDE[ssHADR](../../includes/sshadr-md.md)], the role of the endpoint is ignored.</span></span>  
  
         <span data-ttu-id="12991-180">Per consentire a un'istanza del server di utilizzare un ruolo per una sessione di mirroring del database e un altro ruolo per un'altra sessione, specificare ROLE=ALL.</span><span class="sxs-lookup"><span data-stu-id="12991-180">To allow a server instance to serve as one role for one database mirroring session and different role for another session, specify ROLE=ALL.</span></span> <span data-ttu-id="12991-181">Per limitare un'istanza del server in modo che funga da partner o da server di controllo del mirroring, specificare rispettivamente ROLE=PARTNER o ROLE=WITNESS.</span><span class="sxs-lookup"><span data-stu-id="12991-181">To restrict a server instance to being either a partner or a witness, specify ROLE=PARTNER or ROLE=WITNESS, respectively.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="12991-182">Per ulteriori informazioni sulle opzioni di mirroring del database per le diverse edizioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vedere [funzionalità supportate dalle edizioni di SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="12991-182">For more information about Database Mirroring options for different editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
     <span data-ttu-id="12991-183">Per una descrizione completa della sintassi di CREATE ENDPOINT, vedere [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="12991-183">For a complete description of the CREATE ENDPOINT syntax, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="12991-184">Per modificare un endpoint esistente, usare [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="12991-184">To change an existing endpoint, use [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span></span>  
  
###  <a name="example-creating-endpoints-to-support-for-database-mirroring-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="12991-185">Esempio: Creazione di endpoint per supportare il mirroring del database (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="12991-185">Example: Creating Endpoints to Support for Database Mirroring (Transact-SQL)</span></span>  
 <span data-ttu-id="12991-186">Nell'esempio seguente si creano endpoint del mirroring del database per le istanze del server predefinite in tre sistemi di computer distinti:</span><span class="sxs-lookup"><span data-stu-id="12991-186">The following example creates database mirroring endpoints for the default server instances on three separate computer systems:</span></span>  
  
|<span data-ttu-id="12991-187">Ruolo dell'istanza del server</span><span class="sxs-lookup"><span data-stu-id="12991-187">Role of server instance</span></span>|<span data-ttu-id="12991-188">Nome del computer host</span><span class="sxs-lookup"><span data-stu-id="12991-188">Name of host computer</span></span>|  
|-----------------------------|---------------------------|  
|<span data-ttu-id="12991-189">Partner (inizialmente nel ruolo principale)</span><span class="sxs-lookup"><span data-stu-id="12991-189">Partner (initially in the principal role)</span></span>|`SQLHOST01\.`|  
|<span data-ttu-id="12991-190">Partner (inizialmente nel ruolo mirror)</span><span class="sxs-lookup"><span data-stu-id="12991-190">Partner (initially in the mirror role)</span></span>|`SQLHOST02\.`|  
|<span data-ttu-id="12991-191">Controllo</span><span class="sxs-lookup"><span data-stu-id="12991-191">Witness</span></span>|`SQLHOST03\.`|  
  
 <span data-ttu-id="12991-192">Nell'esempio tutti e tre gli endpoint utilizzano la porta numero 7022, anche se qualunque numero di porta disponibile sarebbe utilizzabile.</span><span class="sxs-lookup"><span data-stu-id="12991-192">In this example, all three endpoints use port number 7022, though any available port number would work.</span></span> <span data-ttu-id="12991-193">L'opzione AUTHENTICATION non è necessaria, in quanto gli endpoint utilizzano il tipo predefinito, autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="12991-193">The AUTHENTICATION option is unnecessary, because the endpoints use the default type, Windows Authentication.</span></span> <span data-ttu-id="12991-194">L'opzione ENCRYPTION è anch'essa superflua, in quanto gli endpoint sono tutti progettati per negoziare il metodo di autenticazione per una connessione, che rappresenta il comportamento predefinito per autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="12991-194">The ENCRYPTION option is also unnecessary, because the endpoints are all intended to negotiate the authentication method for a connection, which is the default behavior for Windows Authentication.</span></span> <span data-ttu-id="12991-195">Inoltre, tutti gli endpoint richiedono la crittografia, che rappresenta il comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="12991-195">Also, all of the endpoints require the encryption, which is the default behavior.</span></span>  
  
 <span data-ttu-id="12991-196">Ogni istanza del server è limitata a fungere da partner o da server di controllo e l'endpoint di ogni server specifica espressamente il ruolo (ROLE=PARTNER o ROLE=WITNESS).</span><span class="sxs-lookup"><span data-stu-id="12991-196">Each server instance is limited to serving as either a partner or a witness, and the endpoint of each server expressly specifies which role (ROLE=PARTNER or ROLE=WITNESS).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="12991-197">Ogni istanza del server può includere un solo endpoint.</span><span class="sxs-lookup"><span data-stu-id="12991-197">Each server instance can have only one endpoint.</span></span> <span data-ttu-id="12991-198">Pertanto, se si desidera che un'istanza del server sia partner in alcune sessioni e server di controllo in altre, specificare ROLE=ALL.</span><span class="sxs-lookup"><span data-stu-id="12991-198">Therefore, if you want a server instance to be a partner in some sessions and the witness in others, specify ROLE=ALL.</span></span>  
  
```sql
--Endpoint for initial principal server instance, which  
--is the only server instance running on SQLHOST01.  
CREATE ENDPOINT endpoint_mirroring  
    STATE = STARTED  
    AS TCP ( LISTENER_PORT = 7022 )  
    FOR DATABASE_MIRRORING (ROLE=PARTNER);  
GO  
--Endpoint for initial mirror server instance, which  
--is the only server instance running on SQLHOST02.  
CREATE ENDPOINT endpoint_mirroring  
    STATE = STARTED  
    AS TCP ( LISTENER_PORT = 7022 )  
    FOR DATABASE_MIRRORING (ROLE=PARTNER);  
GO  
--Endpoint for witness server instance, which  
--is the only server instance running on SQLHOST03.  
CREATE ENDPOINT endpoint_mirroring  
    STATE = STARTED  
    AS TCP ( LISTENER_PORT = 7022 )  
    FOR DATABASE_MIRRORING (ROLE=WITNESS);  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="12991-199">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="12991-199">Related Tasks</span></span>  

### <a name="to-configure-a-database-mirroring-endpoint"></a><span data-ttu-id="12991-200">Per configurare un endpoint del mirroring del database</span><span class="sxs-lookup"><span data-stu-id="12991-200">To Configure a Database Mirroring Endpoint</span></span>
  
-   [<span data-ttu-id="12991-201">Creazione di un endpoint del mirroring del database per Gruppi di disponibilità AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="12991-201">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](../availability-groups/windows/database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="12991-202">Utilizzare certificati per un endpoint del mirroring del database &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="12991-202">Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;</span></span>](use-certificates-for-a-database-mirroring-endpoint-transact-sql.md)  
  
    -   [<span data-ttu-id="12991-203">Impostazione dell'endpoint del mirroring del database per l'utilizzo di certificati per le connessioni in uscita &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="12991-203">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-outbound-connections.md)  
  
    -   [<span data-ttu-id="12991-204">Impostazione dell'endpoint del mirroring del database per l'utilizzo di certificati per le connessioni in ingresso &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="12991-204">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="12991-205">Specificare un indirizzo di rete del server &#40;Mirroring del database&#41;</span><span class="sxs-lookup"><span data-stu-id="12991-205">Specify a Server Network Address &#40;Database Mirroring&#41;</span></span>](specify-a-server-network-address-database-mirroring.md)  
  
-   [<span data-ttu-id="12991-206">Specifica dell'URL dell'endpoint quando si aggiunge o si modifica una replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="12991-206">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](../availability-groups/windows/specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
 <span data-ttu-id="12991-207">**Per visualizzare informazioni sull'endpoint del mirroring del database**</span><span class="sxs-lookup"><span data-stu-id="12991-207">**To View Information About the Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="12991-208">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="12991-208">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="12991-209">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12991-209">See Also</span></span>  
 <span data-ttu-id="12991-210">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="12991-210">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="12991-211">[Scelta di un algoritmo di crittografia](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="12991-211">[Choose an Encryption Algorithm](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md) </span></span>  
 <span data-ttu-id="12991-212">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="12991-212">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="12991-213">[Specificare un indirizzo di rete del server &#40;Mirroring del database&#41;](specify-a-server-network-address-database-mirroring.md) </span><span class="sxs-lookup"><span data-stu-id="12991-213">[Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md) </span></span>  
 <span data-ttu-id="12991-214">[Esempio: Configurazione del mirroring del database tramite l'autenticazione di Windows &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="12991-214">[Example: Setting Up Database Mirroring Using Windows Authentication &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-windows-authentication-transact-sql.md) </span></span>  
 [<span data-ttu-id="12991-215">Endpoint del mirroring del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="12991-215">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](the-database-mirroring-endpoint-sql-server.md)  
