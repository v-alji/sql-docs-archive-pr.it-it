---
title: Creare un ruolo del server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.serverrole.members.f1
- SQL12.SWB.SERVERROLE.GENERAL.F1
- sql12.swb.serverrole.memberships.f1
helpviewer_keywords:
- SERVER ROLE, creating
ms.assetid: 74f19992-8082-4ed7-92a1-04fe676ee82d
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 45c3d5bb9c9c7fdae9abe18ab3cb808cae4c1fa1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635995"
---
# <a name="create-a-server-role"></a><span data-ttu-id="754ad-102">Creazione di un ruolo del server</span><span class="sxs-lookup"><span data-stu-id="754ad-102">Create a Server Role</span></span>
  <span data-ttu-id="754ad-103">In questo argomento viene descritto come creare un nuovo ruolo server in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="754ad-103">This topic describes how to create a new server role in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="754ad-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="754ad-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="754ad-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="754ad-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="754ad-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="754ad-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="754ad-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="754ad-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="754ad-108">**Per creare un nuovo ruolo del server utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="754ad-108">**To create a new server role, using:**</span></span>  
  
     [<span data-ttu-id="754ad-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="754ad-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="754ad-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="754ad-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="754ad-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="754ad-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="754ad-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="754ad-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="754ad-113">Non è possibile concedere ai ruoli del server l'autorizzazione sulle entità a protezione diretta a livello di database.</span><span class="sxs-lookup"><span data-stu-id="754ad-113">Server roles cannot be granted permission on database-level securables.</span></span> <span data-ttu-id="754ad-114">Per creare ruoli del database, vedere [CREATE ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-role-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="754ad-114">To create database roles, see [CREATE ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-role-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="754ad-115">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="754ad-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="754ad-116">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="754ad-116">Permissions</span></span>  
  
-   <span data-ttu-id="754ad-117">È richiesta l'autorizzazione CREATE SERVER ROLE o l'appartenenza al ruolo predefinito del server sysadmin.</span><span class="sxs-lookup"><span data-stu-id="754ad-117">Requires CREATE SERVER ROLE permission or membership in the sysadmin fixed server role.</span></span>  
  
-   <span data-ttu-id="754ad-118">È anche richiesta l'autorizzazione IMPERSONATE in *server_principal* per gli account di accesso, l'autorizzazione ALTER per i ruoli del server usati come *server_principal*o l'appartenenza a un gruppo di Windows usato come server_principal.</span><span class="sxs-lookup"><span data-stu-id="754ad-118">Also requires IMPERSONATE on the *server_principal* for logins, ALTER permission for server roles used as the *server_principal*, or membership in a Windows group that is used as the server_principal.</span></span>  
  
-   <span data-ttu-id="754ad-119">Se si utilizza l'opzione AUTHORIZATION per assegnare la proprietà del ruolo del server, sono necessarie anche le autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="754ad-119">When you use the AUTHORIZATION option to assign server role ownership, the following permissions are also required:</span></span>  
  
    -   <span data-ttu-id="754ad-120">Per assegnare la proprietà di un ruolo del server a un altro account di accesso, è richiesta l'autorizzazione IMPERSONATE per tale account di accesso.</span><span class="sxs-lookup"><span data-stu-id="754ad-120">To assign ownership of a server role to another login, requires IMPERSONATE permission on that login.</span></span>  
  
    -   <span data-ttu-id="754ad-121">Per assegnare la proprietà di un ruolo del server a un altro ruolo del server, è richiesta l'appartenenza al ruolo del server destinatario oppure l'autorizzazione ALTER per tale ruolo.</span><span class="sxs-lookup"><span data-stu-id="754ad-121">To assign ownership of a server role to another server role, requires membership in the recipient server role or ALTER permission on that server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="754ad-122">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="754ad-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-new-server-role"></a><span data-ttu-id="754ad-123">Per creare un nuovo ruolo del server</span><span class="sxs-lookup"><span data-stu-id="754ad-123">To create a new server role</span></span>  
  
1.  <span data-ttu-id="754ad-124">In Esplora oggetti espandere il server in cui si desidera creare il nuovo ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="754ad-124">In Object Explorer, expand the server where you want to create the new server role.</span></span>  
  
2.  <span data-ttu-id="754ad-125">Espandere la cartella **Sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="754ad-125">Expand the **Security** folder.</span></span>  
  
3.  <span data-ttu-id="754ad-126">Fare clic con il pulsante destro del mouse sulla cartella **Ruoli server** e selezionare **Nuovo ruolo server**.</span><span class="sxs-lookup"><span data-stu-id="754ad-126">Right-click the **Server Roles** folder and select **New Server Role...**.</span></span>  
  
4.  <span data-ttu-id="754ad-127">Nella finestra di dialogo **nuovo ruolo server-**_server_role_name_ , nella pagina **generale** , immettere un nome per il nuovo ruolo del server nella casella **nome ruolo server** .</span><span class="sxs-lookup"><span data-stu-id="754ad-127">In the **New Server Role -**_server_role_name_ dialog box, on the **General** page, enter a name for the new server role in the **Server role name** box.</span></span>  
  
5.  <span data-ttu-id="754ad-128">Nella casella **Proprietario** immettere il nome dell'entità del server proprietaria del nuovo ruolo.</span><span class="sxs-lookup"><span data-stu-id="754ad-128">In the **Owner** box, enter the name of the server principal that will own the new role.</span></span> <span data-ttu-id="754ad-129">In alternativa, fare clic sui puntini di sospensione **(...)** per aprire la finestra di dialogo **Seleziona account di accesso o ruolo server**.</span><span class="sxs-lookup"><span data-stu-id="754ad-129">Alternately, click the ellipsis **(...)** to open the **Select Server Login or Role** dialog box.</span></span>  
  
6.  <span data-ttu-id="754ad-130">In **Entità a protezione diretta**selezionare una o più entità a protezione diretta a livello di server.</span><span class="sxs-lookup"><span data-stu-id="754ad-130">Under **Securables**, select one or more server-level securables.</span></span> <span data-ttu-id="754ad-131">Quando è selezionata un'entità a protezione diretta, al ruolo del server è possibile concedere o negare autorizzazioni per tale entità.</span><span class="sxs-lookup"><span data-stu-id="754ad-131">When a securable is selected, this server role can be granted or denied permissions on that securable.</span></span>  
  
7.  <span data-ttu-id="754ad-132">Nella casella **Autorizzazioni: Esplicite** selezionare la casella di controllo per concedere, concedere con concessione o negare autorizzazioni al ruolo del server per le entità a protezione diretta selezionate.</span><span class="sxs-lookup"><span data-stu-id="754ad-132">In the **Permissions: Explicit** box, select the check box to grant, grant with grant, or deny permission to this server role for the selected securables.</span></span> <span data-ttu-id="754ad-133">Se un'autorizzazione non può essere concessa o negata a tutte le entità a protezione diretta selezionate, l'autorizzazione viene rappresentata come selezione parziale.</span><span class="sxs-lookup"><span data-stu-id="754ad-133">If a permission cannot be granted or denied to all of the selected securables, the permission is represented as a partial select.</span></span>  
  
8.  <span data-ttu-id="754ad-134">Nella pagina **Membri** utilizzare il pulsante **Aggiungi** per aggiungere account di accesso che rappresentano singoli utenti o gruppi al nuovo ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="754ad-134">On the **Members** page, use the **Add** button to add logins that represent individuals or groups to the new server role.</span></span>  
  
9. <span data-ttu-id="754ad-135">Un ruolo del server definito dall'utente può essere membro di un altro ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="754ad-135">A user-defined server role can be a member of another server role.</span></span> <span data-ttu-id="754ad-136">Nella pagina **Appartenenze** selezionare una casella di controllo per impostare il ruolo del server definito dall'utente corrente come membro di un ruolo del server selezionato.</span><span class="sxs-lookup"><span data-stu-id="754ad-136">On the **Memberships** page, select a check box to make the current user-defined server role a member of a selected server role.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="754ad-137">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="754ad-137">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-new-server-role"></a><span data-ttu-id="754ad-138">Per creare un nuovo ruolo del server</span><span class="sxs-lookup"><span data-stu-id="754ad-138">To create a new server role</span></span>  
  
1.  <span data-ttu-id="754ad-139">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="754ad-139">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="754ad-140">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="754ad-140">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="754ad-141">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="754ad-141">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    --Creates the server role auditors that is owned the securityadmin fixed server role.  
    USE master;  
    CREATE SERVER ROLE auditors AUTHORIZATION securityadmin;  
    GO  
    ```  
  
 <span data-ttu-id="754ad-142">Per altre informazioni, vedere [CREATE SERVER ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-role-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="754ad-142">For more information, see [CREATE SERVER ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-role-transact-sql).</span></span>  
  
  
