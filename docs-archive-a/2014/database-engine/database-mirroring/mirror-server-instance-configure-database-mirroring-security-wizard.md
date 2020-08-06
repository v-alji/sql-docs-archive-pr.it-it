---
title: Istanza server mirror (Configurazione guidata sicurezza mirroring del database) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.mirrorsrvr.f1
ms.assetid: 53223432-615e-440f-904d-925d33ec2144
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 889e62af592d8d23f2aca0d752f1c7f535df883a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726235"
---
# <a name="mirror-server-instance-configure-database-mirroring-security-wizard"></a><span data-ttu-id="1e993-102">Istanza server mirror (Configurazione guidata sicurezza mirroring del database)</span><span class="sxs-lookup"><span data-stu-id="1e993-102">Mirror Server Instance (Configure Database Mirroring Security Wizard)</span></span>
  <span data-ttu-id="1e993-103">Utilizzare questa pagina per specificare le informazioni relative all'istanza del server del database mirror.</span><span class="sxs-lookup"><span data-stu-id="1e993-103">Use this page to specify information about the server instance with the mirror database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1e993-104">L'istanza del server mirror deve essere in esecuzione nella stessa edizione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Standard o Enterprise, come l'istanza del server principale.</span><span class="sxs-lookup"><span data-stu-id="1e993-104">The mirror server instance must be running the same edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], either Standard or Enterprise, as the principal server instance.</span></span> <span data-ttu-id="1e993-105">È inoltre consigliabile che vengano eseguite in sistemi simili in grado di gestire carichi di lavoro identici.</span><span class="sxs-lookup"><span data-stu-id="1e993-105">Also, we strongly recommend that they run on comparable systems that can handle identical workloads.</span></span>  
  
 <span data-ttu-id="1e993-106">**Per configurare il mirroring del database tramite SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="1e993-106">**To configure database mirroring by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="1e993-107">Stabilire una sessione di mirroring del database tramite autenticazione di Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1e993-107">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="1e993-108">Avvio della Configurazione guidata sicurezza mirroring del database &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1e993-108">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="1e993-109">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1e993-109">Options</span></span>  
 <span data-ttu-id="1e993-110">**Istanza server mirror**</span><span class="sxs-lookup"><span data-stu-id="1e993-110">**Mirror server instance**</span></span>  
 <span data-ttu-id="1e993-111">Se nella pagina **Mirroring** della finestra di dialogo **Proprietà database** è già stata specificata un'istanza del server mirror, tale istanza viene visualizzata. Per altre informazioni, vedere [Proprietà del database &#40;Pagina Mirroring&#41;](../../relational-databases/databases/database-properties-mirroring-page.md).</span><span class="sxs-lookup"><span data-stu-id="1e993-111">If a mirror server instance is already specified (on the **Mirroring** page of the **Database Properties** dialog box), that instance is displayed; for more information, see [Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md).</span></span>  
  
 <span data-ttu-id="1e993-112">In caso contrario, immettere il nome dell'istanza del server mirror.</span><span class="sxs-lookup"><span data-stu-id="1e993-112">Otherwise, enter the name of the mirror server instance.</span></span> <span data-ttu-id="1e993-113">Si noti che l'istanza del server mirror non può essere la stessa istanza del server principale.</span><span class="sxs-lookup"><span data-stu-id="1e993-113">Note that the mirror server instance cannot be the same as the principal server instance.</span></span>  
  
 <span data-ttu-id="1e993-114">**Connettere**</span><span class="sxs-lookup"><span data-stu-id="1e993-114">**Connect**</span></span>  
 <span data-ttu-id="1e993-115">Se non è stata specificata un'istanza del server mirror, fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="1e993-115">If a mirror server instance has not been specified, click **Connect**.</span></span> <span data-ttu-id="1e993-116">Verrà visualizzata la finestra di dialogo **Connetti al server** tramite la quale è possibile specificare l'istanza del server e stabilire una connessione.</span><span class="sxs-lookup"><span data-stu-id="1e993-116">This displays the **Connect to Server** dialog box in which you can specify the server instance and establish a connection.</span></span>  
  
 <span data-ttu-id="1e993-117">Se è stata specificata l'istanza, ma non è disponibile una connessione con autorizzazioni sufficienti per il controllo dell'esistenza dell'endpoint, fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="1e993-117">If the instance has been specified, but the wizard lacks a connection with sufficient permission to check for the existence of the endpoint, click **Connect**.</span></span> <span data-ttu-id="1e993-118">Verrà visualizzata la finestra di dialogo **Connetti al server** in cui l'istanza del server risulterà selezionata automaticamente e non sarà possibile modificarla.</span><span class="sxs-lookup"><span data-stu-id="1e993-118">This displays the **Connect to Server** dialog box with the server instance pre-selected and unchangeable.</span></span> <span data-ttu-id="1e993-119">Specificare un account di dominio dotato di autorizzazioni sufficienti e connettersi all'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="1e993-119">Specify a domain account with sufficient permission, and connect to the server instance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1e993-120">Quando viene stabilita la connessione all'istanza del server, la Configurazione guidata sicurezza mirroring del database usa le credenziali della finestra di dialogo **Connetti al server** .</span><span class="sxs-lookup"><span data-stu-id="1e993-120">When connecting to the server instance, the Configure Database Mirroring Security Wizard uses the credentials provided in the **Connect to Server** dialog box.</span></span> <span data-ttu-id="1e993-121">Queste credenziali sono diverse da quelle di una sessione di mirroring, che utilizza le credenziali dell'account di avvio con il quale l'istanza del server è in esecuzione come servizio.</span><span class="sxs-lookup"><span data-stu-id="1e993-121">These are different from the credentials of a mirroring session, which uses the credentials of the startup account where the server instance is running as a service.</span></span>  
  
 <span data-ttu-id="1e993-122">**Listener Port** (Porta listener)</span><span class="sxs-lookup"><span data-stu-id="1e993-122">**Listener Port**</span></span>  
 <span data-ttu-id="1e993-123">Il funzionamento di questa opzione dipende dalla presenza dell'endpoint di mirroring per l'istanza del server corrente, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="1e993-123">The behavior of this option depends on whether the mirroring endpoint exists for this server instance, as follows:</span></span>  
  
-   <span data-ttu-id="1e993-124">Se non esiste una porta di attesa per l'istanza del server, nella casella di testo **Porta** verrà visualizzato il numero di porta 5022.</span><span class="sxs-lookup"><span data-stu-id="1e993-124">If a listener port does not exist for the server instance, port number 5022 is displayed in the **Port** text box.</span></span> <span data-ttu-id="1e993-125">È possibile utilizzare qualsiasi numero di porta disponibile, ad esempio 7022.</span><span class="sxs-lookup"><span data-stu-id="1e993-125">You can use any available port number, such as 7022.</span></span>  
  
-   <span data-ttu-id="1e993-126">Se esiste già l'endpoint del mirroring, verrà visualizzato il numero di porta dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1e993-126">When the mirroring endpoint already exists, the port number from that endpoint is displayed.</span></span> <span data-ttu-id="1e993-127">Se è necessario modificare la porta, utilizzare un comando ALTER ENDPOINT.</span><span class="sxs-lookup"><span data-stu-id="1e993-127">If you need to change the port, use an ALTER ENDPOINT command.</span></span> <span data-ttu-id="1e993-128">Per altre informazioni, vedere [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1e993-128">For more information, see [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1e993-129">È necessario un numero di porta.</span><span class="sxs-lookup"><span data-stu-id="1e993-129">A port number is required.</span></span>  
  
 <span data-ttu-id="1e993-130">**Nome endpoint**</span><span class="sxs-lookup"><span data-stu-id="1e993-130">**Endpoint name**</span></span>  
 <span data-ttu-id="1e993-131">Se l'endpoint di mirroring esiste per l'istanza del server, viene visualizzato il nome dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1e993-131">If the mirroring endpoint exists for this server instance, the endpoint name is displayed here.</span></span> <span data-ttu-id="1e993-132">Se l'endpoint non esiste, è possibile specificare il nome dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1e993-132">If the endpoint does not exist, you can specify the name of the endpoint.</span></span>  
  
 <span data-ttu-id="1e993-133">**Crittografa i dati inviati tramite questo endpoint**</span><span class="sxs-lookup"><span data-stu-id="1e993-133">**Encrypt data sent through this endpoint**</span></span>  
 <span data-ttu-id="1e993-134">La crittografia è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1e993-134">By default, encryption is enabled.</span></span> <span data-ttu-id="1e993-135">Quando è abilitata, la crittografia non solo è supportata, ma è anche necessaria e utilizza i valori predefiniti per tutte le opzioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="1e993-135">When enabled, encryption is required (not merely supported) and uses the default values for all of the encryption options.</span></span> <span data-ttu-id="1e993-136">Per altre informazioni, vedere [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1e993-136">For more information, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
 <span data-ttu-id="1e993-137">Per disabilitare la crittografia, deselezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="1e993-137">To disable encryption, clear the check box.</span></span> <span data-ttu-id="1e993-138">Per abilitare di nuovo la crittografia, selezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="1e993-138">To re-enable encryption, select the check box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e993-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e993-139">See Also</span></span>  
 <span data-ttu-id="1e993-140">[Endpoint del mirroring del database &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1e993-140">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="1e993-141">[Proprietà del database &#40;Pagina Mirroring&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="1e993-141">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="1e993-142">[Creare un endpoint del mirroring del database per l'autenticazione Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="1e993-142">[Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span></span>  
 <span data-ttu-id="1e993-143">[Avviare il monitoraggio mirroring del database &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="1e993-143">[Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="1e993-144">Mirroring del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1e993-144">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  
