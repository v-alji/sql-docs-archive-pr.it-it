---
title: Creare un account di accesso | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.LOGIN.SERVERROLES.F1
- sql12.swb.login.databaseaccess.f1
- sql12.swb.login.general.f1
- sql12.swb.login.effectivepermissions.f1
- sql12.swb.login.status.f1
helpviewer_keywords:
- authentication [SQL Server], logins
- logins [SQL Server], creating
- creating logins with Management Studio
- Create login [SQL Server]
- SQL Server logins
ms.assetid: fb163e47-1546-4682-abaa-8c9494e9ddc7
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: e476880103a69ae016c6720f36e26ef884db6f5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714059"
---
# <a name="create-a-login"></a><span data-ttu-id="a1bc4-102">Creazione di un account di accesso</span><span class="sxs-lookup"><span data-stu-id="a1bc4-102">Create a Login</span></span>
  <span data-ttu-id="a1bc4-103">In questo argomento viene descritto come creare un account di accesso in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1bc4-103">This topic describes how to create a login in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="a1bc4-104">Un account di accesso è l'identità della persona o del processo che esegue la connessione a un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1bc4-104">A login is the identity of the person or process that is connecting to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="a1bc4-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a1bc4-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a1bc4-107">Background</span><span class="sxs-lookup"><span data-stu-id="a1bc4-107">Background</span></span>](#Background)  
  
     [<span data-ttu-id="a1bc4-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a1bc4-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a1bc4-109">**Per creare un account di accesso utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-109">**To create a login, using:**</span></span>  
  
     [<span data-ttu-id="a1bc4-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a1bc4-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a1bc4-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a1bc4-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="a1bc4-112">**Completamento:**  [passaggi da effettuare dopo aver creato un account di accesso](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="a1bc4-112">**Follow Up:**  [Steps to take after you create a login](#FollowUp)</span></span>  
  
##  <a name="background"></a><a name="Background"></a> <span data-ttu-id="a1bc4-113">Background</span><span class="sxs-lookup"><span data-stu-id="a1bc4-113">Background</span></span>  
 <span data-ttu-id="a1bc4-114">Un accesso è un'entità di sicurezza o un'entità che può essere autenticata da un sistema sicuro.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-114">A login is a security principal, or an entity that can be authenticated by a secure system.</span></span> <span data-ttu-id="a1bc4-115">Per connettersi a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], gli utenti necessitano di un account di accesso.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-115">Users need a login to connect to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a1bc4-116">È possibile creare un account di accesso basato su un'entità di Windows (quale un utente del dominio o un gruppo del dominio Windows) o è possibile creare un account di accesso che non è basato su un'entità di Windows (ad esempio, un accesso [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="a1bc4-116">You can create a login based on a Windows principal (such as a domain user or a Windows domain group) or you can create a login that is not based on a Windows principal (such as an [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a1bc4-117">Per utilizzare l'autenticazione [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], [!INCLUDE[ssDE](../../../includes/ssde-md.md)] deve utilizzare l'autenticazione a modalità mista.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-117">To use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] must use mixed mode authentication.</span></span> <span data-ttu-id="a1bc4-118">Per altre informazioni, vedere [Scegliere una modalità di autenticazione](../choose-an-authentication-mode.md).</span><span class="sxs-lookup"><span data-stu-id="a1bc4-118">For more information, see [Choose an Authentication Mode](../choose-an-authentication-mode.md).</span></span>  
  
 <span data-ttu-id="a1bc4-119">È possibile concedere autorizzazioni agli account di accesso, in quanto entità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-119">As a security principal, permissions can be granted to logins.</span></span> <span data-ttu-id="a1bc4-120">L'ambito di un account di sicurezza è l'intero [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1bc4-120">The scope of a login is the whole [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span> <span data-ttu-id="a1bc4-121">Affinché un account di accesso possa eseguire la connessione a un database specifico nell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], è necessario eseguirne il mapping a un utente del database.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-121">To connect to a specific database on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], a login must be mapped to a database user.</span></span> <span data-ttu-id="a1bc4-122">Le autorizzazioni all'interno del database vengono concesse e negate all'utente del database, non all'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-122">Permissions inside the database are granted and denied to the database user, not the login.</span></span> <span data-ttu-id="a1bc4-123">È possibile concedere a un account di accesso le autorizzazioni il cui ambito è l'intera istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (ad esempio, l'autorizzazione `CREATE ENDPOINT`).</span><span class="sxs-lookup"><span data-stu-id="a1bc4-123">Permissions that have the scope of the whole instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (for example, the `CREATE ENDPOINT` permission) can be granted to a login.</span></span>  
  
##  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a1bc4-124">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a1bc4-124">Security</span></span>  
  
### <a name="permissions"></a><span data-ttu-id="a1bc4-125">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="a1bc4-125">Permissions</span></span>  
 <span data-ttu-id="a1bc4-126">È richiesta l'autorizzazione `ALTER ANY LOGIN` o `ALTER LOGIN` per il server.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-126">Requires `ALTER ANY LOGIN` or `ALTER LOGIN` permission on the server.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a1bc4-127">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a1bc4-127">Using SQL Server Management Studio</span></span>  
  
##### <a name="to-create-a-sql-server-login"></a><span data-ttu-id="a1bc4-128">Per creare un account di accesso di SQL Server</span><span class="sxs-lookup"><span data-stu-id="a1bc4-128">To create a SQL Server login</span></span>  
  
1.  <span data-ttu-id="a1bc4-129">In Esplora oggetti espandere la cartella dell'istanza del server in cui si desidera creare il nuovo account di accesso.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-129">In Object Explorer, expand the folder of the server instance in which you want to create the new login.</span></span>  
  
2.  <span data-ttu-id="a1bc4-130">Fare clic con il pulsante destro del mouse sulla cartella **Sicurezza**, scegliere **Nuovo** e selezionare **Account di accesso...** .</span><span class="sxs-lookup"><span data-stu-id="a1bc4-130">Right-click the **Security** folder, point to **New**, and select **Login...**.</span></span>  
  
3.  <span data-ttu-id="a1bc4-131">Nella pagina **Generale** della finestra di dialogo **Account di accesso - Nuovo** immettere il nome di un utente nella casella **Nome account di accesso**.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-131">In the **Login - New** dialog box, on the **General** page, enter the name of a user in the **Login name** box.</span></span> <span data-ttu-id="a1bc4-132">In alternativa, fare clic su **Cerca...** per aprire la finestra di dialogo **Seleziona un utente o un gruppo**.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-132">Alternately, click **Search...** to open the **Select User or Group** dialog box.</span></span>  
  
     <span data-ttu-id="a1bc4-133">Se si fa clic su **Cerca...** :</span><span class="sxs-lookup"><span data-stu-id="a1bc4-133">If you click **Search...**:</span></span>  
  
    1.  <span data-ttu-id="a1bc4-134">In **Selezionare questo tipo di oggetto** fare clic su **Tipi di oggetti** per aprire la finestra di dialogo **Tipi di oggetti** e selezionare tutte le opzioni seguenti o solo alcune di esse: **Entità di sicurezza predefinite**, **Gruppi** e **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-134">Under **Select this object type**, click **Object Types...** to open the **Object Types** dialog box and select any or all of the following: **Built-in security principals**, **Groups**, and **Users**.</span></span> <span data-ttu-id="a1bc4-135">Le opzioni**Entità di sicurezza predefinite** e **Utenti** sono selezionate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-135">**Built-in security principals** and **Users** are selected by default.</span></span> <span data-ttu-id="a1bc4-136">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-136">When finished, click **OK**.</span></span>  
  
    2.  <span data-ttu-id="a1bc4-137">In **Da questo percorso** fare clic su **Percorsi...** per aprire la finestra di dialogo **Percorsi** e selezionare uno dei percorsi server disponibili.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-137">Under **From this location**, click **Locations...** to open the **Locations** dialog box and select one of the available server locations.</span></span> <span data-ttu-id="a1bc4-138">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-138">When finished, click **OK**.</span></span>  
  
    3.  <span data-ttu-id="a1bc4-139">In **Immettere il nome dell'oggetto da selezionare (esempi)** , immettere il nome dell'utente o del gruppo che si desidera trovare.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-139">Under **Enter the object name to select (examples)**, enter the user or group name that you want to find.</span></span> <span data-ttu-id="a1bc4-140">Per ulteriori informazioni, vedere [Finestra di dialogo Seleziona utenti, computer o gruppi](https://technet.microsoft.com/library/cc771712.aspx).</span><span class="sxs-lookup"><span data-stu-id="a1bc4-140">For more information, see [Select Users, Computers, or Groups Dialog Box](https://technet.microsoft.com/library/cc771712.aspx).</span></span>  
  
    4.  <span data-ttu-id="a1bc4-141">Fare clic su **Avanzate...** per opzioni di ricerca più avanzate.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-141">Click **Advanced...** for more advanced search options.</span></span> <span data-ttu-id="a1bc4-142">Per altre informazioni, vedere [Finestra di dialogo Seleziona utenti, computer o gruppi - Pagina Avanzate](https://technet.microsoft.com/library/cc733110.aspx).</span><span class="sxs-lookup"><span data-stu-id="a1bc4-142">For more information, see [Select Users, Computers, or Groups Dialog Box - Advanced Page](https://technet.microsoft.com/library/cc733110.aspx).</span></span>  
  
    5.  <span data-ttu-id="a1bc4-143">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-143">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="a1bc4-144">Per creare un account di accesso basato su un'entità di Windows, selezionare **Autenticazione di Windows**.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-144">To create a login based on a Windows principal, select **Windows authentication**.</span></span> <span data-ttu-id="a1bc4-145">Si tratta della selezione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-145">This is the default selection.</span></span>  
  
5.  <span data-ttu-id="a1bc4-146">Per creare un account di accesso salvato in un database di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , selezionare **Autenticazione di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-146">To create a login that is saved on a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database, select **SQL Server authentication**.</span></span>  
  
    1.  <span data-ttu-id="a1bc4-147">Nella casella **Password** digitare una password per il nuovo utente.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-147">In the **Password** box, enter a password for the new user.</span></span> <span data-ttu-id="a1bc4-148">Digitare di nuovo la password nella casella **Conferma password** .</span><span class="sxs-lookup"><span data-stu-id="a1bc4-148">Enter that password again into the **Confirm Password** box.</span></span>  
  
    2.  <span data-ttu-id="a1bc4-149">In caso di modifica di una password esistente, selezionare **Specifica vecchia password**e quindi digitare la password precedente nella casella **Vecchia password** .</span><span class="sxs-lookup"><span data-stu-id="a1bc4-149">When changing an existing password, select **Specify old password**, and then type the old password in the **Old password** box.</span></span>  
  
    3.  <span data-ttu-id="a1bc4-150">Per applicare le opzioni dei criteri password per la complessità e l'applicazione, selezionare **Applica criteri password**.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-150">To enforce password policy options for complexity and enforcement, select **Enforce password policy**.</span></span> <span data-ttu-id="a1bc4-151">Per ulteriori informazioni, vedere [Password Policy](../password-policy.md).</span><span class="sxs-lookup"><span data-stu-id="a1bc4-151">For more information, see [Password Policy](../password-policy.md).</span></span> <span data-ttu-id="a1bc4-152">È un'opzione predefinita quando si seleziona **Autenticazione di SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="a1bc4-152">This is a default option when **SQL Server authentication** is selected.</span></span>  
  
    4.  <span data-ttu-id="a1bc4-153">Per applicare le opzioni dei criteri password per la scadenza, selezionare **Imponi scadenza password**.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-153">To enforce password policy options for expiration, select **Enforce password expiration**.</span></span> <span data-ttu-id="a1bc4-154">Per abilitare questa casella di controllo, è necessario selezionare**Applica criteri password** .</span><span class="sxs-lookup"><span data-stu-id="a1bc4-154">**Enforce password policy** must be selected to enable this checkbox.</span></span> <span data-ttu-id="a1bc4-155">È un'opzione predefinita quando si seleziona **Autenticazione di SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="a1bc4-155">This is a default option when **SQL Server authentication** is selected.</span></span>  
  
    5.  <span data-ttu-id="a1bc4-156">Per forzare l'utente a creare una nuova password dopo la prima volta che l'account di accesso viene utilizzato, selezionare **Richiedi modifica della password all'accesso successivo**.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-156">To force the user to create a new password after the first time the login is used, select **User must change password at next login**.</span></span> <span data-ttu-id="a1bc4-157">Per abilitare questa casella di controllo, è necessario selezionare**Imponi scadenza password** .</span><span class="sxs-lookup"><span data-stu-id="a1bc4-157">**Enforce password expiration** must be selected to enable this checkbox.</span></span> <span data-ttu-id="a1bc4-158">È un'opzione predefinita quando si seleziona **Autenticazione di SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="a1bc4-158">This is a default option when **SQL Server authentication** is selected.</span></span>  
  
6.  <span data-ttu-id="a1bc4-159">Per associare l'account di accesso a un certificato di sicurezza autonomo, selezionare **Mapping con certificato** , quindi selezionare il nome di un certificato esistente dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-159">To associate the login with a stand-alone security certificate, select **Mapped to certificate** and then select the name of an existing certificate from the list.</span></span>  
  
7.  <span data-ttu-id="a1bc4-160">Per associare l'account di accesso a una chiave asimmetrica autonoma, selezionare **Mapping con chiave asimmetrica** , quindi selezionare il nome di una chiave esistente dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-160">To associate the login with a stand-alone asymmetric key, select **Mapped to asymmetric key** to, and then select the name of an existing key from the list.</span></span>  
  
8.  <span data-ttu-id="a1bc4-161">Per associare l'accesso a credenziali di sicurezza, selezionare la casella di controllo **Credenziali con mapping** , quindi selezionare credenziali esistenti dall'elenco o fare clic su **Aggiungi** per creare nuove credenziali.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-161">To associate the login with a security credential, select the **Mapped to Credential** check box, and then either select an existing credential from the list or click **Add** to create a new credential.</span></span> <span data-ttu-id="a1bc4-162">Per rimuovere un mapping a credenziali di sicurezza dall'account di accesso, selezionare le credenziali da **Credenziali con mapping** e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-162">To remove a mapping to a security credential from the login, select the credential from **Mapped Credentials** and click **Remove**.</span></span> <span data-ttu-id="a1bc4-163">Per altre informazioni sulle credenziali in generale, vedere [Credenziali &#40;motore di database&#41;](credentials-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="a1bc4-163">For more information about credentials in general, see [Credentials &#40;Database Engine&#41;](credentials-database-engine.md).</span></span>  
  
9. <span data-ttu-id="a1bc4-164">Selezionare dall'elenco **Database predefinito** un database predefinito per l'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-164">From the **Default database** list, select a default database for the login.</span></span> <span data-ttu-id="a1bc4-165">**Principale** è il valore predefinito per questa opzione.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-165">**Master** is the default for this option.</span></span>  
  
10. <span data-ttu-id="a1bc4-166">Selezionare dall'elenco **Lingua predefinita** una lingua predefinita per l'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-166">From the **Default language** list, select a default language for the login.</span></span>  
  
11. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="additional-options"></a><span data-ttu-id="a1bc4-167">Opzioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a1bc4-167">Additional Options</span></span>  
 <span data-ttu-id="a1bc4-168">La finestra di dialogo **Account di accesso - Nuovo** offre inoltre opzioni in altre quattro pagine: **Ruoli del server**, **Mapping utenti**, **Entità a protezione diretta** e **Stato**.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-168">The **Login - New** dialog box also offers options on four additional pages: **Server Roles**, **User Mapping**, **Securables**, and **Status**.</span></span>  
  
### <a name="server-roles"></a><span data-ttu-id="a1bc4-169">Ruoli del server</span><span class="sxs-lookup"><span data-stu-id="a1bc4-169">Server Roles</span></span>  
 <span data-ttu-id="a1bc4-170">Nella pagina **Ruoli del server** sono elencati tutti i possibili ruoli che possono essere assegnati al nuovo account accesso.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-170">The **Server Roles** page lists all possible roles that can be assigned to the new login.</span></span> <span data-ttu-id="a1bc4-171">Sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a1bc4-171">The following options are available:</span></span>  
  
 <span data-ttu-id="a1bc4-172">Casella di controllo**bulkadmin**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-172">**bulkadmin** check box</span></span>  
 <span data-ttu-id="a1bc4-173">I membri del ruolo predefinito del server **bulkadmin** sono autorizzati a eseguire l'istruzione BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-173">Members of the **bulkadmin** fixed server role can run the BULK INSERT statement.</span></span>  
  
 <span data-ttu-id="a1bc4-174">Casella di controllo**dbcreator**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-174">**dbcreator** check box</span></span>  
 <span data-ttu-id="a1bc4-175">I membri del ruolo predefinito del server **dbcreator** sono autorizzati a creare, modificare, eliminare e ripristinare qualsiasi database.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-175">Members of the **dbcreator** fixed server role can create, alter, drop, and restore any database.</span></span>  
  
 <span data-ttu-id="a1bc4-176">Casella di controllo**diskadmin**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-176">**diskadmin** check box</span></span>  
 <span data-ttu-id="a1bc4-177">I membri del ruolo predefinito del server **diskadmin** sono autorizzati a gestire file su disco.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-177">Members of the **diskadmin** fixed server role can manage disk files.</span></span>  
  
 <span data-ttu-id="a1bc4-178">Casella di controllo**processadmin**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-178">**processadmin** check box</span></span>  
 <span data-ttu-id="a1bc4-179">I membri del ruolo predefinito del server **processadmin** sono autorizzati a terminare processi in esecuzione in un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1bc4-179">Members of the **processadmin** fixed server role can terminate processes running in an instance of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="a1bc4-180">Casella di controllo**public**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-180">**public** check box</span></span>  
 <span data-ttu-id="a1bc4-181">Tutti gli utenti, gruppi e ruoli di SQL Server appartengono al ruolo predefinito del server **public** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-181">All SQL Server users, groups, and roles belong to the **public** fixed server role by default.</span></span>  
  
 <span data-ttu-id="a1bc4-182">Casella di controllo**securityadmin**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-182">**securityadmin** check box</span></span>  
 <span data-ttu-id="a1bc4-183">I membri del ruolo predefinito del server **securityadmin** gestiscono gli account di accesso e le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-183">Members of the **securityadmin** fixed server role manage logins and their properties.</span></span> <span data-ttu-id="a1bc4-184">Possono concedere, negare e revocare le autorizzazioni a livello di server</span><span class="sxs-lookup"><span data-stu-id="a1bc4-184">They can GRANT, DENY, and REVOKE server-level permissions.</span></span> <span data-ttu-id="a1bc4-185">e a livello di database.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-185">They can also GRANT, DENY, and REVOKE database-level permissions.</span></span> <span data-ttu-id="a1bc4-186">Questi membri sono inoltre autorizzati a reimpostare le password per gli account di accesso di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a1bc4-186">Additionally, they can reset passwords for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins.</span></span>  
  
 <span data-ttu-id="a1bc4-187">Casella di controllo**serveradmin**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-187">**serveradmin** check box</span></span>  
 <span data-ttu-id="a1bc4-188">I membri del ruolo predefinito del server **serveradmin** sono autorizzati a modificare le opzioni di configurazione a livello di server e ad arrestare il server.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-188">Members of the **serveradmin** fixed server role can change server-wide configuration options and shut down the server.</span></span>  
  
 <span data-ttu-id="a1bc4-189">Casella di controllo**setupadmin**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-189">**setupadmin** check box</span></span>  
 <span data-ttu-id="a1bc4-190">I membri del ruolo predefinito del server **setupadmin** possono aggiungere e rimuovere server collegati e inoltre eseguire alcune stored procedure di sistema.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-190">Members of the **setupadmin** fixed server role can add and remove linked servers, and they can execute some system stored procedures.</span></span>  
  
 <span data-ttu-id="a1bc4-191">Casella di controllo**sysadmin**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-191">**sysadmin** check box</span></span>  
 <span data-ttu-id="a1bc4-192">I membri del ruolo predefinito del server **sysadmin** sono autorizzati a eseguire qualsiasi attività nel [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1bc4-192">Members of the **sysadmin** fixed server role can perform any activity in the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
### <a name="user-mapping"></a><span data-ttu-id="a1bc4-193">Mapping utenti</span><span class="sxs-lookup"><span data-stu-id="a1bc4-193">User Mapping</span></span>  
 <span data-ttu-id="a1bc4-194">Nella pagina **Mapping utenti** sono elencati tutti i possibili database e le appartenenze al ruolo dei database che possono essere applicati all'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-194">The **User Mapping** page lists all possible databases and the database role memberships on those databases that can be applied to the login.</span></span> <span data-ttu-id="a1bc4-195">I database selezionati determinano le appartenenze al ruolo che sono disponibili per l'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-195">The databases selected determine the role memberships that are available for the login.</span></span> <span data-ttu-id="a1bc4-196">In questa pagina sono disponibili le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-196">The following options are available on this page:</span></span>  
  
 <span data-ttu-id="a1bc4-197">**Utenti di cui è stato eseguito il mapping all'account di accesso seguente**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-197">**Users mapped to this login**</span></span>  
 <span data-ttu-id="a1bc4-198">Consente di selezionare i database ai quali può accedere l'account di accesso specificato.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-198">Select the databases that this login can access.</span></span> <span data-ttu-id="a1bc4-199">Quando si seleziona un database, i rispettivi ruoli validi vengono visualizzati nel riquadro **Appartenenza a ruoli del database per:** _database_name_.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-199">When you select a database, its valid database roles are displayed in the **Database role membership for:** _database_name_ pane.</span></span>  
  
 <span data-ttu-id="a1bc4-200">**Mappa**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-200">**Map**</span></span>  
 <span data-ttu-id="a1bc4-201">Consente all'account di accesso di accedere al database sotto indicato.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-201">Allow the login to access the databases listed below.</span></span>  
  
 <span data-ttu-id="a1bc4-202">**Database**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-202">**Database**</span></span>  
 <span data-ttu-id="a1bc4-203">Elenca i database disponibili sul server.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-203">Lists the databases available on the server.</span></span>  
  
 <span data-ttu-id="a1bc4-204">**Utente**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-204">**User**</span></span>  
 <span data-ttu-id="a1bc4-205">Consente di specificare l'utente del database a cui eseguire il mapping dell'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-205">Specify a database user to map to the login.</span></span> <span data-ttu-id="a1bc4-206">Per impostazione predefinita, il nome dell'utente del database è uguale all'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-206">By default, the database user has the same name as the login.</span></span>  
  
 <span data-ttu-id="a1bc4-207">**Schema predefinito**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-207">**Default Schema**</span></span>  
 <span data-ttu-id="a1bc4-208">Consente di specificare lo schema predefinito dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-208">Specifies the default schema of the user.</span></span> <span data-ttu-id="a1bc4-209">Lo schema predefinito dei nuovi utenti creati è **dbo**.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-209">When a user is first created, its default schema is **dbo**.</span></span> <span data-ttu-id="a1bc4-210">È possibile specificare uno schema predefinito non ancora creato.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-210">It is possible to specify a default schema that does not yet exist.</span></span> <span data-ttu-id="a1bc4-211">Non è possibile specificare uno schema predefinito per un utente del quale è stato eseguito il mapping a un gruppo di Windows, un certificato o una chiave asimmetrica.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-211">You cannot specify a default schema for a user that is mapped to a Windows group, a certificate, or an asymmetric key.</span></span>  
  
 <span data-ttu-id="a1bc4-212">**Account Guest abilitato per:** _database_name_</span><span class="sxs-lookup"><span data-stu-id="a1bc4-212">**Guest account enabled for:**  _database_name_</span></span>  
 <span data-ttu-id="a1bc4-213">Attributo di sola lettura che indica se l'account Guest è abilitato nel database selezionato.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-213">Read-only attribute indicating whether the Guest account is enabled on the selected database.</span></span> <span data-ttu-id="a1bc4-214">Utilizzare la pagina **Stato** della finestra di dialogo **Proprietà account di accesso** dell'account Guest per abilitare o disabilitare tale account.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-214">Use the **Status** page of the **Login Properties** dialog box of the Guest account to enable or disable the Guest account.</span></span>  
  
 <span data-ttu-id="a1bc4-215">**Appartenenza a ruoli del database per:** _database_name_</span><span class="sxs-lookup"><span data-stu-id="a1bc4-215">**Database role membership for:**  _database_name_</span></span>  
 <span data-ttu-id="a1bc4-216">Consente di selezionare i ruoli per l'utente nel database specificato.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-216">Select the roles for the user in the specified database.</span></span> <span data-ttu-id="a1bc4-217">Tutti gli utenti sono membri del ruolo **public** in ogni database e non possono essere eliminati.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-217">All users are members of the **public** role in every database and cannot be removed.</span></span> <span data-ttu-id="a1bc4-218">Per altre informazioni sui ruoli di database, vedere [Ruoli a livello di database](database-level-roles.md).</span><span class="sxs-lookup"><span data-stu-id="a1bc4-218">For more information about database roles, see [Database-Level Roles](database-level-roles.md).</span></span>  
  
### <a name="securables"></a><span data-ttu-id="a1bc4-219">Entità a protezione diretta</span><span class="sxs-lookup"><span data-stu-id="a1bc4-219">Securables</span></span>  
 <span data-ttu-id="a1bc4-220">Nella pagina **Entità a protezione diretta** sono elencate tutte le possibili entità a protezione diretta e le autorizzazioni su quelle entità a protezione diretta che possono essere concesse all'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-220">The **Securables** page lists all possible securables and the permissions on those securables that can be granted to the login.</span></span> <span data-ttu-id="a1bc4-221">In questa pagina sono disponibili le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-221">The following options are available on this page:</span></span>  
  
 <span data-ttu-id="a1bc4-222">**Griglia superiore**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-222">**Upper Grid**</span></span>  
 <span data-ttu-id="a1bc4-223">Contiene uno o più elementi per i quali è possibile impostare le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-223">Contains one or more items for which permissions can be set.</span></span> <span data-ttu-id="a1bc4-224">Le colonne visualizzate nella griglia superiore variano a seconda del tipo di entità o di entità a sicurezza diretta.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-224">The columns that are displayed in the upper grid vary depending on the principal or securable.</span></span>  
  
 <span data-ttu-id="a1bc4-225">Per aggiungere elementi alla griglia superiore:</span><span class="sxs-lookup"><span data-stu-id="a1bc4-225">To add items to the upper grid:</span></span>  
  
1.  <span data-ttu-id="a1bc4-226">Fare clic su **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-226">Click **Search**.</span></span>  
  
2.  <span data-ttu-id="a1bc4-227">Nella finestra di dialogo **Aggiungi oggetti** selezionare una delle opzioni seguenti: **oggetti specifici...**, **tutti gli oggetti di tipo...** o **il server**_server_name_.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-227">In the **Add Objects** dialog box, select one of the following options: **Specific objects...**, **All objects of the types...**, or **The server**_server_name_.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="a1bc4-228">Selezionando **il server**_server_name_ viene automaticamente riempita la griglia superiore con tutti gli oggetti a protezione diretta di tale server.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-228">Selecting **The server**_server_name_ automatically fills the upper grid with all of that servers' securable objects.</span></span>  
  
3.  <span data-ttu-id="a1bc4-229">Se si seleziona **Oggetti specifici...** :</span><span class="sxs-lookup"><span data-stu-id="a1bc4-229">If you select **Specific objects...**:</span></span>  
  
    1.  <span data-ttu-id="a1bc4-230">Nella finestra di dialogo **Seleziona oggetti** in **Selezionare i tipi di oggetti seguenti** fare clic su **Tipi di oggetti...** .</span><span class="sxs-lookup"><span data-stu-id="a1bc4-230">In the **Select Objects** dialog box, under **Select these object types**, click **Object Types...**.</span></span>  
  
    2.  <span data-ttu-id="a1bc4-231">Nella finestra di dialogo **Seleziona tipi di oggetti** selezionare uno o tutti i tipi di oggetti seguenti: **Endpoint**, **Account di accesso**, **Server**, **Gruppi di disponibilità** e **Ruoli del server**.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-231">In the **Select Object Types** dialog box, select any or all of the following object types: **Endpoints**, **Logins**, **Servers**, **Availability Groups**, and **Server roles**.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
    3.  <span data-ttu-id="a1bc4-232">In **Immettere i nomi degli oggetti da selezionare (esempi)** fare clic su **Sfoglia...** .</span><span class="sxs-lookup"><span data-stu-id="a1bc4-232">Under **Enter the object names to select (examples)**, click **Browse...**.</span></span>  
  
    4.  <span data-ttu-id="a1bc4-233">Nella finestra di dialogo **Cerca oggetti** , selezionare gli oggetti disponibili del tipo selezionato nella finestra di dialogo **Seleziona tipi di oggetti** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-233">In the **Browse for Objects** dialog box, select any of the available objects of the type that you selected in the **Select Object Types** dialog box, and then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="a1bc4-234">Nella finestra di dialogo **Seleziona oggetti** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-234">In the **Select Objects** dialog box, click **OK**.</span></span>  
  
4.  <span data-ttu-id="a1bc4-235">Se si seleziona **Tutti gli oggetti di tipo** nella finestra di dialogo **Seleziona tipi di oggetti**, selezionare uno o tutti i tipi di oggetti seguenti: **Endpoint**, **Account di accesso**, **Server**, **Gruppi di disponibilità** e **Ruoli del server**.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-235">If you select **All objects of the types...**, in the **Select Object Types** dialog box, select any or all of the following object types: **Endpoints**, **Logins**, **Servers**, **Availability Groups**, and **Server roles**.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
 <span data-ttu-id="a1bc4-236">**Nome**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-236">**Name**</span></span>  
 <span data-ttu-id="a1bc4-237">Nome di ogni entità o entità a sicurezza diretta aggiunto alla griglia.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-237">The name of each principal or securable that is added to the grid.</span></span>  
  
 <span data-ttu-id="a1bc4-238">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-238">**Type**</span></span>  
 <span data-ttu-id="a1bc4-239">Descrive il tipo di ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-239">Describes the type of each item.</span></span>  
  
 <span data-ttu-id="a1bc4-240">**Scheda Esplicita**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-240">**Explicit Tab**</span></span>  
 <span data-ttu-id="a1bc4-241">Sono elencate le possibili autorizzazioni per l'entità a protezione diretta selezionate nella griglia superiore.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-241">Lists the possible permissions for the securable that are selected in the upper grid.</span></span> <span data-ttu-id="a1bc4-242">Non tutte le opzioni sono disponibili per tutte le autorizzazioni esplicite.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-242">Not all options are available for all explicit permissions.</span></span>  
  
 <span data-ttu-id="a1bc4-243">**Autorizzazioni**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-243">**Permissions**</span></span>  
 <span data-ttu-id="a1bc4-244">Nome dell'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-244">The name of the permission.</span></span>  
  
 <span data-ttu-id="a1bc4-245">**Utente che concede le autorizzazioni**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-245">**Grantor**</span></span>  
 <span data-ttu-id="a1bc4-246">Entità che ha concesso l'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-246">The principal that granted the permission.</span></span>  
  
 <span data-ttu-id="a1bc4-247">**Concedi**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-247">**Grant**</span></span>  
 <span data-ttu-id="a1bc4-248">Selezionare questa opzione per concedere l'autorizzazione all'account di accesso,</span><span class="sxs-lookup"><span data-stu-id="a1bc4-248">Select to grant this permission to the login.</span></span> <span data-ttu-id="a1bc4-249">deselezionarla per revocare l'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-249">Clear to revoke this permission.</span></span>  
  
 <span data-ttu-id="a1bc4-250">**Con diritto di concessione**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-250">**With Grant**</span></span>  
 <span data-ttu-id="a1bc4-251">Riflette lo stato dell'opzione WITH GRANT relativo all'autorizzazione elencata.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-251">Reflects the state of the WITH GRANT option for the listed permission.</span></span> <span data-ttu-id="a1bc4-252">Il contenuto di questa casella è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-252">This box is read-only.</span></span> <span data-ttu-id="a1bc4-253">Per applicare questa autorizzazione, utilizzare l'istruzione [GRANT](/sql/t-sql/statements/grant-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="a1bc4-253">To apply this permission, use the [GRANT](/sql/t-sql/statements/grant-transact-sql) statement.</span></span>  
  
 <span data-ttu-id="a1bc4-254">**Nega**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-254">**Deny**</span></span>  
 <span data-ttu-id="a1bc4-255">Selezionare questa opzione per negare l'autorizzazione all'account di accesso,</span><span class="sxs-lookup"><span data-stu-id="a1bc4-255">Select to deny this permission to the login.</span></span> <span data-ttu-id="a1bc4-256">deselezionarla per revocare l'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-256">Clear to revoke this permission.</span></span>  
  
### <a name="status"></a><span data-ttu-id="a1bc4-257">Stato</span><span class="sxs-lookup"><span data-stu-id="a1bc4-257">Status</span></span>  
 <span data-ttu-id="a1bc4-258">Nella pagina **Stato** sono elencate alcune opzioni di autenticazione e autorizzazione che possono essere configurate nell'account di accesso [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] selezionato.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-258">The **Status** page lists some of the authentication and authorization options that can be configured on the selected [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login.</span></span>  
  
 <span data-ttu-id="a1bc4-259">In questa pagina sono disponibili le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-259">The following options are available on this page:</span></span>  
  
 <span data-ttu-id="a1bc4-260">**Autorizzazione per la connessione al Motore di database**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-260">**Permission to connect to database engine**</span></span>  
 <span data-ttu-id="a1bc4-261">Quando si utilizza questa impostazione, è consigliabile pensare all'account di accesso selezionato come a un'entità a cui è possibile concedere o negare l'autorizzazione per un'entità a sicurezza diretta.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-261">When you work with this setting, you should think of the selected login as a principal that can be granted or denied permission on a securable.</span></span>  
  
 <span data-ttu-id="a1bc4-262">Selezionare **Concedi** per concedere l'autorizzazione CONNECT SQL all'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-262">Select **Grant** to grant CONNECT SQL permission to the login.</span></span> <span data-ttu-id="a1bc4-263">Selezionare **Nega** per negare l'autorizzazione CONNECT SQL all'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-263">Select **Deny** to deny CONNECT SQL to the login.</span></span>  
  
 <span data-ttu-id="a1bc4-264">**Accesso**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-264">**Login**</span></span>  
 <span data-ttu-id="a1bc4-265">Quando si utilizza questa impostazione, è consigliabile pensare all'account di accesso selezionato come a un record in una tabella.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-265">When you work with this setting, you should think of the selected login as a record in a table.</span></span> <span data-ttu-id="a1bc4-266">Le modifiche ai valori elencati qui verranno applicate al record.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-266">Changes to the values listed here will be applied to the record.</span></span>  
  
 <span data-ttu-id="a1bc4-267">Un account di accesso che è stato disabilitato continua a esistere come record.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-267">A login that has been disabled continues to exist as a record.</span></span> <span data-ttu-id="a1bc4-268">Se tuttavia tenta di connettersi a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], l'account di accesso non viene autenticato.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-268">But if it tries to connect to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the login will not be authenticated.</span></span>  
  
 <span data-ttu-id="a1bc4-269">Selezionare questa opzione per abilitare o disabilitare l'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-269">Select this option to enable or disable this login.</span></span> <span data-ttu-id="a1bc4-270">Questa opzione utilizza l'istruzione ALTER LOGIN insieme all'opzione ENABLE o DISABLE.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-270">This option uses the ALTER LOGIN statement with the either ENABLE or DISABLE option.</span></span>  
  
 <span data-ttu-id="a1bc4-271">**Autenticazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="a1bc4-271">**SQL Server Authentication**</span></span>  
 <span data-ttu-id="a1bc4-272">La casella di controllo **Account di accesso bloccato** è disponibile solo se l'account di accesso selezionato si connette utilizzando l'autenticazione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ed è stato bloccato. Questa impostazione è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-272">The check box **Login is locked out** is only available if the selected login connects using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication and the login has been locked out. This setting is read-only.</span></span> <span data-ttu-id="a1bc4-273">Per sbloccare un account di accesso bloccato, eseguire l'istruzione ALTER LOGIN con l'opzione UNLOCK.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-273">To unlock a login that is locked out, execute ALTER LOGIN with the UNLOCK option.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a1bc4-274">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a1bc4-274">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-login-using-windows-authentication"></a><span data-ttu-id="a1bc4-275">Per creare un account di accesso tramite l'autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="a1bc4-275">To create a login using Windows Authentication</span></span>  
  
1.  <span data-ttu-id="a1bc4-276">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1bc4-276">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a1bc4-277">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-277">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a1bc4-278">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-278">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Create a login for SQL Server by specifying a server name and a Windows domain account name.  
  
    CREATE LOGIN [<domainName>\<loginName>] FROM WINDOWS;  
    GO  
  
    ```  
  
#### <a name="to-create-a-login-using-sql-server-authentication"></a><span data-ttu-id="a1bc4-279">Per creare un account di accesso tramite l'autenticazione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="a1bc4-279">To create a login using SQL Server Authentication</span></span>  
  
1.  <span data-ttu-id="a1bc4-280">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1bc4-280">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a1bc4-281">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-281">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a1bc4-282">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-282">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates the user "shcooper" for SQL Server using the security credential "RestrictedFaculty"   
    -- The user login starts with the password "Baz1nga," but that password must be changed after the first login.  
  
    CREATE LOGIN shcooper   
       WITH PASSWORD = 'Baz1nga' MUST_CHANGE,  
       CREDENTIAL = RestrictedFaculty;  
    GO  
  
    ```  
  
 <span data-ttu-id="a1bc4-283">Per altre informazioni, vedere [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a1bc4-283">For more information, see [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span></span>  
  
##  <a name="follow-up-steps-to-take-after-you-create-a-login"></a><a name="FollowUp"></a> <span data-ttu-id="a1bc4-284">Completamento: passaggi da effettuare dopo aver creato un account di accesso</span><span class="sxs-lookup"><span data-stu-id="a1bc4-284">Follow Up: Steps to take after you create a login</span></span>  
 <span data-ttu-id="a1bc4-285">Una volta creato, un account di accesso può connettersi a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], ma potrebbe non disporre delle autorizzazioni necessarie a eseguire operazioni utili.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-285">After creating a login, the login can connect to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], but does not necessarily have sufficient permission to perform any useful work.</span></span> <span data-ttu-id="a1bc4-286">Nell'elenco seguente vengono indicati alcuni collegamenti alle operazioni più comuni degli account di accesso.</span><span class="sxs-lookup"><span data-stu-id="a1bc4-286">The following list provides links to common login actions.</span></span>  
  
-   <span data-ttu-id="a1bc4-287">Per consentire l'aggiunta di un account di accesso a un ruolo database, vedere [Aggiungere un ruolo](join-a-role.md).</span><span class="sxs-lookup"><span data-stu-id="a1bc4-287">To have the login join a role, see [Join a Role](join-a-role.md).</span></span>  
  
-   <span data-ttu-id="a1bc4-288">Per autorizzare l'utilizzo di un database da parte di un account di accesso, vedere [Creare un utente del database](../authentication-access/create-a-database-user.md).</span><span class="sxs-lookup"><span data-stu-id="a1bc4-288">To authorize a login to use a database, see [Create a Database User](../authentication-access/create-a-database-user.md).</span></span>  
  
-   <span data-ttu-id="a1bc4-289">Per concedere un'autorizzazione a un account di accesso, vedere [Concedere un'autorizzazione a un'entità](grant-a-permission-to-a-principal.md).</span><span class="sxs-lookup"><span data-stu-id="a1bc4-289">To grant a permission to a login, see [Grant a Permission to a Principal](grant-a-permission-to-a-principal.md).</span></span>  
  
  
