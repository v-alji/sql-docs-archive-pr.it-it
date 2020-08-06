---
title: Modificare gli account dei servizi controller e client | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 44a73ddb-18ad-415c-bfbe-126ab2e3290b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 62a054749f1d53323bde5c9d05a1e7632b1dda85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719266"
---
# <a name="modify-the-controller-and-client-services-accounts"></a><span data-ttu-id="79360-102">Modificare gli account dei servizi controller e client</span><span class="sxs-lookup"><span data-stu-id="79360-102">Modify the Controller and Client Services Accounts</span></span>
  <span data-ttu-id="79360-103">In questo argomento verrà illustrato come modificare gli account dei servizi client e controller di Riesecuzione distribuita e quindi riapplicare gli elenchi di controllo di accesso (ACL).</span><span class="sxs-lookup"><span data-stu-id="79360-103">In this topic, you will learn how to modify the Distributed Replay controller and client service accounts, and then reapply the access control lists (ACLs).</span></span>  
  
### <a name="to-start-or-stop-the-distributed-replay-services-using-computer-management"></a><span data-ttu-id="79360-104">Per avviare o arrestare i servizi client Riesecuzione distribuita tramite Gestione computer</span><span class="sxs-lookup"><span data-stu-id="79360-104">To start or stop the Distributed Replay services using Computer Management</span></span>  
  
1.  <span data-ttu-id="79360-105">Nel computer in cui sono installati i servizi Riesecuzione distribuita digitare `dcomcnfg` al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="79360-105">On the computer on which the Distributed Replay services are installed, from the command prompt, type `dcomcnfg`.</span></span>  
  
2.  <span data-ttu-id="79360-106">Fare doppio clic su **Servizi**, scorrere verso il basso e fare clic con il pulsante destro del mouse su \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] riesecuzione distribuita \<service name> \*\*, quindi fare clic su **Avvia** o **Arresta**.</span><span class="sxs-lookup"><span data-stu-id="79360-106">Double-click **Services**, scroll down and right-click **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay \<service name>**, and then click **Start** or **Stop**.</span></span>  
  
### <a name="to-modify-the-distributed-replay-controller-service"></a><span data-ttu-id="79360-107">Per modificare il servizio controller di Riesecuzione distribuita</span><span class="sxs-lookup"><span data-stu-id="79360-107">To modify the Distributed Replay controller service</span></span>  
  
1.  <span data-ttu-id="79360-108">Nel computer controller arrestare il servizio controller di Riesecuzione distribuita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="79360-108">On the controller computer, stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay controller service.</span></span>  
  
2.  <span data-ttu-id="79360-109">In **Servizi** fare clic con il pulsante destro del mouse su **Controller di Riesecuzione distribuita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** , quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="79360-109">Under **Services**, right-click **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Controller**, and then select **Properties**.</span></span>  
  
3.  <span data-ttu-id="79360-110">Nella scheda **Accesso** della finestra **Proprietà di Controller di Riesecuzione distribuita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** selezionare **Account seguente**, digitare il nuovo account di accesso o fare clic su **Sfoglia** per selezionarlo, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="79360-110">In the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Controller Properties** window, on the **Log On** tab, select **This account**, type or click **Browse** to enter the new logon account, and then click **OK**.</span></span>  
  
     <span data-ttu-id="79360-111">**Importante**: quando si configura il controller di Riesecuzione distribuita, è possibile specificare uno o più account utente da usare per eseguire i servizi client di Riesecuzione distribuita.</span><span class="sxs-lookup"><span data-stu-id="79360-111">**Important**: When you configure Distributed Replay Controller, you can specify one or more user accounts that will be used to run the Distributed Replay Client services.</span></span> <span data-ttu-id="79360-112">Di seguito viene fornito l'elenco degli account supportati:</span><span class="sxs-lookup"><span data-stu-id="79360-112">The following is the list of supported accounts:</span></span>  
  
    -   <span data-ttu-id="79360-113">Account utente di dominio</span><span class="sxs-lookup"><span data-stu-id="79360-113">Domain user account</span></span>  
  
    -   <span data-ttu-id="79360-114">Account utente locale creato dall'utente</span><span class="sxs-lookup"><span data-stu-id="79360-114">User created local user account</span></span>  
  
    -   <span data-ttu-id="79360-115">Amministratore</span><span class="sxs-lookup"><span data-stu-id="79360-115">Administrator</span></span>  
  
    -   <span data-ttu-id="79360-116">Account virtuale e account del servizio gestito</span><span class="sxs-lookup"><span data-stu-id="79360-116">Virtual account and MSA (Managed Service Account)</span></span>  
  
    -   <span data-ttu-id="79360-117">Servizi di rete, Servizi locali e Sistema</span><span class="sxs-lookup"><span data-stu-id="79360-117">Network Services, Local Services, and System</span></span>  
  
     <span data-ttu-id="79360-118">Gli account di gruppo (locale o dominio) e gli altri account predefiniti (come Everyone) non sono accettati.</span><span class="sxs-lookup"><span data-stu-id="79360-118">Group accounts (local or domain) and other built-in accounts (like Everyone) are not accepted.</span></span>  
  
4.  <span data-ttu-id="79360-119">Avviare il servizio controller di Riesecuzione distribuita.</span><span class="sxs-lookup"><span data-stu-id="79360-119">Start the Distributed Replay controller service.</span></span>  
  
### <a name="to-modify-the-distributed-replay-client-service"></a><span data-ttu-id="79360-120">Per modificare il servizio client Riesecuzione distribuita</span><span class="sxs-lookup"><span data-stu-id="79360-120">To modify the Distributed Replay client service</span></span>  
  
1.  <span data-ttu-id="79360-121">Prima di modificare il servizio client Riesecuzione distribuita, verificare che l'account del servizio client da modificare sia stato specificato durante l'installazione, nel parametro CTLRUSERS del computer controller.</span><span class="sxs-lookup"><span data-stu-id="79360-121">Before you modify the Distributed Replay client service, make sure the client service account you are changing was specified during setup (in the CTLRUSERS parameter on the controller computer).</span></span> <span data-ttu-id="79360-122">Se l'account del servizio client da modificare non è stato specificato durante l'installazione, è necessario effettuare innanzitutto i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="79360-122">If the client service account you are changing was not specified during setup, you must perform the following steps first:</span></span>  
  
    1.  <span data-ttu-id="79360-123">Arrestare il servizio controller di Riesecuzione distribuita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="79360-123">Stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay controller service.</span></span>  
  
    2.  <span data-ttu-id="79360-124">Nel computer controller in cui è installato il relativo servizio, digitare `dcomcnfg` dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="79360-124">On the controller computer on which the controller service is installed, from the command prompt, type `dcomcnfg`.</span></span>  
  
    3.  <span data-ttu-id="79360-125">Nella finestra **Servizi componenti** passare a **Radice console -> Servizi componenti -> Computer -> Risorse del computer -> Config DCOM ->DReplayController**.</span><span class="sxs-lookup"><span data-stu-id="79360-125">In the **Component Services** window, navigate to **Console Root -> Component Services -> Computers -> My Computer -> DCOM Config ->DReplayController**.</span></span>  
  
    4.  <span data-ttu-id="79360-126">Fare clic con il pulsante destro del mouse su **DReplayController**, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="79360-126">Right-click **DReplayController**, and then click **Properties**.</span></span>  
  
    5.  <span data-ttu-id="79360-127">Nella scheda **Sicurezza** nella finestra **Proprietà di DReplayController** fare clic su **Modifica** nella sezione **Autorizzazioni di esecuzione e attivazione** .</span><span class="sxs-lookup"><span data-stu-id="79360-127">In the **DReplayController Properties** window, on the **Security** tab, click **Edit** in the **Launch and Activation Permissions** section.</span></span>  
  
    6.  <span data-ttu-id="79360-128">Concedere al nuovo account di accesso del servizio client le autorizzazioni **Attivazione locale e Attivazione remota** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="79360-128">Grant the new client service logon account **Local and Remote activation** permissions, and then click **OK**.</span></span>  
  
    7.  <span data-ttu-id="79360-129">Fare clic su **Modifica** nella sezione **Autorizzazioni di accesso** e concedere al nuovo account di accesso del servizio client le autorizzazioni **Accesso locale e Accesso remoto** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="79360-129">Click **Edit** in the **Access Permissions** section, and grant the new client service logon account **Local and Remote access** permissions, and then click **OK**.</span></span>  
  
    8.  <span data-ttu-id="79360-130">Fare clic su **OK** per chiudere la finestra **Proprietà di DReplayController** .</span><span class="sxs-lookup"><span data-stu-id="79360-130">Click **OK** to close the **DReplayController Properties** window.</span></span>  
  
    9. <span data-ttu-id="79360-131">Nel computer controller aggiungere l'account di accesso del servizio client modificato al gruppo **Distributed COM Users** .</span><span class="sxs-lookup"><span data-stu-id="79360-131">On the controller computer, add the changed client service logon account to the **Distributed COM Users** group.</span></span>  
  
    10. <span data-ttu-id="79360-132">Avviare il servizio SQL Server Distributed Replay Controller.</span><span class="sxs-lookup"><span data-stu-id="79360-132">Start the SQL Server Distributed Replay controller service.</span></span>  
  
2.  <span data-ttu-id="79360-133">Arrestare il servizio client Riesecuzione distribuita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="79360-133">Stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay client service.</span></span>  
  
3.  <span data-ttu-id="79360-134">Nella scheda **Accesso** della finestra **Proprietà di Client Riesecuzione distribuita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** scegliere **Account seguente**, digitare il nuovo account di accesso o fare clic su **Sfoglia** per selezionarlo e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="79360-134">In the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Client Properties** window, on the **Log On** tab, select **This account**, type or click **Browse** to enter the new logon account, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="79360-135">Avviare il servizio client Riesecuzione distribuita.</span><span class="sxs-lookup"><span data-stu-id="79360-135">Start the Distributed Replay client service.</span></span>  
  
  
