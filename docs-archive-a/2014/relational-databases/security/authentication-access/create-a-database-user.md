---
title: Creazione di un utente di database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.DATABASEUSER.GENERAL.F1
- sql12.swb.user.securables.f1
helpviewer_keywords:
- database users, creating
- creating users with Management Studio
- mapping users
- users [SQL Server], creating
- database user additions [SQL Server]
- database users, mapping
- CREATE USER [Management Studio]
- users [SQL Server], adding
- mapping database users
ms.assetid: 782798d3-9552-4514-9f58-e87be4b264e4
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 97fc758c754f5fc8803e988d55147670fc3ff45b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714063"
---
# <a name="create-a-database-user"></a><span data-ttu-id="a14cf-102">Creazione di un utente di database</span><span class="sxs-lookup"><span data-stu-id="a14cf-102">Create a Database User</span></span>
  <span data-ttu-id="a14cf-103">In questo argomento viene descritto come creare un utente di database con mapping a un account di accesso in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a14cf-103">This topic describes how to create a database user mapped to a login in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="a14cf-104">L'utente del database è l'identità dell'account di accesso quando è connesso a un database.</span><span class="sxs-lookup"><span data-stu-id="a14cf-104">The database user is the identity of the login when it is connected to a database.</span></span> <span data-ttu-id="a14cf-105">Può utilizzare lo stesso nome dell'account, ma non si tratta di una condizione obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="a14cf-105">The database user can use the same name as the login, but that is not required.</span></span> <span data-ttu-id="a14cf-106">In questo argomento si presuppone che esista già un account di accesso in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a14cf-106">This topic assumes that a login already exists in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a14cf-107">Per informazioni su come creare un account di accesso, vedere [creare un account di accesso](create-a-login.md).</span><span class="sxs-lookup"><span data-stu-id="a14cf-107">For information about how to create a login, see [Create a Login](create-a-login.md).</span></span>  
  
 <span data-ttu-id="a14cf-108">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="a14cf-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a14cf-109">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="a14cf-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a14cf-110">Background</span><span class="sxs-lookup"><span data-stu-id="a14cf-110">Background</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a14cf-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a14cf-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a14cf-112">**Per creare un utente di database utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="a14cf-112">**To create a database user, using:**</span></span>  
  
     [<span data-ttu-id="a14cf-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a14cf-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a14cf-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a14cf-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a14cf-115">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="a14cf-115">Before You Begin</span></span>  
  
###  <a name="background"></a><a name="Restrictions"></a> <span data-ttu-id="a14cf-116">Background</span><span class="sxs-lookup"><span data-stu-id="a14cf-116">Background</span></span>  
 <span data-ttu-id="a14cf-117">Un utente è un'entità di sicurezza a livello di database.</span><span class="sxs-lookup"><span data-stu-id="a14cf-117">A user is a database level security principal.</span></span> <span data-ttu-id="a14cf-118">Affinché gli account di accesso possano eseguire la connessione al database, è necessario eseguirne il mapping a un utente di database.</span><span class="sxs-lookup"><span data-stu-id="a14cf-118">Logins must be mapped to a database user to connect to a database.</span></span> <span data-ttu-id="a14cf-119">È possibile eseguire il mapping di un account di accesso a database diversi come utenti diversi, ma come un singolo utente per ogni database.</span><span class="sxs-lookup"><span data-stu-id="a14cf-119">A login can be mapped to different databases as different users but can only be mapped as one user in each database.</span></span> <span data-ttu-id="a14cf-120">In un database parzialmente indipendente, può essere creato un utente che non dispone di un account di accesso.</span><span class="sxs-lookup"><span data-stu-id="a14cf-120">In a partially contained database, a user can be created that does not have a login.</span></span> <span data-ttu-id="a14cf-121">Per altre informazioni sugli utenti di database indipendenti, vedere [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a14cf-121">For more information about contained database users, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span> <span data-ttu-id="a14cf-122">Se è abilitato l'utente guest in un database, un account di accesso di cui non è stato eseguito il mapping a un utente del database può accedere al database come utente guest.</span><span class="sxs-lookup"><span data-stu-id="a14cf-122">If the guest user in a database is enabled, a login that is not mapped to a database user can enter the database as the guest user.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a14cf-123">L'utente guest è in genere disabilitato.</span><span class="sxs-lookup"><span data-stu-id="a14cf-123">The guest user is ordinarily disabled.</span></span> <span data-ttu-id="a14cf-124">Non abilitarlo, a meno che non sia strettamente necessario.</span><span class="sxs-lookup"><span data-stu-id="a14cf-124">Do not enable the guest user unless it is necessary.</span></span>  
  
 <span data-ttu-id="a14cf-125">È possibile concedere autorizzazioni agli utenti, in quanto entità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a14cf-125">As a security principal, permissions can be granted to users.</span></span> <span data-ttu-id="a14cf-126">L'ambito di un utente è il database.</span><span class="sxs-lookup"><span data-stu-id="a14cf-126">The scope of a user is the database.</span></span> <span data-ttu-id="a14cf-127">Affinché un account di accesso possa eseguire la connessione a un database specifico nell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], è necessario eseguirne il mapping a un utente del database.</span><span class="sxs-lookup"><span data-stu-id="a14cf-127">To connect to a specific database on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], a login must be mapped to a database user.</span></span> <span data-ttu-id="a14cf-128">Le autorizzazioni all'interno del database vengono concesse e negate all'utente del database, non all'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="a14cf-128">Permissions inside the database are granted and denied to the database user, not the login.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a14cf-129">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a14cf-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a14cf-130">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="a14cf-130">Permissions</span></span>  
 <span data-ttu-id="a14cf-131">È richiesta l'autorizzazione `ALTER ANY USER` per il database.</span><span class="sxs-lookup"><span data-stu-id="a14cf-131">Requires `ALTER ANY USER` permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a14cf-132">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a14cf-132">Using SQL Server Management Studio</span></span>  
  
##### <a name="to-create-a-database-user"></a><span data-ttu-id="a14cf-133">Per creare un utente del database</span><span class="sxs-lookup"><span data-stu-id="a14cf-133">To create a database user</span></span>  
  
1.  <span data-ttu-id="a14cf-134">In Esplora oggetti espandere la cartella **Database** .</span><span class="sxs-lookup"><span data-stu-id="a14cf-134">In Object Explorer, expand the **Databases** folder.</span></span>  
  
2.  <span data-ttu-id="a14cf-135">Espandere il database in cui si desidera creare il nuovo utente del database.</span><span class="sxs-lookup"><span data-stu-id="a14cf-135">Expand the database in which to create the new database user.</span></span>  
  
3.  <span data-ttu-id="a14cf-136">Fare clic con il pulsante destro del mouse sulla cartella **Sicurezza**, scegliere **Nuovo** e quindi **Utente...** .</span><span class="sxs-lookup"><span data-stu-id="a14cf-136">Right-click the **Security** folder, point to **New**, and select **User...**.</span></span>  
  
4.  <span data-ttu-id="a14cf-137">Nella finestra di dialogo **utente database-nuovo** , nella pagina **generale** , selezionare uno dei seguenti tipi di utente nell'elenco **tipo di utente** : **utente SQL con account di accesso**, **utente SQL senza account di accesso**, **utente mappato a un certificato**, **utente mappato a una chiave asimmetrica**o **utente di Windows**.</span><span class="sxs-lookup"><span data-stu-id="a14cf-137">In the **Database User - New** dialog box, on the **General** page, select one of the following user types from the **User type** list: **SQL user with login**, **SQL user without login**, **User mapped to a certificate**, **User mapped to an asymmetric key**, or **Windows user**.</span></span>  
  
5.  <span data-ttu-id="a14cf-138">Immettere un nome per il nuovo utente nella casella **Nuovo utente** .</span><span class="sxs-lookup"><span data-stu-id="a14cf-138">In the **User name** box, enter a name for the new user.</span></span> <span data-ttu-id="a14cf-139">Se si è scelto **Utente di Windows** nell'elenco **Tipo utente**, è anche possibile fare clic sui puntini di sospensione **(...)** per aprire la finestra di dialogo **Seleziona utente o gruppo**.</span><span class="sxs-lookup"><span data-stu-id="a14cf-139">If you have chosen **Windows user** from the **User type** list, you can also click the ellipsis **(...)** to open the **Select User or Group** dialog box.</span></span>  
  
6.  <span data-ttu-id="a14cf-140">Nella casella **Nome account di accesso** immettere l'account di accesso per l'utente.</span><span class="sxs-lookup"><span data-stu-id="a14cf-140">In the **Login name** box, enter the login for the user.</span></span> <span data-ttu-id="a14cf-141">In alternativa, fare clic sui puntini di sospensione **(...)** per aprire la finestra di dialogo **Seleziona account di accesso**.</span><span class="sxs-lookup"><span data-stu-id="a14cf-141">Alternately, click the ellipsis **(...)** to open the **Select Login** dialog box.</span></span> <span data-ttu-id="a14cf-142">È disponibile**Nome account di accesso** se si seleziona **Utente SQL con account di accesso** o **Utente di Windows** dall'elenco **Tipo di utente** .</span><span class="sxs-lookup"><span data-stu-id="a14cf-142">**Login name** is available if you select either **SQL user with login** or **Windows user** from the **User type** list.</span></span>  
  
7.  <span data-ttu-id="a14cf-143">Nella casella **Schema predefinito** è specificato lo schema che diventerà proprietario degli oggetti creati da questo utente.</span><span class="sxs-lookup"><span data-stu-id="a14cf-143">In the **Default schema** box, specifies the schema that will own objects created by this user.</span></span> <span data-ttu-id="a14cf-144">In alternativa, fare clic sui puntini di sospensione **(...)** per aprire la finestra di dialogo **Seleziona schema**.</span><span class="sxs-lookup"><span data-stu-id="a14cf-144">Alternately, click the ellipsis **(...)** to open the **Select Schema** dialog box.</span></span> <span data-ttu-id="a14cf-145">È disponibile**Schema predefinito** se si seleziona **Utente SQL con account di accesso**, **Utente SQL senza account di accesso**o **Utente di Windows** nell'elenco **Tipo di utente** .</span><span class="sxs-lookup"><span data-stu-id="a14cf-145">**Default schema** is available if you select either **SQL user with login**, **SQL user without login**, or **Windows user** from the **User type** list.</span></span>  
  
8.  <span data-ttu-id="a14cf-146">Nella casella **Nome certificato** , immettere il certificato da utilizzare per l'utente del database.</span><span class="sxs-lookup"><span data-stu-id="a14cf-146">In the **Certificate name** box, enter the certificate to be used for the database user.</span></span> <span data-ttu-id="a14cf-147">In alternativa, fare clic sui puntini di sospensione **(...)** per aprire la finestra di dialogo **Seleziona certificato**.</span><span class="sxs-lookup"><span data-stu-id="a14cf-147">Alternately, click the ellipsis **(...)** to open the **Select Certificate** dialog box.</span></span> <span data-ttu-id="a14cf-148">È disponibile**Nome certificato** se si seleziona **Utente con mapping eseguito a un certificato** dall'elenco **Tipo di utente** .</span><span class="sxs-lookup"><span data-stu-id="a14cf-148">**Certificate name** is available if you select **User mapped to a certificate** from the **User type** list.</span></span>  
  
9. <span data-ttu-id="a14cf-149">Nella casella **Nome chiave asimmetrica**  , immettere la chiave da usare per l'utente del database.</span><span class="sxs-lookup"><span data-stu-id="a14cf-149">In the **Asymmetric key name**  box, enter the key to be used for the database user.</span></span> <span data-ttu-id="a14cf-150">In alternativa, fare clic sui puntini di sospensione **(...)** per aprire la finestra di dialogo **Seleziona chiave asimmetrica**.</span><span class="sxs-lookup"><span data-stu-id="a14cf-150">Alternately, click the ellipsis **(...)** to open the **Select Asymmetric Key** dialog box.</span></span> <span data-ttu-id="a14cf-151">È disponibile**Nome chiave asimmetrica** se si seleziona **Utente con mapping eseguito a una chiave asimmetrica** dall'elenco **Tipo di utente** .</span><span class="sxs-lookup"><span data-stu-id="a14cf-151">**Asymmetric key name** is available if you select **User mapped to an asymmetric key** from the **User type** list.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="additional-options"></a><span data-ttu-id="a14cf-152">Opzioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a14cf-152">Additional Options</span></span>  
 <span data-ttu-id="a14cf-153">Nella finestra di dialogo **Utente di database - Nuovo** sono disponibili opzioni anche in altre quattro pagine: **Schemi di proprietà**, **Appartenenza**, **Entità a protezione diretta** e **Proprietà estese**.</span><span class="sxs-lookup"><span data-stu-id="a14cf-153">The **Database User - New** dialog box also offers options on four additional pages: **Owned Schemas**, **Membership**, **Securables**, and **Extended Properties**.</span></span>  
  
-   <span data-ttu-id="a14cf-154">Nella pagina **Schemi di proprietà** sono elencati tutti i possibili schemi che possono essere di proprietà del nuovo utente del database.</span><span class="sxs-lookup"><span data-stu-id="a14cf-154">The **Owned Schemas** page lists all possible schemas that can be owned by the new database user.</span></span> <span data-ttu-id="a14cf-155">Per aggiungere schemi o rimuoverli da un utente del database, in **Schemi di proprietà di questo utente**selezionare o deselezionare le caselle di controllo accanto agli schemi.</span><span class="sxs-lookup"><span data-stu-id="a14cf-155">To add schemas to or remove them from a database user, under **Schemas owned by this user**, select or clear the check boxes next to the schemas.</span></span>  
  
-   <span data-ttu-id="a14cf-156">Nella pagina **Appartenenza** sono elencati tutti i possibili ruoli di appartenenza al database che possono essere di proprietà del nuovo utente del database.</span><span class="sxs-lookup"><span data-stu-id="a14cf-156">The **Membership** page lists all possible database membership roles that can be owned by the new database user.</span></span> <span data-ttu-id="a14cf-157">Per aggiungere ruoli o rimuoverli da un utente del database, in **Appartenenza a ruoli del database**selezionare o deselezionare le caselle di controllo accanto ai ruoli.</span><span class="sxs-lookup"><span data-stu-id="a14cf-157">To add roles to or remove them from a database user, under **Database role membership**, select or clear the check boxes next to the roles.</span></span>  
  
-   <span data-ttu-id="a14cf-158">Nella pagina **Entità a protezione diretta** sono elencate tutte le possibili entità a protezione diretta e le autorizzazioni su quelle entità a protezione diretta che possono essere concesse all'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="a14cf-158">The **Securables** page lists all possible securables and the permissions on those securables that can be granted to the login.</span></span>  
  
-   <span data-ttu-id="a14cf-159">La pagina **Proprietà estese** consente di aggiungere proprietà personalizzate a utenti di database.</span><span class="sxs-lookup"><span data-stu-id="a14cf-159">The **Extended properties** page allows you to add custom properties to database users.</span></span> <span data-ttu-id="a14cf-160">In questa pagina sono disponibili le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="a14cf-160">The following options are available on this page.</span></span>  
  
     <span data-ttu-id="a14cf-161">**Database**</span><span class="sxs-lookup"><span data-stu-id="a14cf-161">**Database**</span></span>  
     <span data-ttu-id="a14cf-162">Consente di visualizzare il nome del database selezionato.</span><span class="sxs-lookup"><span data-stu-id="a14cf-162">Displays the name of the selected database.</span></span> <span data-ttu-id="a14cf-163">Questo campo è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="a14cf-163">This field is read-only.</span></span>  
  
     <span data-ttu-id="a14cf-164">**Regole di confronto**</span><span class="sxs-lookup"><span data-stu-id="a14cf-164">**Collation**</span></span>  
     <span data-ttu-id="a14cf-165">Consente di visualizzare le regole di confronto utilizzate per il database selezionato.</span><span class="sxs-lookup"><span data-stu-id="a14cf-165">Displays the collation used for the selected database.</span></span> <span data-ttu-id="a14cf-166">Questo campo è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="a14cf-166">This field is read-only.</span></span>  
  
     <span data-ttu-id="a14cf-167">**Proprietà**</span><span class="sxs-lookup"><span data-stu-id="a14cf-167">**Properties**</span></span>  
     <span data-ttu-id="a14cf-168">Consente di visualizzare o specificare le proprietà estese relative all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="a14cf-168">View or specify the extended properties for the object.</span></span> <span data-ttu-id="a14cf-169">Ogni proprietà estesa è composta da una coppia nome/valore di metadati associati all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="a14cf-169">Each extended property consists of a name/value pair of metadata associated with the object.</span></span>  
  
     <span data-ttu-id="a14cf-170">**Puntini di sospensione (...)**</span><span class="sxs-lookup"><span data-stu-id="a14cf-170">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="a14cf-171">Fare clic sui puntini di sospensione **(…)** dopo **Valore** per visualizzare la finestra di dialogo **Valore per Proprietà estesa**.</span><span class="sxs-lookup"><span data-stu-id="a14cf-171">Click the ellipsis **(...)** after **Value** to open the **Value for Extended Property** dialog box.</span></span> <span data-ttu-id="a14cf-172">Digitare o visualizzare il valore della proprietà estesa in questa finestra di dimensioni maggiori.</span><span class="sxs-lookup"><span data-stu-id="a14cf-172">Type or view the value of the extended property in this larger location.</span></span> <span data-ttu-id="a14cf-173">Per ulteriori informazioni, vedere [Finestra di dialogo Valore per proprietà estesa](../../databases/value-for-extended-property-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="a14cf-173">For more information, see [Value for Extended Property Dialog Box](../../databases/value-for-extended-property-dialog-box.md).</span></span>  
  
     <span data-ttu-id="a14cf-174">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="a14cf-174">**Delete**</span></span>  
     <span data-ttu-id="a14cf-175">Consente di eliminare la proprietà estesa selezionata.</span><span class="sxs-lookup"><span data-stu-id="a14cf-175">Removes the selected extended property.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a14cf-176">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a14cf-176">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-database-user"></a><span data-ttu-id="a14cf-177">Per creare un utente del database</span><span class="sxs-lookup"><span data-stu-id="a14cf-177">To create a database user</span></span>  
  
1.  <span data-ttu-id="a14cf-178">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a14cf-178">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a14cf-179">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="a14cf-179">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a14cf-180">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="a14cf-180">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates the login AbolrousHazem with password '340$Uuxwp7Mcxo7Khy'.  
    CREATE LOGIN AbolrousHazem   
        WITH PASSWORD = '340$Uuxwp7Mcxo7Khy';  
    GO  
  
    -- Creates a database user for the login created above.  
    CREATE USER AbolrousHazem FOR LOGIN AbolrousHazem;  
    GO  
    ```  
  
 <span data-ttu-id="a14cf-181">Per altre informazioni, vedere [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a14cf-181">For more information, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a14cf-182">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a14cf-182">See Also</span></span>  
 [<span data-ttu-id="a14cf-183">Entità &#40;motore di database&#41;</span><span class="sxs-lookup"><span data-stu-id="a14cf-183">Principals &#40;Database Engine&#41;</span></span>](principals-database-engine.md)  
  
  
