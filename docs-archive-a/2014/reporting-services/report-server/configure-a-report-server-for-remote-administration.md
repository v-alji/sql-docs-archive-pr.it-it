---
title: Configurare un server di report per l'amministrazione remota | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services Configuration tool
- WMI provider [Reporting Services], remote configuration
- configuration management [WMI]
- report servers [Reporting Services], configuring
- remote server administration [Reporting Services]
ms.assetid: 8c7f145f-3ac2-4203-8cd6-2a4694395d09
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2c34db5299fc1b82a7896a41519e55466c3b3b79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630309"
---
# <a name="configure-a-report-server-for-remote-administration"></a><span data-ttu-id="4eeec-102">Configurare un server di report per l'amministrazione remota</span><span class="sxs-lookup"><span data-stu-id="4eeec-102">Configure a Report Server for Remote Administration</span></span>
  <span data-ttu-id="4eeec-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]è possibile configurare istanze del server di report in modalità locale o remota.</span><span class="sxs-lookup"><span data-stu-id="4eeec-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can configure report server instances locally or remotely.</span></span> <span data-ttu-id="4eeec-104">Per configurare un'istanza remota del server di report, è possibile usare lo strumento di configurazione di Reporting Services oppure scrivere codice personalizzato che usi il provider WMI (Windows Management Instrumentation) per [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4eeec-104">To configure a remote report server instance, you can use the Reporting Services Configuration tool or write custom code that uses the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Windows Management Instrumentation (WMI) provider.</span></span> <span data-ttu-id="4eeec-105">Lo strumento Gestione configurazione Reporting Services offre un'interfaccia grafica al provider WMI, per consentire di configurare un server di report senza dover scrivere codice.</span><span class="sxs-lookup"><span data-stu-id="4eeec-105">The Reporting Services Configuration tool provides a graphical interface to the WMI provider so that you can configure a report server without having to write code.</span></span> <span data-ttu-id="4eeec-106">Quando si avvia lo strumento, è possibile specificare un server remoto a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="4eeec-106">When you start the tool, you can specify a remote server to connect to.</span></span>  
  
 <span data-ttu-id="4eeec-107">Prima che sia possibile utilizzare lo strumento per configurare un server di report remoto, è necessario seguire le indicazioni contenute in questo argomento per abilitare le porte in Windows Firewall, consentire le connessioni remote e abilitare le richieste WMI remote.</span><span class="sxs-lookup"><span data-stu-id="4eeec-107">Before you can use the tool to configure a remote report server, you must follow the instructions in this topic to enable ports in Windows Firewall, enable remote connections, and enable remote WMI requests.</span></span>  
  
 <span data-ttu-id="4eeec-108">Una configurazione appropriata consente di evitare l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="4eeec-108">Proper configuration helps you avoid the following error:</span></span>  
  
 `The machine could not be found.`  
  
 `"The RPC server is unavailable. (Exception from HRESULT: 0x800706BA)".`  
  
## <a name="prerequisites"></a><span data-ttu-id="4eeec-109">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="4eeec-109">Prerequisites</span></span>  
 <span data-ttu-id="4eeec-110">A tale scopo, è necessario accedere al sistema localmente ed essere membri del gruppo Administrators locale.</span><span class="sxs-lookup"><span data-stu-id="4eeec-110">To modify firewall settings, you must be logged on locally and you must be a member of the local Administrators group.</span></span> <span data-ttu-id="4eeec-111">Non è possibile modificare le impostazioni di Windows Firewall di un computer remoto tramite una connessione remota.</span><span class="sxs-lookup"><span data-stu-id="4eeec-111">You cannot modify the Windows firewall settings of a remote computer over a remote connection.</span></span>  
  
 <span data-ttu-id="4eeec-112">Se si desidera abilitare l'amministrazione remota per un utente non amministratore, è necessario concedere all'account le autorizzazioni per l'attivazione remota DCOM (Distributed Component Object Model).</span><span class="sxs-lookup"><span data-stu-id="4eeec-112">If you want to enable remote administration for a non-administrator user, you must grant the account Distributed Component Object Model (DCOM) Remote Activation permissions.</span></span> <span data-ttu-id="4eeec-113">In questo argomento vengono fornite le istruzioni per la configurazione del server per l'accesso da parte di utenti non amministratori.</span><span class="sxs-lookup"><span data-stu-id="4eeec-113">Instructions for configuring the server for non-administrator access are provided in this topic.</span></span>  
  
 <span data-ttu-id="4eeec-114">In alcune organizzazioni sono presenti criteri di gruppo che impediscono l'amministrazione remota del server per alcuni sistemi operativi o utenti.</span><span class="sxs-lookup"><span data-stu-id="4eeec-114">Some organizations have group policies that prevent remote server administration for certain operating systems or users.</span></span> <span data-ttu-id="4eeec-115">Prima di iniziare a modificare le impostazioni del firewall, rivolgersi all'amministratore di rete per verificare se vi sono limitazioni all'amministrazione remota.</span><span class="sxs-lookup"><span data-stu-id="4eeec-115">Before you begin modifying firewall settings, check with your network administrator to verify whether there are restrictions on remote administration.</span></span>  
  
 <span data-ttu-id="4eeec-116">Per ulteriori informazioni, vedere [Connecting Through Windows Firewall](https://go.microsoft.com/fwlink/?LinkId=63615) nella documentazione di Platform SDK nel sito Web MSDN.</span><span class="sxs-lookup"><span data-stu-id="4eeec-116">For more information, see [Connecting Through Windows Firewall](https://go.microsoft.com/fwlink/?LinkId=63615) in the Platform SDK documentation on MSDN.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="4eeec-117">Attività</span><span class="sxs-lookup"><span data-stu-id="4eeec-117">Tasks</span></span>  
 <span data-ttu-id="4eeec-118">Tra le attività che consentono di configurare un server di report remoto sono incluse le seguenti:</span><span class="sxs-lookup"><span data-stu-id="4eeec-118">Tasks that enable remote report server configuration include the following:</span></span>  
  
-   <span data-ttu-id="4eeec-119">Abilitare le porte in Windows Firewall per consentire le richieste sulle porte utilizzate dal server di report e dall'istanza del Motore di database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4eeec-119">Enable ports in Windows Firewall to allow requests on ports used by the report server and by the SQL Server Database Engine instance.</span></span>  
  
-   <span data-ttu-id="4eeec-120">Consentire le connessioni remote all'istanza del Motore di database che ospita il database del server di report.</span><span class="sxs-lookup"><span data-stu-id="4eeec-120">Enable remote connections to the instance of the Database Engine instance that hosts the report server database.</span></span> <span data-ttu-id="4eeec-121">Una connessione remota è necessaria per la configurazione della connessione al database del server di report e per la gestione delle chiavi di crittografia.</span><span class="sxs-lookup"><span data-stu-id="4eeec-121">A remote connection is necessary for configuring the report server database connection and managing the encryption keys.</span></span>  
  
-   <span data-ttu-id="4eeec-122">Consentire il passaggio delle richieste WMI remote attraverso [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Firewall.</span><span class="sxs-lookup"><span data-stu-id="4eeec-122">Enable remote WMI requests to pass through the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows firewall.</span></span>  
  
-   <span data-ttu-id="4eeec-123">Se si configura un server di report remoto per l'amministrazione da parte di un utente non amministratore, è necessario impostare autorizzazioni DCOM per consentire l'accesso WMI remoto a un account utente di Windows standard.</span><span class="sxs-lookup"><span data-stu-id="4eeec-123">If you are configuring a remote report server for administration by a non-administrative user, you must set DCOM permissions to enable remote WMI access to a standard Windows user account.</span></span> <span data-ttu-id="4eeec-124">Poiché WMI utilizza DCOM per il trasporto delle chiamate remote, è necessario impostare le autorizzazioni DCOM per consentire agli utenti che non hanno eseguito l'accesso come amministratore locale di configurare il server.</span><span class="sxs-lookup"><span data-stu-id="4eeec-124">Because WMI uses DCOM as transport for remote calls, you must set the DCOM permissions so that users who are not logged on as the local administrator can configure the server.</span></span>  
  
-   <span data-ttu-id="4eeec-125">Se si configura un server di report remoto per l'amministrazione da parte di un utente non amministratore, è inoltre necessario impostare autorizzazioni WMI nello spazio dei nomi WMI del server di report.</span><span class="sxs-lookup"><span data-stu-id="4eeec-125">If you are configuring a remote report server for administration by a non-administrative user, you must also set WMI permissions on the report server WMI namespace.</span></span> <span data-ttu-id="4eeec-126">Per impostazione predefinita, tutti i membri del gruppo Administrators locale dispongono di accesso allo spazio dei nomi WMI del server di report.</span><span class="sxs-lookup"><span data-stu-id="4eeec-126">By default, all members of the local Administrator group have access to the report server WMI namespace.</span></span> <span data-ttu-id="4eeec-127">Per concedere l'accesso a utenti non amministratori, è necessario impostare le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="4eeec-127">If you want to grant access to non-administrators, you must set permissions.</span></span>  
  
 <span data-ttu-id="4eeec-128">Le indicazioni per l'esecuzione di queste attività sono disponibili in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="4eeec-128">Instructions on how to perform these tasks are provided in this topic.</span></span>  
  
### <a name="to-open-ports-in-windows-firewall"></a><span data-ttu-id="4eeec-129">Per aprire porte in Windows Firewall</span><span class="sxs-lookup"><span data-stu-id="4eeec-129">To open ports in Windows Firewall</span></span>  
  
1.  <span data-ttu-id="4eeec-130">[Configurare un Windows Firewall per l'accesso motore di database](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md).</span><span class="sxs-lookup"><span data-stu-id="4eeec-130">[Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md).</span></span>  
  
2.  <span data-ttu-id="4eeec-131">[Configurare un firewall per l'accesso al server di report](configure-a-firewall-for-report-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="4eeec-131">[Configure a Firewall for Report Server Access](configure-a-firewall-for-report-server-access.md).</span></span>  
  
### <a name="to-configure-remote-connections-to-the-report-server-database"></a><span data-ttu-id="4eeec-132">Per configurare connessioni remote al database del server di report</span><span class="sxs-lookup"><span data-stu-id="4eeec-132">To configure remote connections to the report server database</span></span>  
  
1.  <span data-ttu-id="4eeec-133">Fare clic sul pulsante **Start**, scegliere **Programmi**, [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], **Strumenti di configurazione**, quindi **Gestione configurazione SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="4eeec-133">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="4eeec-134">Nel riquadro a sinistra espandere **Configurazione di rete SQL Server**, quindi fare clic su **Protocolli** per l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4eeec-134">In the left pane, expand **SQL Server Network Configuration**, and then click **Protocols** for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="4eeec-135">Nel riquadro dei dettagli abilitare i protocolli TCP/IP e Named Pipes, quindi riavviare il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4eeec-135">In the details pane, enable the TCP/IP and Named Pipes protocols, and then restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
### <a name="to-enable-remote-administration-in-windows-firewall"></a><span data-ttu-id="4eeec-136">Per abilitare l'amministrazione remota in Windows Firewall</span><span class="sxs-lookup"><span data-stu-id="4eeec-136">To enable remote administration in Windows Firewall</span></span>  
  
1.  <span data-ttu-id="4eeec-137">Accedere come amministratore locale al computer per il quale si desidera abilitare l'amministrazione remota.</span><span class="sxs-lookup"><span data-stu-id="4eeec-137">Log on as a local administrator to the computer for which you want to enable remote administration.</span></span>  
  
2.  <span data-ttu-id="4eeec-138">Se il server di report è in esecuzione in Windows Vista, fare clic con il pulsante destro del mouse su **Prompt dei comandi** , quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="4eeec-138">If the report server is running on Windows Vista, right-click **Command Prompt** and select **Run as administrator**.</span></span> <span data-ttu-id="4eeec-139">Per gli altri sistemi operativi, aprire una finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="4eeec-139">For other operating systems, open a command prompt window.</span></span>  
  
3.  <span data-ttu-id="4eeec-140">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4eeec-140">Run the following command:</span></span>  
  
    ```  
    netsh.exe firewall set service type=REMOTEADMIN mode=ENABLE scope=ALL  
    ```  
  
     <span data-ttu-id="4eeec-141">È possibile specificare opzioni diverse per Scope.</span><span class="sxs-lookup"><span data-stu-id="4eeec-141">You can specify different options for Scope.</span></span> <span data-ttu-id="4eeec-142">Per ulteriori informazioni, vedere la documentazione di Windows Firewall.</span><span class="sxs-lookup"><span data-stu-id="4eeec-142">For more information, see the Windows Firewall product documentation.</span></span>  
  
4.  <span data-ttu-id="4eeec-143">Verificare che l'amministrazione remota sia abilitata.</span><span class="sxs-lookup"><span data-stu-id="4eeec-143">Verify that remote administration is enabled.</span></span> <span data-ttu-id="4eeec-144">Per visualizzare lo stato, è possibile eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4eeec-144">You can run the following command to show the status:</span></span>  
  
    ```  
    netsh.exe firewall show state  
    ```  
  
5.  <span data-ttu-id="4eeec-145">Riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="4eeec-145">Reboot the computer.</span></span>  
  
### <a name="to-set-dcom-permissions-to-enable-remote-wmi-access-for-non-administrators"></a><span data-ttu-id="4eeec-146">Per impostare autorizzazioni DCOM per consentire l'accesso WMI remoto a utenti non amministratori</span><span class="sxs-lookup"><span data-stu-id="4eeec-146">To set DCOM permissions to enable remote WMI access for non-administrators</span></span>  
  
1.  <span data-ttu-id="4eeec-147">Nel menu Start, scegliere **Strumenti di amministrazione**e quindi **Servizi componenti**.</span><span class="sxs-lookup"><span data-stu-id="4eeec-147">On the Start menu, point to **Administrative Tools**, click **Component Services**.</span></span>  
  
     <span data-ttu-id="4eeec-148">Per Windows Vista, nel menu Start fare clic su **tutti i programmi**, **Esegui**, quindi immettere `mmc comexp.msc` .</span><span class="sxs-lookup"><span data-stu-id="4eeec-148">For Windows Vista, on the Start menu, click **All Programs**, click **Run**, and then enter `mmc comexp.msc`.</span></span>  
  
2.  <span data-ttu-id="4eeec-149">Aprire la cartella Component Services.</span><span class="sxs-lookup"><span data-stu-id="4eeec-149">Open the Component Services folder.</span></span>  
  
3.  <span data-ttu-id="4eeec-150">Aprire la cartella Computer.</span><span class="sxs-lookup"><span data-stu-id="4eeec-150">Open the Computers folder.</span></span>  
  
4.  <span data-ttu-id="4eeec-151">Selezionare Risorse del computer.</span><span class="sxs-lookup"><span data-stu-id="4eeec-151">Select My Computer.</span></span>  
  
5.  <span data-ttu-id="4eeec-152">Scegliere **Proprietà** dal menu **Azione**.</span><span class="sxs-lookup"><span data-stu-id="4eeec-152">On the **Action** menu, and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="4eeec-153">Fare clic su **Sicurezza COM**.</span><span class="sxs-lookup"><span data-stu-id="4eeec-153">Click **COM Security**.</span></span>  
  
7.  <span data-ttu-id="4eeec-154">In **Autorizzazioni di esecuzione e attivazione**fare clic su **Modifica limiti**.</span><span class="sxs-lookup"><span data-stu-id="4eeec-154">In **Launch and Activation Permissions**, click **Edit Limits**.</span></span>  
  
8.  <span data-ttu-id="4eeec-155">Se il proprio nome non è visualizzato in **Autorizzazioni di avvio**fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="4eeec-155">If you do not see your name in **Launch Permission**, click **Add**.</span></span>  
  
9. <span data-ttu-id="4eeec-156">Digitare il nome del proprio account utente e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4eeec-156">Type the name of your user account, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="4eeec-157">In \*\*autorizzazioni per \<User or Group> \*\*, nella colonna **Consenti** selezionare **avvio remoto** e **attivazione remota**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4eeec-157">In **Permissions for \<User or Group>**, in the **Allow** column, select **Remote Launch** and **Remote Activation**, and then click **OK**.</span></span>  
  
### <a name="to-set-permissions-on-the-report-server-wmi-namespace-for-non-administrators"></a><span data-ttu-id="4eeec-158">Per impostare autorizzazioni nello spazio dei nomi WMI del server di report per utenti non amministratori</span><span class="sxs-lookup"><span data-stu-id="4eeec-158">To set permissions on the report server WMI namespace for non-administrators</span></span>  
  
1.  <span data-ttu-id="4eeec-159">Nel menu Start, scegliere **Strumenti di amministrazione**e quindi **Gestione computer**.</span><span class="sxs-lookup"><span data-stu-id="4eeec-159">On the Start menu, point to **Administrative Tools**, click **Computer Management**.</span></span>  
  
2.  <span data-ttu-id="4eeec-160">Aprire la cartella Servizi e applicazioni.</span><span class="sxs-lookup"><span data-stu-id="4eeec-160">Open the Services and Applications folder.</span></span>  
  
3.  <span data-ttu-id="4eeec-161">Fare clic con il pulsante destro del mouse su **Controllo WMI**e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="4eeec-161">Right-click **WMI Control**, and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="4eeec-162">Fare clic su **Security**.</span><span class="sxs-lookup"><span data-stu-id="4eeec-162">Click **Security**.</span></span>  
  
5.  <span data-ttu-id="4eeec-163">Aprire la cartella Root.</span><span class="sxs-lookup"><span data-stu-id="4eeec-163">Open the Root folder.</span></span>  
  
6.  <span data-ttu-id="4eeec-164">Aprire la cartella Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4eeec-164">Open the Microsoft folder.</span></span>  
  
7.  <span data-ttu-id="4eeec-165">Aprire la cartella SQLServer.</span><span class="sxs-lookup"><span data-stu-id="4eeec-165">Open the SQLServer folder.</span></span>  
  
8.  <span data-ttu-id="4eeec-166">Aprire la cartella ReportServer.</span><span class="sxs-lookup"><span data-stu-id="4eeec-166">Open the ReportServer folder.</span></span>  
  
9. <span data-ttu-id="4eeec-167">Aprire la cartella dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="4eeec-167">Open instance folder.</span></span> <span data-ttu-id="4eeec-168">Se è stata installata l'istanza predefinita, il nome della cartella è MSSQLSERVER.</span><span class="sxs-lookup"><span data-stu-id="4eeec-168">If you installed the default instance, the folder is MSSQLSERVER.</span></span>  
  
10. <span data-ttu-id="4eeec-169">Aprire la cartella v10.</span><span class="sxs-lookup"><span data-stu-id="4eeec-169">Open the v10 folder.</span></span>  
  
11. <span data-ttu-id="4eeec-170">Selezionare la cartella Admin e quindi fare clic su **Sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="4eeec-170">Select the Admin folder, and then click **Security**.</span></span>  
  
12. <span data-ttu-id="4eeec-171">Fare clic su **Aggiungi**e quindi digitare l'account utente che si desidera utilizzare per gestire il server.</span><span class="sxs-lookup"><span data-stu-id="4eeec-171">Click **Add**, and then type the user account you will use to manage the server.</span></span>  
  
13. <span data-ttu-id="4eeec-172">Nella colonna **Consenti** selezionare **Abilita account**, **Abilita remoto**e **Sicurezza da lettura**, quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="4eeec-172">In the **Allow** column, select **Enable Account**, **Remote Enable**, and **Read Security**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eeec-173">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4eeec-173">See Also</span></span>  
 [<span data-ttu-id="4eeec-174">Gestione configurazione Reporting Services &#40;modalità nativa&#41;</span><span class="sxs-lookup"><span data-stu-id="4eeec-174">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../sql-server/install/reporting-services-configuration-manager-native-mode.md)  
  
  
