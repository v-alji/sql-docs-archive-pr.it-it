---
title: Abilitare o disabilitare un protocollo di rete del server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- network protocols [SQL Server], disabling
- remote connections [SQL Server], enabling using Configuration Manager
- protocols [SQL Server], enabling using Configuration Manager
- protocols [SQL Server], disabling using Configuration Manager
- disabling network protocols, Configuration Manager
- network protocols [SQL Server], enabling
- enabling network protocols, Configuration Manager
- surface area configuration [SQL Server], connection protocols
- connections [SQL Server], enabling remote using Configuration Manager
ms.assetid: ec5ccb69-61c9-4576-8843-014b976fd46e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 737edae84ff284ed726ade69cb48e574b830611e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715696"
---
# <a name="enable-or-disable-a-server-network-protocol"></a><span data-ttu-id="3099d-102">Abilitare o disabilitare un protocollo di rete del server</span><span class="sxs-lookup"><span data-stu-id="3099d-102">Enable or Disable a Server Network Protocol</span></span>
  <span data-ttu-id="3099d-103">Tutti i protocolli di rete vengono installati dal programma di installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ma è possibile abilitarli o meno.</span><span class="sxs-lookup"><span data-stu-id="3099d-103">All network protocols are installed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup, but may or may not be enabled.</span></span> <span data-ttu-id="3099d-104">In questo argomento viene descritto come abilitare o disabilitare un protocollo di rete del server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3099d-104">This topic describes how to enable or disable a server network protocol in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager or PowerShell.</span></span> <span data-ttu-id="3099d-105">Per rendere effettive le modifiche, è necessario arrestare e riavviare il [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3099d-105">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] must be stopped and restarted for the change to take effect.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3099d-106">Durante l'installazione di [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] viene aggiunto un account di accesso per il gruppo BUILTIN\Users.</span><span class="sxs-lookup"><span data-stu-id="3099d-106">During setup of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] a login is added for the BUILTIN\Users group.</span></span> <span data-ttu-id="3099d-107">In questo modo, tutti gli utenti autenticati del computer possono accedere all'istanza di [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] come un membro del ruolo pubblico.</span><span class="sxs-lookup"><span data-stu-id="3099d-107">This allows all authenticated users of the computer to access the instance of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] as a member of the public role.</span></span> <span data-ttu-id="3099d-108">L'account di accesso BUILTIN\Users può essere rimosso in sicurezza per limitare l'accesso del [!INCLUDE[ssDE](../../includes/ssde-md.md)] agli utenti di computer che dispongono di account di accesso singoli o sono membri di altri gruppi di Windows con account di accesso.</span><span class="sxs-lookup"><span data-stu-id="3099d-108">The BUILTIN\Users login can be safely removed to restrict [!INCLUDE[ssDE](../../includes/ssde-md.md)] access to computer users who have individual logins or are members of other Windows groups with logins.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="3099d-109">I provider di dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e [!INCLUDE[msCoName](../../includes/msconame-md.md)] per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supportano TLS 1.0 e SSL 3.0.</span><span class="sxs-lookup"><span data-stu-id="3099d-109">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[msCoName](../../includes/msconame-md.md)] data providers for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] support TLS 1.0 and SSL 3.0.</span></span> <span data-ttu-id="3099d-110">Se si applica un protocollo diverso, ad esempio TLS 1.1 o TLS 1.2, apportando modifiche nel livello SChannel del sistema operativo, le connessioni a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] potrebbero non riuscire.</span><span class="sxs-lookup"><span data-stu-id="3099d-110">If you enforce a different protocol (such as TLS 1.1 or TLS 1.2) by making changes in the operating system SChannel layer, your connections to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] might fail.</span></span>  
  
 <span data-ttu-id="3099d-111">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="3099d-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3099d-112">**Per abilitare e disabilitare un protocollo di rete del server utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="3099d-112">**To enable or disable a server network protocol using:**</span></span>  
  
     [<span data-ttu-id="3099d-113">Gestione configurazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="3099d-113">SQL Server Configuration Manager</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3099d-114">PowerShell</span><span class="sxs-lookup"><span data-stu-id="3099d-114">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3099d-115">Utilizzo di Gestione configurazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="3099d-115">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-enable-a-server-network-protocol"></a><span data-ttu-id="3099d-116">Per abilitare un protocollo di rete del server</span><span class="sxs-lookup"><span data-stu-id="3099d-116">To enable a server network protocol</span></span>  
  
1.  <span data-ttu-id="3099d-117">Nel riquadro della console di Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] espandere **Configurazione di rete SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="3099d-117">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the console pane, expand **SQL Server  Network Configuration**.</span></span>  
  
2.  <span data-ttu-id="3099d-118">Nel riquadro della console fare clic su **Protocolli per**  *\<instance name>* .</span><span class="sxs-lookup"><span data-stu-id="3099d-118">In the console pane, click **Protocols for** *\<instance name>*.</span></span>  
  
3.  <span data-ttu-id="3099d-119">Nel riquadro dei dettagli fare clic con il pulsante destro del mouse sul protocollo da modificare e quindi scegliere **Abilita** o **Disabilita**.</span><span class="sxs-lookup"><span data-stu-id="3099d-119">In the details pane, right-click the protocol you want to change, and then click **Enable** or **Disable**.</span></span>  
  
4.  <span data-ttu-id="3099d-120">Nel riquadro della console fare clic su **Servizi di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="3099d-120">In the console pane, click **SQL Server Services**.</span></span>  
  
5.  <span data-ttu-id="3099d-121">Nel riquadro dei dettagli fare clic con il pulsante destro del mouse su **SQL Server ( ***\<instance name>*** )**, quindi scegliere **Riavvia**per arrestare e riavviare il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] servizio.</span><span class="sxs-lookup"><span data-stu-id="3099d-121">In the details pane, right-click **SQL Server (***\<instance name>***)**, and then click **Restart**, to stop and restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
##  <a name="using-sql-server-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="3099d-122">Utilizzo di SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="3099d-122">Using SQL Server PowerShell</span></span>  
  
#### <a name="to-enable-a-server-network-protocol-using-powershell"></a><span data-ttu-id="3099d-123">Per abilitare un protocollo di rete del server utilizzando PowerShell</span><span class="sxs-lookup"><span data-stu-id="3099d-123">To Enable a Server Network Protocol Using PowerShell</span></span>  
  
1.  <span data-ttu-id="3099d-124">Aprire un prompt dei comandi con autorizzazioni di amministratore.</span><span class="sxs-lookup"><span data-stu-id="3099d-124">Using administrator permissions open a command prompt.</span></span>  
  
2.  <span data-ttu-id="3099d-125">Avviare Windows PowerShell 2.0 dalla barra delle applicazioni oppure fare clic su Start, Tutti i programmi, Accessori, Windows PowerShell e quindi ancora Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3099d-125">Start Windows PowerShell 2.0 from the taskbar, or click Start, then All Programs, then Accessories, then Windows PowerShell, then Windows PowerShell.</span></span>  
  
3.  <span data-ttu-id="3099d-126">Importare il modulo **sqlps** immettendo`Import-Module "sqlps"`</span><span class="sxs-lookup"><span data-stu-id="3099d-126">Import the **sqlps** module by entering `Import-Module "sqlps"`</span></span>  
  
4.  <span data-ttu-id="3099d-127">Eseguire le seguenti istruzioni per abilitare i protocolli TCP e Named Pipes.</span><span class="sxs-lookup"><span data-stu-id="3099d-127">Execute the following statements to enable both the TCP and named pipes protocols.</span></span> <span data-ttu-id="3099d-128">Sostituire `<computer_name>` con il nome del computer in cui è in esecuzione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3099d-128">Replace `<computer_name>` with the name of the computer that is running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3099d-129">Se si configura un'istanza denominata, sostituire `MSSQLSERVER` con il nome dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="3099d-129">If you are configuring a named instance, replace `MSSQLSERVER` with the instance name.</span></span>  
  
     <span data-ttu-id="3099d-130">Per disabilitare i protocolli, impostare le proprietà `IsEnabled` su `$false`.</span><span class="sxs-lookup"><span data-stu-id="3099d-130">To disable protocols, set the `IsEnabled` properties to `$false`.</span></span>  
  
    ```powershell
    $smo = 'Microsoft.SqlServer.Management.Smo.'  
    $wmi = new-object ($smo + 'Wmi.ManagedComputer').  
  
    # List the object properties, including the instance names.  
    $Wmi  
  
    # Enable the TCP protocol on the default instance.  
    $uri = "ManagedComputer[@Name='<computer_name>']/ ServerInstance[@Name='MSSQLSERVER']/ServerProtocol[@Name='Tcp']"  
    $Tcp = $wmi.GetSmoObject($uri)  
    $Tcp.IsEnabled = $true  
    $Tcp.Alter()  
    $Tcp  
  
    # Enable the named pipes protocol for the default instance.  
    $uri = "ManagedComputer[@Name='<computer_name>']/ ServerInstance[@Name='MSSQLSERVER']/ServerProtocol[@Name='Np']"  
    $Np = $wmi.GetSmoObject($uri)  
    $Np.IsEnabled = $true  
    $Np.Alter()  
    $Np  
    ```  
  
#### <a name="to-configure-the-protocols-for-the-local-computer"></a><span data-ttu-id="3099d-131">Per configurare i protocolli per il computer locale</span><span class="sxs-lookup"><span data-stu-id="3099d-131">To configure the protocols for the local computer</span></span>  
  
-   <span data-ttu-id="3099d-132">Quando lo script viene eseguito localmente e configura il computer locale, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell offre una maggiore flessibilità per lo script determinando dinamicamente il nome del computer locale.</span><span class="sxs-lookup"><span data-stu-id="3099d-132">When the script is run locally and configures the local computer, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell can make the script more flexible by dynamically determining the local computer name.</span></span> <span data-ttu-id="3099d-133">Per recuperare il nome del computer locale, sostituire la riga che imposta la variabile `$uri` con la riga seguente.</span><span class="sxs-lookup"><span data-stu-id="3099d-133">To retrieve the local computer name, replace the line setting the `$uri` variable with the following line.</span></span>  
  
    ```powershell
    $uri = "ManagedComputer[@Name='" + (Get-Item env:\computername).Value + "']/ServerInstance[@Name='MSSQLSERVER']/ServerProtocol[@Name='Tcp']"  
    ```  
  
#### <a name="to-restart-the-database-engine-by-using-sql-server-powershell"></a><span data-ttu-id="3099d-134">Per riavviare il Motore di database tramite SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="3099d-134">To restart the Database Engine by using SQL Server PowerShell</span></span>  
  
-   <span data-ttu-id="3099d-135">Dopo aver disabilitato o abilitato i protocolli, è necessario arrestare e riavviare il [!INCLUDE[ssDE](../../includes/ssde-md.md)] per rendere effettiva la modifica.</span><span class="sxs-lookup"><span data-stu-id="3099d-135">After you enable or disable protocols, you must stop and restart the [!INCLUDE[ssDE](../../includes/ssde-md.md)] for the change to take effect.</span></span> <span data-ttu-id="3099d-136">Eseguire le istruzioni seguenti per arrestare e avviare l'istanza predefinita tramite [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3099d-136">Execute the following statements to stop and start the default instance by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell.</span></span> <span data-ttu-id="3099d-137">Per arrestare e avviare un'istanza denominata, sostituire `'MSSQLSERVER'` con `'MSSQL$<instance_name>'`.</span><span class="sxs-lookup"><span data-stu-id="3099d-137">To stop and start a named instance replace `'MSSQLSERVER'` with `'MSSQL$<instance_name>'`.</span></span>  
  
    ```powershell
    # Get a reference to the ManagedComputer class.  
    CD SQLSERVER:\SQL\<computer_name>  
    $Wmi = (Get-Item .).ManagedComputer  
    # Get a reference to the default instance of the Database Engine.  
    $DfltInstance = $Wmi.Services['MSSQLSERVER']  
    # Display the state of the service.  
    $DfltInstance  
    # Stop the service.  
    $DfltInstance.Stop();  
    # Wait until the service has time to stop.  
    # Refresh the cache.  
    $DfltInstance.Refresh();   
    # Display the state of the service.  
    $DfltInstance  
    # Start the service again.  
    $DfltInstance.Start();  
    # Wait until the service has time to start.  
    # Refresh the cache and display the state of the service.  
    $DfltInstance.Refresh(); $DfltInstance  
    ```  
