---
title: Finestra di dialogo Seleziona origine | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.selectsource.f1
ms.assetid: d664c2e5-dd0c-4da8-b27d-aa4ee4fc0ffd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 535d211d6827477fcf029accc27a9000e8c695c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724535"
---
# <a name="select-source-dialog-box"></a><span data-ttu-id="a1c5d-102">Finestra di dialogo Seleziona origine</span><span class="sxs-lookup"><span data-stu-id="a1c5d-102">Select Source Dialog Box</span></span>
  <span data-ttu-id="a1c5d-103">Utilizzare questa finestra di dialogo per selezionare l'origine dei criteri da eseguire.</span><span class="sxs-lookup"><span data-stu-id="a1c5d-103">Use this dialog box to select the source of the policies to be run.</span></span> <span data-ttu-id="a1c5d-104">Per selezionare uno o più file XML che contengono criteri, selezionare **File**.</span><span class="sxs-lookup"><span data-stu-id="a1c5d-104">To select one or more XML files that contain policies, select **Files**.</span></span> <span data-ttu-id="a1c5d-105">Per eseguire i criteri individuati nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], selezionare **Server**.</span><span class="sxs-lookup"><span data-stu-id="a1c5d-105">To run the policies that are found on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], select **Server**.</span></span>  
  
 <span data-ttu-id="a1c5d-106">È possibile aprire questa finestra di dialogo in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="a1c5d-106">You can open this dialog box in several ways.</span></span>  
  
 <span data-ttu-id="a1c5d-107">**Per aprire la finestra di dialogo**</span><span class="sxs-lookup"><span data-stu-id="a1c5d-107">**To open this dialog box**</span></span>  
  
-   <span data-ttu-id="a1c5d-108">In Server registrati fare clic con il pulsante destro del mouse su **Gruppi di server locali** , su qualsiasi server in **Gruppi di server locali**o su qualsiasi server in **Server di gestione centrale**, quindi scegliere **Valuta criteri**.</span><span class="sxs-lookup"><span data-stu-id="a1c5d-108">In Registered Servers, right-click **Local Server Groups** or any server under **Local Server Groups**, or any server under **Central Management Servers**, and then select **Evaluate Policies**.</span></span> <span data-ttu-id="a1c5d-109">Nella pagina **Selezione criteri** della finestra di dialogo **Valuta criteri** fare clic sul pulsante Sfoglia ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="a1c5d-109">In the **Policy Selection** page of the **Evaluate Policies** dialog box, click the Browse (**...**) button.</span></span>  
  
-   <span data-ttu-id="a1c5d-110">In Esplora oggetti espandere **Gestione**, espandere **Gestione criteri**, fare clic con il pulsante destro del mouse su **Criteri**, quindi scegliere **Importa criteri**.</span><span class="sxs-lookup"><span data-stu-id="a1c5d-110">In Object Explorer, expand **Management**, expand **Policy Management**, right-click **Policies**, and select **Import Policy**.</span></span> <span data-ttu-id="a1c5d-111">Nella finestra di dialogo **Importa** fare clic sul pulsante Sfoglia ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="a1c5d-111">In the **Import** dialog box, click the Browse (**...**) button.</span></span>  
  
-   <span data-ttu-id="a1c5d-112">In Esplora oggetti fare clic con il pulsante destro del mouse su un server, un database o un oggetto di database, scegliere **Criteri**, quindi fare clic su **Valuta**.</span><span class="sxs-lookup"><span data-stu-id="a1c5d-112">In Object Explorer, right-click a server, database, or database object, select **Policies**, and then select **Evaluate**.</span></span> <span data-ttu-id="a1c5d-113">Nella pagina **Selezione criteri** della finestra di dialogo **Valuta criteri** fare clic sul pulsante Sfoglia ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="a1c5d-113">In the **Policy Selection** page of the **Evaluate Policies** dialog box, click the Browse (**...**) button.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a1c5d-114">Opzioni</span><span class="sxs-lookup"><span data-stu-id="a1c5d-114">Options</span></span>  
 <span data-ttu-id="a1c5d-115">**File**</span><span class="sxs-lookup"><span data-stu-id="a1c5d-115">**Files**</span></span>  
 <span data-ttu-id="a1c5d-116">Selezionare uno o più file XML che contengono criteri.</span><span class="sxs-lookup"><span data-stu-id="a1c5d-116">Select one or more XML files that contain policies.</span></span>  
  
 <span data-ttu-id="a1c5d-117">**Server**</span><span class="sxs-lookup"><span data-stu-id="a1c5d-117">**Server**</span></span>  
 <span data-ttu-id="a1c5d-118">Consente di selezionare un server contenente i criteri che si desidera eseguire.</span><span class="sxs-lookup"><span data-stu-id="a1c5d-118">Enables you to select a server that contains the policies that you want to run.</span></span>  
  
 <span data-ttu-id="a1c5d-119">**Tipo di server**</span><span class="sxs-lookup"><span data-stu-id="a1c5d-119">**Server type**</span></span>  
 <span data-ttu-id="a1c5d-120">Solo i server del [!INCLUDE[ssDE](../../includes/ssde-md.md)] contengono criteri.</span><span class="sxs-lookup"><span data-stu-id="a1c5d-120">Only [!INCLUDE[ssDE](../../includes/ssde-md.md)] servers contain policies.</span></span> <span data-ttu-id="a1c5d-121">Il contenuto di questa casella è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="a1c5d-121">This box is read-only.</span></span>  
  
 <span data-ttu-id="a1c5d-122">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="a1c5d-122">**Server name**</span></span>  
 <span data-ttu-id="a1c5d-123">Consente di selezionare l'istanza del server a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="a1c5d-123">Select the server instance to connect to.</span></span> <span data-ttu-id="a1c5d-124">Per impostazione predefinita, viene visualizzata l'istanza del server a cui è stata effettuata l'ultima connessione.</span><span class="sxs-lookup"><span data-stu-id="a1c5d-124">By default, the server instance last connected to is displayed.</span></span>  
  
 <span data-ttu-id="a1c5d-125">**autenticazione**</span><span class="sxs-lookup"><span data-stu-id="a1c5d-125">**Authentication**</span></span>  
 <span data-ttu-id="a1c5d-126">Sono disponibili due modalità di autenticazione per la connessione a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1c5d-126">Two authentication modes are available when you connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="a1c5d-127">**Modalità di autenticazione di Windows (Autenticazione di Windows)**</span><span class="sxs-lookup"><span data-stu-id="a1c5d-127">**Windows Authentication Mode (Windows Authentication)**</span></span>  
 <span data-ttu-id="a1c5d-128">La modalità di autenticazione di Windows modalità consente di connettersi tramite un account utente di Windows.</span><span class="sxs-lookup"><span data-stu-id="a1c5d-128">Windows Authentication mode allows for a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="a1c5d-129">**Autenticazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="a1c5d-129">**SQL Server Authentication**</span></span>  
 <span data-ttu-id="a1c5d-130">Quando un utente si connette con un nome di accesso e una password da una connessione di tipo non trusted, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] esegue l'autenticazione verificando che sia impostato un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e che la password specificata corrisponda a quella registrata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="a1c5d-130">When a user connects with a specified login name and password from a nontrusted connection, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs the authentication itself by checking whether a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login account has been set up and whether the specified password matches the one previously recorded.</span></span> <span data-ttu-id="a1c5d-131">Se non è stato impostato alcun account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , l'autenticazione non viene completata e viene segnalato un errore all'utente.</span><span class="sxs-lookup"><span data-stu-id="a1c5d-131">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not have a login account set, authentication fails, and the user receives an error message.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a1c5d-132">Se possibile, usare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="a1c5d-132">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="a1c5d-133">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="a1c5d-133">**User name**</span></span>  
 <span data-ttu-id="a1c5d-134">Immettere il nome utente da utilizzare per la connessione.</span><span class="sxs-lookup"><span data-stu-id="a1c5d-134">Enter the user name to connect with.</span></span> <span data-ttu-id="a1c5d-135">Questa opzione è disponibile solo si è scelto di utilizzare l'autenticazione di Windows per la connessione.</span><span class="sxs-lookup"><span data-stu-id="a1c5d-135">This option is available only if you have selected to connect by using Windows Authentication.</span></span>  
  
 <span data-ttu-id="a1c5d-136">**Accesso**</span><span class="sxs-lookup"><span data-stu-id="a1c5d-136">**Login**</span></span>  
 <span data-ttu-id="a1c5d-137">Immettere l'account di accesso da utilizzare per la connessione.</span><span class="sxs-lookup"><span data-stu-id="a1c5d-137">Enter the login to connect with.</span></span> <span data-ttu-id="a1c5d-138">Questa opzione è disponibile solo se si è scelto di utilizzare l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per la connessione.</span><span class="sxs-lookup"><span data-stu-id="a1c5d-138">This option is available only if you have selected to connect by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="a1c5d-139">**Password**</span><span class="sxs-lookup"><span data-stu-id="a1c5d-139">**Password**</span></span>  
 <span data-ttu-id="a1c5d-140">Immettere la password per l'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="a1c5d-140">Enter the password for the login.</span></span> <span data-ttu-id="a1c5d-141">Questa opzione è modificabile solo se si è scelto di utilizzare l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per la connessione.</span><span class="sxs-lookup"><span data-stu-id="a1c5d-141">This option is editable only if you have selected to connect by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1c5d-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1c5d-142">See Also</span></span>  
 <span data-ttu-id="a1c5d-143">[Nodo Gestione criteri &#40;Esplora oggetti&#41;](../../ssms/object/object-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="a1c5d-143">[Policy Management Node &#40;Object Explorer&#41;](../../ssms/object/object-explorer.md) </span></span>  
 [<span data-ttu-id="a1c5d-144">Amministrazione di server tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="a1c5d-144">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
