---
title: Registrazione di server
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqlserverregisteredserver.dhelp
helpviewer_keywords:
- connections [SQL Server], registered servers
- registering servers
- servers [SQL Server], registering
- server management [SQL Server], registering servers
- server registration [SQL Server]
ms.assetid: c2a2513e-fa09-419c-99e7-a12d57c5a0db
author: markingmyname
ms.author: maghan
ms.openlocfilehash: f4b23ba127c6b000b0abbe832c4c072ada78c5e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627018"
---
# <a name="register-servers"></a><span data-ttu-id="48076-102">Registrazione di server</span><span class="sxs-lookup"><span data-stu-id="48076-102">Register Servers</span></span>
  <span data-ttu-id="48076-103">La registrazione di un server in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] consente di archiviare le informazioni sulla connessione al server per uso futuro. È possibile registrare un server in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]in tre modi.</span><span class="sxs-lookup"><span data-stu-id="48076-103">Registering a server in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] allows you to store the server connection information for future connections.There are three ways to register a server in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
1.  <span data-ttu-id="48076-104">Le istanze locali di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengono registrate automaticamente durante il primo avvio di [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] dopo l'installazione.</span><span class="sxs-lookup"><span data-stu-id="48076-104">Local instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are automatically registered during the first launch of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] after its installation.</span></span>  
  
2.  <span data-ttu-id="48076-105">È inoltre possibile iniziare la procedura di registrazione automatica in qualsiasi momento, per ripristinare la registrazione delle istanze locali del server.</span><span class="sxs-lookup"><span data-stu-id="48076-105">You can also initiate the automatic registration process at any time, to restore the registration of local server instances.</span></span>  
  
3.  <span data-ttu-id="48076-106">Infine, è possibile registrare un server utilizzando lo strumento Server registrati di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48076-106">Lastly, you can register a server using the Registered Servers tool in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="benefits-of-registered-servers"></a><span data-ttu-id="48076-107">Vantaggi di Server registrati</span><span class="sxs-lookup"><span data-stu-id="48076-107">Benefits of Registered Servers</span></span>  
 <span data-ttu-id="48076-108">Server registrati consente di:</span><span class="sxs-lookup"><span data-stu-id="48076-108">With Registered Servers you can:</span></span>  
  
-   <span data-ttu-id="48076-109">Registrare i server per mantenere le informazioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="48076-109">Register servers to preserve the connection information.</span></span>  
  
-   <span data-ttu-id="48076-110">Stabilire se un server registrato è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="48076-110">Determine if a registered server is running.</span></span>  
  
-   <span data-ttu-id="48076-111">Collegare facilmente Esplora oggetti e l'editor di query a un server registrato.</span><span class="sxs-lookup"><span data-stu-id="48076-111">Easily connect Object Explorer and Query Editor to a registered server.</span></span>  
  
-   <span data-ttu-id="48076-112">Modificare o eliminare le informazioni di registrazione per un server registrato.</span><span class="sxs-lookup"><span data-stu-id="48076-112">Edit or delete the registration information for a registered server.</span></span>  
  
-   <span data-ttu-id="48076-113">Creare gruppi di server.</span><span class="sxs-lookup"><span data-stu-id="48076-113">Create groups of servers.</span></span>  
  
-   <span data-ttu-id="48076-114">Specificare nomi semplici da usare per i server registrati immettendo nella casella **Nome server registrato** un valore diverso da quello presente nell'elenco **Nome server** .</span><span class="sxs-lookup"><span data-stu-id="48076-114">Provide user-friendly names for registered servers by providing a value in the **Registered server name** box that is different from the **Server name** list.</span></span>  
  
-   <span data-ttu-id="48076-115">Specificare descrizioni dettagliate per i server registrati.</span><span class="sxs-lookup"><span data-stu-id="48076-115">Provide detailed descriptions for registered servers.</span></span>  
  
-   <span data-ttu-id="48076-116">Specificare descrizioni dettagliate dei gruppi di server registrati.</span><span class="sxs-lookup"><span data-stu-id="48076-116">Provide detailed descriptions of registered server groups.</span></span>  
  
-   <span data-ttu-id="48076-117">Esportare gruppi di server registrati.</span><span class="sxs-lookup"><span data-stu-id="48076-117">Export registered server groups.</span></span>  
  
-   <span data-ttu-id="48076-118">Importare gruppi di server registrati.</span><span class="sxs-lookup"><span data-stu-id="48076-118">Import registered server groups.</span></span>  
  
-   <span data-ttu-id="48076-119">Visualizzare i file di log di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per le istanze online o offline di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48076-119">View the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files for online or offline instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="48076-120">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="48076-120">Related Tasks</span></span>  
 <span data-ttu-id="48076-121">Utilizzare gli argomenti seguenti per iniziare a utilizzare i server registrati:</span><span class="sxs-lookup"><span data-stu-id="48076-121">Use the following topics to get started with registered servers:</span></span>  
  
|<span data-ttu-id="48076-122">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="48076-122">**Description**</span></span>|<span data-ttu-id="48076-123">**Argomento**</span><span class="sxs-lookup"><span data-stu-id="48076-123">**Topic**</span></span>|  
|---------------------|---------------|  
|<span data-ttu-id="48076-124">Registrare istanze locali del server</span><span class="sxs-lookup"><span data-stu-id="48076-124">Register local server instances</span></span>|[<span data-ttu-id="48076-125">Registrare un server connesso &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="48076-125">Register a Connected Server &#40;SQL Server Management Studio&#41;</span></span>](register-a-connected-server-sql-server-management-studio.md)|  
|<span data-ttu-id="48076-126">Registrare un server</span><span class="sxs-lookup"><span data-stu-id="48076-126">Register a server</span></span>|[<span data-ttu-id="48076-127">Creare un nuovo server registrato &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="48076-127">Create a New Registered Server &#40;SQL Server Management Studio&#41;</span></span>](create-a-new-registered-server-sql-server-management-studio.md)|  
|<span data-ttu-id="48076-128">Visualizzare i server registrati</span><span class="sxs-lookup"><span data-stu-id="48076-128">View registered servers</span></span>|[<span data-ttu-id="48076-129">Visualizzazione della finestra Server registrati in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="48076-129">View Registered Servers in SQL Server Management Studio</span></span>](view-registered-servers-in-sql-server-management-studio.md)|  
|<span data-ttu-id="48076-130">Rimuovere un server registrato</span><span class="sxs-lookup"><span data-stu-id="48076-130">Remove a registered server</span></span>|[<span data-ttu-id="48076-131">Rimuovere un server registrato &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="48076-131">Remove a Registered Server &#40;SQL Server Management Studio&#41;</span></span>](remove-a-registered-server-sql-server-management-studio.md)|  
|<span data-ttu-id="48076-132">Modificare la registrazione di un server</span><span class="sxs-lookup"><span data-stu-id="48076-132">Change a server's registration</span></span>|[<span data-ttu-id="48076-133">Modificare la registrazione di un server &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="48076-133">Change a Server's Registration &#40;SQL Server Management Studio&#41;</span></span>](change-a-server-s-registration-sql-server-management-studio.md)|  
|<span data-ttu-id="48076-134">Connettersi a un server registrato</span><span class="sxs-lookup"><span data-stu-id="48076-134">Connect to a registered server</span></span>|[<span data-ttu-id="48076-135">Connessione a un server registrato &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="48076-135">Connect to a Registered Server &#40;SQL Server Management Studio&#41;</span></span>](connect-to-a-registered-server-sql-server-management-studio.md)|  
|<span data-ttu-id="48076-136">Disconnettersi da un server registrato</span><span class="sxs-lookup"><span data-stu-id="48076-136">Disconnect from a registered server</span></span>|[<span data-ttu-id="48076-137">Disconnettersi da un server registrato &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="48076-137">Disconnect from a Registered Server &#40;SQL Server Management Studio&#41;</span></span>](disconnect-from-a-registered-server-sql-server-management-studio.md)|  
|<span data-ttu-id="48076-138">Spostare un server registrato o un gruppo di server</span><span class="sxs-lookup"><span data-stu-id="48076-138">Move a registered server or server group</span></span>|[<span data-ttu-id="48076-139">Spostare un server registrato o un gruppo di server registrati &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="48076-139">Move a Registered Server or Registered Server Group &#40;SQL Server Management Studio&#41;</span></span>](move-a-registered-server-or-registered-server-group.md)|  
|<span data-ttu-id="48076-140">Modificare il nome di un server registrato o di un gruppo di server</span><span class="sxs-lookup"><span data-stu-id="48076-140">Change the name of a registered server or server group</span></span>|[<span data-ttu-id="48076-141">Modificare il nome di un server registrato o di un gruppo di server registrati &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="48076-141">Change the Name of a Registered Server or Registered Server Group &#40;SQL Server Management Studio&#41;</span></span>](change-the-name-of-registered-server-or-registered-server-group.md)|  
|<span data-ttu-id="48076-142">Creare o modificare un gruppo di server</span><span class="sxs-lookup"><span data-stu-id="48076-142">Create or edit a server group</span></span>|[<span data-ttu-id="48076-143">Creare o modificare un gruppo di server &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="48076-143">Create or Edit a Server Group &#40;SQL Server Management Studio&#41;</span></span>](create-or-edit-a-server-group-sql-server-management-studio.md)|  
|<span data-ttu-id="48076-144">Rimuovere un gruppo di server</span><span class="sxs-lookup"><span data-stu-id="48076-144">Remove a server group</span></span>|[<span data-ttu-id="48076-145">Rimuovere un gruppo di server &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="48076-145">Remove a Server Group &#40;SQL Server Management Studio&#41;</span></span>](remove-a-server-group-sql-server-management-studio.md)|  
|<span data-ttu-id="48076-146">Esportare informazioni relative a server registrati</span><span class="sxs-lookup"><span data-stu-id="48076-146">Export registered server information</span></span>|[<span data-ttu-id="48076-147">Esportare informazioni relative a server registrati &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="48076-147">Export Registered Server Information &#40;SQL Server Management Studio&#41;</span></span>](export-registered-server-information-sql-server-management-studio.md)|  
|<span data-ttu-id="48076-148">Importare informazioni relative ai server registrati</span><span class="sxs-lookup"><span data-stu-id="48076-148">Import registered server information</span></span>|[<span data-ttu-id="48076-149">Importare informazioni relative a server registrati &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="48076-149">Import Registered Server Information &#40;SQL Server Management Studio&#41;</span></span>](import-registered-server-information-sql-server-management-studio.md)|  
|<span data-ttu-id="48076-150">Creare un server di gestione centrale e un gruppo di server</span><span class="sxs-lookup"><span data-stu-id="48076-150">Create a Central Management Server and Server Group</span></span>|[<span data-ttu-id="48076-151">Creare un server di gestione centrale e un gruppo di server &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="48076-151">Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;</span></span>](create-a-central-management-server-and-server-group.md)|  
|<span data-ttu-id="48076-152">Eseguire istruzioni su più server contemporaneamente</span><span class="sxs-lookup"><span data-stu-id="48076-152">Execute statements against multiple servers simultaneously</span></span>|[<span data-ttu-id="48076-153">Eseguire istruzioni su più server contemporaneamente &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="48076-153">Execute Statements Against Multiple Servers Simultaneously &#40;SQL Server Management Studio&#41;</span></span>](execute-statements-against-multiple-servers-simultaneously.md)|  
  
## <a name="see-also"></a><span data-ttu-id="48076-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48076-154">See Also</span></span>  
 [<span data-ttu-id="48076-155">Server remoti</span><span class="sxs-lookup"><span data-stu-id="48076-155">Remote Servers</span></span>](../../database-engine/configure-windows/remote-servers.md)  
  
  
