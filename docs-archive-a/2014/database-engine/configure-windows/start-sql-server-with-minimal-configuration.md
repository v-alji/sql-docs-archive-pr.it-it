---
title: Avviare SQL Server con la configurazione minima | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- minimal configuration [SQL Server]
- starting SQL Server, minimal configuration
ms.assetid: 4d733c99-28b3-42d8-b7f6-7b943b548173
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5c78fc10be584803b438b2cd125a77400ff369b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624338"
---
# <a name="start-sql-server-with-minimal-configuration"></a><span data-ttu-id="f2a5a-102">Avvio di SQL Server con la configurazione minima</span><span class="sxs-lookup"><span data-stu-id="f2a5a-102">Start SQL Server with Minimal Configuration</span></span>
  <span data-ttu-id="f2a5a-103">In caso di problemi di configurazione che impediscono l'avvio del server, è possibile avviare un'istanza di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando la configurazione minima.</span><span class="sxs-lookup"><span data-stu-id="f2a5a-103">If you have configuration problems that prevent the server from starting, you can start an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using the minimal configuration startup option.</span></span> <span data-ttu-id="f2a5a-104">Si tratta dell'opzione di avvio **-f**.</span><span class="sxs-lookup"><span data-stu-id="f2a5a-104">This is the startup option **-f**.</span></span> <span data-ttu-id="f2a5a-105">L'avvio di un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con la configurazione minima comporta l'attivazione automatica della modalità utente singolo per il server.</span><span class="sxs-lookup"><span data-stu-id="f2a5a-105">Starting an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with minimal configuration automatically puts the server in single-user mode.</span></span>  
  
 <span data-ttu-id="f2a5a-106">Quando si avvia un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con la configurazione minima, si noti quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f2a5a-106">When you start an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in minimal configuration mode, note the following:</span></span>  
  
-   <span data-ttu-id="f2a5a-107">La connessione è consentita a un solo utente e il processo CHECKPOINT non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="f2a5a-107">Only a single user can connect, and the CHECKPOINT process is not executed.</span></span>  
  
-   <span data-ttu-id="f2a5a-108">L'accesso remoto e il read-ahead sono disabilitati.</span><span class="sxs-lookup"><span data-stu-id="f2a5a-108">Remote access and read-ahead are disabled.</span></span>  
  
-   <span data-ttu-id="f2a5a-109">Le stored procedure di avvio non vengono eseguite.</span><span class="sxs-lookup"><span data-stu-id="f2a5a-109">Startup stored procedures do not run.</span></span>  
  
 <span data-ttu-id="f2a5a-110">Dopo aver avviato il server con la configurazione minima, è necessario modificare il valore o i valori delle opzioni del server appropriati e quindi arrestare e riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="f2a5a-110">After the server has been started with minimal configuration, you should change the appropriate server option value or values, stop, and then restart the server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f2a5a-111">Usare l'utilità **sqlcmd** e la connessione amministrativa dedicata (DAC) per eseguire la connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2a5a-111">Use the **sqlcmd** utility and the dedicated administrator connection (DAC) to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f2a5a-112">Se si utilizza una connessione normale, arrestare il servizio SQL Server Agent prima di connettersi a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in modalità configurazione minima.</span><span class="sxs-lookup"><span data-stu-id="f2a5a-112">If you use a typical connection, stop the SQL Server Agent service before connecting to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in minimal configuration mode.</span></span> <span data-ttu-id="f2a5a-113">In caso contrario, il servizio SQL Server Agent utilizzerà la connessione, bloccandola.</span><span class="sxs-lookup"><span data-stu-id="f2a5a-113">Otherwise, the SQL Server Agent service uses the connection, thereby blocking it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2a5a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2a5a-114">See Also</span></span>  
 <span data-ttu-id="f2a5a-115">[Avvio, arresto o sospensione del servizio SQL Server Agent](../../ssms/agent/start-stop-or-pause-the-sql-server-agent-service.md) </span><span class="sxs-lookup"><span data-stu-id="f2a5a-115">[Start, Stop, or Pause the SQL Server Agent Service](../../ssms/agent/start-stop-or-pause-the-sql-server-agent-service.md) </span></span>  
 <span data-ttu-id="f2a5a-116">[Connessione di diagnostica per gli amministratori di database](diagnostic-connection-for-database-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="f2a5a-116">[Diagnostic Connection for Database Administrators](diagnostic-connection-for-database-administrators.md) </span></span>  
 <span data-ttu-id="f2a5a-117">[Utilità sqlcmd](../../tools/sqlcmd-utility.md) </span><span class="sxs-lookup"><span data-stu-id="f2a5a-117">[sqlcmd Utility](../../tools/sqlcmd-utility.md) </span></span>  
 <span data-ttu-id="f2a5a-118">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f2a5a-118">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="f2a5a-119">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f2a5a-119">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="f2a5a-120">Opzioni di avvio del servizio del motore di database</span><span class="sxs-lookup"><span data-stu-id="f2a5a-120">Database Engine Service Startup Options</span></span>](database-engine-service-startup-options.md)  
  
  
