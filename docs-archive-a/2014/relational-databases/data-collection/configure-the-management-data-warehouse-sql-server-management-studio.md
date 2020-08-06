---
title: Configurare il data warehouse di gestione (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dc.datacollection.wizard_finish.f1
- sql12.swb.dc.datacollection.wizard_maploginuser.f1
- sql12.swb.dc.datacollection.wizard_welcome.f1
- sql12.swb.dc.datacollection.wizard_choosemdw.f1
- sql12.swb.dc.datacollection.wizard_completecfg.f1
- sql12.swb.dc.datacollection.wizard_config.f1
- sql12.swb.dc.datacollection.wizard_createmdw.f1
helpviewer_keywords:
- data warehouse [SQL Server], multiple instances
- data warehouse [SQL Server], configuring
- Configure Management Data Warehouse Wizard
- management data warehouse, configuring
ms.assetid: 23a584f3-c5e1-414c-9afe-73cd7efbda4b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1ef4ddd518343a3076c72ecc41f9b15ddf092dc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638421"
---
# <a name="configure-the-management-data-warehouse-sql-server-management-studio"></a><span data-ttu-id="66e42-102">Configurazione del data warehouse di gestione (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="66e42-102">Configure the Management Data Warehouse (SQL Server Management Studio)</span></span>
  <span data-ttu-id="66e42-103">In questo argomento viene descritto come configurare il data warehouse di gestione per supportare l'archiviazione dei dati per una singola istanza o per più istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che utilizzano l'agente di raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="66e42-103">This topic describes how to configure the management data warehouse to support data storage on a single instance or multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are using the data collector.</span></span> <span data-ttu-id="66e42-104">Queste istanze possono essere installate nello stesso server o in server diversi.</span><span class="sxs-lookup"><span data-stu-id="66e42-104">These instances can be on the same server or on different servers.</span></span> <span data-ttu-id="66e42-105">In questo argomento vengono fornite anche le descrizioni dell'interfaccia utente per la finestra di dialogo [Configurazione guidata data warehouse di gestione](#Wizard) .</span><span class="sxs-lookup"><span data-stu-id="66e42-105">This topic also provides descriptions of the user interface for the [Configure Data Management Warehouse Wizard](#Wizard) dialog box.</span></span> <span data-ttu-id="66e42-106">Per ulteriori informazioni sulla configurazione di un agente di raccolta dati, vedere [Configure Properties of a Data Collector](configure-properties-of-a-data-collector.md).</span><span class="sxs-lookup"><span data-stu-id="66e42-106">For information about configuring a data collector, see [Configure Properties of a Data Collector](configure-properties-of-a-data-collector.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="66e42-107">Se [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent è configurato per essere eseguito utilizzando uno degli account di servizio del sistema (Sistema locale, Servizio di rete o Servizio locale) e il data warehouse di gestione viene creato in un'istanza diversa da quella dell'agente di raccolta dati, è necessario configurare i set di raccolta in modo che venga utilizzato un proxy per il caricamento di dati nel data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="66e42-107">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is configured to run using one of the System service accounts (Local System, Network Service, or Local Service), and the management data warehouse is created on a different instance from the data collector, you must configure collection sets to use a proxy for uploading data to the management data warehouse.</span></span>  
  
### <a name="configure-the-management-data-warehouse-on-a-single-instance-or-multiple-instances-of-ssnoversion"></a><span data-ttu-id="66e42-108">Configurare il data warehouse di gestione su una o più istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66e42-108">Configure the management data warehouse on a single instance or multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
1.  <span data-ttu-id="66e42-109">Verificare che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="66e42-109">Ensure that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is running.</span></span>  
  
2.  <span data-ttu-id="66e42-110">In Esplora oggetti espandere il nodo **Gestione** .</span><span class="sxs-lookup"><span data-stu-id="66e42-110">In Object Explorer, expand the **Management** node.</span></span>  
  
3.  <span data-ttu-id="66e42-111">Fare clic con il pulsante destro del mouse **Raccolta dati**, espandere **Attività**e fare clic su **Configura data warehouse di gestione**.</span><span class="sxs-lookup"><span data-stu-id="66e42-111">Right-click **Data Collection**, expand **Tasks**, and then click **Configure Management Data Warehouse**.</span></span>  
  
4.  <span data-ttu-id="66e42-112">Utilizzare la [Configurazione guidata data warehouse di gestione](#Wizard) per creare un data warehouse di gestione, configurare gli account di accesso, abilitare la raccolta dati e avviare i **Set di raccolta dati di sistema**.</span><span class="sxs-lookup"><span data-stu-id="66e42-112">Use the [Configure Management Data Warehouse Wizard](#Wizard) to create a management data warehouse, configure logins, enable data collection, and start the **System Data Collection Sets**.</span></span>  
  
     <span data-ttu-id="66e42-113">Per configurare più istanze, continuare con il passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="66e42-113">To configure multiple instances, continue with step 5.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="66e42-114">Una procedura consigliata consiste nell'utilizzo di proxy in distribuzioni in cui l'agente di raccolta dati è installato su più istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che si servono dello stesso data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="66e42-114">It is considered best practice to use proxies in deployments where the data collector is installed on multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are using the same management data warehouse.</span></span>  
  
5.  <span data-ttu-id="66e42-115">Aprire [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] in un'altra istanza ed effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="66e42-115">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] on another instance and do either of the following:</span></span>  
  
    -   <span data-ttu-id="66e42-116">Utilizzare la Configurazione guidata data warehouse di gestione per configurare la raccolta dati per il data warehouse di gestione esistente.</span><span class="sxs-lookup"><span data-stu-id="66e42-116">Use the Configure Management Data Warehouse wizard to configure data collection for the existing management data warehouse.</span></span>  
  
    -   <span data-ttu-id="66e42-117">Fare clic con il pulsante destro del mouse su **Raccolta dati**e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="66e42-117">Right-click **Data Collection**, and then click **Properties**.</span></span> <span data-ttu-id="66e42-118">Nella scheda **Generale** specificare il data warehouse di gestione esistente e il server in cui è installato.</span><span class="sxs-lookup"><span data-stu-id="66e42-118">On the **General** tab, specify the existing management data warehouse and the server that it is installed on.</span></span>  
  
6.  <span data-ttu-id="66e42-119">Ripetere il passaggio 5 fino a quando tutte le istanze del database che utilizzano l'agente di raccolta dati sono configurate per caricare dati sul data warehouse di gestione condiviso.</span><span class="sxs-lookup"><span data-stu-id="66e42-119">Repeat step 5 until all the database instances that use the data collector are configured to upload data to the shared management data warehouse.</span></span>  
  
####  <a name="configure-management-data-warehouse-wizard"></a><a name="Wizard"></a> <span data-ttu-id="66e42-120">Configurazione guidata data warehouse di gestione</span><span class="sxs-lookup"><span data-stu-id="66e42-120">Configure Management Data Warehouse Wizard</span></span>  
 <span data-ttu-id="66e42-121">**Pagina introduttiva**</span><span class="sxs-lookup"><span data-stu-id="66e42-121">**Welcome Page**</span></span>  
  
 <span data-ttu-id="66e42-122">La pagina iniziale corrisponde alla pagina di avvio di Configurazione guidata raccolta dati</span><span class="sxs-lookup"><span data-stu-id="66e42-122">The Welcome page is the starting page of the Configure Data Collection Wizard.</span></span> <span data-ttu-id="66e42-123">e la sua visualizzazione è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="66e42-123">Displaying this page is optional.</span></span>  
  
 <span data-ttu-id="66e42-124">**Non visualizzare più questa pagina iniziale.**</span><span class="sxs-lookup"><span data-stu-id="66e42-124">**Do not show this starting page again.**</span></span>  
 <span data-ttu-id="66e42-125">Selezionare questa opzione per evitare la visualizzazione di questa pagina al prossimo avvio di Configurazione guidata raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="66e42-125">Select to suppress this page the next time you launch the Configure Data Collection Wizard.</span></span>  
  
 <span data-ttu-id="66e42-126">**Configurazione archiviazione del data warehouse di gestione**</span><span class="sxs-lookup"><span data-stu-id="66e42-126">**Configure Management Data Warehouse Storage Page**</span></span>  
  
 <span data-ttu-id="66e42-127">Utilizzare questa pagina per selezionare un server di database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e un data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="66e42-127">Use this page to select a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database server and management data warehouse.</span></span> <span data-ttu-id="66e42-128">Il data warehouse di gestione è un database relazionale in cui vengono archiviati i dati raccolti.</span><span class="sxs-lookup"><span data-stu-id="66e42-128">The management data warehouse is a relational database that will store collected data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="66e42-129">Per creare il data warehouse di gestione nel server è necessario disporre del livello adeguato di autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="66e42-129">You must have the appropriate level of permissions in order to create the management data warehouse on the server.</span></span> <span data-ttu-id="66e42-130">Per alte informazioni, vedere [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="66e42-130">For more information, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span> <span data-ttu-id="66e42-131">È inoltre necessario disporre del livello adeguato di autorizzazioni per la creazione degli account di accesso per i ruoli del data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="66e42-131">You also must have the appropriate level of permissions to create logins for management data warehouse roles.</span></span>  
  
 <span data-ttu-id="66e42-132">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="66e42-132">**Server name**</span></span>  
 <span data-ttu-id="66e42-133">Consente di specificare il nome del server in cui risiederà il data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="66e42-133">Specifies the name of the server that will host the management data warehouse.</span></span>  
  
 <span data-ttu-id="66e42-134">In caso di configurazione di un data warehouse di gestione, **Nome server** è sempre il nome del server locale e non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="66e42-134">When configuring a management data warehouse, **Server name** is always the name of the local server and cannot be modified.</span></span>  
  
 <span data-ttu-id="66e42-135">**Nome database**</span><span class="sxs-lookup"><span data-stu-id="66e42-135">**Database name**</span></span>  
 <span data-ttu-id="66e42-136">Consente di specificare il database relazionale in cui saranno archiviati i dati raccolti.</span><span class="sxs-lookup"><span data-stu-id="66e42-136">Specifies the relational database that will store collected data.</span></span> <span data-ttu-id="66e42-137">Utilizzare l'elenco per selezionare un database esistente o fare clic su **Nuovo** per creare un database nuovo mediante la finestra di dialogo **Nuovo database** .</span><span class="sxs-lookup"><span data-stu-id="66e42-137">Use the list to select an existing database or click **New** to create a new database using the **New Database** dialog.</span></span>  
  
 <span data-ttu-id="66e42-138">L'opzione **Nuovo** è disponibile solo in caso di configurazione di un set di raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="66e42-138">The **New** option is available only when configuring a data collection set</span></span>  
  
 <span data-ttu-id="66e42-139">**Pagina Mapping account di accesso e utenti**</span><span class="sxs-lookup"><span data-stu-id="66e42-139">**Map Logins and Users Page**</span></span>  
  
 <span data-ttu-id="66e42-140">Utilizzare questa pagina per eseguire il mapping degli account di accesso ai ruoli utente del database per il data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="66e42-140">Use this page to map logins to database user roles for the management data warehouse.</span></span>  
  
 <span data-ttu-id="66e42-141">**Utenti di cui è stato eseguito il mapping all'account di accesso seguente**</span><span class="sxs-lookup"><span data-stu-id="66e42-141">**Users mapped to this login**</span></span>  
 <span data-ttu-id="66e42-142">Visualizza gli account di accesso esistenti nel server che ospiterà il data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="66e42-142">Displays the existing logins on the server that will host the management data warehouse.</span></span> <span data-ttu-id="66e42-143">Ciascuna riga contiene una casella di controllo **Mapping** modificabile, un nome di **Account di accesso** e un **Tipo** di account di accesso.</span><span class="sxs-lookup"><span data-stu-id="66e42-143">Each row contains an editable **Map** check box, a **Login** name, and a **Type** of login.</span></span>  
  
 <span data-ttu-id="66e42-144">Specificare un account di accesso selezionando la casella di controllo **Mapping** .</span><span class="sxs-lookup"><span data-stu-id="66e42-144">Specify a login by selecting the **Map** checkbox for the login.</span></span>  
  
 <span data-ttu-id="66e42-145">**Appartenenza a ruoli del database per:** *\<data warehouse name>*</span><span class="sxs-lookup"><span data-stu-id="66e42-145">**Database role membership for:**  *\<data warehouse name>*</span></span>  
 <span data-ttu-id="66e42-146">Selezionare il ruolo del data warehouse di gestione cui viene eseguito il mapping dell'account di accesso facendo clic nella casella di controllo di una o più delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="66e42-146">Select the management data warehouse role that the login is mapped to by clicking the checkbox by one or more of the following options:</span></span>  
  
-   <span data-ttu-id="66e42-147">**mdw_admin**</span><span class="sxs-lookup"><span data-stu-id="66e42-147">**mdw_admin**</span></span>  
  
-   <span data-ttu-id="66e42-148">**mdw_reader**</span><span class="sxs-lookup"><span data-stu-id="66e42-148">**mdw_reader**</span></span>  
  
-   <span data-ttu-id="66e42-149">**mdw_writer**</span><span class="sxs-lookup"><span data-stu-id="66e42-149">**mdw_writer**</span></span>  
  
 <span data-ttu-id="66e42-150">**Nuovo account di accesso**</span><span class="sxs-lookup"><span data-stu-id="66e42-150">**New Login**</span></span>  
 <span data-ttu-id="66e42-151">Aprire la finestra di dialogo **Account di accesso - Nuovo** e creare un nuovo account di accesso per il data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="66e42-151">Open the **Login - New** dialog box and create a new login for the management data warehouse.</span></span>  
  
 <span data-ttu-id="66e42-152">**Pagina Completamento procedura guidata**</span><span class="sxs-lookup"><span data-stu-id="66e42-152">**Complete the Wizard Page**</span></span>  
  
 <span data-ttu-id="66e42-153">Utilizzare questa pagina per verificare e completare la configurazione della raccolta di dati.</span><span class="sxs-lookup"><span data-stu-id="66e42-153">Use this page to verify and complete data collection configuration.</span></span> <span data-ttu-id="66e42-154">L'albero nella finestra di visualizzazione mostra le configurazioni applicate e le azioni eseguite dopo la selezione di **Fine**.</span><span class="sxs-lookup"><span data-stu-id="66e42-154">The tree displayed in the viewing window shows what configurations will applied as well as what actions will take place when you click **Finish**.</span></span>  
  
 <span data-ttu-id="66e42-155">**Pagina Stato Configurazione guidata raccolta dati**</span><span class="sxs-lookup"><span data-stu-id="66e42-155">**Configure Data Collection Wizard Progress Page**</span></span>  
  
 <span data-ttu-id="66e42-156">Utilizzare questa pagina per visualizzare i risultati di ciascun passaggio di configurazione.</span><span class="sxs-lookup"><span data-stu-id="66e42-156">Use this page to view the results of each configuration step.</span></span>  
  
 <span data-ttu-id="66e42-157">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="66e42-157">**Details**</span></span>  
 <span data-ttu-id="66e42-158">Consente di visualizzare ogni passaggio di configurazione in una riga nella griglia **Dettagli** .</span><span class="sxs-lookup"><span data-stu-id="66e42-158">Displays each configuration step as a row in the **Details** grid.</span></span> <span data-ttu-id="66e42-159">Ogni riga contiene una colonna **Azione** con la descrizione del passaggio e una colonna **Stato** con l'indicazione dell'esito positivo o negativo dello stesso.</span><span class="sxs-lookup"><span data-stu-id="66e42-159">Each row contains an **Action** column that describes the step, and a **Status** column that indicates the success or failure of the step.</span></span> <span data-ttu-id="66e42-160">In presenza di errori, nella colonna **Messaggio** è visualizzato un messaggio.</span><span class="sxs-lookup"><span data-stu-id="66e42-160">If there is an error, a message appears in the **Message** column.</span></span>  
  
 <span data-ttu-id="66e42-161">**Stop**</span><span class="sxs-lookup"><span data-stu-id="66e42-161">**Stop**</span></span>  
 <span data-ttu-id="66e42-162">Consente di arrestare l'elaborazione della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="66e42-162">Stop wizard processing.</span></span>  
  
 <span data-ttu-id="66e42-163">**Report**</span><span class="sxs-lookup"><span data-stu-id="66e42-163">**Report**</span></span>  
 <span data-ttu-id="66e42-164">Consente di visualizzare un report della configurazione di raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="66e42-164">View a report of the data collection configuration.</span></span> <span data-ttu-id="66e42-165">Sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="66e42-165">The following report options are provided:</span></span>  
  
-   <span data-ttu-id="66e42-166">Visualizza report</span><span class="sxs-lookup"><span data-stu-id="66e42-166">View Report</span></span>  
  
-   <span data-ttu-id="66e42-167">Salva report su file</span><span class="sxs-lookup"><span data-stu-id="66e42-167">Save Report to File</span></span>  
  
-   <span data-ttu-id="66e42-168">Copia report negli Appunti</span><span class="sxs-lookup"><span data-stu-id="66e42-168">Copy Report to Clipboard</span></span>  
  
-   <span data-ttu-id="66e42-169">Invia report per posta elettronica</span><span class="sxs-lookup"><span data-stu-id="66e42-169">Send Report as E-mail</span></span>  
  
 <span data-ttu-id="66e42-170">**Close**</span><span class="sxs-lookup"><span data-stu-id="66e42-170">**Close**</span></span>  
 <span data-ttu-id="66e42-171">Consente di chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="66e42-171">Close the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66e42-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66e42-172">See Also</span></span>  
 <span data-ttu-id="66e42-173">[sp_syscollector_enable_collector &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syscollector-enable-collector-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="66e42-173">[sp_syscollector_enable_collector &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syscollector-enable-collector-transact-sql) </span></span>  
 <span data-ttu-id="66e42-174">[sp_syscollector_disable_collector &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syscollector-disable-collector-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="66e42-174">[sp_syscollector_disable_collector &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syscollector-disable-collector-transact-sql) </span></span>  
 <span data-ttu-id="66e42-175">[Raccolta dati](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="66e42-175">[Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="66e42-176">Gestire raccolta dati</span><span class="sxs-lookup"><span data-stu-id="66e42-176">Manage Data Collection</span></span>](manage-data-collection.md)  
  
  
