---
title: 'Lezione 3: Configurazione della distribuzione | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: f248984a-0b59-4c2f-a56d-31f8dafe72b5
author: rothja
ms.author: jroth
ms.openlocfilehash: 52b284b6186e599b7afe73bd37ab0a8348ec38da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723696"
---
# <a name="lesson-3-configuring-distribution"></a><span data-ttu-id="170ba-102">Lezione 3: Configurazione della distribuzione</span><span class="sxs-lookup"><span data-stu-id="170ba-102">Lesson 3: Configuring Distribution</span></span>
  <span data-ttu-id="170ba-103">In questa lezione verrà configurata la distribuzione nel server di pubblicazione e verranno impostate le autorizzazioni necessarie per i database di pubblicazione e di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="170ba-103">In this lesson, you will configure distribution at the Publisher and set the required permissions on the publication and distribution databases.</span></span> <span data-ttu-id="170ba-104">Se il server di distribuzione è già stato configurato, è necessario disabilitare la pubblicazione e la distribuzione prima di iniziare questa lezione.</span><span class="sxs-lookup"><span data-stu-id="170ba-104">If you have already configured the Distributor, you must first disable publishing and distribution before you begin this lesson.</span></span> <span data-ttu-id="170ba-105">Non eseguire questa operazione se è necessario mantenere la topologia di replica esistente.</span><span class="sxs-lookup"><span data-stu-id="170ba-105">Do not do this if you must retain an existing replication topology.</span></span>  
  
 <span data-ttu-id="170ba-106">In questa esercitazione non è prevista la configurazione del server di pubblicazione con un server di distribuzione remoto.</span><span class="sxs-lookup"><span data-stu-id="170ba-106">Configuring a Publisher with a remote Distributor is outside the scope of this tutorial.</span></span>  
  
### <a name="configuring-distribution-at-the-publisher"></a><span data-ttu-id="170ba-107">Configurazione della distribuzione nel server di pubblicazione</span><span class="sxs-lookup"><span data-stu-id="170ba-107">Configuring distribution at the Publisher</span></span>  
  
1.  <span data-ttu-id="170ba-108">Connettersi al server di pubblicazione in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]e quindi espandere il nodo del server.</span><span class="sxs-lookup"><span data-stu-id="170ba-108">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="170ba-109">Fare clic con il pulsante destro del mouse sulla cartella **Replica** e scegliere **Configura distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="170ba-109">Right-click the **Replication** folder and click **Configure Distribution**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="170ba-110">Se è stata effettuata la connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando **localhost** anziché il nome effettivo del server, verrà visualizzato un avviso in cui viene indicata l'impossibilità di stabilire una connessione tra [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e il server **'localhost'**.</span><span class="sxs-lookup"><span data-stu-id="170ba-110">If you have connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using **localhost** rather than the actual server name you will be prompted with a warning that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is unable to connect to server **'localhost'**.</span></span> <span data-ttu-id="170ba-111">Fare clic su **OK** nella finestra di dialogo di avviso.</span><span class="sxs-lookup"><span data-stu-id="170ba-111">Click **OK** on the warning dialog.</span></span> <span data-ttu-id="170ba-112">Nella finestra di dialogo **Connetti al server** modificare **Nome server** sostituendo **localhost** con il nome del server.</span><span class="sxs-lookup"><span data-stu-id="170ba-112">In the **Connect to Server** dialog change the **Server name** from **localhost** to the name of your server.</span></span> <span data-ttu-id="170ba-113">Fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="170ba-113">Click **Connect**.</span></span>  
  
     <span data-ttu-id="170ba-114">Verrà avviata la Configurazione guidata distribuzione.</span><span class="sxs-lookup"><span data-stu-id="170ba-114">The Distribution Configuration Wizard launches.</span></span>  
  
3.  <span data-ttu-id="170ba-115">Nella pagina **server di distribuzione** selezionare **'** _\<ServerName>_ **' fungerà da server di distribuzione per se stesso. SQL Server creerà un database di distribuzione e un log**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="170ba-115">On the **Distributor** page, select **'**_\<ServerName>_**' will act as its own Distributor; SQL Server will create a distribution database and log**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="170ba-116">Se [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non è in esecuzione, nella pagina [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**Agent** selezionare **Sì**e configurare l'avvio automatico del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="170ba-116">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not running, on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**Agent Start** page, select **Yes**, configure the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service to start automatically.</span></span> <span data-ttu-id="170ba-117">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="170ba-117">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="170ba-118">Immettere **\\\\** \<_Machine_Name> _**\repldata** nella casella di testo **cartella snapshot** , dove \<*Machine_Name> \* è il nome del server di pubblicazione, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="170ba-118">Enter **\\\\**\<_Machine_Name>_**\repldata** in the **Snapshot folder** text box, where \<*Machine_Name>\* is the name of the Publisher, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="170ba-119">Accettare i valori predefiniti nella pagine seguenti della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="170ba-119">Accept the default values on the remaining pages of the wizard.</span></span>  
  
7.  <span data-ttu-id="170ba-120">Fare clic su **Fine** per abilitare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="170ba-120">Click **Finish** to enable distribution.</span></span>  
  
### <a name="setting-database-permissions-at-the-publisher"></a><span data-ttu-id="170ba-121">Impostazione delle autorizzazioni per il database nel server di pubblicazione</span><span class="sxs-lookup"><span data-stu-id="170ba-121">Setting database permissions at the Publisher</span></span>  
  
1.  <span data-ttu-id="170ba-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] espandere **sicurezza**, fare clic con il pulsante destro del mouse su **account di accesso**, quindi scegliere **nuovo account di accesso**.</span><span class="sxs-lookup"><span data-stu-id="170ba-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand **Security**, right-click **Logins**, and then select **New Login**.</span></span>  
  
2.  <span data-ttu-id="170ba-123">Nella pagina **generale** fare clic su **Cerca**, immettere \<_Machine_Name> _**\ repl_snapshot** nella casella **immettere il nome dell'oggetto da selezionare** , dove \<*Machine_Name> \* è il nome del server di pubblicazione locale, fare clic su **Controlla nomi**e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="170ba-123">On the **General** page, click **Search**, enter \<_Machine_Name>_**\repl_snapshot** in the **Enter the object name to select** box, where \<*Machine_Name>\* is the name of the local Publisher server, click **Check Names**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="170ba-124">Nell'elenco utenti con mapping **a questo account di accesso** nella pagina **mapping** utenti selezionare i database e la **distribuzione** [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="170ba-124">On the **User Mapping** page, in the **Users mapped to this login** list select both the **distribution** and [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] databases.</span></span>  
  
     <span data-ttu-id="170ba-125">Nell'elenco **appartenenza a ruoli del database** selezionare il `db_owner` ruolo per l'account di accesso per entrambi i database.</span><span class="sxs-lookup"><span data-stu-id="170ba-125">In the **Database role membership** list select the `db_owner` role for the login for both databases.</span></span>  
  
4.  <span data-ttu-id="170ba-126">Fare clic su **OK** per creare l'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="170ba-126">Click **OK** to create the login.</span></span>  
  
5.  <span data-ttu-id="170ba-127">Ripetere i passaggi da 1 a 4 per creare un account di accesso per l'account locale repl_logreader.</span><span class="sxs-lookup"><span data-stu-id="170ba-127">Repeat steps 1-4 to create a login for the local repl_logreader account.</span></span> <span data-ttu-id="170ba-128">È necessario eseguire il mapping di questo account di accesso anche agli utenti che sono membri del `db_owner` ruolo predefinito del database nei database **AdventureWorks** e di **distribuzione** .</span><span class="sxs-lookup"><span data-stu-id="170ba-128">This login must also be mapped to users that are members of the `db_owner` fixed database role in the **distribution** and **AdventureWorks** databases.</span></span>  
  
6.  <span data-ttu-id="170ba-129">Ripetere i passaggi da 1 a 4 per creare un account di accesso per l'account locale repl_distribution.</span><span class="sxs-lookup"><span data-stu-id="170ba-129">Repeat steps 1-4 to create a login for the local repl_distribution account.</span></span> <span data-ttu-id="170ba-130">È necessario eseguire il mapping di questo account di accesso a un utente membro del `db_owner` ruolo predefinito del database nel database di **distribuzione** .</span><span class="sxs-lookup"><span data-stu-id="170ba-130">This login must be mapped to a user that is a member of the `db_owner` fixed database role in the **distribution** database.</span></span>  
  
7.  <span data-ttu-id="170ba-131">Ripetere i passaggi da 1 a 4 per creare un account di accesso per l'account locale repl_merge.</span><span class="sxs-lookup"><span data-stu-id="170ba-131">Repeat steps 1-4 to create a login for the local repl_merge account.</span></span> <span data-ttu-id="170ba-132">Questo account deve avere mapping di utenti nel database di **distribuzione** e nel database **AdventureWorks** .</span><span class="sxs-lookup"><span data-stu-id="170ba-132">This login must have user mappings in the **distribution** and **AdventureWorks** databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="170ba-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="170ba-133">See Also</span></span>  
 <span data-ttu-id="170ba-134">[Configura distribuzione](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="170ba-134">[Configure Distribution](configure-distribution.md) </span></span>  
 [<span data-ttu-id="170ba-135">Modello di sicurezza dell'agente di replica</span><span class="sxs-lookup"><span data-stu-id="170ba-135">Replication Agent Security Model</span></span>](security/replication-agent-security-model.md)  
  
  
