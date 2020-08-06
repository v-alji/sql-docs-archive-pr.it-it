---
title: Creazione di un server e di un gruppo di gestione centrale
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- configuration server
ms.assetid: da265482-3953-440a-ac23-0ab7e42a55eb
author: markingmyname
ms.author: maghan
ms.openlocfilehash: f53b75966a14dbc6fd6cdc9bea0929ccac7780c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711528"
---
# <a name="create-a-central-management-server-and-server-group-sql-server-management-studio"></a><span data-ttu-id="66fdd-102">Creazione di un server di gestione centrale e di un gruppo di server (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="66fdd-102">Create a Central Management Server and Server Group (SQL Server Management Studio)</span></span>
  <span data-ttu-id="66fdd-103">In questo argomento viene illustrato come designare un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] come server di gestione centrale in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66fdd-103">This topic describes how to designate an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as a central management server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="66fdd-104">Nei server di gestione centrale è archiviato un elenco di istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] organizzato in uno o più gruppi di server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="66fdd-104">Central management servers store a list of instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is organized into one or more central management server groups.</span></span> <span data-ttu-id="66fdd-105">Le azioni effettuate utilizzando un gruppo di server di gestione centrale hanno effetto su tutti i server inclusi nel gruppo.</span><span class="sxs-lookup"><span data-stu-id="66fdd-105">Actions that are taken by using a central management server group act on all servers in the server group.</span></span> <span data-ttu-id="66fdd-106">Tali azioni includono la connessione ai server tramite Esplora oggetti e l'esecuzione di istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] e criteri della gestione basata su criteri in più server contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="66fdd-106">This includes connecting to servers by using Object Explorer and executing [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and Policy-Based Management policies on multiple servers at the same time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="66fdd-107">Le versioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] precedenti a [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] non possono essere definite come server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="66fdd-107">Versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are earlier than [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] cannot be designated as a central management server.</span></span>  
  
 <span data-ttu-id="66fdd-108">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="66fdd-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="66fdd-109">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="66fdd-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="66fdd-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="66fdd-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="66fdd-111">**Per creare un server di gestione centrale e un gruppo di server utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="66fdd-111">**To create a Central Management Server and Server Group, using:**</span></span>  
  
     [<span data-ttu-id="66fdd-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="66fdd-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="66fdd-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="66fdd-113">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="66fdd-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="66fdd-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="66fdd-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="66fdd-115">Permissions</span></span>  
 <span data-ttu-id="66fdd-116">Due ruoli del database nel database msdb concedono l'accesso ai server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="66fdd-116">Two database roles in the msdb database grant access to central management servers.</span></span> <span data-ttu-id="66fdd-117">Solo i membri del ruolo ServerGroupAdministratorRole possono gestire il server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="66fdd-117">Only members of the ServerGroupAdministratorRole role can manage the central management server.</span></span> <span data-ttu-id="66fdd-118">Per connettersi a un server di gestione centrale, è necessario appartenere a un ruolo ServerGroupReaderRole.</span><span class="sxs-lookup"><span data-stu-id="66fdd-118">Membership in the ServerGroupReaderRole role is required to connect to a central management server.</span></span>  
  
 <span data-ttu-id="66fdd-119">Poiché le connessioni gestite da un server di gestione centrale vengono eseguite nel contesto dell'utente, l'utilizzo dell'autenticazione di Windows comporta la possibile variazione delle autorizzazioni effettive per i server registrati.</span><span class="sxs-lookup"><span data-stu-id="66fdd-119">Because the connections that are maintained by a central management server execute in the context of the user, by using Windows Authentication, the effective permissions on the registered servers might vary.</span></span> <span data-ttu-id="66fdd-120">L'utente, ad esempio, potrebbe essere un membro del ruolo predefinito del server sysadmin nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] A, ma disporre di autorizzazioni limitate per l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] B.</span><span class="sxs-lookup"><span data-stu-id="66fdd-120">For example, the user might be a member of the sysadmin fixed server role on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] A, but have limited permissions on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] B.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="66fdd-121">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="66fdd-121">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="66fdd-122">Nelle procedure indicate di seguito viene descritto come eseguire i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="66fdd-122">The following procedures describe how to perform the following steps.</span></span>  
  
1.  <span data-ttu-id="66fdd-123">Creare un server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="66fdd-123">Create a central management server.</span></span>  
  
2.  <span data-ttu-id="66fdd-124">Aggiungere uno o più gruppi di server al server di gestione centrale e aggiungere uno o più server registrati ai gruppi di server.</span><span class="sxs-lookup"><span data-stu-id="66fdd-124">Add one or more server groups to the central management server and add one or more registered servers to the server groups.</span></span>  
  
#### <a name="create-a-central-management-server"></a><span data-ttu-id="66fdd-125">Creare un server di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="66fdd-125">Create a central management server</span></span>  
  
1.  <span data-ttu-id="66fdd-126">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]scegliere **Server registrati** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="66fdd-126">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Registered Servers**.</span></span>  
  
2.  <span data-ttu-id="66fdd-127">In Server registrati espandere **Motore di database**, fare clic con il pulsante destro del mouse su **Server di gestione centrale**e quindi scegliere **Registra server di gestione centrale**.</span><span class="sxs-lookup"><span data-stu-id="66fdd-127">In Registered Servers, expand **Database Engine**, right-click **Central Management Servers**, and then  click **Register Central Management Server**.</span></span>  
  
3.  <span data-ttu-id="66fdd-128">Nella finestra di dialogo **Nuova registrazione server** selezionare dall'elenco a discesa di server l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che si desidera impostare come server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="66fdd-128">In the **New Server Registration** dialog box, select the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to become the central management server from the drop-down list of servers.</span></span> <span data-ttu-id="66fdd-129">È necessario utilizzare l'autenticazione di Windows per il server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="66fdd-129">You must use Windows Authentication for the central management server.</span></span>  
  
4.  <span data-ttu-id="66fdd-130">In **Server registrato**immettere un nome del server e una descrizione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="66fdd-130">In **Registered Server**, enter a server name and optional description.</span></span>  
  
5.  <span data-ttu-id="66fdd-131">Nella scheda **Proprietà connessione** rivedere o modificare le proprietà di connessione e della rete.</span><span class="sxs-lookup"><span data-stu-id="66fdd-131">From the **Connection Properties** tab, review or modifiy the network  and connection properties.</span></span> <span data-ttu-id="66fdd-132">Per altre informazioni, vedere [Connettersi al server &#40;pagina Proprietà connessione&#41; Motore di database](../f1-help/connect-to-server-connection-properties-page-database-engine.md)</span><span class="sxs-lookup"><span data-stu-id="66fdd-132">For more information, see [Connect to Server &#40;Connection Properties Page&#41; Database Engine](../f1-help/connect-to-server-connection-properties-page-database-engine.md)</span></span>  
  
6.  <span data-ttu-id="66fdd-133">Fare clic su **Test**per verificare la connessione.</span><span class="sxs-lookup"><span data-stu-id="66fdd-133">Click **Test**, to test the connection.</span></span>  
  
7.  <span data-ttu-id="66fdd-134">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="66fdd-134">Click **Save**.</span></span> <span data-ttu-id="66fdd-135">L'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verrà visualizzata nella cartella **Server di gestione centrale** .</span><span class="sxs-lookup"><span data-stu-id="66fdd-135">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will appear under the **Central Management Servers** folder.</span></span>  
  
#### <a name="create-a-new-server-group-and-add-servers-to-the-group"></a><span data-ttu-id="66fdd-136">Creare un gruppo di server e aggiungere server al gruppo</span><span class="sxs-lookup"><span data-stu-id="66fdd-136">Create a new server group and add servers to the group</span></span>  
  
1.  <span data-ttu-id="66fdd-137">Da **Server registrati**espandere **Server di gestione centrale**.</span><span class="sxs-lookup"><span data-stu-id="66fdd-137">From **Registered Servers**, expand **Central Management Servers**.</span></span> <span data-ttu-id="66fdd-138">Fare clic con il pulsante destro del mouse sull'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aggiunta nella procedura precedente e scegliere **Nuovo gruppo di server**.</span><span class="sxs-lookup"><span data-stu-id="66fdd-138">Right-click the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] added in the procedure above and select **New Server Group**.</span></span>  
  
2.  <span data-ttu-id="66fdd-139">In **Proprietà nuovo gruppo di server**immettere un nome di gruppo e una descrizione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="66fdd-139">In **New Server Group Properties**, enter a group name and optional description.</span></span>  
  
3.  <span data-ttu-id="66fdd-140">In **Server registrati**fare clic con il pulsante destro del mouse sul gruppo di server di gestione centrale, quindi scegliere **Nuova registrazione server**.</span><span class="sxs-lookup"><span data-stu-id="66fdd-140">From **Registered Servers**, right-click the server group and click **New Server Registration**.</span></span>  
  
4.  <span data-ttu-id="66fdd-141">In Nuova registrazione server selezionare un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66fdd-141">From New Server Registration, select an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="66fdd-142">Per altre informazioni, vedere [Creare un nuovo server registrato &#40;SQL Server Management Studio&#41;](create-a-new-registered-server-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="66fdd-142">For more information, see [Create a New Registered Server &#40;SQL Server Management Studio&#41;](create-a-new-registered-server-sql-server-management-studio.md).</span></span> <span data-ttu-id="66fdd-143">Aggiungere più server in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="66fdd-143">Add more servers as appropriate.</span></span>  
  
#### <a name="to-execute-queries-against-several-configuration-targets-at-the-same-time"></a><span data-ttu-id="66fdd-144">Per eseguire query su più destinazioni di configurazione contemporaneamente</span><span class="sxs-lookup"><span data-stu-id="66fdd-144">To execute queries against several configuration targets at the same time</span></span>  
  
-   <span data-ttu-id="66fdd-145">Dopo avere creato un server di gestione centrale, uno o più gruppi di server e uno o più server registrati, è possibile eseguire query su un intero gruppo simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="66fdd-145">After you create a central management server, one or more server groups, and one or more registered servers, you can execute queries against a whole group at the same time.</span></span> <span data-ttu-id="66fdd-146">Per altre informazioni su come eseguire istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] sui server di un gruppo di server contemporaneamente, vedere [Eseguire istruzioni su più server contemporaneamente &#40;SQL Server Management Studio&#41;](execute-statements-against-multiple-servers-simultaneously.md).</span><span class="sxs-lookup"><span data-stu-id="66fdd-146">For more information about how to execute [!INCLUDE[tsql](../../includes/tsql-md.md)] statements on the servers in a server group at the same time, see [Execute Statements Against Multiple Servers Simultaneously &#40;SQL Server Management Studio&#41;](execute-statements-against-multiple-servers-simultaneously.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66fdd-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66fdd-147">See Also</span></span>  
 [<span data-ttu-id="66fdd-148">Amministrare più server tramite server di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="66fdd-148">Administer Multiple Servers Using Central Management Servers</span></span>](../../relational-databases/administer-multiple-servers-using-central-management-servers.md)  
  
  
