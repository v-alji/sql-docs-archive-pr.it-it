---
title: Istanza server principale (Configurazione guidata sicurezza mirroring del database) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.principalsrvr.f1
ms.assetid: 58af27d7-c5dd-4669-be6b-b472bc2c8ef4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2632b5ffd5355065b4b5c1f905b3b6e5c5b6204d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716780"
---
# <a name="principal-server-instance-configure-database-mirroring-security-wizard"></a><span data-ttu-id="2706a-102">Istanza server principale (Configurazione guidata sicurezza mirroring del database)</span><span class="sxs-lookup"><span data-stu-id="2706a-102">Principal Server Instance (Configure Database Mirroring Security Wizard)</span></span>
  <span data-ttu-id="2706a-103">Utilizzare questa pagina per specificare le informazioni relative all'istanza del server del database principale.</span><span class="sxs-lookup"><span data-stu-id="2706a-103">Use this page to specify information about the server instance of the principal database.</span></span> <span data-ttu-id="2706a-104">Il database principale è la copia del database che avvia la sessione di mirroring.</span><span class="sxs-lookup"><span data-stu-id="2706a-104">The principal database is the copy of the database that begins the mirroring session.</span></span> <span data-ttu-id="2706a-105">Dopo l'avvio della sessione il database principale è la copia del database che accetta le modifiche dell'utente.</span><span class="sxs-lookup"><span data-stu-id="2706a-105">After the session has begun, the principal database is the copy of the database that accepts user changes.</span></span> <span data-ttu-id="2706a-106">Quando si verifica un failover, i ruoli principale e mirror vengono invertiti, quindi il database principale iniziale potrebbe non rimanere tale.</span><span class="sxs-lookup"><span data-stu-id="2706a-106">(When a failover occurs, the principal and mirroring roles are swapped; therefore, the initial principal database might not remain the principal database.)</span></span>  
  
 <span data-ttu-id="2706a-107">**Per configurare il mirroring del database tramite SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="2706a-107">**To configure database mirroring by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="2706a-108">Stabilire una sessione di mirroring del database tramite autenticazione di Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2706a-108">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="2706a-109">Avvio della Configurazione guidata sicurezza mirroring del database &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2706a-109">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="2706a-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="2706a-110">Options</span></span>  
 <span data-ttu-id="2706a-111">**Istanza server principale**</span><span class="sxs-lookup"><span data-stu-id="2706a-111">**Principal server instance**</span></span>  
 <span data-ttu-id="2706a-112">Poiché il mirroring del database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] viene sempre configurato dal server principale, l'istanza corrente del server è sempre l'istanza del server principale.</span><span class="sxs-lookup"><span data-stu-id="2706a-112">Because database mirroring in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is always configured from the principal server, the current server instance is always the principal server instance.</span></span>  
  
 <span data-ttu-id="2706a-113">**Listener Port** (Porta listener)</span><span class="sxs-lookup"><span data-stu-id="2706a-113">**Listener Port**</span></span>  
 <span data-ttu-id="2706a-114">Il funzionamento di questa opzione dipende dalla presenza dell'endpoint di mirroring per l'istanza del server corrente, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="2706a-114">The behavior of this option depends on whether the mirroring endpoint exists for this server instance, as follows:</span></span>  
  
-   <span data-ttu-id="2706a-115">Se non esiste una porta di attesa per l'istanza del server, nella casella di testo **Porta** verrà visualizzato il numero di porta 5022.</span><span class="sxs-lookup"><span data-stu-id="2706a-115">If the listener port does not exist for this server instance, port number 5022 is displayed in the **Port** text box.</span></span> <span data-ttu-id="2706a-116">È possibile utilizzare qualsiasi numero di porta disponibile, ad esempio 7022.</span><span class="sxs-lookup"><span data-stu-id="2706a-116">You can use any available port number, such as, 7022.</span></span>  
  
-   <span data-ttu-id="2706a-117">Se l'endpoint di mirroring esiste già, viene visualizzato il numero di porta ricevuto dall'endpoint.</span><span class="sxs-lookup"><span data-stu-id="2706a-117">When the mirroring endpoint already exists, the port number from the endpoint is displayed.</span></span> <span data-ttu-id="2706a-118">Se è necessario modificare la porta, utilizzare un comando ALTER ENDPOINT.</span><span class="sxs-lookup"><span data-stu-id="2706a-118">If you need to change the port, use an ALTER ENDPOINT command.</span></span> <span data-ttu-id="2706a-119">Per altre informazioni, vedere [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2706a-119">For more information, see [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2706a-120">È necessario un numero di porta.</span><span class="sxs-lookup"><span data-stu-id="2706a-120">A port number is required.</span></span>  
  
 <span data-ttu-id="2706a-121">**Nome endpoint**</span><span class="sxs-lookup"><span data-stu-id="2706a-121">**Endpoint name**</span></span>  
 <span data-ttu-id="2706a-122">Se l'endpoint di mirroring esiste per l'istanza del server, viene visualizzato il nome dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="2706a-122">If the mirroring endpoint exists for this server instance, the endpoint name is displayed here.</span></span> <span data-ttu-id="2706a-123">Se l'endpoint non esiste, è possibile specificare il nome dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="2706a-123">If the endpoint does not exist, you can specify the name of the endpoint.</span></span>  
  
 <span data-ttu-id="2706a-124">**Crittografa i dati inviati tramite questo endpoint**</span><span class="sxs-lookup"><span data-stu-id="2706a-124">**Encrypt data sent through this endpoint**</span></span>  
 <span data-ttu-id="2706a-125">La crittografia è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2706a-125">By default, encryption is enabled.</span></span> <span data-ttu-id="2706a-126">Quando è abilitata, la crittografia non solo è supportata, ma è anche necessaria e utilizza i valori predefiniti per tutte le opzioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="2706a-126">When enabled, encryption is required (not merely supported) and uses the default values for all of the encryption options.</span></span> <span data-ttu-id="2706a-127">Per altre informazioni, vedere [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2706a-127">For more information, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
 <span data-ttu-id="2706a-128">Per disabilitare la crittografia, deselezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="2706a-128">To disable encryption, clear the check box.</span></span> <span data-ttu-id="2706a-129">Per abilitare di nuovo la crittografia, selezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="2706a-129">To re-enable encryption, select the check box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2706a-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2706a-130">See Also</span></span>  
 <span data-ttu-id="2706a-131">[Endpoint del mirroring del database &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2706a-131">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="2706a-132">[Proprietà del database &#40;Pagina Mirroring&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="2706a-132">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="2706a-133">[Creare un endpoint del mirroring del database per l'autenticazione Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="2706a-133">[Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span></span>  
 <span data-ttu-id="2706a-134">[Avviare il monitoraggio mirroring del database &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="2706a-134">[Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="2706a-135">Mirroring del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2706a-135">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  
