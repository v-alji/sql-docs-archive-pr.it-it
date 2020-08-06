---
title: Creare un controllo del server e una specifica del controllo del database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqlaudit.dbaudit.general.f1
helpviewer_keywords:
- audits [SQL Server], creating database specification
- database audit [SQL Server]
ms.assetid: 26ee85de-6e97-4318-b526-900924d96e62
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 0cad01eae45d534f0f74911ce8f57827858cc920
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716199"
---
# <a name="create-a-server-audit-and-database-audit-specification"></a><span data-ttu-id="deaf5-102">Creazione di un controllo del server e di una specifica del controllo del database</span><span class="sxs-lookup"><span data-stu-id="deaf5-102">Create a Server Audit and Database Audit Specification</span></span>
  <span data-ttu-id="deaf5-103">In questo argomento viene illustrato come creare un controllo del server e la specifica di un controllo del database in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="deaf5-103">This topic describes how to create a server audit and database audit specification in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="deaf5-104">Il*controllo* di un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o di un database di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] comporta il rilevamento e la registrazione di eventi che si verificano nel sistema.</span><span class="sxs-lookup"><span data-stu-id="deaf5-104">*Auditing* an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database involves tracking and logging events that occur on the system.</span></span> <span data-ttu-id="deaf5-105">L'oggetto *SQL Server Audit* raccoglie un'unica istanza di azioni a livello di server o di database e gruppi di azioni da monitorare.</span><span class="sxs-lookup"><span data-stu-id="deaf5-105">The *SQL Server Audit* object collects a single instance of server- or database-level actions and groups of actions to monitor.</span></span> <span data-ttu-id="deaf5-106">Il controllo si trova a livello dell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="deaf5-106">The audit is at the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance level.</span></span> <span data-ttu-id="deaf5-107">Per ogni istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] è possibile disporre di più controlli.</span><span class="sxs-lookup"><span data-stu-id="deaf5-107">You can have multiple audits per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="deaf5-108">Anche l'oggetto *Database-Level Audit Specification* fa parte di un controllo.</span><span class="sxs-lookup"><span data-stu-id="deaf5-108">The *Database-Level Audit Specification* object belongs to an audit.</span></span> <span data-ttu-id="deaf5-109">È possibile creare una specifica del controllo del database per ogni database di SQL Server e per ogni controllo.</span><span class="sxs-lookup"><span data-stu-id="deaf5-109">You can create one database audit specification per SQL Server database per audit.</span></span> <span data-ttu-id="deaf5-110">Per altre informazioni, vedere [SQL Server Audit &#40;Motore di database&#41;](sql-server-audit-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="deaf5-110">For more information, see [SQL Server Audit &#40;Database Engine&#41;](sql-server-audit-database-engine.md).</span></span>  
  
 <span data-ttu-id="deaf5-111">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="deaf5-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="deaf5-112">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="deaf5-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="deaf5-113">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="deaf5-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="deaf5-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="deaf5-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="deaf5-115">**Per creare un controllo del server e una specifica del controllo del database utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="deaf5-115">**To create a server audit and database audit specification, using:**</span></span>  
  
     [<span data-ttu-id="deaf5-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="deaf5-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="deaf5-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="deaf5-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="deaf5-118">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="deaf5-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="deaf5-119">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="deaf5-119">Limitations and Restrictions</span></span>  
 <span data-ttu-id="deaf5-120">Le specifiche del controllo del database sono oggetti non a sicurezza diretta che risiedono in un database specifico.</span><span class="sxs-lookup"><span data-stu-id="deaf5-120">Database audit specifications are non-securable objects that reside in a given database.</span></span> <span data-ttu-id="deaf5-121">Quando una specifica del controllo del database viene creata, il relativo stato è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="deaf5-121">When a database audit specification is created, it is in a disabled state.</span></span>  
  
 <span data-ttu-id="deaf5-122">Durante la creazione o la modifica di una specifica di controllo in un database utente, non includere azioni di controllo su oggetti con ambito server, come le viste di sistema.</span><span class="sxs-lookup"><span data-stu-id="deaf5-122">When you are creating or modifying a database audit specification in a user database, do not include audit actions on server-scope objects, such as the system views.</span></span> <span data-ttu-id="deaf5-123">Se si includono oggetti con ambito server, verrà creato il controllo,</span><span class="sxs-lookup"><span data-stu-id="deaf5-123">If server-scoped objects are included, the audit will be created.</span></span> <span data-ttu-id="deaf5-124">ma gli oggetti con ambito server non saranno inclusi e non verranno restituiti errori.</span><span class="sxs-lookup"><span data-stu-id="deaf5-124">However, the server-scoped objects will not be included, and no error will be returned.</span></span> <span data-ttu-id="deaf5-125">Per eseguire il controllo degli oggetti con ambito server, utilizzare una specifica di controllo database nel database master.</span><span class="sxs-lookup"><span data-stu-id="deaf5-125">To audit server-scope objects, use a database audit specification in the master database.</span></span>  
  
 <span data-ttu-id="deaf5-126">Le specifiche di controllo del database risiedono nel database dove sono create, ad eccezione del database di sistema `tempdb`.</span><span class="sxs-lookup"><span data-stu-id="deaf5-126">Database audit specifications reside in the database where they are created, with the exception of the `tempdb` system database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="deaf5-127">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="deaf5-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="deaf5-128">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="deaf5-128">Permissions</span></span>  
  
-   <span data-ttu-id="deaf5-129">Gli utenti che dispongono dell'autorizzazione ALTER ANY DATABASE AUDIT possono creare specifiche del controllo del database e associarle a qualsiasi controllo.</span><span class="sxs-lookup"><span data-stu-id="deaf5-129">Users with the ALTER ANY DATABASE AUDIT permission can create database audit specifications and bind them to any audit.</span></span>  
  
-   <span data-ttu-id="deaf5-130">Dopo essere stata creata, la specifica di controllo del database può essere visualizzata dalle entità che dispongono delle autorizzazioni CONTROL SERVER, ALTER ANY DATABASE AUDIT o dell'account sysadmin.</span><span class="sxs-lookup"><span data-stu-id="deaf5-130">After a database audit specification is created, it can be viewed by principals with the CONTROL SERVER,  ALTER ANY DATABASE AUDIT permissions, or the sysadmin account.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="deaf5-131">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="deaf5-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-server-audit"></a><span data-ttu-id="deaf5-132">Per creare un controllo del server</span><span class="sxs-lookup"><span data-stu-id="deaf5-132">To create a server audit</span></span>  
  
1.  <span data-ttu-id="deaf5-133">In Esplora oggetti espandere la cartella **Sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="deaf5-133">In Object Explorer, expand the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="deaf5-134">Fare clic con il pulsante destro del mouse sulla cartella **controlli** e scegliere **nuovo controllo.**... Per altre informazioni, vedere [creare un controllo del server e una specifica del controllo del server](create-a-server-audit-and-server-audit-specification.md).</span><span class="sxs-lookup"><span data-stu-id="deaf5-134">Right-click the **Audits** folder and select **New Audit...**. For more information, see [Create a Server Audit and Server Audit Specification](create-a-server-audit-and-server-audit-specification.md).</span></span>  
  
3.  <span data-ttu-id="deaf5-135">Una volta selezionate le opzioni, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="deaf5-135">When you are finished selecting options, click **OK**.</span></span>  
  
#### <a name="to-create-a-database-level-audit-specification"></a><span data-ttu-id="deaf5-136">Per creare una specifica del controllo a livello di database</span><span class="sxs-lookup"><span data-stu-id="deaf5-136">To create a database-level audit specification</span></span>  
  
1.  <span data-ttu-id="deaf5-137">In Esplora oggetti espandere il database in cui si desidera creare una nuova specifica del controllo.</span><span class="sxs-lookup"><span data-stu-id="deaf5-137">In Object Explorer, expand the database where you want to create an audit specification.</span></span>  
  
2.  <span data-ttu-id="deaf5-138">Espandere la cartella **Sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="deaf5-138">Expand the **Security** folder.</span></span>  
  
3.  <span data-ttu-id="deaf5-139">Fare clic con il pulsante destro del mouse sulla cartella **Specifiche controllo** database e selezionare **nuova specifica controllo database...**.</span><span class="sxs-lookup"><span data-stu-id="deaf5-139">Right-click the **Database Audit Specifications** folder and select **New Database Audit Specification...**.</span></span>  
  
     <span data-ttu-id="deaf5-140">Nella finestra di dialogo **Crea specifica controllo database** sono disponibili le opzioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="deaf5-140">The following options are available on the **Create Database Audit Specification** dialog box.</span></span>  
  
     <span data-ttu-id="deaf5-141">**Nome**</span><span class="sxs-lookup"><span data-stu-id="deaf5-141">**Name**</span></span>  
     <span data-ttu-id="deaf5-142">Nome della specifica del controllo del database.</span><span class="sxs-lookup"><span data-stu-id="deaf5-142">The name of the database audit specification.</span></span> <span data-ttu-id="deaf5-143">Tale nome viene generato automaticamente quando si crea una nuova specifica del controllo del server, ma è modificabile.</span><span class="sxs-lookup"><span data-stu-id="deaf5-143">This is generated automatically when you create a new server audit specification but is editable.</span></span>  
  
     <span data-ttu-id="deaf5-144">**Controllo**</span><span class="sxs-lookup"><span data-stu-id="deaf5-144">**Audit**</span></span>  
     <span data-ttu-id="deaf5-145">Nome di un controllo del database esistente.</span><span class="sxs-lookup"><span data-stu-id="deaf5-145">The name of an existing database audit.</span></span> <span data-ttu-id="deaf5-146">Digitare il nome del controllo o selezionarlo nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="deaf5-146">Either type in the name of the audit or select it from the list.</span></span>  
  
     <span data-ttu-id="deaf5-147">**Tipo di azione di controllo**</span><span class="sxs-lookup"><span data-stu-id="deaf5-147">**Audit Action Type**</span></span>  
     <span data-ttu-id="deaf5-148">Specifica i gruppi di azioni di controllo a livello di database e le azioni di controllo da acquisire.</span><span class="sxs-lookup"><span data-stu-id="deaf5-148">Specifies the database-level audit action groups and audit actions to capture.</span></span> <span data-ttu-id="deaf5-149">Per l'elenco di gruppi di azioni di controllo a livello di database e di azioni di controllo e una descrizione degli eventi contenuti, vedere [Azioni e gruppi di azioni di SQL Server Audit](sql-server-audit-action-groups-and-actions.md).</span><span class="sxs-lookup"><span data-stu-id="deaf5-149">For the list of database-level audit action groups and audit actions and a description of the events they contain, see [SQL Server Audit Action Groups and Actions](sql-server-audit-action-groups-and-actions.md).</span></span>  
  
     <span data-ttu-id="deaf5-150">**Schema dell'oggetto**</span><span class="sxs-lookup"><span data-stu-id="deaf5-150">**Object Schema**</span></span>  
     <span data-ttu-id="deaf5-151">Consente di visualizzare lo schema per il **nome oggetto**specificato.</span><span class="sxs-lookup"><span data-stu-id="deaf5-151">Displays the schema for the specified **Object Name**.</span></span>  
  
     <span data-ttu-id="deaf5-152">**nome oggetto**</span><span class="sxs-lookup"><span data-stu-id="deaf5-152">**Object Name**</span></span>  
     <span data-ttu-id="deaf5-153">Nome dell'oggetto da controllare.</span><span class="sxs-lookup"><span data-stu-id="deaf5-153">The name of the object to audit.</span></span> <span data-ttu-id="deaf5-154">Tale opzione è disponibile solo per le azioni di controllo e non si applica ai gruppi di controllo.</span><span class="sxs-lookup"><span data-stu-id="deaf5-154">This is only available for audit actions; it does not apply to audit groups.</span></span>  
  
     <span data-ttu-id="deaf5-155">**Puntini di sospensione (...)**</span><span class="sxs-lookup"><span data-stu-id="deaf5-155">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="deaf5-156">Consente di visualizzare la finestra di dialogo **Seleziona oggetti** per eseguire la ricerca e la selezione di un oggetto disponibile, in base all'opzione **Tipo di azione di controllo**.</span><span class="sxs-lookup"><span data-stu-id="deaf5-156">Opens the **Select Objects** dialog to browse for and select an available object, based on the specified **Audit Action Type**.</span></span>  
  
     <span data-ttu-id="deaf5-157">**Nome entità**</span><span class="sxs-lookup"><span data-stu-id="deaf5-157">**Principal Name**</span></span>  
     <span data-ttu-id="deaf5-158">Account per filtrare il controllo per l'oggetto da controllare.</span><span class="sxs-lookup"><span data-stu-id="deaf5-158">The account to filter the audit by for the object being audited.</span></span>  
  
     <span data-ttu-id="deaf5-159">**Puntini di sospensione (...)**</span><span class="sxs-lookup"><span data-stu-id="deaf5-159">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="deaf5-160">Viene visualizzata la finestra di dialogo **Seleziona oggetti** per eseguire la ricerca e selezionare un oggetto disponibile, in base all'opzione **Nome oggetto**specificata.</span><span class="sxs-lookup"><span data-stu-id="deaf5-160">Opens the **Select Objects** dialog to browse for and select an available object, based on the specified **Object Name**.</span></span>  
  
4.  <span data-ttu-id="deaf5-161">Una volta selezionate le opzioni, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="deaf5-161">When you are finished selecting option, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="deaf5-162">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="deaf5-162">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-server-audit"></a><span data-ttu-id="deaf5-163">Per creare un controllo del server</span><span class="sxs-lookup"><span data-stu-id="deaf5-163">To create a server audit</span></span>  
  
1.  <span data-ttu-id="deaf5-164">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="deaf5-164">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="deaf5-165">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="deaf5-165">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="deaf5-166">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="deaf5-166">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE master ;  
    GO  
    -- Create the server audit.   
    CREATE SERVER AUDIT Payrole_Security_Audit  
        TO FILE ( FILEPATH =   
    'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA' ) ;   
    GO  
    -- Enable the server audit.   
    ALTER SERVER AUDIT Payrole_Security_Audit   
    WITH (STATE = ON) ;  
    ```  
  
#### <a name="to-create-a-database-level-audit-specification"></a><span data-ttu-id="deaf5-167">Per creare una specifica del controllo a livello di database</span><span class="sxs-lookup"><span data-stu-id="deaf5-167">To create a database-level audit specification</span></span>  
  
1.  <span data-ttu-id="deaf5-168">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="deaf5-168">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="deaf5-169">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="deaf5-169">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="deaf5-170">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="deaf5-170">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="deaf5-171">Nell'esempio seguente viene creata una specifica del controllo del database denominata `Audit_Pay_Tables` che controlla le istruzioni SELECT e INSERT per l'utente `dbo` per la tabella `HumanResources.EmployeePayHistory` in base al controllo del server definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="deaf5-171">The example creates a database audit specification called `Audit_Pay_Tables` that audits SELECT and INSERT statements by the `dbo` user, for the `HumanResources.EmployeePayHistory` table based on the server audit defined above.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;   
    GO  
    -- Create the database audit specification.   
    CREATE DATABASE AUDIT SPECIFICATION Audit_Pay_Tables  
    FOR SERVER AUDIT Payrole_Security_Audit  
    ADD (SELECT , INSERT  
         ON HumanResources.EmployeePayHistory BY dbo )   
    WITH (STATE = ON) ;   
    GO  
  
    ```  
  
 <span data-ttu-id="deaf5-172">Per altre informazioni, vedere [CREATE SERVER AUDIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-transact-sql) e [CREATE DATABASE AUDIT SPECIFICATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-database-audit-specification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="deaf5-172">For more information, see [CREATE SERVER AUDIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-transact-sql) and [CREATE DATABASE AUDIT SPECIFICATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-database-audit-specification-transact-sql).</span></span>  
  
  
