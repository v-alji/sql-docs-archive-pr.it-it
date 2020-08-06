---
title: Creare un ruolo applicazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.approle.general.f1
helpviewer_keywords:
- application roles [SQL Server], creating
ms.assetid: 6b8da1f5-3d8e-4f88-b111-b915788b06f1
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 51272dad57558cdb771f9b98a2f5e5b3da7609cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635993"
---
# <a name="create-an-application-role"></a><span data-ttu-id="c3cb7-102">Creazione di un ruolo applicazione</span><span class="sxs-lookup"><span data-stu-id="c3cb7-102">Create an Application Role</span></span>
  <span data-ttu-id="c3cb7-103">In questo argomento viene descritto come creare un ruolo applicazione in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3cb7-103">This topic describes how to create an application role in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c3cb7-104">I ruoli applicazione limitano l'accesso dell'utente a un database solo tramite applicazioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="c3cb7-104">Application roles restrict user access to a database except through specific applications.</span></span> <span data-ttu-id="c3cb7-105">Poiché i ruoli applicazione non dispongono di utenti, l'elenco **Membri ruolo** non viene visualizzato quando si seleziona **Ruolo applicazione** .</span><span class="sxs-lookup"><span data-stu-id="c3cb7-105">Application roles have no users, so the **Role Members** list is not displayed when **Application role** is selected.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c3cb7-106">In fase di impostazione delle password per i ruoli applicazione viene eseguito il controllo dei requisiti di complessità delle password.</span><span class="sxs-lookup"><span data-stu-id="c3cb7-106">Password complexity is checked when application role passwords are set.</span></span> <span data-ttu-id="c3cb7-107">Le applicazioni che richiamano i ruoli applicazione devono archiviare le relative password.</span><span class="sxs-lookup"><span data-stu-id="c3cb7-107">Applications that invoke application roles must store their passwords.</span></span> <span data-ttu-id="c3cb7-108">Le password dei ruoli applicazione devono essere sempre archiviate in forma crittografata.</span><span class="sxs-lookup"><span data-stu-id="c3cb7-108">Application role passwords should always be stored encrypted.</span></span>  
  
 <span data-ttu-id="c3cb7-109">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="c3cb7-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c3cb7-110">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="c3cb7-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c3cb7-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c3cb7-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c3cb7-112">**Per creare un ruolo applicazione utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="c3cb7-112">**To create an application role, using:**</span></span>  
  
     [<span data-ttu-id="c3cb7-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c3cb7-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c3cb7-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c3cb7-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c3cb7-115">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="c3cb7-115">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c3cb7-116">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c3cb7-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c3cb7-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="c3cb7-117">Permissions</span></span>  
 <span data-ttu-id="c3cb7-118">È richiesta l'autorizzazione ALTER ANY APPLICATION ROLE nel database.</span><span class="sxs-lookup"><span data-stu-id="c3cb7-118">Requires ALTER ANY APPLICATION ROLE permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c3cb7-119">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c3cb7-119">Using SQL Server Management Studio</span></span>  
  
##### <a name="to-create-an-application-role"></a><span data-ttu-id="c3cb7-120">Per creare un ruolo applicazione</span><span class="sxs-lookup"><span data-stu-id="c3cb7-120">To create an application role</span></span>  
  
1.  <span data-ttu-id="c3cb7-121">In Esplora oggetti espandere il database in cui si desidera creare un ruolo applicazione.</span><span class="sxs-lookup"><span data-stu-id="c3cb7-121">In Object Explorer, expand the database where you want to create an application role.</span></span>  
  
2.  <span data-ttu-id="c3cb7-122">Espandere la cartella **Sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="c3cb7-122">Expand the **Security** folder.</span></span>  
  
3.  <span data-ttu-id="c3cb7-123">Espandere la cartella **Ruoli** .</span><span class="sxs-lookup"><span data-stu-id="c3cb7-123">Expand the **Roles** folder.</span></span>  
  
4.  <span data-ttu-id="c3cb7-124">Fare clic con il pulsante destro del mouse sulla cartella **Ruoli applicazione**, quindi scegliere **Nuovo ruolo applicazione...** .</span><span class="sxs-lookup"><span data-stu-id="c3cb7-124">Right-click the **Application Roles** folder and select **New Application Role...**.</span></span>  
  
5.  <span data-ttu-id="c3cb7-125">Nella pagina **Generale** della finestra di dialogo **Ruolo applicazione - Nuovo**immettere il nome del nuovo ruolo applicazione nella casella **Nome ruolo**.</span><span class="sxs-lookup"><span data-stu-id="c3cb7-125">In the **Application Role - New** dialog box, on the **General Page**, enter the new name of the new application role in the **Role name** box.</span></span>  
  
6.  <span data-ttu-id="c3cb7-126">Nella casella **Schema predefinito** specificare lo schema che diventerà proprietario degli oggetti creati da questo ruolo immettendo i nomi degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="c3cb7-126">In the **Default Schema** box, specify the schema that will own objects created by this role by entering the object names.</span></span> <span data-ttu-id="c3cb7-127">In alternativa, fare clic sui puntini di sospensione **(...)** per aprire la finestra di dialogo **Individua schema**.</span><span class="sxs-lookup"><span data-stu-id="c3cb7-127">Alternately, click the ellipsis **(...)** to open the **Locate Schema** dialog box.</span></span>  
  
7.  <span data-ttu-id="c3cb7-128">Nella casella **Password** , immettere una password per il nuovo ruolo.</span><span class="sxs-lookup"><span data-stu-id="c3cb7-128">In the **Password** box, enter a password for the new role.</span></span> <span data-ttu-id="c3cb7-129">Digitare di nuovo la password nella casella **Conferma password** .</span><span class="sxs-lookup"><span data-stu-id="c3cb7-129">Enter that password again into the **Confirm Password** box.</span></span>  
  
8.  <span data-ttu-id="c3cb7-130">In **Schemi di proprietà del ruolo**, selezionare o visualizzare gli schemi che saranno di proprietà di questo ruolo.</span><span class="sxs-lookup"><span data-stu-id="c3cb7-130">Under **Schemas owned by this role**, select or view schemas that will be owned by this role.</span></span> <span data-ttu-id="c3cb7-131">Uno schema può essere di proprietà di un solo schema o ruolo.</span><span class="sxs-lookup"><span data-stu-id="c3cb7-131">A schema can be owned by only one schema or role.</span></span>  
  
9. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="additional-options"></a><span data-ttu-id="c3cb7-132">Opzioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c3cb7-132">Additional Options</span></span>  
 <span data-ttu-id="c3cb7-133">La finestra di dialogo **Ruolo applicazione - Nuovo** offre anche opzioni in altre due pagine: **Entità a protezione diretta** e **Proprietà estese**.</span><span class="sxs-lookup"><span data-stu-id="c3cb7-133">The **Application Role - New** dialog box also offers options on two additional pages: **Securables** and **Extended Properties**.</span></span>  
  
-   <span data-ttu-id="c3cb7-134">Nella pagina **Entità a protezione diretta** sono elencate tutte le possibili entità a protezione diretta e le autorizzazioni su quelle entità a protezione diretta che possono essere concesse all'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="c3cb7-134">The **Securables** page lists all possible securables and the permissions on those securables that can be granted to the login.</span></span>  
  
-   <span data-ttu-id="c3cb7-135">La pagina **Proprietà estese** consente di aggiungere proprietà personalizzate a utenti di database.</span><span class="sxs-lookup"><span data-stu-id="c3cb7-135">The **Extended properties** page allows you to add custom properties to database users.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c3cb7-136">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c3cb7-136">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-application-role"></a><span data-ttu-id="c3cb7-137">Per creare un ruolo applicazione</span><span class="sxs-lookup"><span data-stu-id="c3cb7-137">To create an application role</span></span>  
  
1.  <span data-ttu-id="c3cb7-138">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3cb7-138">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c3cb7-139">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="c3cb7-139">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c3cb7-140">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="c3cb7-140">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates an application role called "weekly_receipts" that has the password "987Gbv876sPYY5m23" and "Sales" as its default schema.  
  
    CREATE APPLICATION ROLE weekly_receipts   
        WITH PASSWORD = '987G^bv876sPY)Y5m23'   
        , DEFAULT_SCHEMA = Sales;  
    GO  
    ```  
  
 <span data-ttu-id="c3cb7-141">Per altre informazioni, vedere [CREATE APPLICATION ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-application-role-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c3cb7-141">For more information, see [CREATE APPLICATION ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-application-role-transact-sql).</span></span>  
  
  
