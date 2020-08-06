---
title: Connetti al server (Motore di database) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.connectoserverunknownservertype.f1
- sql12.swb.connection.login.sqlserver.f1
- sql12.swb.connection.login.sqlce.f1
- sql12.swb.manageSS2k.f1
- sql12.swb.connecttoce.f1
- sql12.swb.connecttoce.connectionproperties.f1
ms.assetid: ee9017b4-8a19-4360-9003-9e6484082d41
author: stevestein
ms.author: sstein
ms.openlocfilehash: ca227d1a3bbc13160962ba2fcad23ff011c950f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717256"
---
# <a name="connect-to-server-database-engine"></a><span data-ttu-id="62fbf-102">Connetti al server (Motore di database)</span><span class="sxs-lookup"><span data-stu-id="62fbf-102">Connect to Server (Database Engine)</span></span>
  <span data-ttu-id="62fbf-103">Usare questa finestra di dialogo per visualizzare o specificare le opzioni per la connessione a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62fbf-103">Use this dialog to view or specify options when connecting to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="62fbf-104">Nella maggior parte dei casi è possibile connettersi specificando il nome del computer del server di database nella casella **Nome server** e facendo clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="62fbf-104">In most cases, you can connect by entering the computer name of the database server in the **Server name** box and then clicking **Connect**.</span></span> <span data-ttu-id="62fbf-105">Se ci si connette a [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], usare il nome del computer seguito da **\sqlexpress**.</span><span class="sxs-lookup"><span data-stu-id="62fbf-105">If you are connecting to [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], use the computer name followed by **\sqlexpress**.</span></span>  
  
 <span data-ttu-id="62fbf-106">Molti fattori possono incidere sulla possibilità di connettersi a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62fbf-106">Many factors can affect your ability to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="62fbf-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="62fbf-107">Options</span></span>  
 <span data-ttu-id="62fbf-108">**Tipo di server**</span><span class="sxs-lookup"><span data-stu-id="62fbf-108">**Server type**</span></span>  
 <span data-ttu-id="62fbf-109">Per la registrazione di un server da Esplora oggetti, selezionare il tipo di server a cui connettersi, ovvero [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62fbf-109">When registering a server from Object Explorer, select the type of server to connect to: [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="62fbf-110">Nelle altre parti della finestra di dialogo vengono visualizzate solo le opzioni applicabili al tipo di server selezionato.</span><span class="sxs-lookup"><span data-stu-id="62fbf-110">The rest of the dialog shows only the options that apply to the selected server type.</span></span> <span data-ttu-id="62fbf-111">Durante la registrazione di un server da Server registrati, la casella **Tipo server** è di sola lettura e corrisponde al tipo di server visualizzato nel componente Server registrati.</span><span class="sxs-lookup"><span data-stu-id="62fbf-111">When registering a server from Registered Servers, the **Server type** box is read-only, and matches the type of server displayed in the Registered Servers component.</span></span> <span data-ttu-id="62fbf-112">Per registrare un tipo diverso di server, selezionare [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], [!INCLUDE[ssEW](../../includes/ssew-md.md)]o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sulla barra degli strumenti Server registrati prima di iniziare a registrare un nuovo server.</span><span class="sxs-lookup"><span data-stu-id="62fbf-112">To register a different type of server, select [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], [!INCLUDE[ssEW](../../includes/ssew-md.md)], or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] from the Registered Servers toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="62fbf-113">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="62fbf-113">**Server name**</span></span>  
 <span data-ttu-id="62fbf-114">Consente di selezionare l'istanza del server a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="62fbf-114">Select the server instance to connect to.</span></span> <span data-ttu-id="62fbf-115">Per impostazione predefinita verrà visualizzata l'ultima istanza del server a cui è stata effettuata la connessione.</span><span class="sxs-lookup"><span data-stu-id="62fbf-115">The server instance last connected to is displayed by default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="62fbf-116">Per connettersi a un'istanza utente attiva di [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] , eseguire la connessione tramite il protocollo Named Pipes specificando il nome della pipe, ad esempio np:\\\\.\\.\pipe\3C3DF6B1-2262-47\tsql\query. Per altre informazioni, vedere la documentazione di [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="62fbf-116">To connect to an active user instance of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] connect using named pipes protocol specifying the pipe name, such as np:\\\\.\pipe\3C3DF6B1-2262-47\tsql\query For more information, see the [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] documentation.</span></span>  
  
 <span data-ttu-id="62fbf-117">**autenticazione**</span><span class="sxs-lookup"><span data-stu-id="62fbf-117">**Authentication**</span></span>  
 <span data-ttu-id="62fbf-118">Sono disponibili due modalità di autenticazione per la connessione a un'istanza di [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62fbf-118">Two authentication modes are available when connecting to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="62fbf-119">**Modalità di autenticazione di Windows (Autenticazione di Windows)**</span><span class="sxs-lookup"><span data-stu-id="62fbf-119">**Windows Authentication Mode (Windows Authentication)**</span></span>  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="62fbf-120">Tale modalità consente di connettersi tramite un account utente di Windows.</span><span class="sxs-lookup"><span data-stu-id="62fbf-120">Windows Authentication mode allows a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="62fbf-121">**Autenticazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="62fbf-121">**SQL Server Authentication**</span></span>  
 <span data-ttu-id="62fbf-122">Quando un utente si connette con un nome account di accesso e una password specifici da una connessione non affidabile, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] esegue l'autenticazione verificando che sia impostato un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e che la password specificata corrisponda a quella registrata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="62fbf-122">When a user connects with a specified login name and password from a non-trusted connection, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs the authentication itself by checking to see if a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login account has been set up and if the specified password matches the one previously recorded.</span></span> <span data-ttu-id="62fbf-123">Se non è stato impostato alcun account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , l'autenticazione non viene completata e viene segnalato un errore all'utente.</span><span class="sxs-lookup"><span data-stu-id="62fbf-123">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not have a login account set, authentication fails, and the user receives an error message.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="62fbf-124">Se possibile, usare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="62fbf-124">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="62fbf-125">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="62fbf-125">**User name**</span></span>  
 <span data-ttu-id="62fbf-126">Immettere il nome utente da utilizzare per la connessione.</span><span class="sxs-lookup"><span data-stu-id="62fbf-126">Enter the user name to connect with.</span></span> <span data-ttu-id="62fbf-127">Questa opzione è disponibile solo si è scelto di utilizzare l'autenticazione di Windows per la connessione.</span><span class="sxs-lookup"><span data-stu-id="62fbf-127">This option is only available if you have selected to connect using Windows Authentication.</span></span>  
  
 <span data-ttu-id="62fbf-128">**Accesso**</span><span class="sxs-lookup"><span data-stu-id="62fbf-128">**Login**</span></span>  
 <span data-ttu-id="62fbf-129">Immettere l'account di accesso da utilizzare per la connessione.</span><span class="sxs-lookup"><span data-stu-id="62fbf-129">Enter the login to connect with.</span></span> <span data-ttu-id="62fbf-130">Questa opzione è disponibile solo se si è scelto di utilizzare l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per la connessione.</span><span class="sxs-lookup"><span data-stu-id="62fbf-130">This option is only available if you have selected to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="62fbf-131">**Password**</span><span class="sxs-lookup"><span data-stu-id="62fbf-131">**Password**</span></span>  
 <span data-ttu-id="62fbf-132">Immettere la password per l'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="62fbf-132">Enter the password for the login.</span></span> <span data-ttu-id="62fbf-133">Questa opzione è modificabile solo se si è scelto di utilizzare l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per la connessione.</span><span class="sxs-lookup"><span data-stu-id="62fbf-133">This option is only editable if you have selected to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="62fbf-134">**Connettere**</span><span class="sxs-lookup"><span data-stu-id="62fbf-134">**Connect**</span></span>  
 <span data-ttu-id="62fbf-135">Fare clic su questo pulsante per connettersi al server selezionato.</span><span class="sxs-lookup"><span data-stu-id="62fbf-135">Click to connect to the server selected above.</span></span>  
  
 <span data-ttu-id="62fbf-136">**Opzioni**</span><span class="sxs-lookup"><span data-stu-id="62fbf-136">**Options**</span></span>  
 <span data-ttu-id="62fbf-137">Fare clic su questo pulsante per visualizzare ulteriori opzioni per la connessione al server, come le opzioni per la registrazione di un server e la memorizzazione della password.</span><span class="sxs-lookup"><span data-stu-id="62fbf-137">Click to display additional server connection options, such as registering a server and remembering the password.</span></span>  
  
  
