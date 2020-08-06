---
title: Concedere autorizzazioni per una stored procedure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], permissions
ms.assetid: a7d15816-a788-4099-ad91-dc4b26618299
author: stevestein
ms.author: sstein
ms.openlocfilehash: 23ea130b9d2033128adc99413c053d66936e3ccc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629274"
---
# <a name="grant-permissions-on-a-stored-procedure"></a><span data-ttu-id="886a9-102">Concedere autorizzazioni per una stored procedure</span><span class="sxs-lookup"><span data-stu-id="886a9-102">Grant Permissions on a Stored Procedure</span></span>
  <span data-ttu-id="886a9-103">In questo argomento viene illustrato come concedere autorizzazioni per una stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="886a9-103">This topic describes how to grant permissions on a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="886a9-104">Le autorizzazioni possono essere concesse a un utente, a un ruolo del database o a un ruolo applicazione nel database.</span><span class="sxs-lookup"><span data-stu-id="886a9-104">Permissions can be granted to an existing user, database role, or application role in the database.</span></span>  
  
 <span data-ttu-id="886a9-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="886a9-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="886a9-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="886a9-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="886a9-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="886a9-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="886a9-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="886a9-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="886a9-109">**Per concedere autorizzazioni per una stored procedure utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="886a9-109">**To grant permissions on a stored procedure, using:**</span></span>  
  
     [<span data-ttu-id="886a9-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="886a9-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="886a9-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="886a9-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="886a9-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="886a9-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="886a9-113">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="886a9-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="886a9-114">Non è possibile utilizzare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per concedere autorizzazioni per stored procedure o funzioni di sistema.</span><span class="sxs-lookup"><span data-stu-id="886a9-114">You cannot use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to grant permissions on system procedures or system functions.</span></span> <span data-ttu-id="886a9-115">Utilizzare invece [GRANT - autorizzazioni per oggetti](/sql/t-sql/statements/grant-object-permissions-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="886a9-115">Use [GRANT Object Permissions](/sql/t-sql/statements/grant-object-permissions-transact-sql) instead.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="886a9-116">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="886a9-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="886a9-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="886a9-117">Permissions</span></span>  
 <span data-ttu-id="886a9-118">L'utente che concede le autorizzazioni (o l'entità specificata con l'opzione AS) deve disporre della relativa autorizzazione con GRANT OPTION oppure di un'autorizzazione di livello superiore che include l'autorizzazione che viene concessa.</span><span class="sxs-lookup"><span data-stu-id="886a9-118">The grantor (or the principal specified with the AS option) must have either the permission itself with GRANT OPTION, or a higher permission that implies the permission being granted.</span></span> <span data-ttu-id="886a9-119">È richiesta l'autorizzazione ALTER per lo schema a cui appartiene la stored procedure oppure l'autorizzazione CONTROL per la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="886a9-119">Requires ALTER permission on the schema to which the procedure belongs, or CONTROL permission on the procedure.</span></span> <span data-ttu-id="886a9-120">Per altre informazioni, vedere [GRANT - autorizzazioni per oggetti &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="886a9-120">For more information, see [GRANT Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="886a9-121">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="886a9-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-grant-permissions-on-a-stored-procedure"></a><span data-ttu-id="886a9-122">Per concedere autorizzazioni per una stored procedure</span><span class="sxs-lookup"><span data-stu-id="886a9-122">To grant permissions on a stored procedure</span></span>  
  
1.  <span data-ttu-id="886a9-123">In Esplora oggetti connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)] , quindi espanderla.</span><span class="sxs-lookup"><span data-stu-id="886a9-123">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="886a9-124">Espandere **Database**, espandere il database a cui appartiene la stored procedure, quindi espandere **Programmabilità**.</span><span class="sxs-lookup"><span data-stu-id="886a9-124">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="886a9-125">Espandere **Stored procedure**, fare clic con il pulsante destro del mouse sulla procedura per cui concedere autorizzazioni e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="886a9-125">Expand **Stored Procedures**, right-click the procedure to grant permissions on, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="886a9-126">Da **Proprietà stored procedure**selezionare la pagina **Autorizzazioni** .</span><span class="sxs-lookup"><span data-stu-id="886a9-126">From **Stored Procedure Properties**, select the **Permissions** page.</span></span>  
  
5.  <span data-ttu-id="886a9-127">Per concedere autorizzazioni a un utente, a un ruolo del database o a un ruolo applicazione, fare clic su **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="886a9-127">To grant permissions to a user, database role, or application role, click **Search**.</span></span>  
  
6.  <span data-ttu-id="886a9-128">In **Selezione utenti o ruoli**fare clic su **Tipi di oggetti** per aggiungere o cancellare gli utenti e i ruoli desiderati.</span><span class="sxs-lookup"><span data-stu-id="886a9-128">In **Select Users or Roles**, click **Object Types** to add or clear the users and roles you want.</span></span>  
  
7.  <span data-ttu-id="886a9-129">Fare clic su **Sfoglia** per visualizzare l'elenco di utenti o ruoli.</span><span class="sxs-lookup"><span data-stu-id="886a9-129">Click **Browse** to display the list of users or roles.</span></span> <span data-ttu-id="886a9-130">Selezionare gli utenti o i ruoli a cui concedere le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="886a9-130">Select the users or roles to whom permissions should be granted.</span></span>  
  
8.  <span data-ttu-id="886a9-131">Nella griglia **Autorizzazioni esplicite** selezionare le autorizzazioni da concedere all'utente o al ruolo specificato.</span><span class="sxs-lookup"><span data-stu-id="886a9-131">In the **Explicit Permissions** grid, select the permissions to grant to the specified user or role.</span></span> <span data-ttu-id="886a9-132">Per una descrizione delle autorizzazioni, vedere [Autorizzazioni &#40;Motore di database&#41;](../security/permissions-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="886a9-132">For a description of the permissions, see [Permissions &#40;Database Engine&#41;](../security/permissions-database-engine.md).</span></span>  
  
 <span data-ttu-id="886a9-133">Selezionando **Concedi** al beneficiario verrà assegnata l'autorizzazione specificata.</span><span class="sxs-lookup"><span data-stu-id="886a9-133">Selecting **Grant** indicates the grantee will be given the specified permission.</span></span> <span data-ttu-id="886a9-134">Se si seleziona **Autorizza alla concessione di autorizzazioni** al beneficiario verrà inoltre consentito di concedere l'autorizzazione specificata ad altre entità.</span><span class="sxs-lookup"><span data-stu-id="886a9-134">Selecting **Grant With** indicates that the grantee will also be able to grant the specified permission to other principals.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="886a9-135">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="886a9-135">Using Transact-SQL</span></span>  
  
#### <a name="to-grant-permissions-on-a-stored-procedure"></a><span data-ttu-id="886a9-136">Per concedere autorizzazioni per una stored procedure</span><span class="sxs-lookup"><span data-stu-id="886a9-136">To grant permissions on a stored procedure</span></span>  
  
1.  <span data-ttu-id="886a9-137">Connettersi al [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="886a9-137">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="886a9-138">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="886a9-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="886a9-139">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="886a9-139">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="886a9-140">Nell'esempio viene concessa l'autorizzazione `EXECUTE` per la stored procedure `HumanResources.uspUpdateEmployeeHireInfo` a un ruolo applicazione denominato `Recruiting11`.</span><span class="sxs-lookup"><span data-stu-id="886a9-140">This example grants `EXECUTE` permission on the stored procedure `HumanResources.uspUpdateEmployeeHireInfo` to an application role named `Recruiting11`.</span></span>  
  
```sql  
USE AdventureWorks2012;   
GRANT EXECUTE ON OBJECT::HumanResources.uspUpdateEmployeeHireInfo  
    TO Recruiting11;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="886a9-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="886a9-141">See Also</span></span>  
 <span data-ttu-id="886a9-142">[sys.fn_builtin_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-builtin-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="886a9-142">[sys.fn_builtin_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-builtin-permissions-transact-sql) </span></span>  
 <span data-ttu-id="886a9-143">[GRANT - autorizzazioni per oggetti &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="886a9-143">[GRANT Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql) </span></span>  
 <span data-ttu-id="886a9-144">[Creazione di una stored procedure](../stored-procedures/create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="886a9-144">[Create a Stored Procedure](../stored-procedures/create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="886a9-145">[Modificare una stored procedure](modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="886a9-145">[Modify a Stored Procedure](modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="886a9-146">[Eliminare una stored procedure](../stored-procedures/delete-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="886a9-146">[Delete a Stored Procedure](../stored-procedures/delete-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="886a9-147">Rinominare una stored procedure</span><span class="sxs-lookup"><span data-stu-id="886a9-147">Rename a Stored Procedure</span></span>](rename-a-stored-procedure.md)  
  
  
