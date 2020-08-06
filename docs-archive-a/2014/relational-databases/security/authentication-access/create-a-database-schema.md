---
title: Creare uno schema di database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.schemas.general.f1
helpviewer_keywords:
- creating schemas with Management Studio
- CREATE SCHEMA [Management Studio]
- database schemas
- schemas [SQL Server], creating
ms.assetid: ed2a5522-f4d2-4111-95a4-d3e1e5081739
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 3ac0c00768db6501c7d786c35758c1a9d75a5a7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714068"
---
# <a name="create-a-database-schema"></a><span data-ttu-id="e7751-102">Creazione di uno schema di database</span><span class="sxs-lookup"><span data-stu-id="e7751-102">Create a Database Schema</span></span>
  <span data-ttu-id="e7751-103">In questo argomento si illustra come creare uno schema in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7751-103">This topic describes how to create a schema in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="e7751-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="e7751-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e7751-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="e7751-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e7751-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="e7751-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e7751-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e7751-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e7751-108">**Per creare un schema mediante:**</span><span class="sxs-lookup"><span data-stu-id="e7751-108">**To create a schema, using:**</span></span>  
  
     [<span data-ttu-id="e7751-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e7751-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e7751-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e7751-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e7751-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e7751-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e7751-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="e7751-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="e7751-113">Il nuovo schema è di proprietà di una delle seguenti entità a livello di database: utente di database, ruolo di database o ruolo applicazione.</span><span class="sxs-lookup"><span data-stu-id="e7751-113">The new schema is owned by one of the following database-level principals: database user, database role, or application role.</span></span> <span data-ttu-id="e7751-114">Gli oggetti creati all'interno di uno schema appartengono al proprietario dello schema e hanno un valore NULL per **principal_id** in **sys.objects**.</span><span class="sxs-lookup"><span data-stu-id="e7751-114">Objects created within a schema are owned by the owner of the schema, and have a NULL **principal_id** in **sys.objects**.</span></span> <span data-ttu-id="e7751-115">La proprietà degli oggetti contenuti in uno schema può essere trasferita a qualsiasi entità a livello di database, ma il proprietario dello schema mantiene sempre l'autorizzazione CONTROL per gli oggetti all'interno dello schema.</span><span class="sxs-lookup"><span data-stu-id="e7751-115">Ownership of schema-contained objects can be transferred to any database-level principal, but the schema owner always retains CONTROL permission on objects within the schema.</span></span>  
  
-   <span data-ttu-id="e7751-116">Quando si crea un oggetto di database, se si specifica un'entità di dominio valida (utente o gruppo) come proprietario dell'oggetto, l'entità di dominio sarà aggiunta al database come uno schema.</span><span class="sxs-lookup"><span data-stu-id="e7751-116">When creating a database object, if you specify a valid domain principal (user or group) as the object owner, the domain principal will be added to the database as a schema.</span></span> <span data-ttu-id="e7751-117">Il proprietario del nuovo schema sarà l'entità di dominio.</span><span class="sxs-lookup"><span data-stu-id="e7751-117">The new schema will be owned by that domain principal.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e7751-118">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e7751-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e7751-119">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="e7751-119">Permissions</span></span>  
  
-   <span data-ttu-id="e7751-120">È richiesta l'autorizzazione CREATE SCHEMA per il database.</span><span class="sxs-lookup"><span data-stu-id="e7751-120">Requires CREATE SCHEMA permission on the database.</span></span>  
  
-   <span data-ttu-id="e7751-121">Per specificare un altro utente come proprietario dello schema che viene creato, l'utente deve disporre dell'autorizzazione IMPERSONATE per quell'utente.</span><span class="sxs-lookup"><span data-stu-id="e7751-121">To specify another user as the owner of the schema being created, the caller must have IMPERSONATE permission on that user.</span></span> <span data-ttu-id="e7751-122">Se si specifica un ruolo di database come proprietario, il chiamante deve disporre dell'appartenenza al ruolo oppure dell'autorizzazione ALTER per il ruolo.</span><span class="sxs-lookup"><span data-stu-id="e7751-122">If a database role is specified as the owner, the caller must have one of the following: membership in the role or ALTER permission on the role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e7751-123">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e7751-123">Using SQL Server Management Studio</span></span>  
  
##### <a name="to-create-a-schema"></a><span data-ttu-id="e7751-124">Per creare uno schema</span><span class="sxs-lookup"><span data-stu-id="e7751-124">To create a schema</span></span>  
  
1.  <span data-ttu-id="e7751-125">In Esplora oggetti espandere la cartella **Database** .</span><span class="sxs-lookup"><span data-stu-id="e7751-125">In Object Explorer, expand the **Databases** folder.</span></span>  
  
2.  <span data-ttu-id="e7751-126">Espandere il database in cui si desidera creare il nuovo schema di database.</span><span class="sxs-lookup"><span data-stu-id="e7751-126">Expand the database in which to create the new database schema.</span></span>  
  
3.  <span data-ttu-id="e7751-127">Fare clic con il pulsante destro del mouse sulla cartella **Sicurezza** , scegliere **Nuovo**, quindi selezionare **Schema**.</span><span class="sxs-lookup"><span data-stu-id="e7751-127">Right-click the **Security** folder, point to **New**, and select **Schema**.</span></span>  
  
4.  <span data-ttu-id="e7751-128">Nella finestra di dialogo **Schema - Nuovo** della pagina **Generale** immettere un nome per il nuovo schema nella casella **Nome schema** .</span><span class="sxs-lookup"><span data-stu-id="e7751-128">In the **Schema - New** dialog box, on the **General** page, enter a name for the new schema in the **Schema name** box.</span></span>  
  
5.  <span data-ttu-id="e7751-129">Nella casella **Proprietario schema** immettere il nome di un utente o ruolo del database proprietario dello schema.</span><span class="sxs-lookup"><span data-stu-id="e7751-129">In the **Schema owner** box, enter the name of a database user or role to own the schema.</span></span> <span data-ttu-id="e7751-130">In alternativa, fare clic su **Cerca** per aprire la finestra di dialogo **Cerca ruoli e utenti** .</span><span class="sxs-lookup"><span data-stu-id="e7751-130">Alternately, click **Search** to open the **Search Roles and Users** dialog box.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="additional-options"></a><span data-ttu-id="e7751-131">Opzioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="e7751-131">Additional Options</span></span>  
 <span data-ttu-id="e7751-132">La finestra di dialogo **Schema - Nuovo** offre anche opzioni in altre due pagine: **Autorizzazioni** e **Proprietà estese**.</span><span class="sxs-lookup"><span data-stu-id="e7751-132">The **Schema- New** dialog box also offers options on two additional pages: **Permissions** and **Extended Properties**.</span></span>  
  
-   <span data-ttu-id="e7751-133">Nella pagina **Autorizzazioni** sono elencate tutte le possibili entità a protezione diretta e le autorizzazioni su quelle entità a protezione diretta che possono essere concesse all'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="e7751-133">The **Permissions** page lists all possible securables and the permissions on those securables that can be granted to the login.</span></span>  
  
-   <span data-ttu-id="e7751-134">La pagina **Proprietà estese** consente di aggiungere proprietà personalizzate a utenti di database.</span><span class="sxs-lookup"><span data-stu-id="e7751-134">The **Extended properties** page allows you to add custom properties to database users.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e7751-135">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e7751-135">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-schema"></a><span data-ttu-id="e7751-136">Per creare uno schema</span><span class="sxs-lookup"><span data-stu-id="e7751-136">To create a schema</span></span>  
  
1.  <span data-ttu-id="e7751-137">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7751-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e7751-138">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="e7751-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e7751-139">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="e7751-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Creates the schema Sprockets owned by Annik that contains table NineProngs.   
    -- The statement grants SELECT to Mandar and denies SELECT to Prasanna.  
  
    CREATE SCHEMA Sprockets AUTHORIZATION Annik  
        CREATE TABLE NineProngs (source int, cost int, partnumber int)  
        GRANT SELECT ON SCHEMA::Sprockets TO Mandar  
        DENY SELECT ON SCHEMA::Sprockets TO Prasanna;  
    GO  
    ```  
  
 <span data-ttu-id="e7751-140">Per altre informazioni, vedere [CREATE SCHEMA &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-schema-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e7751-140">For more information, see [CREATE SCHEMA &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-schema-transact-sql).</span></span>  
  
  
