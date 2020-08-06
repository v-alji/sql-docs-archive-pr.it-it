---
title: Usare certificati per un endpoint del mirroring del database (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- certificates [SQL Server], database mirroring
- authentication [SQL Server], database mirroring
- database mirroring [SQL Server], security
ms.assetid: f7c23cc2-48dc-4b78-b441-89ca29a0bd9e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c159e66e798524c41bf6e653283c299cc8393be5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627384"
---
# <a name="use-certificates-for-a-database-mirroring-endpoint-transact-sql"></a><span data-ttu-id="493f4-102">Utilizzare certificati per un endpoint del mirroring del database (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="493f4-102">Use Certificates for a Database Mirroring Endpoint (Transact-SQL)</span></span>
  <span data-ttu-id="493f4-103">Per abilitare l'autenticazione del certificato per il mirroring del database in una determinata istanza del server, l'amministratore di sistema deve configurare ogni istanza del server per l'utilizzo dei certificati nelle connessioni in uscita e in ingresso.</span><span class="sxs-lookup"><span data-stu-id="493f4-103">To enable certificate authentication for database mirroring on a given server instance, the system administrator must configure each server instance to use certificates on both outbound and inbound connections.</span></span> <span data-ttu-id="493f4-104">Le connessioni in uscita devono essere configurate per prime.</span><span class="sxs-lookup"><span data-stu-id="493f4-104">Outbound connections must be configured first.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="493f4-105">Tutte le connessioni per il mirroring in un'istanza del server utilizzano un singolo endpoint del mirroring del database ed è necessario specificare il metodo di autenticazione dell'istanza del server quando si crea l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="493f4-105">All mirroring connections on a server instance use a single database mirroring endpoint, and you must specify the authentication method of the server instance when you create the endpoint.</span></span> <span data-ttu-id="493f4-106">È pertanto possibile utilizzare un solo metodo di autenticazione per istanza di server per il mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="493f4-106">Therefore, you can use only one form of authentication per server instance for database mirroring.</span></span>  
  
## <a name="configuring-outbound-connections"></a><span data-ttu-id="493f4-107">Configurazione delle connessioni in uscita</span><span class="sxs-lookup"><span data-stu-id="493f4-107">Configuring Outbound Connections</span></span>  
 <span data-ttu-id="493f4-108">Per ogni istanza del server che si sta configurando per il mirroring del database eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="493f4-108">Follow these steps on each server instance that you are configuring for database mirroring:</span></span>  
  
1.  <span data-ttu-id="493f4-109">Nel database **master** creare una chiave master del database.</span><span class="sxs-lookup"><span data-stu-id="493f4-109">In the **master** database, create a database master key.</span></span>  
  
2.  <span data-ttu-id="493f4-110">Nel database **master** creare un certificato crittografato nell'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="493f4-110">In the **master** database, create an encrypted certificate on the server instance.</span></span>  
  
3.  <span data-ttu-id="493f4-111">Creare un endpoint per l'istanza del server utilizzando il relativo certificato.</span><span class="sxs-lookup"><span data-stu-id="493f4-111">Create an endpoint for the server instance using its certificate.</span></span>  
  
4.  <span data-ttu-id="493f4-112">Eseguire il backup del certificato in un file e copiarlo nell'altro sistema o negli altri sistemi.</span><span class="sxs-lookup"><span data-stu-id="493f4-112">Back up the certificate to a file and securely copy it to the other system or systems.</span></span>  
  
 <span data-ttu-id="493f4-113">È necessario eseguire questa procedura per ogni partner e per il server di controllo del mirroring, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="493f4-113">You must complete these steps for each partner and the witness, if there is one.</span></span>  
  
 <span data-ttu-id="493f4-114">Per altre informazioni, vedere [Impostare l'endpoint del mirroring del database per l'uso di certificati per le connessioni in uscita &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="493f4-114">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
## <a name="configuring-inbound-connections"></a><span data-ttu-id="493f4-115">Configurazione delle connessioni in ingresso</span><span class="sxs-lookup"><span data-stu-id="493f4-115">Configuring Inbound Connections</span></span>  
 <span data-ttu-id="493f4-116">Eseguire quindi la procedura seguente per ogni partner che si sta configurando per il mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="493f4-116">Next, follow these steps for each partner that you are configuring for database mirroring.</span></span> <span data-ttu-id="493f4-117">Nel database **master** :</span><span class="sxs-lookup"><span data-stu-id="493f4-117">In the **master** database:</span></span>  
  
1.  <span data-ttu-id="493f4-118">Creare un account di accesso per l'altro sistema.</span><span class="sxs-lookup"><span data-stu-id="493f4-118">Create a login for the other system.</span></span>  
  
2.  <span data-ttu-id="493f4-119">Creare un utente per tale account di accesso.</span><span class="sxs-lookup"><span data-stu-id="493f4-119">Create a user for that login.</span></span>  
  
3.  <span data-ttu-id="493f4-120">Ottenere il certificato per l'endpoint del mirroring dell'altra istanza del server.</span><span class="sxs-lookup"><span data-stu-id="493f4-120">Obtain the certificate for the mirroring endpoint of the other server instance.</span></span>  
  
4.  <span data-ttu-id="493f4-121">Associare il certificato all'utente creato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="493f4-121">Associate the certificate with the user created in step 2.</span></span>  
  
5.  <span data-ttu-id="493f4-122">Concedere l'autorizzazione CONNECT all'account di accesso per l'endpoint del mirroring.</span><span class="sxs-lookup"><span data-stu-id="493f4-122">Grant CONNECT permission on the login for that mirroring endpoint.</span></span>  
  
 <span data-ttu-id="493f4-123">Se è disponibile un server di controllo del mirroring, è necessario configurare le connessioni in ingresso anche per tale server.</span><span class="sxs-lookup"><span data-stu-id="493f4-123">If there is a witness, you must also set up inbound connections for it.</span></span> <span data-ttu-id="493f4-124">Questa operazione prevede la configurazione di account di accesso, utenti e certificati per il server di controllo del mirroring in entrambi i partner, e viceversa.</span><span class="sxs-lookup"><span data-stu-id="493f4-124">This requires setting up logins, users, and certificates for the witness on both of the partners, and vice versa.</span></span>  
  
 <span data-ttu-id="493f4-125">Per altre informazioni, vedere [Impostazione dell'endpoint del mirroring del database per l'utilizzo di certificati per le connessioni in ingresso &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="493f4-125">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="493f4-126">Security</span><span class="sxs-lookup"><span data-stu-id="493f4-126">Security</span></span>  
 <span data-ttu-id="493f4-127">A meno che la sicurezza della rete in uso non sia già garantita, è consigliabile utilizzare la crittografia per le connessioni per il mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="493f4-127">Unless you can guarantee that your network is secure, we recommend that you use encryption for database mirroring connections.</span></span> <span data-ttu-id="493f4-128">Per altre informazioni, vedere [Endpoint del mirroring del database &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="493f4-128">For more information, see [The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md).</span></span>  
  
 <span data-ttu-id="493f4-129">Quando si copia un certificato in un altro sistema, utilizzare un metodo di copia sicuro.</span><span class="sxs-lookup"><span data-stu-id="493f4-129">When copying a certificate to another system, use a secure copy method.</span></span> <span data-ttu-id="493f4-130">È estremamente importante garantire la protezione di tutti i certificati.</span><span class="sxs-lookup"><span data-stu-id="493f4-130">Be extremely careful to keep all of your certificates secure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="493f4-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="493f4-131">See Also</span></span>  
 <span data-ttu-id="493f4-132">[Creazione della chiave master di un database](../../relational-databases/security/encryption/create-a-database-master-key.md) </span><span class="sxs-lookup"><span data-stu-id="493f4-132">[Create a Database Master Key](../../relational-databases/security/encryption/create-a-database-master-key.md) </span></span>  
 <span data-ttu-id="493f4-133">[CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="493f4-133">[CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) </span></span>  
 <span data-ttu-id="493f4-134">[Sicurezza del trasporto per il mirroring del database e Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="493f4-134">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="493f4-135">[Centro di sicurezza per il motore di database di SQL Server e il database SQL di Azure](../../relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database.md) </span><span class="sxs-lookup"><span data-stu-id="493f4-135">[Security Center for SQL Server Database Engine and Azure SQL Database](../../relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database.md) </span></span>  
 [<span data-ttu-id="493f4-136">Endpoint del mirroring del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="493f4-136">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](the-database-mirroring-endpoint-sql-server.md)  
  
  
