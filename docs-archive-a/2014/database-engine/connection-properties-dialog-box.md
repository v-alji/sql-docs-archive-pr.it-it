---
title: Finestra di dialogo Proprietà connessione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connectionproperties.f1
helpviewer_keywords:
- Connection Properties dialog box
ms.assetid: 6df812ad-4d80-4503-8a23-47719ce85624
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: db2817ebaf3f1655f146c060fcb79d550ad0cc8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724127"
---
# <a name="connection-properties-dialog-box"></a><span data-ttu-id="5888b-102">Proprietà connessione - finestra di dialogo</span><span class="sxs-lookup"><span data-stu-id="5888b-102">Connection Properties Dialog Box</span></span>
  <span data-ttu-id="5888b-103">Utilizzare questa finestra di dialogo per visualizzare le proprietà della connessione corrente.</span><span class="sxs-lookup"><span data-stu-id="5888b-103">Use this dialog box to view the current connection properties.</span></span> <span data-ttu-id="5888b-104">Questa finestra di dialogo è disponibile se si fa clic su **Visualizza proprietà connessione** in varie finestre di dialogo di Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="5888b-104">This dialog box is available when you click **View connection properties** in various Object Explorer dialog boxes.</span></span> <span data-ttu-id="5888b-105">Le proprietà visualizzate in questa pagina sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="5888b-105">The properties displayed on this page are read-only.</span></span>  
  
 <span data-ttu-id="5888b-106">Per modificare proprietà quale **Database**, connettersi al database con Esplora oggetti prima di aprire la finestra di dialogo **Proprietà connessione** .</span><span class="sxs-lookup"><span data-stu-id="5888b-106">To change properties such as **Database**, connect to the desired database with Object Explorer before opening the **Connection Properties** dialog box.</span></span>  
  
 <span data-ttu-id="5888b-107">Il periodo di timeout della query per SQL Azure è di 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="5888b-107">Note that the query time-out period for SQL Azure is 30 minutes.</span></span>  
  
## <a name="authentication"></a><span data-ttu-id="5888b-108">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="5888b-108">Authentication</span></span>  
 <span data-ttu-id="5888b-109">Consente di visualizzare le proprietà di autenticazione per la connessione corrente.</span><span class="sxs-lookup"><span data-stu-id="5888b-109">View authentication properties for the current connection.</span></span> <span data-ttu-id="5888b-110">Le proprietà di autenticazione sono costituite dall'account di accesso e dal metodo di autenticazione utilizzati al momento della connessione.</span><span class="sxs-lookup"><span data-stu-id="5888b-110">Authentication properties are the login and authentication method when the connection was established.</span></span> <span data-ttu-id="5888b-111">Per modificare le proprietà di autenticazione, disconnettersi da [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e quindi riconnettersi Esplora oggetti al server utilizzando le opzioni di connessione desiderate.</span><span class="sxs-lookup"><span data-stu-id="5888b-111">To change the authentication properties, disconnect from [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], and then connect Object Explorer to the server again, using the desired connection options.</span></span>  
  
 <span data-ttu-id="5888b-112">**Metodo di autenticazione**</span><span class="sxs-lookup"><span data-stu-id="5888b-112">**Authentication Method**</span></span>  
 <span data-ttu-id="5888b-113">Metodo di autenticazione utilizzato per la connessione corrente.</span><span class="sxs-lookup"><span data-stu-id="5888b-113">The authentication method used for the current connection.</span></span>  
  
 <span data-ttu-id="5888b-114">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="5888b-114">**User Name**</span></span>  
 <span data-ttu-id="5888b-115">Nome dell'utente dell'account di accesso utilizzato per l'autenticazione della connessione.</span><span class="sxs-lookup"><span data-stu-id="5888b-115">The name of the user of login used for the connection authentication.</span></span>  
  
## <a name="connection-category"></a><span data-ttu-id="5888b-116">Connessione</span><span class="sxs-lookup"><span data-stu-id="5888b-116">Connection Category</span></span>  
 <span data-ttu-id="5888b-117">Consente di visualizzare le proprietà di connessione della connessione corrente.</span><span class="sxs-lookup"><span data-stu-id="5888b-117">View connection properties for the current connection.</span></span> <span data-ttu-id="5888b-118">La maggior parte delle proprietà di connessione viene selezionata nella scheda **Proprietà connessione** della finestra di dialogo **Connetti al server** durante il processo di connessione.</span><span class="sxs-lookup"><span data-stu-id="5888b-118">Most connection properties were selected on the **Connection Properties** tab of the **Connect to server** dialog box during the connection process.</span></span>  
  
 <span data-ttu-id="5888b-119">**Database**</span><span class="sxs-lookup"><span data-stu-id="5888b-119">**Database**</span></span>  
 <span data-ttu-id="5888b-120">Nome del database al quale si è attualmente connessi.</span><span class="sxs-lookup"><span data-stu-id="5888b-120">The name of the database currently connected to.</span></span> <span data-ttu-id="5888b-121">Per modificare questa impostazione, utilizzare la barra degli strumenti Editor SQL.</span><span class="sxs-lookup"><span data-stu-id="5888b-121">To change this use, the SQL Editor toolbar.</span></span>  
  
 <span data-ttu-id="5888b-122">**SPID**</span><span class="sxs-lookup"><span data-stu-id="5888b-122">**SPID**</span></span>  
 <span data-ttu-id="5888b-123">ID di processo di sistema assegnato dal server alla connessione.</span><span class="sxs-lookup"><span data-stu-id="5888b-123">The system process ID assigned by the server to the connection.</span></span> <span data-ttu-id="5888b-124">Non è possibile modificare questa impostazione per la connessione corrente.</span><span class="sxs-lookup"><span data-stu-id="5888b-124">This cannot be changed for this connection.</span></span>  
  
 <span data-ttu-id="5888b-125">**Protocollo di rete**</span><span class="sxs-lookup"><span data-stu-id="5888b-125">**Network Protocol**</span></span>  
 <span data-ttu-id="5888b-126">Protocollo di rete della connessione [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5888b-126">The network protocol of the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] connection.</span></span> <span data-ttu-id="5888b-127">Per modificare questa impostazione, riconnettersi con le proprietà di connessione desiderate.</span><span class="sxs-lookup"><span data-stu-id="5888b-127">To change this, connect again with the desired connection properties.</span></span>  
  
 <span data-ttu-id="5888b-128">**Dimensioni pacchetto di rete**</span><span class="sxs-lookup"><span data-stu-id="5888b-128">**Network Packet Size**</span></span>  
 <span data-ttu-id="5888b-129">Dimensioni di pacchetto utilizzate per la comunicazione con il server.</span><span class="sxs-lookup"><span data-stu-id="5888b-129">The packet size used when communicating with the server.</span></span> <span data-ttu-id="5888b-130">Per modificare questa impostazione, riconnettersi con le proprietà di connessione desiderate.</span><span class="sxs-lookup"><span data-stu-id="5888b-130">To change this, connect again with the desired connection properties.</span></span>  
  
 <span data-ttu-id="5888b-131">**Timeout connessione**</span><span class="sxs-lookup"><span data-stu-id="5888b-131">**Connection Timeout**</span></span>  
 <span data-ttu-id="5888b-132">Tempo di attesa in secondi per la connessione a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] prima che si verifichi il timeout o venga restituito un errore di connessione all'utente.</span><span class="sxs-lookup"><span data-stu-id="5888b-132">The amount of time is seconds to wait when connecting to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] before timing out and returning a failure to connect error to the user.</span></span> <span data-ttu-id="5888b-133">Per modificare questa impostazione, riconnettersi con le proprietà di connessione desiderate.</span><span class="sxs-lookup"><span data-stu-id="5888b-133">To change this, connect again with the desired connection properties.</span></span>  
  
 <span data-ttu-id="5888b-134">**Timeout esecuzione**</span><span class="sxs-lookup"><span data-stu-id="5888b-134">**Execution Timeout**</span></span>  
 <span data-ttu-id="5888b-135">Tempo di attesa in secondi prima del completamento dell'esecuzione di un'attività nel server.</span><span class="sxs-lookup"><span data-stu-id="5888b-135">The amount of time in seconds to wait before execution of a task is completed on the server.</span></span> <span data-ttu-id="5888b-136">Per modificare questa impostazione, riconnettersi con le proprietà di connessione desiderate.</span><span class="sxs-lookup"><span data-stu-id="5888b-136">To change this, connect again with the desired connection properties.</span></span>  
  
 <span data-ttu-id="5888b-137">**Crittografata**</span><span class="sxs-lookup"><span data-stu-id="5888b-137">**Encrypted**</span></span>  
 <span data-ttu-id="5888b-138">Consente di indicare se la connessione corrente è crittografata.</span><span class="sxs-lookup"><span data-stu-id="5888b-138">Whether the current connection is encrypted.</span></span> <span data-ttu-id="5888b-139">Per modificare questa impostazione, riconnettersi con le proprietà di connessione desiderate.</span><span class="sxs-lookup"><span data-stu-id="5888b-139">To change this, connect again with the desired connection properties.</span></span>  
  
## <a name="product-category"></a><span data-ttu-id="5888b-140">Categoria di prodotto</span><span class="sxs-lookup"><span data-stu-id="5888b-140">Product Category</span></span>  
 <span data-ttu-id="5888b-141">Consente di visualizzare le proprietà del prodotto per la connessione corrente.</span><span class="sxs-lookup"><span data-stu-id="5888b-141">View product properties for the current connection.</span></span> <span data-ttu-id="5888b-142">Queste proprietà descrivono il prodotto server, la versione, il nome istanza e le regole di confronto.</span><span class="sxs-lookup"><span data-stu-id="5888b-142">These properties describe the server product, version, instance name, and collation.</span></span> <span data-ttu-id="5888b-143">Le proprietà vengono impostate durante l'installazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5888b-143">The properties are set during [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] installation.</span></span>  
  
 <span data-ttu-id="5888b-144">**Nome prodotto**</span><span class="sxs-lookup"><span data-stu-id="5888b-144">**Product Name**</span></span>  
 <span data-ttu-id="5888b-145">Il nome del prodotto [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5888b-145">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] product name.</span></span>  
  
 <span data-ttu-id="5888b-146">**Versione prodotto**</span><span class="sxs-lookup"><span data-stu-id="5888b-146">**Product Version**</span></span>  
 <span data-ttu-id="5888b-147">La versione del prodotto [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5888b-147">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] product version.</span></span>  
  
 <span data-ttu-id="5888b-148">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="5888b-148">**Server Name**</span></span>  
 <span data-ttu-id="5888b-149">Il nome del computer su cui è in esecuzione [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5888b-149">The name of the computer running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="5888b-150">**Nome istanza**</span><span class="sxs-lookup"><span data-stu-id="5888b-150">**Instance Name**</span></span>  
 <span data-ttu-id="5888b-151">Nome dell'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="5888b-151">The instance name of the server.</span></span> <span data-ttu-id="5888b-152">L'istanza predefinita è vuota.</span><span class="sxs-lookup"><span data-stu-id="5888b-152">The default instance is blank.</span></span>  
  
 <span data-ttu-id="5888b-153">**Lingua**</span><span class="sxs-lookup"><span data-stu-id="5888b-153">**Language**</span></span>  
 <span data-ttu-id="5888b-154">Lingua della versione del prodotto [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5888b-154">The language version of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] product.</span></span>  
  
 <span data-ttu-id="5888b-155">**Regole di confronto**</span><span class="sxs-lookup"><span data-stu-id="5888b-155">**Collation**</span></span>  
 <span data-ttu-id="5888b-156">Regole di confronto del server.</span><span class="sxs-lookup"><span data-stu-id="5888b-156">The collation of the server.</span></span>  
  
## <a name="server-environment-category"></a><span data-ttu-id="5888b-157">Ambiente server</span><span class="sxs-lookup"><span data-stu-id="5888b-157">Server Environment Category</span></span>  
 <span data-ttu-id="5888b-158">Consente di visualizzare le proprietà dell'ambiente del server per la connessione corrente correlate all'hardware e al sistema operativo del server.</span><span class="sxs-lookup"><span data-stu-id="5888b-158">View server environment properties for the current connection related to the server hardware and operating system.</span></span> <span data-ttu-id="5888b-159">Le proprietà non possono essere configurate da [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5888b-159">The properties cannot be configured by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="5888b-160">**Nome computer**</span><span class="sxs-lookup"><span data-stu-id="5888b-160">**Computer Name**</span></span>  
 <span data-ttu-id="5888b-161">Nome del computer server che esegue [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5888b-161">The name of the server computer that is running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="5888b-162">**Piattaforma**</span><span class="sxs-lookup"><span data-stu-id="5888b-162">**Platform**</span></span>  
 <span data-ttu-id="5888b-163">Nome del sistema operativo, nome del produttore e famiglia di CPU del server.</span><span class="sxs-lookup"><span data-stu-id="5888b-163">The operating system name, manufacturer name, and CPU family of the server.</span></span>  
  
 <span data-ttu-id="5888b-164">**Sistema operativo**</span><span class="sxs-lookup"><span data-stu-id="5888b-164">**Operating System**</span></span>  
 <span data-ttu-id="5888b-165">Versione di [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows installata nel server.</span><span class="sxs-lookup"><span data-stu-id="5888b-165">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows version installed on the server.</span></span>  
  
 <span data-ttu-id="5888b-166">**Processori**</span><span class="sxs-lookup"><span data-stu-id="5888b-166">**Processors**</span></span>  
 <span data-ttu-id="5888b-167">Numero di processori presenti nel server.</span><span class="sxs-lookup"><span data-stu-id="5888b-167">The number of processors on the server.</span></span>  
  
 <span data-ttu-id="5888b-168">**Memoria sistema operativo**</span><span class="sxs-lookup"><span data-stu-id="5888b-168">**Operating System Memory**</span></span>  
 <span data-ttu-id="5888b-169">Quantità totale di memoria fisica disponibile nel server espressa in megabyte (MB).</span><span class="sxs-lookup"><span data-stu-id="5888b-169">The total amount of physical memory on the server, in megabytes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5888b-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5888b-170">See Also</span></span>  
 <span data-ttu-id="5888b-171">[Pagine delle proprietà in SQL Server Management Studio](../ssms/property-pages-in-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="5888b-171">[Property Pages in SQL Server Management Studio](../ssms/property-pages-in-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="5888b-172">Connetti al server &#40;Pagina di accesso&#41; Motore di database</span><span class="sxs-lookup"><span data-stu-id="5888b-172">Connect to Server &#40;Login Page&#41; Database Engine</span></span>](../ssms/f1-help/connect-to-server-login-page-database-engine.md)  
  
  
