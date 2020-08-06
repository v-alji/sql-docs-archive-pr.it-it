---
title: Visualizzare file di log offline | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- Log File Viewer, viewing offline logs
- offline log files
ms.assetid: 9223e474-f224-4907-a4f2-081e11db58f5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2afc1992b54c78f69bfae1fc152b41c20bcd4ea1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635577"
---
# <a name="view-offline-log-files"></a><span data-ttu-id="1638c-102">Visualizzare file di log offline</span><span class="sxs-lookup"><span data-stu-id="1638c-102">View Offline Log Files</span></span>
  <span data-ttu-id="1638c-103">A partire da [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], è possibile visualizzare file di log di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da un'istanza locale o remota di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] quando l'istanza di destinazione è offline o non può essere avviata.</span><span class="sxs-lookup"><span data-stu-id="1638c-103">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], you can view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files from a local or remote instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] when the target instance is offline or cannot start.</span></span>  
  
 <span data-ttu-id="1638c-104">È possibile accedere ai file di log offline tramite lo strumento Server registrati o a livello di codice tramite query WMI e WQL (WMI Query Language).</span><span class="sxs-lookup"><span data-stu-id="1638c-104">You can access the offline log files from Registered Servers, or programmatically through WMI and WQL (WMI Query Language) queries.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1638c-105">È possibile utilizzare questi metodi anche per connettersi a un'istanza a cui, benché online, non è possibile connettersi tramite una connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per qualche motivo.</span><span class="sxs-lookup"><span data-stu-id="1638c-105">You can also use these methods to connect to an instance that is online, but for some reason, you cannot connect through a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="1638c-106">Operazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="1638c-106">Before you Begin</span></span>  
 <span data-ttu-id="1638c-107">Per connettersi ai file di log offline, è necessario che nel computer utilizzato per visualizzare i file di log offline e nel computer in cui si trovano i file di log che si desidera visualizzare sia installata un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1638c-107">To connect to offline log files, an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be installed on the computer that you are using to view the offline log files, and on the computer where the log files that you want to view are located.</span></span> <span data-ttu-id="1638c-108">Se in entrambi i computer è installata un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , è possibile visualizzare file offline per istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]e per istanze che eseguono versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in uno dei computer.</span><span class="sxs-lookup"><span data-stu-id="1638c-108">If an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed on both computers, you can view offline files for instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and for instances that are running earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on either computer.</span></span>  
  
 <span data-ttu-id="1638c-109">Se si usa Server registrati, l'istanza a cui ci si vuole connettere deve essere registrata in **Gruppi di server locali** o **Server di gestione centrale**.</span><span class="sxs-lookup"><span data-stu-id="1638c-109">If you are using Registered Servers, the instance that you want to connect to must be registered under **Local Server Groups** or under **Central Management Servers**.</span></span> <span data-ttu-id="1638c-110">L'istanza può essere registrata in modo autonomo o essere un membro di un gruppo di server. Per ulteriori informazioni su come aggiungere un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a Server registrati, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1638c-110">(The instance can be registered on its own or be a member of a server group.) For more information about how to add an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to Registered Servers, see the following topics:</span></span>  
  
-   [<span data-ttu-id="1638c-111">Creare o modificare un gruppo di server &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1638c-111">Create or Edit a Server Group &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/register-servers/create-or-edit-a-server-group-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="1638c-112">Registrare un server connesso &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1638c-112">Register a Connected Server &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/register-servers/register-a-connected-server-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="1638c-113">Creare un server di gestione centrale e un gruppo di server &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1638c-113">Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/register-servers/create-a-central-management-server-and-server-group.md)  
  
 <span data-ttu-id="1638c-114">Per ulteriori informazioni su come visualizzare file di log offline a livello di codice tramite query WMI e WQL, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1638c-114">For more information about how to view offline log files programmatically through WMI and WQL queries, see the following topics:</span></span>  
  
-   <span data-ttu-id="1638c-115">[Classe SqlErrorLogEvent](../wmi-provider-configuration-classes/sqlerrorlogevent-class.md) Questo argomento mostra come recuperare i valori per gli eventi registrati in un file di log specificato.</span><span class="sxs-lookup"><span data-stu-id="1638c-115">[SqlErrorLogEvent Class](../wmi-provider-configuration-classes/sqlerrorlogevent-class.md) (This topic shows how to retrieve values for logged events in a specified log file.)</span></span>  
  
-   <span data-ttu-id="1638c-116">[SqlErrorLogFile Class](../wmi-provider-configuration-classes/sqlerrorlogfile-class.md) Questo argomento mostra come recuperare le informazioni su tutti i file di log di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in un'istanza specificata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1638c-116">[SqlErrorLogFile Class](../wmi-provider-configuration-classes/sqlerrorlogfile-class.md) (This topic shows how to retrieve information about all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files on a specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span></span>  
  
##  <a name="permissions"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1638c-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="1638c-117">Permissions</span></span>  
 <span data-ttu-id="1638c-118">Per connettersi a un file di log offline, è necessario disporre delle autorizzazioni seguenti nei computer locale e remoto:</span><span class="sxs-lookup"><span data-stu-id="1638c-118">To connect to an offline log file, you must have the following permissions on both the local and remote computers:</span></span>  
  
-   <span data-ttu-id="1638c-119">Accesso in lettura allo spazio dei nomi WMI **Root\Microsoft\SqlServer\ComputerManagement12** .</span><span class="sxs-lookup"><span data-stu-id="1638c-119">Read access to the **Root\Microsoft\SqlServer\ComputerManagement12** WMI namespace.</span></span> <span data-ttu-id="1638c-120">Per impostazione predefinita, chiunque dispone di accesso in lettura tramite l'autorizzazione Abilita account.</span><span class="sxs-lookup"><span data-stu-id="1638c-120">By default, everyone has read access through the Enable Account permission.</span></span> <span data-ttu-id="1638c-121">Per ulteriori informazioni, vedere la procedura "Per verificare le autorizzazioni WMI" più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="1638c-121">For more information, see the "To verify WMI permissions" procedure later in this section.</span></span>  
  
-   <span data-ttu-id="1638c-122">Autorizzazione di lettura per la cartella che contiene i file di log degli errori.</span><span class="sxs-lookup"><span data-stu-id="1638c-122">Read permission to the folder that contains the error log files.</span></span> <span data-ttu-id="1638c-123">Per impostazione predefinita, i file di log degli errori si trovano nel percorso seguente, dove \<*Drive>\* rappresenta l'unità in cui è stato installato [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e \<*InstanceName*> è il nome dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="1638c-123">By default the error log files are located in the following path (where \<*Drive>\* represents the drive where you installed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and \<*InstanceName*> is the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]):</span></span>  
  
     <span data-ttu-id="1638c-124">**\<Drive>: \Programmi\Microsoft SQL Server\MSSQL12. \<InstanceName> \MSSQL\Log**</span><span class="sxs-lookup"><span data-stu-id="1638c-124">**\<Drive>:\Program Files\Microsoft SQL Server\MSSQL12.\<InstanceName>\MSSQL\Log**</span></span>  
  
 <span data-ttu-id="1638c-125">Per verificare le impostazioni di sicurezza dello spazio dei nomi WMI, è possibile utilizzare lo snap-in Controllo WMI.</span><span class="sxs-lookup"><span data-stu-id="1638c-125">To verify WMI namespace security settings, you can use the WMI Control snap-in.</span></span>  
  
#### <a name="to-verify-wmi-permissions"></a><span data-ttu-id="1638c-126">Per verificare le autorizzazioni WMI</span><span class="sxs-lookup"><span data-stu-id="1638c-126">To verify WMI permissions</span></span>  
  
1.  <span data-ttu-id="1638c-127">Aprire lo snap-in Controllo WMI.</span><span class="sxs-lookup"><span data-stu-id="1638c-127">Open the WMI Control snap-in.</span></span> <span data-ttu-id="1638c-128">A tale scopo, effettuare una delle operazioni seguenti a seconda del sistema operativo in uso:</span><span class="sxs-lookup"><span data-stu-id="1638c-128">To do this, do either of the following, depending on the operating system:</span></span>  
  
    -   <span data-ttu-id="1638c-129">Fare clic su **Start**, digitare `wmimgmt.msc` nella casella **Inizia ricerca** , quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="1638c-129">Click **Start**, type `wmimgmt.msc` in the **Start Search** box, and then press ENTER.</span></span>  
  
    -   <span data-ttu-id="1638c-130">Fare clic sul pulsante **Start**, scegliere **Esegui**, digitare `wmimgmt.msc` e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="1638c-130">Click **Start**, click **Run**, type `wmimgmt.msc`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="1638c-131">Per impostazione predefinita, lo snap-in Controllo WMI gestisce il computer locale.</span><span class="sxs-lookup"><span data-stu-id="1638c-131">By default, the WMI Control snap-in manages the local computer.</span></span>  
  
     <span data-ttu-id="1638c-132">Se si desidera connettersi a un computer remoto, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1638c-132">If you want to connect to a remote computer, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="1638c-133">Fare clic con il pulsante destro del mouse su **Controllo WMI (computer locale)** , quindi scegliere **Connetti a un altro computer**.</span><span class="sxs-lookup"><span data-stu-id="1638c-133">Right-click **WMI Control (Local)**, and then click **Connect to another computer**.</span></span>  
  
    2.  <span data-ttu-id="1638c-134">Nella finestra di dialogo **Cambio computer gestito** fare clic su **Altro computer**.</span><span class="sxs-lookup"><span data-stu-id="1638c-134">In the **Change managed computer** dialog box, click **Another computer**.</span></span>  
  
    3.  <span data-ttu-id="1638c-135">Immettere il nome del computer remoto, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1638c-135">Enter the remote computer name, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="1638c-136">Fare clic con il pulsante destro del mouse su **controllo WMI (locale)** o **controllo WMI (***NomeComputerRemoto***)**, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="1638c-136">Right-click **WMI Control (Local)** or **WMI Control (***RemoteComputerName***)**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="1638c-137">Nella finestra di dialogo delle proprietà di **Controllo WMI** fare clic sulla scheda **Sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="1638c-137">In the **WMI Control Properties** dialog box, click the **Security** tab.</span></span>  
  
5.  <span data-ttu-id="1638c-138">Nell'albero dello spazio dei nomi individuare e selezionare lo spazio dei nomi seguente:</span><span class="sxs-lookup"><span data-stu-id="1638c-138">In the namespace tree, locate and then click the following namespace:</span></span>  
  
     <span data-ttu-id="1638c-139">**Root\Microsoft\SqlServer\ComputerManagement10**</span><span class="sxs-lookup"><span data-stu-id="1638c-139">**Root\Microsoft\SqlServer\ComputerManagement10**</span></span>  
  
6.  <span data-ttu-id="1638c-140">Fare clic su **Security**.</span><span class="sxs-lookup"><span data-stu-id="1638c-140">Click **Security**.</span></span>  
  
7.  <span data-ttu-id="1638c-141">Verificare che l'account usato abbia l'autorizzazione **Abilita account** .</span><span class="sxs-lookup"><span data-stu-id="1638c-141">Make sure that the account that will be used has the **Enable Account** permission.</span></span> <span data-ttu-id="1638c-142">Questa autorizzazione consente accesso in lettura a oggetti WMI.</span><span class="sxs-lookup"><span data-stu-id="1638c-142">This permission allows Read access to WMI objects.</span></span>  
  
### <a name="view-log-files"></a><span data-ttu-id="1638c-143">Visualizzare file di log</span><span class="sxs-lookup"><span data-stu-id="1638c-143">View Log Files</span></span>  
 <span data-ttu-id="1638c-144">Nella procedura seguente viene illustrato come visualizzare file di log offline tramite Server registrati.</span><span class="sxs-lookup"><span data-stu-id="1638c-144">The following procedure shows how to view offline log files through Registered Servers.</span></span> <span data-ttu-id="1638c-145">Nella procedura si suppone quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1638c-145">The procedure assumes the following:</span></span>  
  
 <span data-ttu-id="1638c-146">L'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a cui si desidera connettersi è già registrata in Server registrati.</span><span class="sxs-lookup"><span data-stu-id="1638c-146">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to connect to is already registered in Registered Servers.</span></span>  
  
##### <a name="to-view-log-files-for-instances-that-are-offline"></a><span data-ttu-id="1638c-147">Per visualizzare file di log per istanze offline</span><span class="sxs-lookup"><span data-stu-id="1638c-147">To view log files for instances that are offline</span></span>  
  
1.  <span data-ttu-id="1638c-148">Se si desidera visualizzare file di log offline in un'istanza locale, assicurarsi di avviare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] con autorizzazioni elevate.</span><span class="sxs-lookup"><span data-stu-id="1638c-148">If you want to view offline log files on a local instance, make sure that you start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] with elevated permissions.</span></span> <span data-ttu-id="1638c-149">A questo scopo, quando si avvia [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], fare clic con il pulsante destro del mouse su **SQL Server Management Studio**, quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="1638c-149">To do this, when you start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], right-click **SQL Server Management Studio**, and then click **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="1638c-150">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]scegliere **Server registrati** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="1638c-150">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Registered Servers**.</span></span>  
  
3.  <span data-ttu-id="1638c-151">Nell'albero della console individuare l'istanza in cui si desidera visualizzare i file offline.</span><span class="sxs-lookup"><span data-stu-id="1638c-151">In the console tree, locate the instance on which you want to view the offline files.</span></span>  
  
4.  <span data-ttu-id="1638c-152">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1638c-152">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="1638c-153">Se l'istanza è in **Gruppi di server locali**, espandere **Gruppi di server locali**, espandere il gruppo di server se l'istanza è un membro di un gruppo, fare clic con il pulsante destro del mouse sull'istanza e quindi scegliere **Visualizza log di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="1638c-153">If the instance is under **Local Server Groups**, expand **Local Server Groups**, expand the server group (if the instance is a member of a group), right-click the instance, and then click **View SQL Server Log**.</span></span>  
  
    -   <span data-ttu-id="1638c-154">Se l'istanza corrisponde allo stesso server di gestione centrale, espandere **Server di gestione centrale**, fare clic con il pulsante destro del mouse sull'istanza, scegliere **Azioni server di gestione centrale**, quindi fare clic su **Visualizza log di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="1638c-154">If the instance is the Central Management Server itself, expand **Central Management Servers**, right-click the instance, point to **Central Management Server Actions**, and then click **View SQL Server Log**.</span></span>  
  
    -   <span data-ttu-id="1638c-155">Se l'istanza è in **Server di gestione centrale**, espandere **Server di gestione centrale**, espandere il server di gestione centrale, fare clic con il pulsante destro del mouse sull'istanza o espandere un gruppo di server e fare clic con il pulsante destro del mouse sull'istanza, quindi scegliere **Visualizza log di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="1638c-155">If the instance is under **Central Management Servers**, expand **Central Management Servers**, expand the Central Management Server, right-click the instance (or expand a server group and right-click the instance), and then click **View SQL Server Log**.</span></span>  
  
5.  <span data-ttu-id="1638c-156">Se ci si connette a un'istanza locale, la connessione viene eseguita utilizzando le credenziali utente correnti.</span><span class="sxs-lookup"><span data-stu-id="1638c-156">If you are connecting to a local instance, the connection is made using the current user credentials.</span></span>  
  
     <span data-ttu-id="1638c-157">Se ci si connette a un'istanza remota, nella finestra di dialogo **Visualizzatore file di log - Connetti come** eseguire una di queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="1638c-157">If you are connecting to a remote instance, in the **Log File Viewer - Connect As** dialog box, do either of the following:</span></span>  
  
    -   <span data-ttu-id="1638c-158">Per connettersi come utente corrente, verificare che la casella di controllo **Connetti come altro utente** sia deselezionata, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1638c-158">To connect as the current user, make sure that the **Connect as another user** check box is cleared, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="1638c-159">Per connettersi come utente diverso, selezionare la casella di controllo **Connetti come altro utente** , quindi fare clic su **Imposta utente**.</span><span class="sxs-lookup"><span data-stu-id="1638c-159">To connect as another user, select the **Connect as another user** check box, and then click **Set User**.</span></span> <span data-ttu-id="1638c-160">Quando viene richiesto, immettere le credenziali utente con il nome utente in formato *nome_dominio*\\*nome_utente*, fare clic su **OK**e quindi di nuovo su **OK** per connettersi.</span><span class="sxs-lookup"><span data-stu-id="1638c-160">When you are prompted, enter the user credentials (with the user name in the format *domain_name*\\*user_name*), click **OK**, and then click **OK** again to connect.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1638c-161">Se il caricamento dei file di log richiede troppo tempo, è possibile fare clic su **Arresta** nella barra degli strumenti Visualizzatore file di log.</span><span class="sxs-lookup"><span data-stu-id="1638c-161">If the log files take too long to load, you can click **Stop** on the Log File Viewer toolbar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1638c-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1638c-162">See Also</span></span>  
 [<span data-ttu-id="1638c-163">Visualizzatore file di log</span><span class="sxs-lookup"><span data-stu-id="1638c-163">Log File Viewer</span></span>](log-file-viewer.md)  
  
  
