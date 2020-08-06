---
title: Creare un profilo di Posta elettronica database | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Database Mail [SQL Server], public profiles
- profiles [SQL Server], Database Mail
- public profiles [Database Mail]
ms.assetid: 58ae749d-6ada-4f9c-bf00-de7c7a992a2d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0453d495c90c1e599bfc7777b4899f30e6659c52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626806"
---
# <a name="create-a-database-mail-profile"></a><span data-ttu-id="96ef3-102">Creare un profilo di Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="96ef3-102">Create a Database Mail Profile</span></span>
  <span data-ttu-id="96ef3-103">Per creare profili pubblici e privati di Posta elettronica database, è possibile utilizzare **Configurazione guidata posta elettronica database** o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="96ef3-103">Use either the **Database Mail Configuration Wizard** or [!INCLUDE[tsql](../../includes/tsql-md.md)] to create Database Mail public and private profiles.</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="96ef3-104">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="96ef3-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="96ef3-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="96ef3-105">Prerequisites</span></span>  
 <span data-ttu-id="96ef3-106">Creare uno o più account di Posta elettronica database per il profilo.</span><span class="sxs-lookup"><span data-stu-id="96ef3-106">Create one or more Database Mail accounts for the profile.</span></span> <span data-ttu-id="96ef3-107">Per altre informazioni sulla creazione di account di Posta elettronica database, vedere [Creare un account di Posta elettronica database](create-a-database-mail-account.md).</span><span class="sxs-lookup"><span data-stu-id="96ef3-107">For more information about creating Database Mail accounts, see [Create a Database Mail Account](create-a-database-mail-account.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="96ef3-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="96ef3-108">Security</span></span>  
 <span data-ttu-id="96ef3-109">Gli utenti in grado di accedere al database **msdb** possono usare un profilo pubblico per inviare messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="96ef3-109">A public profile allows any user with access to the **msdb** database to send e-mail using that profile.</span></span> <span data-ttu-id="96ef3-110">Un profilo privato può essere utilizzato da un utente o da un ruolo.</span><span class="sxs-lookup"><span data-stu-id="96ef3-110">A private profile can be used by a user or by a role.</span></span> <span data-ttu-id="96ef3-111">Concedendo ai ruoli l'accesso ai profili viene creata un'architettura gestita in modo più semplice.</span><span class="sxs-lookup"><span data-stu-id="96ef3-111">Granting roles access to profiles creates a more easily maintained architecture.</span></span> <span data-ttu-id="96ef3-112">Solo un membro del ruolo **DatabaseMailUserRole** del database **msdb** con accesso ad almeno un profilo di Posta elettronica database può inviare messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="96ef3-112">To send mail you must be a member of the **DatabaseMailUserRole** in the **msdb** database, and have access to at least one Database Mail profile.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="96ef3-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="96ef3-113">Permissions</span></span>  
 <span data-ttu-id="96ef3-114">Per creare gli account dei profili ed eseguire le stored procedure è necessario che l'utente sia un membro del ruolo predefinito del server sysadmin.</span><span class="sxs-lookup"><span data-stu-id="96ef3-114">The user creating the profiles accounts and executing stored procedures should be a member of the sysadmin fixed server role.</span></span>  
  

  
##  <a name="using-database-mail-configuration-wizard"></a><a name="SSMSProcedure"></a> <span data-ttu-id="96ef3-115">Utilizzo della Configurazione guidata Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="96ef3-115">Using Database Mail Configuration Wizard</span></span>  
 <span data-ttu-id="96ef3-116">**Per creare un profilo di Posta elettronica database**</span><span class="sxs-lookup"><span data-stu-id="96ef3-116">**To Create a Database Mail profile**</span></span>  
  
-   <span data-ttu-id="96ef3-117">In Esplora oggetti, connettersi all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] su cui si desidera configurare Posta elettronica database ed espandere l'albero di server.</span><span class="sxs-lookup"><span data-stu-id="96ef3-117">In Object Explorer, connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you want to configure Database Mail on, and expand the server tree.</span></span>  
  
-   <span data-ttu-id="96ef3-118">Espandere il nodo **Gestione**</span><span class="sxs-lookup"><span data-stu-id="96ef3-118">Expand the **Management** node</span></span>  
  
-   <span data-ttu-id="96ef3-119">Fare doppio clic su Posta elettronica database per aprire la Configurazione guidata posta elettronica database.</span><span class="sxs-lookup"><span data-stu-id="96ef3-119">Double click Database Mail to open the Database Mail Configuration Wizard.</span></span>  
  
-   <span data-ttu-id="96ef3-120">Nella pagina **Selezione attività di configurazione** selezionare l'opzione **Gestisci account e profili posta elettronica database** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="96ef3-120">On the **Select Configuration Task** page, select **Manage Database Mail accounts and profiles** option and click **Next**.</span></span>  
  
-   <span data-ttu-id="96ef3-121">Nella pagina **Gestione profili e account** selezionare l'opzione **Crea un nuovo profilo** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="96ef3-121">On the **Manage Profiles and Accounts** page, select **Create a new profile** option, and click **Next**.</span></span>  
  
-   <span data-ttu-id="96ef3-122">Nella pagina **Nuovo profilo** specificare il nome e la descrizione del profilo e aggiungere gli account da includere nel profilo, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="96ef3-122">On the **New Profile** page, specify the Profile name, Description and add accounts to be included in the profile, and click **Next**.</span></span>  
  
-   <span data-ttu-id="96ef3-123">Per completare la creazione del nuovo profilo, rivedere le azioni da eseguire nella pagina **Completamento procedura guidata** quindi fare clic su **Fine** .</span><span class="sxs-lookup"><span data-stu-id="96ef3-123">On the **Complete the Wizard** page, review the actions to be performed and click **Finish** to complete creating the new profile.</span></span>  
  
-   <span data-ttu-id="96ef3-124">**Per configurare un profilo privato di Posta elettronica database:**</span><span class="sxs-lookup"><span data-stu-id="96ef3-124">**To configure a Database Mail private profile:**</span></span>  
  
    -   <span data-ttu-id="96ef3-125">Aprire la configurazione guidata posta elettronica database.</span><span class="sxs-lookup"><span data-stu-id="96ef3-125">Open the Database Mail Configuration Wizard.</span></span>  
  
    -   <span data-ttu-id="96ef3-126">Nella pagina **Selezione attività di configurazione** selezionare l'opzione **Gestisci account e profili di Posta elettronica database** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="96ef3-126">On the **Select Configuration Task** page, select **Manage Database Mail accounts and profiles** option, and click **Next**.</span></span>  
  
    -   <span data-ttu-id="96ef3-127">Nella pagina **Gestione profili e account** selezionare l'opzione **Gestione sicurezza profilo** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="96ef3-127">On the **Manage Profiles and Accounts** page, select **Manage profile security** option and click **Next**.</span></span>  
  
    -   <span data-ttu-id="96ef3-128">Nella scheda **Profili privati** selezionare la casella di controllo per il profilo che si desidera configurare e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="96ef3-128">In the **Private Profiles** tab, select the check box for the profile you would like to configure and click **Next**.</span></span>  
  
    -   <span data-ttu-id="96ef3-129">Per completare la configurazione del profilo, rivedere le azioni da eseguire nella pagina **Completamento procedura guidata** quindi fare clic su **Fine** .</span><span class="sxs-lookup"><span data-stu-id="96ef3-129">On the **Complete the Wizard** page, review the actions to be performed and click **Finish** to complete configuring the profile.</span></span>  
  
-   <span data-ttu-id="96ef3-130">**Per configurare un profilo pubblico di Posta elettronica database:**</span><span class="sxs-lookup"><span data-stu-id="96ef3-130">**To configure a Database Mail public profile:**</span></span>  
  
    -   <span data-ttu-id="96ef3-131">Aprire la configurazione guidata posta elettronica database.</span><span class="sxs-lookup"><span data-stu-id="96ef3-131">Open the Database Mail Configuration Wizard.</span></span>  
  
    -   <span data-ttu-id="96ef3-132">Nella pagina **Selezione attività di configurazione** selezionare l'opzione **Gestisci account e profili di Posta elettronica database** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="96ef3-132">On the **Select Configuration Task** page, select **Manage Database Mail accounts and profiles** option, and click **Next**.</span></span>  
  
    -   <span data-ttu-id="96ef3-133">Nella pagina **Gestione profili e account** selezionare l'opzione **Gestione sicurezza profilo** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="96ef3-133">On the **Manage Profiles and Accounts** page, select **Manage profile security** option and click **Next**.</span></span>  
  
    -   <span data-ttu-id="96ef3-134">Nella scheda **Profili pubblici** selezionare la casella di controllo per il profilo che si desidera configurare e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="96ef3-134">In the **Public Profiles** tab, select the check box for the profile you would like to configure and click **Next**.</span></span>  
  
    -   <span data-ttu-id="96ef3-135">Per completare la configurazione del profilo, rivedere le azioni da eseguire nella pagina **Completamento procedura guidata** quindi fare clic su **Fine** .</span><span class="sxs-lookup"><span data-stu-id="96ef3-135">On the **Complete the Wizard** page, review the actions to be performed and click **Finish** to complete configuring the profile.</span></span>  
  

  
## <a name="using-transact-sql"></a><span data-ttu-id="96ef3-136">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="96ef3-136">Using Transact-SQL</span></span>  
  
###  <a name="to-create-a-database-mail-private-profile"></a><a name="PrivateProfile"></a> <span data-ttu-id="96ef3-137">Per creare un profilo privato di Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="96ef3-137">To Create a Database Mail private profile</span></span>  
  
-   <span data-ttu-id="96ef3-138">Connettersi all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="96ef3-138">Connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="96ef3-139">Per creare un nuovo profilo, eseguire la stored procedure di sistema [sysmail_add_profile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profile-sp-transact-sql) come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="96ef3-139">To create a new profile, run the system stored procedure [sysmail_add_profile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profile-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="96ef3-140">**EXECUTEmsdb.dbo.sysmail_add_profile_sp**</span><span class="sxs-lookup"><span data-stu-id="96ef3-140">**EXECUTEmsdb.dbo.sysmail_add_profile_sp**</span></span>  
  
     <span data-ttu-id="96ef3-141">*@profile_name*='*Nome profilo*'</span><span class="sxs-lookup"><span data-stu-id="96ef3-141">*@profile_name* = '*Profile Name*'</span></span>  
  
     <span data-ttu-id="96ef3-142">*@description*='*Descrizione*'</span><span class="sxs-lookup"><span data-stu-id="96ef3-142">*@description* = '*Desciption*'</span></span>  
  
     <span data-ttu-id="96ef3-143">dove *@profile_name* è il nome del profilo e *@description* è la descrizione del profilo.</span><span class="sxs-lookup"><span data-stu-id="96ef3-143">where *@profile_name* is the name of the profile, and *@description* is the description of the profile.</span></span> <span data-ttu-id="96ef3-144">Questo parametro è facoltativo e,</span><span class="sxs-lookup"><span data-stu-id="96ef3-144">This parameter is optional.</span></span>  
  
-   <span data-ttu-id="96ef3-145">Per ogni account, eseguire la stored procedure [sysmail_add_profileaccount_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profileaccount-sp-transact-sql) come descritto di seguito:</span><span class="sxs-lookup"><span data-stu-id="96ef3-145">For each account, run the stored procedure [sysmail_add_profileaccount_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profileaccount-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="96ef3-146">**EXECUTEmsdb.dbo.sysmail_add_profileaccount_sp**</span><span class="sxs-lookup"><span data-stu-id="96ef3-146">**EXECUTEmsdb.dbo.sysmail_add_profileaccount_sp**</span></span>  
  
     <span data-ttu-id="96ef3-147">*@profile_name*='*Nome del profilo*'</span><span class="sxs-lookup"><span data-stu-id="96ef3-147">*@profile_name* = '*Name of the profile*'</span></span>  
  
     <span data-ttu-id="96ef3-148">*@account_name*='*Nome dell'account*'</span><span class="sxs-lookup"><span data-stu-id="96ef3-148">*@account_name* = '*Name of the account*'</span></span>  
  
     <span data-ttu-id="96ef3-149">*@sequence_number*='*numero di sequenza dell'account all'interno del profilo.*</span><span class="sxs-lookup"><span data-stu-id="96ef3-149">*@sequence_number* = '*sequence number of the account within the profile.*</span></span> <span data-ttu-id="96ef3-150">'</span><span class="sxs-lookup"><span data-stu-id="96ef3-150">'</span></span>  
  
     <span data-ttu-id="96ef3-151">dove *@profile_name* è il nome del profilo e *@account_name* è il nome dell'account da aggiungere al profilo, *@sequence_number* determina l'ordine in cui gli account vengono usati nel profilo.</span><span class="sxs-lookup"><span data-stu-id="96ef3-151">where *@profile_name* is the name of the profile, and *@account_name* is the name of the account to add to the profile, *@sequence_number* determines the order in which the accounts are used in the profile.</span></span>  
  
-   <span data-ttu-id="96ef3-152">Concedere l'accesso al profilo a ogni utente o ruolo del database che invierà posta elettronica tramite questo profilo.</span><span class="sxs-lookup"><span data-stu-id="96ef3-152">For each database role or user that will send mail using this profile, grant access to the profile.</span></span> <span data-ttu-id="96ef3-153">A tale scopo, eseguire la stored procedure [sysmail_add_principalprofile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-principalprofile-sp-transact-sql) come descritto di seguito:</span><span class="sxs-lookup"><span data-stu-id="96ef3-153">To do this, run the stored procedure [sysmail_add_principalprofile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-principalprofile-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="96ef3-154">**EXECUTEmsdb.sysmail_add_principalprofile_sp**</span><span class="sxs-lookup"><span data-stu-id="96ef3-154">**EXECUTEmsdb.sysmail_add_principalprofile_sp**</span></span>  
  
     <span data-ttu-id="96ef3-155">*@profile_name*='*Nome del profilo*'</span><span class="sxs-lookup"><span data-stu-id="96ef3-155">*@profile_name* = '*Name of the profile*'</span></span>  
  
     <span data-ttu-id="96ef3-156">*@ principal_name* = '*Nome dell'utente del database o ruolo*'</span><span class="sxs-lookup"><span data-stu-id="96ef3-156">*@ principal_name* = '*Name of the database user or role*'</span></span>  
  
     <span data-ttu-id="96ef3-157">*@is_default*='*Stato del profilo predefinito* '</span><span class="sxs-lookup"><span data-stu-id="96ef3-157">*@is_default* = '*Default Profile status* '</span></span>  
  
     <span data-ttu-id="96ef3-158">dove *@profile_name* è il nome del profilo e *@principal_name* è il nome dell'utente o del ruolo del database, *@is_default* determina se il profilo è quello predefinito per l'utente o il ruolo del database.</span><span class="sxs-lookup"><span data-stu-id="96ef3-158">where *@profile_name* is the name of the profile, and *@principal_name* is the name of the database user or role, *@is_default* determines the whether this profile is the default for the database user or role.</span></span>  
  
 <span data-ttu-id="96ef3-159">Nell'esempio seguente vengono creati un account e un profilo privato di Posta elettronica database, viene quindi aggiunto l'account al profilo e viene concesso al ruolo del database **DBMailUsers** nel database **msdb** l'accesso al profilo.</span><span class="sxs-lookup"><span data-stu-id="96ef3-159">The following example creates a Database Mail account, creates a Database Mail private profile, then adds the account to the profile and grants access to the profile to the **DBMailUsers** database role in the **msdb** database.</span></span>  
  
```  
-- Create a Database Mail account  
EXECUTE msdb.dbo.sysmail_add_account_sp  
    @account_name = 'AdventureWorks Administrator',  
    @description = 'Mail account for administrative e-mail.',  
    @email_address = 'dba@Adventure-Works.com',  
    @replyto_address = 'danw@Adventure-Works.com',  
    @display_name = 'AdventureWorks Automated Mailer',  
    @mailserver_name = 'smtp.Adventure-Works.com' ;  
  
-- Create a Database Mail profile  
EXECUTE msdb.dbo.sysmail_add_profile_sp  
    @profile_name = 'AdventureWorks Administrator Profile',  
    @description = 'Profile used for administrative mail.' ;  
  
-- Add the account to the profile  
EXECUTE msdb.dbo.sysmail_add_profileaccount_sp  
    @profile_name = 'AdventureWorks Administrator Profile',  
    @account_name = 'AdventureWorks Administrator',  
    @sequence_number =1 ;  
  
-- Grant access to the profile to the DBMailUsers role  
EXECUTE msdb.dbo.sysmail_add_principalprofile_sp  
    @profile_name = 'AdventureWorks Administrator Profile',  
    @principal_name = 'ApplicationUser',  
    @is_default = 1 ;  
```  
  
 
  
###  <a name="to-create-a-database-mail-public-profile"></a><a name="PublicProfile"></a> <span data-ttu-id="96ef3-160">Per creare un profilo pubblica di Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="96ef3-160">To Create a Database Mail public profile</span></span>  
  
-   <span data-ttu-id="96ef3-161">Connettersi all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="96ef3-161">Connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="96ef3-162">Per creare un nuovo profilo, eseguire la stored procedure di sistema [sysmail_add_profile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profile-sp-transact-sql) come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="96ef3-162">To create a new profile, run the system stored procedure [sysmail_add_profile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profile-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="96ef3-163">**EXECUTEmsdb.dbo.sysmail_add_profile_sp**</span><span class="sxs-lookup"><span data-stu-id="96ef3-163">**EXECUTEmsdb.dbo.sysmail_add_profile_sp**</span></span>  
  
     <span data-ttu-id="96ef3-164">*@profile_name*='*Nome profilo*'</span><span class="sxs-lookup"><span data-stu-id="96ef3-164">*@profile_name* = '*Profile Name*'</span></span>  
  
     <span data-ttu-id="96ef3-165">*@description*='*Descrizione*'</span><span class="sxs-lookup"><span data-stu-id="96ef3-165">*@description* = '*Desciption*'</span></span>  
  
     <span data-ttu-id="96ef3-166">dove *@profile_name* è il nome del profilo e *@description* è la descrizione del profilo.</span><span class="sxs-lookup"><span data-stu-id="96ef3-166">where *@profile_name* is the name of the profile, and *@description* is the description of the profile.</span></span> <span data-ttu-id="96ef3-167">Questo parametro è facoltativo e,</span><span class="sxs-lookup"><span data-stu-id="96ef3-167">This parameter is optional.</span></span>  
  
-   <span data-ttu-id="96ef3-168">Per ogni account, eseguire la stored procedure [sysmail_add_profileaccount_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profileaccount-sp-transact-sql) come descritto di seguito:</span><span class="sxs-lookup"><span data-stu-id="96ef3-168">For each account, run the stored procedure [sysmail_add_profileaccount_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profileaccount-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="96ef3-169">**EXECUTEmsdb.dbo.sysmail_add_profileaccount_sp**</span><span class="sxs-lookup"><span data-stu-id="96ef3-169">**EXECUTEmsdb.dbo.sysmail_add_profileaccount_sp**</span></span>  
  
     <span data-ttu-id="96ef3-170">*@profile_name*='*Nome del profilo*'</span><span class="sxs-lookup"><span data-stu-id="96ef3-170">*@profile_name* = '*Name of the profile*'</span></span>  
  
     <span data-ttu-id="96ef3-171">*@account_name*='*Nome dell'account*'</span><span class="sxs-lookup"><span data-stu-id="96ef3-171">*@account_name* = '*Name of the account*'</span></span>  
  
     <span data-ttu-id="96ef3-172">*@sequence_number*='*numero di sequenza dell'account all'interno del profilo.*</span><span class="sxs-lookup"><span data-stu-id="96ef3-172">*@sequence_number* = '*sequence number of the account within the profile.*</span></span> <span data-ttu-id="96ef3-173">'</span><span class="sxs-lookup"><span data-stu-id="96ef3-173">'</span></span>  
  
     <span data-ttu-id="96ef3-174">dove *@profile_name* è il nome del profilo e *@account_name* è il nome dell'account da aggiungere al profilo, *@sequence_number* determina l'ordine in cui gli account vengono usati nel profilo.</span><span class="sxs-lookup"><span data-stu-id="96ef3-174">where *@profile_name* is the name of the profile, and *@account_name* is the name of the account to add to the profile, *@sequence_number* determines the order in which the accounts are used in the profile.</span></span>  
  
-   <span data-ttu-id="96ef3-175">Per dare accesso, eseguire la stored procedure [sysmail_add_principalprofile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-principalprofile-sp-transact-sql) come descritto di seguito:</span><span class="sxs-lookup"><span data-stu-id="96ef3-175">To grant public access, run the stored procedure [sysmail_add_principalprofile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-principalprofile-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="96ef3-176">**EXECUTEmsdb.sysmail_add_principalprofile_sp**</span><span class="sxs-lookup"><span data-stu-id="96ef3-176">**EXECUTEmsdb.sysmail_add_principalprofile_sp**</span></span>  
  
     <span data-ttu-id="96ef3-177">*@profile_name*='*Nome del profilo*'</span><span class="sxs-lookup"><span data-stu-id="96ef3-177">*@profile_name* = '*Name of the profile*'</span></span>  
  
     <span data-ttu-id="96ef3-178">*@ principal_name* = '**pubblico** o **0**'</span><span class="sxs-lookup"><span data-stu-id="96ef3-178">*@ principal_name* = '**public** or **0**'</span></span>  
  
     <span data-ttu-id="96ef3-179">*@is_default*='*Stato del profilo predefinito* '</span><span class="sxs-lookup"><span data-stu-id="96ef3-179">*@is_default* = '*Default Profile status* '</span></span>  
  
     <span data-ttu-id="96ef3-180">dove *@profile_name* è il nome del profilo e *@principal_name* per indicare che si tratta di un profilo pubblico, *@is_default* determina se il profilo è l'impostazione predefinita per l'utente o il ruolo del database.</span><span class="sxs-lookup"><span data-stu-id="96ef3-180">where *@profile_name* is the name of the profile, and *@principal_name* to indicate this is a public profile, *@is_default* determines the whether this profile is the default for the database user or role.</span></span>  
  
 <span data-ttu-id="96ef3-181">Nell'esempio seguente vengono creati un account e un profilo privato di Posta elettronica database, quindi viene aggiunto l'account al profilo e viene concesso l'accesso pubblico al profilo.</span><span class="sxs-lookup"><span data-stu-id="96ef3-181">The following example creates a Database Mail account, creates a Database Mail private profile, then adds the account to the profile and grants public access to the profile.</span></span>  
  
```  
-- Create a Database Mail account  
  
EXECUTE msdb.dbo.sysmail_add_account_sp  
    @account_name = 'AdventureWorks Public Account',  
    @description = 'Mail account for use by all database users.',  
    @email_address = 'db_users@Adventure-Works.com',  
    @replyto_address = 'danw@Adventure-Works.com',  
    @display_name = 'AdventureWorks Automated Mailer',  
    @mailserver_name = 'smtp.Adventure-Works.com' ;  
  
-- Create a Database Mail profile  
  
EXECUTE msdb.dbo.sysmail_add_profile_sp  
    @profile_name = 'AdventureWorks Public Profile',  
    @description = 'Profile used for administrative mail.' ;  
  
-- Add the account to the profile  
  
EXECUTE msdb.dbo.sysmail_add_profileaccount_sp  
    @profile_name = 'AdventureWorks Public Profile',  
    @account_name = 'AdventureWorks Public Account',  
    @sequence_number =1 ;  
  
-- Grant access to the profile to all users in the msdb database  
  
EXECUTE msdb.dbo.sysmail_add_principalprofile_sp  
    @profile_name = 'AdventureWorks Public Profile',  
    @principal_name = 'public',  
    @is_default = 1 ;  
```  
  

  
  
