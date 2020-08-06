---
title: Nuova registrazione o modifica registrazione server (scheda generale) (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.registerserver.general.reportserver.f1
ms.assetid: 5f899a8e-52ef-46b5-b7a9-f200ccd9f724
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 195756498dcefe4686d4b06e758dba9919c0b304
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636872"
---
# <a name="new-or-edit-server-registration-general-tab-reporting-services"></a><span data-ttu-id="0020c-102">Creazione o modifica della registrazione del server (scheda Generale) (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="0020c-102">New or Edit Server Registration (General Tab) (Reporting Services)</span></span>
  <span data-ttu-id="0020c-103">Utilizzare questa scheda per specificare le opzioni per la registrazione di un'istanza di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0020c-103">Use this tab to specify options when registering an instance of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0020c-104">Per accedere a questa pagina, in Server registrati fare clic su **Reporting Services** sulla barra degli strumenti **Server registrati** , fare clic con il pulsante destro del mouse su qualsiasi gruppo di server registrati, ad esempio **Reporting Services**, scegliere **Nuovo**e quindi fare clic su **Nuova registrazione server**.</span><span class="sxs-lookup"><span data-stu-id="0020c-104">To access this page, in Registered Servers, click **Reporting Services** on the **Registered Servers** toolbar, right-click any registered servers group such as **Reporting Services**, point to **New**, and then click **Server Registration**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0020c-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="0020c-105">Options</span></span>  
 <span data-ttu-id="0020c-106">**Tipo di server**</span><span class="sxs-lookup"><span data-stu-id="0020c-106">**Server type**</span></span>  
 <span data-ttu-id="0020c-107">Quando un server viene registrato da server registrati, la casella **tipo server** è di sola lettura e corrisponde al tipo di server visualizzato nel riquadro **Server registrati** .</span><span class="sxs-lookup"><span data-stu-id="0020c-107">When a server is registered from Registered Servers, the **Server type** box is read-only, and it matches the type of server displayed in the **Registered Servers** pane.</span></span> <span data-ttu-id="0020c-108">Per registrare un tipo diverso di server, selezionare il server desiderato dalla barra degli strumenti **Server registrati** prima di iniziare la registrazione del nuovo server.</span><span class="sxs-lookup"><span data-stu-id="0020c-108">To register a different type of server, click the server you want on the **Registered Servers** toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="0020c-109">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="0020c-109">**Server name**</span></span>  
 <span data-ttu-id="0020c-110">Consente di selezionare l'istanza del server di report a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="0020c-110">Specify the report server instance to connect to.</span></span> <span data-ttu-id="0020c-111">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]è possibile accedere a un server di report tramite il nome della relativa istanza.</span><span class="sxs-lookup"><span data-stu-id="0020c-111">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], you can access a report server through its instance name.</span></span> <span data-ttu-id="0020c-112">È possibile disporre di un'istanza del server di report per ogni istanza di SQL Server installata</span><span class="sxs-lookup"><span data-stu-id="0020c-112">You can have one report server instance for each SQL Server instance that you install.</span></span> <span data-ttu-id="0020c-113">Se si utilizza l'istanza predefinita, digitare il nome dell'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0020c-113">If you are using the default instance, type the name of the SQL Server instance.</span></span> <span data-ttu-id="0020c-114">Se si utilizza un'istanza denominata, indicarla nel formato MSSQL$instancename per la connessione al server di report.</span><span class="sxs-lookup"><span data-stu-id="0020c-114">If you are using a named instance, specify the named instance to connect to the report server in the format MSSQL$InstanceName.</span></span>  
  
 <span data-ttu-id="0020c-115">**autenticazione**</span><span class="sxs-lookup"><span data-stu-id="0020c-115">**Authentication**</span></span>  
 <span data-ttu-id="0020c-116">Il processo di autenticazione a un server di report viene eseguito tramite Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="0020c-116">Authentication to a report server is made through Internet Information Services (IIS).</span></span> <span data-ttu-id="0020c-117">Selezionare una delle modalità di autenticazione disponibili seguenti per la connessione a Reporting Services:</span><span class="sxs-lookup"><span data-stu-id="0020c-117">Select from one of the following authentication modes when connecting to Reporting Services:</span></span>  
  
 <span data-ttu-id="0020c-118">**Modalità di autenticazione di Windows (Autenticazione di Windows)**</span><span class="sxs-lookup"><span data-stu-id="0020c-118">**Windows Authentication Mode (Windows Authentication)**</span></span>  
 <span data-ttu-id="0020c-119">Consente di connettersi a un'istanza del server di report tramite le credenziali di [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="0020c-119">Connect to the report server instance using your [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows credentials.</span></span>  
  
 <span data-ttu-id="0020c-120">**Autenticazione base**</span><span class="sxs-lookup"><span data-stu-id="0020c-120">**Basic Authentication**</span></span>  
 <span data-ttu-id="0020c-121">Consente di connettersi mediante la modalità di **Autenticazione di base** se l'installazione di Reporting Services è configurata per usarla.</span><span class="sxs-lookup"><span data-stu-id="0020c-121">Connect using **Basic Authentication** if your Reporting Services installation is configured to use Basic Authentication.</span></span>  
  
 <span data-ttu-id="0020c-122">**Autenticazione basata su form**</span><span class="sxs-lookup"><span data-stu-id="0020c-122">**Forms Authentication**</span></span>  
 <span data-ttu-id="0020c-123">Consente di connettersi mediante la modalità **Autenticazione basata su form** se l'installazione di Reporting Services è configurata per usare un'estensione di autenticazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="0020c-123">Connect using **Forms Authentication** if your Reporting Services installation is configured to use a custom authentication extension.</span></span>  
  
 <span data-ttu-id="0020c-124">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="0020c-124">**User Name**</span></span>  
 <span data-ttu-id="0020c-125">Immettere il nome account di accesso da utilizzare per la connessione.</span><span class="sxs-lookup"><span data-stu-id="0020c-125">Enter the login name to use for the connection.</span></span> <span data-ttu-id="0020c-126">Questa opzione è disponibile solo se si è scelto di utilizzare **l'autenticazione di base** o **basata su form**.</span><span class="sxs-lookup"><span data-stu-id="0020c-126">This option is only available if you have selected **Basic** or **Forms Authentication**.</span></span>  
  
 <span data-ttu-id="0020c-127">**Password**</span><span class="sxs-lookup"><span data-stu-id="0020c-127">**Password**</span></span>  
 <span data-ttu-id="0020c-128">Immettere il nome utente e la password</span><span class="sxs-lookup"><span data-stu-id="0020c-128">Enter the password for the user name.</span></span> <span data-ttu-id="0020c-129">Questa opzione può essere modificata solo se si è scelto di utilizzare **l'autenticazione di base** o **basata su form**.</span><span class="sxs-lookup"><span data-stu-id="0020c-129">This option is only editable if you have selected **Basic** or **Forms Authentication**.</span></span>  
  
 <span data-ttu-id="0020c-130">**Memorizza password**</span><span class="sxs-lookup"><span data-stu-id="0020c-130">**Remember password**</span></span>  
 <span data-ttu-id="0020c-131">Consente di archiviare la password immessa.</span><span class="sxs-lookup"><span data-stu-id="0020c-131">Store the password you have entered.</span></span> <span data-ttu-id="0020c-132">Questa opzione è disponibile solo se si è scelto di utilizzare **l'autenticazione di base** o **basata su form**.</span><span class="sxs-lookup"><span data-stu-id="0020c-132">This option is only available if you have clicked **Basic** or **Forms Authentication**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0020c-133">Se la password è stata archiviata e si desidera arrestarne la memorizzazione, deselezionare questa casella di controllo e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0020c-133">If you have stored the password and want to stop storing it, clear this check box and then click **Save**.</span></span>  
  
 <span data-ttu-id="0020c-134">**Nome server registrato**</span><span class="sxs-lookup"><span data-stu-id="0020c-134">**Registered server name**</span></span>  
 <span data-ttu-id="0020c-135">Nome che si desidera venga visualizzato nel componente Server registrati.</span><span class="sxs-lookup"><span data-stu-id="0020c-135">The name you want to appear in Registered Servers.</span></span> <span data-ttu-id="0020c-136">Non è necessario che questo nome corrisponda a quello indicato nella casella **Nome server** .</span><span class="sxs-lookup"><span data-stu-id="0020c-136">This name does not have to match the name in the **Server name** box.</span></span>  
  
 <span data-ttu-id="0020c-137">**Descrizione server registrato**</span><span class="sxs-lookup"><span data-stu-id="0020c-137">**Registered server description**</span></span>  
 <span data-ttu-id="0020c-138">Consente di immettere una descrizione facoltativa del server.</span><span class="sxs-lookup"><span data-stu-id="0020c-138">Enter an optional description of the server.</span></span>  
  
 <span data-ttu-id="0020c-139">**Test**</span><span class="sxs-lookup"><span data-stu-id="0020c-139">**Test**</span></span>  
 <span data-ttu-id="0020c-140">Consente di testare la connessione al server selezionato in **Nome server**.</span><span class="sxs-lookup"><span data-stu-id="0020c-140">Click to test the connection to the server selected in **Server name**.</span></span>  
  
 <span data-ttu-id="0020c-141">**Salva**</span><span class="sxs-lookup"><span data-stu-id="0020c-141">**Save**</span></span>  
 <span data-ttu-id="0020c-142">Fare clic su questo pulsante per salvare le impostazioni del server registrato.</span><span class="sxs-lookup"><span data-stu-id="0020c-142">Click to save the registered server settings.</span></span>  
  
  
