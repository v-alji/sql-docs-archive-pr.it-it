---
title: Accesso di rete a un endpoint del mirroring del database
description: Informazioni su come consentire l'accesso alla rete authenticatino di Windows a un endpoint del mirroring del database per SQL Server.
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Windows authentication [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 28c8fec5-5feb-4c84-8d72-f2bd1ae3b40d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0d1d8786d128ef2cc99fe571e33f89c4c4e7699c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635722"
---
# <a name="allow-network-access-to-a-database-mirroring-endpoint-using-windows-authentication-sql-server"></a><span data-ttu-id="4ae61-103">Concessione dell'accesso alla rete a un endpoint per il mirroring del database utilizzando l'autenticazione di Windows (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4ae61-103">Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication (SQL Server)</span></span>
  <span data-ttu-id="4ae61-104">L'utilizzo dell'autenticazione di Windows per la connessione degli endpoint del mirroring di database di due istanze di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] richiede la configurazione manuale degli account di accesso nelle seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="4ae61-104">Using Windows Authentication for connecting the database mirroring endpoints of two instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] requires manual configuration of login accounts under the following conditions:</span></span>  
  
-   <span data-ttu-id="4ae61-105">Se l'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] è in esecuzione come servizi con diversi account di dominio (in domini uguali o attendibili), è necessario creare l'account di accesso di ogni account in **master** in ognuna delle istanze del server remoto e a quell'account di accesso devono essere concesse le autorizzazioni CONNECT sull'endpoint.</span><span class="sxs-lookup"><span data-stu-id="4ae61-105">If the instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] run as services under different domain accounts (in the same or trusted domains), the login of each account must be created in **master** on each of the remote server instances and that login must be granted CONNECT permissions on the endpoint.</span></span>  
  
-   <span data-ttu-id="4ae61-106">Se l'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] è in esecuzione come account del servizio di rete, l'account di accesso di ogni account del computer host (*DomainName***\\***ComputerName$* ) deve essere creato in **master** in ognuna delle istanze del server remoto e a quell'account di accesso devono essere concesse le autorizzazioni CONNECT sull'endpoint.</span><span class="sxs-lookup"><span data-stu-id="4ae61-106">If the instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] run as the Network Service account, the login of the each host computer account (*DomainName***\\***ComputerName$*) must be created in **master** on each of the remote server instances and that login must be granted CONNECT permissions on the endpoint.</span></span> <span data-ttu-id="4ae61-107">Ciò avviene in quanto un'istanza del server che è in esecuzione con l'account del servizio di rete esegue l'autenticazione utilizzando l'account di dominio del computer host.</span><span class="sxs-lookup"><span data-stu-id="4ae61-107">This is because a server instance running under the Network Service account authenticates using the domain account of the host computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4ae61-108">Assicurarsi che sia disponibile un endpoint per ogni istanza del server.</span><span class="sxs-lookup"><span data-stu-id="4ae61-108">Ensure that an endpoint exists for each of the server instances.</span></span> <span data-ttu-id="4ae61-109">Per altre informazioni, vedere [Creare un endpoint del mirroring del database per l'autenticazione Windows &#40;Transact-SQL&#41;](database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="4ae61-109">For more information, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
### <a name="to-configure-logins-for-windows-authentication"></a><span data-ttu-id="4ae61-110">Per configurare gli account di accesso per l'autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="4ae61-110">To configure logins for Windows Authentication</span></span>  
  
1.  <span data-ttu-id="4ae61-111">Per l'account utente di ogni istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], creare un account di accesso nelle altre istanze di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ae61-111">For the user account of each instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], create a login on the other instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4ae61-112">Utilizzare un'istruzione [CREATE LOGIN](/sql/t-sql/statements/create-login-transact-sql) con la clausola FROM WINDOWS.</span><span class="sxs-lookup"><span data-stu-id="4ae61-112">Use a [CREATE LOGIN](/sql/t-sql/statements/create-login-transact-sql) statement with the FROM WINDOWS clause.</span></span>  
  
     <span data-ttu-id="4ae61-113">Per altre informazioni, vedere [Creazione di un account di accesso](../relational-databases/security/authentication-access/create-a-login.md).</span><span class="sxs-lookup"><span data-stu-id="4ae61-113">For more information, see [Create a Login](../relational-databases/security/authentication-access/create-a-login.md).</span></span>  
  
2.  <span data-ttu-id="4ae61-114">Per assicurarsi inoltre che l'utente di accesso sia in grado di accedere all'endpoint, utilizzare l'istruzione [GRANT](/sql/t-sql/statements/grant-transact-sql) per concedere le autorizzazioni di connessione sull'endpoint per l'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="4ae61-114">Also, to ensure that the login user has access to the endpoint, use the [GRANT](/sql/t-sql/statements/grant-transact-sql) statement to grant connect permissions on the endpoint to the login.</span></span> <span data-ttu-id="4ae61-115">Si noti che la concessione di autorizzazioni di accesso per l'endpoint non è necessaria se l'utente è un amministratore.</span><span class="sxs-lookup"><span data-stu-id="4ae61-115">Note that granting connect permissions to the endpoint is unnecessary if the user is an Administrator.</span></span>  
  
     <span data-ttu-id="4ae61-116">Per altre informazioni, vedere [Grant a Permission to a Principal](../relational-databases/security/authentication-access/grant-a-permission-to-a-principal.md).</span><span class="sxs-lookup"><span data-stu-id="4ae61-116">For more information, see [Grant a Permission to a Principal](../relational-databases/security/authentication-access/grant-a-permission-to-a-principal.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ae61-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="4ae61-117">Example</span></span>  
 <span data-ttu-id="4ae61-118">Nel seguente esempio [!INCLUDE[tsql](../includes/tsql-md.md)] viene creato un account di accesso [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] per un account utente denominato `Otheruser` che appartiene a un dominio denominato `Adomain`.</span><span class="sxs-lookup"><span data-stu-id="4ae61-118">The following [!INCLUDE[tsql](../includes/tsql-md.md)] example creates a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login for a user account named `Otheruser` that belongs to a domain called `Adomain`.</span></span> <span data-ttu-id="4ae61-119">Nell'esempio vengono quindi concesse all'utente autorizzazioni per la connessione a un endpoint di mirroring del database preesistente denominato `Mirroring_Endpoint`.</span><span class="sxs-lookup"><span data-stu-id="4ae61-119">The example then grants this user connect permissions to a pre-existing database mirroring endpoint named `Mirroring_Endpoint`.</span></span>  
  
```  
USE master;  
GO  
CREATE LOGIN [Adomain\Otheruser] FROM WINDOWS;  
GO  
GRANT CONNECT on ENDPOINT::Mirroring_Endpoint TO [Adomain\Otheruser];  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ae61-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ae61-120">See Also</span></span>  
 <span data-ttu-id="4ae61-121">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4ae61-121">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="4ae61-122">[Mirroring del database &#40;SQL Server&#41;](database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4ae61-122">[Database Mirroring &#40;SQL Server&#41;](database-mirroring/database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="4ae61-123">[Sicurezza del trasporto per il mirroring del database e Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](database-mirroring/transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="4ae61-123">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](database-mirroring/transport-security-database-mirroring-always-on-availability.md) </span></span>  
 [<span data-ttu-id="4ae61-124">Endpoint del mirroring del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4ae61-124">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](database-mirroring/the-database-mirroring-endpoint-sql-server.md)  
  
  
