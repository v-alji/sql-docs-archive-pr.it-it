---
title: Proprietà del server di pubblicazione replica di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.configdistwizard.distpubproperties.f1
- sql12.rep.configdistwizard.pubproperties.general.f1
- sql12.rep.configdistwizard.pubproperties.pubdb.f1
- sql12.rep.configdistwizard.pubproperties.subscribers.f1
ms.assetid: 98df1aea-0406-40bf-a917-4bd80464125c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f3e14f82e855cc29f83859d85dfdaaf85a1bda37
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716252"
---
# <a name="sql-server-replication-publisher-properties"></a><span data-ttu-id="cfaef-102">Proprietà del server di replica di SQL Server</span><span class="sxs-lookup"><span data-stu-id="cfaef-102">SQL Server Replication Publisher Properties</span></span>
  <span data-ttu-id="cfaef-103">In questa sezione vengono fornite informazioni sulle proprietà del server di pubblicazione disponibili nel server di distribuzione e nel server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="cfaef-103">This section contains information on Publisher properties available at the Distributor and the Publisher.</span></span> 

## <a name="general"></a><span data-ttu-id="cfaef-104">Generale</span><span class="sxs-lookup"><span data-stu-id="cfaef-104">General</span></span>  
  <span data-ttu-id="cfaef-105"> La pagina **Generale** della finestra di dialogo **Proprietà server di pubblicazione** visualizza informazioni di sola lettura sul server di distribuzione e sul database di distribuzione usati dal server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="cfaef-105">The **General** page of the **Publisher Properties** dialog box displays read-only information on the Distributor and distribution database that the Publisher uses.</span></span> <span data-ttu-id="cfaef-106">Per modificare il server di distribuzione o il database di distribuzione per un server di pubblicazione, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cfaef-106">To change the Distributor or distribution database for a Publisher:</span></span>  
  
1.  <span data-ttu-id="cfaef-107">Disabilitare la pubblicazione nel server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="cfaef-107">Disable publishing on the Publisher.</span></span> <span data-ttu-id="cfaef-108">Per altre informazioni, vedere [Disabilitare la pubblicazione e la distribuzione](disable-publishing-and-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="cfaef-108">For more information, see [Disable Publishing and Distribution](disable-publishing-and-distribution.md).</span></span>    
2.  <span data-ttu-id="cfaef-109">Riconfigurare la pubblicazione e la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cfaef-109">Reconfigure publishing and distribution.</span></span> <span data-ttu-id="cfaef-110">Per altre informazioni, vedere [Configure Publishing and Distribution](configure-publishing-and-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="cfaef-110">For more information, see [Configure Publishing and Distribution](configure-publishing-and-distribution.md).</span></span>  

## <a name="distributor"></a><span data-ttu-id="cfaef-111">Database di distribuzione</span><span class="sxs-lookup"><span data-stu-id="cfaef-111">Distributor</span></span>
  <span data-ttu-id="cfaef-112"> La finestra di dialogo **Proprietà server di pubblicazione** consente di visualizzare e modificare le proprietà associate alla relazione tra il server di pubblicazione e il relativo server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cfaef-112">The **Publisher Properties** dialog box allows you to view and modify properties associated with the relationship between the Publisher and its Distributor.</span></span>  
  
### <a name="options"></a><span data-ttu-id="cfaef-113">Opzioni</span><span class="sxs-lookup"><span data-stu-id="cfaef-113">Options</span></span>  
 <span data-ttu-id="cfaef-114">**Connessione agente al server di pubblicazione**</span><span class="sxs-lookup"><span data-stu-id="cfaef-114">**Agent Connection to the Publisher**</span></span>  
 <span data-ttu-id="cfaef-115">Consente di specificare il contesto in cui gli agenti indicati di seguito creeranno connessioni dal server di distribuzione al server di pubblicazione:</span><span class="sxs-lookup"><span data-stu-id="cfaef-115">Specify the context under which the following agents make connections from the Distributor to the Publisher:</span></span>  
  
-   <span data-ttu-id="cfaef-116">Agente di lettura coda per pubblicazioni transazionali che consentono sottoscrizioni ad aggiornamento in coda.</span><span class="sxs-lookup"><span data-stu-id="cfaef-116">The Queue Reader Agent for transactional publications that allow queued updating subscriptions.</span></span>  
  
-   <span data-ttu-id="cfaef-117">Agente snapshot e agente di lettura log per pubblicazioni Oracle.</span><span class="sxs-lookup"><span data-stu-id="cfaef-117">The Snapshot Agent and Log Reader Agent for Oracle publications.</span></span>  
  
 <span data-ttu-id="cfaef-118">Selezionare **Rappresenta l'account del processo dell'agente** per stabilire una connessione al server di pubblicazione tramite il contesto dell'account di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows con cui vengono eseguiti gli agenti oppure specificare **Autenticazione di SQL Server**e quindi immettere un valore per **Nome account di accesso** e **Password**.</span><span class="sxs-lookup"><span data-stu-id="cfaef-118">Select **Impersonate agent process account** to make connections to the Publisher using the context of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which these agents run, or specify **SQL Server Authentication**, and then enter a value for **Login** and **Password**.</span></span> <span data-ttu-id="cfaef-119">È consigliabile scegliere l'opzione **Rappresenta l'account del processo dell'agente**.</span><span class="sxs-lookup"><span data-stu-id="cfaef-119">It is recommended that you select **Impersonate agent process account**.</span></span> <span data-ttu-id="cfaef-120">Per altre informazioni sulla sicurezza dell'agente, vedere [Modello di sicurezza dell'agente di replica](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="cfaef-120">For more information on agent security, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
 <span data-ttu-id="cfaef-121">Gli account di Windows con cui vengono eseguiti questi agenti sono specificati nella Creazione guidata nuova pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="cfaef-121">The Windows accounts under which these agents run are specified in the New Publication Wizard.</span></span> <span data-ttu-id="cfaef-122">È possibile modificare gli account seguenti:</span><span class="sxs-lookup"><span data-stu-id="cfaef-122">These accounts can be changed:</span></span>  
  
-   <span data-ttu-id="cfaef-123">Nella finestra di dialogo **Proprietà server di distribuzione** per l'agente di lettura coda.</span><span class="sxs-lookup"><span data-stu-id="cfaef-123">In the **Distributor Properties** dialog box for the Queue Reader Agent.</span></span>  
  
-   <span data-ttu-id="cfaef-124">Nella finestra di dialogo **Proprietà server di pubblicazione** per gli agenti snapshot e di lettura log.</span><span class="sxs-lookup"><span data-stu-id="cfaef-124">In the **Publication Properties** dialog box for the Snapshot Agent and Log Reader Agent.</span></span>  
  
 <span data-ttu-id="cfaef-125">**Varie**</span><span class="sxs-lookup"><span data-stu-id="cfaef-125">**Miscellaneous**</span></span>  
 <span data-ttu-id="cfaef-126">Le proprietà **Tipo server di pubblicazione** e **Nome database di distribuzione** sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="cfaef-126">The properties **Publisher Type** and **Distribution Database Name** are read-only.</span></span> <span data-ttu-id="cfaef-127">La proprietà **Cartella snapshot predefinita** può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="cfaef-127">The property **Default Snapshot Folder** can be changed.</span></span> <span data-ttu-id="cfaef-128">Per altre informazioni sulla cartella snapshot, vedere [Proteggere la cartella snapshot](security/secure-the-snapshot-folder.md).</span><span class="sxs-lookup"><span data-stu-id="cfaef-128">For more information about the snapshot folder, see [Secure the Snapshot Folder](security/secure-the-snapshot-folder.md).</span></span>  
  

## <a name="publication-databases"></a><span data-ttu-id="cfaef-129">Database di pubblicazione</span><span class="sxs-lookup"><span data-stu-id="cfaef-129">Publication Databases</span></span>
  <span data-ttu-id="cfaef-130">La pagina **Database di pubblicazione** della finestra di dialogo **Proprietà server di pubblicazione** consente a un utente membro del ruolo predefinito del server **sysadmin** di abilitare i database per la replica.</span><span class="sxs-lookup"><span data-stu-id="cfaef-130">The **Publication Databases** page of the **Publisher Properties** dialog box allows a user in the **sysadmin** fixed server role to enable databases for replication.</span></span> <span data-ttu-id="cfaef-131">L'abilitazione di un database non ne implica la sua pubblicazione, ma consente a qualsiasi utente membro del ruolo predefinito del database **db_owner** per tale database di creare una o più pubblicazioni sul database.</span><span class="sxs-lookup"><span data-stu-id="cfaef-131">Enabling a database does not publish that database; rather, it allows any user in the **db_owner** fixed database role for that database to create one or more publications on the database.</span></span>  
  
### <a name="options"></a><span data-ttu-id="cfaef-132">Opzioni</span><span class="sxs-lookup"><span data-stu-id="cfaef-132">Options</span></span>  
 <span data-ttu-id="cfaef-133">**Transazionale**</span><span class="sxs-lookup"><span data-stu-id="cfaef-133">**Transactional**</span></span>  
 <span data-ttu-id="cfaef-134">Selezionare questa casella di controllo per consentire agli utenti membri del ruolo predefinito del database **db_owner** di creare pubblicazioni snapshot o pubblicazioni transazionali nel database.</span><span class="sxs-lookup"><span data-stu-id="cfaef-134">Select this check box to allow users in the **db_owner** fixed database role to create snapshot publications or transactional publications in the database.</span></span> 
  
 <span data-ttu-id="cfaef-135">**Merge**</span><span class="sxs-lookup"><span data-stu-id="cfaef-135">**Merge**</span></span>  
 <span data-ttu-id="cfaef-136">Selezionare questa casella di controllo per consentire agli utenti membri del ruolo predefinito del database **db_owner** di creare pubblicazioni di tipo merge nel database.</span><span class="sxs-lookup"><span data-stu-id="cfaef-136">Select this check box to allow users in the **db_owner** fixed database role to create merge publications in the database.</span></span>  

## <a name="subscribers"></a><span data-ttu-id="cfaef-137">Sottoscrittori</span><span class="sxs-lookup"><span data-stu-id="cfaef-137">Subscribers</span></span>

  <span data-ttu-id="cfaef-138">La pagina **Sottoscrittori** della finestra di dialogo **Proprietà server di pubblicazione** viene usata per i server di pubblicazione che eseguono versioni di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] precedenti a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cfaef-138">The **Subscribers** page of the **Publisher Properties** dialog box is used for Publishers running versions of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="cfaef-139">Questa pagina consente di abilitare i Sottoscrittori al ricevimento di dati dalle pubblicazioni incluse nel server di pubblicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="cfaef-139">The page allows you to enable Subscribers to receive data from publications on this Publisher.</span></span> <span data-ttu-id="cfaef-140">L'abilitazione di un Sottoscrittore al ricevimento di dati dal server di pubblicazione corrente non crea sottoscrizioni delle pubblicazioni incluse nel server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="cfaef-140">Enabling a Subscriber to receive data from this Publisher does not create subscriptions to publications on this Publisher.</span></span> <span data-ttu-id="cfaef-141">Per creare una sottoscrizione è necessario utilizzare la Creazione guidata nuova sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="cfaef-141">To create a subscription, you must use the New Subscription Wizard.</span></span>  
  
### <a name="options"></a><span data-ttu-id="cfaef-142">Opzioni</span><span class="sxs-lookup"><span data-stu-id="cfaef-142">Options</span></span>  
 <span data-ttu-id="cfaef-143">**Sottoscrittori**</span><span class="sxs-lookup"><span data-stu-id="cfaef-143">**Subscribers**</span></span>  
 <span data-ttu-id="cfaef-144">La griglia delle proprietà **Sottoscrittori** visualizza i Sottoscrittori abilitati al ricevimento di dati dalle pubblicazioni incluse nel server di pubblicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="cfaef-144">The **Subscribers** property grid shows Subscribers that are enabled to receive data from publications on this Publisher.</span></span> <span data-ttu-id="cfaef-145">Per visualizzare e impostare proprietà aggiuntive fare clic sul pulsante delle proprietà (**...**) accanto a un Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="cfaef-145">Click the properties button (**...**) next to a Subscriber to view and set additional properties.</span></span>  
  
 <span data-ttu-id="cfaef-146">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="cfaef-146">**Add**</span></span>  
 <span data-ttu-id="cfaef-147">Fare clic su **Aggiungi** per aggiungere un Sottoscrittore e quindi fare clic su **Aggiungi Sottoscrittore SQL Server** o su **Aggiungi Sottoscrittore non SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="cfaef-147">Click **Add** to add a Subscriber, and then click **Add SQL Server Subscriber** or **Add Non-SQL Server Subscriber**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="cfaef-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cfaef-148">See Also</span></span>  
 [<span data-ttu-id="cfaef-149">Visualizzare e modificare le proprietà del server di pubblicazione e del database di distribuzione</span><span class="sxs-lookup"><span data-stu-id="cfaef-149">View and Modify Distributor and Publisher Properties</span></span>](view-and-modify-distributor-and-publisher-properties.md)   

  
  
